# ScoStreamQueue_Add(_SCO_STREAM_QUEUE *,_IRP *)

- ea: `0x14014324c`
- end: `0x1401433c8`
- name: `?ScoStreamQueue_Add@@YAJPEAU_SCO_STREAM_QUEUE@@PEAU_IRP@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(struct _SCO_STREAM_QUEUE *, struct _IRP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140145158`
- `0x1401452b8`

## callees

- `0x14000bdb8`
- `0x14014324c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401432b6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401432b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140143265`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140143265`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401433aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401433aa`

## pseudocode

```c
__int64 __fastcall ScoStreamQueue_Add(struct _SCO_STREAM_QUEUE *a1, struct _IRP *a2)
{
  KIRQL v4; // al
  int v5; // edx
  int AbortStatus; // edi
  KIRQL v7; // r15
  _IO_SECURITY_CONTEXT *SecurityContext; // rdi
  _SECURITY_QUALITY_OF_SERVICE *SecurityQos; // rcx
  _ACCESS_STATE *v10; // rbp
  unsigned int DataSize; // r8d
  int AccessState_high; // r9d
  unsigned int v13; // r14d
  __int16 DeviceType; // ax
  _LIST_ENTRY *Blink; // rcx

  v4 = KeAcquireSpinLockRaiseToDpc(a1->LockedList.ListLock);
  AbortStatus = a1->AbortStatus;
  v7 = v4;
  if ( AbortStatus >= 0 )
  {
    SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
    SecurityQos = SecurityContext[6].SecurityQos;
    if ( (*(&SecurityQos->EffectiveOnly + 1) & 5) != 0 )
      v10 = *(_ACCESS_STATE **)&SecurityQos[2].Length;
    else
      v10 = (_ACCESS_STATE *)MmMapLockedPagesSpecifyCache((PMDL)SecurityQos, 0, MmCached, 0, 0, 0x40000010u);
    if ( v10 )
    {
      DataSize = a1->DataSize;
      AccessState_high = HIDWORD(SecurityContext[5].AccessState);
      v13 = AccessState_high + DataSize;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        LOBYTE(v5) = 0;
      DeviceType = WPP_GLOBAL_Control->DeviceType;
      if ( (_BYTE)v5 || DeviceType )
      {
        LOBYTE(DataSize) = DeviceType != 0;
        WPP_RECORDER_AND_TRACE_SF_qLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v5,
          DataSize,
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          4,
          10,
          (__int64)WPP_311ed0e083403915a5ce25981feb8787_Traceguids,
          (char)SecurityContext,
          AccessState_high,
          a1->DataSize);
      }
      if ( v13 >= a1->DataSize )
      {
        a1->DataSize = v13;
        SecurityContext[2].DesiredAccess = 0;
        SecurityContext[2].AccessState = v10;
        Blink = a1->LockedList.ListHead.Blink;
        if ( (struct _SCO_STREAM_QUEUE *)Blink->Flink != a1 )
          __fastfail(3u);
        AbortStatus = 259;
        a2->Tail.Overlay.ListEntry.Flink = &a1->LockedList.ListHead;
        a2->Tail.Overlay.ListEntry.Blink = Blink;
        Blink->Flink = &a2->Tail.Overlay.ListEntry;
        a1->LockedList.ListHead.Blink = &a2->Tail.Overlay.ListEntry;
        ++a1->LockedList.Count;
        a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        a2->IoStatus.Status = 259;
      }
      else
      {
        AbortStatus = -2147483643;
      }
    }
    else
    {
      AbortStatus = -1073741670;
    }
  }
  KeReleaseSpinLock(a1->LockedList.ListLock, v7);
  return (unsigned int)AbortStatus;
}

```

## disassembly

```asm
0x14014324c  push    rbx
0x14014324e  push    rbp
0x14014324f  push    rsi
0x140143250  push    rdi
0x140143251  push    r12
0x140143253  push    r14
0x140143255  push    r15
0x140143257  sub     rsp, 60h
0x14014325b  mov     rbx, rcx
0x14014325e  mov     rsi, rdx
0x140143261  mov     rcx, [rcx+18h]; SpinLock
0x140143265  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14014326c  nop     dword ptr [rax+rax+00h]
0x140143271  mov     edi, [rbx+2Ch]
0x140143274  xor     r12d, r12d
0x140143277  mov     r15b, al
0x14014327a  test    edi, edi
0x14014327c  js      loc_1401433A3
0x140143282  mov     rax, [rsi+0B8h]
0x140143289  mov     rdi, [rax+8]
0x14014328d  mov     rcx, [rdi+90h]; MemoryDescriptorList
0x140143294  test    byte ptr [rcx+0Ah], 5
0x140143298  jz      short loc_1401432A0
0x14014329a  mov     rbp, [rcx+18h]
0x14014329e  jmp     short loc_1401432C5
0x1401432a0  xor     r9d, r9d; RequestedAddress
0x1401432a3  mov     [rsp+98h+Priority], 40000010h; Priority
0x1401432ab  xor     edx, edx; AccessMode
0x1401432ad  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x1401432b2  lea     r8d, [r9+1]; CacheType
0x1401432b6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1401432bd  nop     dword ptr [rax+rax+00h]
0x1401432c2  mov     rbp, rax
0x1401432c5  test    rbp, rbp
0x1401432c8  jnz     short loc_1401432D4
0x1401432ca  mov     edi, 0C000009Ah
0x1401432cf  jmp     loc_1401433A3
0x1401432d4  mov     r8d, [rbx+28h]
0x1401432d8  mov     r9d, [rdi+84h]
0x1401432df  lea     r14d, [r9+r8]
0x1401432e3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401432ea  mov     eax, [rcx+2Ch]
0x1401432ed  test    al, 8
0x1401432ef  jz      short loc_1401432F9
0x1401432f1  cmp     byte ptr [rcx+29h], 5
0x1401432f5  mov     dl, 1
0x1401432f7  jnb     short loc_1401432FC
0x1401432f9  mov     dl, r12b
0x1401432fc  movzx   eax, word ptr [rcx+48h]
0x140143300  test    ax, ax
0x140143303  setnz   r10b
0x140143307  test    dl, dl
0x140143309  jnz     short loc_140143310
0x14014330b  test    ax, ax
0x14014330e  jz      short loc_14014334F
0x140143310  mov     [rsp+98h+var_48], r8d
0x140143315  lea     rax, WPP_311ed0e083403915a5ce25981feb8787_Traceguids
0x14014331c  mov     [rsp+98h+var_50], r9d
0x140143321  mov     r8b, r10b
0x140143324  mov     r9, [rcx+40h]
0x140143328  mov     rcx, [rcx+18h]
0x14014332c  mov     [rsp+98h+var_58], rdi
0x140143331  mov     [rsp+98h+var_60], rax
0x140143336  mov     [rsp+98h+var_68], 0Ah
0x14014333d  mov     [rsp+98h+Priority], 4
0x140143345  mov     byte ptr [rsp+98h+BugCheckOnFailure], 5
0x14014334a  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x14014334f  cmp     r14d, [rbx+28h]
0x140143353  jnb     short loc_14014335C
0x140143355  mov     edi, 80000005h
0x14014335a  jmp     short loc_1401433A3
0x14014335c  mov     [rbx+28h], r14d
0x140143360  mov     [rdi+40h], r12d
0x140143364  mov     [rdi+38h], rbp
0x140143368  mov     rcx, [rbx+8]
0x14014336c  cmp     [rcx], rbx
0x14014336f  jz      short loc_140143378
0x140143371  mov     ecx, 3
0x140143376  int     29h; Win8: RtlFailFast(ecx)
0x140143378  lea     rax, [rsi+0A8h]
0x14014337f  mov     edi, 103h
0x140143384  mov     [rax], rbx
0x140143387  mov     [rax+8], rcx
0x14014338b  mov     [rcx], rax
0x14014338e  mov     [rbx+8], rax
0x140143392  inc     dword ptr [rbx+20h]
0x140143395  mov     rax, [rsi+0B8h]
0x14014339c  or      byte ptr [rax+3], 1
0x1401433a0  mov     [rsi+30h], edi
0x1401433a3  mov     rcx, [rbx+18h]; SpinLock
0x1401433a7  mov     dl, r15b; NewIrql
0x1401433aa  call    cs:__imp_KeReleaseSpinLock
0x1401433b1  nop     dword ptr [rax+rax+00h]
0x1401433b6  mov     eax, edi
0x1401433b8  add     rsp, 60h
0x1401433bc  pop     r15
0x1401433be  pop     r14
0x1401433c0  pop     r12
0x1401433c2  pop     rdi
0x1401433c3  pop     rsi
0x1401433c4  pop     rbp
0x1401433c5  pop     rbx
0x1401433c6  retn
```

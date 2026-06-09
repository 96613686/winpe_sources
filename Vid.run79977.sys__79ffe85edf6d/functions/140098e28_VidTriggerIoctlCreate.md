# VidTriggerIoctlCreate

- ea: `0x140098e28`
- end: `0x1400990d2`
- name: `VidTriggerIoctlCreate`
- size: `682`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x1400248f4`
- `0x140030990`
- `0x1400309d0`
- `0x1400386a0`
- `0x140098e28`
- `0x140099688`
- `0x140099950`
- `0x1400999b0`
- `0x1400f1ea0`

## import_xrefs

- `ntoskrnl!ExEventObjectType` at `0x140098f71`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140098f8c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140098f8c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140098efb`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140098efb`
- `ntoskrnl!ExCreateDpcEvent` at `0x140098f2e`
- `ntoskrnl!ExCreateDpcEvent` at `0x140098f2e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140099086`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140099086`
- `ntoskrnl!ExQueueDpcEventWait` at `0x140099098`
- `ntoskrnl!ExQueueDpcEventWait` at `0x140099098`
- `ntoskrnl!ZwClose` at `0x14009903b`
- `ntoskrnl!ZwClose` at `0x14009903b`
- `ntoskrnl!KeInitializeDpc` at `0x140098f15`
- `ntoskrnl!KeInitializeDpc` at `0x140098f15`
- `ntoskrnl!ExAllocatePool2` at `0x140098e92`
- `ntoskrnl!ExAllocatePool2` at `0x140098e92`

## string_xrefs

- `0x140098e71`: `VidTriggerIoctlCreate`
- `0x140098eb8`: `VidTriggerIoctlCreate`
- `0x140098f4d`: `VidTriggerIoctlCreate`
- `0x140098fab`: `VidTriggerIoctlCreate`
- `0x140098fd9`: `VidTriggerIoctlCreate`
- `0x14009901d`: `VidTriggerIoctlCreate`
- `0x140099074`: `VidTriggerIoctlCreate`

## pseudocode

```c
__int64 __fastcall VidTriggerIoctlCreate(__int64 a1, _OWORD *a2, _QWORD *a3, HANDLE *a4)
{
  struct _EX_RUNDOWN_REF *Pool2; // rdi
  NTSTATUS Entry; // ebx
  __int128 v10; // xmm1
  HANDLE v11; // rcx
  HANDLE Handle; // [rsp+40h] [rbp-68h] BYREF
  PVOID Object; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v15[11]; // [rsp+50h] [rbp-58h] BYREF

  Pool2 = 0;
  Object = 0;
  v15[0] = 0;
  Handle = 0;
  Entry = VidTriggerpValidateParameters(a2);
  if ( Entry >= 0 )
  {
    Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(64, 200, 1917084758);
    if ( Pool2 )
    {
      Pool2->Count = *(ULONG_PTR *)(a1 + 648);
      *(_OWORD *)&Pool2[13].Count = *a2;
      v10 = a2[1];
      LODWORD(Pool2[17].Count) |= 0xFFFFFFu;
      Pool2[20].Count = -1;
      *(_OWORD *)&Pool2[15].Count = v10;
      ExInitializeRundownProtection(Pool2 + 11);
      KeInitializeDpc((PRKDPC)&Pool2[3], VidTriggerpDpcRoutine, Pool2);
      Entry = ExCreateDpcEvent(&Pool2[2], &Object, &Pool2[3]);
      if ( Entry >= 0 )
      {
        Entry = ObOpenObjectByPointer(Object, 0, 0, 2u, (POBJECT_TYPE)ExEventObjectType, 0, &Handle);
        if ( Entry >= 0 )
        {
          if ( *(_DWORD *)a2 == 3 && (Entry = VidTriggerpCreatePort(Pool2), Entry < 0) )
          {
            VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 260);
          }
          else
          {
            VidLockAcquireExclusive(a1 + 3368);
            Entry = VidHandleTableAllocateEntry(a1 + 3336, Pool2, v15);
            if ( Entry >= 0 )
            {
              ExAcquireRundownProtection(Pool2 + 11);
              ExQueueDpcEventWait(Pool2[2].Count, 0);
              VidLockRelease(a1 + 3368);
              Entry = 0;
              *a3 = v15[0];
              *a4 = Handle;
              return (unsigned int)Entry;
            }
            VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 273);
            VidLockRelease(a1 + 3368);
          }
        }
        else
        {
          VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 248);
        }
      }
      else
      {
        VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 234);
      }
    }
    else
    {
      Entry = -1073741670;
      VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 221);
    }
  }
  else
  {
    VidTraceErrorInternal0("VidTriggerIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 213);
  }
  v11 = Handle;
  if ( Handle )
    ZwClose(Handle);
  if ( Pool2 )
    VidTriggerpFree(v11, Pool2);
  VidTraceErrorStatusPartitionInternal0(
    (unsigned int)"VidTriggerIoctlCreate",
    (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidtrigger.c",
    314,
    Entry,
    a1 + 656);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x140098e28  push    rbx
0x140098e2a  push    rbp
0x140098e2b  push    rsi
0x140098e2c  push    rdi
0x140098e2d  push    r12
0x140098e2f  push    r13
0x140098e31  push    r14
0x140098e33  push    r15
0x140098e35  sub     rsp, 68h
0x140098e39  xor     edi, edi
0x140098e3b  mov     rbp, rcx
0x140098e3e  mov     rcx, rdx
0x140098e41  mov     [rsp+0A8h+Object], rdi
0x140098e46  mov     [rsp+0A8h+var_58], rdi
0x140098e4b  mov     r14, r9
0x140098e4e  mov     [rsp+0A8h+var_68], rdi
0x140098e53  mov     r15, r8
0x140098e56  mov     rsi, rdx
0x140098e59  call    VidTriggerpValidateParameters
0x140098e5e  mov     ebx, eax
0x140098e60  test    eax, eax
0x140098e62  jns     short loc_140098E82
0x140098e64  mov     r8d, 0D5h
0x140098e6a  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140098e71  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140098e78  call    VidTraceErrorInternal0
0x140098e7d  jmp     loc_140099031
0x140098e82  mov     edx, 0C8h
0x140098e87  mov     ecx, 40h ; '@'
0x140098e8c  mov     r8d, 72446456h
0x140098e92  call    cs:__imp_ExAllocatePool2
0x140098e99  nop     dword ptr [rax+rax+00h]
0x140098e9e  mov     rdi, rax
0x140098ea1  test    rax, rax
0x140098ea4  jnz     short loc_140098EC9
0x140098ea6  mov     ebx, 0C000009Ah
0x140098eab  mov     r8d, 0DDh
0x140098eb1  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140098eb8  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140098ebf  call    VidTraceErrorInternal0
0x140098ec4  jmp     loc_140099031
0x140098ec9  mov     rax, [rbp+288h]
0x140098ed0  lea     rcx, [rdi+58h]; RunRef
0x140098ed4  mov     [rdi], rax
0x140098ed7  movups  xmm0, xmmword ptr [rsi]
0x140098eda  movups  xmmword ptr [rdi+68h], xmm0
0x140098ede  movups  xmm1, xmmword ptr [rsi+10h]
0x140098ee2  or      dword ptr [rdi+88h], 0FFFFFFh
0x140098eec  mov     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x140098ef7  movups  xmmword ptr [rdi+78h], xmm1
0x140098efb  call    cs:__imp_ExInitializeRundownProtection
0x140098f02  nop     dword ptr [rax+rax+00h]
0x140098f07  mov     r8, rdi; DeferredContext
0x140098f0a  lea     rdx, VidTriggerpDpcRoutine; DeferredRoutine
0x140098f11  lea     rcx, [rdi+18h]; Dpc
0x140098f15  call    cs:__imp_KeInitializeDpc
0x140098f1c  nop     dword ptr [rax+rax+00h]
0x140098f21  lea     r8, [rdi+18h]
0x140098f25  lea     rdx, [rsp+0A8h+Object]
0x140098f2a  lea     rcx, [rdi+10h]
0x140098f2e  call    cs:__imp_ExCreateDpcEvent
0x140098f35  nop     dword ptr [rax+rax+00h]
0x140098f3a  mov     ebx, eax
0x140098f3c  test    eax, eax
0x140098f3e  jns     short loc_140098F5E
0x140098f40  mov     r8d, 0EAh
0x140098f46  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140098f4d  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140098f54  call    VidTraceErrorInternal0
0x140098f59  jmp     loc_140099031
0x140098f5e  lea     rax, [rsp+0A8h+var_68]
0x140098f63  mov     r9d, 2; DesiredAccess
0x140098f69  mov     [rsp+0A8h+Handle], rax; Handle
0x140098f6e  xor     r8d, r8d; PassedAccessState
0x140098f71  mov     rax, cs:ExEventObjectType
0x140098f78  xor     edx, edx; HandleAttributes
0x140098f7a  mov     [rsp+0A8h+AccessMode], 0; AccessMode
0x140098f7f  mov     rcx, [rax]
0x140098f82  mov     [rsp+0A8h+ObjectType], rcx; ObjectType
0x140098f87  mov     rcx, [rsp+0A8h+Object]; Object
0x140098f8c  call    cs:__imp_ObOpenObjectByPointer
0x140098f93  nop     dword ptr [rax+rax+00h]
0x140098f98  mov     ebx, eax
0x140098f9a  test    eax, eax
0x140098f9c  jns     short loc_140098FB9
0x140098f9e  mov     r8d, 0F8h
0x140098fa4  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140098fab  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140098fb2  call    VidTraceErrorInternal0
0x140098fb7  jmp     short loc_140099031
0x140098fb9  cmp     dword ptr [rsi], 3
0x140098fbc  jnz     short loc_140098FE7
0x140098fbe  mov     rcx, rdi
0x140098fc1  call    VidTriggerpCreatePort
0x140098fc6  mov     ebx, eax
0x140098fc8  test    eax, eax
0x140098fca  jns     short loc_140098FE7
0x140098fcc  mov     r8d, 104h
0x140098fd2  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140098fd9  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140098fe0  call    VidTraceErrorInternal0
0x140098fe5  jmp     short loc_140099031
0x140098fe7  lea     rsi, [rbp+0D28h]
0x140098fee  mov     rcx, rsi
0x140098ff1  call    VidLockAcquireExclusive
0x140098ff6  lea     rcx, [rbp+0D08h]
0x140098ffd  mov     rdx, rdi
0x140099000  lea     r8, [rsp+0A8h+var_58]
0x140099005  call    VidHandleTableAllocateEntry
0x14009900a  mov     ebx, eax
0x14009900c  test    eax, eax
0x14009900e  jns     short loc_140099082
0x140099010  mov     r8d, 111h
0x140099016  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x14009901d  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x140099024  call    VidTraceErrorInternal0
0x140099029  mov     rcx, rsi
0x14009902c  call    VidLockRelease
0x140099031  mov     rcx, [rsp+0A8h+var_68]; Handle
0x140099036  test    rcx, rcx
0x140099039  jz      short loc_140099047
0x14009903b  call    cs:__imp_ZwClose
0x140099042  nop     dword ptr [rax+rax+00h]
0x140099047  test    rdi, rdi
0x14009904a  jz      short loc_140099054
0x14009904c  mov     rdx, rdi
0x14009904f  call    VidTriggerpFree
0x140099054  test    ebx, ebx
0x140099056  jns     short loc_1400990BE
0x140099058  lea     rax, [rbp+290h]
0x14009905f  mov     r9d, ebx
0x140099062  mov     r8d, 13Ah
0x140099068  mov     [rsp+0A8h+ObjectType], rax
0x14009906d  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140099074  lea     rcx, aVidtriggerioct_3; "VidTriggerIoctlCreate"
0x14009907b  call    VidTraceErrorStatusPartitionInternal0
0x140099080  jmp     short loc_1400990BE
0x140099082  lea     rcx, [rdi+58h]; RunRef
0x140099086  call    cs:__imp_ExAcquireRundownProtection
0x14009908d  nop     dword ptr [rax+rax+00h]
0x140099092  mov     rcx, [rdi+10h]
0x140099096  xor     edx, edx
0x140099098  call    cs:__imp_ExQueueDpcEventWait
0x14009909f  nop     dword ptr [rax+rax+00h]
0x1400990a4  mov     rcx, rsi
0x1400990a7  call    VidLockRelease
0x1400990ac  mov     rax, [rsp+0A8h+var_58]
0x1400990b1  xor     ebx, ebx
0x1400990b3  mov     [r15], rax
0x1400990b6  mov     rax, [rsp+0A8h+var_68]
0x1400990bb  mov     [r14], rax
0x1400990be  mov     eax, ebx
0x1400990c0  add     rsp, 68h
0x1400990c4  pop     r15
0x1400990c6  pop     r14
0x1400990c8  pop     r13
0x1400990ca  pop     r12
0x1400990cc  pop     rdi
0x1400990cd  pop     rsi
0x1400990ce  pop     rbp
0x1400990cf  pop     rbx
0x1400990d0  retn
```

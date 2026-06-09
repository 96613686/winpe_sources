# MbbWorkMgrCleanup(void *)

- ea: `0x140023db0`
- end: `0x140023f46`
- name: `?MbbWorkMgrCleanup@@YAXPEAX@Z`
- size: `406`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140006aa4`
- `0x1400196ac`
- `0x14001a2a4`
- `0x140023f4c`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x14001dd20`
- `0x140023db0`

## import_xrefs

- `ntoskrnl!PsThreadType` at `0x140023e38`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023e66`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023e66`
- `ntoskrnl!ZwClose` at `0x140023f10`
- `ntoskrnl!ZwClose` at `0x140023f10`
- `ntoskrnl!KeSetEvent` at `0x140023dd5`
- `ntoskrnl!KeSetEvent` at `0x140023dd5`
- `ntoskrnl!ObfDereferenceObject` at `0x140023ed0`
- `ntoskrnl!ObfDereferenceObject` at `0x140023ed0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140023e8f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140023e8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023f2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023f2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023de7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023de7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023dbd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023dbd`

## pseudocode

```c
void __fastcall MbbWorkMgrCleanup(PVOID P)
{
  int v2; // edx
  void *v3; // rcx
  NTSTATUS v4; // eax
  int v5; // edx
  PVOID v6; // rdi
  NTSTATUS v7; // eax
  int v8; // edx
  char *v9; // rcx
  PVOID Object; // [rsp+60h] [rbp+8h] BYREF

  *((_BYTE *)P + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P);
  KeSetEvent((PRKEVENT)P + 1, 0, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)P, *((_BYTE *)P + 8));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      9,
      14,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
  }
  v3 = (void *)*((_QWORD *)P + 11);
  if ( v3 )
  {
    Object = 0;
    v4 = ObReferenceObjectByHandle(v3, 0xF0000u, (POBJECT_TYPE)PsThreadType, 0, &Object, 0);
    if ( v4 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          9,
          16,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          v4);
      }
    }
    else
    {
      v6 = Object;
      v7 = KeWaitForSingleObject(Object, Executive, 0, 1u, 0);
      if ( v7 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          9,
          15,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          v7);
      }
      ObfDereferenceObject(v6);
    }
    ZwClose(*((HANDLE *)P + 11));
  }
  v9 = (char *)*((_QWORD *)P + 2);
  if ( v9 )
    MbbAllocMgrCleanup(v9);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140023db0  push    rbx
0x140023db2  push    rbp
0x140023db3  push    rdi
0x140023db4  push    r15
0x140023db6  sub     rsp, 38h
0x140023dba  mov     rbx, rcx
0x140023dbd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140023dc4  nop     dword ptr [rax+rax+00h]
0x140023dc9  lea     rcx, [rbx+18h]; Event
0x140023dcd  xor     r8d, r8d; Wait
0x140023dd0  xor     edx, edx; Increment
0x140023dd2  mov     [rbx+8], al
0x140023dd5  call    cs:__imp_KeSetEvent
0x140023ddc  nop     dword ptr [rax+rax+00h]
0x140023de1  mov     dl, [rbx+8]; NewIrql
0x140023de4  mov     rcx, rbx; SpinLock
0x140023de7  call    cs:__imp_KeReleaseSpinLock
0x140023dee  nop     dword ptr [rax+rax+00h]
0x140023df3  lea     rbp, WPP_RECORDER_INITIALIZED
0x140023dfa  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140023e01  lea     r15, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140023e08  jz      short loc_140023E2B
0x140023e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e11  mov     r9d, 0Eh
0x140023e17  mov     dl, 4
0x140023e19  mov     [rsp+58h+Object], r15
0x140023e1e  mov     rcx, [rcx+40h]
0x140023e22  lea     r8d, [r9-5]
0x140023e26  call    WPP_RECORDER_SF_
0x140023e2b  mov     rcx, [rbx+58h]; Handle
0x140023e2f  test    rcx, rcx
0x140023e32  jz      loc_140023F1C
0x140023e38  mov     r8, cs:__imp_PsThreadType
0x140023e3f  lea     rax, [rsp+58h+arg_0]
0x140023e44  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x140023e4d  xor     r9d, r9d; AccessMode
0x140023e50  mov     edx, 0F0000h; DesiredAccess
0x140023e55  mov     [rsp+58h+arg_0], 0
0x140023e5e  mov     [rsp+58h+Object], rax; Object
0x140023e63  mov     r8, [r8]; ObjectType
0x140023e66  call    cs:__imp_ObReferenceObjectByHandle
0x140023e6d  nop     dword ptr [rax+rax+00h]
0x140023e72  test    eax, eax
0x140023e74  js      short loc_140023EDE
0x140023e76  mov     rdi, [rsp+58h+arg_0]
0x140023e7b  mov     r9b, 1; Alertable
0x140023e7e  mov     rcx, rdi; Object
0x140023e81  mov     [rsp+58h+Object], 0; Timeout
0x140023e8a  xor     r8d, r8d; WaitMode
0x140023e8d  xor     edx, edx; WaitReason
0x140023e8f  call    cs:__imp_KeWaitForSingleObject
0x140023e96  nop     dword ptr [rax+rax+00h]
0x140023e9b  test    eax, eax
0x140023e9d  jz      short loc_140023ECD
0x140023e9f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140023ea6  jz      short loc_140023ECD
0x140023ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x140023eaf  mov     r9d, 0Fh
0x140023eb5  mov     dword ptr [rsp+58h+HandleInformation], eax
0x140023eb9  mov     dl, 2
0x140023ebb  mov     [rsp+58h+Object], r15
0x140023ec0  mov     rcx, [rcx+40h]
0x140023ec4  lea     r8d, [r9-6]
0x140023ec8  call    WPP_RECORDER_SF_d
0x140023ecd  mov     rcx, rdi; Object
0x140023ed0  call    cs:__imp_ObfDereferenceObject
0x140023ed7  nop     dword ptr [rax+rax+00h]
0x140023edc  jmp     short loc_140023F0C
0x140023ede  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140023ee5  jz      short loc_140023F0C
0x140023ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x140023eee  mov     r9d, 10h
0x140023ef4  mov     dword ptr [rsp+58h+HandleInformation], eax
0x140023ef8  mov     dl, 2
0x140023efa  mov     [rsp+58h+Object], r15
0x140023eff  mov     rcx, [rcx+40h]
0x140023f03  lea     r8d, [r9-7]
0x140023f07  call    WPP_RECORDER_SF_d
0x140023f0c  mov     rcx, [rbx+58h]; Handle
0x140023f10  call    cs:__imp_ZwClose
0x140023f17  nop     dword ptr [rax+rax+00h]
0x140023f1c  mov     rcx, [rbx+10h]; P
0x140023f20  test    rcx, rcx
0x140023f23  jz      short loc_140023F2A
0x140023f25  call    ?MbbAllocMgrCleanup@@YAXPEAX@Z; MbbAllocMgrCleanup(void *)
0x140023f2a  xor     edx, edx; Tag
0x140023f2c  mov     rcx, rbx; P
0x140023f2f  call    cs:__imp_ExFreePoolWithTag
0x140023f36  nop     dword ptr [rax+rax+00h]
0x140023f3b  add     rsp, 38h
0x140023f3f  pop     r15
0x140023f41  pop     rdi
0x140023f42  pop     rbp
0x140023f43  pop     rbx
0x140023f44  retn
```

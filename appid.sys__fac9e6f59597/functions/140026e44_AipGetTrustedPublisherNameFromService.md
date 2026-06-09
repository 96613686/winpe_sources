# AipGetTrustedPublisherNameFromService

- ea: `0x140026e44`
- end: `0x140026fc7`
- name: `AipGetTrustedPublisherNameFromService`
- size: `387`
- prototype: `__int64 __fastcall(HANDLE SourceHandle, __int64, struct _UNICODE_STRING *, _BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140025560`

## callees

- `0x140003878`
- `0x140006a20`
- `0x140026e44`
- `0x1400328b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026f9e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026f9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026e94`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026e94`
- `ntoskrnl!ObCloseHandle` at `0x140026f63`
- `ntoskrnl!ObCloseHandle` at `0x140026f63`
- `ntoskrnl!ZwDuplicateObject` at `0x140026efb`
- `ntoskrnl!ZwDuplicateObject` at `0x140026efb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026ea9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026ea9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026f92`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026f92`
- `ntoskrnl!KeStackAttachProcess` at `0x140026f51`
- `ntoskrnl!KeStackAttachProcess` at `0x140026f51`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140026f73`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140026f73`
- `ntoskrnl!RtlInitUnicodeString` at `0x140026f3a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140026f3a`

## pseudocode

```c
__int64 __fastcall AipGetTrustedPublisherNameFromService(
        HANDLE SourceHandle,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        _BYTE *a4)
{
  NTSTATUS v8; // ebx
  void *TargetHandle; // [rsp+40h] [rbp-19h] BYREF
  PCWSTR SourceString; // [rsp+48h] [rbp-11h] BYREF
  _KAPC_STATE ApcState; // [rsp+50h] [rbp-9h] BYREF

  TargetHandle = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  SourceString = 0;
  *a4 = 1;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&AipServiceContext, 0);
  if ( *(&Binding + 1) && Binding )
  {
    v8 = ZwDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, SourceHandle, TargetProcessHandle, &TargetHandle, 0, 0, 2u);
    if ( v8 >= 0 )
    {
      v8 = AiVerifyFile(Binding, TargetHandle, a2, &SourceString);
      if ( v8 >= 0 )
      {
        AiFree(a3->Buffer);
        RtlInitUnicodeString(a3, SourceString);
      }
      KeStackAttachProcess((PRKPROCESS)*(&Binding + 1), &ApcState);
      ObCloseHandle(TargetHandle, 1);
      KeUnstackDetachProcess(&ApcState);
    }
  }
  else
  {
    v8 = -2;
    *a4 = 0;
  }
  ExReleasePushLockSharedEx(&AipServiceContext, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140026e44  push    rbp
0x140026e46  push    rbx
0x140026e47  push    rsi
0x140026e48  push    rdi
0x140026e49  push    r14
0x140026e4b  lea     rbp, [rsp-37h]
0x140026e50  sub     rsp, 90h
0x140026e57  mov     rax, cs:__security_cookie
0x140026e5e  xor     rax, rsp
0x140026e61  mov     [rbp+57h+var_30], rax
0x140026e65  xorps   xmm0, xmm0
0x140026e68  mov     [rbp+57h+TargetHandle], 0
0x140026e70  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x140026e74  mov     rsi, r9
0x140026e77  mov     rdi, r8
0x140026e7a  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x140026e7e  mov     r14, rdx
0x140026e81  mov     rbx, rcx
0x140026e84  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x140026e88  mov     [rbp+57h+SourceString], 0
0x140026e90  mov     byte ptr [r9], 1
0x140026e94  call    cs:__imp_KeEnterCriticalRegion
0x140026e9b  nop     dword ptr [rax+rax+00h]
0x140026ea0  xor     edx, edx
0x140026ea2  lea     rcx, AipServiceContext
0x140026ea9  call    cs:__imp_ExAcquirePushLockSharedEx
0x140026eb0  nop     dword ptr [rax+rax+00h]
0x140026eb5  cmp     qword ptr cs:Binding+8, 0
0x140026ebd  jz      loc_140026F81
0x140026ec3  cmp     qword ptr cs:Binding, 0
0x140026ecb  jz      loc_140026F81
0x140026ed1  mov     r8, qword ptr cs:TargetProcessHandle; TargetProcessHandle
0x140026ed8  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x140026edc  mov     [rsp+0B0h+Options], 2; Options
0x140026ee4  mov     rdx, rbx; SourceHandle
0x140026ee7  mov     [rsp+0B0h+HandleAttributes], 0; HandleAttributes
0x140026eef  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x140026ef3  mov     [rsp+0B0h+DesiredAccess], 0; DesiredAccess
0x140026efb  call    cs:__imp_ZwDuplicateObject
0x140026f02  nop     dword ptr [rax+rax+00h]
0x140026f07  mov     ebx, eax
0x140026f09  test    eax, eax
0x140026f0b  js      short loc_140026F89
0x140026f0d  mov     rdx, [rbp+57h+TargetHandle]
0x140026f11  lea     r9, [rbp+57h+SourceString]
0x140026f15  mov     rcx, qword ptr cs:Binding
0x140026f1c  mov     r8, r14
0x140026f1f  call    AiVerifyFile
0x140026f24  mov     ebx, eax
0x140026f26  test    eax, eax
0x140026f28  js      short loc_140026F46
0x140026f2a  mov     rcx, [rdi+8]
0x140026f2e  call    AiFree
0x140026f33  mov     rdx, [rbp+57h+SourceString]; SourceString
0x140026f37  mov     rcx, rdi; DestinationString
0x140026f3a  call    cs:__imp_RtlInitUnicodeString
0x140026f41  nop     dword ptr [rax+rax+00h]
0x140026f46  mov     rcx, qword ptr cs:Binding+8; PROCESS
0x140026f4d  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140026f51  call    cs:__imp_KeStackAttachProcess
0x140026f58  nop     dword ptr [rax+rax+00h]
0x140026f5d  mov     rcx, [rbp+57h+TargetHandle]; Handle
0x140026f61  mov     dl, 1; PreviousMode
0x140026f63  call    cs:__imp_ObCloseHandle
0x140026f6a  nop     dword ptr [rax+rax+00h]
0x140026f6f  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140026f73  call    cs:__imp_KeUnstackDetachProcess
0x140026f7a  nop     dword ptr [rax+rax+00h]
0x140026f7f  jmp     short loc_140026F89
0x140026f81  mov     ebx, 0FFFFFFFEh
0x140026f86  mov     byte ptr [rsi], 0
0x140026f89  xor     edx, edx
0x140026f8b  lea     rcx, AipServiceContext
0x140026f92  call    cs:__imp_ExReleasePushLockSharedEx
0x140026f99  nop     dword ptr [rax+rax+00h]
0x140026f9e  call    cs:__imp_KeLeaveCriticalRegion
0x140026fa5  nop     dword ptr [rax+rax+00h]
0x140026faa  mov     eax, ebx
0x140026fac  mov     rcx, [rbp+57h+var_30]
0x140026fb0  xor     rcx, rsp; StackCookie
0x140026fb3  call    __security_check_cookie
0x140026fb8  add     rsp, 90h
0x140026fbf  pop     r14
0x140026fc1  pop     rdi
0x140026fc2  pop     rsi
0x140026fc3  pop     rbx
0x140026fc4  pop     rbp
0x140026fc5  retn
```

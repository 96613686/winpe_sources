# HandleSendReceiveServer::ValidateStopListening(_AE_API_MSG * const &)

- ea: `0x1400acebc`
- end: `0x1400acfb4`
- name: `?ValidateStopListening@HandleSendReceiveServer@@AEAAJAEBQEAU_AE_API_MSG@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(HandleSendReceiveServer *__hidden this, struct _AE_API_MSG *const *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002f830`

## callees

- `0x1400acebc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400acf31`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400acf31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400acf39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400acf39`
- `ntdll!NtClose` at `0x1400acf53`
- `ntdll!NtClose` at `0x1400acf53`
- `ntdll!NtAlpcOpenSenderProcess` at `0x1400acf21`
- `ntdll!NtAlpcOpenSenderProcess` at `0x1400acf21`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1400acf90`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1400acf90`

## pseudocode

```c
__int64 __fastcall HandleSendReceiveServer::ValidateStopListening(
        HandleSendReceiveServer *this,
        struct _AE_API_MSG *const *a2)
{
  __int64 v2; // r8
  __int64 v4; // rdx
  signed int v6; // esi
  DWORD ProcessId; // edi
  DWORD CurrentProcessId; // ebx
  _QWORD v10[4]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v11; // [rsp+60h] [rbp-18h]
  HANDLE Process; // [rsp+B0h] [rbp+38h] BYREF

  v2 = (__int64)*a2;
  v4 = *((_QWORD *)this + 1);
  v10[0] = 48;
  Process = 0;
  memset(&v10[1], 0, 24);
  v11 = 0;
  v6 = NtAlpcOpenSenderProcess(&Process, v4, v2, 0, 0x80000000, v10);
  if ( v6 >= 0 )
  {
    ProcessId = GetProcessId(Process);
    CurrentProcessId = GetCurrentProcessId();
    v6 = ProcessId != CurrentProcessId ? 0xC0000001 : 0;
    NtClose(Process);
    if ( CurrentProcessId == ProcessId )
    {
      v6 = NtAlpcSendWaitReceivePort(*((_QWORD *)this + 1), 0x10000, *a2, 0, 0, 0, 0, 0);
      if ( v6 >= 0 )
        _InterlockedExchange((volatile __int32 *)this + 12, 1);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400acebc  push    rbp
0x1400acebe  push    rbx
0x1400acebf  push    rsi
0x1400acec0  push    rdi
0x1400acec1  push    r14
0x1400acec3  push    r15
0x1400acec5  mov     rbp, rsp
0x1400acec8  sub     rsp, 78h
0x1400acecc  mov     r8, [rdx]
0x1400acecf  lea     rax, [rbp+var_38]
0x1400aced3  mov     r15, rdx
0x1400aced6  mov     [rsp+78h+var_50], rax
0x1400acedb  mov     rdx, [rcx+8]
0x1400acedf  mov     r14, rcx
0x1400acee2  xorps   xmm0, xmm0
0x1400acee5  mov     dword ptr [rsp+78h+var_58], 80000000h
0x1400aceed  lea     rcx, [rbp+Process]
0x1400acef1  mov     [rbp+var_38], 30h ; '0'
0x1400acef9  xor     r9d, r9d
0x1400acefc  mov     [rbp+var_20], 0
0x1400acf04  mov     [rbp+Process], 0
0x1400acf0c  mov     [rbp+var_30], 0
0x1400acf14  mov     [rbp+var_28], 0
0x1400acf1c  movdqu  [rbp+var_18], xmm0
0x1400acf21  call    cs:__imp_NtAlpcOpenSenderProcess
0x1400acf27  mov     esi, eax
0x1400acf29  test    eax, eax
0x1400acf2b  js      short loc_1400ACFA5
0x1400acf2d  mov     rcx, [rbp+Process]; Process
0x1400acf31  call    cs:__imp_GetProcessId
0x1400acf37  mov     edi, eax
0x1400acf39  call    cs:__imp_GetCurrentProcessId
0x1400acf3f  mov     ecx, eax
0x1400acf41  mov     ebx, eax
0x1400acf43  sub     ecx, edi
0x1400acf45  neg     ecx
0x1400acf47  mov     rcx, [rbp+Process]; Handle
0x1400acf4b  sbb     esi, esi
0x1400acf4d  and     esi, 0C0000001h
0x1400acf53  call    cs:__imp_NtClose
0x1400acf59  cmp     ebx, edi
0x1400acf5b  jnz     short loc_1400ACFA5
0x1400acf5d  mov     r8, [r15]
0x1400acf60  xor     r9d, r9d
0x1400acf63  mov     rcx, [r14+8]
0x1400acf67  mov     edx, 10000h
0x1400acf6c  mov     [rsp+78h+var_40], 0
0x1400acf75  mov     [rsp+78h+var_48], 0
0x1400acf7e  mov     [rsp+78h+var_50], 0
0x1400acf87  mov     [rsp+78h+var_58], 0
0x1400acf90  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1400acf96  mov     esi, eax
0x1400acf98  test    eax, eax
0x1400acf9a  js      short loc_1400ACFA5
0x1400acf9c  mov     eax, 1
0x1400acfa1  xchg    eax, [r14+30h]
0x1400acfa5  mov     eax, esi
0x1400acfa7  add     rsp, 78h
0x1400acfab  pop     r15
0x1400acfad  pop     r14
0x1400acfaf  pop     rdi
0x1400acfb0  pop     rsi
0x1400acfb1  pop     rbx
0x1400acfb2  pop     rbp
0x1400acfb3  retn
```

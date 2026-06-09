# AppReadiness::GetCallingUserToken

- ea: `0x180012124`
- end: `0x180012183`
- name: `AppReadiness::GetCallingUserToken`
- size: `95`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011cac`
- `0x180012028`
- `0x1800371d8`

## callees

- `0x180012124`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180012138`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180012138`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012172`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012172`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012166`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012166`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012151`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012151`

## pseudocode

```c
__int64 __fastcall AppReadiness::GetCallingUserToken(__int64 a1, void **a2)
{
  HRESULT Error; // ebx
  HANDLE CurrentThread; // rax

  *a2 = 0;
  Error = CoImpersonateClient();
  if ( Error >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, a2) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    CoRevertToSelf();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180012124  mov     [rsp+arg_0], rbx
0x180012129  push    rdi
0x18001212a  sub     rsp, 20h
0x18001212e  mov     rdi, rdx
0x180012131  mov     qword ptr [rdx], 0
0x180012138  call    cs:__imp_CoImpersonateClient
0x18001213e  mov     ebx, eax
0x180012140  test    eax, eax
0x180012142  jns     short loc_180012151
0x180012144  mov     eax, ebx
0x180012146  mov     rbx, [rsp+28h+arg_0]
0x18001214b  add     rsp, 20h
0x18001214f  pop     rdi
0x180012150  retn
0x180012151  call    cs:__imp_GetCurrentThread
0x180012157  mov     edx, 8; DesiredAccess
0x18001215c  mov     r9, rdi; TokenHandle
0x18001215f  mov     rcx, rax; ThreadHandle
0x180012162  lea     r8d, [rdx-7]; OpenAsSelf
0x180012166  call    cs:__imp_OpenThreadToken
0x18001216c  test    eax, eax
0x18001216e  jz      short loc_18001217A
0x180012170  xor     ebx, ebx
0x180012172  call    cs:__imp_CoRevertToSelf
0x180012178  jmp     short loc_180012144
0x18001217a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001217f  mov     ebx, eax
0x180012181  jmp     short loc_180012172
```

# CAxInstaller::GetClientsToken(void * *)

- ea: `0x180006918`
- end: `0x1800069e5`
- name: `?GetClientsToken@CAxInstaller@@AEAAJPEAPEAX@Z`
- size: `205`
- prototype: `int(CAxInstaller *__hidden this, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180006aec`

## callees

- `0x180006918`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000693a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000693a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800069a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800069a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006994`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006986`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006946`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006946`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000695f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000695f`

## pseudocode

```c
__int64 __fastcall CAxInstaller::GetClientsToken(CAxInstaller *this, void **a2)
{
  int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF

  TokenHandle = 0;
  *a2 = 0;
  v3 = CoImpersonateClient();
  if ( v3 < 0 )
    goto LABEL_15;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle)
    && DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, a2) )
  {
    v3 = 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  CoRevertToSelf();
  if ( v3 < 0 )
  {
LABEL_15:
    if ( *a2 )
    {
      CloseHandle(*a2);
      *a2 = 0;
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006918  mov     [rsp+arg_8], rbx
0x18000691d  mov     [rsp+TokenHandle], rcx
0x180006922  push    rdi
0x180006923  sub     rsp, 30h
0x180006927  mov     rdi, rdx
0x18000692a  mov     [rsp+38h+TokenHandle], 0
0x180006933  mov     qword ptr [rdx], 0
0x18000693a  call    cs:__imp_CoImpersonateClient
0x180006940  mov     ebx, eax
0x180006942  test    eax, eax
0x180006944  js      short loc_1800069B3
0x180006946  call    cs:__imp_GetCurrentThread
0x18000694c  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180006951  mov     edx, 0F01FFh; DesiredAccess
0x180006956  mov     rcx, rax; ThreadHandle
0x180006959  mov     r8d, 1; OpenAsSelf
0x18000695f  call    cs:__imp_OpenThreadToken
0x180006965  test    eax, eax
0x180006967  jz      short loc_180006994
0x180006969  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18000696e  mov     r9d, 2; ImpersonationLevel
0x180006974  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x180006979  xor     r8d, r8d; lpTokenAttributes
0x18000697c  mov     edx, 2000000h; dwDesiredAccess
0x180006981  mov     [rsp+38h+TokenType], r9d; TokenType
0x180006986  call    cs:__imp_DuplicateTokenEx
0x18000698c  test    eax, eax
0x18000698e  jz      short loc_180006994
0x180006990  xor     ebx, ebx
0x180006992  jmp     short loc_1800069A9
0x180006994  call    cs:__imp_GetLastError
0x18000699a  mov     ebx, eax
0x18000699c  test    eax, eax
0x18000699e  jle     short loc_1800069A9
0x1800069a0  movzx   ebx, ax
0x1800069a3  or      ebx, 80070000h
0x1800069a9  call    cs:__imp_CoRevertToSelf
0x1800069af  test    ebx, ebx
0x1800069b1  jns     short loc_1800069C8
0x1800069b3  mov     rcx, [rdi]; hObject
0x1800069b6  test    rcx, rcx
0x1800069b9  jz      short loc_1800069C8
0x1800069bb  call    cs:__imp_CloseHandle
0x1800069c1  mov     qword ptr [rdi], 0
0x1800069c8  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800069cd  test    rcx, rcx
0x1800069d0  jz      short loc_1800069D8
0x1800069d2  call    cs:__imp_CloseHandle
0x1800069d8  mov     eax, ebx
0x1800069da  mov     rbx, [rsp+38h+arg_8]
0x1800069df  add     rsp, 30h
0x1800069e3  pop     rdi
0x1800069e4  retn
```

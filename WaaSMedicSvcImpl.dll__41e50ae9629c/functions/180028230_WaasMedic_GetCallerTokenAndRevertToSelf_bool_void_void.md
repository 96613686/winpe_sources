# WaasMedic::GetCallerTokenAndRevertToSelf(bool,void * *,void * *)

- ea: `0x180028230`
- end: `0x1800283c2`
- name: `?GetCallerTokenAndRevertToSelf@WaasMedic@@YAJ_NPEAPEAX1@Z`
- size: `402`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, bool, void **, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800288a0`
- `0x180068840`

## callees

- `0x180028230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002829e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002831a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002829e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002831a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002827c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800282fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002827c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800282fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028294`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028310`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028294`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800283a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800283a3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800282b0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800282b0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180028337`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180028337`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002834f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002834f`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800282cc`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800282cc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002838a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002838a`

## pseudocode

```c
__int64 __fastcall WaasMedic::GetCallerTokenAndRevertToSelf(WaasMedic *this, HANDLE *a2, void **a3, void **a4)
{
  BOOL v7; // r14d
  HANDLE CurrentThread; // rax
  int v9; // esi
  signed int LastError; // eax
  signed int v11; // ebx
  int v12; // r12d
  HRESULT v13; // eax
  bool v14; // cc
  HANDLE v15; // rax
  signed int v16; // eax
  HRESULT v17; // eax
  HANDLE v18; // rcx
  void *v19; // rax
  void *TokenHandle; // [rsp+58h] [rbp+38h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+48h] BYREF

  TokenHandle = 0;
  hObject = 0;
  if ( !a2 )
    return 2147942487LL;
  v7 = 0;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  CurrentThread = GetCurrentThread();
  v9 = 1;
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    goto LABEL_14;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError == 1008 )
  {
    v12 = 0;
    v13 = CoImpersonateClient();
    v11 = v13;
    if ( v13 < 0 )
    {
      if ( v13 != -2147417833 )
        goto LABEL_28;
      v9 = 0;
      v7 = ImpersonateSelf(SecurityImpersonation);
      if ( !v7 )
      {
        LastError = GetLastError();
        v11 = LastError;
        v14 = LastError <= 0;
        goto LABEL_11;
      }
    }
LABEL_15:
    v15 = GetCurrentThread();
    if ( OpenThreadToken(v15, 0xBu, 1, &hObject) )
    {
      v11 = 0;
    }
    else
    {
      v16 = GetLastError();
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
    }
    if ( v9 )
    {
      v17 = CoRevertToSelf();
      if ( v11 < 0 )
        goto LABEL_28;
      v11 = v17;
    }
    else if ( v7 || v12 )
    {
      RevertToSelf();
    }
    goto LABEL_25;
  }
  v14 = LastError <= 0;
  if ( !LastError )
  {
LABEL_14:
    v9 = 0;
    v12 = 1;
    goto LABEL_15;
  }
LABEL_11:
  if ( !v14 )
    v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_25:
  if ( v11 >= 0 )
  {
    v18 = 0;
    *a2 = hObject;
    v19 = TokenHandle;
    hObject = 0;
    if ( a3 )
    {
      *a3 = TokenHandle;
      v19 = 0;
      TokenHandle = 0;
    }
    goto LABEL_29;
  }
LABEL_28:
  v19 = TokenHandle;
  v18 = hObject;
LABEL_29:
  if ( v19 )
  {
    ImpersonateLoggedOnUser(v19);
    CloseHandle(TokenHandle);
    v18 = hObject;
  }
  if ( v18 )
    CloseHandle(v18);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180028230  mov     [rsp-28h+arg_0], rbx
0x180028235  mov     [rsp-28h+arg_10], rsi
0x18002823a  push    rbp
0x18002823b  push    rdi
0x18002823c  push    r12
0x18002823e  push    r14
0x180028240  push    r15
0x180028242  mov     rbp, rsp
0x180028245  sub     rsp, 20h
0x180028249  mov     [rbp+TokenHandle], 0
0x180028251  mov     rdi, r8
0x180028254  mov     [rbp+hObject], 0
0x18002825c  mov     r15, rdx
0x18002825f  test    rdx, rdx
0x180028262  jnz     short loc_18002826E
0x180028264  mov     eax, 80070057h
0x180028269  jmp     loc_1800283AB
0x18002826e  xor     r14d, r14d
0x180028271  mov     [rdx], r14
0x180028274  test    rdi, rdi
0x180028277  jz      short loc_18002827C
0x180028279  mov     [r8], r14
0x18002827c  call    cs:__imp_GetCurrentThread
0x180028282  mov     esi, 1
0x180028287  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002828b  mov     rcx, rax; ThreadHandle
0x18002828e  mov     r8d, esi; OpenAsSelf
0x180028291  lea     edx, [rsi+0Bh]; DesiredAccess
0x180028294  call    cs:__imp_OpenThreadToken
0x18002829a  test    eax, eax
0x18002829c  jnz     short loc_1800282F4
0x18002829e  call    cs:__imp_GetLastError
0x1800282a4  mov     ebx, eax
0x1800282a6  cmp     eax, 3F0h
0x1800282ab  jnz     short loc_1800282F0
0x1800282ad  xor     r12d, r12d
0x1800282b0  call    cs:__imp_CoImpersonateClient
0x1800282b6  mov     ebx, eax
0x1800282b8  test    eax, eax
0x1800282ba  jns     short loc_1800282FA
0x1800282bc  cmp     eax, 80010117h
0x1800282c1  jnz     loc_18002837A
0x1800282c7  xor     esi, esi
0x1800282c9  lea     ecx, [rsi+2]; ImpersonationLevel
0x1800282cc  call    cs:__imp_ImpersonateSelf
0x1800282d2  mov     r14d, eax
0x1800282d5  test    eax, eax
0x1800282d7  jnz     short loc_1800282FA
0x1800282d9  call    cs:__imp_GetLastError
0x1800282df  mov     ebx, eax
0x1800282e1  test    eax, eax
0x1800282e3  jle     short loc_180028355
0x1800282e5  movzx   ebx, ax
0x1800282e8  or      ebx, 80070000h
0x1800282ee  jmp     short loc_180028355
0x1800282f0  test    eax, eax
0x1800282f2  jnz     short loc_1800282E3
0x1800282f4  xor     esi, esi
0x1800282f6  lea     r12d, [rsi+1]
0x1800282fa  call    cs:__imp_GetCurrentThread
0x180028300  mov     edx, 0Bh; DesiredAccess
0x180028305  lea     r9, [rbp+hObject]; TokenHandle
0x180028309  mov     rcx, rax; ThreadHandle
0x18002830c  lea     r8d, [rdx-0Ah]; OpenAsSelf
0x180028310  call    cs:__imp_OpenThreadToken
0x180028316  test    eax, eax
0x180028318  jnz     short loc_180028331
0x18002831a  call    cs:__imp_GetLastError
0x180028320  mov     ebx, eax
0x180028322  test    eax, eax
0x180028324  jle     short loc_180028333
0x180028326  movzx   ebx, ax
0x180028329  or      ebx, 80070000h
0x18002832f  jmp     short loc_180028333
0x180028331  xor     ebx, ebx
0x180028333  test    esi, esi
0x180028335  jz      short loc_180028345
0x180028337  call    cs:__imp_CoRevertToSelf
0x18002833d  test    ebx, ebx
0x18002833f  js      short loc_18002837A
0x180028341  mov     ebx, eax
0x180028343  jmp     short loc_180028355
0x180028345  test    r14d, r14d
0x180028348  jnz     short loc_18002834F
0x18002834a  test    r12d, r12d
0x18002834d  jz      short loc_180028355
0x18002834f  call    cs:__imp_RevertToSelf
0x180028355  test    ebx, ebx
0x180028357  js      short loc_18002837A
0x180028359  mov     rax, [rbp+hObject]
0x18002835d  xor     ecx, ecx
0x18002835f  mov     [r15], rax
0x180028362  mov     rax, [rbp+TokenHandle]
0x180028366  mov     [rbp+hObject], rcx
0x18002836a  test    rdi, rdi
0x18002836d  jz      short loc_180028382
0x18002836f  mov     [rdi], rax
0x180028372  xor     eax, eax
0x180028374  mov     [rbp+TokenHandle], rax
0x180028378  jmp     short loc_180028382
0x18002837a  mov     rax, [rbp+TokenHandle]
0x18002837e  mov     rcx, [rbp+hObject]
0x180028382  test    rax, rax
0x180028385  jz      short loc_18002839E
0x180028387  mov     rcx, rax; hToken
0x18002838a  call    cs:__imp_ImpersonateLoggedOnUser
0x180028390  mov     rcx, [rbp+TokenHandle]; hObject
0x180028394  call    cs:__imp_CloseHandle
0x18002839a  mov     rcx, [rbp+hObject]; hObject
0x18002839e  test    rcx, rcx
0x1800283a1  jz      short loc_1800283A9
0x1800283a3  call    cs:__imp_CloseHandle
0x1800283a9  mov     eax, ebx
0x1800283ab  mov     rbx, [rsp+20h+arg_0]
0x1800283b0  mov     rsi, [rsp+20h+arg_10]
0x1800283b5  add     rsp, 20h
0x1800283b9  pop     r15
0x1800283bb  pop     r14
0x1800283bd  pop     r12
0x1800283bf  pop     rdi
0x1800283c0  pop     rbp
0x1800283c1  retn
```

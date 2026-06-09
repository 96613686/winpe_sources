# CloudStoreUtilities::OpenCurrentThreadAccessToken(void)

- ea: `0x180031fb0`
- end: `0x1800320ce`
- name: `?OpenCurrentThreadAccessToken@CloudStoreUtilities@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@XZ`
- size: `286`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003137c`
- `0x1800322f8`
- `0x18003be48`
- `0x18003c1a0`

## callees

- `0x180031fb0`
- `0x180032b98`
- `0x180032bd0`
- `0x1800a15ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003202e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003202e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031ff0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031ff0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003201b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003201b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudStoreUtilities::OpenCurrentThreadAccessToken(__int64 a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  HANDLE CurrentProcess; // rax
  bool v6; // bl
  char *v7; // rbp
  signed int v9; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  char v11; // [rsp+38h] [rbp-20h]
  char *v12; // [rsp+68h] [rbp+10h] BYREF
  __int64 v13; // [rsp+70h] [rbp+18h] BYREF

  v12 = 0;
  TokenHandle = 0;
  v11 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
  {
    v4 = 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
      {
        v4 = 0;
      }
      else
      {
        v9 = GetLastError();
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
      }
    }
  }
  v6 = v4 >= 0;
  if ( v11 )
  {
    v7 = (char *)TokenHandle;
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v12);
    v12 = v7;
  }
  if ( v6 )
  {
    *(_QWORD *)a1 = v12;
    *(_BYTE *)(a1 + 8) = 0;
  }
  else
  {
    wil::open_current_access_token(&v13);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v12,
      v13);
    *(_QWORD *)a1 = v12;
    *(_BYTE *)(a1 + 8) = 1;
  }
  return a1;
}

```

## disassembly

```asm
0x180031fb0  mov     [rsp+arg_0], rbx
0x180031fb5  push    rbp
0x180031fb6  push    rsi
0x180031fb7  push    rdi
0x180031fb8  sub     rsp, 40h
0x180031fbc  mov     rdi, rcx
0x180031fbf  xor     esi, esi
0x180031fc1  mov     [rsp+58h+arg_8], rsi
0x180031fc6  lea     rax, [rsp+58h+arg_8]
0x180031fcb  mov     [rsp+58h+var_30], rax
0x180031fd0  mov     [rsp+58h+TokenHandle], rsi
0x180031fd5  mov     [rsp+58h+var_20], 1
0x180031fda  call    cs:__imp_GetCurrentThread
0x180031fe0  mov     rcx, rax; ThreadHandle
0x180031fe3  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180031fe8  xor     r8d, r8d; OpenAsSelf
0x180031feb  mov     edx, 2000000h; DesiredAccess
0x180031ff0  call    cs:__imp_OpenThreadToken
0x180031ff6  test    eax, eax
0x180031ff8  jnz     loc_180032081
0x180031ffe  call    cs:__imp_GetLastError
0x180032004  mov     ebx, eax
0x180032006  test    eax, eax
0x180032008  jle     short loc_180032013
0x18003200a  movzx   ebx, ax
0x18003200d  or      ebx, 80070000h
0x180032013  cmp     ebx, 800703F0h
0x180032019  jnz     short loc_18003203A
0x18003201b  call    cs:__imp_GetCurrentProcess
0x180032021  mov     rcx, rax; ProcessHandle
0x180032024  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180032029  mov     edx, 2000000h; DesiredAccess
0x18003202e  call    cs:__imp_OpenProcessToken
0x180032034  test    eax, eax
0x180032036  jz      short loc_1800320AC
0x180032038  mov     ebx, esi
0x18003203a  shr     ebx, 1Fh
0x18003203d  xor     bl, 1
0x180032040  cmp     [rsp+58h+var_20], 0
0x180032045  jz      short loc_180032061
0x180032047  mov     rbp, [rsp+58h+TokenHandle]
0x18003204c  mov     rsi, [rsp+58h+var_30]
0x180032051  mov     rcx, [rsi]; hObject
0x180032054  lea     rax, [rcx-1]
0x180032058  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003205c  jbe     short loc_1800320C6
0x18003205e  mov     [rsi], rbp
0x180032061  test    bl, bl
0x180032063  jz      short loc_180032085
0x180032065  mov     rax, [rsp+58h+arg_8]
0x18003206a  mov     [rdi], rax
0x18003206d  mov     byte ptr [rdi+8], 0
0x180032071  mov     rax, rdi
0x180032074  mov     rbx, [rsp+58h+arg_0]
0x180032079  add     rsp, 40h
0x18003207d  pop     rdi
0x18003207e  pop     rsi
0x18003207f  pop     rbp
0x180032080  retn
0x180032081  mov     ebx, esi
0x180032083  jmp     short loc_18003203A
0x180032085  lea     rcx, [rsp+58h+arg_10]
0x18003208a  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x18003208f  mov     rdx, [rsp+58h+arg_10]
0x180032094  lea     rcx, [rsp+58h+arg_8]
0x180032099  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003209e  mov     rax, [rsp+58h+arg_8]
0x1800320a3  mov     [rdi], rax
0x1800320a6  mov     byte ptr [rdi+8], 1
0x1800320aa  jmp     short loc_180032071
0x1800320ac  call    cs:__imp_GetLastError
0x1800320b2  mov     ebx, eax
0x1800320b4  test    eax, eax
0x1800320b6  jle     short loc_18003203A
0x1800320b8  movzx   ebx, ax
0x1800320bb  or      ebx, 80070000h
0x1800320c1  jmp     loc_18003203A
0x1800320c6  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x1800320cb  jmp     short loc_18003205E
```

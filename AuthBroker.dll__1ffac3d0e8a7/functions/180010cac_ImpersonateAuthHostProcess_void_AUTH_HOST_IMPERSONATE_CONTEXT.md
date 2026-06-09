# _ImpersonateAuthHostProcess(void *,_AUTH_HOST_IMPERSONATE_CONTEXT *)

- ea: `0x180010cac`
- end: `0x180010e51`
- name: `?_ImpersonateAuthHostProcess@@YAJPEAXPEAU_AUTH_HOST_IMPERSONATE_CONTEXT@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(void *processHandle, _AUTH_HOST_IMPERSONATE_CONTEXT *impersonateContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ed84`

## callees

- `0x18000737c`
- `0x180010cac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010dc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010d73`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010cd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010cd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010cef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010cef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e39`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180010dbd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180010dbd`

## pseudocode

```c
__int64 __fastcall _ImpersonateAuthHostProcess(void *processHandle, _AUTH_HOST_IMPERSONATE_CONTEXT *impersonateContext)
{
  HANDLE CurrentThread; // rax
  signed int v5; // eax
  unsigned int v6; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v7; // rcx
  unsigned __int16 v8; // dx
  signed int v9; // eax
  signed int LastError; // eax
  void *userToken; // [rsp+40h] [rbp+18h] BYREF
  void *appContainerToken; // [rsp+48h] [rbp+20h] BYREF

  userToken = 0;
  *impersonateContext = 0;
  appContainerToken = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &userToken) || (v5 = GetLastError(), userToken = 0, v6 = v5, v5 == 1008) )
  {
    if ( OpenProcessToken(processHandle, 0xEu, &appContainerToken) )
    {
      if ( ImpersonateLoggedOnUser(appContainerToken) )
      {
        v6 = 0;
        impersonateContext->restoreToken = userToken;
        impersonateContext->doRevert = 1;
        userToken = 0;
$Exit_11:
        if ( userToken )
          CloseHandle(userToken);
        goto LABEL_27;
      }
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $Exit_11;
      }
      v8 = 76;
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $Exit_11;
      }
      v8 = 75;
    }
LABEL_9:
    WPP_SF_d(v7[1].Control.Logger, v8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v6);
    goto $Exit_11;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    v8 = 74;
    goto LABEL_9;
  }
LABEL_27:
  if ( appContainerToken )
    CloseHandle(appContainerToken);
  return v6;
}

```

## disassembly

```asm
0x180010cac  mov     rax, rsp
0x180010caf  mov     [rax+8], rbx
0x180010cb3  mov     [rax+10h], rsi
0x180010cb7  push    rdi
0x180010cb8  sub     rsp, 20h
0x180010cbc  xorps   xmm0, xmm0
0x180010cbf  mov     qword ptr [rax+18h], 0
0x180010cc7  movups  xmmword ptr [impersonateContext], xmm0
0x180010cca  mov     rdi, impersonateContext
0x180010ccd  mov     qword ptr [rax+20h], 0
0x180010cd5  mov     rsi, processHandle
0x180010cd8  call    cs:__imp_GetCurrentThread
0x180010cde  mov     edx, 0Eh; DesiredAccess
0x180010ce3  lea     r9, [rsp+28h+userToken]; TokenHandle
0x180010ce8  mov     processHandle, rax; ThreadHandle
0x180010ceb  lea     r8d, [impersonateContext-0Dh]; OpenAsSelf
0x180010cef  call    cs:__imp_OpenThreadToken
0x180010cf5  test    eax, eax
0x180010cf7  jnz     short loc_180010D66
0x180010cf9  call    cs:__imp_GetLastError
0x180010cff  mov     [rsp+28h+userToken], 0
0x180010d08  mov     ebx, eax
0x180010d0a  cmp     eax, 3F0h
0x180010d0f  jz      short loc_180010D66
0x180010d11  test    eax, eax
0x180010d13  jle     short loc_180010D1E
0x180010d15  movzx   ebx, ax
0x180010d18  or      ebx, 80070000h
0x180010d1e  mov     processHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010d25  lea     rax, WPP_GLOBAL_Control
0x180010d2c  cmp     processHandle, rax
0x180010d2f  jz      loc_180010E2F
0x180010d35  test    byte ptr [processHandle+44h], 10h
0x180010d39  jz      loc_180010E2F
0x180010d3f  cmp     byte ptr [processHandle+41h], 2
0x180010d43  jb      loc_180010E2F
0x180010d49  mov     edx, 4Ah ; 'J'; id
0x180010d4e  mov     processHandle, [processHandle+38h]; Logger
0x180010d52  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180010d59  mov     r9d, ebx; _a1
0x180010d5c  call    WPP_SF_d
0x180010d61  jmp     $Exit_11
0x180010d66  lea     r8, [rsp+28h+appContainerToken]; TokenHandle
0x180010d6b  mov     edx, 0Eh; DesiredAccess
0x180010d70  mov     processHandle, rsi; ProcessHandle
0x180010d73  call    cs:__imp_OpenProcessToken
0x180010d79  test    eax, eax
0x180010d7b  jnz     short loc_180010DB8
0x180010d7d  call    cs:__imp_GetLastError
0x180010d83  mov     ebx, eax
0x180010d85  test    eax, eax
0x180010d87  jle     short loc_180010D92
0x180010d89  movzx   ebx, ax
0x180010d8c  or      ebx, 80070000h
0x180010d92  mov     processHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010d99  lea     rax, WPP_GLOBAL_Control
0x180010da0  cmp     processHandle, rax
0x180010da3  jz      short $Exit_11
0x180010da5  test    byte ptr [processHandle+44h], 10h
0x180010da9  jz      short $Exit_11
0x180010dab  cmp     byte ptr [processHandle+41h], 2
0x180010daf  jb      short $Exit_11
0x180010db1  mov     edx, 4Bh ; 'K'
0x180010db6  jmp     short loc_180010D4E
0x180010db8  mov     processHandle, [rsp+28h+appContainerToken]; hToken
0x180010dbd  call    cs:__imp_ImpersonateLoggedOnUser
0x180010dc3  test    eax, eax
0x180010dc5  jnz     short loc_180010E05
0x180010dc7  call    cs:__imp_GetLastError
0x180010dcd  mov     ebx, eax
0x180010dcf  test    eax, eax
0x180010dd1  jle     short loc_180010DDC
0x180010dd3  movzx   ebx, ax
0x180010dd6  or      ebx, 80070000h
0x180010ddc  mov     processHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010de3  lea     rax, WPP_GLOBAL_Control
0x180010dea  cmp     processHandle, rax
0x180010ded  jz      short $Exit_11
0x180010def  test    byte ptr [processHandle+44h], 10h
0x180010df3  jz      short $Exit_11
0x180010df5  cmp     byte ptr [processHandle+41h], 2
0x180010df9  jb      short $Exit_11
0x180010dfb  mov     edx, 4Ch ; 'L'
0x180010e00  jmp     loc_180010D4E
0x180010e05  mov     rax, [rsp+28h+userToken]
0x180010e0a  xor     ebx, ebx
0x180010e0c  mov     [rdi+8], rax
0x180010e10  mov     dword ptr [rdi], 1
0x180010e16  mov     [rsp+28h+userToken], 0
0x180010e1f  mov     processHandle, [rsp+28h+userToken]; hObject
0x180010e24  test    processHandle, processHandle
0x180010e27  jz      short loc_180010E2F
0x180010e29  call    cs:__imp_CloseHandle
0x180010e2f  mov     processHandle, [rsp+28h+appContainerToken]; hObject
0x180010e34  test    processHandle, processHandle
0x180010e37  jz      short loc_180010E3F
0x180010e39  call    cs:__imp_CloseHandle
0x180010e3f  mov     rsi, [rsp+28h+arg_8]
0x180010e44  mov     eax, ebx
0x180010e46  mov     rbx, [rsp+28h+arg_0]
0x180010e4b  add     rsp, 20h
0x180010e4f  pop     rdi
0x180010e50  retn
```

# _RevertAuthHostProcessImpersonation(_AUTH_HOST_IMPERSONATE_CONTEXT *)

- ea: `0x180011264`
- end: `0x18001130c`
- name: `?_RevertAuthHostProcessImpersonation@@YAJPEAU_AUTH_HOST_IMPERSONATE_CONTEXT@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(_AUTH_HOST_IMPERSONATE_CONTEXT *impersonateContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000ed84`

## callees

- `0x18000737c`
- `0x180011264`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001128f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001128f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011285`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800112b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800112b2`

## pseudocode

```c
__int64 __fastcall _RevertAuthHostProcessImpersonation(_AUTH_HOST_IMPERSONATE_CONTEXT *impersonateContext)
{
  int v1; // ebx
  void **p_restoreToken; // rdi
  signed int LastError; // eax

  v1 = 0;
  p_restoreToken = &impersonateContext->restoreToken;
  if ( impersonateContext->doRevert )
  {
    if ( !SetThreadToken(0, *p_restoreToken) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
    impersonateContext->doRevert = 0;
  }
  if ( *p_restoreToken )
  {
    CloseHandle(*p_restoreToken);
    *p_restoreToken = 0;
  }
  if ( v1 < 0
    && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x4Du, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180011264  mov     [rsp+arg_0], rbx
0x180011269  mov     [rsp+arg_8], rsi
0x18001126e  push    rdi
0x18001126f  sub     rsp, 20h
0x180011273  xor     ebx, ebx
0x180011275  lea     rdi, [impersonateContext+8]
0x180011279  mov     rsi, impersonateContext
0x18001127c  cmp     [impersonateContext], ebx
0x18001127e  jz      short loc_1800112AA
0x180011280  mov     rdx, [rdi]; Token
0x180011283  xor     ecx, ecx; Thread
0x180011285  call    cs:__imp_SetThreadToken
0x18001128b  test    eax, eax
0x18001128d  jnz     short loc_1800112A4
0x18001128f  call    cs:__imp_GetLastError
0x180011295  mov     ebx, eax
0x180011297  test    eax, eax
0x180011299  jle     short loc_1800112A4
0x18001129b  movzx   ebx, ax
0x18001129e  or      ebx, 80070000h
0x1800112a4  mov     dword ptr [rsi], 0
0x1800112aa  mov     impersonateContext, [rdi]; hObject
0x1800112ad  test    impersonateContext, impersonateContext
0x1800112b0  jz      short loc_1800112BF
0x1800112b2  call    cs:__imp_CloseHandle
0x1800112b8  mov     qword ptr [rdi], 0
0x1800112bf  test    ebx, ebx
0x1800112c1  jns     short loc_1800112FA
0x1800112c3  mov     impersonateContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800112ca  lea     rax, WPP_GLOBAL_Control
0x1800112d1  cmp     impersonateContext, rax
0x1800112d4  jz      short loc_1800112FA
0x1800112d6  test    byte ptr [impersonateContext+44h], 10h
0x1800112da  jz      short loc_1800112FA
0x1800112dc  cmp     byte ptr [impersonateContext+41h], 2
0x1800112e0  jb      short loc_1800112FA
0x1800112e2  mov     impersonateContext, [impersonateContext+38h]; Logger
0x1800112e6  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800112ed  mov     edx, 4Dh ; 'M'; id
0x1800112f2  mov     r9d, ebx; _a1
0x1800112f5  call    WPP_SF_d
0x1800112fa  mov     rsi, [rsp+28h+arg_8]
0x1800112ff  mov     eax, ebx
0x180011301  mov     rbx, [rsp+28h+arg_0]
0x180011306  add     rsp, 20h
0x18001130a  pop     rdi
0x18001130b  retn
```

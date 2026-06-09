# AuthBrokerClearThreadClientContext

- ea: `0x180011630`
- end: `0x180011709`
- name: `AuthBrokerClearThreadClientContext`
- size: `217`
- prototype: `HRESULT __fastcall(void *clientContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011840`

## callees

- `0x180003330`
- `0x180004560`
- `0x180011630`
- `0x180011fd4`
- `0x180012128`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800116a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800116a8`

## pseudocode

```c
__int64 __fastcall AuthBrokerClearThreadClientContext(
        _AUTH_BROKER_CLIENT_CONTEXT *clientContext,
        __int64 a2,
        const _GUID *a3)
{
  unsigned int Logger; // ebx
  __int64 v6; // rdx
  const _GUID *v7; // r8
  signed int LastError; // eax

  Logger = -2147024809;
  if ( !clientContext )
  {
LABEL_4:
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control[1].Control.Logger, 0x6Fu, a3, clientContext, Logger);
    }
    return Logger;
  }
  if ( clientContextTlsIndex == -1 )
  {
    Logger = -2147467258;
    goto LABEL_4;
  }
  if ( GetClientContextTlsValue() != clientContext )
    goto LABEL_4;
  if ( TlsSetValue(clientContextTlsIndex, 0) )
  {
    FreeAuthBrokerClientContext(clientContext, v6, v7);
    Logger = 0;
  }
  else
  {
    LastError = GetLastError();
    Logger = LastError;
    if ( LastError > 0 )
      Logger = (unsigned __int16)LastError | 0x80070000;
    if ( (Logger & 0x80000000) != 0 )
      goto LABEL_4;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Control.Logger, 0x70u, a3, clientContext);
  }
  return Logger;
}

```

## disassembly

```asm
0x180011630  mov     [rsp+arg_0], rbx
0x180011635  push    rdi
0x180011636  sub     rsp, 30h
0x18001163a  mov     rdi, clientContext
0x18001163d  mov     ebx, 80070057h
0x180011642  test    clientContext, clientContext
0x180011645  jz      short loc_180011655
0x180011647  cmp     cs:_clientContextTlsIndex, 0FFFFFFFFh
0x18001164e  jnz     short loc_180011696
0x180011650  mov     ebx, 80004006h
0x180011655  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001165c  lea     rax, WPP_GLOBAL_Control
0x180011663  cmp     clientContext, rax
0x180011666  jz      short loc_180011689
0x180011668  test    byte ptr [clientContext+44h], 10h
0x18001166c  jz      short loc_180011689
0x18001166e  cmp     byte ptr [clientContext+41h], 2
0x180011672  jb      short loc_180011689
0x180011674  mov     clientContext, [clientContext+38h]; Logger
0x180011678  mov     edx, 6Fh ; 'o'; id
0x18001167d  mov     r9, rdi; _a2
0x180011680  mov     [rsp+38h+Logger], ebx; Logger
0x180011684  call    WPP_SF_qd
0x180011689  mov     eax, ebx
0x18001168b  mov     rbx, [rsp+38h+arg_0]
0x180011690  add     rsp, 30h
0x180011694  pop     rdi
0x180011695  retn
0x180011696  call    _GetClientContextTlsValue
0x18001169b  cmp     rax, rdi
0x18001169e  jnz     short loc_180011655
0x1800116a0  mov     ecx, cs:_clientContextTlsIndex; dwTlsIndex
0x1800116a6  xor     edx, edx; lpTlsValue
0x1800116a8  call    cs:__imp_TlsSetValue
0x1800116ae  test    eax, eax
0x1800116b0  jnz     short loc_1800116CD
0x1800116b2  call    cs:__imp_GetLastError
0x1800116b8  mov     ebx, eax
0x1800116ba  test    eax, eax
0x1800116bc  jle     short $Exit_14
0x1800116be  movzx   ebx, ax
0x1800116c1  or      ebx, 80070000h
0x1800116c7  test    ebx, ebx
0x1800116c9  jns     short loc_1800116D7
0x1800116cb  jmp     short loc_180011655
0x1800116cd  mov     clientContext, rdi; clientContext
0x1800116d0  call    ?FreeAuthBrokerClientContext@@YAXPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; FreeAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *)
0x1800116d5  xor     ebx, ebx
0x1800116d7  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800116de  lea     rax, WPP_GLOBAL_Control
0x1800116e5  cmp     clientContext, rax
0x1800116e8  jz      short loc_180011689
0x1800116ea  test    byte ptr [clientContext+44h], 10h
0x1800116ee  jz      short loc_180011689
0x1800116f0  cmp     byte ptr [clientContext+41h], 5
0x1800116f4  jb      short loc_180011689
0x1800116f6  mov     clientContext, [clientContext+38h]; Logger
0x1800116fa  mov     edx, 70h ; 'p'; id
0x1800116ff  mov     r9, rdi; Logger
0x180011702  call    WPP_SF_q
0x180011707  jmp     short loc_180011689
```

# AuthBrokerSetThreadClientContext

- ea: `0x180011840`
- end: `0x18001196f`
- name: `AuthBrokerSetThreadClientContext`
- size: `303`
- prototype: `HRESULT __fastcall(void *clientContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004560`
- `0x18000f34c`
- `0x180011630`
- `0x180011840`
- `0x180011fd4`
- `0x180012128`
- `0x18001217c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001190d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001190d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011903`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011903`

## pseudocode

```c
__int64 __fastcall AuthBrokerSetThreadClientContext(
        _AUTH_BROKER_CLIENT_CONTEXT *clientContext,
        __int64 a2,
        const _GUID *a3)
{
  unsigned int Logger; // ebx
  _AUTH_BROKER_CLIENT_CONTEXT *ClientContextTlsValue; // rax
  _AUTH_BROKER_CLIENT_CONTEXT *v7; // rbx
  __int64 v8; // rdx
  const _GUID *v9; // r8
  signed int LastError; // eax

  Logger = -2147024809;
  if ( !clientContext )
  {
LABEL_4:
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control[1].Control.Logger, 0x6Du, a3, clientContext, Logger);
    }
    return Logger;
  }
  if ( clientContextTlsIndex == -1 )
  {
    Logger = -2147467258;
    goto LABEL_4;
  }
  ClientContextTlsValue = GetClientContextTlsValue();
  v7 = ClientContextTlsValue;
  if ( ClientContextTlsValue )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 3u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control[1].Control.Logger,
        0x6Cu,
        WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
        clientContext,
        ClientContextTlsValue);
    }
    AuthBrokerClearThreadClientContext(v7);
  }
  if ( TlsSetValue(clientContextTlsIndex, clientContext) )
  {
    AddRefAuthBrokerClientContext(clientContext, v8, v9);
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
    WPP_SF_q(WPP_GLOBAL_Control[1].Control.Logger, 0x6Eu, a3, clientContext);
  }
  return Logger;
}

```

## disassembly

```asm
0x180011840  mov     [rsp+arg_0], rbx
0x180011845  mov     [rsp+arg_8], rbp
0x18001184a  push    rdi
0x18001184b  sub     rsp, 30h
0x18001184f  lea     rbp, WPP_GLOBAL_Control
0x180011856  mov     rdi, clientContext
0x180011859  mov     ebx, 80070057h
0x18001185e  test    clientContext, clientContext
0x180011861  jz      short loc_180011871
0x180011863  cmp     cs:_clientContextTlsIndex, 0FFFFFFFFh
0x18001186a  jnz     short loc_1800118B0
0x18001186c  mov     ebx, 80004006h
0x180011871  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180011878  cmp     clientContext, rbp
0x18001187b  jz      short loc_18001189E
0x18001187d  test    byte ptr [clientContext+44h], 10h
0x180011881  jz      short loc_18001189E
0x180011883  cmp     byte ptr [clientContext+41h], 2
0x180011887  jb      short loc_18001189E
0x180011889  mov     clientContext, [clientContext+38h]; Logger
0x18001188d  mov     edx, 6Dh ; 'm'; id
0x180011892  mov     r9, rdi; _a2
0x180011895  mov     [rsp+38h+Logger], ebx; Logger
0x180011899  call    WPP_SF_qd
0x18001189e  mov     rbp, [rsp+38h+arg_8]
0x1800118a3  mov     eax, ebx
0x1800118a5  mov     rbx, [rsp+38h+arg_0]
0x1800118aa  add     rsp, 30h
0x1800118ae  pop     rdi
0x1800118af  retn
0x1800118b0  call    _GetClientContextTlsValue
0x1800118b5  mov     rbx, rax
0x1800118b8  test    rax, rax
0x1800118bb  jz      short loc_1800118FA
0x1800118bd  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800118c4  cmp     clientContext, rbp
0x1800118c7  jz      short loc_1800118F2
0x1800118c9  test    byte ptr [clientContext+44h], 10h
0x1800118cd  jz      short loc_1800118F2
0x1800118cf  cmp     byte ptr [clientContext+41h], 3
0x1800118d3  jb      short loc_1800118F2
0x1800118d5  mov     clientContext, [clientContext+38h]; Logger
0x1800118d9  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800118e0  mov     edx, 6Ch ; 'l'; id
0x1800118e5  mov     qword ptr [rsp+38h+Logger], rax; _a2
0x1800118ea  mov     r9, rdi; _a1
0x1800118ed  call    WPP_SF_qq
0x1800118f2  mov     clientContext, rbx; clientContext
0x1800118f5  call    AuthBrokerClearThreadClientContext
0x1800118fa  mov     ecx, cs:_clientContextTlsIndex; dwTlsIndex
0x180011900  mov     rdx, rdi; lpTlsValue
0x180011903  call    cs:__imp_TlsSetValue
0x180011909  test    eax, eax
0x18001190b  jnz     short loc_18001192B
0x18001190d  call    cs:__imp_GetLastError
0x180011913  mov     ebx, eax
0x180011915  test    eax, eax
0x180011917  jle     short $Exit_15
0x180011919  movzx   ebx, ax
0x18001191c  or      ebx, 80070000h
0x180011922  test    ebx, ebx
0x180011924  jns     short loc_180011935
0x180011926  jmp     loc_180011871
0x18001192b  mov     clientContext, rdi; clientContext
0x18001192e  call    ?AddRefAuthBrokerClientContext@@YAXPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; AddRefAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *)
0x180011933  xor     ebx, ebx
0x180011935  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001193c  cmp     clientContext, rbp
0x18001193f  jz      loc_18001189E
0x180011945  test    byte ptr [clientContext+44h], 10h
0x180011949  jz      loc_18001189E
0x18001194f  cmp     byte ptr [clientContext+41h], 5
0x180011953  jb      loc_18001189E
0x180011959  mov     clientContext, [clientContext+38h]; Logger
0x18001195d  mov     edx, 6Eh ; 'n'; id
0x180011962  mov     r9, rdi; Logger
0x180011965  call    WPP_SF_q
0x18001196a  jmp     loc_18001189E
```

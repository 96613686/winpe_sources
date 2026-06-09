# AuthBrokerCreateClientContext

- ea: `0x180011710`
- end: `0x180011831`
- name: `AuthBrokerCreateClientContext`
- size: `289`
- prototype: `__int64 __fastcall(unsigned int flags, HWND__ *parentWindow, const wchar_t *dialogTitle, _AUTH_BROKER_CLIENT_CONTEXT **clientContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x18000737c`
- `0x180011710`
- `0x180011e48`
- `0x180012070`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180011743`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180011743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011754`

## pseudocode

```c
__int64 __fastcall AuthBrokerCreateClientContext(
        unsigned int flags,
        HWND__ *parentWindow,
        const wchar_t *dialogTitle,
        _AUTH_BROKER_CLIENT_CONTEXT **clientContext)
{
  unsigned __int16 v8; // dx
  const _GUID *v9; // r8
  signed int LastError; // eax
  WPP_PROJECT_CONTROL_BLOCK *v11; // rcx
  unsigned int v12; // ebx
  int v13; // eax

  *clientContext = 0;
  if ( InitOnceExecuteOnce(&TlsAllocClientContextInitOnce, TlsAllocClientContextInitOnceCallback, 0, 0) )
    goto LABEL_8;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x68u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, LastError);
LABEL_8:
    v11 = WPP_GLOBAL_Control;
  }
  if ( clientContextTlsIndex == -1 )
  {
    v12 = -2147467258;
LABEL_12:
    if ( v11 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v11[1].ReserveSpace[28] & 0x10) != 0
      && v11[1].Control.Level >= 2u )
    {
      WPP_SF_dDqS(v11[1].Control.Logger, v8, v9, v12, flags, parentWindow, dialogTitle);
    }
    return v12;
  }
  v13 = AllocateAndInitializeAuthBrokerClientContextFromRpcThread(flags, parentWindow, dialogTitle, clientContext);
  v11 = WPP_GLOBAL_Control;
  v12 = v13;
  if ( v13 < 0 )
    goto LABEL_12;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_qDqS(WPP_GLOBAL_Control[1].Control.Logger, v8, v9, *clientContext, flags, parentWindow, dialogTitle);
  }
  return v12;
}

```

## disassembly

```asm
0x180011710  push    rbx
0x180011712  push    rbp
0x180011713  push    rsi
0x180011714  push    rdi
0x180011715  push    r14
0x180011717  push    r15
0x180011719  sub     rsp, 48h
0x18001171d  mov     r14, clientContext
0x180011720  mov     qword ptr [clientContext], 0
0x180011727  mov     rdi, dialogTitle
0x18001172a  mov     rsi, parentWindow
0x18001172d  mov     ebp, flags
0x18001172f  lea     parentWindow, _TlsAllocClientContextInitOnceCallback; InitFn
0x180011736  xor     r9d, r9d; Context
0x180011739  lea     rcx, _TlsAllocClientContextInitOnce; InitOnce
0x180011740  xor     r8d, r8d; Parameter
0x180011743  call    cs:__imp_InitOnceExecuteOnce
0x180011749  lea     r15, WPP_GLOBAL_Control
0x180011750  test    eax, eax
0x180011752  jnz     short loc_180011796
0x180011754  call    cs:__imp_GetLastError
0x18001175a  test    eax, eax
0x18001175c  jle     short loc_180011766
0x18001175e  movzx   eax, ax
0x180011761  or      eax, 80070000h
0x180011766  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001176d  cmp     rcx, r15
0x180011770  jz      short loc_18001179D
0x180011772  test    byte ptr [rcx+44h], 10h
0x180011776  jz      short loc_18001179D
0x180011778  cmp     byte ptr [rcx+41h], 2
0x18001177c  jb      short loc_18001179D
0x18001177e  mov     rcx, [rcx+38h]; Logger
0x180011782  lea     dialogTitle, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180011789  mov     edx, 68h ; 'h'; id
0x18001178e  mov     r9d, eax; _a1
0x180011791  call    WPP_SF_d
0x180011796  mov     rcx, cs:WPP_GLOBAL_Control
0x18001179d  cmp     cs:_clientContextTlsIndex, 0FFFFFFFFh
0x1800117a4  jnz     short loc_1800117AD
0x1800117a6  mov     ebx, 80004006h
0x1800117ab  jmp     short loc_1800117CA
0x1800117ad  mov     clientContext, r14; clientContext
0x1800117b0  mov     dialogTitle, rdi; dialogTitle
0x1800117b3  mov     parentWindow, rsi; parentWindow
0x1800117b6  mov     flags, ebp; flags
0x1800117b8  call    _AllocateAndInitializeAuthBrokerClientContextFromRpcThread
0x1800117bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117c4  mov     ebx, eax
0x1800117c6  test    eax, eax
0x1800117c8  jns     short loc_1800117F7
0x1800117ca  cmp     rcx, r15; __annotation("TMF:",
0x1800117cd  jz      short loc_180011822
0x1800117cf  test    byte ptr [rcx+44h], 10h
0x1800117d3  jz      short loc_180011822
0x1800117d5  cmp     byte ptr [rcx+41h], 2
0x1800117d9  jb      short loc_180011822
0x1800117db  mov     rcx, [rcx+38h]; Logger
0x1800117df  mov     r9d, ebx; _a3
0x1800117e2  mov     [rsp+78h+id], rdi; id
0x1800117e7  mov     [rsp+78h+Logger], rsi; Logger
0x1800117ec  mov     [rsp+78h+_a4], ebp; _a4
0x1800117f0  call    WPP_SF_dDqS
0x1800117f5  jmp     short loc_180011822
0x1800117f7  cmp     rcx, r15; __annotation("TMF:",
0x1800117fa  jz      short loc_180011822
0x1800117fc  test    byte ptr [rcx+44h], 10h
0x180011800  jz      short loc_180011822
0x180011802  cmp     byte ptr [rcx+41h], 5
0x180011806  jb      short loc_180011822
0x180011808  mov     clientContext, [r14]; _a3
0x18001180b  mov     rcx, [rcx+38h]; Logger
0x18001180f  mov     [rsp+78h+id], rdi; id
0x180011814  mov     [rsp+78h+Logger], rsi; Logger
0x180011819  mov     [rsp+78h+_a4], ebp; _a4
0x18001181d  call    WPP_SF_qDqS
0x180011822  mov     eax, ebx
0x180011824  add     rsp, 48h
0x180011828  pop     r15
0x18001182a  pop     r14
0x18001182c  pop     rdi
0x18001182d  pop     rsi
0x18001182e  pop     rbp
0x18001182f  pop     rbx
0x180011830  retn
```

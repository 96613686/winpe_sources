# WDLIB_Load

- ea: `0x180071c4c`
- end: `0x18007210d`
- name: `WDLIB_Load`
- size: `1217`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180068a9c`

## callees

- `0x18000116c`
- `0x180001308`
- `0x1800024a8`
- `0x18000b48c`
- `0x18004e93c`
- `0x180071c4c`
- `0x18007f42c`
- `0x18007f6a4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071fd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071fea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072001`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071fd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071fea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072001`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072018`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071dc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071e23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071e7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071ed5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071f2a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071dc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071e23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071e7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071ed5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180071f2a`

## string_xrefs

- `0x180071e65`: `Failed to allocate memory for hCreateEvent`

## pseudocode

```c
__int64 __fastcall WDLIB_Load(_QWORD *a1, __int64 a2, __int64 a3, int a4)
{
  char *v5; // rax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rbx
  int v10; // r8d
  int v11; // r9d
  _QWORD *v12; // r14
  HANDLE EventW; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  HANDLE *v17; // rsi
  char *v18; // rdx
  const char *v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  unsigned int v24; // edi
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  __int64 v30; // [rsp+60h] [rbp-20h] BYREF
  char *v31; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v32[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v33; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v35; // [rsp+C0h] [rbp+40h] BYREF
  const char *v36; // [rsp+C8h] [rbp+48h] BYREF

  v35 = a3;
  v34 = a2;
  *a1 = 0;
  a1[1] = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v35) = 3752;
    v36 = "Alloc TSWD=%d + NM/SM=%d (= %d) bytes for TSWd";
    LODWORD(v34) = 1888;
    LODWORD(v33) = 1864;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_1802A7951,
      a3,
      a4,
      (__int64)&v36,
      (__int64)&v33,
      (__int64)&v34,
      (__int64)&v35);
  }
  v5 = (char *)WDLIBRT_MemAlloc(0xEA8u);
  v9 = v5;
  if ( !v5 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v35) = 320;
      v33 = (__int64)"WDLIB_Load";
      LODWORD(v34) = -2147467259;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwint.cpp";
      v32[0] = "Failed alloc TSWD";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)qword_1802A79E0,
        v7,
        v8,
        (__int64)v32,
        (__int64)&v34,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v33);
    }
    v24 = -1073741801;
    v12 = a1 + 2;
    goto LABEL_38;
  }
  memset_0(v5, 0, 0xEA8u);
  *((_DWORD *)v9 + 268) = 0x40000000;
  *((_QWORD *)v9 + 17) = v9 + 1864;
  *((_QWORD *)v9 + 18) = v9 + 2120;
  *((_DWORD *)v9 + 30) = -1073741823;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v36 = (const char *)*((_QWORD *)v9 + 18);
    v30 = *((_QWORD *)v9 + 17);
    v32[0] = "pTSWd=%p, pSM=%p, pNM=%p, sizeof(TSWd)=%u, sizeof(SM)=%u, sizeof(NM)=%u";
    v35 = 1632;
    v34 = 256;
    v33 = 1864;
    v31 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v9 + 2120,
      (unsigned int)&dword_1802A783C,
      v10,
      v11,
      (__int64)v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v36,
      (__int64)&v33,
      (__int64)&v34,
      (__int64)&v35);
  }
  *((_QWORD *)v9 + 1) = a1;
  v12 = a1 + 2;
  *v12 = v9;
  EventW = CreateEventW(0, 0, 0, 0);
  v17 = (HANDLE *)(v9 + 80);
  *((_QWORD *)v9 + 10) = EventW;
  if ( !EventW )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v35) = 355;
      v33 = (__int64)"WDLIB_Load";
      v18 = &byte_1802A77F7;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwint.cpp";
      v19 = "Failed to allocate memory for hConnEvent";
LABEL_21:
      v32[0] = v19;
      LODWORD(v34) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v14,
        (_DWORD)v18,
        v15,
        v16,
        (__int64)v32,
        (__int64)&v34,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v33);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v20 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v9 + 11) = v20;
  if ( !v20 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v35) = 362;
      v33 = (__int64)"WDLIB_Load";
      v18 = (char *)&dword_1802A790C;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwint.cpp";
      v19 = "Failed to allocate memory for hCreateEvent";
      goto LABEL_21;
    }
LABEL_22:
    v24 = -1073741801;
    if ( *v17 )
    {
      CloseHandle(*v17);
      *v17 = 0;
    }
    v25 = (void *)*((_QWORD *)v9 + 11);
    if ( v25 )
    {
      CloseHandle(v25);
      *((_QWORD *)v9 + 11) = 0;
    }
    v26 = (void *)*((_QWORD *)v9 + 12);
    if ( v26 )
    {
      CloseHandle(v26);
      *((_QWORD *)v9 + 12) = 0;
    }
    v27 = (void *)*((_QWORD *)v9 + 13);
    if ( v27 )
    {
      CloseHandle(v27);
      *((_QWORD *)v9 + 13) = 0;
    }
    v28 = (void *)*((_QWORD *)v9 + 14);
    if ( v28 )
    {
      CloseHandle(v28);
      *((_QWORD *)v9 + 14) = 0;
    }
    operator delete(v9);
LABEL_38:
    *v12 = 0;
    return v24;
  }
  v21 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v9 + 12) = v21;
  if ( !v21 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v35) = 369;
      v33 = (__int64)"WDLIB_Load";
      v18 = &byte_1802A78C7;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwint.cpp";
      v19 = "Failed to allocate memory for hSecEvent";
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v22 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v9 + 13) = v22;
  if ( !v22 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v35) = 376;
      v33 = (__int64)"WDLIB_Load";
      v18 = byte_1802A7791;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwint.cpp";
      v19 = "Failed to allocate memory for hSessKeyEvent";
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v23 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v9 + 14) = v23;
  if ( !v23 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v35) = 383;
      v33 = (__int64)"WDLIB_Load";
      v18 = (char *)&dword_1802A774C;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwint.cpp";
      v19 = "Failed to allocate memory for hClientDisconnectEvent";
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v24 = 0;
  *((_DWORD *)v9 + 372) = 1600;
  *((_DWORD *)v9 + 370) = 1600;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v35 = (__int64)"WDWLoad done";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v14,
      (unsigned int)&word_1802A77D6,
      v15,
      v16,
      (__int64)&v35);
  }
  return v24;
}

```

## disassembly

```asm
0x180071c4c  mov     r11, rsp
0x180071c4f  mov     [r11+18h], r8
0x180071c53  mov     [r11+10h], rdx
0x180071c57  push    rbp
0x180071c58  push    rbx
0x180071c59  push    rsi
0x180071c5a  push    rdi
0x180071c5b  push    r14
0x180071c5d  mov     rbp, rsp
0x180071c60  sub     rsp, 80h
0x180071c67  mov     qword ptr [rcx], 0
0x180071c6e  mov     r14, rcx
0x180071c71  mov     qword ptr [rcx+8], 0
0x180071c79  mov     edi, 0EA8h
0x180071c7e  mov     eax, cs:CallbackContext
0x180071c84  mov     esi, 748h
0x180071c89  cmp     eax, 4
0x180071c8c  jbe     short loc_180071CD3
0x180071c8e  lea     rax, aAllocTswdDNmSm; "Alloc TSWD=%d + NM/SM=%d (= %d) bytes f"...
0x180071c95  mov     dword ptr [rbp+arg_10], edi
0x180071c98  mov     [rbp+arg_18], rax
0x180071c9c  lea     rdx, byte_1802A7951
0x180071ca3  lea     rax, [rbp+arg_10]
0x180071ca7  mov     dword ptr [rbp+arg_8], 760h
0x180071cae  mov     [r11-70h], rax
0x180071cb2  lea     rax, [rbp+arg_8]
0x180071cb6  mov     [r11-78h], rax
0x180071cba  lea     rax, [rbp+arg_0]
0x180071cbe  mov     [r11-80h], rax
0x180071cc2  lea     rax, [rbp+arg_18]
0x180071cc6  mov     [rsp+80h+var_60], rax
0x180071ccb  mov     dword ptr [rbp+arg_0], esi
0x180071cce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180071cd3  mov     ecx, edi; Size
0x180071cd5  call    WDLIBRT_MemAlloc
0x180071cda  mov     rbx, rax
0x180071cdd  test    rax, rax
0x180071ce0  jz      loc_18007207A
0x180071ce6  mov     r8, rdi; Size
0x180071ce9  xor     edx, edx; Val
0x180071ceb  mov     rcx, rax; void *
0x180071cee  call    memset_0
0x180071cf3  lea     rcx, [rbx+748h]
0x180071cfa  mov     dword ptr [rbx+430h], 40000000h
0x180071d04  mov     [rbx+88h], rcx
0x180071d0b  lea     rcx, [rbx+848h]
0x180071d12  mov     [rbx+90h], rcx
0x180071d19  mov     dword ptr [rbx+78h], 0C0000001h
0x180071d20  mov     eax, cs:CallbackContext
0x180071d26  cmp     eax, 4
0x180071d29  jbe     loc_180071DB3
0x180071d2f  mov     rax, [rbx+90h]
0x180071d36  lea     rdx, dword_1802A783C
0x180071d3d  mov     [rbp+arg_18], rax
0x180071d41  mov     rax, [rbx+88h]
0x180071d48  mov     [rbp+var_20], rax
0x180071d4c  lea     rax, aPtswdPPsmPPnmP; "pTSWd=%p, pSM=%p, pNM=%p, sizeof(TSWd)="...
0x180071d53  mov     [rbp+var_10], rax
0x180071d57  lea     rax, [rbp+arg_10]
0x180071d5b  mov     [rsp+80h+var_30], rax
0x180071d60  lea     rax, [rbp+arg_8]
0x180071d64  mov     [rsp+80h+var_38], rax
0x180071d69  lea     rax, [rbp+arg_0]
0x180071d6d  mov     [rsp+80h+var_40], rax
0x180071d72  lea     rax, [rbp+arg_18]
0x180071d76  mov     [rsp+80h+var_48], rax
0x180071d7b  lea     rax, [rbp+var_20]
0x180071d7f  mov     [rsp+80h+var_50], rax
0x180071d84  lea     rax, [rbp+var_18]
0x180071d88  mov     [rsp+80h+var_58], rax
0x180071d8d  lea     rax, [rbp+var_10]
0x180071d91  mov     [rsp+80h+var_60], rax
0x180071d96  mov     [rbp+arg_10], 660h
0x180071d9e  mov     [rbp+arg_8], 100h
0x180071da6  mov     [rbp+arg_0], rsi
0x180071daa  mov     [rbp+var_18], rbx
0x180071dae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180071db3  mov     [rbx+8], r14
0x180071db7  xor     r9d, r9d; lpName
0x180071dba  add     r14, 10h
0x180071dbe  xor     r8d, r8d; bInitialState
0x180071dc1  xor     edx, edx; bManualReset
0x180071dc3  xor     ecx, ecx; lpEventAttributes
0x180071dc5  mov     [r14], rbx
0x180071dc8  call    cs:__imp_CreateEventW
0x180071dce  lea     rsi, [rbx+50h]
0x180071dd2  mov     [rsi], rax
0x180071dd5  test    rax, rax
0x180071dd8  jnz     short loc_180071E19
0x180071dda  mov     eax, cs:CallbackContext
0x180071de0  cmp     eax, 2
0x180071de3  jbe     loc_180071FB0
0x180071de9  lea     rax, aWdlibLoad; "WDLIB_Load"
0x180071df0  mov     dword ptr [rbp+arg_10], 163h
0x180071df7  mov     [rbp+arg_0], rax
0x180071dfb  lea     rdx, byte_1802A77F7
0x180071e02  lea     rax, aOnecoreTermsrv_35; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071e09  mov     [rbp+arg_18], rax
0x180071e0d  lea     rax, aFailedToAlloca_3; "Failed to allocate memory for hConnEven"...
0x180071e14  jmp     loc_180071F73
0x180071e19  xor     r9d, r9d; lpName
0x180071e1c  xor     r8d, r8d; bInitialState
0x180071e1f  xor     edx, edx; bManualReset
0x180071e21  xor     ecx, ecx; lpEventAttributes
0x180071e23  call    cs:__imp_CreateEventW
0x180071e29  mov     [rbx+58h], rax
0x180071e2d  test    rax, rax
0x180071e30  jnz     short loc_180071E71
0x180071e32  mov     eax, cs:CallbackContext
0x180071e38  cmp     eax, 2
0x180071e3b  jbe     loc_180071FB0
0x180071e41  lea     rax, aWdlibLoad; "WDLIB_Load"
0x180071e48  mov     dword ptr [rbp+arg_10], 16Ah
0x180071e4f  mov     [rbp+arg_0], rax
0x180071e53  lea     rdx, dword_1802A790C
0x180071e5a  lea     rax, aOnecoreTermsrv_35; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071e61  mov     [rbp+arg_18], rax
0x180071e65  lea     rax, aFailedToAlloca_12; "Failed to allocate memory for hCreateEv"...
0x180071e6c  jmp     loc_180071F73
0x180071e71  xor     r9d, r9d; lpName
0x180071e74  xor     r8d, r8d; bInitialState
0x180071e77  xor     edx, edx; bManualReset
0x180071e79  xor     ecx, ecx; lpEventAttributes
0x180071e7b  call    cs:__imp_CreateEventW
0x180071e81  mov     [rbx+60h], rax
0x180071e85  test    rax, rax
0x180071e88  jnz     short loc_180071EC9
0x180071e8a  mov     eax, cs:CallbackContext
0x180071e90  cmp     eax, 2
0x180071e93  jbe     loc_180071FB0
0x180071e99  lea     rax, aWdlibLoad; "WDLIB_Load"
0x180071ea0  mov     dword ptr [rbp+arg_10], 171h
0x180071ea7  mov     [rbp+arg_0], rax
0x180071eab  lea     rdx, byte_1802A78C7
0x180071eb2  lea     rax, aOnecoreTermsrv_35; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071eb9  mov     [rbp+arg_18], rax
0x180071ebd  lea     rax, aFailedToAlloca_0; "Failed to allocate memory for hSecEvent"
0x180071ec4  jmp     loc_180071F73
0x180071ec9  xor     r9d, r9d; lpName
0x180071ecc  xor     r8d, r8d; bInitialState
0x180071ecf  xor     ecx, ecx; lpEventAttributes
0x180071ed1  lea     edx, [r9+1]; bManualReset
0x180071ed5  call    cs:__imp_CreateEventW
0x180071edb  mov     [rbx+68h], rax
0x180071edf  test    rax, rax
0x180071ee2  jnz     short loc_180071F20
0x180071ee4  mov     eax, cs:CallbackContext
0x180071eea  cmp     eax, 2
0x180071eed  jbe     loc_180071FB0
0x180071ef3  lea     rax, aWdlibLoad; "WDLIB_Load"
0x180071efa  mov     dword ptr [rbp+arg_10], 178h
0x180071f01  mov     [rbp+arg_0], rax
0x180071f05  lea     rdx, byte_1802A7791
0x180071f0c  lea     rax, aOnecoreTermsrv_35; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071f13  mov     [rbp+arg_18], rax
0x180071f17  lea     rax, aFailedToAlloca_9; "Failed to allocate memory for hSessKeyE"...
0x180071f1e  jmp     short loc_180071F73
0x180071f20  xor     r9d, r9d; lpName
0x180071f23  xor     r8d, r8d; bInitialState
0x180071f26  xor     edx, edx; bManualReset
0x180071f28  xor     ecx, ecx; lpEventAttributes
0x180071f2a  call    cs:__imp_CreateEventW
0x180071f30  mov     [rbx+70h], rax
0x180071f34  test    rax, rax
0x180071f37  jnz     loc_180072033
0x180071f3d  mov     eax, cs:CallbackContext
0x180071f43  cmp     eax, 2
0x180071f46  jbe     short loc_180071FB0
0x180071f48  lea     rax, aWdlibLoad; "WDLIB_Load"
0x180071f4f  mov     dword ptr [rbp+arg_10], 17Fh
0x180071f56  mov     [rbp+arg_0], rax
0x180071f5a  lea     rdx, dword_1802A774C
0x180071f61  lea     rax, aOnecoreTermsrv_35; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071f68  mov     [rbp+arg_18], rax
0x180071f6c  lea     rax, aFailedToAlloca_21; "Failed to allocate memory for hClientDi"...
0x180071f73  mov     [rbp+var_10], rax
0x180071f77  lea     rax, [rbp+arg_0]
0x180071f7b  mov     [rsp+80h+var_40], rax
0x180071f80  lea     rax, [rbp+arg_10]
0x180071f84  mov     [rsp+80h+var_48], rax
0x180071f89  lea     rax, [rbp+arg_18]
0x180071f8d  mov     [rsp+80h+var_50], rax
0x180071f92  lea     rax, [rbp+arg_8]
0x180071f96  mov     [rsp+80h+var_58], rax
0x180071f9b  lea     rax, [rbp+var_10]
0x180071f9f  mov     [rsp+80h+var_60], rax
0x180071fa4  mov     dword ptr [rbp+arg_8], 80004005h
0x180071fab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180071fb0  mov     rcx, [rsi]; hObject
0x180071fb3  mov     edi, 0C0000017h
0x180071fb8  test    rcx, rcx
0x180071fbb  jz      short loc_180071FCA
0x180071fbd  call    cs:__imp_CloseHandle
0x180071fc3  mov     qword ptr [rsi], 0
0x180071fca  mov     rcx, [rbx+58h]; hObject
0x180071fce  test    rcx, rcx
0x180071fd1  jz      short loc_180071FE1
0x180071fd3  call    cs:__imp_CloseHandle
0x180071fd9  mov     qword ptr [rbx+58h], 0
0x180071fe1  mov     rcx, [rbx+60h]; hObject
0x180071fe5  test    rcx, rcx
0x180071fe8  jz      short loc_180071FF8
0x180071fea  call    cs:__imp_CloseHandle
0x180071ff0  mov     qword ptr [rbx+60h], 0
0x180071ff8  mov     rcx, [rbx+68h]; hObject
0x180071ffc  test    rcx, rcx
0x180071fff  jz      short loc_18007200F
0x180072001  call    cs:__imp_CloseHandle
0x180072007  mov     qword ptr [rbx+68h], 0
0x18007200f  mov     rcx, [rbx+70h]; hObject
0x180072013  test    rcx, rcx
0x180072016  jz      short loc_180072026
0x180072018  call    cs:__imp_CloseHandle
0x18007201e  mov     qword ptr [rbx+70h], 0
0x180072026  mov     rcx, rbx; Block
0x180072029  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007202e  jmp     loc_1800720F6
0x180072033  mov     eax, 640h
0x180072038  xor     edi, edi
0x18007203a  mov     [rbx+5D0h], eax
0x180072040  mov     [rbx+5C8h], eax
0x180072046  mov     eax, cs:CallbackContext
0x18007204c  cmp     eax, 4
0x18007204f  jbe     loc_1800720FD
0x180072055  lea     rax, aWdwloadDone; "WDWLoad done"
0x18007205c  mov     [rbp+arg_10], rax
0x180072060  lea     rdx, word_1802A77D6
0x180072067  lea     rax, [rbp+arg_10]
0x18007206b  mov     [rsp+80h+var_60], rax
0x180072070  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180072075  jmp     loc_1800720FD
0x18007207a  mov     eax, cs:CallbackContext
0x180072080  cmp     eax, 2
0x180072083  jbe     short loc_1800720ED
0x180072085  lea     rax, aWdlibLoad; "WDLIB_Load"
0x18007208c  mov     dword ptr [rbp+arg_10], 140h
0x180072093  mov     [rbp+arg_0], rax
0x180072097  lea     rdx, qword_1802A79E0
0x18007209e  lea     rax, aOnecoreTermsrv_35; "onecore\\termsrv\\rdpplatform\\drivers"...
0x1800720a5  mov     dword ptr [rbp+arg_8], 80004005h
0x1800720ac  mov     [rbp+arg_18], rax
0x1800720b0  lea     rax, aFailedAllocTsw; "Failed alloc TSWD"
0x1800720b7  mov     [rbp+var_10], rax
0x1800720bb  lea     rax, [rbp+arg_0]
0x1800720bf  mov     [rsp+80h+var_40], rax
0x1800720c4  lea     rax, [rbp+arg_10]
0x1800720c8  mov     [rsp+80h+var_48], rax
0x1800720cd  lea     rax, [rbp+arg_18]
0x1800720d1  mov     [rsp+80h+var_50], rax
0x1800720d6  lea     rax, [rbp+arg_8]
0x1800720da  mov     [rsp+80h+var_58], rax
0x1800720df  lea     rax, [rbp+var_10]
0x1800720e3  mov     [rsp+80h+var_60], rax
0x1800720e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800720ed  mov     edi, 0C0000017h
0x1800720f2  add     r14, 10h
0x1800720f6  mov     qword ptr [r14], 0
0x1800720fd  mov     eax, edi
0x1800720ff  add     rsp, 80h
0x180072106  pop     r14
0x180072108  pop     rdi
0x180072109  pop     rsi
0x18007210a  pop     rbx
0x18007210b  pop     rbp
0x18007210c  retn
```

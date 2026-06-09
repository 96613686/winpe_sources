# CHttpIoSessionWinHttp::Initialize(ushort const *,RdpXInterfaceProxyResolver *,bool)

- ea: `0x18009d310`
- end: `0x18009d5fb`
- name: `?Initialize@CHttpIoSessionWinHttp@@UEAAJPEBGPEAURdpXInterfaceProxyResolver@@_N@Z`
- size: `747`
- prototype: `int(CHttpIoSessionWinHttp *__hidden this, const unsigned __int16 *, struct RdpXInterfaceProxyResolver *, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001aa0`
- `0x180004a94`
- `0x180088810`
- `0x18009d310`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d539`
- `WINHTTP!WinHttpOpen` at `0x18009d398`
- `WINHTTP!WinHttpOpen` at `0x18009d398`
- `WINHTTP!WinHttpSetOption` at `0x18009d46d`
- `WINHTTP!WinHttpSetOption` at `0x18009d52b`
- `WINHTTP!WinHttpSetOption` at `0x18009d46d`
- `WINHTTP!WinHttpSetOption` at `0x18009d52b`

## string_xrefs

- `0x18009d3cf`: `WinHttpOpen failed`

## pseudocode

```c
__int64 __fastcall CHttpIoSessionWinHttp::Initialize(
        CHttpIoSessionWinHttp *this,
        const unsigned __int16 *a2,
        struct RdpXInterfaceProxyResolver *a3,
        char a4)
{
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  DWORD v11; // ebx
  void *v12; // rax
  signed int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ebx
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  void *v22; // rcx
  signed int LastError; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v28; // [rsp+50h] [rbp-19h] BYREF
  const char *v29; // [rsp+58h] [rbp-11h] BYREF
  int v30; // [rsp+60h] [rbp-9h] BYREF
  const char *v31; // [rsp+68h] [rbp-1h] BYREF
  const char *v32; // [rsp+70h] [rbp+7h] BYREF
  const char *v33; // [rsp+78h] [rbp+Fh] BYREF
  _QWORD v34[8]; // [rsp+80h] [rbp+17h] BYREF
  int Buffer; // [rsp+D0h] [rbp+67h] BYREF

  if ( IsWindowsVersionOrGreater((unsigned __int16)this, 3u, (unsigned __int16)a3) )
    v11 = 4;
  else
    v11 = a3 == 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    Buffer = v11;
    v29 = "Initializing session instance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)&word_1801B2C26,
      v9,
      v10,
      (__int64)&v29,
      (__int64)&Buffer);
  }
  v12 = WinHttpOpen(a2, v11, 0, 0, 0x10000000u);
  *((_QWORD *)this + 2) = v12;
  if ( v12 )
  {
    if ( a4 || (Buffer = 0, WinHttpSetOption(v12, 0x58u, &Buffer, 4u)) )
    {
      v22 = (void *)*((_QWORD *)this + 2);
      v30 = 0;
      if ( WinHttpSetOption(v22, 0x5Au, &v30, 4u) )
      {
        v17 = 0;
        if ( a3 )
        {
          (**(void (__fastcall ***)(struct RdpXInterfaceProxyResolver *))a3)(a3);
          *((_QWORD *)this + 3) = a3;
        }
      }
      else
      {
        LastError = GetLastError();
        v17 = LastError;
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          Buffer = 314;
          v34[0] = "WinHttpSetOption failed";
          LODWORD(v29) = v17;
          v33 = "Initialize";
          v32 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
          v31 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v24,
            (unsigned int)word_1801B2B42,
            v25,
            v26,
            (__int64)&v31,
            (__int64)&v29,
            (__int64)&v32,
            (__int64)&Buffer,
            (__int64)&v33,
            (__int64)v34);
        }
      }
    }
    else
    {
      v18 = GetLastError();
      v17 = v18;
      if ( v18 > 0 )
        v17 = (unsigned __int16)v18 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v28 = 303;
        v33 = "WinHttpSetOption failed";
        LODWORD(v29) = v17;
        v32 = "Initialize";
        v31 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v34[0] = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v19,
          (unsigned int)&word_1801B2B8E,
          v20,
          v21,
          (__int64)v34,
          (__int64)&v29,
          (__int64)&v31,
          (__int64)&v28,
          (__int64)&v32,
          (__int64)&v33);
      }
    }
  }
  else
  {
    v13 = GetLastError();
    v17 = v13;
    if ( v13 > 0 )
      v17 = (unsigned __int16)v13 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      Buffer = 289;
      v29 = "WinHttpOpen failed";
      v28 = v17;
      v31 = "Initialize";
      v32 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v33 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)word_1801B2BDA,
        v15,
        v16,
        (__int64)&v33,
        (__int64)&v28,
        (__int64)&v32,
        (__int64)&Buffer,
        (__int64)&v31,
        (__int64)&v29);
    }
  }
  return v17;
}

```

## disassembly

```asm
0x18009d310  push    rbp
0x18009d312  push    rbx
0x18009d313  push    rsi
0x18009d314  push    rdi
0x18009d315  push    r14
0x18009d317  push    r15
0x18009d319  lea     rbp, [rsp-2Fh]
0x18009d31e  sub     rsp, 98h
0x18009d325  mov     r15, rdx
0x18009d328  mov     r14b, r9b
0x18009d32b  mov     edx, 3; unsigned __int16
0x18009d330  mov     rdi, r8
0x18009d333  mov     rsi, rcx
0x18009d336  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18009d33b  test    al, al
0x18009d33d  jz      short loc_18009D346
0x18009d33f  mov     ebx, 4
0x18009d344  jmp     short loc_18009D34E
0x18009d346  xor     ebx, ebx
0x18009d348  test    rdi, rdi
0x18009d34b  setz    bl
0x18009d34e  mov     eax, cs:CallbackContext
0x18009d354  cmp     eax, 4
0x18009d357  jbe     short loc_18009D385
0x18009d359  lea     rax, aInitializingSe; "Initializing session instance"
0x18009d360  mov     [rbp+57h+Buffer], ebx
0x18009d363  mov     [rbp+57h+var_68], rax
0x18009d367  lea     rdx, word_1801B2C26
0x18009d36e  lea     rax, [rbp+57h+Buffer]
0x18009d372  mov     [rsp+0C0h+var_98], rax
0x18009d377  lea     rax, [rbp+57h+var_68]
0x18009d37b  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18009d380  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009d385  xor     r9d, r9d; pszProxyBypassW
0x18009d388  mov     [rsp+0C0h+dwFlags], 10000000h; dwFlags
0x18009d390  xor     r8d, r8d; pszProxyW
0x18009d393  mov     edx, ebx; dwAccessType
0x18009d395  mov     rcx, r15; pszAgentW
0x18009d398  call    cs:__imp_WinHttpOpen
0x18009d39e  mov     [rsi+10h], rax
0x18009d3a2  test    rax, rax
0x18009d3a5  jnz     loc_18009D44C
0x18009d3ab  call    cs:__imp_GetLastError
0x18009d3b1  mov     ebx, eax
0x18009d3b3  test    eax, eax
0x18009d3b5  jle     short loc_18009D3C0
0x18009d3b7  movzx   ebx, ax
0x18009d3ba  or      ebx, 80070000h
0x18009d3c0  mov     eax, cs:CallbackContext
0x18009d3c6  cmp     eax, 2
0x18009d3c9  jbe     loc_18009D5E9
0x18009d3cf  lea     rax, aWinhttpopenFai; "WinHttpOpen failed"
0x18009d3d6  mov     [rbp+57h+Buffer], 121h
0x18009d3dd  mov     [rbp+57h+var_68], rax
0x18009d3e1  lea     rdx, word_1801B2BDA
0x18009d3e8  lea     rax, aInitialize; "Initialize"
0x18009d3ef  mov     [rbp+57h+var_70], ebx
0x18009d3f2  mov     [rbp+57h+var_58], rax
0x18009d3f6  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009d3fd  mov     [rbp+57h+var_50], rax
0x18009d401  lea     rax, aErrorCondition; "Error condition failed"
0x18009d408  mov     [rbp+57h+var_48], rax
0x18009d40c  lea     rax, [rbp+57h+var_68]
0x18009d410  mov     [rsp+0C0h+var_78], rax
0x18009d415  lea     rax, [rbp+57h+var_58]
0x18009d419  mov     [rsp+0C0h+var_80], rax
0x18009d41e  lea     rax, [rbp+57h+Buffer]
0x18009d422  mov     [rsp+0C0h+var_88], rax
0x18009d427  lea     rax, [rbp+57h+var_50]
0x18009d42b  mov     [rsp+0C0h+var_90], rax
0x18009d430  lea     rax, [rbp+57h+var_70]
0x18009d434  mov     [rsp+0C0h+var_98], rax
0x18009d439  lea     rax, [rbp+57h+var_48]
0x18009d43d  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18009d442  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009d447  jmp     loc_18009D5E9
0x18009d44c  test    r14b, r14b
0x18009d44f  jnz     loc_18009D512
0x18009d455  mov     r9d, 4; dwBufferLength
0x18009d45b  mov     [rbp+57h+Buffer], 0
0x18009d462  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18009d466  mov     rcx, rax; hInternet
0x18009d469  lea     edx, [r9+54h]; dwOption
0x18009d46d  call    cs:__imp_WinHttpSetOption
0x18009d473  test    eax, eax
0x18009d475  jnz     loc_18009D512
0x18009d47b  call    cs:__imp_GetLastError
0x18009d481  mov     ebx, eax
0x18009d483  test    eax, eax
0x18009d485  jle     short loc_18009D490
0x18009d487  movzx   ebx, ax
0x18009d48a  or      ebx, 80070000h
0x18009d490  mov     eax, cs:CallbackContext
0x18009d496  cmp     eax, 2
0x18009d499  jbe     loc_18009D5E9
0x18009d49f  lea     rax, aWinhttpsetopti_0; "WinHttpSetOption failed"
0x18009d4a6  mov     [rbp+57h+var_70], 12Fh
0x18009d4ad  mov     [rbp+57h+var_48], rax
0x18009d4b1  lea     rdx, word_1801B2B8E
0x18009d4b8  lea     rax, aInitialize; "Initialize"
0x18009d4bf  mov     dword ptr [rbp+57h+var_68], ebx
0x18009d4c2  mov     [rbp+57h+var_50], rax
0x18009d4c6  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009d4cd  mov     [rbp+57h+var_58], rax
0x18009d4d1  lea     rax, aErrorCondition; "Error condition failed"
0x18009d4d8  mov     [rbp+57h+var_40], rax
0x18009d4dc  lea     rax, [rbp+57h+var_48]
0x18009d4e0  mov     [rsp+0C0h+var_78], rax
0x18009d4e5  lea     rax, [rbp+57h+var_50]
0x18009d4e9  mov     [rsp+0C0h+var_80], rax
0x18009d4ee  lea     rax, [rbp+57h+var_70]
0x18009d4f2  mov     [rsp+0C0h+var_88], rax
0x18009d4f7  lea     rax, [rbp+57h+var_58]
0x18009d4fb  mov     [rsp+0C0h+var_90], rax
0x18009d500  lea     rax, [rbp+57h+var_68]
0x18009d504  mov     [rsp+0C0h+var_98], rax
0x18009d509  lea     rax, [rbp+57h+var_40]
0x18009d50d  jmp     loc_18009D43D
0x18009d512  mov     rcx, [rsi+10h]; hInternet
0x18009d516  lea     r8, [rbp+57h+var_60]; lpBuffer
0x18009d51a  mov     r9d, 4; dwBufferLength
0x18009d520  mov     [rbp+57h+var_60], 0
0x18009d527  lea     edx, [r9+56h]; dwOption
0x18009d52b  call    cs:__imp_WinHttpSetOption
0x18009d531  test    eax, eax
0x18009d533  jnz     loc_18009D5D0
0x18009d539  call    cs:__imp_GetLastError
0x18009d53f  mov     ebx, eax
0x18009d541  test    eax, eax
0x18009d543  jle     short loc_18009D54E
0x18009d545  movzx   ebx, ax
0x18009d548  or      ebx, 80070000h
0x18009d54e  mov     eax, cs:CallbackContext
0x18009d554  cmp     eax, 2
0x18009d557  jbe     loc_18009D5E9
0x18009d55d  lea     rax, aWinhttpsetopti_0; "WinHttpSetOption failed"
0x18009d564  mov     [rbp+57h+Buffer], 13Ah
0x18009d56b  mov     [rbp+57h+var_40], rax
0x18009d56f  lea     rdx, word_1801B2B42
0x18009d576  lea     rax, aInitialize; "Initialize"
0x18009d57d  mov     dword ptr [rbp+57h+var_68], ebx
0x18009d580  mov     [rbp+57h+var_48], rax
0x18009d584  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009d58b  mov     [rbp+57h+var_50], rax
0x18009d58f  lea     rax, aErrorCondition; "Error condition failed"
0x18009d596  mov     [rbp+57h+var_58], rax
0x18009d59a  lea     rax, [rbp+57h+var_40]
0x18009d59e  mov     [rsp+0C0h+var_78], rax
0x18009d5a3  lea     rax, [rbp+57h+var_48]
0x18009d5a7  mov     [rsp+0C0h+var_80], rax
0x18009d5ac  lea     rax, [rbp+57h+Buffer]
0x18009d5b0  mov     [rsp+0C0h+var_88], rax
0x18009d5b5  lea     rax, [rbp+57h+var_50]
0x18009d5b9  mov     [rsp+0C0h+var_90], rax
0x18009d5be  lea     rax, [rbp+57h+var_68]
0x18009d5c2  mov     [rsp+0C0h+var_98], rax
0x18009d5c7  lea     rax, [rbp+57h+var_58]
0x18009d5cb  jmp     loc_18009D43D
0x18009d5d0  xor     ebx, ebx
0x18009d5d2  test    rdi, rdi
0x18009d5d5  jz      short loc_18009D5E9
0x18009d5d7  mov     rcx, [rdi]
0x18009d5da  mov     rax, [rcx]
0x18009d5dd  mov     rcx, rdi
0x18009d5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d5e5  mov     [rsi+18h], rdi
0x18009d5e9  mov     eax, ebx
0x18009d5eb  add     rsp, 98h
0x18009d5f2  pop     r15
0x18009d5f4  pop     r14
0x18009d5f6  pop     rdi
0x18009d5f7  pop     rsi
0x18009d5f8  pop     rbx
0x18009d5f9  pop     rbp
0x18009d5fa  retn
```

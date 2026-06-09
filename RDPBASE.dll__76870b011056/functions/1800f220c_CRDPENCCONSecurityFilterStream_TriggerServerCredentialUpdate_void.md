# CRDPENCCONSecurityFilterStream::TriggerServerCredentialUpdate(void)

- ea: `0x1800f220c`
- end: `0x1800f23b8`
- name: `?TriggerServerCredentialUpdate@CRDPENCCONSecurityFilterStream@@AEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(CRDPENCCONSecurityFilterStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ec1c0`

## callees

- `0x180001aa0`
- `0x1800f220c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2300`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f2234`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f2234`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f22f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f22f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f23a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f23a8`

## string_xrefs

- `0x1800f2272`: `Failed to open TS Certificate Update Event`
- `0x1800f2328`: `Failed to set TS Certificate Update Event`
- `0x1800f228b`: `TriggerServerCredentialUpdate`
- `0x1800f2341`: `TriggerServerCredentialUpdate`

## pseudocode

```c
__int64 __fastcall CRDPENCCONSecurityFilterStream::TriggerServerCredentialUpdate(CRDPENCCONSecurityFilterStream *this)
{
  const WCHAR *v1; // r8
  signed int v2; // ebx
  HANDLE v3; // rdi
  signed int LastError; // eax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  signed int v8; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v13; // [rsp+50h] [rbp-10h] BYREF
  const char *v14; // [rsp+58h] [rbp-8h] BYREF
  int v15; // [rsp+80h] [rbp+20h] BYREF
  signed int v16; // [rsp+88h] [rbp+28h] BYREF
  const char *v17; // [rsp+90h] [rbp+30h] BYREF
  const char *v18; // [rsp+98h] [rbp+38h] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 35);
  if ( v1 )
  {
    v2 = -2147467263;
    v3 = OpenEventW(2u, 0, v1);
    if ( v3 )
      goto LABEL_20;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_20:
      if ( !SetEvent(v3) )
      {
        v8 = GetLastError();
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        if ( v2 < 0 && (unsigned int)CallbackContext > 2 )
        {
          v15 = 3830;
          v17 = "Failed to set TS Certificate Update Event";
          v16 = v2;
          v18 = "TriggerServerCredentialUpdate";
          v14 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
          v13 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v9,
            (unsigned int)&word_1801BFEF6,
            v10,
            v11,
            (__int64)&v13,
            (__int64)&v16,
            (__int64)&v14,
            (__int64)&v15,
            (__int64)&v18,
            (__int64)&v17);
        }
      }
      if ( v3 )
        CloseHandle(v3);
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v15 = 3825;
      v17 = "Failed to open TS Certificate Update Event";
      v16 = v2;
      v18 = "TriggerServerCredentialUpdate";
      v13 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v14 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)byte_1801BFF4B,
        v6,
        v7,
        (__int64)&v14,
        (__int64)&v16,
        (__int64)&v13,
        (__int64)&v15,
        (__int64)&v18,
        (__int64)&v17);
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800f220c  push    rbp
0x1800f220e  push    rbx
0x1800f220f  push    rdi
0x1800f2210  mov     rbp, rsp
0x1800f2213  sub     rsp, 60h
0x1800f2217  mov     r8, [rcx+118h]; lpName
0x1800f221e  test    r8, r8
0x1800f2221  jnz     short loc_1800F222A
0x1800f2223  xor     ebx, ebx
0x1800f2225  jmp     loc_1800F23AE
0x1800f222a  xor     edx, edx; bInheritHandle
0x1800f222c  mov     ebx, 80004001h
0x1800f2231  lea     ecx, [rdx+2]; dwDesiredAccess
0x1800f2234  call    cs:__imp_OpenEventW
0x1800f223a  mov     rdi, rax
0x1800f223d  test    rax, rax
0x1800f2240  jnz     loc_1800F22EF
0x1800f2246  call    cs:__imp_GetLastError
0x1800f224c  mov     ebx, eax
0x1800f224e  test    eax, eax
0x1800f2250  jle     short loc_1800F225B
0x1800f2252  movzx   ebx, ax
0x1800f2255  or      ebx, 80070000h
0x1800f225b  test    ebx, ebx
0x1800f225d  jns     loc_1800F22EF
0x1800f2263  mov     eax, cs:CallbackContext
0x1800f2269  cmp     eax, 2
0x1800f226c  jbe     loc_1800F23AE
0x1800f2272  lea     rax, aFailedToOpenTs; "Failed to open TS Certificate Update Ev"...
0x1800f2279  mov     [rbp+arg_0], 0EF1h
0x1800f2280  mov     [rbp+arg_10], rax
0x1800f2284  lea     rdx, byte_1801BFF4B
0x1800f228b  lea     rax, aTriggerserverc; "TriggerServerCredentialUpdate"
0x1800f2292  mov     [rbp+arg_8], ebx
0x1800f2295  mov     [rbp+arg_18], rax
0x1800f2299  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f22a0  mov     [rbp+var_10], rax
0x1800f22a4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f22ab  mov     [rbp+var_8], rax
0x1800f22af  lea     rax, [rbp+arg_10]
0x1800f22b3  mov     [rsp+60h+var_18], rax
0x1800f22b8  lea     rax, [rbp+arg_18]
0x1800f22bc  mov     [rsp+60h+var_20], rax
0x1800f22c1  lea     rax, [rbp+arg_0]
0x1800f22c5  mov     [rsp+60h+var_28], rax
0x1800f22ca  lea     rax, [rbp+var_10]
0x1800f22ce  mov     [rsp+60h+var_30], rax
0x1800f22d3  lea     rax, [rbp+arg_8]
0x1800f22d7  mov     [rsp+60h+var_38], rax
0x1800f22dc  lea     rax, [rbp+var_8]
0x1800f22e0  mov     [rsp+60h+var_40], rax
0x1800f22e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800f22ea  jmp     loc_1800F23AE
0x1800f22ef  mov     rcx, rdi; hEvent
0x1800f22f2  call    cs:__imp_SetEvent
0x1800f22f8  test    eax, eax
0x1800f22fa  jnz     loc_1800F23A0
0x1800f2300  call    cs:__imp_GetLastError
0x1800f2306  mov     ebx, eax
0x1800f2308  test    eax, eax
0x1800f230a  jle     short loc_1800F2315
0x1800f230c  movzx   ebx, ax
0x1800f230f  or      ebx, 80070000h
0x1800f2315  test    ebx, ebx
0x1800f2317  jns     loc_1800F23A0
0x1800f231d  mov     eax, cs:CallbackContext
0x1800f2323  cmp     eax, 2
0x1800f2326  jbe     short loc_1800F23A0
0x1800f2328  lea     rax, aFailedToSetTsC; "Failed to set TS Certificate Update Eve"...
0x1800f232f  mov     [rbp+arg_0], 0EF6h
0x1800f2336  mov     [rbp+arg_10], rax
0x1800f233a  lea     rdx, word_1801BFEF6
0x1800f2341  lea     rax, aTriggerserverc; "TriggerServerCredentialUpdate"
0x1800f2348  mov     [rbp+arg_8], ebx
0x1800f234b  mov     [rbp+arg_18], rax
0x1800f234f  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f2356  mov     [rbp+var_8], rax
0x1800f235a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f2361  mov     [rbp+var_10], rax
0x1800f2365  lea     rax, [rbp+arg_10]
0x1800f2369  mov     [rsp+60h+var_18], rax
0x1800f236e  lea     rax, [rbp+arg_18]
0x1800f2372  mov     [rsp+60h+var_20], rax
0x1800f2377  lea     rax, [rbp+arg_0]
0x1800f237b  mov     [rsp+60h+var_28], rax
0x1800f2380  lea     rax, [rbp+var_8]
0x1800f2384  mov     [rsp+60h+var_30], rax
0x1800f2389  lea     rax, [rbp+arg_8]
0x1800f238d  mov     [rsp+60h+var_38], rax
0x1800f2392  lea     rax, [rbp+var_10]
0x1800f2396  mov     [rsp+60h+var_40], rax
0x1800f239b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800f23a0  test    rdi, rdi
0x1800f23a3  jz      short loc_1800F23AE
0x1800f23a5  mov     rcx, rdi; hObject
0x1800f23a8  call    cs:__imp_CloseHandle
0x1800f23ae  mov     eax, ebx
0x1800f23b0  add     rsp, 60h
0x1800f23b4  pop     rdi
0x1800f23b5  pop     rbx
0x1800f23b6  pop     rbp
0x1800f23b7  retn
```

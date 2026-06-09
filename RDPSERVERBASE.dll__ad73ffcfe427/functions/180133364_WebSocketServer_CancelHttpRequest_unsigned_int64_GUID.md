# WebSocketServer::CancelHttpRequest(unsigned __int64,_GUID)

- ea: `0x180133364`
- end: `0x180133524`
- name: `?CancelHttpRequest@WebSocketServer@@AEAAX_KU_GUID@@@Z`
- size: `448`
- prototype: `void(WebSocketServer *__hidden this, unsigned __int64, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18013352c`
- `0x1801344cc`

## callees

- `0x18000116c`
- `0x18000202c`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x180133364`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1801333f0`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1801333f0`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1801333bb`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1801333bb`
- `HTTPAPI!HttpCancelHttpRequest` at `0x1801333ce`
- `HTTPAPI!HttpCancelHttpRequest` at `0x1801333ce`

## pseudocode

```c
void __fastcall WebSocketServer::CancelHttpRequest(WebSocketServer *this, HTTP_REQUEST_ID a2, struct _GUID *a3)
{
  char *v6; // rax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  struct _OVERLAPPED *v10; // rbx
  ULONG v11; // eax
  signed int v12; // edi
  int v13; // r8d
  int v14; // r9d
  int v15; // [rsp+50h] [rbp-30h] BYREF
  const char *v16; // [rsp+58h] [rbp-28h] BYREF
  const char *v17; // [rsp+60h] [rbp-20h] BYREF
  const char *v18; // [rsp+68h] [rbp-18h] BYREF
  const char *v19; // [rsp+70h] [rbp-10h] BYREF
  int v20; // [rsp+B8h] [rbp+38h] BYREF

  v6 = (char *)operator new(0x38u);
  v10 = (struct _OVERLAPPED *)v6;
  if ( !v6 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v20 = 2485;
      v18 = "Failed allocationg OVERLAPPED_INFO";
      v15 = -2147024882;
      v17 = "CancelHttpRequest";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v19 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)&word_18029305E,
        v8,
        v9,
        (__int64)&v19,
        (__int64)&v15,
        (__int64)&v16,
        (__int64)&v20,
        (__int64)&v17,
        (__int64)&v18);
    }
    v10 = 0;
    goto LABEL_11;
  }
  *(_OWORD *)v6 = 0;
  *((_OWORD *)v6 + 1) = 0;
  *((_DWORD *)v6 + 8) = 1;
  *(struct _GUID *)(v6 + 36) = *a3;
  StartThreadpoolIo(*((PTP_IO *)this + 20));
  v11 = HttpCancelHttpRequest(*((HANDLE *)this + 19), a2, v10);
  v12 = v11;
  if ( v11 && v11 != 997 )
  {
    CancelThreadpoolIo(*((PTP_IO *)this + 20));
    if ( (unsigned int)CallbackContext > 2 )
    {
      v20 = 2495;
      v16 = "CancelHttpRequest";
      v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v15 = v12;
      v18 = "HttpCancelHttpRequest failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&word_180292FCE,
        v13,
        v14,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)&v17,
        (__int64)&v20,
        (__int64)&v16);
    }
LABEL_11:
    operator delete(v10);
  }
}

```

## disassembly

```asm
0x180133364  mov     [rsp-18h+arg_0], rbx
0x180133369  mov     [rsp-18h+arg_8], rsi
0x18013336e  push    rbp
0x18013336f  push    rdi
0x180133370  push    r14
0x180133372  mov     rbp, rsp
0x180133375  sub     rsp, 80h
0x18013337c  mov     rsi, rcx
0x18013337f  mov     rdi, r8
0x180133382  mov     ecx, 38h ; '8'; Size
0x180133387  mov     r14, rdx
0x18013338a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18013338f  mov     rbx, rax
0x180133392  test    rax, rax
0x180133395  jz      loc_18013347B
0x18013339b  xorps   xmm0, xmm0
0x18013339e  movups  xmmword ptr [rax], xmm0
0x1801333a1  movups  xmmword ptr [rax+10h], xmm0
0x1801333a5  mov     dword ptr [rax+20h], 1
0x1801333ac  movups  xmm0, xmmword ptr [rdi]
0x1801333af  movdqu  xmmword ptr [rax+24h], xmm0
0x1801333b4  mov     rcx, [rsi+0A0h]; pio
0x1801333bb  call    cs:__imp_StartThreadpoolIo
0x1801333c1  mov     rcx, [rsi+98h]; RequestQueueHandle
0x1801333c8  mov     r8, rbx; Overlapped
0x1801333cb  mov     rdx, r14; RequestId
0x1801333ce  call    cs:__imp_HttpCancelHttpRequest
0x1801333d4  mov     edi, eax
0x1801333d6  test    eax, eax
0x1801333d8  jz      loc_18013350C
0x1801333de  cmp     eax, 3E5h
0x1801333e3  jz      loc_18013350C
0x1801333e9  mov     rcx, [rsi+0A0h]; pio
0x1801333f0  call    cs:__imp_CancelThreadpoolIo
0x1801333f6  mov     ecx, cs:CallbackContext
0x1801333fc  cmp     ecx, 2
0x1801333ff  jbe     loc_180133504
0x180133405  mov     [rbp+arg_18], 9BFh
0x18013340c  lea     rax, aCancelhttprequ; "CancelHttpRequest"
0x180133413  mov     [rbp+var_28], rax
0x180133417  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013341e  mov     [rbp+var_20], rax
0x180133422  test    edi, edi
0x180133424  jle     short loc_18013342F
0x180133426  movzx   edi, di
0x180133429  or      edi, 80070000h
0x18013342f  lea     rax, aHttpcancelhttp_0; "HttpCancelHttpRequest failed"
0x180133436  mov     [rbp+var_30], edi
0x180133439  mov     [rbp+var_18], rax
0x18013343d  lea     rdx, word_180292FCE
0x180133444  lea     rax, [rbp+var_28]
0x180133448  mov     [rsp+80h+var_40], rax
0x18013344d  lea     rax, [rbp+arg_18]
0x180133451  mov     [rsp+80h+var_48], rax
0x180133456  lea     rax, [rbp+var_20]
0x18013345a  mov     [rsp+80h+var_50], rax
0x18013345f  lea     rax, [rbp+var_30]
0x180133463  mov     [rsp+80h+var_58], rax
0x180133468  lea     rax, [rbp+var_18]
0x18013346c  mov     [rsp+80h+var_60], rax
0x180133471  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180133476  jmp     loc_180133504
0x18013347b  mov     eax, cs:CallbackContext
0x180133481  cmp     eax, 2
0x180133484  jbe     short loc_180133502
0x180133486  lea     rax, aFailedAllocati_1; "Failed allocationg OVERLAPPED_INFO"
0x18013348d  mov     [rbp+arg_18], 9B5h
0x180133494  mov     [rbp+var_18], rax
0x180133498  lea     rdx, word_18029305E
0x18013349f  lea     rax, aCancelhttprequ; "CancelHttpRequest"
0x1801334a6  mov     [rbp+var_30], 8007000Eh
0x1801334ad  mov     [rbp+var_20], rax
0x1801334b1  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801334b8  mov     [rbp+var_28], rax
0x1801334bc  lea     rax, aErrorCondition; "Error condition failed"
0x1801334c3  mov     [rbp+var_10], rax
0x1801334c7  lea     rax, [rbp+var_18]
0x1801334cb  mov     [rsp+80h+var_38], rax
0x1801334d0  lea     rax, [rbp+var_20]
0x1801334d4  mov     [rsp+80h+var_40], rax
0x1801334d9  lea     rax, [rbp+arg_18]
0x1801334dd  mov     [rsp+80h+var_48], rax
0x1801334e2  lea     rax, [rbp+var_28]
0x1801334e6  mov     [rsp+80h+var_50], rax
0x1801334eb  lea     rax, [rbp+var_30]
0x1801334ef  mov     [rsp+80h+var_58], rax
0x1801334f4  lea     rax, [rbp+var_10]
0x1801334f8  mov     [rsp+80h+var_60], rax
0x1801334fd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180133502  xor     ebx, ebx
0x180133504  mov     rcx, rbx; Block
0x180133507  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18013350c  lea     r11, [rsp+80h+var_s0]
0x180133514  mov     rbx, [r11+20h]
0x180133518  mov     rsi, [r11+28h]
0x18013351c  mov     rsp, r11
0x18013351f  pop     r14
0x180133521  pop     rdi
0x180133522  pop     rbp
0x180133523  retn
```

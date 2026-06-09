# WDW_OnSMConnected

- ea: `0x18017b774`
- end: `0x18017baff`
- name: `WDW_OnSMConnected`
- size: `907`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18018cf48`
- `0x18018f4b4`

## callees

- `0x18000116c`
- `0x180001f84`
- `0x18004e93c`
- `0x18007f6a4`
- `0x18017adb0`
- `0x18017b774`

## import_xrefs

- `RDPBASE!RDPCompress_GetContextSize` at `0x18017b83d`
- `RDPBASE!RDPCompress_GetContextSize` at `0x18017b83d`
- `RDPBASE!RDPCompress_InitSendContext` at `0x18017b890`
- `RDPBASE!RDPCompress_InitSendContext` at `0x18017b890`
- `RDPBASE!RDPDeCompress_GetContextSize` at `0x18017b9cb`
- `RDPBASE!RDPDeCompress_GetContextSize` at `0x18017b9cb`
- `RDPBASE!RDPCompress_InitRecvContext` at `0x18017b9fb`
- `RDPBASE!RDPCompress_InitRecvContext` at `0x18017b9fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18017b7cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18017b7cd`

## string_xrefs

- `0x18017b8de`: `Failed allocation of compression context buffer`
- `0x18017b8b8`: `Failed allocation of compression buffer`
- `0x18017ba14`: `Failed init of decompression buffers`
- `0x18017ba99`: `Failed alloc of decompression buffers`

## pseudocode

```c
void __fastcall WDW_OnSMConnected(__int64 a1, int a2, int a3, int a4)
{
  void *v6; // rcx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  unsigned int v11; // ecx
  unsigned int v12; // edi
  unsigned int v13; // ecx
  size_t ContextSize; // rsi
  __int64 v15; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rcx
  const char *v21; // rax
  int *v22; // rdx
  __int64 v23; // rax
  unsigned int v24; // edi
  __int64 v25; // rax
  int v26; // ecx
  int v27; // r8d
  __int64 v28; // r9
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  _QWORD v32[2]; // [rsp+50h] [rbp-10h] BYREF
  const char *v33; // [rsp+A0h] [rbp+40h] BYREF
  int v34; // [rsp+A8h] [rbp+48h] BYREF
  const char *v35; // [rsp+B0h] [rbp+50h] BYREF
  const char *v36; // [rsp+B8h] [rbp+58h] BYREF

  if ( (unsigned int)CallbackContext > 4 )
  {
    v34 = a2;
    v33 = "Got Connected Notification, rc %lu";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)&word_1802A4D46,
      a3,
      a4,
      (__int64)&v33,
      (__int64)&v34);
  }
  v6 = *(void **)(a1 + 80);
  *(_BYTE *)(a1 + 161) = 1;
  SetEvent(v6);
  if ( a2 == 1 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v35 = "WDW_OnSMConnected";
      v32[0] = "Connection error: winding down now";
      v34 = 684;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
      LODWORD(v33) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)&byte_1802A4C77,
        v8,
        v9,
        (__int64)v32,
        (__int64)&v33,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)&v35);
    }
    WDW_LogAndDisconnect(a1, 1, 211, 0, 0);
  }
  else if ( !*(_DWORD *)(a1 + 1352) )
  {
    v10 = *(_QWORD *)(a1 + 1152);
    if ( v10 )
    {
      v11 = *(_DWORD *)(v10 + 4);
      if ( (v11 & 0x80u) != 0 && (v11 & 0x1E00) >= 0x200 )
      {
        v12 = *(_DWORD *)(a1 + 1348);
        v13 = (v11 >> 9) & 0xF;
        if ( v13 <= v12 )
          v12 = v13;
        ContextSize = (unsigned int)RDPCompress_GetContextSize(v12);
        v15 = WDLIBRT_MemAlloc(ContextSize);
        *(_QWORD *)(a1 + 1248) = v15;
        if ( v15 )
        {
          v19 = WDLIBRT_MemAlloc(0x3E70u);
          *(_QWORD *)(a1 + 1264) = v19;
          if ( v19 )
          {
            v20 = *(_QWORD *)(a1 + 1248);
            *(_DWORD *)(a1 + 1256) = ContextSize;
            *(_DWORD *)(a1 + 1272) = 15984;
            *(_DWORD *)(a1 + 1244) = v12;
            RDPCompress_InitSendContext(v20, (unsigned int)ContextSize, v12);
            *(_BYTE *)(a1 + 1240) = 1;
            goto LABEL_21;
          }
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_21;
          v34 = 674;
          v21 = "Failed allocation of compression buffer";
          v22 = &dword_1802A4DB4;
        }
        else
        {
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_21;
          v34 = 678;
          v21 = "Failed allocation of compression context buffer";
          v22 = &dword_1802A4CBC;
        }
        v32[0] = v21;
        LODWORD(v33) = -2147467259;
        v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
        v35 = "WDW_OnSMConnected";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v16,
          (_DWORD)v22,
          v17,
          v18,
          (__int64)v32,
          (__int64)&v33,
          (__int64)&v36,
          (__int64)&v34,
          (__int64)&v35);
      }
    }
  }
LABEL_21:
  v23 = *(_QWORD *)(a1 + 1152);
  if ( v23 && *(char *)(v23 + 4) < 0 )
  {
    v24 = RDPDeCompress_GetContextSize(0);
    v25 = WDLIBRT_MemAlloc(v24);
    *(_QWORD *)(a1 + 1296) = v25;
    if ( v25 )
    {
      LOBYTE(v28) = 1;
      *(_DWORD *)(a1 + 1304) = v24;
      if ( !(unsigned int)RDPCompress_InitRecvContext(v25, v24, 0, v28) )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v35 = "WDW_OnSMConnected";
          v32[0] = "Failed init of decompression buffers";
          v34 = 706;
          v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
          LODWORD(v33) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v29,
            (unsigned int)byte_1802A4D01,
            v30,
            v31,
            (__int64)v32,
            (__int64)&v33,
            (__int64)&v36,
            (__int64)&v34,
            (__int64)&v35);
        }
        operator delete(*(void **)(a1 + 1296));
        *(_QWORD *)(a1 + 1296) = 0;
        *(_DWORD *)(a1 + 1304) = 0;
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v35 = "WDW_OnSMConnected";
      v32[0] = "Failed alloc of decompression buffers";
      v34 = 714;
      v36 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
      LODWORD(v33) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v26,
        (unsigned int)word_1802A4BE2,
        v27,
        v28,
        (__int64)v32,
        (__int64)&v33,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)&v35);
    }
  }
}

```

## disassembly

```asm
0x18017b774  push    rbp
0x18017b776  push    rbx
0x18017b777  push    rsi
0x18017b778  push    rdi
0x18017b779  push    r12
0x18017b77b  push    r14
0x18017b77d  push    r15
0x18017b77f  mov     rbp, rsp
0x18017b782  sub     rsp, 60h
0x18017b786  mov     eax, cs:CallbackContext
0x18017b78c  mov     edi, edx
0x18017b78e  mov     rbx, rcx
0x18017b791  cmp     eax, 4
0x18017b794  jbe     short loc_18017B7C2
0x18017b796  lea     rax, aGotConnectedNo; "Got Connected Notification, rc %lu"
0x18017b79d  mov     [rbp+arg_8], edx
0x18017b7a0  mov     [rbp+arg_0], rax
0x18017b7a4  lea     rdx, word_1802A4D46
0x18017b7ab  lea     rax, [rbp+arg_8]
0x18017b7af  mov     [rsp+60h+var_38], rax
0x18017b7b4  lea     rax, [rbp+arg_0]
0x18017b7b8  mov     [rsp+60h+var_40], rax
0x18017b7bd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017b7c2  mov     rcx, [rbx+50h]; hEvent
0x18017b7c6  mov     byte ptr [rbx+0A1h], 1
0x18017b7cd  call    cs:__imp_SetEvent
0x18017b7d3  lea     r14, aWdwOnsmconnect_0; "WDW_OnSMConnected"
0x18017b7da  mov     r12d, 80004005h
0x18017b7e0  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18017b7e7  cmp     edi, 1
0x18017b7ea  jz      loc_18017B930
0x18017b7f0  cmp     dword ptr [rbx+548h], 0
0x18017b7f7  jnz     loc_18017B9AF
0x18017b7fd  mov     rcx, [rbx+480h]
0x18017b804  test    rcx, rcx
0x18017b807  jz      loc_18017B9AF
0x18017b80d  mov     ecx, [rcx+4]
0x18017b810  test    cl, cl
0x18017b812  jns     loc_18017B9AF
0x18017b818  mov     eax, ecx
0x18017b81a  and     eax, 1E00h
0x18017b81f  cmp     eax, 200h
0x18017b824  jb      loc_18017B9AF
0x18017b82a  mov     edi, [rbx+544h]
0x18017b830  shr     ecx, 9
0x18017b833  and     ecx, 0Fh
0x18017b836  cmp     ecx, edi
0x18017b838  cmovbe  edi, ecx
0x18017b83b  mov     ecx, edi
0x18017b83d  call    cs:__imp_RDPCompress_GetContextSize
0x18017b843  mov     ecx, eax; Size
0x18017b845  mov     esi, eax
0x18017b847  call    WDLIBRT_MemAlloc
0x18017b84c  mov     [rbx+4E0h], rax
0x18017b853  test    rax, rax
0x18017b856  jz      short loc_18017B8C8
0x18017b858  mov     ecx, 3E70h; Size
0x18017b85d  call    WDLIBRT_MemAlloc
0x18017b862  mov     [rbx+4F0h], rax
0x18017b869  test    rax, rax
0x18017b86c  jz      short loc_18017B8A2
0x18017b86e  mov     rcx, [rbx+4E0h]
0x18017b875  mov     r8d, edi
0x18017b878  mov     edx, esi
0x18017b87a  mov     [rbx+4E8h], esi
0x18017b880  mov     dword ptr [rbx+4F8h], 3E70h
0x18017b88a  mov     [rbx+4DCh], edi
0x18017b890  call    cs:__imp_RDPCompress_InitSendContext
0x18017b896  mov     byte ptr [rbx+4D8h], 1
0x18017b89d  jmp     loc_18017B9AF
0x18017b8a2  mov     eax, cs:CallbackContext
0x18017b8a8  cmp     eax, 2
0x18017b8ab  jbe     loc_18017B9AF
0x18017b8b1  mov     [rbp+arg_8], 2A2h
0x18017b8b8  lea     rax, aFailedAllocati_0; "Failed allocation of compression buffer"
0x18017b8bf  lea     rdx, dword_1802A4DB4
0x18017b8c6  jmp     short loc_18017B8EC
0x18017b8c8  mov     eax, cs:CallbackContext
0x18017b8ce  cmp     eax, 2
0x18017b8d1  jbe     loc_18017B9AF
0x18017b8d7  mov     [rbp+arg_8], 2A6h
0x18017b8de  lea     rax, aFailedAllocati_3; "Failed allocation of compression contex"...
0x18017b8e5  lea     rdx, dword_1802A4CBC
0x18017b8ec  mov     [rbp+var_10], rax
0x18017b8f0  lea     rax, [rbp+arg_10]
0x18017b8f4  mov     [rsp+60h+var_20], rax
0x18017b8f9  lea     rax, [rbp+arg_8]
0x18017b8fd  mov     [rsp+60h+var_28], rax
0x18017b902  lea     rax, [rbp+arg_18]
0x18017b906  mov     [rsp+60h+var_30], rax
0x18017b90b  lea     rax, [rbp+arg_0]
0x18017b90f  mov     [rsp+60h+var_38], rax
0x18017b914  lea     rax, [rbp+var_10]
0x18017b918  mov     [rsp+60h+var_40], rax
0x18017b91d  mov     dword ptr [rbp+arg_0], r12d
0x18017b921  mov     [rbp+arg_18], r15
0x18017b925  mov     [rbp+arg_10], r14
0x18017b929  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18017b92e  jmp     short loc_18017B9AF
0x18017b930  mov     eax, cs:CallbackContext
0x18017b936  cmp     eax, 2
0x18017b939  jbe     short loc_18017B992
0x18017b93b  lea     rax, aConnectionErro; "Connection error: winding down now"
0x18017b942  mov     [rbp+arg_10], r14
0x18017b946  mov     [rbp+var_10], rax
0x18017b94a  lea     rdx, byte_1802A4C77
0x18017b951  lea     rax, [rbp+arg_10]
0x18017b955  mov     [rbp+arg_8], 2ACh
0x18017b95c  mov     [rsp+60h+var_20], rax
0x18017b961  lea     rax, [rbp+arg_8]
0x18017b965  mov     [rsp+60h+var_28], rax
0x18017b96a  lea     rax, [rbp+arg_18]
0x18017b96e  mov     [rsp+60h+var_30], rax
0x18017b973  lea     rax, [rbp+arg_0]
0x18017b977  mov     [rsp+60h+var_38], rax
0x18017b97c  lea     rax, [rbp+var_10]
0x18017b980  mov     [rsp+60h+var_40], rax
0x18017b985  mov     [rbp+arg_18], r15
0x18017b989  mov     dword ptr [rbp+arg_0], r12d
0x18017b98d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18017b992  xor     r9d, r9d
0x18017b995  mov     dword ptr [rsp+60h+var_40], 0
0x18017b99d  mov     r8d, 0D3h
0x18017b9a3  mov     rcx, rbx
0x18017b9a6  lea     edx, [r9+1]
0x18017b9aa  call    WDW_LogAndDisconnect
0x18017b9af  mov     rax, [rbx+480h]
0x18017b9b6  test    rax, rax
0x18017b9b9  jz      loc_18017BAF0
0x18017b9bf  test    byte ptr [rax+4], 80h
0x18017b9c3  jz      loc_18017BAF0
0x18017b9c9  xor     ecx, ecx
0x18017b9cb  call    cs:__imp_RDPDeCompress_GetContextSize
0x18017b9d1  mov     ecx, eax; Size
0x18017b9d3  mov     edi, eax
0x18017b9d5  call    WDLIBRT_MemAlloc
0x18017b9da  mov     [rbx+510h], rax
0x18017b9e1  test    rax, rax
0x18017b9e4  jz      loc_18017BA8E
0x18017b9ea  mov     r9b, 1
0x18017b9ed  mov     [rbx+518h], edi
0x18017b9f3  xor     r8d, r8d
0x18017b9f6  mov     edx, edi
0x18017b9f8  mov     rcx, rax
0x18017b9fb  call    cs:__imp_RDPCompress_InitRecvContext
0x18017ba01  test    eax, eax
0x18017ba03  jnz     loc_18017BAF0
0x18017ba09  mov     eax, cs:CallbackContext
0x18017ba0f  cmp     eax, 2
0x18017ba12  jbe     short loc_18017BA6B
0x18017ba14  lea     rax, aFailedInitOfDe; "Failed init of decompression buffers"
0x18017ba1b  mov     [rbp+arg_10], r14
0x18017ba1f  mov     [rbp+var_10], rax
0x18017ba23  lea     rdx, byte_1802A4D01
0x18017ba2a  lea     rax, [rbp+arg_10]
0x18017ba2e  mov     [rbp+arg_8], 2C2h
0x18017ba35  mov     [rsp+60h+var_20], rax
0x18017ba3a  lea     rax, [rbp+arg_8]
0x18017ba3e  mov     [rsp+60h+var_28], rax
0x18017ba43  lea     rax, [rbp+arg_18]
0x18017ba47  mov     [rsp+60h+var_30], rax
0x18017ba4c  lea     rax, [rbp+arg_0]
0x18017ba50  mov     [rsp+60h+var_38], rax
0x18017ba55  lea     rax, [rbp+var_10]
0x18017ba59  mov     [rsp+60h+var_40], rax
0x18017ba5e  mov     [rbp+arg_18], r15
0x18017ba62  mov     dword ptr [rbp+arg_0], r12d
0x18017ba66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18017ba6b  mov     rcx, [rbx+510h]; Block
0x18017ba72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017ba77  mov     qword ptr [rbx+510h], 0
0x18017ba82  mov     dword ptr [rbx+518h], 0
0x18017ba8c  jmp     short loc_18017BAF0
0x18017ba8e  mov     eax, cs:CallbackContext
0x18017ba94  cmp     eax, 2
0x18017ba97  jbe     short loc_18017BAF0
0x18017ba99  lea     rax, aFailedAllocOfD; "Failed alloc of decompression buffers"
0x18017baa0  mov     [rbp+arg_10], r14
0x18017baa4  mov     [rbp+var_10], rax
0x18017baa8  lea     rdx, word_1802A4BE2
0x18017baaf  lea     rax, [rbp+arg_10]
0x18017bab3  mov     [rbp+arg_8], 2CAh
0x18017baba  mov     [rsp+60h+var_20], rax
0x18017babf  lea     rax, [rbp+arg_8]
0x18017bac3  mov     [rsp+60h+var_28], rax
0x18017bac8  lea     rax, [rbp+arg_18]
0x18017bacc  mov     [rsp+60h+var_30], rax
0x18017bad1  lea     rax, [rbp+arg_0]
0x18017bad5  mov     [rsp+60h+var_38], rax
0x18017bada  lea     rax, [rbp+var_10]
0x18017bade  mov     [rsp+60h+var_40], rax
0x18017bae3  mov     [rbp+arg_18], r15
0x18017bae7  mov     dword ptr [rbp+arg_0], r12d
0x18017baeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18017baf0  add     rsp, 60h
0x18017baf4  pop     r15
0x18017baf6  pop     r14
0x18017baf8  pop     r12
0x18017bafa  pop     rdi
0x18017bafb  pop     rsi
0x18017bafc  pop     rbx
0x18017bafd  pop     rbp
0x18017bafe  retn
```

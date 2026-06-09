# WebSocketServer::SubscribeForDisconnect(ushort *,_GUID,unsigned __int64)

- ea: `0x180137838`
- end: `0x180137a5e`
- name: `?SubscribeForDisconnect@WebSocketServer@@AEAAJPEAGU_GUID@@_K@Z`
- size: `550`
- prototype: `int(WebSocketServer *__hidden this, unsigned __int16 *, struct _GUID *__struct_ptr, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180135984`

## callees

- `0x18000202c`
- `0x18003b118`
- `0x180076090`
- `0x180079724`
- `0x18007f42c`
- `0x18007f6b0`
- `0x180137838`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801378d9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137982`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801378d9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137982`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18013794b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18013794b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18013791a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18013791a`
- `HTTPAPI!HttpWaitForDisconnect` at `0x18013792d`
- `HTTPAPI!HttpWaitForDisconnect` at `0x18013792d`

## string_xrefs

- `0x1801378df`: `StringCchCopy failed`

## pseudocode

```c
__int64 __fastcall WebSocketServer::SubscribeForDisconnect(
        WebSocketServer *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        HTTP_CONNECTION_ID a4)
{
  char *v8; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  char *v12; // rdi
  __int64 v13; // rdx
  int v14; // ebx
  int v15; // eax
  ULONG v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // edi
  unsigned int ActivityIdPrefix; // eax
  int v21; // [rsp+50h] [rbp-9h] BYREF
  int v22; // [rsp+54h] [rbp-5h] BYREF
  const char *v23; // [rsp+58h] [rbp-1h] BYREF
  const char *v24; // [rsp+60h] [rbp+7h] BYREF
  const char *v25; // [rsp+68h] [rbp+Fh] BYREF
  const char *v26; // [rsp+70h] [rbp+17h] BYREF

  v8 = (char *)operator new(0x88u);
  v12 = v8;
  if ( v8 )
  {
    memset_0(v8 + 52, 0, 0x54u);
    *(_OWORD *)v12 = 0;
    *((_OWORD *)v12 + 1) = 0;
    *((_DWORD *)v12 + 8) = 6;
    *(struct _GUID *)(v12 + 36) = *a3;
    v14 = StringCchCopyW((unsigned __int16 *)v12 + 28, 0x28u, a2);
    if ( v14 >= 0 )
    {
      StartThreadpoolIo(*((PTP_IO *)this + 20));
      v16 = HttpWaitForDisconnect(*((HANDLE *)this + 19), a4, (LPOVERLAPPED)v12);
      v14 = v16;
      if ( !v16 || v16 == 997 )
      {
        return 0;
      }
      else
      {
        CancelThreadpoolIo(*((PTP_IO *)this + 20));
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( v14 > 0 )
            v18 = (unsigned __int16)v14 | 0x80070000;
          else
            v18 = v14;
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v17);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            &WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
            ActivityIdPrefix,
            v18);
        }
        if ( v14 > 0 )
          return (unsigned __int16)v14 | 0x80070000;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v13);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        v15,
        (__int64)"StringCchCopy failed",
        v14);
    }
  }
  else
  {
    v14 = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v21 = 2671;
      v23 = "Failed allocationg OVERLAPPED_INFO";
      v22 = -2147024882;
      v24 = "SubscribeForDisconnect";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v26 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)&word_180292E7E,
        v10,
        v11,
        (__int64)&v26,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&v21,
        (__int64)&v24,
        (__int64)&v23);
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180137838  push    rbp
0x18013783a  push    rbx
0x18013783b  push    rsi
0x18013783c  push    rdi
0x18013783d  push    r14
0x18013783f  push    r15
0x180137841  lea     rbp, [rsp-2Fh]
0x180137846  sub     rsp, 88h
0x18013784d  mov     rsi, rcx
0x180137850  mov     r14, r9
0x180137853  mov     ecx, 88h; Size
0x180137858  mov     rbx, r8
0x18013785b  mov     r15, rdx
0x18013785e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180137863  mov     rdi, rax
0x180137866  test    rax, rax
0x180137869  jz      loc_1801379C4
0x18013786f  xor     edx, edx; Val
0x180137871  lea     rcx, [rax+34h]; void *
0x180137875  lea     r8d, [rdx+54h]; Size
0x180137879  call    memset_0
0x18013787e  xorps   xmm0, xmm0
0x180137881  lea     rcx, [rdi+38h]; unsigned __int16 *
0x180137885  movups  xmmword ptr [rdi], xmm0
0x180137888  mov     r8, r15; unsigned __int16 *
0x18013788b  mov     edx, 28h ; '('; unsigned __int64
0x180137890  movups  xmmword ptr [rdi+10h], xmm0
0x180137894  mov     dword ptr [rdi+20h], 6
0x18013789b  movups  xmm0, xmmword ptr [rbx]
0x18013789e  movdqu  xmmword ptr [rdi+24h], xmm0
0x1801378a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801378a8  mov     ebx, eax
0x1801378aa  test    eax, eax
0x1801378ac  jns     short loc_180137913
0x1801378ae  mov     rax, cs:WPP_GLOBAL_Control
0x1801378b5  lea     rcx, WPP_GLOBAL_Control
0x1801378bc  cmp     rax, rcx
0x1801378bf  jz      loc_180137A4C
0x1801378c5  test    byte ptr [rax+1Ch], 8
0x1801378c9  jz      loc_180137A4C
0x1801378cf  cmp     byte ptr [rax+19h], 2
0x1801378d3  jb      loc_180137A4C
0x1801378d9  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801378df  lea     rcx, aStringcchcopyF_0; "StringCchCopy failed"
0x1801378e6  mov     dword ptr [rsp+0B0h+var_88], ebx
0x1801378ea  mov     [rsp+0B0h+var_90], rcx
0x1801378ef  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x1801378f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801378fd  mov     edx, 2Fh ; '/'
0x180137902  mov     r9d, eax
0x180137905  mov     rcx, [rcx+10h]
0x180137909  call    WPP_SF_DsD
0x18013790e  jmp     loc_180137A4C
0x180137913  mov     rcx, [rsi+0A0h]; pio
0x18013791a  call    cs:__imp_StartThreadpoolIo
0x180137920  mov     rcx, [rsi+98h]; RequestQueueHandle
0x180137927  mov     r8, rdi; Overlapped
0x18013792a  mov     rdx, r14; ConnectionId
0x18013792d  call    cs:__imp_HttpWaitForDisconnect
0x180137933  mov     ebx, eax
0x180137935  test    eax, eax
0x180137937  jz      loc_1801379BD
0x18013793d  cmp     eax, 3E5h
0x180137942  jz      short loc_1801379BD
0x180137944  mov     rcx, [rsi+0A0h]; pio
0x18013794b  call    cs:__imp_CancelThreadpoolIo
0x180137951  mov     rax, cs:WPP_GLOBAL_Control
0x180137958  lea     rcx, WPP_GLOBAL_Control
0x18013795f  mov     esi, 80070000h
0x180137964  cmp     rax, rcx
0x180137967  jz      short loc_1801379AB
0x180137969  test    byte ptr [rax+1Ch], 8
0x18013796d  jz      short loc_1801379AB
0x18013796f  cmp     byte ptr [rax+19h], 2
0x180137973  jb      short loc_1801379AB
0x180137975  test    ebx, ebx
0x180137977  jg      short loc_18013797D
0x180137979  mov     edi, ebx
0x18013797b  jmp     short loc_180137982
0x18013797d  movzx   edi, bx
0x180137980  or      edi, esi
0x180137982  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180137988  mov     rcx, cs:WPP_GLOBAL_Control
0x18013798f  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180137996  mov     edx, 30h ; '0'
0x18013799b  mov     dword ptr [rsp+0B0h+var_90], edi
0x18013799f  mov     r9d, eax
0x1801379a2  mov     rcx, [rcx+10h]
0x1801379a6  call    WPP_SF_Dd
0x1801379ab  test    ebx, ebx
0x1801379ad  jle     loc_180137A4C
0x1801379b3  movzx   ebx, bx
0x1801379b6  or      ebx, esi
0x1801379b8  jmp     loc_180137A4C
0x1801379bd  xor     ebx, ebx
0x1801379bf  jmp     loc_180137A4C
0x1801379c4  mov     eax, cs:CallbackContext
0x1801379ca  mov     ebx, 8007000Eh
0x1801379cf  cmp     eax, 2
0x1801379d2  jbe     short loc_180137A4C
0x1801379d4  lea     rax, aFailedAllocati_1; "Failed allocationg OVERLAPPED_INFO"
0x1801379db  mov     [rbp+57h+var_60], 0A6Fh
0x1801379e2  mov     [rbp+57h+var_58], rax
0x1801379e6  lea     rdx, word_180292E7E
0x1801379ed  lea     rax, aSubscribefordi_0; "SubscribeForDisconnect"
0x1801379f4  mov     [rbp+57h+var_5C], ebx
0x1801379f7  mov     [rbp+57h+var_50], rax
0x1801379fb  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180137a02  mov     [rbp+57h+var_48], rax
0x180137a06  lea     rax, aErrorCondition; "Error condition failed"
0x180137a0d  mov     [rbp+57h+var_40], rax
0x180137a11  lea     rax, [rbp+57h+var_58]
0x180137a15  mov     [rsp+0B0h+var_68], rax
0x180137a1a  lea     rax, [rbp+57h+var_50]
0x180137a1e  mov     [rsp+0B0h+var_70], rax
0x180137a23  lea     rax, [rbp+57h+var_60]
0x180137a27  mov     [rsp+0B0h+var_78], rax
0x180137a2c  lea     rax, [rbp+57h+var_48]
0x180137a30  mov     [rsp+0B0h+var_80], rax
0x180137a35  lea     rax, [rbp+57h+var_5C]
0x180137a39  mov     [rsp+0B0h+var_88], rax
0x180137a3e  lea     rax, [rbp+57h+var_40]
0x180137a42  mov     [rsp+0B0h+var_90], rax
0x180137a47  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180137a4c  mov     eax, ebx
0x180137a4e  add     rsp, 88h
0x180137a55  pop     r15
0x180137a57  pop     r14
0x180137a59  pop     rdi
0x180137a5a  pop     rsi
0x180137a5b  pop     rbx
0x180137a5c  pop     rbp
0x180137a5d  retn
```

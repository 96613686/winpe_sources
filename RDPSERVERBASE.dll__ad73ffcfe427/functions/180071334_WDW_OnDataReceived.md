# WDW_OnDataReceived

- ea: `0x180071334`
- end: `0x180071c43`
- name: `WDW_OnDataReceived`
- size: `2319`
- prototype: `__int64 __fastcall(__int64, _BYTE *, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180073e70`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180001f84`
- `0x180002170`
- `0x18000a378`
- `0x18000a730`
- `0x18000a928`
- `0x18004b520`
- `0x18004e93c`
- `0x180071334`
- `0x1800725d4`
- `0x18007a404`
- `0x18007a664`
- `0x18007e9e0`
- `0x18017adb0`
- `0x18019b31c`

## import_xrefs

- `RDPBASE!RDPCompress_InitRecvContext` at `0x1800714d9`
- `RDPBASE!RDPCompress_InitRecvContext` at `0x1800714d9`
- `RDPBASE!RDPDecompress` at `0x180071510`
- `RDPBASE!RDPDecompress` at `0x180071510`

## string_xrefs

- `0x18007146e`: `No decompression context!!!`
- `0x18007153d`: `Include VC protocol header (decompressed)`
- `0x180071797`: `Decompression failure, dropping link`
- `0x180071702`: `Decompressed when dead, bailing out`
- `0x1800716cb`: `Exclude VC protocol header (decompressed)`
- `0x1800718ec`: `Include VC protocol header`
- `0x180071920`: `Exclude VC protocol header`

## pseudocode

```c
__int64 __fastcall WDW_OnDataReceived(__int64 a1, _BYTE *a2, unsigned int a3, unsigned __int16 a4)
{
  unsigned __int64 v4; // rdi
  void *v7; // rcx
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // r12d
  struct tagNM_CHANNEL_DATA *v15; // r14
  int v16; // ecx
  int v17; // r13d
  char v18; // r14
  size_t v19; // rcx
  __int64 result; // rax
  __int64 *v21; // rdx
  const char *v22; // rax
  unsigned __int64 v23; // rcx
  _QWORD *v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned __int64 v27; // rcx
  _WORD *v28; // r14
  int v29; // ecx
  unsigned int v30; // r15d
  int v31; // eax
  int v32; // r12d
  char *v33; // r13
  unsigned int v34; // edi
  unsigned int v35; // ecx
  unsigned int v36; // eax
  int v37; // r14d
  int v38; // edx
  int v39; // r9d
  int v40; // r8d
  struct tagNM_CHANNEL_DATA *v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+6Ch] [rbp-94h] BYREF
  const char *v44; // [rsp+70h] [rbp-90h] BYREF
  const char *v45; // [rsp+78h] [rbp-88h] BYREF
  size_t Size; // [rsp+80h] [rbp-80h] BYREF
  const char *v47; // [rsp+88h] [rbp-78h] BYREF
  const char *v48; // [rsp+90h] [rbp-70h] BYREF
  const char *v49; // [rsp+98h] [rbp-68h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  int v51; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v52; // [rsp+B4h] [rbp-4Ch]
  _BYTE v53[1608]; // [rsp+B8h] [rbp-48h] BYREF

  v4 = a3;
  v41 = 0;
  Src = 0;
  v7 = *(void **)(a1 + 144);
  LODWORD(Size) = 0;
  v9 = NM_MCSChannelToVirtual(v7, a4, &v41);
  v43 = v9;
  v14 = v9;
  if ( v9 == -1 || (v15 = v41) == 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LOWORD(v44) = a4;
      v47 = "WDW_OnDataReceived";
      LODWORD(v41) = 850;
      v49 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
      v48 = "Invalid MCS Channel ID: %u";
      LODWORD(v45) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
        v11,
        (unsigned int)&byte_1802A4C27,
        v12,
        v13,
        (__int64)&v48,
        (__int64)&v45,
        (__int64)&v49,
        (__int64)&v41,
        (__int64)&v47,
        (__int64)&v44);
    }
    v40 = 239;
    return WDW_LogAndDisconnect(a1, 1, v40, (_DWORD)a2, v4);
  }
  v16 = (int)CallbackContext;
  if ( (unsigned int)CallbackContext > 5 )
  {
    v42 = v9;
    LOWORD(v44) = a4;
    v41 = (struct tagNM_CHANNEL_DATA *)"Data received on MCS channel %hx, virtual channel %d";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      (_DWORD)CallbackContext,
      (unsigned int)&word_1802A4B1E,
      v12,
      v13,
      (__int64)&v41,
      (__int64)&v44,
      (__int64)&v42);
  }
  if ( (unsigned int)v4 < 8 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v41) = v4;
      v47 = "WDW_OnDataReceived";
      LODWORD(v45) = 869;
      v49 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
      v48 = "Channel data len %u not enough for channel header";
      v42 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)byte_1802A4ACD,
        v12,
        v13,
        (__int64)&v48,
        (__int64)&v42,
        (__int64)&v49,
        (__int64)&v45,
        (__int64)&v47,
        (__int64)&v41);
    }
    v40 = 225;
    return WDW_LogAndDisconnect(a1, 1, v40, (_DWORD)a2, v4);
  }
  v17 = *(_DWORD *)a2;
  if ( (*((_DWORD *)v15 + 3) & 0x800000) != 0 && (v18 = a2[6], (v18 & 0x20) != 0) )
  {
    v19 = *(_QWORD *)(a1 + 1296);
    if ( !v19 )
    {
      result = (unsigned int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        return result;
      v42 = 889;
      v41 = (struct tagNM_CHANNEL_DATA *)"WDW_OnDataReceived";
      v21 = qword_1802A4B58;
      v45 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
      v22 = "No decompression context!!!";
      goto LABEL_11;
    }
    if ( (v18 & 0xF) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_db0912be5576377935263293d40a2408_Traceguids, v18 & 0xF);
      }
      return WDW_LogAndDisconnect(a1, 1, 237, 0, 0);
    }
    if ( v18 < 0 )
      RDPCompress_InitRecvContext(v19, *(unsigned int *)(a1 + 1304), 0, 0);
    if ( !(unsigned int)RDPDecompress(
                          a2 + 8,
                          (unsigned int)(v4 - 8),
                          v18 & 0x40,
                          &Src,
                          &Size,
                          *(_QWORD *)(a1 + 1296),
                          0,
                          0) )
    {
      v29 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_db0912be5576377935263293d40a2408_Traceguids);
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        v42 = 994;
        v41 = (struct tagNM_CHANNEL_DATA *)"WDW_OnDataReceived";
        v43 = -2147467259;
        v45 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
        v44 = "Decompression failure, dropping link";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v29,
          (unsigned int)byte_1802A4935,
          v12,
          v13,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v45,
          (__int64)&v42,
          (__int64)&v41);
      }
      return WDW_LogAndDisconnect(a1, 1, 236, 0, 0);
    }
    result = (unsigned int)CallbackContext;
    if ( *(_BYTE *)(a1 + 16) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v41 = (struct tagNM_CHANNEL_DATA *)"Decompressed when dead, bailing out";
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                 v23,
                 (unsigned int)&byte_1802A4A67,
                 v12,
                 v13,
                 (__int64)&v41);
      }
      return result;
    }
    if ( (a2[4] & 0x10) != 0 )
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v41 = (struct tagNM_CHANNEL_DATA *)"Include VC protocol header (decompressed)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v23,
          (unsigned int)&word_1802A4A46,
          v12,
          v13,
          (__int64)&v41);
      }
      v24 = *(_QWORD **)(a1 + 1312);
      if ( !v24 )
      {
        v25 = *(_DWORD *)(a1 + 1480);
        v19 = v25 + 8;
        if ( (unsigned int)v19 < v25 || (unsigned int)v19 < 8 )
        {
          result = (unsigned int)CallbackContext;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v42 = 939;
            v41 = (struct tagNM_CHANNEL_DATA *)"WDW_OnDataReceived";
            v21 = (__int64 *)byte_1802A4A01;
            v45 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
            v22 = "Overflow in buffer size calculation";
LABEL_11:
            v44 = v22;
            v43 = -2147467259;
            return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                     v19,
                     (_DWORD)v21,
                     v12,
                     v13,
                     (__int64)&v44,
                     (__int64)&v43,
                     (__int64)&v45,
                     (__int64)&v42,
                     (__int64)&v41);
          }
          return result;
        }
        v26 = WDLIBRT_MemAlloc(v19);
        *(_QWORD *)(a1 + 1312) = v26;
        v24 = (_QWORD *)v26;
        if ( !v26 )
          goto LABEL_30;
      }
      LODWORD(v27) = Size + 8;
      if ( (int)Size + 8 < (unsigned int)Size
        || (unsigned int)v27 < 8
        || (v27 = *(unsigned int *)(a1 + 1480) + 8LL, (unsigned __int64)(unsigned int)Size + 8 > v27) )
      {
LABEL_30:
        if ( (unsigned int)CallbackContext > 2 )
        {
          v42 = 973;
          v41 = (struct tagNM_CHANNEL_DATA *)"WDW_OnDataReceived";
          v43 = -2147467259;
          v45 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
          v44 = "Can't use reassembly buffer";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v27,
            (unsigned int)qword_1802A4A88,
            v12,
            v13,
            (__int64)&v44,
            (__int64)&v43,
            (__int64)&v45,
            (__int64)&v42,
            (__int64)&v41);
        }
        return WDW_LogAndDisconnect(a1, 1, 298, 0, 0);
      }
      *v24 = *(_QWORD *)a2;
      memcpy_0((void *)(*(_QWORD *)(a1 + 1312) + 8LL), Src, (unsigned int)Size);
      v28 = *(_WORD **)(a1 + 1312);
      LODWORD(v4) = Size + 8;
      v28[3] = 0;
    }
    else
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v41 = (struct tagNM_CHANNEL_DATA *)"Exclude VC protocol header (decompressed)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v23,
          (unsigned int)word_1802A497A,
          v12,
          v13,
          (__int64)&v41);
      }
      v28 = Src;
      LODWORD(v4) = Size;
    }
  }
  else
  {
    v23 = *(unsigned int *)(a1 + 1480) + 8LL;
    if ( v4 > v23 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v42 = 1019;
        v41 = (struct tagNM_CHANNEL_DATA *)"WDW_OnDataReceived";
        v43 = -2147467259;
        v45 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwapi.cpp";
        v44 = "VCData too long";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v23,
          (unsigned int)&dword_1802A49BC,
          v12,
          v13,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v45,
          (__int64)&v42,
          (__int64)&v41);
      }
      return WDW_LogAndDisconnect(a1, 1, 299, 0, 0);
    }
    if ( (a2[4] & 0x10) != 0 )
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v41 = (struct tagNM_CHANNEL_DATA *)"Include VC protocol header";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v23,
          (unsigned int)byte_1802A499B,
          v12,
          v13,
          (__int64)&v41);
      }
      v28 = a2;
      *((_WORD *)a2 + 3) = 0;
    }
    else
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v41 = (struct tagNM_CHANNEL_DATA *)"Exclude VC protocol header";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v23,
          (unsigned int)byte_1802A487D,
          v12,
          v13,
          (__int64)&v41);
      }
      LODWORD(v4) = v4 - 8;
      v28 = a2 + 8;
    }
  }
  result = (unsigned int)CallbackContext;
  if ( !*(_BYTE *)(a1 + 16) )
  {
    if ( (unsigned int)CallbackContext > 5 )
    {
      LODWORD(v44) = *((_DWORD *)a2 + 1);
      v47 = "Input %d bytes (of %d) at %p (Hdr %p, flags %#x) on channel %d";
      v42 = v14;
      v48 = a2;
      v49 = (const char *)v28;
      LODWORD(v45) = v17;
      LODWORD(v41) = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)qword_1802A4818,
        v12,
        v13,
        (__int64)&v47,
        (__int64)&v41,
        (__int64)&v45,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v44,
        (__int64)&v42);
    }
    v30 = v4 - 8;
    v31 = *((_DWORD *)a2 + 1) & 0x10;
    if ( !v31 )
      v30 = v4;
    if ( v30 <= 0x640 )
    {
      if ( v31 )
        v17 = 0;
    }
    else
    {
      v32 = 0;
      if ( v31 )
      {
        v33 = (char *)(v28 + 4);
        do
        {
          v34 = v30 - v32;
          v51 = *(_DWORD *)a2;
          if ( v30 - v32 > 0x640 )
            v34 = 1600;
          v35 = (unsigned __int16)*((_DWORD *)a2 + 1);
          v52 = v35;
          v36 = v35 & 0xFFFFFFFE;
          if ( v32 )
            v52 = v35 & 0xFFFFFFFE;
          v37 = v34 + v32;
          if ( !v32 )
            v36 = v35;
          if ( v37 != v30 )
            v52 = v36 & 0xFFFFFFFD;
          memcpy_0(v53, &v33[v32], v34);
          v32 += v34;
          result = WDICART_IcaChannelInputEx(*(_QWORD *)(a1 + 8), v38, v43, v39, (__int64)&v51, v34 + 8, 0);
        }
        while ( v37 != v30 );
        return result;
      }
      v14 = v43;
    }
    return WDICART_IcaChannelInputEx(*(_QWORD *)(a1 + 8), v10, v14, v13, (__int64)v28, v4, v17);
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v41) = v4;
    v47 = "Skipping input (%d bytes) because dead";
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
             v23,
             (unsigned int)qword_1802A4908,
             v12,
             v13,
             (__int64)&v47,
             (__int64)&v41);
  }
  return result;
}

```

## disassembly

```asm
0x180071334  push    rbp
0x180071336  push    rbx
0x180071337  push    rsi
0x180071338  push    rdi
0x180071339  push    r12
0x18007133b  push    r13
0x18007133d  push    r14
0x18007133f  push    r15
0x180071341  lea     rbp, [rsp-618h]
0x180071349  sub     rsp, 718h
0x180071350  mov     rax, cs:__security_cookie
0x180071357  xor     rax, rsp
0x18007135a  mov     [rbp+650h+var_50], rax
0x180071361  xor     r13d, r13d
0x180071364  mov     edi, r8d
0x180071367  mov     rsi, rdx
0x18007136a  mov     [rsp+750h+var_6F0], r13
0x18007136f  mov     rbx, rcx
0x180071372  mov     [rbp+650h+Src], r13
0x180071376  mov     rcx, [rcx+90h]; void *
0x18007137d  lea     r8, [rsp+750h+var_6F0]; struct tagNM_CHANNEL_DATA **
0x180071382  movzx   edx, r9w; unsigned __int16
0x180071386  mov     dword ptr [rbp+650h+Size], r13d
0x18007138a  movzx   r15d, r9w
0x18007138e  call    ?NM_MCSChannelToVirtual@@YAJPEAXGPEAPEAUtagNM_CHANNEL_DATA@@@Z; NM_MCSChannelToVirtual(void *,ushort,tagNM_CHANNEL_DATA * *)
0x180071393  mov     [rsp+750h+var_6E4], eax
0x180071397  mov     r12d, eax
0x18007139a  cmp     eax, 0FFFFFFFFh
0x18007139d  jz      loc_180071B7F
0x1800713a3  mov     r14, [rsp+750h+var_6F0]
0x1800713a8  test    r14, r14
0x1800713ab  jz      loc_180071B7F
0x1800713b1  mov     ecx, cs:CallbackContext
0x1800713b7  cmp     ecx, 5
0x1800713ba  jbe     short loc_1800713FC
0x1800713bc  mov     [rsp+750h+var_6E8], eax
0x1800713c0  lea     rdx, word_1802A4B1E
0x1800713c7  lea     rax, aDataReceivedOn; "Data received on MCS channel %hx, virtu"...
0x1800713ce  mov     word ptr [rsp+750h+var_6E0], r15w
0x1800713d4  mov     [rsp+750h+var_6F0], rax
0x1800713d9  lea     rax, [rsp+750h+var_6E8]
0x1800713de  mov     [rsp+750h+var_720], rax
0x1800713e3  lea     rax, [rsp+750h+var_6E0]
0x1800713e8  mov     [rsp+750h+var_728], rax
0x1800713ed  lea     rax, [rsp+750h+var_6F0]
0x1800713f2  mov     [rsp+750h+var_730], rax
0x1800713f7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800713fc  cmp     edi, 8
0x1800713ff  jb      loc_180071AEF
0x180071405  test    dword ptr [r14+0Ch], 800000h
0x18007140d  mov     r13d, [rsi]
0x180071410  jz      loc_18007183B
0x180071416  movzx   r14d, byte ptr [rsi+6]
0x18007141b  test    r14b, 20h
0x18007141f  jz      loc_18007183B
0x180071425  mov     rcx, [rbx+510h]
0x18007142c  xor     r15d, r15d
0x18007142f  test    rcx, rcx
0x180071432  jnz     loc_1800714BE
0x180071438  mov     eax, cs:CallbackContext
0x18007143e  cmp     eax, 2
0x180071441  jbe     loc_180071C20
0x180071447  lea     rax, aWdwOndatarecei; "WDW_OnDataReceived"
0x18007144e  mov     [rsp+750h+var_6E8], 379h
0x180071456  mov     [rsp+750h+var_6F0], rax
0x18007145b  lea     rdx, qword_1802A4B58
0x180071462  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071469  mov     [rsp+750h+var_6D8], rax
0x18007146e  lea     rax, aNoDecompressio; "No decompression context!!!"
0x180071475  mov     [rsp+750h+var_6E0], rax
0x18007147a  lea     rax, [rsp+750h+var_6F0]
0x18007147f  mov     [rsp+750h+var_710], rax
0x180071484  lea     rax, [rsp+750h+var_6E8]
0x180071489  mov     [rsp+750h+var_718], rax
0x18007148e  lea     rax, [rsp+750h+var_6D8]
0x180071493  mov     [rsp+750h+var_720], rax
0x180071498  lea     rax, [rsp+750h+var_6E4]
0x18007149d  mov     [rsp+750h+var_728], rax
0x1800714a2  lea     rax, [rsp+750h+var_6E0]
0x1800714a7  mov     [rsp+750h+var_730], rax
0x1800714ac  mov     [rsp+750h+var_6E4], 80004005h
0x1800714b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800714b9  jmp     loc_180071C20
0x1800714be  test    r14b, 0Fh
0x1800714c2  jnz     loc_1800717ED
0x1800714c8  test    r14b, r14b
0x1800714cb  jns     short loc_1800714DF
0x1800714cd  mov     edx, [rbx+518h]
0x1800714d3  xor     r9d, r9d
0x1800714d6  xor     r8d, r8d
0x1800714d9  call    cs:__imp_RDPCompress_InitRecvContext
0x1800714df  mov     rax, [rbx+510h]
0x1800714e6  lea     edx, [rdi-8]
0x1800714e9  mov     dword ptr [rsp+750h+var_718], r15d
0x1800714ee  lea     rcx, [rsi+8]
0x1800714f2  mov     dword ptr [rsp+750h+var_720], r15d
0x1800714f7  lea     r9, [rbp+650h+Src]
0x1800714fb  mov     [rsp+750h+var_728], rax
0x180071500  mov     r8d, r14d
0x180071503  lea     rax, [rbp+650h+Size]
0x180071507  and     r8d, 40h
0x18007150b  mov     [rsp+750h+var_730], rax
0x180071510  call    cs:__imp_RDPDecompress
0x180071516  test    eax, eax
0x180071518  jz      loc_180071729
0x18007151e  mov     eax, cs:CallbackContext
0x180071524  cmp     [rbx+10h], r15b
0x180071528  jnz     loc_1800716F9
0x18007152e  test    byte ptr [rsi+4], 10h
0x180071532  jz      loc_1800716C6
0x180071538  cmp     eax, 5
0x18007153b  jbe     short loc_18007155F
0x18007153d  lea     rax, aIncludeVcProto; "Include VC protocol header (decompresse"...
0x180071544  mov     [rsp+750h+var_6F0], rax
0x180071549  lea     rdx, word_1802A4A46
0x180071550  lea     rax, [rsp+750h+var_6F0]
0x180071555  mov     [rsp+750h+var_730], rax
0x18007155a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007155f  mov     rdx, [rbx+520h]
0x180071566  test    rdx, rdx
0x180071569  jnz     short loc_180071595
0x18007156b  mov     eax, [rbx+5C8h]
0x180071571  lea     ecx, [rax+8]; Size
0x180071574  cmp     ecx, eax
0x180071576  jb      short loc_1800715F4
0x180071578  cmp     ecx, 8
0x18007157b  jb      short loc_1800715F4
0x18007157d  call    WDLIBRT_MemAlloc
0x180071582  mov     [rbx+520h], rax
0x180071589  mov     rdx, rax
0x18007158c  test    rax, rax
0x18007158f  jz      loc_180071636
0x180071595  mov     eax, dword ptr [rbp+650h+Size]
0x180071598  lea     ecx, [rax+8]
0x18007159b  cmp     ecx, eax
0x18007159d  jb      loc_180071636
0x1800715a3  cmp     ecx, 8
0x1800715a6  jb      loc_180071636
0x1800715ac  mov     ecx, [rbx+5C8h]
0x1800715b2  add     rax, 8
0x1800715b6  add     rcx, 8
0x1800715ba  cmp     rax, rcx
0x1800715bd  ja      short loc_180071636
0x1800715bf  mov     rax, [rsi]
0x1800715c2  mov     [rdx], rax
0x1800715c5  mov     rcx, [rbx+520h]
0x1800715cc  mov     r8d, dword ptr [rbp+650h+Size]; Size
0x1800715d0  add     rcx, 8; void *
0x1800715d4  mov     rdx, [rbp+650h+Src]; Src
0x1800715d8  call    memcpy_0
0x1800715dd  mov     edi, dword ptr [rbp+650h+Size]
0x1800715e0  mov     r14, [rbx+520h]
0x1800715e7  add     edi, 8
0x1800715ea  mov     [r14+6], r15w
0x1800715ef  jmp     loc_18007194C
0x1800715f4  mov     eax, cs:CallbackContext
0x1800715fa  cmp     eax, 2
0x1800715fd  jbe     loc_180071C20
0x180071603  lea     rax, aWdwOndatarecei; "WDW_OnDataReceived"
0x18007160a  mov     [rsp+750h+var_6E8], 3ABh
0x180071612  mov     [rsp+750h+var_6F0], rax
0x180071617  lea     rdx, byte_1802A4A01
0x18007161e  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071625  mov     [rsp+750h+var_6D8], rax
0x18007162a  lea     rax, aOverflowInBuff; "Overflow in buffer size calculation"
0x180071631  jmp     loc_180071475
0x180071636  mov     eax, cs:CallbackContext
0x18007163c  cmp     eax, 2
0x18007163f  jbe     short loc_1800716B3
0x180071641  lea     rax, aWdwOndatarecei; "WDW_OnDataReceived"
0x180071648  mov     [rsp+750h+var_6E8], 3CDh
0x180071650  mov     [rsp+750h+var_6F0], rax
0x180071655  lea     rdx, qword_1802A4A88
0x18007165c  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180071663  mov     [rsp+750h+var_6E4], 80004005h
0x18007166b  mov     [rsp+750h+var_6D8], rax
0x180071670  lea     rax, aCanTUseReassem; "Can't use reassembly buffer"
0x180071677  mov     [rsp+750h+var_6E0], rax
0x18007167c  lea     rax, [rsp+750h+var_6F0]
0x180071681  mov     [rsp+750h+var_710], rax
0x180071686  lea     rax, [rsp+750h+var_6E8]
0x18007168b  mov     [rsp+750h+var_718], rax
0x180071690  lea     rax, [rsp+750h+var_6D8]
0x180071695  mov     [rsp+750h+var_720], rax
0x18007169a  lea     rax, [rsp+750h+var_6E4]
0x18007169f  mov     [rsp+750h+var_728], rax
0x1800716a4  lea     rax, [rsp+750h+var_6E0]
0x1800716a9  mov     [rsp+750h+var_730], rax
0x1800716ae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800716b3  mov     dword ptr [rsp+750h+var_730], r15d
0x1800716b8  xor     r9d, r9d
0x1800716bb  mov     r8d, 12Ah
0x1800716c1  jmp     loc_180071C13
0x1800716c6  cmp     eax, 5
0x1800716c9  jbe     short loc_1800716ED
0x1800716cb  lea     rax, aExcludeVcProto_0; "Exclude VC protocol header (decompresse"...
0x1800716d2  mov     [rsp+750h+var_6F0], rax
0x1800716d7  lea     rdx, word_1802A497A
0x1800716de  lea     rax, [rsp+750h+var_6F0]
0x1800716e3  mov     [rsp+750h+var_730], rax
0x1800716e8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800716ed  mov     r14, [rbp+650h+Src]
0x1800716f1  mov     edi, dword ptr [rbp+650h+Size]
0x1800716f4  jmp     loc_18007194C
0x1800716f9  cmp     eax, 4
0x1800716fc  jbe     loc_180071C20
0x180071702  lea     rax, aDecompressedWh; "Decompressed when dead, bailing out"
0x180071709  mov     [rsp+750h+var_6F0], rax
0x18007170e  lea     rdx, byte_1802A4A67
0x180071715  lea     rax, [rsp+750h+var_6F0]
0x18007171a  mov     [rsp+750h+var_730], rax
0x18007171f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180071724  jmp     loc_180071C20
0x180071729  mov     rcx, cs:WPP_GLOBAL_Control
0x180071730  lea     rax, WPP_GLOBAL_Control
0x180071737  cmp     rcx, rax
0x18007173a  jz      short loc_18007175D
0x18007173c  test    byte ptr [rcx+1Ch], 1
0x180071740  jz      short loc_18007175D
0x180071742  cmp     byte ptr [rcx+19h], 1
0x180071746  jb      short loc_18007175D
0x180071748  mov     rcx, [rcx+10h]
0x18007174c  lea     r8, WPP_db0912be5576377935263293d40a2408_Traceguids
0x180071753  mov     edx, 0Ch
0x180071758  call    WPP_SF_
0x18007175d  mov     eax, cs:CallbackContext
0x180071763  cmp     eax, 2
0x180071766  jbe     short loc_1800717DA
0x180071768  lea     rax, aWdwOndatarecei; "WDW_OnDataReceived"
0x18007176f  mov     [rsp+750h+var_6E8], 3E2h
0x180071777  mov     [rsp+750h+var_6F0], rax
0x18007177c  lea     rdx, byte_1802A4935
0x180071783  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18007178a  mov     [rsp+750h+var_6E4], 80004005h
0x180071792  mov     [rsp+750h+var_6D8], rax
0x180071797  lea     rax, aDecompressionF; "Decompression failure, dropping link"
0x18007179e  mov     [rsp+750h+var_6E0], rax
0x1800717a3  lea     rax, [rsp+750h+var_6F0]
0x1800717a8  mov     [rsp+750h+var_710], rax
0x1800717ad  lea     rax, [rsp+750h+var_6E8]
0x1800717b2  mov     [rsp+750h+var_718], rax
0x1800717b7  lea     rax, [rsp+750h+var_6D8]
0x1800717bc  mov     [rsp+750h+var_720], rax
0x1800717c1  lea     rax, [rsp+750h+var_6E4]
0x1800717c6  mov     [rsp+750h+var_728], rax
0x1800717cb  lea     rax, [rsp+750h+var_6E0]
0x1800717d0  mov     [rsp+750h+var_730], rax
0x1800717d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800717da  mov     dword ptr [rsp+750h+var_730], r15d
0x1800717df  xor     r9d, r9d
0x1800717e2  mov     r8d, 0ECh
0x1800717e8  jmp     loc_180071C13
0x1800717ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800717f4  lea     rax, WPP_GLOBAL_Control
0x1800717fb  cmp     rcx, rax
0x1800717fe  jz      short loc_180071828
0x180071800  test    byte ptr [rcx+1Ch], 1
0x180071804  jz      short loc_180071828
0x180071806  cmp     byte ptr [rcx+19h], 1
0x18007180a  jb      short loc_180071828
0x18007180c  mov     rcx, [rcx+10h]
0x180071810  lea     r8, WPP_db0912be5576377935263293d40a2408_Traceguids
0x180071817  mov     r9d, r14d
0x18007181a  mov     edx, 0Dh
0x18007181f  and     r9d, 0Fh
0x180071823  call    WPP_SF_d
0x180071828  mov     dword ptr [rsp+750h+var_730], r15d
0x18007182d  xor     r9d, r9d
0x180071830  mov     r8d, 0EDh
0x180071836  jmp     loc_180071C13
0x18007183b  mov     ecx, [rbx+5C8h]
0x180071841  mov     eax, cs:CallbackContext
0x180071847  add     rcx, 8
0x18007184b  cmp     rdi, rcx
0x18007184e  jbe     loc_1800718E1
0x180071854  cmp     eax, 2
0x180071857  jbe     short loc_1800718CB
0x180071859  lea     rax, aWdwOndatarecei; "WDW_OnDataReceived"
0x180071860  mov     [rsp+750h+var_6E8], 3FBh
0x180071868  mov     [rsp+750h+var_6F0], rax
0x18007186d  lea     rdx, dword_1802A49BC
0x180071874  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18007187b  mov     [rsp+750h+var_6E4], 80004005h
0x180071883  mov     [rsp+750h+var_6D8], rax
0x180071888  lea     rax, aVcdataTooLong; "VCData too long"
0x18007188f  mov     [rsp+750h+var_6E0], rax
0x180071894  lea     rax, [rsp+750h+var_6F0]
0x180071899  mov     [rsp+750h+var_710], rax
0x18007189e  lea     rax, [rsp+750h+var_6E8]
0x1800718a3  mov     [rsp+750h+var_718], rax
0x1800718a8  lea     rax, [rsp+750h+var_6D8]
0x1800718ad  mov     [rsp+750h+var_720], rax
0x1800718b2  lea     rax, [rsp+750h+var_6E4]
0x1800718b7  mov     [rsp+750h+var_728], rax
0x1800718bc  lea     rax, [rsp+750h+var_6E0]
0x1800718c1  mov     [rsp+750h+var_730], rax
0x1800718c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800718cb  mov     dword ptr [rsp+750h+var_730], 0
0x1800718d3  xor     r9d, r9d
0x1800718d6  mov     r8d, 12Bh
  ... truncated ...
```

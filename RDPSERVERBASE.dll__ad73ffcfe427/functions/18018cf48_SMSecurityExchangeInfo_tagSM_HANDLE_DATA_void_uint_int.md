# SMSecurityExchangeInfo(tagSM_HANDLE_DATA *,void *,uint,int)

- ea: `0x18018cf48`
- end: `0x18018f120`
- name: `?SMSecurityExchangeInfo@@YAEPEAUtagSM_HANDLE_DATA@@PEAXIH@Z`
- size: `8664`
- prototype: `unsigned __int8 __fastcall(struct tagSM_HANDLE_DATA *, void *, unsigned int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180180890`
- `0x18018c7a8`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180001574`
- `0x180001f84`
- `0x180002170`
- `0x180002c94`
- `0x180004924`
- `0x1800067c8`
- `0x18004e93c`
- `0x18007f42c`
- `0x18017aee4`
- `0x18017b018`
- `0x18017b774`
- `0x18018c930`
- `0x18018cf48`
- `0x18019b31c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d81d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d81d`
- `CRYPT32!CryptProtectMemory` at `0x18018d801`
- `CRYPT32!CryptProtectMemory` at `0x18018d801`

## string_xrefs

- `0x18018d07b`: `Unencrypted data in encrypted protocol`
- `0x18018cff6`: `SMSecurityExchangeInfo`
- `0x18018d090`: `SMSecurityExchangeInfo`
- `0x18018d15f`: `SMSecurityExchangeInfo`
- `0x18018d21c`: `SMSecurityExchangeInfo`
- `0x18018d3d5`: `SMSecurityExchangeInfo`
- `0x18018d6cc`: `SMSecurityExchangeInfo`
- `0x18018d757`: `SMSecurityExchangeInfo`
- `0x18018ecb7`: `SMSecurityExchangeInfo`
- `0x18018ed56`: `SMSecurityExchangeInfo`
- `0x18018edf5`: `SMSecurityExchangeInfo`
- `0x18018ee94`: `SMSecurityExchangeInfo`
- `0x18018ef33`: `SMSecurityExchangeInfo`
- `0x18018efd2`: `SMSecurityExchangeInfo`
- `0x18018f071`: `SMSecurityExchangeInfo`
- `0x18018d20a`: `Data length too small to contain RNS_SECURITY_HEADER1: %ld`
- `0x18018ddec`: `Client directory: %s`

## pseudocode

```c
char __fastcall SMSecurityExchangeInfo(struct tagSM_HANDLE_DATA *a1, char *a2, unsigned int a3, int a4)
{
  char v4; // bl
  unsigned __int64 v5; // rdi
  _DWORD *v6; // r14
  struct tagSM_HANDLE_DATA *v7; // rsi
  int v8; // r8d
  int v9; // r8d
  char *v10; // rcx
  __int64 v11; // rax
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  void *v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // r12d
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rcx
  unsigned int v32; // r12d
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rcx
  unsigned int v36; // eax
  int v37; // r9d
  __int64 v38; // rcx
  const void *v39; // rdx
  size_t v40; // r8
  DWORD LastError; // eax
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rdx
  _BYTE *v46; // rcx
  __int64 v47; // rcx
  char *v48; // rdx
  _BYTE *v49; // rax
  unsigned int v50; // ebx
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rcx
  unsigned int v54; // ebx
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // r8
  int v57; // r9d
  __int64 v58; // rcx
  char *v59; // rbx
  unsigned int v60; // eax
  int v61; // ecx
  unsigned __int16 *v62; // rbx
  _OWORD *v63; // rcx
  unsigned int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  int v67; // ecx
  _OWORD *v68; // rax
  int v69; // eax
  unsigned __int16 *v70; // rbx
  int v71; // r9d
  _OWORD *v72; // rax
  int v73; // r8d
  int v74; // r8d
  __int64 v75; // rdx
  __int128 v76; // xmm1
  _OWORD *v77; // rax
  __int128 v78; // xmm0
  int v79; // eax
  __int64 v80; // rcx
  int v81; // eax
  __int64 v82; // rcx
  unsigned int v83; // ecx
  unsigned int v84; // ebx
  __int64 v85; // rdx
  __int64 v86; // rbx
  unsigned int v87; // ecx
  int v88; // eax
  unsigned int v89; // ecx
  _OWORD *v90; // rbx
  unsigned int v91; // ecx
  _OWORD *v92; // rax
  int v93; // ecx
  int v94; // r8d
  int v95; // r9d
  char *v96; // rbx
  char *v97; // rbx
  char *v98; // rbx
  char *v99; // rbx
  char *v100; // rbx
  unsigned int v101; // r15d
  int v102; // ecx
  int v103; // ecx
  __int64 v104; // r13
  unsigned int v105; // r15d
  unsigned __int16 *v106; // rbx
  int v107; // ecx
  __int64 v108; // r13
  unsigned int v109; // r15d
  unsigned __int16 *v110; // rbx
  unsigned int v111; // r15d
  _OWORD *v112; // rax
  __int64 v113; // rcx
  void *Src; // [rsp+60h] [rbp-A0h] BYREF
  const char *v116; // [rsp+68h] [rbp-98h] BYREF
  const char *v117; // [rsp+70h] [rbp-90h] BYREF
  const char *v118; // [rsp+78h] [rbp-88h] BYREF
  const char *v119; // [rsp+80h] [rbp-80h] BYREF
  void *v120[31]; // [rsp+88h] [rbp-78h] BYREF
  size_t Size; // [rsp+1A8h] [rbp+A8h] BYREF

  v4 = 0;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  if ( a4 )
  {
    if ( *((_BYTE *)a1 + 39) )
    {
      if ( (*a2 & 8) != 0 )
      {
        if ( (unsigned int)CallbackContext > 5 )
        {
          Src = "Decrypt the packet";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (_DWORD)a1,
            (unsigned int)byte_1802AD6A1,
            4,
            a4,
            (__int64)&Src);
        }
        if ( !(unsigned int)SMDecryptPacket(v7, v6, v5, 0) )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = 327;
            v118 = "Failed to decrypt packet";
            Src = "SMSecurityExchangeInfo";
            v119 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v120[0]) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (_DWORD)a1,
              (unsigned int)byte_1802AD501,
              v8,
              a4,
              (__int64)&v118,
              (__int64)v120,
              (__int64)&v119,
              (__int64)&Size,
              (__int64)&Src);
          }
          v9 = 402;
LABEL_208:
          WDW_LogStateTransitionAndDisconnect(*((_QWORD *)v7 + 9), (_DWORD)a2, v9, (_DWORD)v6, v5, 7, 34);
          return v4;
        }
      }
      else if ( *(_DWORD *)(*((_QWORD *)a1 + 9) + 1332LL) )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(Size) = 343;
          v119 = "Unencrypted data in encrypted protocol";
          v118 = "SMSecurityExchangeInfo";
          Src = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
          LODWORD(v120[0]) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)a1,
            (unsigned int)&dword_1802AD4BC,
            4,
            a4,
            (__int64)&v119,
            (__int64)v120,
            (__int64)&Src,
            (__int64)&Size,
            (__int64)&v118);
        }
        WDW_LogStateTransitionAndDisconnect(*((_QWORD *)v7 + 9), (_DWORD)a2, 405, 0, 0, 7, 34);
        return v4;
      }
      if ( *((_DWORD *)v7 + 3) == 16 )
      {
        a2 = (char *)*((unsigned __int8 *)v6 + 7);
        v10 = a2 + 16;
        if ( (unsigned __int64)(a2 + 16) < 0x10 || v10 < a2 || v5 < (unsigned __int64)v10 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = *((unsigned __int8 *)v6 + 7);
            v118 = "SMSecurityExchangeInfo";
            v117 = "padlen %ld is too large";
            LODWORD(v120[0]) = 368;
            Src = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)v10,
              (unsigned int)&byte_1802AD597,
              4,
              a4,
              (__int64)&v117,
              (__int64)&v119,
              (__int64)&Src,
              (__int64)v120,
              (__int64)&v118,
              (__int64)&Size);
          }
          return v4;
        }
        v11 = 16;
        LODWORD(a1) = -16 - (_DWORD)a2;
        LODWORD(v5) = -16 - (_DWORD)a2 + v5;
      }
      else
      {
        v11 = 12;
        if ( (unsigned int)v5 < 0xC )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v5;
            Src = "Data length too small to contain RNS_SECURITY_HEADER1: %ld";
            v117 = "SMSecurityExchangeInfo";
            LODWORD(v119) = 383;
            v118 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v120[0]) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)a1,
              (unsigned int)&word_1802AD546,
              4,
              a4,
              (__int64)&Src,
              (__int64)v120,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Size);
          }
          return v4;
        }
        LODWORD(v5) = v5 - 12;
      }
      v6 = (_DWORD *)((char *)v6 + v11);
    }
    else
    {
      v6 = a2 + 4;
      LODWORD(v5) = a3 - 4;
    }
  }
  *(_OWORD *)((char *)&v120[20] + 4) = 0x60000u;
  memset(&v120[1], 0, 68);
  v12 = (_OWORD *)*((_QWORD *)v7 + 9);
  HIDWORD(v120[9]) = 655360;
  v120[10] = (void *)393216;
  memset(&v120[11], 0, 72);
  LODWORD(v120[20]) = 0x40000;
  v13 = *(_OWORD *)&v120[3];
  v12[52] = *(_OWORD *)&v120[1];
  v14 = *(_OWORD *)&v120[5];
  v12[53] = v13;
  v15 = *(_OWORD *)&v120[7];
  v12[54] = v14;
  v16 = *(_OWORD *)&v120[9];
  v12[55] = v15;
  v17 = *(_OWORD *)&v120[11];
  v12[56] = v16;
  v18 = *(_OWORD *)&v120[13];
  v12[57] = v17;
  v19 = *(_OWORD *)&v120[15];
  v12[58] = v18;
  v20 = *(_OWORD *)&v120[17];
  v12[59] = v19;
  v21 = *(_OWORD *)&v120[19];
  v12[60] = v20;
  v22 = *(_OWORD *)((char *)&v120[20] + 4);
  v12[61] = v21;
  *(_OWORD *)((char *)v12 + 988) = v22;
  *(_DWORD *)(*((_QWORD *)v7 + 9) + 1004LL) = -2;
  if ( (unsigned int)v5 < 0x12 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(Size) = v5;
      v118 = "Packet len %u too short for info packet header";
      v116 = "SMSecurityExchangeInfo";
      LODWORD(Src) = 456;
      v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
      LODWORD(v119) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)a1,
        (unsigned int)&byte_1802AD397,
        4,
        a4,
        (__int64)&v118,
        (__int64)&v119,
        (__int64)&v117,
        (__int64)&Src,
        (__int64)&v116,
        (__int64)&Size);
    }
    v9 = 277;
    goto LABEL_208;
  }
  v23 = (v6[1] & 0x10) != 0 ? 5 : 0;
  LODWORD(a2) = *((unsigned __int16 *)v6 + 6)
              + *((unsigned __int16 *)v6 + 5)
              + *((unsigned __int16 *)v6 + 4)
              + *((unsigned __int16 *)v6 + 7)
              + *((unsigned __int16 *)v6 + 8)
              + v23
              + 23;
  if ( (unsigned int)v5 < (unsigned int)a2 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(Size) = *((unsigned __int16 *)v6 + 6)
                    + *((unsigned __int16 *)v6 + 5)
                    + *((unsigned __int16 *)v6 + 4)
                    + *((unsigned __int16 *)v6 + 7)
                    + *((unsigned __int16 *)v6 + 8)
                    + v23
                    + 23;
      v116 = "Packet len %u too short for info packet data %u";
      LODWORD(v119) = v5;
      v117 = "SMSecurityExchangeInfo";
      LODWORD(v120[0]) = 444;
      v118 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
      LODWORD(Src) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)qword_1802AD3E8,
        4,
        a4,
        (__int64)&v116,
        (__int64)&Src,
        (__int64)&v118,
        (__int64)v120,
        (__int64)&v117,
        (__int64)&v119,
        (__int64)&Size);
    }
    v9 = 276;
    goto LABEL_208;
  }
  if ( *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) )
    goto LABEL_37;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v116 = (const char *)3756;
    v117 = "Alloc %u bytes for InfoPkt";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v23,
      (unsigned int)word_1802AD482,
      4,
      a4,
      (__int64)&v117,
      (__int64)&v116);
  }
  *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) = WDLIBRT_MemAlloc(0xEACu);
  v26 = *(void **)(*((_QWORD *)v7 + 9) + 1152LL);
  if ( v26 )
  {
    memset_0(v26, 0, 0xEACu);
LABEL_37:
    v27 = *((_QWORD *)v7 + 9);
    if ( (v6[1] & 0x10) == 0 )
    {
      *(_DWORD *)(v27 + 1076) = 0;
      memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 18LL), 0, 0x200u);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 8LL) = 0;
      v96 = (char *)v6 + *((unsigned __int16 *)v6 + 4);
      memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 530LL), 0, 0x200u);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 10LL) = 0;
      v97 = &v96[*((unsigned __int16 *)v6 + 5)];
      memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1042LL), 0, 0x200u);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 12LL) = 0;
      v98 = &v97[*((unsigned __int16 *)v6 + 6)];
      memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1554LL), 0, 0x200u);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 14LL) = 0;
      v99 = &v98[*((unsigned __int16 *)v6 + 7)];
      memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 2066LL), 0, 0x200u);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 16LL) = 0;
      v100 = &v99[*((unsigned __int16 *)v6 + 8)];
      v101 = (_DWORD)v100 + 23 - (_DWORD)v6;
      if ( v101 < (unsigned int)v5 )
      {
        if ( (int)v101 + 4LL >= (unsigned __int64)(unsigned int)v5 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v5;
            v118 = "Packet len %u too short for extra info packet data";
            v116 = "SMSecurityExchangeInfo";
            LODWORD(Src) = 1099;
            v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v5,
              (unsigned int)&byte_1802ACBA7,
              v56,
              v57,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Src,
              (__int64)&v116,
              (__int64)&Size);
          }
          v74 = 288;
          goto LABEL_89;
        }
        v102 = *(unsigned __int16 *)(v100 + 23);
        *(_DWORD *)(*((_QWORD *)v7 + 9) + 236LL) = v102;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v103 = *(_DWORD *)(*((_QWORD *)v7 + 9) + 236LL);
          v116 = "Client address family=%d";
          LODWORD(Size) = v103;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v103,
            (unsigned int)qword_1802ACBF8,
            v56,
            v57,
            (__int64)&v116,
            (__int64)&Size);
        }
        v104 = *(unsigned __int16 *)(v100 + 25);
        v105 = v101 + 4;
        v106 = (unsigned __int16 *)(v100 + 27);
        LODWORD(v55) = 0;
        if ( (_WORD)v104 )
        {
          v105 += v104;
          if ( v105 >= (unsigned int)v5 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(Size) = v5;
              v118 = "Packet len %u too short for extra info packet data";
              v116 = "SMSecurityExchangeInfo";
              LODWORD(Src) = 1120;
              v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
              LODWORD(v119) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v102,
                (unsigned int)word_1802ACA12,
                v56,
                v57,
                (__int64)&v118,
                (__int64)&v119,
                (__int64)&v117,
                (__int64)&Src,
                (__int64)&v116,
                (__int64)&Size);
            }
            v74 = 289;
            goto LABEL_89;
          }
          memset_0((void *)(*((_QWORD *)v7 + 9) + 240LL), 0, 0x50u);
          v106 = (unsigned __int16 *)((char *)v106 + v104);
        }
        v107 = v5;
        if ( (int)v105 + 2LL >= (unsigned __int64)(unsigned int)v5 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v5;
            v118 = "Packet len %u too short for extra info packet data";
            v116 = "SMSecurityExchangeInfo";
            LODWORD(Src) = 1142;
            v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v5,
              (unsigned int)byte_1802AC9C1,
              v56,
              v57,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Src,
              (__int64)&v116,
              (__int64)&Size);
          }
          v74 = 290;
          goto LABEL_89;
        }
        v108 = *v106;
        v109 = v105 + 2;
        v110 = v106 + 1;
        if ( (_WORD)v108 )
        {
          v109 += v108;
          if ( v109 > (unsigned int)v5 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(Size) = v5;
              v118 = "Packet len %u too short for extra info packet data";
              v116 = "SMSecurityExchangeInfo";
              LODWORD(Src) = 1162;
              v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
              LODWORD(v119) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v5,
                (unsigned int)&dword_1802ACAB4,
                v56,
                v57,
                (__int64)&v118,
                (__int64)&v119,
                (__int64)&v117,
                (__int64)&Src,
                (__int64)&v116,
                (__int64)&Size);
            }
            v74 = 291;
            goto LABEL_89;
          }
          memset_0((void *)(*((_QWORD *)v7 + 9) + 320LL), 0, 0x200u);
          v110 = (unsigned __int16 *)((char *)v110 + v108);
        }
        if ( v109 < (unsigned int)v5 )
        {
          v111 = v109 + 172;
          if ( v111 > (unsigned int)v5 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(Size) = v5;
              v118 = "Packet len %u too short for time zone data";
              v116 = "SMSecurityExchangeInfo";
              LODWORD(Src) = 1190;
              v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
              LODWORD(v119) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v107,
                (unsigned int)byte_1802ACA63,
                v56,
                v57,
                (__int64)&v118,
                (__int64)&v119,
                (__int64)&v117,
                (__int64)&Src,
                (__int64)&v116,
                (__int64)&Size);
            }
            v74 = 292;
            goto LABEL_89;
          }
          v112 = (_OWORD *)*((_QWORD *)v7 + 9);
          v112[52] = *(_OWORD *)v110;
          v112[53] = *((_OWORD *)v110 + 1);
          v112[54] = *((_OWORD *)v110 + 2);
          v112[55] = *((_OWORD *)v110 + 3);
          v112[56] = *((_OWORD *)v110 + 4);
          v112[57] = *((_OWORD *)v110 + 5);
          v112[58] = *((_OWORD *)v110 + 6);
          v112[59] = *((_OWORD *)v110 + 7);
          v112[60] = *((_OWORD *)v110 + 8);
          v112[61] = *((_OWORD *)v110 + 9);
          *(_OWORD *)((char *)v112 + 988) = *(_OWORD *)(v110 + 78);
          if ( v111 < (unsigned int)v5 )
          {
            if ( v111 + 4 > (unsigned int)v5 )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                LODWORD(Size) = v5;
                v118 = "Packet len %u too short for session id data";
                v116 = "SMSecurityExchangeInfo";
                LODWORD(Src) = 1218;
                v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
                LODWORD(v119) = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v107,
                  (unsigned int)byte_1802AC8CD,
                  v56,
                  v57,
                  (__int64)&v118,
                  (__int64)&v119,
                  (__int64)&v117,
                  (__int64)&Src,
                  (__int64)&v116,
                  (__int64)&Size);
              }
              v74 = 293;
              goto LABEL_89;
            }
            *(_DWORD *)(*((_QWORD *)v7 + 9) + 1004LL) = *((_DWORD *)v110 + 43);
          }
        }
      }
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 4LL) = v6[1];
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 4LL) |= 0x10u;
      goto LABEL_186;
    }
    *(_DWORD *)(v27 + 1076) = *v6;
    v28 = *((unsigned __int16 *)v6 + 4);
    if ( v28 > 0x1FE )
      v28 = 510;
    *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 8LL) = v28;
    memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 18LL), 0, 0x200u);
    memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 18LL), (char *)v6 + 18, v28);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v31 = *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL);
      v117 = "Received Domain (len %d):'%s'";
      v116 = (const char *)(v31 + 18);
      LODWORD(Size) = v28;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v31 + 18,
        (unsigned int)&word_1802AD2C6,
        v29,
        v30,
        (__int64)&v117,
        (__int64)&Size,
        (__int64)&v116);
    }
    v32 = *((unsigned __int16 *)v6 + 5);
    Src = (char *)v6 + *((unsigned __int16 *)v6 + 4) + 20;
    if ( v32 > 0x1FE )
      v32 = 510;
    *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 10LL) = v32;
    memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 530LL), 0, 0x200u);
    memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 530LL), Src, v32);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v35 = *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL);
      v117 = "Received UserName (len %d):'%s'";
      v116 = (const char *)(v35 + 530);
      LODWORD(Size) = v32;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v35 + 530,
        (unsigned int)byte_1802AD269,
        v33,
        v34,
        (__int64)&v117,
        (__int64)&Size,
        (__int64)&v116);
    }
    v120[0] = (char *)Src + *((unsigned __int16 *)v6 + 5) + 2;
    v36 = *((unsigned __int16 *)v6 + 6);
    if ( v36 > 0x1FE )
      v36 = 510;
    LODWORD(Size) = v36;
    memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1042LL), 0, 0x200u);
    v38 = *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL);
    if ( *((_BYTE *)v7 + 42) )
    {
      *(_WORD *)(v38 + 12) = 0;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v116 = "Skipped saving client password";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v38,
          (unsigned int)&word_1802AD376,
          0,
          v37,
          (__int64)&v116);
      }
    }
    else
    {
      v39 = v120[0];
      v40 = (unsigned int)Size;
      *(_WORD *)(v38 + 12) = Size;
      memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1042LL), v39, v40);
      if ( !CryptProtectMemory((LPVOID)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1042LL), 0x200u, 0) )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LastError = GetLastError();
          v116 = "SMSecurityExchangeInfo";
          LODWORD(Size) = LastError;
          v118 = "Failed to encrypt the password: Error %d";
          LODWORD(Src) = 554;
          v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
          LODWORD(v119) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v42,
            (unsigned int)byte_1802AD321,
            v43,
            v44,
            (__int64)&v118,
            (__int64)&v119,
            (__int64)&v117,
            (__int64)&Src,
            (__int64)&v116,
            (__int64)&Size);
        }
        v45 = 512;
        v46 = (_BYTE *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1042LL);
        do
        {
          *v46++ = 0;
          --v45;
        }
        while ( v45 );
        *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 12LL) = 0;
      }
    }
    v47 = *((unsigned __int16 *)v6 + 6);
    v48 = (char *)v120[0];
    v49 = v120[0];
    if ( *((_WORD *)v6 + 6) )
    {
      do
      {
        *v49++ = 0;
        --v47;
      }
      while ( v47 );
    }
    v50 = *((unsigned __int16 *)v6 + 7);
    Src = &v48[*((unsigned __int16 *)v6 + 6) + 2];
    if ( v50 > 0x1FE )
      v50 = 510;
    *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 14LL) = v50;
    memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1554LL), 0, 0x200u);
    memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 1554LL), Src, v50);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v53 = *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL);
      v117 = "Received AlternateShell (len %d):'%s'";
      v116 = (const char *)(v53 + 1554);
      LODWORD(Size) = v50;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v53 + 1554,
        (unsigned int)byte_1802AD165,
        v51,
        v52,
        (__int64)&v117,
        (__int64)&Size,
        (__int64)&v116);
    }
    v54 = *((unsigned __int16 *)v6 + 8);
    Src = (char *)Src + *((unsigned __int16 *)v6 + 7) + 2;
    if ( v54 > 0x1FE )
      v54 = 510;
    *(_WORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 16LL) = v54;
    memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 2066LL), 0, 0x200u);
    memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 2066LL), Src, v54);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v58 = *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL);
      v117 = "Received WorkingDir (len %d):'%s'";
      v116 = (const char *)(v58 + 2066);
      LODWORD(Size) = v54;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v58 + 2066,
        (unsigned int)&word_1802AD106,
        v56,
        v57,
        (__int64)&v117,
        (__int64)&Size,
        (__int64)&v116);
    }
    v59 = (char *)Src + *((unsigned __int16 *)v6 + 8);
    v60 = (_DWORD)v59 + 2 - (_DWORD)v6;
    LODWORD(Src) = v60;
    if ( v60 >= (unsigned int)v5 )
      goto LABEL_147;
    if ( (int)v60 + 4LL >= (unsigned __int64)(unsigned int)v5 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(Size) = v5;
        v118 = "Packet len %u too short for extra info packet data";
        v116 = "SMSecurityExchangeInfo";
        LODWORD(Src) = 615;
        v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
        LODWORD(v119) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)qword_1802AD1C8,
          v56,
          v57,
          (__int64)&v118,
          (__int64)&v119,
          (__int64)&v117,
          (__int64)&Src,
          (__int64)&v116,
          (__int64)&Size);
      }
      v74 = 278;
      goto LABEL_89;
    }
    *(_DWORD *)(*((_QWORD *)v7 + 9) + 236LL) = *((unsigned __int16 *)v59 + 1);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v61 = *(_DWORD *)(*((_QWORD *)v7 + 9) + 236LL);
      v116 = "Client address family=%d";
      LODWORD(Size) = v61;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v61,
        (unsigned int)byte_1802AD219,
        v56,
        v57,
        (__int64)&v116,
        (__int64)&Size);
    }
    LODWORD(v55) = *((unsigned __int16 *)v59 + 2);
    v57 = 0;
    v62 = (unsigned __int16 *)(v59 + 6);
    LODWORD(v63) = (_DWORD)Src + 4;
    LOWORD(Size) = v55;
    if ( (_WORD)v55 )
    {
      v64 = v55 + (_DWORD)v63;
      LODWORD(Src) = v64;
      if ( v64 >= (unsigned int)v5 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(Size) = v5;
          v118 = "Packet len %u too short for extra info packet data";
          v116 = "SMSecurityExchangeInfo";
          LODWORD(Src) = 647;
          v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
          LODWORD(v119) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v64,
            (unsigned int)&dword_1802ACFD4,
            v56,
            0,
            (__int64)&v118,
            (__int64)&v119,
            (__int64)&v117,
            (__int64)&Src,
            (__int64)&v116,
            (__int64)&Size);
        }
        v74 = 279;
        goto LABEL_89;
      }
      memset_0((void *)(*((_QWORD *)v7 + 9) + 240LL), 0, 0x50u);
      v67 = (unsigned __int16)Size;
      v55 = (unsigned __int16)Size;
      v68 = (_OWORD *)(*((_QWORD *)v7 + 9) + 240LL);
      v116 = (const char *)(unsigned __int16)Size;
      if ( (unsigned __int16)Size > 0x4Eu )
      {
        *v68 = *(_OWORD *)v62;
        v68[1] = *((_OWORD *)v62 + 1);
        v68[2] = *((_OWORD *)v62 + 2);
        v68[3] = *((_OWORD *)v62 + 3);
        *(_OWORD *)((char *)v68 + 62) = *(_OWORD *)(v62 + 31);
      }
      else
      {
        memcpy_0(v68, v62, (unsigned __int16)Size);
        v55 = (unsigned __int64)v116;
      }
      v62 = (unsigned __int16 *)((char *)v62 + v55);
      if ( (unsigned int)CallbackContext > 4 )
      {
        v116 = (const char *)(*((_QWORD *)v7 + 9) + 240LL);
        v117 = "Client address=%s";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v67,
          (unsigned int)byte_1802AD025,
          v65,
          v66,
          (__int64)&v117,
          (__int64)&v116);
      }
      LODWORD(v63) = (_DWORD)Src;
      v57 = 0;
    }
    v56 = (unsigned int)v5;
    if ( (int)v63 + 2LL >= (unsigned __int64)(unsigned int)v5 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(Size) = v5;
        v118 = "Packet len %u too short for extra info packet data";
        v116 = "SMSecurityExchangeInfo";
        LODWORD(Src) = 669;
        v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
        LODWORD(v119) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v63,
          (unsigned int)byte_1802AD0B5,
          v5,
          0,
          (__int64)&v118,
          (__int64)&v119,
          (__int64)&v117,
          (__int64)&Src,
          (__int64)&v116,
          (__int64)&Size);
      }
      v74 = 280;
      goto LABEL_89;
    }
    v69 = *v62;
    LODWORD(v55) = (_DWORD)v63 + 2;
    v70 = v62 + 1;
    LOWORD(Size) = v69;
    if ( (_WORD)v69 )
    {
      LODWORD(v55) = v69 + v55;
      LODWORD(v120[0]) = v55;
      if ( (unsigned int)v55 > (unsigned int)v5 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(Size) = v5;
          v118 = "Packet len %u too short for extra info packet data";
          v116 = "SMSecurityExchangeInfo";
          LODWORD(Src) = 700;
          v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
          LODWORD(v119) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)v63,
            (unsigned int)byte_1802ACEE1,
            v5,
            0,
            (__int64)&v118,
            (__int64)&v119,
            (__int64)&v117,
            (__int64)&Src,
            (__int64)&v116,
            (__int64)&Size);
        }
        v74 = 281;
        goto LABEL_89;
      }
      memset_0((void *)(*((_QWORD *)v7 + 9) + 320LL), 0, 0x200u);
      v72 = (_OWORD *)(*((_QWORD *)v7 + 9) + 320LL);
      v116 = (const char *)(unsigned __int16)Size;
      if ( (unsigned __int16)Size > 0x1FEu )
      {
        v75 = 3;
        v63 = v70;
        v73 = 128;
        do
        {
          *v72 = *v63;
          v72[1] = v63[1];
          v72[2] = v63[2];
          v72[3] = v63[3];
          v72[4] = v63[4];
          v72[5] = v63[5];
          v72[6] = v63[6];
          v76 = v63[7];
          v63 += 8;
          v72[7] = v76;
          v72 += 8;
          --v75;
        }
        while ( v75 );
        *v72 = *v63;
        v72[1] = v63[1];
        v72[2] = v63[2];
        v72[3] = v63[3];
        v72[4] = v63[4];
        v72[5] = v63[5];
        v72[6] = v63[6];
        *(_OWORD *)((char *)v72 + 110) = *(_OWORD *)((char *)v63 + 110);
      }
      else
      {
        memcpy_0(v72, v70, (unsigned __int16)Size);
      }
      v70 = (unsigned __int16 *)((char *)v70 + (_QWORD)v116);
      if ( (unsigned int)CallbackContext > 4 )
      {
        v116 = (const char *)(*((_QWORD *)v7 + 9) + 320LL);
        v117 = "Client directory: %s";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v63,
          (unsigned int)&byte_1802AD06F,
          v73,
          v71,
          (__int64)&v117,
          (__int64)&v116);
      }
      LODWORD(v55) = v120[0];
      v57 = 0;
      v56 = (unsigned int)v5;
    }
    if ( (unsigned int)v55 < (unsigned int)v5 )
    {
      LODWORD(v55) = v55 + 172;
      if ( (unsigned int)v55 > (unsigned int)v5 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(Size) = v5;
          v118 = "Packet len %u too short for time zone data";
          v116 = "SMSecurityExchangeInfo";
          LODWORD(Src) = 729;
          v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
          LODWORD(v119) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)v63,
            (unsigned int)qword_1802ACE90,
            v56,
            0,
            (__int64)&v118,
            (__int64)&v119,
            (__int64)&v117,
            (__int64)&Src,
            (__int64)&v116,
            (__int64)&Size);
        }
        v74 = 282;
        goto LABEL_89;
      }
      v77 = (_OWORD *)*((_QWORD *)v7 + 9);
      v77[52] = *(_OWORD *)v70;
      v77[53] = *((_OWORD *)v70 + 1);
      v77[54] = *((_OWORD *)v70 + 2);
      v77[55] = *((_OWORD *)v70 + 3);
      v77[56] = *((_OWORD *)v70 + 4);
      v77[57] = *((_OWORD *)v70 + 5);
      v77[58] = *((_OWORD *)v70 + 6);
      v77[59] = *((_OWORD *)v70 + 7);
      v77[60] = *((_OWORD *)v70 + 8);
      v77[61] = *((_OWORD *)v70 + 9);
      v78 = *(_OWORD *)(v70 + 78);
      v70 += 86;
      *(_OWORD *)((char *)v77 + 988) = v78;
      if ( (unsigned int)v55 < (unsigned int)v5 )
      {
        LODWORD(v55) = v55 + 4;
        if ( (unsigned int)v55 > (unsigned int)v5 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v5;
            v118 = "Packet len %u too short for session id data";
            v116 = "SMSecurityExchangeInfo";
            LODWORD(Src) = 757;
            v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)v63,
              (unsigned int)byte_1802ACF83,
              v56,
              0,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Src,
              (__int64)&v116,
              (__int64)&Size);
          }
          v74 = 283;
          goto LABEL_89;
        }
        v79 = *(_DWORD *)v70;
        v70 += 2;
        v80 = *((_QWORD *)v7 + 9);
        *(_DWORD *)(v80 + 1004) = v79;
        if ( (unsigned int)v55 < (unsigned int)v5 )
        {
          LODWORD(v55) = v55 + 4;
          if ( (unsigned int)v55 > (unsigned int)v5 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(Size) = v5;
              v118 = "Packet len %u too short for session id data";
              v116 = "SMSecurityExchangeInfo";
              LODWORD(Src) = 787;
              v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
              LODWORD(v119) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v80,
                (unsigned int)word_1802ACF32,
                v56,
                0,
                (__int64)&v118,
                (__int64)&v119,
                (__int64)&v117,
                (__int64)&Src,
                (__int64)&v116,
                (__int64)&Size);
            }
            v74 = 284;
            goto LABEL_89;
          }
          v81 = *(_DWORD *)v70;
          v70 += 2;
          *(_DWORD *)(*((_QWORD *)v7 + 9) + 1072LL) = v81;
        }
      }
    }
    v82 = *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL);
    *(_WORD *)(v82 + 3360) = 0;
    if ( (unsigned int)v55 < (unsigned int)v5 )
    {
      if ( (int)v55 + 2LL > v56 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(Size) = v5;
          v118 = "Packet len %u too short for extra info packet data";
          v116 = "SMSecurityExchangeInfo";
          LODWORD(Src) = 815;
          v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
          LODWORD(v119) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v82,
            (unsigned int)byte_1802ACDB9,
            v56,
            0,
            (__int64)&v118,
            (__int64)&v119,
            (__int64)&v117,
            (__int64)&Src,
            (__int64)&v116,
            (__int64)&Size);
        }
        v74 = 285;
        goto LABEL_89;
      }
      v83 = *v70;
      LODWORD(v55) = v55 + 2;
      Src = ++v70;
      if ( (_WORD)v83 )
      {
        LODWORD(v55) = v83 + v55;
        v84 = v83;
        LODWORD(v120[0]) = v55;
        if ( (unsigned int)v55 > (unsigned int)v5 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v5;
            v118 = "Packet len %u too short for extra info packet data";
            v116 = "SMSecurityExchangeInfo";
            LODWORD(Src) = 858;
            v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v83,
              (unsigned int)&byte_1802ACE3F,
              v56,
              0,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Src,
              (__int64)&v116,
              (__int64)&Size);
          }
          v74 = 287;
          goto LABEL_89;
        }
        v85 = *(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL);
        if ( (unsigned __int16)v83 > 0x80u )
        {
          *(_WORD *)(v85 + 3360) = 0;
          memset_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 3362LL), 0, 0x80u);
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v84;
            v118 = "Autoreconnect info too long %d";
            v116 = "SMSecurityExchangeInfo";
            LODWORD(Src) = 844;
            v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v93,
              (unsigned int)qword_1802ACD70,
              v94,
              v95,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Src,
              (__int64)&v116,
              (__int64)&Size);
          }
          v74 = 286;
          goto LABEL_89;
        }
        *(_WORD *)(v85 + 3360) = v83;
        v86 = v83;
        memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 3362LL), Src, v83);
        Src = (char *)Src + v86;
        v70 = (unsigned __int16 *)Src;
        LODWORD(v55) = v120[0];
      }
    }
    if ( (unsigned __int64)(unsigned int)v55 + 4 > (unsigned int)v5 )
    {
LABEL_147:
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 9) + 1152LL) + 4LL) = v6[1];
LABEL_186:
      v4 = 1;
      *(_DWORD *)(*((_QWORD *)v7 + 9) + 1332LL) = (v6[1] >> 14) & 1;
      v113 = *((_QWORD *)v7 + 9);
      *((_DWORD *)v7 + 12) = 4;
      WDW_OnSMConnected(v113, 0, v56, v57);
      WDW_LogTCPStateTransitionEvent(*((_QWORD *)v7 + 9), 7, 10, 10);
      return v4;
    }
    LODWORD(Src) = v55 + 2;
    if ( (int)v55 + 2 > (unsigned int)v5 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(Size) = v5;
        v118 = "Packet length %u too short for uEncryptionCoveragePercentage";
        v116 = "SMSecurityExchangeInfo";
        LODWORD(Src) = 893;
        v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
        LODWORD(v119) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)byte_1802ACC7D,
          v56,
          v57,
          (__int64)&v118,
          (__int64)&v119,
          (__int64)&v117,
          (__int64)&Src,
          (__int64)&v116,
          (__int64)&Size);
      }
      v74 = 295;
    }
    else
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(Size) = *v70;
        v116 = "Received sparse encryption coverage: %u.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)word_1802ACE0A,
          v56,
          v57,
          (__int64)&v116,
          (__int64)&Size);
      }
      v87 = (_DWORD)Src + 2;
      LODWORD(Src) = v87;
      if ( v87 > (unsigned int)v5 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(Size) = v5;
          v118 = "Packet length %u too short for cbForcedEncryptedHeader";
          v116 = "SMSecurityExchangeInfo";
          LODWORD(Src) = 917;
          v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
          LODWORD(v119) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v87,
            (unsigned int)&byte_1802ACD1F,
            v56,
            v57,
            (__int64)&v118,
            (__int64)&v119,
            (__int64)&v117,
            (__int64)&Src,
            (__int64)&v116,
            (__int64)&Size);
        }
        v74 = 296;
      }
      else
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          LODWORD(Size) = v70[1];
          v116 = "Received sparse encryption paramter - force encrypted header: %u.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v87,
            (unsigned int)qword_1802ACC48,
            v56,
            v57,
            (__int64)&v116,
            (__int64)&Size);
          v87 = (unsigned int)Src;
        }
        if ( v87 >= (unsigned int)v5 )
          goto LABEL_147;
        LODWORD(v55) = v5;
        if ( (int)v87 + 2LL > (unsigned __int64)(unsigned int)v5 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v5;
            v118 = "Packet len %u too short for extra info packet data";
            v116 = "SMSecurityExchangeInfo";
            LODWORD(Src) = 961;
            v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v87,
              (unsigned int)&word_1802ACCCE,
              v56,
              v57,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Src,
              (__int64)&v116,
              (__int64)&Size);
          }
          v74 = 304;
        }
        else
        {
          v88 = v70[2];
          v89 = v87 + 2;
          v90 = v70 + 3;
          LOWORD(Size) = v88;
          LODWORD(v55) = 0;
          if ( !(_WORD)v88 )
          {
LABEL_145:
            if ( v89 + 2 <= (unsigned int)v5 )
            {
              *(_WORD *)(*((_QWORD *)v7 + 9) + 1824LL) = *(_WORD *)v90;
              goto LABEL_147;
            }
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(Size) = v5;
              v118 = "Packet length %u too short for DynamicDaylightTimeDisabled";
              v116 = "SMSecurityExchangeInfo";
              LODWORD(Src) = 1019;
              v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
              LODWORD(v119) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v89,
                (unsigned int)byte_1802ACB05,
                v56,
                v57,
                (__int64)&v118,
                (__int64)&v119,
                (__int64)&v117,
                (__int64)&Src,
                (__int64)&v116,
                (__int64)&Size);
            }
            v74 = 306;
            goto LABEL_89;
          }
          v91 = v88 + v89;
          LODWORD(Src) = v91;
          if ( v91 <= (unsigned int)v5 )
          {
            memset_0((void *)(*((_QWORD *)v7 + 9) + 1568LL), 0, 0x100u);
            LODWORD(v56) = 254;
            v55 = (unsigned __int16)Size;
            v92 = (_OWORD *)(*((_QWORD *)v7 + 9) + 1568LL);
            v116 = (const char *)(unsigned __int16)Size;
            if ( (unsigned __int16)Size > 0xFEu )
            {
              *v92 = *v90;
              v92[1] = v90[1];
              v92[2] = v90[2];
              v92[3] = v90[3];
              v92[4] = v90[4];
              v92[5] = v90[5];
              v92[6] = v90[6];
              v92[7] = v90[7];
              v92[8] = v90[8];
              v92[9] = v90[9];
              v92[10] = v90[10];
              v92[11] = v90[11];
              v92[12] = v90[12];
              v92[13] = v90[13];
              v92[14] = v90[14];
              *(_OWORD *)((char *)v92 + 238) = *(_OWORD *)((char *)v90 + 238);
            }
            else
            {
              memcpy_0(v92, v90, (unsigned __int16)Size);
              v55 = (unsigned __int64)v116;
            }
            v89 = (unsigned int)Src;
            v90 = (_OWORD *)((char *)v90 + v55);
            goto LABEL_145;
          }
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(Size) = v5;
            v118 = "Packet len %d too short for time zone key name";
            v116 = "SMSecurityExchangeInfo";
            LODWORD(Src) = 996;
            v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
            LODWORD(v119) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v91,
              (unsigned int)&word_1802ACB56,
              v56,
              v57,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&v117,
              (__int64)&Src,
              (__int64)&v116,
              (__int64)&Size);
          }
          v74 = 305;
        }
      }
    }
LABEL_89:
    WDW_LogStateTransitionAndDisconnect(*((_QWORD *)v7 + 9), v55, v74, (_DWORD)v6, v5, 7, 34);
    return 0;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(Size) = 477;
    v118 = "Failed alloc InfoPkt";
    v116 = "SMSecurityExchangeInfo";
    v117 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmint.cpp";
    LODWORD(Src) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)byte_1802AD43D,
      v24,
      v25,
      (__int64)&v118,
      (__int64)&Src,
      (__int64)&v117,
      (__int64)&Size,
      (__int64)&v116);
  }
  return v4;
}

```

## disassembly

```asm
0x18018cf48  push    rbp
0x18018cf4a  push    rbx
0x18018cf4b  push    rsi
0x18018cf4c  push    rdi
0x18018cf4d  push    r12
0x18018cf4f  push    r13
0x18018cf51  push    r14
0x18018cf53  push    r15
0x18018cf55  lea     rbp, [rsp-48h]
0x18018cf5a  sub     rsp, 148h
0x18018cf61  xor     ebx, ebx
0x18018cf63  mov     edi, r8d
0x18018cf66  mov     r14, rdx
0x18018cf69  mov     rsi, rcx
0x18018cf6c  lea     r8d, [rbx+4]
0x18018cf70  lea     r15d, [rbx+10h]
0x18018cf74  test    r9d, r9d
0x18018cf77  jz      loc_18018D28E
0x18018cf7d  cmp     [rcx+27h], bl
0x18018cf80  jz      loc_18018D288
0x18018cf86  test    byte ptr [rdx], 8
0x18018cf89  jz      loc_18018D060
0x18018cf8f  mov     eax, cs:CallbackContext
0x18018cf95  cmp     eax, 5
0x18018cf98  jbe     short loc_18018CFBC
0x18018cf9a  lea     rax, aDecryptThePack; "Decrypt the packet"
0x18018cfa1  mov     [rsp+180h+Src], rax
0x18018cfa6  lea     rdx, byte_1802AD6A1
0x18018cfad  lea     rax, [rsp+180h+Src]
0x18018cfb2  mov     [rsp+180h+var_160], rax
0x18018cfb7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18018cfbc  xor     r9d, r9d; int
0x18018cfbf  mov     r8d, edi; unsigned int
0x18018cfc2  mov     rdx, r14; void *
0x18018cfc5  mov     rcx, rsi; struct tagSM_HANDLE_DATA *
0x18018cfc8  call    ?SMDecryptPacket@@YAHPEAUtagSM_HANDLE_DATA@@PEAXIH@Z; SMDecryptPacket(tagSM_HANDLE_DATA *,void *,uint,int)
0x18018cfcd  test    eax, eax
0x18018cfcf  jnz     loc_18018D112
0x18018cfd5  mov     eax, cs:CallbackContext
0x18018cfdb  cmp     eax, 2
0x18018cfde  jbe     short loc_18018D055
0x18018cfe0  lea     rax, aFailedToDecryp_1; "Failed to decrypt packet"
0x18018cfe7  mov     dword ptr [rbp+80h+Size], 147h
0x18018cff1  mov     [rsp+180h+var_108], rax
0x18018cff6  lea     r15, aSmsecurityexch_0; "SMSecurityExchangeInfo"
0x18018cffd  lea     rax, [rsp+180h+Src]
0x18018d002  mov     [rsp+180h+Src], r15
0x18018d007  mov     [rsp+180h+var_140], rax
0x18018d00c  lea     r12, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18018d013  lea     rax, [rbp+80h+Size]
0x18018d01a  mov     [rbp+80h+var_100], r12
0x18018d01e  mov     [rsp+180h+var_148], rax
0x18018d023  lea     rdx, byte_1802AD501
0x18018d02a  lea     rax, [rbp+80h+var_100]
0x18018d02e  mov     r13d, 80004005h
0x18018d034  mov     [rsp+180h+var_150], rax
0x18018d039  lea     rax, [rbp+80h+var_F8]
0x18018d03d  mov     [rsp+180h+var_158], rax
0x18018d042  lea     rax, [rsp+180h+var_108]
0x18018d047  mov     [rsp+180h+var_160], rax
0x18018d04c  mov     dword ptr [rbp+80h+var_F8], r13d
0x18018d050  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18018d055  mov     r8d, 192h
0x18018d05b  jmp     loc_18018F0EA
0x18018d060  mov     rax, [rcx+48h]
0x18018d064  cmp     [rax+534h], ebx
0x18018d06a  jz      loc_18018D118
0x18018d070  mov     eax, cs:CallbackContext
0x18018d076  cmp     eax, 2
0x18018d079  jbe     short loc_18018D0F0
0x18018d07b  lea     rax, aUnencryptedDat; "Unencrypted data in encrypted protocol"
0x18018d082  mov     dword ptr [rbp+80h+Size], 157h
0x18018d08c  mov     [rbp+80h+var_100], rax
0x18018d090  lea     r15, aSmsecurityexch_0; "SMSecurityExchangeInfo"
0x18018d097  lea     rax, [rsp+180h+var_108]
0x18018d09c  mov     [rsp+180h+var_108], r15
0x18018d0a1  mov     [rsp+180h+var_140], rax
0x18018d0a6  lea     r12, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18018d0ad  lea     rax, [rbp+80h+Size]
0x18018d0b4  mov     [rsp+180h+Src], r12
0x18018d0b9  mov     [rsp+180h+var_148], rax
0x18018d0be  lea     rdx, dword_1802AD4BC
0x18018d0c5  lea     rax, [rsp+180h+Src]
0x18018d0ca  mov     r13d, 80004005h
0x18018d0d0  mov     [rsp+180h+var_150], rax
0x18018d0d5  lea     rax, [rbp+80h+var_F8]
0x18018d0d9  mov     [rsp+180h+var_158], rax
0x18018d0de  lea     rax, [rbp+80h+var_100]
0x18018d0e2  mov     [rsp+180h+var_160], rax
0x18018d0e7  mov     dword ptr [rbp+80h+var_F8], r13d
0x18018d0eb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18018d0f0  mov     dword ptr [rsp+180h+var_150], 22h ; '"'
0x18018d0f8  xor     r9d, r9d
0x18018d0fb  mov     dword ptr [rsp+180h+var_158], 7
0x18018d103  mov     r8d, 195h
0x18018d109  mov     dword ptr [rsp+180h+var_160], ebx
0x18018d10d  jmp     loc_18018F101
0x18018d112  mov     r8d, 4
0x18018d118  cmp     [rsi+0Ch], r15d
0x18018d11c  jnz     loc_18018D1E7
0x18018d122  movzx   edx, byte ptr [r14+7]
0x18018d127  lea     rcx, [rdx+10h]
0x18018d12b  cmp     rcx, r15
0x18018d12e  jb      short loc_18018D14B
0x18018d130  cmp     rcx, rdx
0x18018d133  jb      short loc_18018D14B
0x18018d135  cmp     rdi, rcx
0x18018d138  jb      short loc_18018D14B
0x18018d13a  mov     ecx, 0FFFFFFF0h
0x18018d13f  mov     rax, r15
0x18018d142  sub     ecx, edx
0x18018d144  add     edi, ecx
0x18018d146  jmp     loc_18018D1F3
0x18018d14b  mov     eax, cs:CallbackContext
0x18018d151  cmp     eax, 2
0x18018d154  jbe     loc_18018F10A
0x18018d15a  movzx   eax, byte ptr [r14+7]
0x18018d15f  lea     r15, aSmsecurityexch_0; "SMSecurityExchangeInfo"
0x18018d166  mov     dword ptr [rbp+80h+Size], eax
0x18018d16c  lea     r12, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18018d173  lea     rax, aPadlenLdIsTooL; "padlen %ld is too large"
0x18018d17a  mov     [rsp+180h+var_108], r15
0x18018d17f  mov     [rsp+180h+var_110], rax
0x18018d184  lea     rdx, byte_1802AD597
0x18018d18b  lea     rax, [rbp+80h+Size]
0x18018d192  mov     dword ptr [rbp+80h+var_F8], 170h
0x18018d199  mov     [rsp+180h+var_138], rax
0x18018d19e  mov     r13d, 80004005h
0x18018d1a4  lea     rax, [rsp+180h+var_108]
0x18018d1a9  mov     [rsp+180h+Src], r12
0x18018d1ae  mov     [rsp+180h+var_140], rax
0x18018d1b3  lea     rax, [rbp+80h+var_F8]
0x18018d1b7  mov     [rsp+180h+var_148], rax
0x18018d1bc  lea     rax, [rsp+180h+Src]
0x18018d1c1  mov     [rsp+180h+var_150], rax
0x18018d1c6  lea     rax, [rbp+80h+var_100]
0x18018d1ca  mov     [rsp+180h+var_158], rax
0x18018d1cf  lea     rax, [rsp+180h+var_110]
0x18018d1d4  mov     dword ptr [rbp+80h+var_100], r13d
0x18018d1d8  mov     [rsp+180h+var_160], rax
0x18018d1dd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18018d1e2  jmp     loc_18018F10A
0x18018d1e7  mov     eax, 0Ch
0x18018d1ec  cmp     edi, eax
0x18018d1ee  jb      short loc_18018D1FB
0x18018d1f0  add     edi, 0FFFFFFF4h
0x18018d1f3  add     r14, rax
0x18018d1f6  jmp     loc_18018D28E
0x18018d1fb  mov     eax, cs:CallbackContext
0x18018d201  cmp     eax, 2
0x18018d204  jbe     loc_18018F10A
0x18018d20a  lea     rax, aDataLengthTooS; "Data length too small to contain RNS_SE"...
0x18018d211  mov     dword ptr [rbp+80h+Size], edi
0x18018d217  mov     [rsp+180h+Src], rax
0x18018d21c  lea     r15, aSmsecurityexch_0; "SMSecurityExchangeInfo"
0x18018d223  lea     rax, [rbp+80h+Size]
0x18018d22a  mov     [rsp+180h+var_110], r15
0x18018d22f  mov     [rsp+180h+var_138], rax
0x18018d234  lea     r12, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18018d23b  lea     rax, [rsp+180h+var_110]
0x18018d240  mov     dword ptr [rbp+80h+var_100], 17Fh
0x18018d247  mov     [rsp+180h+var_140], rax
0x18018d24c  lea     rdx, word_1802AD546
0x18018d253  lea     rax, [rbp+80h+var_100]
0x18018d257  mov     [rsp+180h+var_108], r12
0x18018d25c  mov     [rsp+180h+var_148], rax
0x18018d261  mov     r13d, 80004005h
0x18018d267  lea     rax, [rsp+180h+var_108]
0x18018d26c  mov     dword ptr [rbp+80h+var_F8], r13d
0x18018d270  mov     [rsp+180h+var_150], rax
0x18018d275  lea     rax, [rbp+80h+var_F8]
0x18018d279  mov     [rsp+180h+var_158], rax
0x18018d27e  lea     rax, [rsp+180h+Src]
0x18018d283  jmp     loc_18018D1D8
0x18018d288  add     r14, r8
0x18018d28b  add     edi, 0FFFFFFFCh
0x18018d28e  xorps   xmm0, xmm0
0x18018d291  mov     qword ptr [rbp+80h+var_54], 60000h
0x18018d299  movups  [rbp+80h+var_CA], xmm0
0x18018d29d  xor     eax, eax
0x18018d29f  mov     dword ptr [rbp+80h+var_F0], ebx
0x18018d2a2  mov     rax, [rsi+48h]
0x18018d2a6  mov     word ptr [rbp+80h+var_F0+4], bx
0x18018d2aa  mov     [rbp+80h+var_AC], 0A0000h
0x18018d2b1  mov     [rbp+80h+var_A8], 60000h
0x18018d2b9  mov     qword ptr [rbp+80h+var_A0], rbx
0x18018d2bd  mov     word ptr [rbp+80h+var_A0+8], bx
0x18018d2c1  mov     qword ptr [rbp+80h+var_54+8], rbx
0x18018d2c5  mov     [rbp+80h+var_58], 40000h
0x18018d2cc  movups  [rbp+80h+var_76], xmm0
0x18018d2d0  movups  [rbp+80h+var_F0+6], xmm0
0x18018d2d4  movups  [rbp+80h+var_DA], xmm0
0x18018d2d8  movaps  xmm1, xmmword ptr [rbp-60h]
0x18018d2dc  movups  [rbp+80h+var_CA+0Eh], xmm0
0x18018d2e0  movups  [rbp+80h+var_A0+0Ah], xmm0
0x18018d2e4  movups  [rbp+80h+var_86], xmm0
0x18018d2e8  movups  [rbp+80h+var_76+0Eh], xmm0
0x18018d2ec  movaps  xmm0, [rbp+80h+var_F0]
0x18018d2f0  movups  xmmword ptr [rax+340h], xmm0
0x18018d2f7  movaps  xmm0, [rbp+80h+var_DA+0Ah]
0x18018d2fb  movups  xmmword ptr [rax+350h], xmm1
0x18018d302  movaps  xmm1, [rbp+80h+var_CA+0Ah]
0x18018d306  movups  xmmword ptr [rax+360h], xmm0
0x18018d30d  movaps  xmm0, xmmword ptr [rbp-30h]
0x18018d311  movups  xmmword ptr [rax+370h], xmm1
0x18018d318  movaps  xmm1, [rbp+80h+var_A0]
0x18018d31c  movups  xmmword ptr [rax+380h], xmm0
0x18018d323  movaps  xmm0, xmmword ptr [rbp-10h]
0x18018d327  movups  xmmword ptr [rax+390h], xmm1
0x18018d32e  movaps  xmm1, [rbp+80h+var_86+6]
0x18018d332  movups  xmmword ptr [rax+3A0h], xmm0
0x18018d339  movaps  xmm0, [rbp+80h+var_76+6]
0x18018d33d  movups  xmmword ptr [rax+3B0h], xmm1
0x18018d344  movaps  xmm1, xmmword ptr [rbp+20h]
0x18018d348  movups  xmmword ptr [rax+3C0h], xmm0
0x18018d34f  movups  xmm0, [rbp+80h+var_54]
0x18018d353  movups  xmmword ptr [rax+3D0h], xmm1
0x18018d35a  movups  xmmword ptr [rax+3DCh], xmm0
0x18018d361  mov     rax, [rsi+48h]
0x18018d365  mov     dword ptr [rax+3ECh], 0FFFFFFFEh
0x18018d36f  cmp     edi, 12h
0x18018d372  jb      loc_18018F050
0x18018d378  mov     al, [r14+4]
0x18018d37c  and     al, r15b
0x18018d37f  neg     al
0x18018d381  movzx   eax, word ptr [r14+10h]
0x18018d386  sbb     ecx, ecx
0x18018d388  and     ecx, 5
0x18018d38b  lea     edx, [rcx+17h]
0x18018d38e  add     edx, eax
0x18018d390  movzx   eax, word ptr [r14+0Eh]
0x18018d395  add     edx, eax
0x18018d397  movzx   eax, word ptr [r14+8]
0x18018d39c  add     edx, eax
0x18018d39e  movzx   eax, word ptr [r14+0Ah]
0x18018d3a3  add     edx, eax
0x18018d3a5  movzx   eax, word ptr [r14+0Ch]
0x18018d3aa  add     edx, eax
0x18018d3ac  cmp     edi, edx
0x18018d3ae  jnb     loc_18018D45F
0x18018d3b4  mov     eax, cs:CallbackContext
0x18018d3ba  cmp     eax, 2
0x18018d3bd  jbe     loc_18018D454
0x18018d3c3  lea     rax, aPacketLenUTooS_0; "Packet len %u too short for info packet"...
0x18018d3ca  mov     dword ptr [rbp+80h+Size], edx
0x18018d3d0  mov     [rsp+180h+var_118], rax
0x18018d3d5  lea     r15, aSmsecurityexch_0; "SMSecurityExchangeInfo"
0x18018d3dc  lea     rax, [rbp+80h+Size]
0x18018d3e3  mov     dword ptr [rbp+80h+var_100], edi
0x18018d3e6  mov     [rsp+180h+var_130], rax
0x18018d3eb  lea     r12, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18018d3f2  lea     rax, [rbp+80h+var_100]
0x18018d3f6  mov     [rsp+180h+var_110], r15
0x18018d3fb  mov     [rsp+180h+var_138], rax
0x18018d400  lea     rdx, qword_1802AD3E8
0x18018d407  lea     rax, [rsp+180h+var_110]
0x18018d40c  mov     dword ptr [rbp+80h+var_F8], 1BCh
0x18018d413  mov     [rsp+180h+var_140], rax
0x18018d418  mov     r13d, 80004005h
0x18018d41e  lea     rax, [rbp+80h+var_F8]
0x18018d422  mov     [rsp+180h+var_108], r12
0x18018d427  mov     [rsp+180h+var_148], rax
0x18018d42c  lea     rax, [rsp+180h+var_108]
0x18018d431  mov     [rsp+180h+var_150], rax
0x18018d436  lea     rax, [rsp+180h+Src]
0x18018d43b  mov     [rsp+180h+var_158], rax
0x18018d440  lea     rax, [rsp+180h+var_118]
0x18018d445  mov     [rsp+180h+var_160], rax
0x18018d44a  mov     dword ptr [rsp+180h+Src], r13d
0x18018d44f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18018d454  mov     r8d, 114h
0x18018d45a  jmp     loc_18018F0EA
0x18018d45f  mov     rax, [rsi+48h]
0x18018d463  cmp     [rax+480h], rbx
0x18018d46a  jnz     short loc_18018D4DF
0x18018d46c  mov     eax, cs:CallbackContext
0x18018d472  mov     r12d, 0EACh
0x18018d478  cmp     eax, r8d
0x18018d47b  jbe     short loc_18018D4AE
0x18018d47d  lea     rax, aAllocUBytesFor; "Alloc %u bytes for InfoPkt"
0x18018d484  mov     [rsp+180h+var_118], r12
0x18018d489  mov     [rsp+180h+var_110], rax
0x18018d48e  lea     rdx, word_1802AD482
0x18018d495  lea     rax, [rsp+180h+var_118]
0x18018d49a  mov     [rsp+180h+var_158], rax
0x18018d49f  lea     rax, [rsp+180h+var_110]
0x18018d4a4  mov     [rsp+180h+var_160], rax
0x18018d4a9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18018d4ae  mov     ecx, r12d; Size
0x18018d4b1  call    WDLIBRT_MemAlloc
0x18018d4b6  mov     rcx, [rsi+48h]
0x18018d4ba  mov     [rcx+480h], rax
0x18018d4c1  mov     rax, [rsi+48h]
0x18018d4c5  mov     rcx, [rax+480h]; void *
0x18018d4cc  test    rcx, rcx
0x18018d4cf  jz      loc_18018D732
0x18018d4d5  mov     r8, r12; Size
0x18018d4d8  xor     edx, edx; Val
0x18018d4da  call    memset_0
0x18018d4df  mov     ebx, 1
  ... truncated ...
```

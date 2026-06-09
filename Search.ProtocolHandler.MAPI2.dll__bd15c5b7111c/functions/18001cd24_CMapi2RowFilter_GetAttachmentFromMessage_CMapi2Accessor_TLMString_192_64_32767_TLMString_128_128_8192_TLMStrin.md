# CMapi2RowFilter::GetAttachmentFromMessage(CMapi2Accessor *,TLMString<192,64,32767> &,TLMString<128,128,8192> &,TLMString<128,128,8192> &,TLMString<1024,1024,1048576> &,TLMString<1024,1024,1048576> &,TLMString<1024,1024,1048576> &,TLMString<1024,1024,1048576> &,TLMString<1024,1024,1048576> &,TLMString<1024,1024,1048576> &,TLMString<128,128,8192> &,TLMString<128,128,8192> &,ulong &,_FILETIME &,_FILETIME &,_FILETIME &,_FILETIME &,IStream * *)

- ea: `0x18001cd24`
- end: `0x18001da96`
- name: `?GetAttachmentFromMessage@CMapi2RowFilter@@QEAAJPEAVCMapi2Accessor@@AEAV?$TLMString@$0MA@$0EA@$0HPPP@@@AEAV?$TLMString@$0IA@$0IA@$0CAAA@@@2AEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@3333322AEAKAEAU_FILETIME@@555PEAPEAUIStream@@@Z`
- size: `3442`
- prototype: `__int64 __fastcall(__int64, struct CMapi2Accessor *, __int64, __int64, __int64, __int64, __int64, struct IMAPITable *, __int64, struct _SRowSet *, struct _SPropTagArray, __int64, int, size_t, _QWORD *, _QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002781c`

## callees

- `0x180002300`
- `0x18000da40`
- `0x18000ea18`
- `0x18000ec8c`
- `0x18000fd58`
- `0x180013fac`
- `0x180013fe0`
- `0x180014420`
- `0x180014448`
- `0x180017894`
- `0x180017a64`
- `0x180017afc`
- `0x180018898`
- `0x18001a248`
- `0x18001a280`
- `0x18001cd24`
- `0x18001da9c`
- `0x18001e08c`
- `0x18001e700`
- `0x180020a48`
- `0x180020e44`
- `0x180029fb4`
- `0x18002b6f4`
- `0x180036e7c`
- `0x180036ecc`
- `0x180037388`
- `0x18003a060`
- `0x18003a0d8`
- `0x18003f010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x18001d9f3`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x18001d9f3`

## string_xrefs

- `0x18001d0cc`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMapi2RowFilter::GetAttachmentFromMessage(
        __int64 a1,
        struct CMapi2Accessor *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        struct IMAPITable *a8,
        __int64 a9,
        struct _SRowSet *a10,
        struct _SPropTagArray a11,
        __int64 a12,
        int a13,
        size_t a14,
        _QWORD *a15,
        _QWORD *a16,
        __int64 a17,
        __int64 a18,
        __int64 a19)
{
  int AttachmentTable; // edi
  __int64 v23; // rdx
  struct IMessage *v24; // rbx
  struct _SPropValue *v25; // rcx
  LONG l; // eax
  const CHAR *lpszA; // r14
  wchar_t *v28; // r8
  __int64 v29; // rdi
  unsigned int v30; // esi
  ULONG v31; // r15d
  int v32; // ecx
  __int64 v33; // rax
  int v34; // ecx
  CMapi2RowFilter *v35; // rcx
  size_t v36; // r12
  int v37; // eax
  LPSRowSet v38; // r14
  LPSPropValue lpProps; // rsi
  __int64 v40; // rcx
  __int64 v41; // r8
  CLMString *v43; // [rsp+20h] [rbp-3A68h]
  CLMString *v44; // [rsp+20h] [rbp-3A68h]
  struct _SPropValue *v45; // [rsp+40h] [rbp-3A48h] BYREF
  int v46[2]; // [rsp+48h] [rbp-3A40h] BYREF
  int v47; // [rsp+50h] [rbp-3A38h] BYREF
  unsigned int v48[2]; // [rsp+58h] [rbp-3A30h] BYREF
  LPSRowSet lpRows; // [rsp+60h] [rbp-3A28h] BYREF
  struct IMAPITable *v50; // [rsp+68h] [rbp-3A20h] BYREF
  struct IMessage *v51; // [rsp+70h] [rbp-3A18h] BYREF
  __int64 v52; // [rsp+78h] [rbp-3A10h] BYREF
  int v53; // [rsp+80h] [rbp-3A08h] BYREF
  __int64 v54; // [rsp+88h] [rbp-3A00h] BYREF
  __int64 v55; // [rsp+90h] [rbp-39F8h]
  size_t Size[2]; // [rsp+98h] [rbp-39F0h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-39E0h]
  __int64 v58; // [rsp+B0h] [rbp-39D8h]
  struct CMapi2Accessor *v59; // [rsp+B8h] [rbp-39D0h]
  _QWORD *v60; // [rsp+C0h] [rbp-39C8h]
  struct _SPropTagArray v61; // [rsp+C8h] [rbp-39C0h] BYREF
  int v62; // [rsp+D0h] [rbp-39B8h]
  int v63; // [rsp+D4h] [rbp-39B4h]
  int v64; // [rsp+D8h] [rbp-39B0h]
  int v65; // [rsp+DCh] [rbp-39ACh]
  _DWORD v66[24]; // [rsp+E0h] [rbp-39A8h] BYREF
  int v67[2]; // [rsp+140h] [rbp-3948h] BYREF
  wchar_t *v68; // [rsp+148h] [rbp-3940h]
  int v69; // [rsp+150h] [rbp-3938h]
  int v70; // [rsp+154h] [rbp-3934h]
  _BYTE v71[2056]; // [rsp+158h] [rbp-3930h] BYREF
  int v72[2]; // [rsp+960h] [rbp-3128h] BYREF
  __int16 *v73; // [rsp+968h] [rbp-3120h]
  __int64 v74; // [rsp+970h] [rbp-3118h]
  __int16 v75; // [rsp+978h] [rbp-3110h] BYREF
  int v76[2]; // [rsp+1180h] [rbp-2908h] BYREF
  __int16 *v77; // [rsp+1188h] [rbp-2900h]
  __int64 v78; // [rsp+1190h] [rbp-28F8h]
  __int16 v79; // [rsp+1198h] [rbp-28F0h] BYREF
  void **v80; // [rsp+19A0h] [rbp-20E8h] BYREF
  __int16 *v81; // [rsp+19A8h] [rbp-20E0h]
  __int64 v82; // [rsp+19B0h] [rbp-20D8h]
  __int16 v83; // [rsp+19B8h] [rbp-20D0h] BYREF
  void **v84; // [rsp+21C0h] [rbp-18C8h] BYREF
  __int16 *v85; // [rsp+21C8h] [rbp-18C0h]
  __int64 v86; // [rsp+21D0h] [rbp-18B8h]
  __int16 v87; // [rsp+21D8h] [rbp-18B0h] BYREF
  void **v88; // [rsp+29E0h] [rbp-10A8h] BYREF
  __int16 *v89; // [rsp+29E8h] [rbp-10A0h]
  __int64 v90; // [rsp+29F0h] [rbp-1098h]
  __int16 v91; // [rsp+29F8h] [rbp-1090h] BYREF
  _BYTE v92[2080]; // [rsp+3200h] [rbp-888h] BYREF
  __int64 v93; // [rsp+3A20h] [rbp-68h] BYREF
  int v94; // [rsp+3A28h] [rbp-60h]
  _QWORD *v95; // [rsp+3A30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A88h] [rbp+0h]

  v54 = a3;
  v59 = a2;
  *(_QWORD *)v48 = a5;
  v57 = a7;
  v50 = a8;
  v58 = a9;
  lpRows = a10;
  v61 = a11;
  Size[0] = a14;
  v95 = a15;
  v60 = a16;
  v52 = a17;
  *(_QWORD *)v46 = a18;
  v55 = a19;
  AttachmentTable = 0;
  v47 = 0;
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      MSSearchTraceId_GetAttachmentFromMessage_Start,
      a3,
      1,
      &v93);
  try
  {
    *(_QWORD *)(a1 + 23952) = a1 + 23912;
    *(_QWORD *)(a1 + 23960) = a1 + 23920;
    *(_QWORD *)(a1 + 23968) = 0;
    CLMString::operator=(a1 + 21168, *((_QWORD *)a2 + 13));
    v51 = 0;
    v23 = *(_QWORD *)(a1 + 23832);
    if ( v23 )
    {
      TComPointer<IFilter>::operator=(&v51, v23);
      v24 = v51;
    }
    else
    {
      AttachmentTable = CMapi2RowFilter::OpenMessage((CMapi2RowFilter *)a1, a2, 0, &v51);
      v24 = v51;
      if ( !v51 )
        AttachmentTable = -2147216895;
    }
    v66[0] = 20;
    v66[1] = 235339779;
    v66[2] = 4325407;
    v66[3] = 4325406;
    v66[4] = 7405826;
    v66[5] = 1703967;
    v66[6] = 1703966;
    v66[7] = 6553631;
    v66[8] = 6553630;
    v66[9] = 6619167;
    v66[10] = 6619166;
    v66[11] = 235143199;
    v66[12] = 235143198;
    v66[13] = 235077663;
    v66[14] = 235077662;
    v66[15] = 235012127;
    v66[16] = 235012126;
    v66[17] = 235471106;
    v66[18] = 3735616;
    v66[19] = 235274304;
    v66[20] = 1507331;
    v53 = 0;
    v45 = 0;
    if ( AttachmentTable < 0
      || (v43 = (CLMString *)&v45,
          AttachmentTable = ((__int64 (__fastcall *)(struct IMessage *, _DWORD *, _QWORD, int *))v24->lpVtbl->GetIDsOfNames)(
                              v24,
                              v66,
                              0,
                              &v53),
          AttachmentTable < 0) )
    {
      v31 = 0;
LABEL_71:
      if ( v55 && (*(_BYTE *)(a1 + 21676) & 0x10) != 0 && AttachmentTable >= 0 )
      {
        v48[0] = 0;
        CEntryId::CEntryId((CEntryId *)Size, *(const wchar_t **)(v54 + 8), v46);
        v61.cValues = 5;
        v61.aulPropTag[0] = 237043715;
        v62 = 267976962;
        v63 = 923205663;
        v64 = 923074563;
        v65 = 236978179;
        v50 = 0;
        AttachmentTable = CMapi2RowFilter::GetAttachmentTable(v35, v24, &v61, &v50, v48);
        v36 = LODWORD(Size[0]);
        while ( 1 )
        {
          lpRows = 0;
          if ( AttachmentTable < 0 || !v48[0] )
            break;
          if ( v47 )
            goto LABEL_102;
          v37 = ((__int64 (__fastcall *)(struct IMAPITable *, __int64, _QWORD, LPSRowSet *))v50->lpVtbl->QueryRows)(
                  v50,
                  10,
                  0,
                  &lpRows);
          AttachmentTable = v37;
          if ( v37 < 0 )
            goto LABEL_101;
          if ( !v48[0] )
          {
            CLogger::Error(v37, L"GetAttachmentFromMessage failure from QueryRows");
            AttachmentTable = -2147216895;
            goto LABEL_101;
          }
          v38 = lpRows;
          while ( 1 )
          {
            if ( v31 >= v38->cRows )
            {
              v31 = 0;
              goto LABEL_99;
            }
            lpProps = v38->aRow[v31].lpProps;
            if ( lpProps[1].ulPropTag == 267976962
              && lpProps[1].Value.l == (_DWORD)v36
              && !memcmp_0(lpProps[1].Value.bin.lpb, (const void *)Size[1], v36) )
            {
              break;
            }
            ++v31;
          }
          v31 = 0;
          *(_QWORD *)v46 = 0;
          if ( lpProps->ulPropTag == 237043715 )
          {
            AttachmentTable = ((__int64 (__fastcall *)(struct IMessage *, _QWORD, _QWORD, __int64, int *))v24->lpVtbl->get_Keywords)(
                                v24,
                                lpProps->Value.ul,
                                0,
                                8,
                                v46);
            if ( AttachmentTable >= 0 )
            {
              LODWORD(v44) = 8;
              AttachmentTable = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, _QWORD, CLMString *, __int64))(**(_QWORD **)v46 + 56LL))(
                                  *(_QWORD *)v46,
                                  922812674,
                                  &IID_IStream,
                                  0,
                                  v44,
                                  v55);
              if ( AttachmentTable >= 0 )
              {
                v93 = 0x3008004000000002LL;
                v94 = 805765184;
                v47 = 0;
                v52 = 0;
                AttachmentTable = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, int *, __int64 *))(**(_QWORD **)v46 + 40LL))(
                                    *(_QWORD *)v46,
                                    &v93,
                                    0,
                                    &v47,
                                    &v52);
                if ( AttachmentTable >= 0 )
                {
                  v40 = v52;
                  if ( *(_DWORD *)v52 == 805830720 && *(_DWORD *)(v52 + 24) == 805765184 )
                  {
                    v54 = v52;
                    *v60 = *(_QWORD *)(v52 + 8);
                    *v95 = *(_QWORD *)(v40 + 32);
                    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v54);
                  }
                }
              }
            }
            v47 = 1;
          }
          if ( lpProps[4].ulPropTag == 236978179 )
            *(_DWORD *)(a1 + 21672) = lpProps[4].Value.l;
          TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(v46);
          v38 = lpRows;
LABEL_99:
          v48[0] -= v38->cRows;
          FreeProws(v38);
        }
        if ( v47 )
          goto LABEL_102;
LABEL_101:
        CLogger::Error(AttachmentTable, L"GetAttachmentFromMessage did not find the attachment specified");
        AttachmentTable = -2147467259;
LABEL_102:
        TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v50);
        CEntryId::FreeBuffer((CEntryId *)Size);
      }
      TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v51);
      goto LABEL_109;
    }
    v25 = v45;
    v93 = (__int64)v45;
    if ( v45->ulPropTag == 235339779 )
      l = v45->Value.l;
    else
      l = 0;
    *(_DWORD *)(a1 + 21676) = l;
    if ( v25[3].ulPropTag == 7405826 )
    {
      LODWORD(v43) = a13;
      CMapi2RowFilter::GetConversationID(v25, v25[3].Value.bin.lpb, v25[3].Value.ul, a12);
      v25 = v45;
    }
    if ( v25[1].ulPropTag == 4325407 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(a4, (CURRENCY)v25[1].Value.cur.int64);
    }
    else
    {
      if ( v25[2].ulPropTag != 4325406 )
        goto LABEL_25;
      lpszA = v25[2].Value.lpszA;
      *(_QWORD *)v67 = &CLMString::`vftable';
      v28 = (wchar_t *)v71;
      v68 = (wchar_t *)v71;
      v69 = 129;
      if ( !lpszA )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
          (const char *)0x80004003LL,
          (int)v43);
      v29 = -1;
      do
        ++v29;
      while ( lpszA[v29] );
      v30 = v29 + 1;
      if ( (unsigned int)(v29 + 1) > 0x81 )
      {
        CLMString::GrowInConstructor((CLMString *)v67, v30);
        v28 = v68;
      }
      v70 = MultiByteToWideCharSZ(lpszA, v29, v28, v30);
      *(_QWORD *)v67 = &TLMString<128,128,8192>::`vftable';
      CLMString::operator=(a4, v68);
      TLMString<128,128,8192>::~TLMString<128,128,8192>(v67);
    }
    v25 = v45;
LABEL_25:
    if ( v25[4].ulPropTag == 1703967 )
    {
      TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v67, "MAPI/");
      CLMString::operator=(a1 + 21696, v68);
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
      (*(void (__fastcall **)(__int64, CURRENCY, _QWORD, __int64))(*(_QWORD *)(a1 + 21696) + 32LL))(
        a1 + 21696,
        v45[4].Value.cur,
        *(unsigned int *)(a1 + 21716),
        0xFFFFFFFFLL);
    }
    else
    {
      if ( v25[5].ulPropTag != 1703966 )
        goto LABEL_30;
      TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v67, "MAPI/");
      CLMString::operator=(a1 + 21696, v68);
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
      (*(void (__fastcall **)(__int64, CURRENCY, _QWORD, __int64))(*(_QWORD *)(a1 + 21696) + 24LL))(
        a1 + 21696,
        v45[5].Value.cur,
        *(unsigned int *)(a1 + 21716),
        0xFFFFFFFFLL);
    }
    v25 = v45;
LABEL_30:
    v77 = &v79;
    v78 = 1025;
    v31 = 0;
    v79 = 0;
    *(_QWORD *)v76 = &TLMString<1024,1024,1048576>::`vftable';
    v73 = &v75;
    v74 = 1025;
    v75 = 0;
    *(_QWORD *)v72 = &TLMString<1024,1024,1048576>::`vftable';
    if ( v25[6].ulPropTag == 6553631 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(v76, (CURRENCY)v25[6].Value.cur.int64);
    }
    else
    {
      if ( v25[7].ulPropTag != 6553630 )
        goto LABEL_35;
      ((void (__fastcall *)(_QWORD, _QWORD))TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>)(
        v67,
        (CURRENCY)v25[7].Value.cur.int64);
      CLMString::operator=(v76, v68);
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
    }
    v25 = v45;
LABEL_35:
    if ( v25[8].ulPropTag == 6619167 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(v72, (CURRENCY)v25[8].Value.cur.int64);
    }
    else
    {
      if ( v25[9].ulPropTag != 6619166 )
        goto LABEL_40;
      ((void (__fastcall *)(_QWORD, _QWORD))TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>)(
        v67,
        (CURRENCY)v25[9].Value.cur.int64);
      CLMString::operator=(v72, v68);
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
    }
    v25 = v45;
LABEL_40:
    if ( v25[10].ulPropTag == 235143199 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(a6, (CURRENCY)v25[10].Value.cur.int64);
    }
    else
    {
      if ( v25[11].ulPropTag != 235143198 )
        goto LABEL_45;
      ((void (__fastcall *)(_QWORD, _QWORD))TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>)(
        v67,
        (CURRENCY)v25[11].Value.cur.int64);
      CLMString::operator=(a6, v68);
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
    }
    v25 = v45;
LABEL_45:
    if ( v25[12].ulPropTag == 235077663 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(v50, (CURRENCY)v25[12].Value.cur.int64);
    }
    else
    {
      if ( v25[13].ulPropTag != 235077662 )
        goto LABEL_50;
      ((void (__fastcall *)(_QWORD, _QWORD))TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>)(
        v67,
        (CURRENCY)v25[13].Value.cur.int64);
      CLMString::operator=(v50, v68);
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
    }
    v25 = v45;
LABEL_50:
    if ( v25[14].ulPropTag == 235012127 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(lpRows, (CURRENCY)v25[14].Value.cur.int64);
    }
    else
    {
      if ( v25[15].ulPropTag != 235012126 )
      {
LABEL_55:
        if ( v25[17].ulPropTag == 3735616 )
          *(_QWORD *)v52 = v25[17].Value.cur.int64;
        if ( v25[18].ulPropTag == 235274304 )
          **(_QWORD **)v46 = v25[18].Value.cur.int64;
        TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v92, &dword_1800444C4);
        v33 = CMapi2RowFilter::MakeFromAddress(v32, (int)v67, (int)v76, (int)v72, (CLMString *)v92);
        CLMString::operator=(*(_QWORD *)v48, v33);
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
        v89 = &v91;
        v90 = 1025;
        v91 = 0;
        v88 = &TLMString<1024,1024,1048576>::`vftable';
        v85 = &v87;
        v86 = 1025;
        v87 = 0;
        v84 = &TLMString<1024,1024,1048576>::`vftable';
        v81 = &v83;
        v82 = 1025;
        v83 = 0;
        v80 = &TLMString<1024,1024,1048576>::`vftable';
        AttachmentTable = CMapi2RowFilter::GetRecipientAddresses(
                            v34,
                            (_DWORD)v24,
                            (unsigned int)&v88,
                            (unsigned int)&v84,
                            (__int64)&v80);
        v46[0] = AttachmentTable;
        if ( AttachmentTable >= 0 )
        {
          CLMString::operator=(v57, v89);
          CLMString::operator=(v58, v85);
          ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(v61, v81);
        }
        *(_DWORD *)(a1 + 23812) = 0;
        *(_DWORD *)(a1 + 23816) = 0;
        if ( AttachmentTable >= 0 )
        {
          if ( v45[16].ulPropTag == 235471106 )
          {
            CEntryId::CEntryId((CEntryId *)&v61, v45 + 16, v46);
            AttachmentTable = v46[0];
            if ( v46[0] >= 0 )
              AttachmentTable = CMapi2RowFilter::CBaseProps::ComputeMessageDeletedAndHiddenState(
                                  v59,
                                  a1 + 21168,
                                  &v61,
                                  a1 + 23816,
                                  a1 + 23812);
            CEntryId::FreeBuffer((CEntryId *)&v61);
          }
          if ( AttachmentTable >= 0 && v45[19].ulPropTag == 1507331 )
            AttachmentTable = CMapi2RowFilter::CBaseProps::ComputeImportance(v45 + 19, (unsigned int *)Size[0]);
        }
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(&v80);
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(&v84);
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(&v88);
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v92);
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v72);
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v76);
        CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v93);
        goto LABEL_71;
      }
      ((void (__fastcall *)(_QWORD, _QWORD))TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>)(
        v67,
        (CURRENCY)v25[15].Value.cur.int64);
      CLMString::operator=(lpRows, v68);
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v67);
    }
    v25 = v45;
    goto LABEL_55;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      1798,
      "onecoreuap\\base\\appmodel\\search\\mssph\\mapi2\\mapi2rowfilt.cxx");
  }
LABEL_109:
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      MSSearchTraceId_GetAttachmentFromMessage_Stop,
      v41,
      1,
      &v95);
  return (unsigned int)AttachmentTable;
}

```

## disassembly

```asm
0x18001cd24  push    rbx
0x18001cd26  push    rsi
0x18001cd27  push    rdi
0x18001cd28  push    r12
0x18001cd2a  push    r13
0x18001cd2c  push    r14
0x18001cd2e  push    r15
0x18001cd30  mov     eax, 3A50h
0x18001cd35  call    _alloca_probe
0x18001cd3a  sub     rsp, rax
0x18001cd3d  mov     rax, cs:__security_cookie
0x18001cd44  xor     rax, rsp
0x18001cd47  mov     [rsp+3A88h+var_48], rax
0x18001cd4f  mov     r15, r9
0x18001cd52  mov     [rsp+3A88h+var_3A00], r8
0x18001cd5a  mov     rbx, rdx
0x18001cd5d  mov     [rsp+3A88h+var_39D0], rdx
0x18001cd65  mov     r13, rcx
0x18001cd68  mov     rax, [rsp+3A88h+arg_20]
0x18001cd70  mov     qword ptr [rsp+3A88h+var_3A30], rax
0x18001cd75  mov     r12, [rsp+3A88h+arg_28]
0x18001cd7d  mov     rax, [rsp+3A88h+arg_30]
0x18001cd85  mov     [rsp+3A88h+var_39E0], rax
0x18001cd8d  mov     rax, [rsp+3A88h+arg_38]
0x18001cd95  mov     [rsp+3A88h+var_3A20], rax
0x18001cd9a  mov     rax, [rsp+3A88h+arg_40]
0x18001cda2  mov     [rsp+3A88h+var_39D8], rax
0x18001cdaa  mov     rax, [rsp+3A88h+arg_48]
0x18001cdb2  mov     [rsp+3A88h+lpRows], rax
0x18001cdb7  mov     rax, [rsp+3A88h+arg_50]
0x18001cdbf  mov     qword ptr [rsp+3A88h+var_39C0.cValues], rax
0x18001cdc7  mov     rsi, [rsp+3A88h+arg_58]
0x18001cdcf  mov     r14, qword ptr [rsp+3A88h+arg_60]
0x18001cdd7  mov     rax, [rsp+3A88h+arg_68]
0x18001cddf  mov     [rsp+3A88h+Size], rax
0x18001cde7  mov     rax, [rsp+3A88h+arg_70]
0x18001cdef  mov     [rsp+3A88h+var_58], rax
0x18001cdf7  mov     rax, [rsp+3A88h+arg_78]
0x18001cdff  mov     [rsp+3A88h+var_39C8], rax
0x18001ce07  mov     rax, [rsp+3A88h+arg_80]
0x18001ce0f  mov     [rsp+3A88h+var_3A10], rax
0x18001ce14  mov     rax, [rsp+3A88h+arg_88]
0x18001ce1c  mov     qword ptr [rsp+3A88h+var_3A40], rax
0x18001ce21  mov     rax, [rsp+3A88h+arg_90]
0x18001ce29  mov     [rsp+3A88h+var_39F8], rax
0x18001ce31  xor     edi, edi
0x18001ce33  mov     [rsp+3A88h+var_3A38], edi
0x18001ce37  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 4
0x18001ce3e  jz      short loc_18001CE65
0x18001ce40  lea     rax, [rsp+3A88h+var_68]
0x18001ce48  mov     [rsp+3A88h+var_3A68], rax
0x18001ce4d  lea     r9d, [rdi+1]
0x18001ce51  lea     rdx, MSSearchTraceId_GetAttachmentFromMessage_Start
0x18001ce58  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18001ce5f  call    McGenEventWrite_EventWriteTransfer
0x18001ce64  nop
0x18001ce65  lea     rax, [r13+5D68h]
0x18001ce6c  mov     [r13+5D90h], rax
0x18001ce73  add     rax, 8
0x18001ce77  mov     [r13+5D98h], rax
0x18001ce7e  mov     qword ptr [r13+5DA0h], 0
0x18001ce89  lea     rcx, [r13+52B0h]
0x18001ce90  mov     rdx, [rbx+68h]
0x18001ce94  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001ce99  mov     [rsp+3A88h+var_3A18], 0
0x18001cea2  mov     rdx, [r13+5D18h]
0x18001cea9  test    rdx, rdx
0x18001ceac  jz      short loc_18001CEBF
0x18001ceae  lea     rcx, [rsp+3A88h+var_3A18]
0x18001ceb3  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18001ceb8  mov     rbx, [rsp+3A88h+var_3A18]
0x18001cebd  jmp     short loc_18001CEE4
0x18001cebf  lea     r9, [rsp+3A88h+var_3A18]; struct IMessage **
0x18001cec4  xor     r8d, r8d; int
0x18001cec7  mov     rdx, rbx; struct CMapi2Accessor *
0x18001ceca  mov     rcx, r13; this
0x18001cecd  call    ?OpenMessage@CMapi2RowFilter@@AEAAJPEAVCMapi2Accessor@@HPEAPEAUIMessage@@@Z; CMapi2RowFilter::OpenMessage(CMapi2Accessor *,int,IMessage * *)
0x18001ced2  mov     edi, eax
0x18001ced4  mov     eax, 80041201h
0x18001ced9  mov     rbx, [rsp+3A88h+var_3A18]
0x18001cede  test    rbx, rbx
0x18001cee1  cmovz   edi, eax
0x18001cee4  mov     [rsp+3A88h+var_39A8], 14h
0x18001ceef  mov     [rsp+3A88h+var_39A4], 0E070003h
0x18001cefa  mov     [rsp+3A88h+var_39A0], 42001Fh
0x18001cf05  mov     [rsp+3A88h+var_399C], 42001Eh
0x18001cf10  mov     [rsp+3A88h+var_3998], 710102h
0x18001cf1b  mov     [rsp+3A88h+var_3994], 1A001Fh
0x18001cf26  mov     [rsp+3A88h+var_3990], 1A001Eh
0x18001cf31  mov     [rsp+3A88h+var_398C], 64001Fh
0x18001cf3c  mov     [rsp+3A88h+var_3988], 64001Eh
0x18001cf47  mov     [rsp+3A88h+var_3984], 65001Fh
0x18001cf52  mov     [rsp+3A88h+var_3980], 65001Eh
0x18001cf5d  mov     [rsp+3A88h+var_397C], 0E04001Fh
0x18001cf68  mov     [rsp+3A88h+var_3978], 0E04001Eh
0x18001cf73  mov     [rsp+3A88h+var_3974], 0E03001Fh
0x18001cf7e  mov     [rsp+3A88h+var_3970], 0E03001Eh
0x18001cf89  mov     [rsp+3A88h+var_396C], 0E02001Fh
0x18001cf94  mov     [rsp+3A88h+var_3968], 0E02001Eh
0x18001cf9f  mov     [rsp+3A88h+var_3964], 0E090102h
0x18001cfaa  mov     [rsp+3A88h+var_3960], 390040h
0x18001cfb5  mov     [rsp+3A88h+var_395C], 0E060040h
0x18001cfc0  mov     [rsp+3A88h+var_3958], 170003h
0x18001cfcb  mov     [rsp+3A88h+var_3A08], 0
0x18001cfd6  mov     [rsp+3A88h+var_3A48], 0
0x18001cfdf  test    edi, edi
0x18001cfe1  js      loc_18001D710
0x18001cfe7  mov     rax, [rbx]
0x18001cfea  lea     rcx, [rsp+3A88h+var_3A48]
0x18001cfef  mov     [rsp+3A88h+var_3A68], rcx
0x18001cff4  lea     r9, [rsp+3A88h+var_3A08]
0x18001cffc  xor     r8d, r8d
0x18001cfff  lea     rdx, [rsp+3A88h+var_39A8]
0x18001d007  mov     rcx, rbx
0x18001d00a  mov     rax, [rax+28h]
0x18001d00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d013  mov     edi, eax
0x18001d015  test    eax, eax
0x18001d017  js      loc_18001D710
0x18001d01d  mov     rcx, [rsp+3A88h+var_3A48]
0x18001d022  mov     [rsp+3A88h+var_68], rcx
0x18001d02a  cmp     dword ptr [rcx], 0E070003h
0x18001d030  jnz     short loc_18001D037
0x18001d032  mov     eax, [rcx+8]
0x18001d035  jmp     short loc_18001D039
0x18001d037  xor     eax, eax
0x18001d039  mov     [r13+54ACh], eax
0x18001d040  cmp     dword ptr [rcx+48h], 710102h
0x18001d047  jnz     short loc_18001D063
0x18001d049  mov     [rsp+3A88h+var_3A68], r14; int
0x18001d04e  mov     r9, rsi
0x18001d051  mov     r8d, [rcx+50h]
0x18001d055  mov     rdx, [rcx+58h]
0x18001d059  call    ?GetConversationID@CMapi2RowFilter@@AEAAHPEAUENTRYID@@KAEAV?$TLMString@$0IA@$0IA@$0CAAA@@@1@Z; CMapi2RowFilter::GetConversationID(ENTRYID *,ulong,TLMString<128,128,8192> &,TLMString<128,128,8192> &)
0x18001d05e  mov     rcx, [rsp+3A88h+var_3A48]
0x18001d063  cmp     dword ptr [rcx+18h], 42001Fh
0x18001d06a  jnz     short loc_18001D07D
0x18001d06c  mov     rdx, [rcx+20h]
0x18001d070  mov     rcx, r15
0x18001d073  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d078  jmp     loc_18001D148
0x18001d07d  cmp     dword ptr [rcx+30h], 42001Eh
0x18001d084  jnz     loc_18001D14D
0x18001d08a  mov     r14, [rcx+38h]
0x18001d08e  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18001d095  mov     qword ptr [rsp+3A88h+var_3948], rax
0x18001d09d  lea     r8, [rsp+3A88h+var_3930]
0x18001d0a5  mov     [rsp+3A88h+var_3940], r8
0x18001d0ad  mov     eax, 81h
0x18001d0b2  mov     [rsp+3A88h+var_3938], eax
0x18001d0b9  test    r14, r14
0x18001d0bc  jnz     short loc_18001D0DB
0x18001d0be  mov     rcx, [rsp+3A88h]; this
0x18001d0c6  mov     r9d, 80004003h; char *
0x18001d0cc  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18001d0d3  lea     edx, [rax+35h]; void *
0x18001d0d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d0db  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d0df  inc     rdi
0x18001d0e2  cmp     byte ptr [r14+rdi], 0
0x18001d0e7  jnz     short loc_18001D0DF
0x18001d0e9  lea     esi, [rdi+1]
0x18001d0ec  cmp     esi, eax
0x18001d0ee  jbe     short loc_18001D107
0x18001d0f0  mov     edx, esi; unsigned int
0x18001d0f2  lea     rcx, [rsp+3A88h+var_3948]; this
0x18001d0fa  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x18001d0ff  mov     r8, [rsp+3A88h+var_3940]; wchar_t *
0x18001d107  mov     r9d, esi; int
0x18001d10a  mov     edx, edi; cbMultiByte
0x18001d10c  mov     rcx, r14; lpMultiByteStr
0x18001d10f  call    ?MultiByteToWideCharSZ@@YAHPEBDHPEA_WH@Z; MultiByteToWideCharSZ(char const *,int,wchar_t *,int)
0x18001d114  mov     [rsp+3A88h+var_3934], eax
0x18001d11b  lea     rax, ??_7?$TLMString@$0IA@$0IA@$0CAAA@@@6B@; const TLMString<128,128,8192>::`vftable'
0x18001d122  mov     qword ptr [rsp+3A88h+var_3948], rax
0x18001d12a  mov     rdx, [rsp+3A88h+var_3940]
0x18001d132  mov     rcx, r15
0x18001d135  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d13a  nop
0x18001d13b  lea     rcx, [rsp+3A88h+var_3948]
0x18001d143  call    ??1?$TLMString@$0IA@$0IA@$0CAAA@@@UEAA@XZ; TLMString<128,128,8192>::~TLMString<128,128,8192>(void)
0x18001d148  mov     rcx, [rsp+3A88h+var_3A48]
0x18001d14d  cmp     dword ptr [rcx+60h], 1A001Fh
0x18001d154  jnz     short loc_18001D1B2
0x18001d156  lea     rdx, aMapi_3; "MAPI/"
0x18001d15d  lea     rcx, [rsp+3A88h+var_3948]
0x18001d165  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEBD@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(char const *)
0x18001d16a  nop
0x18001d16b  lea     rdi, [r13+54C0h]
0x18001d172  mov     rdx, [rsp+3A88h+var_3940]
0x18001d17a  mov     rcx, rdi
0x18001d17d  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d182  nop
0x18001d183  lea     rcx, [rsp+3A88h+var_3948]
0x18001d18b  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001d190  mov     rax, [rdi]
0x18001d193  or      r9d, 0FFFFFFFFh
0x18001d197  mov     r8d, [rdi+14h]
0x18001d19b  mov     rdx, [rsp+3A88h+var_3A48]
0x18001d1a0  mov     rdx, [rdx+68h]
0x18001d1a4  mov     rcx, rdi
0x18001d1a7  mov     rax, [rax+20h]
0x18001d1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1b0  jmp     short loc_18001D218
0x18001d1b2  cmp     dword ptr [rcx+78h], 1A001Eh
0x18001d1b9  jnz     short loc_18001D21D
0x18001d1bb  lea     rdx, aMapi_3; "MAPI/"
0x18001d1c2  lea     rcx, [rsp+3A88h+var_3948]
0x18001d1ca  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEBD@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(char const *)
0x18001d1cf  nop
0x18001d1d0  lea     rdi, [r13+54C0h]
0x18001d1d7  mov     rdx, [rsp+3A88h+var_3940]
0x18001d1df  mov     rcx, rdi
0x18001d1e2  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d1e7  nop
0x18001d1e8  lea     rcx, [rsp+3A88h+var_3948]
0x18001d1f0  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001d1f5  mov     rax, [rdi]
0x18001d1f8  or      r9d, 0FFFFFFFFh
0x18001d1fc  mov     r8d, [rdi+14h]
0x18001d200  mov     rdx, [rsp+3A88h+var_3A48]
0x18001d205  mov     rdx, [rdx+80h]
0x18001d20c  mov     rcx, rdi
0x18001d20f  mov     rax, [rax+18h]
0x18001d213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d218  mov     rcx, [rsp+3A88h+var_3A48]
0x18001d21d  lea     rax, [rsp+3A88h+var_28F0]
0x18001d225  mov     [rsp+3A88h+var_2900], rax
0x18001d22d  mov     [rsp+3A88h+var_28F8], 401h
0x18001d239  xor     r15d, r15d
0x18001d23c  mov     [rsp+3A88h+var_28F0], r15w
0x18001d245  lea     rsi, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x18001d24c  mov     qword ptr [rsp+3A88h+var_2908], rsi
0x18001d254  lea     rax, [rsp+3A88h+var_3110]
0x18001d25c  mov     [rsp+3A88h+var_3120], rax
0x18001d264  mov     [rsp+3A88h+var_3118], 401h
0x18001d270  mov     [rsp+3A88h+var_3110], r15w
0x18001d279  mov     qword ptr [rsp+3A88h+var_3128], rsi
0x18001d281  cmp     dword ptr [rcx+90h], 64001Fh
0x18001d28b  jnz     short loc_18001D2A3
0x18001d28d  mov     rdx, [rcx+98h]
0x18001d294  lea     rcx, [rsp+3A88h+var_2908]
0x18001d29c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d2a1  jmp     short loc_18001D2E7
0x18001d2a3  cmp     dword ptr [rcx+0A8h], 64001Eh
0x18001d2ad  jnz     short loc_18001D2EC
0x18001d2af  mov     rdx, [rcx+0B0h]
0x18001d2b6  lea     rcx, [rsp+3A88h+var_3948]
0x18001d2be  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEBD@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(char const *)
0x18001d2c3  nop
0x18001d2c4  mov     rdx, [rsp+3A88h+var_3940]
0x18001d2cc  lea     rcx, [rsp+3A88h+var_2908]
0x18001d2d4  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d2d9  nop
0x18001d2da  lea     rcx, [rsp+3A88h+var_3948]
0x18001d2e2  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001d2e7  mov     rcx, [rsp+3A88h+var_3A48]
0x18001d2ec  cmp     dword ptr [rcx+0C0h], 65001Fh
0x18001d2f6  jnz     short loc_18001D30E
0x18001d2f8  mov     rdx, [rcx+0C8h]
0x18001d2ff  lea     rcx, [rsp+3A88h+var_3128]
0x18001d307  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d30c  jmp     short loc_18001D352
0x18001d30e  cmp     dword ptr [rcx+0D8h], 65001Eh
0x18001d318  jnz     short loc_18001D357
0x18001d31a  mov     rdx, [rcx+0E0h]
0x18001d321  lea     rcx, [rsp+3A88h+var_3948]
0x18001d329  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEBD@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(char const *)
0x18001d32e  nop
0x18001d32f  mov     rdx, [rsp+3A88h+var_3940]
0x18001d337  lea     rcx, [rsp+3A88h+var_3128]
0x18001d33f  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d344  nop
0x18001d345  lea     rcx, [rsp+3A88h+var_3948]
0x18001d34d  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001d352  mov     rcx, [rsp+3A88h+var_3A48]
0x18001d357  cmp     dword ptr [rcx+0F0h], 0E04001Fh
0x18001d361  jnz     short loc_18001D374
0x18001d363  mov     rdx, [rcx+0F8h]
0x18001d36a  mov     rcx, r12
0x18001d36d  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d372  jmp     short loc_18001D3B3
0x18001d374  cmp     dword ptr [rcx+108h], 0E04001Eh
0x18001d37e  jnz     short loc_18001D3B8
0x18001d380  mov     rdx, [rcx+110h]
0x18001d387  lea     rcx, [rsp+3A88h+var_3948]
0x18001d38f  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEBD@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(char const *)
0x18001d394  nop
0x18001d395  mov     rdx, [rsp+3A88h+var_3940]
0x18001d39d  mov     rcx, r12
0x18001d3a0  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001d3a5  nop
0x18001d3a6  lea     rcx, [rsp+3A88h+var_3948]
0x18001d3ae  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001d3b3  mov     rcx, [rsp+3A88h+var_3A48]
0x18001d3b8  cmp     dword ptr [rcx+120h], 0E03001Fh
0x18001d3c2  jnz     short loc_18001D3D7
0x18001d3c4  mov     rdx, [rcx+128h]
0x18001d3cb  mov     rcx, [rsp+3A88h+var_3A20]
0x18001d3d0  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
  ... truncated ...
```

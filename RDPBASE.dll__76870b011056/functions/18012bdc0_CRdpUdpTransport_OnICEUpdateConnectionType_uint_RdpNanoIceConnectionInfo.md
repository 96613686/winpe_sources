# CRdpUdpTransport::OnICEUpdateConnectionType(uint,RdpNanoIceConnectionInfo *)

- ea: `0x18012bdc0`
- end: `0x18012cb22`
- name: `?OnICEUpdateConnectionType@CRdpUdpTransport@@UEAAJIPEAURdpNanoIceConnectionInfo@@@Z`
- size: `3426`
- prototype: `__int64 __fastcall(CRdpUdpTransport *__hidden this, unsigned int, struct RdpNanoIceConnectionInfo *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, installer_update`

## callees

- `0x180001008`
- `0x1800018a4`
- `0x180001be4`
- `0x180002550`
- `0x180003158`
- `0x1800032bc`
- `0x18000367c`
- `0x1800043c4`
- `0x180004a94`
- `0x18000552c`
- `0x18001b3f8`
- `0x180046778`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x180125e20`
- `0x1801287d0`
- `0x180129f7c`
- `0x18012bdc0`
- `0x18012d6e4`
- `0x18012ebfc`
- `0x18012f210`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18012be92`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18012be92`

## string_xrefs

- `0x18012c33c`: `OnICEUpdateConnectionType`
- `0x18012c243`: `ICE: Smiles Add Link`
- `0x18012c364`: `Set new links failed`
- `0x18012c876`: `ICE: Smiles Switch Active Link`
- `0x18012c560`: `ICE: Smiles Remove Link`
- `0x18012c964`: `ICE: Set first Smiles active Link`
- `0x18012c926`: `ICE: Updated active link type`
- `0x18012ca91`: `ICE: Updated active link type`
- `0x18012c9cd`: `ICE: swap smilesLinkInfo`

## pseudocode

```c
__int64 __fastcall CRdpUdpTransport::OnICEUpdateConnectionType(
        CRdpUdpTransport *this,
        unsigned int a2,
        struct RdpNanoIceConnectionInfo *a3,
        int a4)
{
  unsigned int v4; // r13d
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  unsigned __int64 v12; // r14
  unsigned int v13; // r15d
  __int64 v14; // rax
  bool v15; // cf
  size_t v16; // rax
  unsigned __int64 *v17; // rax
  char *v18; // rsi
  unsigned __int64 v19; // rdx
  struct RdpNanoIceCandidate *v20; // rcx
  char (**v21)[7]; // r8
  struct SessionStartupCtl *v22; // r14
  const char *v23; // r9
  unsigned int v24; // r12d
  int v25; // r11d
  __int64 v26; // rcx
  int v27; // r9d
  __int64 v28; // r8
  __int64 v29; // rax
  unsigned int *v30; // r10
  __int64 v31; // rax
  struct RdpNanoIceCandidate *v32; // r8
  unsigned int *v33; // r8
  unsigned int v34; // eax
  __int64 v35; // rax
  bool v36; // zf
  int IsEqual; // eax
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // r14d
  const unsigned __int16 *v41; // r14
  unsigned int v42; // ecx
  unsigned int v43; // eax
  unsigned int v44; // ecx
  unsigned int v45; // eax
  __int64 v46; // rdx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  unsigned int v50; // ecx
  unsigned int v51; // eax
  unsigned int v52; // ecx
  unsigned int v53; // eax
  __int64 v54; // rdx
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  unsigned int v58; // r13d
  unsigned int *v59; // rbx
  unsigned int v60; // eax
  unsigned __int64 v61; // rcx
  const unsigned __int16 *v62; // r10
  __int64 v63; // r11
  __int64 v64; // rax
  __int64 v65; // rax
  const unsigned __int16 *v66; // rbx
  const unsigned __int16 *v67; // r13
  unsigned __int64 v68; // rcx
  const unsigned __int16 *v69; // r14
  SessionStartupCtl::SmilesLinkInfo *v70; // r11
  const unsigned __int16 *v71; // rax
  unsigned __int64 v72; // rcx
  const unsigned __int16 *v73; // r10
  __int64 v74; // rax
  int v75; // ecx
  __int64 v76; // r10
  const unsigned __int16 *v77; // r11
  struct SessionStartupCtl *v78; // rax
  SessionStartupCtl::SmilesLinkInfo *v79; // rcx
  __int64 v80; // rax
  unsigned int v81; // ecx
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // r8
  __int64 v85; // rdx
  unsigned int v86; // edx
  unsigned int v87; // ecx
  int v88; // [rsp+B0h] [rbp-80h] BYREF
  const unsigned __int16 *v89; // [rsp+B8h] [rbp-78h] BYREF
  struct RdpNanoIceCandidate *v90; // [rsp+C0h] [rbp-70h] BYREF
  struct SessionStartupCtl *v91; // [rsp+C8h] [rbp-68h] BYREF
  const char *v92; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v93; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v94; // [rsp+E0h] [rbp-50h] BYREF
  SessionStartupCtl::SmilesLinkInfo *v95; // [rsp+E8h] [rbp-48h] BYREF
  const char *v96; // [rsp+F0h] [rbp-40h] BYREF
  int v97[2]; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v98; // [rsp+100h] [rbp-30h] BYREF
  const char *v99; // [rsp+108h] [rbp-28h] BYREF
  __int64 v100; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v101; // [rsp+118h] [rbp-18h] BYREF
  GUID *v102; // [rsp+120h] [rbp-10h] BYREF
  const char *v103; // [rsp+128h] [rbp-8h] BYREF
  const unsigned __int16 *v104; // [rsp+130h] [rbp+0h] BYREF
  const unsigned __int16 *v105; // [rsp+138h] [rbp+8h] BYREF
  SessionStartupCtl::SmilesLinkInfo *v106; // [rsp+140h] [rbp+10h] BYREF
  const unsigned __int16 *v107; // [rsp+148h] [rbp+18h] BYREF
  __int64 v108; // [rsp+150h] [rbp+20h] BYREF
  const unsigned __int16 *v109; // [rsp+158h] [rbp+28h] BYREF
  const unsigned __int16 *v110; // [rsp+160h] [rbp+30h] BYREF
  const unsigned __int16 *v111; // [rsp+168h] [rbp+38h] BYREF
  GUID *v112; // [rsp+170h] [rbp+40h] BYREF
  const char *v113; // [rsp+178h] [rbp+48h] BYREF
  const char *v114; // [rsp+180h] [rbp+50h] BYREF
  __int64 v115; // [rsp+188h] [rbp+58h] BYREF
  GUID v116; // [rsp+190h] [rbp+60h] BYREF
  GUID ActivityId; // [rsp+1A0h] [rbp+70h] BYREF

  v4 = 0;
  v91 = 0;
  if ( !*((_DWORD *)this + 102) )
  {
    v80 = *((unsigned int *)a3 + 17);
    v81 = 7;
    if ( (unsigned int)v80 < *((_DWORD *)a3 + 16) )
    {
      v82 = *((_QWORD *)a3 + 7);
      v83 = 2 * v80;
      v84 = *(unsigned int *)(v82 + 8 * v83);
      if ( (unsigned int)v84 >= *((_DWORD *)a3 + 8)
        || (v85 = *(unsigned int *)(v82 + 8 * v83 + 4), (unsigned int)v85 >= *((_DWORD *)a3 + 12)) )
      {
        if ( (unsigned int)CallbackContext > 3 )
        {
          v96 = "Invalid RdpNanoIceConnectionInfo structure";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)&dword_1801D1CBC,
            0,
            a4,
            (__int64)&v96);
        }
        return 0;
      }
      v86 = *(_DWORD *)(*((_QWORD *)a3 + 5) + 40 * v85);
      v87 = *(_DWORD *)(*((_QWORD *)a3 + 3) + 40 * v84);
      if ( v87 <= v86 )
        v87 = v86;
      v81 = RdpNanoIceCandidateTypeToType(v87);
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v89) = v81;
      v96 = "ICE: Updated active link type";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v81,
        (unsigned int)byte_1801CFE25,
        (_DWORD)a3,
        a4,
        (__int64)&v96,
        (__int64)&v89);
    }
    return 0;
  }
  if ( (unsigned int)SessionCtlBlkManager::Find((CRdpUdpTransport *)((char *)this + 416), a2, &v91) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v88 = *((_DWORD *)this + 109);
      v95 = (SessionStartupCtl::SmilesLinkInfo *)"ICE: find SessionStartupCtl for request failed";
      LODWORD(v93) = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)byte_1801D0FA9,
        v9,
        v10,
        (__int64)&v95,
        (__int64)&v93,
        (__int64)&v88);
    }
    return 2147500037LL;
  }
  v116 = (GUID)*((_OWORD *)v91 + 6);
  ActivityId = v116;
  EventActivityIdControl(4u, &ActivityId);
  if ( !*((_DWORD *)a3 + 16) )
  {
LABEL_89:
    CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
    return 0;
  }
  v12 = *((unsigned int *)a3 + 16);
  v13 = -1;
  v88 = 7;
  v14 = v12 << 6;
  if ( !is_mul_ok(v12, 0x40u) )
    v14 = -1;
  v15 = __CFADD__(v14, 8);
  v16 = v14 + 8;
  if ( v15 )
    v16 = -1;
  v17 = (unsigned __int64 *)operator new(v16);
  if ( v17 )
  {
    v18 = (char *)(v17 + 1);
    *v17 = v12;
    `vector constructor iterator'(
      v17 + 1,
      0x40u,
      (unsigned int)v12,
      (void *(*)(void *))SessionStartupCtl::SmilesLinkInfo::SmilesLinkInfo);
  }
  else
  {
    v18 = 0;
  }
  memset_0(v18, 0, (unsigned __int64)*((unsigned int *)a3 + 16) << 6);
  v21 = &off_18016AA80;
  v22 = v91;
  v23 = "Udp";
  v24 = 0;
  if ( !*((_DWORD *)a3 + 16) )
  {
LABEL_46:
    v58 = 0;
    if ( *((_DWORD *)v22 + 28) )
    {
      do
      {
        v59 = (unsigned int *)(*((_QWORD *)v22 + 16) + ((unsigned __int64)v58 << 6));
        if ( v59[14] )
        {
          v36 = v59[15] == 0;
          v60 = v24;
          v59[14] = 0;
          if ( v36 )
            v60 = v13;
          v13 = v60;
          if ( v58 == *((_DWORD *)v91 + 30) )
            *((_DWORD *)v91 + 30) = v24;
          v61 = (unsigned __int64)v24++ << 6;
          SessionStartupCtl::SmilesLinkInfo::Transfer(
            (SessionStartupCtl::SmilesLinkInfo *)&v18[v61],
            (struct SessionStartupCtl::SmilesLinkInfo *)v59);
        }
        else
        {
          if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
          {
            v92 = (const char *)*((_QWORD *)v59 + 6);
            v100 = *((_QWORD *)v59 + 5);
            v99 = (const char *)*((_QWORD *)v59 + 4);
            v103 = (const char *)*((_QWORD *)v59 + 3);
            v102 = (GUID *)*((_QWORD *)v59 + 2);
            v95 = (SessionStartupCtl::SmilesLinkInfo *)*((_QWORD *)v59 + 1);
            v64 = v59[1];
            v94 = (const unsigned __int16 *)v23;
            v89 = v62;
            v93 = 0x1000000;
            v98 = (const unsigned __int16 *)v21[v64];
            v65 = *v59;
            *(_QWORD *)v97 = v63;
            v101 = (const unsigned __int16 *)v21[v65];
            v90 = (struct RdpNanoIceCandidate *)&v116;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              (_DWORD)v20,
              (unsigned int)word_1801D1012,
              (_DWORD)v21,
              (_DWORD)v23,
              (__int64)v97,
              (__int64)&v93,
              (__int64)&v89,
              (__int64)&v94,
              (__int64)&v90,
              (__int64)&v101,
              (__int64)&v98,
              (__int64)&v95,
              (__int64)&v102,
              (__int64)&v103,
              (__int64)&v99,
              (__int64)&v100,
              (__int64)&v92);
          }
          if ( (unsigned int)CallbackContext > 4 )
          {
            v92 = (const char *)*((_QWORD *)v59 + 6);
            v100 = *((_QWORD *)v59 + 5);
            v99 = (const char *)*((_QWORD *)v59 + 4);
            v103 = (const char *)*((_QWORD *)v59 + 3);
            v102 = (GUID *)*((_QWORD *)v59 + 2);
            v95 = (SessionStartupCtl::SmilesLinkInfo *)*((_QWORD *)v59 + 1);
            v98 = (const unsigned __int16 *)*(&off_18016AA80 + v59[1]);
            v101 = (const unsigned __int16 *)*(&off_18016AA80 + *v59);
            v90 = (struct RdpNanoIceCandidate *)"ICE: Smiles Remove Link";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              (unsigned int)&off_18016AA80,
              (unsigned int)&dword_1801D09FC,
              (_DWORD)v21,
              (_DWORD)v23,
              (__int64)&v90,
              (__int64)&v101,
              (__int64)&v98,
              (__int64)&v95,
              (__int64)&v102,
              (__int64)&v103,
              (__int64)&v99,
              (__int64)&v100,
              (__int64)&v92);
          }
        }
        v22 = v91;
        v21 = &off_18016AA80;
        ++v58;
        v23 = "Udp";
      }
      while ( v58 < *((_DWORD *)v91 + 28) );
    }
    if ( *((_DWORD *)v22 + 30) != v13 )
    {
      v36 = *((_DWORD *)v22 + 30) == -1;
      v66 = &byte_1801700E9;
      v67 = &byte_1801700E9;
      v98 = &byte_1801700E9;
      v21 = (char (**)[7])&byte_1801700E9;
      v101 = &byte_1801700E9;
      v23 = (const char *)&byte_1801700E9;
      v104 = &byte_1801700E9;
      v90 = (struct RdpNanoIceCandidate *)&byte_1801700E9;
      v20 = (struct RdpNanoIceCandidate *)&byte_1801700E9;
      v19 = (unsigned __int64)&off_18016AA80;
      if ( v36 )
      {
        v70 = (SessionStartupCtl::SmilesLinkInfo *)&byte_1801700E9;
        *(_QWORD *)v97 = &byte_1801700E9;
        v93 = (__int64)&byte_1801700E9;
        v69 = &byte_1801700E9;
        v89 = &byte_1801700E9;
        v94 = &byte_1801700E9;
      }
      else
      {
        v68 = (unsigned __int64)*((unsigned int *)v22 + 30) << 6;
        v69 = (const unsigned __int16 *)*(&off_18016AA80 + *(unsigned int *)&v18[v68]);
        v70 = (SessionStartupCtl::SmilesLinkInfo *)*(&off_18016AA80 + *(unsigned int *)&v18[v68 + 4]);
        *(_QWORD *)v97 = *(_QWORD *)&v18[v68 + 8];
        v93 = *(_QWORD *)&v18[v68 + 16];
        v89 = *(const unsigned __int16 **)&v18[v68 + 32];
        v71 = *(const unsigned __int16 **)&v18[v68 + 40];
        v20 = (struct RdpNanoIceCandidate *)&byte_1801700E9;
        v94 = v71;
      }
      v95 = v70;
      if ( v13 != -1 )
      {
        v72 = (unsigned __int64)v13 << 6;
        v21 = *(char (***)[7])&v18[v72 + 8];
        v23 = *(const char **)&v18[v72 + 16];
        v73 = *(const unsigned __int16 **)&v18[v72 + 32];
        v66 = (const unsigned __int16 *)*(&off_18016AA80 + *(unsigned int *)&v18[v72]);
        v74 = *(unsigned int *)&v18[v72 + 4];
        v20 = *(struct RdpNanoIceCandidate **)&v18[v72 + 40];
        v98 = (const unsigned __int16 *)v21;
        v101 = (const unsigned __int16 *)v23;
        v67 = (const unsigned __int16 *)*(&off_18016AA80 + v74);
        v104 = v73;
        v90 = v20;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
        {
          v92 = (const char *)v90;
          v106 = (SessionStartupCtl::SmilesLinkInfo *)v94;
          v107 = v89;
          v108 = v93;
          v109 = *(const unsigned __int16 **)v97;
          v112 = &v116;
          v113 = "Udp";
          v114 = "Stack";
          v96 = "Checkpoint";
          v100 = v76;
          v99 = v23;
          v103 = (const char *)v21;
          v102 = (GUID *)v67;
          v105 = v66;
          v110 = v77;
          v111 = v69;
          v115 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v75,
            (unsigned int)byte_1801D1523,
            (_DWORD)v21,
            (_DWORD)v23,
            (__int64)&v96,
            (__int64)&v115,
            (__int64)&v114,
            (__int64)&v113,
            (__int64)&v112,
            (__int64)&v111,
            (__int64)&v110,
            (__int64)&v109,
            (__int64)&v108,
            (__int64)&v107,
            (__int64)&v106,
            (__int64)&v105,
            (__int64)&v102,
            (__int64)&v103,
            (__int64)&v99,
            (__int64)&v100,
            (__int64)&v92);
        }
        v20 = v90;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v115 = (__int64)v104;
        v114 = (const char *)v101;
        v113 = (const char *)v98;
        v110 = v94;
        v109 = v89;
        v108 = v93;
        v107 = *(const unsigned __int16 **)v97;
        v106 = v95;
        v92 = "ICE: Smiles Switch Active Link";
        v96 = (const char *)v20;
        v112 = (GUID *)v67;
        v111 = v66;
        v105 = v69;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v20,
          (unsigned int)&byte_1801CFC5F,
          (_DWORD)v21,
          (_DWORD)v23,
          (__int64)&v92,
          (__int64)&v105,
          (__int64)&v106,
          (__int64)&v107,
          (__int64)&v108,
          (__int64)&v109,
          (__int64)&v110,
          (__int64)&v111,
          (__int64)&v112,
          (__int64)&v113,
          (__int64)&v114,
          (__int64)&v115,
          (__int64)&v96);
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v89) = v88;
      v96 = "ICE: Updated active link type";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v20,
        (unsigned int)byte_1801CFFB1,
        (_DWORD)v21,
        (_DWORD)v23,
        (__int64)&v96,
        (__int64)&v89);
    }
    v78 = v91;
    if ( *((_DWORD *)v91 + 30) == -1 && v13 != -1 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v96 = "ICE: Set first Smiles active Link";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&word_1801D077E,
          0,
          (_DWORD)v23,
          (__int64)&v96);
      }
      v78 = v91;
    }
    v79 = (SessionStartupCtl::SmilesLinkInfo *)*((_QWORD *)v78 + 16);
    if ( v79 )
      SessionStartupCtl::SmilesLinkInfo::`vector deleting destructor'(v79, v19);
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v89) = v24;
      v88 = v13;
      LODWORD(v93) = *((_DWORD *)v91 + 28);
      v97[0] = *((_DWORD *)v91 + 30);
      v96 = "ICE: swap smilesLinkInfo";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v91,
        (unsigned int)&byte_1801D08A7,
        (_DWORD)v21,
        (_DWORD)v23,
        (__int64)&v96,
        (__int64)v97,
        (__int64)&v93,
        (__int64)&v88,
        (__int64)&v89);
    }
    *((_DWORD *)v91 + 30) = v13;
    *((_QWORD *)v91 + 16) = v18;
    *((_DWORD *)v91 + 28) = v24;
    goto LABEL_89;
  }
  while ( 1 )
  {
    v25 = *((_DWORD *)a3 + 17);
    v26 = *((_QWORD *)a3 + 7);
    v27 = v4 == v25;
    LODWORD(v93) = v25;
    v97[0] = v27;
    v28 = *(unsigned int *)(v26 + 16LL * v4);
    if ( (unsigned int)v28 >= *((_DWORD *)a3 + 8) )
      break;
    v19 = *(unsigned int *)(v26 + 16LL * v4 + 4);
    if ( (unsigned int)v19 >= *((_DWORD *)a3 + 12) )
      break;
    v29 = *((_QWORD *)a3 + 3);
    LODWORD(v89) = v13;
    v30 = (unsigned int *)(v29 + 40 * v28);
    v31 = *((_QWORD *)a3 + 5);
    v94 = (const unsigned __int16 *)v30;
    v32 = (struct RdpNanoIceCandidate *)(v31 + 40 * v19);
    v90 = v32;
    if ( v4 == v25 )
    {
      RdpNanoIceCandidateTypeToType(*v30);
      v34 = RdpNanoIceCandidateTypeToType(*v33);
      if ( (_DWORD)v19 == 4 )
        LODWORD(v19) = 2;
      if ( v34 == 4 )
        v34 = 2;
      if ( (unsigned int)v19 > v34 )
        v34 = v19;
      v88 = v34;
    }
    v20 = (struct RdpNanoIceCandidate *)*((_QWORD *)v22 + 16);
    v35 = 0;
    LODWORD(v104) = 0;
    if ( v20 )
    {
      v36 = *((_DWORD *)v22 + 28) == 0;
      if ( !*((_DWORD *)v22 + 28) )
        goto LABEL_33;
      while ( 1 )
      {
        v98 = (const unsigned __int16 *)(v35 << 6);
        v95 = (struct RdpNanoIceCandidate *)((char *)v20 + 64 * v35);
        IsEqual = SessionStartupCtl::SmilesLinkInfo::IsEqual(v95, (const struct RdpNanoIceCandidate *)v30, v32);
        v30 = (unsigned int *)v94;
        v32 = v90;
        if ( IsEqual )
          break;
        v20 = (struct RdpNanoIceCandidate *)*((_QWORD *)v22 + 16);
        v35 = (unsigned int)((_DWORD)v104 + 1);
        LODWORD(v104) = v35;
        if ( (unsigned int)v35 >= *((_DWORD *)v22 + 28) )
        {
          v27 = v97[0];
          goto LABEL_31;
        }
      }
      v27 = v97[0];
      *((_DWORD *)v95 + 14) = 1;
      v20 = (struct RdpNanoIceCandidate *)*((_QWORD *)v91 + 16);
      *(_DWORD *)((char *)v98 + (_QWORD)v20 + 60) = v27;
      v22 = v91;
      LODWORD(v35) = (_DWORD)v104;
LABEL_31:
      v25 = v93;
    }
    v36 = (_DWORD)v35 == *((_DWORD *)v22 + 28);
LABEL_33:
    if ( v36 )
    {
      v13 = v24;
      if ( v4 != v25 )
        v13 = (unsigned int)v89;
      v40 = SessionStartupCtl::SmilesLinkInfo::Set(
              (SessionStartupCtl::SmilesLinkInfo *)&v18[64 * (unsigned __int64)v24],
              (const struct RdpNanoIceCandidate *)v30,
              v32,
              v27);
      if ( v40 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v89) = 739;
          v92 = "OnICEUpdateConnectionType";
          v88 = v40;
          v100 = (__int64)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
          v99 = "Set new links failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)v20,
            (unsigned int)&byte_1801CFD9F,
            v38,
            v39,
            (__int64)&v99,
            (__int64)&v88,
            (__int64)&v100,
            (__int64)&v89,
            (__int64)&v92);
        }
        goto LABEL_58;
      }
      ++v24;
      if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
      {
        v41 = v94;
        v95 = (SessionStartupCtl::SmilesLinkInfo *)*((_QWORD *)v90 + 3);
        v98 = (const unsigned __int16 *)*((_QWORD *)v90 + 1);
        v42 = *(_DWORD *)v90;
        v101 = (const unsigned __int16 *)*((_QWORD *)v90 + 2);
        v94 = (const unsigned __int16 *)*((_QWORD *)v94 + 3);
        v89 = (const unsigned __int16 *)*((_QWORD *)v41 + 1);
        v93 = *((_QWORD *)v41 + 2);
        v43 = RdpNanoIceCandidateTypeToType(v42);
        v44 = *(_DWORD *)v41;
        *(_QWORD *)v97 = *(&off_18016AA80 + v43);
        v45 = RdpNanoIceCandidateTypeToType(v44);
        v100 = 0x1000000;
        v104 = *(const unsigned __int16 **)(v46 + 8LL * v45);
        v102 = &v116;
        v103 = "Udp";
        v99 = "Stack";
        v92 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v47,
          (unsigned int)byte_1801D0481,
          v48,
          v49,
          (__int64)&v92,
          (__int64)&v100,
          (__int64)&v99,
          (__int64)&v103,
          (__int64)&v102,
          (__int64)&v104,
          (__int64)v97,
          (__int64)&v93,
          (__int64)&v89,
          (__int64)&v94,
          (__int64)&v101,
          (__int64)&v98,
          (__int64)&v95);
      }
      else
      {
        v41 = v94;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v92 = (const char *)*((_QWORD *)v90 + 3);
        v100 = *((_QWORD *)v90 + 1);
        v50 = *(_DWORD *)v90;
        v99 = (const char *)*((_QWORD *)v90 + 2);
        v103 = (const char *)*((_QWORD *)v41 + 3);
        v102 = (GUID *)*((_QWORD *)v41 + 1);
        v95 = (SessionStartupCtl::SmilesLinkInfo *)*((_QWORD *)v41 + 2);
        v51 = RdpNanoIceCandidateTypeToType(v50);
        v52 = *(_DWORD *)v41;
        v98 = (const unsigned __int16 *)*(&off_18016AA80 + v51);
        v53 = RdpNanoIceCandidateTypeToType(v52);
        v101 = *(const unsigned __int16 **)(v54 + 8LL * v53);
        v90 = (struct RdpNanoIceCandidate *)"ICE: Smiles Add Link";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v55,
          (unsigned int)byte_1801D1DA5,
          v56,
          v57,
          (__int64)&v90,
          (__int64)&v101,
          (__int64)&v98,
          (__int64)&v95,
          (__int64)&v102,
          (__int64)&v103,
          (__int64)&v99,
          (__int64)&v100,
          (__int64)&v92);
      }
      v22 = v91;
    }
    if ( ++v4 >= *((_DWORD *)a3 + 16) )
    {
      v21 = &off_18016AA80;
      v23 = "Udp";
      goto LABEL_46;
    }
  }
  if ( (unsigned int)CallbackContext > 3 )
  {
    v92 = "Invalid RdpNanoIceConnectionInfo structure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)byte_1801D2EE9,
      0,
      v27,
      (__int64)&v92);
  }
  v40 = 0;
LABEL_58:
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  return v40;
}

```

## disassembly

```asm
0x18012bdc0  mov     [rsp-8+arg_8], rbx
0x18012bdc5  mov     [rsp-8+arg_18], rsi
0x18012bdca  push    rbp
0x18012bdcb  push    r12
0x18012bdcd  push    r13
0x18012bdcf  push    r14
0x18012bdd1  push    r15
0x18012bdd3  lea     rbp, [rsp-90h]
0x18012bddb  sub     rsp, 1C0h
0x18012bde2  mov     rax, cs:__security_cookie
0x18012bde9  xor     rax, rsp
0x18012bdec  mov     [rbp+0B0h+var_30], rax
0x18012bdf3  xor     r13d, r13d
0x18012bdf6  mov     rbx, r8
0x18012bdf9  mov     r14d, edx
0x18012bdfc  mov     rsi, rcx
0x18012bdff  mov     [rbp+0B0h+var_118], r13
0x18012be03  cmp     [rcx+198h], r13d
0x18012be0a  jz      loc_18012CA33
0x18012be10  add     rcx, 1A0h; this
0x18012be17  lea     r8, [rbp+0B0h+var_118]; struct SessionStartupCtl **
0x18012be1b  call    ?Find@SessionCtlBlkManager@@QEAAJIPEAPEAUSessionStartupCtl@@@Z; SessionCtlBlkManager::Find(uint,SessionStartupCtl * *)
0x18012be20  test    eax, eax
0x18012be22  jz      short loc_18012BE78
0x18012be24  mov     eax, cs:CallbackContext
0x18012be2a  cmp     eax, 4
0x18012be2d  jbe     short loc_18012BE6E
0x18012be2f  mov     eax, [rsi+1B4h]
0x18012be35  lea     rdx, byte_1801D0FA9
0x18012be3c  mov     [rbp+0B0h+var_130], eax
0x18012be3f  lea     rax, aIceFindSession; "ICE: find SessionStartupCtl for request"...
0x18012be46  mov     [rbp+0B0h+var_F8], rax
0x18012be4a  lea     rax, [rbp+0B0h+var_130]
0x18012be4e  mov     [rsp+1E0h+var_1B0], rax
0x18012be53  lea     rax, [rbp+0B0h+var_108]
0x18012be57  mov     [rsp+1E0h+var_1B8], rax
0x18012be5c  lea     rax, [rbp+0B0h+var_F8]
0x18012be60  mov     [rsp+1E0h+var_1C0], rax
0x18012be65  mov     dword ptr [rbp+0B0h+var_108], r14d
0x18012be69  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18012be6e  mov     eax, 80004005h
0x18012be73  jmp     loc_18012CABF
0x18012be78  mov     rax, [rbp+0B0h+var_118]
0x18012be7c  lea     rdx, [rbp+0B0h+ActivityId]; ActivityId
0x18012be80  mov     ecx, 4; ControlCode
0x18012be85  movups  xmm0, xmmword ptr [rax+60h]
0x18012be89  movaps  [rbp+0B0h+var_50], xmm0
0x18012be8d  movdqa  xmmword ptr [rbp+0B0h+ActivityId.Data1], xmm0
0x18012be92  call    cs:__imp_EventActivityIdControl
0x18012be98  cmp     [rbx+40h], r13d
0x18012be9c  jbe     loc_18012CA25
0x18012bea2  mov     r14d, [rbx+40h]
0x18012bea6  mov     r12d, 40h ; '@'
0x18012beac  or      r15d, 0FFFFFFFFh
0x18012beb0  mov     [rbp+0B0h+var_130], 7
0x18012beb7  mov     eax, r12d
0x18012beba  mul     r14
0x18012bebd  lea     rcx, [r12-41h]
0x18012bec2  cmovb   rax, rcx
0x18012bec6  add     rax, 8
0x18012beca  cmovb   rax, rcx
0x18012bece  mov     rcx, rax; Size
0x18012bed1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012bed6  test    rax, rax
0x18012bed9  jz      short loc_18012BEF9
0x18012bedb  lea     rsi, [rax+8]
0x18012bedf  mov     [rax], r14
0x18012bee2  mov     rcx, rsi; void *
0x18012bee5  lea     r9, ??0SmilesLinkInfo@SessionStartupCtl@@QEAA@XZ; void *(*)(void *)
0x18012beec  mov     r8d, r14d; unsigned __int64
0x18012beef  mov     edx, r12d; unsigned __int64
0x18012bef2  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18012bef7  jmp     short loc_18012BEFC
0x18012bef9  mov     rsi, r13
0x18012befc  mov     r8d, [rbx+40h]
0x18012bf00  xor     edx, edx; Val
0x18012bf02  shl     r8, 6; Size
0x18012bf06  mov     rcx, rsi; void *
0x18012bf09  call    memset_0
0x18012bf0e  lea     r8, off_18016AA80
0x18012bf15  mov     r14, [rbp+0B0h+var_118]
0x18012bf19  lea     r9, aUdp_0; "Udp"
0x18012bf20  mov     r12d, r13d
0x18012bf23  lea     r10, aStack; "Stack"
0x18012bf2a  lea     r11, aCheckpoint; "Checkpoint"
0x18012bf31  cmp     [rbx+40h], r13d
0x18012bf35  jbe     loc_18012C2D1
0x18012bf3b  mov     r11d, [rbx+44h]
0x18012bf3f  xor     r9d, r9d
0x18012bf42  mov     rcx, [rbx+38h]
0x18012bf46  cmp     r13d, r11d
0x18012bf49  mov     eax, r13d
0x18012bf4c  setz    r9b
0x18012bf50  mov     dword ptr [rbp+0B0h+var_108], r11d
0x18012bf54  add     rax, rax
0x18012bf57  mov     [rbp+0B0h+var_E8], r9d
0x18012bf5b  mov     r8d, [rcx+rax*8]
0x18012bf5f  cmp     r8d, [rbx+20h]
0x18012bf63  jnb     loc_18012C3A3
0x18012bf69  mov     edx, [rcx+rax*8+4]
0x18012bf6d  cmp     edx, [rbx+30h]
0x18012bf70  jnb     loc_18012C3A3
0x18012bf76  mov     rax, [rbx+18h]
0x18012bf7a  lea     rcx, [r8+r8*4]
0x18012bf7e  mov     dword ptr [rbp+0B0h+var_128], r15d
0x18012bf82  lea     r10, [rax+rcx*8]
0x18012bf86  mov     rax, [rbx+28h]
0x18012bf8a  mov     [rbp+0B0h+var_100], r10
0x18012bf8e  lea     rcx, [rdx+rdx*4]
0x18012bf92  lea     r8, [rax+rcx*8]
0x18012bf96  mov     [rbp+0B0h+var_120], r8
0x18012bf9a  cmp     r13d, r11d
0x18012bf9d  jnz     short loc_18012BFCA
0x18012bf9f  mov     ecx, [r10]; unsigned int
0x18012bfa2  call    ?RdpNanoIceCandidateTypeToType@@YAII@Z; RdpNanoIceCandidateTypeToType(uint)
0x18012bfa7  mov     ecx, [r8]; unsigned int
0x18012bfaa  mov     edx, eax
0x18012bfac  call    ?RdpNanoIceCandidateTypeToType@@YAII@Z; RdpNanoIceCandidateTypeToType(uint)
0x18012bfb1  cmp     edx, 4
0x18012bfb4  mov     ecx, 2
0x18012bfb9  cmovz   edx, ecx
0x18012bfbc  cmp     eax, 4
0x18012bfbf  cmovz   eax, ecx
0x18012bfc2  cmp     edx, eax
0x18012bfc4  cmova   eax, edx
0x18012bfc7  mov     [rbp+0B0h+var_130], eax
0x18012bfca  mov     rcx, [r14+80h]
0x18012bfd1  xor     eax, eax
0x18012bfd3  mov     dword ptr [rbp+0B0h+var_B0], eax
0x18012bfd6  test    rcx, rcx
0x18012bfd9  jz      short loc_18012C050
0x18012bfdb  cmp     eax, [r14+70h]
0x18012bfdf  jnb     short loc_18012C054
0x18012bfe1  shl     rax, 6
0x18012bfe5  mov     rdx, r10; struct RdpNanoIceCandidate *
0x18012bfe8  mov     [rbp+0B0h+var_E0], rax
0x18012bfec  add     rax, rcx
0x18012bfef  mov     rcx, rax; this
0x18012bff2  mov     [rbp+0B0h+var_F8], rax
0x18012bff6  call    ?IsEqual@SmilesLinkInfo@SessionStartupCtl@@QEAAHPEBURdpNanoIceCandidate@@0@Z; SessionStartupCtl::SmilesLinkInfo::IsEqual(RdpNanoIceCandidate const *,RdpNanoIceCandidate const *)
0x18012bffb  mov     r10, [rbp+0B0h+var_100]
0x18012bfff  mov     r8, [rbp+0B0h+var_120]; struct RdpNanoIceCandidate *
0x18012c003  test    eax, eax
0x18012c005  jnz     short loc_18012C022
0x18012c007  mov     eax, dword ptr [rbp+0B0h+var_B0]
0x18012c00a  mov     rcx, [r14+80h]
0x18012c011  inc     eax
0x18012c013  mov     dword ptr [rbp+0B0h+var_B0], eax
0x18012c016  cmp     eax, [r14+70h]
0x18012c01a  jb      short loc_18012BFE1
0x18012c01c  mov     r9d, [rbp+0B0h+var_E8]
0x18012c020  jmp     short loc_18012C04C
0x18012c022  mov     rax, [rbp+0B0h+var_F8]
0x18012c026  mov     r9d, [rbp+0B0h+var_E8]; int
0x18012c02a  mov     dword ptr [rax+38h], 1
0x18012c031  mov     rax, [rbp+0B0h+var_118]
0x18012c035  mov     rcx, [rax+80h]
0x18012c03c  mov     rax, [rbp+0B0h+var_E0]
0x18012c040  mov     [rcx+rax+3Ch], r9d
0x18012c045  mov     r14, [rbp+0B0h+var_118]
0x18012c049  mov     eax, dword ptr [rbp+0B0h+var_B0]
0x18012c04c  mov     r11d, dword ptr [rbp+0B0h+var_108]
0x18012c050  cmp     eax, [r14+70h]
0x18012c054  jnz     loc_18012C2A8
0x18012c05a  cmp     r13d, r11d
0x18012c05d  mov     ecx, r12d
0x18012c060  mov     r15d, r12d
0x18012c063  mov     rdx, r10; struct RdpNanoIceCandidate *
0x18012c066  cmovnz  r15d, dword ptr [rbp+0B0h+var_128]
0x18012c06b  shl     rcx, 6
0x18012c06f  add     rcx, rsi; this
0x18012c072  call    ?Set@SmilesLinkInfo@SessionStartupCtl@@QEAAJPEBURdpNanoIceCandidate@@0H@Z; SessionStartupCtl::SmilesLinkInfo::Set(RdpNanoIceCandidate const *,RdpNanoIceCandidate const *,int)
0x18012c077  mov     r14d, eax
0x18012c07a  test    eax, eax
0x18012c07c  mov     eax, cs:CallbackContext
0x18012c082  jnz     loc_18012C333
0x18012c088  inc     r12d
0x18012c08b  cmp     eax, 4
0x18012c08e  jbe     loc_18012C1CB
0x18012c094  mov     rdx, 470000000000h
0x18012c09e  lea     rcx, CallbackContext
0x18012c0a5  call    _tlgKeywordOn
0x18012c0aa  test    al, al
0x18012c0ac  jz      loc_18012C1CB
0x18012c0b2  mov     rcx, [rbp+0B0h+var_120]
0x18012c0b6  mov     r14, [rbp+0B0h+var_100]
0x18012c0ba  mov     rax, [rcx+18h]
0x18012c0be  mov     [rbp+0B0h+var_F8], rax
0x18012c0c2  mov     rax, [rcx+8]
0x18012c0c6  mov     [rbp+0B0h+var_E0], rax
0x18012c0ca  mov     rax, [rcx+10h]
0x18012c0ce  mov     ecx, [rcx]; unsigned int
0x18012c0d0  mov     [rbp+0B0h+var_C8], rax
0x18012c0d4  mov     rax, [r14+18h]
0x18012c0d8  mov     [rbp+0B0h+var_100], rax
0x18012c0dc  mov     rax, [r14+8]
0x18012c0e0  mov     [rbp+0B0h+var_128], rax
0x18012c0e4  mov     rax, [r14+10h]
0x18012c0e8  mov     [rbp+0B0h+var_108], rax
0x18012c0ec  call    ?RdpNanoIceCandidateTypeToType@@YAII@Z; RdpNanoIceCandidateTypeToType(uint)
0x18012c0f1  mov     ecx, [r14]; unsigned int
0x18012c0f4  lea     rdx, off_18016AA80
0x18012c0fb  mov     eax, eax
0x18012c0fd  mov     rax, [rdx+rax*8]
0x18012c101  mov     qword ptr [rbp+0B0h+var_E8], rax
0x18012c105  call    ?RdpNanoIceCandidateTypeToType@@YAII@Z; RdpNanoIceCandidateTypeToType(uint)
0x18012c10a  mov     eax, eax
0x18012c10c  mov     [rbp+0B0h+var_D0], 1000000h
0x18012c114  mov     rax, [rdx+rax*8]
0x18012c118  lea     rdx, byte_1801D0481
0x18012c11f  mov     [rbp+0B0h+var_B0], rax
0x18012c123  lea     rax, [rbp+0B0h+var_50]
0x18012c127  mov     [rbp+0B0h+var_C0], rax
0x18012c12b  lea     rax, aUdp_0; "Udp"
0x18012c132  mov     [rbp+0B0h+var_B8], rax
0x18012c136  lea     rax, aStack; "Stack"
0x18012c13d  mov     [rbp+0B0h+var_D8], rax
0x18012c141  lea     rax, aCheckpoint; "Checkpoint"
0x18012c148  mov     [rbp+0B0h+var_110], rax
0x18012c14c  lea     rax, [rbp+0B0h+var_F8]
0x18012c150  mov     [rsp+1E0h+var_160], rax
0x18012c158  lea     rax, [rbp+0B0h+var_E0]
0x18012c15c  mov     [rsp+1E0h+var_168], rax
0x18012c161  lea     rax, [rbp+0B0h+var_C8]
0x18012c165  mov     [rsp+1E0h+var_170], rax
0x18012c16a  lea     rax, [rbp+0B0h+var_100]
0x18012c16e  mov     [rsp+1E0h+var_178], rax
0x18012c173  lea     rax, [rbp+0B0h+var_128]
0x18012c177  mov     [rsp+1E0h+var_180], rax
0x18012c17c  lea     rax, [rbp+0B0h+var_108]
0x18012c180  mov     [rsp+1E0h+var_188], rax
0x18012c185  lea     rax, [rbp+0B0h+var_E8]
0x18012c189  mov     [rsp+1E0h+var_190], rax
0x18012c18e  lea     rax, [rbp+0B0h+var_B0]
0x18012c192  mov     [rsp+1E0h+var_198], rax
0x18012c197  lea     rax, [rbp+0B0h+var_C0]
0x18012c19b  mov     [rsp+1E0h+var_1A0], rax
0x18012c1a0  lea     rax, [rbp+0B0h+var_B8]
0x18012c1a4  mov     [rsp+1E0h+var_1A8], rax
0x18012c1a9  lea     rax, [rbp+0B0h+var_D8]
0x18012c1ad  mov     [rsp+1E0h+var_1B0], rax
0x18012c1b2  lea     rax, [rbp+0B0h+var_D0]
0x18012c1b6  mov     [rsp+1E0h+var_1B8], rax
0x18012c1bb  lea     rax, [rbp+0B0h+var_110]
0x18012c1bf  mov     [rsp+1E0h+var_1C0], rax
0x18012c1c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@33333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18012c1c9  jmp     short loc_18012C1CF
0x18012c1cb  mov     r14, [rbp+0B0h+var_100]
0x18012c1cf  mov     eax, cs:CallbackContext
0x18012c1d5  cmp     eax, 4
0x18012c1d8  jbe     loc_18012C2A4
0x18012c1de  mov     rcx, [rbp+0B0h+var_120]
0x18012c1e2  mov     rax, [rcx+18h]
0x18012c1e6  mov     [rbp+0B0h+var_110], rax
0x18012c1ea  mov     rax, [rcx+8]
0x18012c1ee  mov     [rbp+0B0h+var_D0], rax
0x18012c1f2  mov     rax, [rcx+10h]
0x18012c1f6  mov     ecx, [rcx]; unsigned int
0x18012c1f8  mov     [rbp+0B0h+var_D8], rax
0x18012c1fc  mov     rax, [r14+18h]
0x18012c200  mov     [rbp+0B0h+var_B8], rax
0x18012c204  mov     rax, [r14+8]
0x18012c208  mov     [rbp+0B0h+var_C0], rax
0x18012c20c  mov     rax, [r14+10h]
0x18012c210  mov     [rbp+0B0h+var_F8], rax
0x18012c214  call    ?RdpNanoIceCandidateTypeToType@@YAII@Z; RdpNanoIceCandidateTypeToType(uint)
0x18012c219  mov     ecx, [r14]; unsigned int
0x18012c21c  lea     rdx, off_18016AA80
0x18012c223  mov     eax, eax
0x18012c225  mov     rax, [rdx+rax*8]
0x18012c229  mov     [rbp+0B0h+var_E0], rax
0x18012c22d  call    ?RdpNanoIceCandidateTypeToType@@YAII@Z; RdpNanoIceCandidateTypeToType(uint)
0x18012c232  mov     eax, eax
0x18012c234  mov     rax, [rdx+rax*8]
0x18012c238  lea     rdx, byte_1801D1DA5
0x18012c23f  mov     [rbp+0B0h+var_C8], rax
0x18012c243  lea     rax, aIceSmilesAddLi; "ICE: Smiles Add Link"
0x18012c24a  mov     [rbp+0B0h+var_120], rax
0x18012c24e  lea     rax, [rbp+0B0h+var_110]
0x18012c252  mov     [rsp+1E0h+var_180], rax
0x18012c257  lea     rax, [rbp+0B0h+var_D0]
0x18012c25b  mov     [rsp+1E0h+var_188], rax
0x18012c260  lea     rax, [rbp+0B0h+var_D8]
0x18012c264  mov     [rsp+1E0h+var_190], rax
0x18012c269  lea     rax, [rbp+0B0h+var_B8]
0x18012c26d  mov     [rsp+1E0h+var_198], rax
0x18012c272  lea     rax, [rbp+0B0h+var_C0]
0x18012c276  mov     [rsp+1E0h+var_1A0], rax
0x18012c27b  lea     rax, [rbp+0B0h+var_F8]
0x18012c27f  mov     [rsp+1E0h+var_1A8], rax
0x18012c284  lea     rax, [rbp+0B0h+var_E0]
0x18012c288  mov     [rsp+1E0h+var_1B0], rax
0x18012c28d  lea     rax, [rbp+0B0h+var_C8]
0x18012c291  mov     [rsp+1E0h+var_1B8], rax
0x18012c296  lea     rax, [rbp+0B0h+var_120]
0x18012c29a  mov     [rsp+1E0h+var_1C0], rax
0x18012c29f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18012c2a4  mov     r14, [rbp+0B0h+var_118]
0x18012c2a8  inc     r13d
0x18012c2ab  cmp     r13d, [rbx+40h]
  ... truncated ...
```

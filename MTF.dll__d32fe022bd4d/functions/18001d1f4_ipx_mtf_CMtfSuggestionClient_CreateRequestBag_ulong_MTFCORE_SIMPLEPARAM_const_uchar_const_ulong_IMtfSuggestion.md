# ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)

- ea: `0x18001d1f4`
- end: `0x18001dbad`
- name: `?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z`
- size: `2489`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, unsigned int, const struct MTFCORE_SIMPLEPARAM *, const unsigned __int8 *, unsigned int, struct IMtfSuggestionCandidatePrimitive *, struct IMtfSuggestionContextProperty *, struct IMtfSuggestionInputQuery *, struct IMtfPropertyBag **)`
- caller_count: `25`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014c90`
- `0x1800150a0`
- `0x180015370`
- `0x180015580`
- `0x180015960`
- `0x180015ce0`
- `0x180015e80`
- `0x180016020`
- `0x180016150`
- `0x180016430`
- `0x180016750`
- `0x180016cf0`
- `0x180017a40`
- `0x1800189d0`
- `0x180019b00`
- `0x18001a150`
- `0x18001a450`
- `0x18001a800`
- `0x18001aa70`
- `0x18001ae00`
- `0x18001b040`
- `0x18001c840`
- `0x18001cae0`
- `0x18001cdd4`
- `0x18001cf68`

## callees

- `0x180001fc4`
- `0x1800046d4`
- `0x180006074`
- `0x180013ad4`
- `0x180016b18`
- `0x18001d1f4`
- `0x18001e068`
- `0x18001e224`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d24d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d24d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(
        ipx::mtf::CMtfSuggestionClient *this,
        unsigned int a2,
        const struct MTFCORE_SIMPLEPARAM *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        struct IMtfSuggestionCandidatePrimitive *a6,
        struct IMtfSuggestionContextProperty *a7,
        struct IMtfSuggestionInputQuery *a8,
        struct IMtfPropertyBag **a9)
{
  ipx::mtf::CMtfSuggestionClient *v11; // rsi
  _DWORD *v12; // rdi
  char v13; // bl
  unsigned __int16 v14; // di
  __int16 v15; // cx
  __int16 CurrentThreadId; // ax
  __int16 v17; // dx
  unsigned __int16 v18; // cx
  char *v19; // r13
  _DWORD *v20; // rax
  int v21; // eax
  __int16 v22; // cx
  int v23; // eax
  int v24; // eax
  const char *v25; // r9
  unsigned int v26; // edi
  struct IMtfPropertyBag *v27; // rcx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  struct IMtfSuggestionCandidatePrimitive *v34; // rbx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  struct IMtfSuggestionInputQuery *v38; // rbx
  int v39; // eax
  int v40; // eax
  struct IMtfPropertyBag *v41; // rcx
  int v42; // eax
  struct IMtfSuggestionInputQuery *v43; // rbx
  int v44; // eax
  struct IMtfPropertyBag *v45; // rcx
  int v46; // eax
  int v47; // [rsp+20h] [rbp-79h]
  _DWORD v48[15]; // [rsp+40h] [rbp-59h] BYREF
  int v49; // [rsp+7Ch] [rbp-1Dh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+3Fh]
  struct IMtfPropertyBag *v51; // [rsp+E0h] [rbp+47h] BYREF
  unsigned int v52; // [rsp+E8h] [rbp+4Fh] BYREF

  v52 = a2;
  v11 = this;
  v12 = (_DWORD *)*((_QWORD *)this + 17);
  v13 = 1;
  if ( v12 )
  {
    v19 = (char *)this + 48;
  }
  else
  {
    v14 = -22277;
    v15 = ipx::mtf::CMtfSuggestionClient::s_dwClientIDCookie;
    if ( !ipx::mtf::CMtfSuggestionClient::s_dwClientIDCookie )
    {
      CurrentThreadId = GetCurrentThreadId();
      v17 = 7149 * CurrentThreadId - 22277;
      if ( 7149 * CurrentThreadId == 22277 )
        v17 = -22277;
      v15 = v17;
    }
    v18 = 7149 * v15 - 22277;
    if ( v18 )
      v14 = v18;
    ipx::mtf::CMtfSuggestionClient::s_dwClientIDCookie = v14;
    v19 = (char *)v11 + 48;
    *((_WORD *)v11 + 28) = v14;
    MtfPlatformTelemetry::InitializingMtfClientId<unsigned long &,unsigned long &,unsigned short &>(
      (char *)v11 + 48,
      (char *)v11 + 52);
    v20 = operator new(0x18u);
    v12 = v20;
    if ( v20 )
    {
      v20[2] = 0;
      *(_QWORD *)v20 = &ipx::mtf::EventReciever::`vftable';
      *((_QWORD *)v20 + 2) = ((unsigned __int64)v11 + 24) & -(__int64)(v11 != 0);
      _InterlockedAdd(&g_cRefDll, 1u);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 8LL))(v20);
    }
    else
    {
      v12 = 0;
    }
    this = (ipx::mtf::CMtfSuggestionClient *)*((_QWORD *)v11 + 17);
    if ( this )
      (*(void (__fastcall **)(ipx::mtf::CMtfSuggestionClient *))(*(_QWORD *)this + 16LL))(this);
    *((_QWORD *)v11 + 17) = v12;
  }
  if ( !*((_QWORD *)v11 + 14) )
  {
    LOBYTE(this) = *((_BYTE *)v11 + 145);
    ipx::mtf::CMtfSuggestionClient::EstablishServerConnectionInternal(this, (char *)v11 + 112);
    v21 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, char *))(**((_QWORD **)v11 + 14) + 24LL))(
            *((_QWORD *)v11 + 14),
            v12,
            v19);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6B3,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v21,
        v47);
  }
  v22 = 17405 * *((_WORD *)v11 + 102) - 24893;
  if ( 17405 * *((_WORD *)v11 + 102) == 24893 )
    v22 = -24893;
  *((_WORD *)v11 + 102) = v22;
  v51 = 0;
  v23 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *))Hooked_CoCreateInstance)(
          &CLSID_MtfPropertyBag,
          0,
          1,
          &GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5);
  if ( v23 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x849,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v23,
      (int)&v51);
  v24 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, unsigned int *, __int64))(*(_QWORD *)v51 + 24LL))(
          v51,
          &GUID_MTFCORE_VERB,
          &v52,
          4);
  v26 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84B,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v24,
      (int)&v51);
    v27 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return v26;
  }
  if ( v52 <= 0xF )
  {
    if ( v52 != 15 )
    {
      if ( v52 <= 8 )
      {
        switch ( v52 )
        {
          case 8u:
            goto LABEL_35;
          case 1u:
            if ( !a3 && !a4 && !a5 && !a6 && !a8 )
              v13 = 0;
            if ( v13 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x8AF,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                v25);
            if ( !a7 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x8B1,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                v25);
            v32 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *))(*(_QWORD *)v51 + 48LL))(
                    v51,
                    &GUID_MTFCORE_CONTEXTPROP);
            if ( v32 < 0 )
              wil::details::in1diag3::_FailFast_Hr(
                retaddr,
                (void *)0x8B3,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                (const char *)(unsigned int)v32,
                (int)&v51);
            goto LABEL_134;
          case 2u:
            goto LABEL_35;
          case 3u:
            if ( !a6 && !a7 && !a8 )
              v13 = 0;
            if ( v13 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x886,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                v25);
            if ( !a3 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x888,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                v25);
            v30 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, const struct MTFCORE_SIMPLEPARAM *, __int64))(*(_QWORD *)v51 + 24LL))(
                    v51,
                    &GUID_MTFCORE_SIMPLEPARAM,
                    a3,
                    24);
            if ( v30 < 0 )
              wil::details::in1diag3::_FailFast_Hr(
                retaddr,
                (void *)0x88A,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                (const char *)(unsigned int)v30,
                (int)&v51);
            v31 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, const unsigned __int8 *, _QWORD))(*(_QWORD *)v51 + 24LL))(
                    v51,
                    &GUID_MTFCORE_CUSTOMDATA,
                    a4,
                    a5);
            if ( v31 < 0 )
              wil::details::in1diag3::_FailFast_Hr(
                retaddr,
                (void *)0x88E,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                (const char *)(unsigned int)v31,
                (int)&v51);
            goto LABEL_134;
        }
        if ( v52 != 4 )
        {
          if ( v52 != 5 && v52 != 6 )
          {
            if ( v52 == 7 )
              goto LABEL_35;
LABEL_141:
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x8E3,
              (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
              v25);
          }
LABEL_86:
          if ( !a7 && !a8 )
            v13 = 0;
          if ( v13 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x898,
              (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
              v25);
          v34 = a6;
          if ( !a6 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x89A,
              (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
              v25);
          v35 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, const struct MTFCORE_SIMPLEPARAM *, __int64))(*(_QWORD *)v51 + 24LL))(
                  v51,
                  &GUID_MTFCORE_SIMPLEPARAM,
                  a3,
                  24);
          if ( v35 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x89C,
              (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
              (const char *)(unsigned int)v35,
              (int)&v51);
          v36 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v51 + 48LL))(
                  v51,
                  &GUID_MTFCORE_PRIMITIVE,
                  v34);
          if ( v36 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x89E,
              (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
              (const char *)(unsigned int)v36,
              (int)&v51);
          if ( a4 )
          {
            if ( a5 )
            {
              v37 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, const unsigned __int8 *))(*(_QWORD *)v51 + 24LL))(
                      v51,
                      &GUID_MTFCORE_CUSTOMDATA,
                      a4);
              if ( v37 < 0 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0x8A4,
                  (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                  (const char *)(unsigned int)v37,
                  (int)&v51);
            }
          }
          goto LABEL_134;
        }
        goto LABEL_121;
      }
      if ( v52 == 9 )
      {
LABEL_70:
        if ( !a3 && !a4 && !a5 && !a7 && !a8 )
          v13 = 0;
        if ( v13 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x866,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            v25);
        if ( !a6 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x868,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            v25);
        v33 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *))(*(_QWORD *)v51 + 48LL))(
                v51,
                &GUID_MTFCORE_PRIMITIVE);
        if ( v33 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x86A,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v33,
            (int)&v51);
        goto LABEL_134;
      }
      if ( v52 != 10 )
      {
        if ( v52 == 11 || v52 == 12 )
          goto LABEL_141;
        if ( v52 != 13 )
        {
          if ( v52 != 14 )
            goto LABEL_141;
          goto LABEL_70;
        }
LABEL_121:
        if ( !a3 && !a4 && !a5 && !a6 && !a7 )
          v13 = 0;
        if ( v13 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x8BF,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            v25);
        v43 = a8;
        if ( !a8 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x8C1,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            v25);
        v48[0] = 4096;
        v49 = *((unsigned __int16 *)v11 + 102);
        v44 = (*(__int64 (__fastcall **)(struct IMtfSuggestionInputQuery *, _DWORD *))(*(_QWORD *)a8 + 32LL))(a8, v48);
        v26 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8C6,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v44,
            (int)&v51);
          v45 = v51;
          if ( v51 )
          {
            v51 = 0;
            (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v45 + 16LL))(v45);
          }
          return v26;
        }
        v46 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, struct IMtfSuggestionInputQuery *))(*(_QWORD *)v51 + 48LL))(
                v51,
                &GUID_MTFCORE_INPUTQUERY,
                v43);
        if ( v46 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x8C8,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v46,
            (int)&v51);
        goto LABEL_134;
      }
    }
LABEL_112:
    if ( !a3 && !a4 && !a5 && !a6 && !a7 && !a8 )
      v13 = 0;
    if ( v13 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x85B,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        v25);
    goto LABEL_134;
  }
  if ( v52 <= 0x17 )
  {
    if ( v52 != 23 )
    {
      if ( v52 == 16 || v52 == 17 )
        goto LABEL_86;
      if ( v52 != 18 )
        goto LABEL_141;
    }
    goto LABEL_35;
  }
  switch ( v52 )
  {
    case 0x18u:
      goto LABEL_141;
    case 0x19u:
      goto LABEL_121;
    case 0x1Au:
      goto LABEL_35;
    case 0x1Bu:
      goto LABEL_112;
    case 0x1Cu:
LABEL_35:
      if ( !a4 && !a5 && !a6 && !a7 && !a8 )
        v13 = 0;
      if ( v13 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x87A,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          v25);
      if ( !a3 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x87C,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          v25);
      v29 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, const struct MTFCORE_SIMPLEPARAM *, __int64))(*(_QWORD *)v51 + 24LL))(
              v51,
              &GUID_MTFCORE_SIMPLEPARAM,
              a3,
              24);
      if ( v29 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x87E,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v29,
          (int)&v51);
      goto LABEL_134;
  }
  if ( v52 != 29 )
    goto LABEL_141;
  if ( !a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x8CC,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      v25);
  v38 = a8;
  if ( !a8 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x8CD,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      v25);
  v39 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, const struct MTFCORE_SIMPLEPARAM *, __int64))(*(_QWORD *)v51 + 24LL))(
          v51,
          &GUID_MTFCORE_SIMPLEPARAM,
          a3,
          24);
  if ( v39 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x8D0,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v39,
      (int)&v51);
  v48[0] = 4096;
  v49 = *((unsigned __int16 *)v11 + 102);
  v40 = (*(__int64 (__fastcall **)(struct IMtfSuggestionInputQuery *, _DWORD *))(*(_QWORD *)v38 + 32LL))(v38, v48);
  v26 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D5,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v40,
      (int)&v51);
    v41 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    return v26;
  }
  v42 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, struct IMtfSuggestionInputQuery *))(*(_QWORD *)v51 + 48LL))(
          v51,
          &GUID_MTFCORE_INPUTQUERY,
          v38);
  if ( v42 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x8D8,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v42,
      (int)&v51);
LABEL_134:
  *a9 = v51;
  return 0;
}

```

## disassembly

```asm
0x18001d1f4  mov     [rsp-8+arg_10], rbx
0x18001d1f9  mov     [rsp-8+arg_8], edx
0x18001d1fd  push    rbp
0x18001d1fe  push    rsi
0x18001d1ff  push    rdi
0x18001d200  push    r12
0x18001d202  push    r13
0x18001d204  push    r14
0x18001d206  push    r15
0x18001d208  lea     rbp, [rsp-7]
0x18001d20d  sub     rsp, 0A0h
0x18001d214  mov     r15, r9
0x18001d217  mov     r14, r8
0x18001d21a  mov     rsi, rcx
0x18001d21d  mov     rdi, [rcx+88h]
0x18001d224  mov     ebx, 1
0x18001d229  test    rdi, rdi
0x18001d22c  jnz     loc_18001D312
0x18001d232  mov     edi, 0A8FBh
0x18001d237  mov     r12d, 1BEDh
0x18001d23d  mov     r13d, 5705h
0x18001d243  mov     ecx, cs:?s_dwClientIDCookie@CMtfSuggestionClient@mtf@ipx@@1KA; ulong ipx::mtf::CMtfSuggestionClient::s_dwClientIDCookie
0x18001d249  test    ecx, ecx
0x18001d24b  jnz     short loc_18001D266
0x18001d24d  call    cs:__imp_GetCurrentThreadId
0x18001d253  movzx   edx, ax
0x18001d256  imul    edx, r12d
0x18001d25a  sub     dx, r13w
0x18001d25e  jnz     short loc_18001D263
0x18001d260  movzx   edx, di
0x18001d263  movzx   ecx, dx
0x18001d266  movzx   ecx, cx
0x18001d269  imul    ecx, r12d
0x18001d26d  sub     cx, r13w
0x18001d271  jz      short loc_18001D276
0x18001d273  movzx   edi, cx
0x18001d276  movzx   eax, di
0x18001d279  mov     cs:?s_dwClientIDCookie@CMtfSuggestionClient@mtf@ipx@@1KA, eax; ulong ipx::mtf::CMtfSuggestionClient::s_dwClientIDCookie
0x18001d27f  lea     r13, [rsi+30h]
0x18001d283  lea     r8, [r13+8]
0x18001d287  mov     [r8], di
0x18001d28b  lea     rdx, [r13+4]
0x18001d28f  mov     rcx, r13
0x18001d292  call    ??$InitializingMtfClientId@AEAKAEAKAEAG@MtfPlatformTelemetry@@SAXAEAK0AEAG@Z; MtfPlatformTelemetry::InitializingMtfClientId<ulong &,ulong &,ushort &>(ulong &,ulong &,ushort &)
0x18001d297  mov     ecx, 18h; Size
0x18001d29c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d2a1  mov     rdi, rax
0x18001d2a4  mov     [rbp+37h+var_A0], rax
0x18001d2a8  test    rax, rax
0x18001d2ab  jz      short loc_18001D2EF
0x18001d2ad  mov     dword ptr [rax+8], 0
0x18001d2b4  lea     rax, ??_7EventReciever@mtf@ipx@@6B@; const ipx::mtf::EventReciever::`vftable'
0x18001d2bb  mov     [rdi], rax
0x18001d2be  mov     rax, rsi
0x18001d2c1  lea     rdx, [rsi+18h]
0x18001d2c5  neg     rax
0x18001d2c8  sbb     rcx, rcx
0x18001d2cb  and     rcx, rdx
0x18001d2ce  mov     [rdi+10h], rcx
0x18001d2d2  lock add cs:?g_cRefDll@@3JA, ebx; long g_cRefDll
0x18001d2d9  test    rdi, rdi
0x18001d2dc  jz      short loc_18001D2F1
0x18001d2de  mov     rax, [rdi]
0x18001d2e1  mov     rcx, rdi
0x18001d2e4  mov     rax, [rax+8]
0x18001d2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ed  jmp     short loc_18001D2F1
0x18001d2ef  xor     edi, edi
0x18001d2f1  mov     rcx, [rsi+88h]
0x18001d2f8  test    rcx, rcx
0x18001d2fb  jz      short loc_18001D309
0x18001d2fd  mov     rax, [rcx]
0x18001d300  mov     rax, [rax+10h]
0x18001d304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d309  mov     [rsi+88h], rdi
0x18001d310  jmp     short loc_18001D316
0x18001d312  lea     r13, [rcx+30h]
0x18001d316  lea     r12, [rsi+70h]
0x18001d31a  cmp     qword ptr [r12], 0
0x18001d31f  jnz     short loc_18001D356
0x18001d321  mov     rdx, r12
0x18001d324  mov     cl, [rsi+91h]
0x18001d32a  call    ?EstablishServerConnectionInternal@CMtfSuggestionClient@mtf@ipx@@KAXW4MTFServerConnection@23@PEAPEAUIMtfTransportServer@@@Z; ipx::mtf::CMtfSuggestionClient::EstablishServerConnectionInternal(ipx::mtf::MTFServerConnection,IMtfTransportServer * *)
0x18001d32f  mov     rcx, [r12]
0x18001d333  mov     rax, [rcx]
0x18001d336  mov     r8, r13
0x18001d339  mov     rdx, rdi
0x18001d33c  mov     rax, [rax+18h]
0x18001d340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d345  mov     rcx, [rbp+3Fh]; this
0x18001d349  xor     r12d, r12d
0x18001d34c  test    eax, eax
0x18001d34e  js      loc_18001D985
0x18001d354  jmp     short loc_18001D359
0x18001d356  xor     r12d, r12d
0x18001d359  mov     eax, 43FDh
0x18001d35e  movzx   ecx, word ptr [rsi+0CCh]
0x18001d365  imul    ecx, eax
0x18001d368  mov     eax, 613Dh
0x18001d36d  sub     cx, ax
0x18001d370  jnz     short loc_18001D377
0x18001d372  mov     ecx, 9EC3h
0x18001d377  mov     [rsi+0CCh], cx
0x18001d37e  mov     [rbp+37h+arg_0], r12
0x18001d382  lea     rax, [rbp+37h+arg_0]
0x18001d386  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18001d38b  lea     r9, _GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5
0x18001d392  mov     r8d, ebx
0x18001d395  xor     edx, edx
0x18001d397  lea     rcx, CLSID_MtfPropertyBag
0x18001d39e  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18001d3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3aa  mov     rcx, [rbp+3Fh]; this
0x18001d3ae  test    eax, eax
0x18001d3b0  js      loc_18001DA48
0x18001d3b6  mov     rcx, [rbp+37h+arg_0]
0x18001d3ba  mov     rax, [rcx]
0x18001d3bd  mov     r9d, 4
0x18001d3c3  lea     r8, [rbp+37h+arg_8]
0x18001d3c7  lea     rdx, GUID_MTFCORE_VERB
0x18001d3ce  mov     rax, [rax+18h]
0x18001d3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3d7  mov     edi, eax
0x18001d3d9  test    eax, eax
0x18001d3db  jns     short loc_18001D42D
0x18001d3dd  mov     rcx, [rbp+3Fh]; this
0x18001d3e1  mov     r9d, eax; char *
0x18001d3e4  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001d3eb  mov     edx, 84Bh; void *
0x18001d3f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3f5  nop
0x18001d3f6  mov     rcx, [rbp+37h+arg_0]
0x18001d3fa  test    rcx, rcx
0x18001d3fd  jz      short loc_18001D410
0x18001d3ff  mov     [rbp+37h+arg_0], r12
0x18001d403  mov     rax, [rcx]
0x18001d406  mov     rax, [rax+10h]
0x18001d40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d40f  nop
0x18001d410  mov     eax, edi
0x18001d412  mov     rbx, [rsp+0D0h+arg_10]
0x18001d41a  add     rsp, 0A0h
0x18001d421  pop     r15
0x18001d423  pop     r14
0x18001d425  pop     r13
0x18001d427  pop     r12
0x18001d429  pop     rdi
0x18001d42a  pop     rsi
0x18001d42b  pop     rbp
0x18001d42c  retn
0x18001d42d  mov     eax, [rbp+37h+arg_8]
0x18001d430  cmp     eax, 0Fh
0x18001d433  ja      loc_18001D672
0x18001d439  jz      loc_18001D865
0x18001d43f  cmp     eax, 8
0x18001d442  ja      loc_18001D5DC
0x18001d448  jz      short loc_18001D485
0x18001d44a  sub     eax, 1
0x18001d44d  jz      loc_18001D578
0x18001d453  sub     eax, 1
0x18001d456  jz      short loc_18001D485
0x18001d458  sub     eax, 1
0x18001d45b  jz      loc_18001D4EF
0x18001d461  sub     eax, 1
0x18001d464  jz      loc_18001D89B
0x18001d46a  sub     eax, 1
0x18001d46d  jz      loc_18001D699
0x18001d473  sub     eax, 1
0x18001d476  jz      loc_18001D699
0x18001d47c  cmp     eax, 1
0x18001d47f  jnz     loc_18001D9F6
0x18001d485  test    r15, r15
0x18001d488  jnz     short loc_18001D4A5
0x18001d48a  cmp     [rbp+37h+arg_20], r12d
0x18001d48e  jnz     short loc_18001D4A5
0x18001d490  cmp     [rbp+37h+arg_28], r12
0x18001d494  jnz     short loc_18001D4A5
0x18001d496  cmp     [rbp+37h+arg_30], r12
0x18001d49a  jnz     short loc_18001D4A5
0x18001d49c  cmp     [rbp+37h+arg_38], r12
0x18001d4a0  jnz     short loc_18001D4A5
0x18001d4a2  mov     bl, r12b
0x18001d4a5  mov     rcx, [rbp+3Fh]; this
0x18001d4a9  test    bl, bl
0x18001d4ab  jnz     loc_18001DB65
0x18001d4b1  mov     rcx, [rbp+3Fh]; this
0x18001d4b5  test    r14, r14
0x18001d4b8  jz      loc_18001DB77
0x18001d4be  mov     rcx, [rbp+37h+arg_0]
0x18001d4c2  mov     rax, [rcx]
0x18001d4c5  mov     r9d, 18h
0x18001d4cb  mov     r8, r14
0x18001d4ce  lea     rdx, GUID_MTFCORE_SIMPLEPARAM
0x18001d4d5  mov     rax, [rax+18h]
0x18001d4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4de  mov     rcx, [rbp+3Fh]; this
0x18001d4e2  test    eax, eax
0x18001d4e4  js      loc_18001D99A
0x18001d4ea  jmp     loc_18001D95B
0x18001d4ef  cmp     [rbp+37h+arg_28], r12
0x18001d4f3  jnz     short loc_18001D504
0x18001d4f5  cmp     [rbp+37h+arg_30], r12
0x18001d4f9  jnz     short loc_18001D504
0x18001d4fb  cmp     [rbp+37h+arg_38], r12
0x18001d4ff  jnz     short loc_18001D504
0x18001d501  mov     bl, r12b
0x18001d504  mov     rcx, [rbp+3Fh]; this
0x18001d508  test    bl, bl
0x18001d50a  jnz     loc_18001DA5D
0x18001d510  mov     rcx, [rbp+3Fh]; this
0x18001d514  test    r14, r14
0x18001d517  jz      loc_18001DA6F
0x18001d51d  mov     rcx, [rbp+37h+arg_0]
0x18001d521  mov     rax, [rcx]
0x18001d524  mov     r9d, 18h
0x18001d52a  mov     r8, r14
0x18001d52d  lea     rdx, GUID_MTFCORE_SIMPLEPARAM
0x18001d534  mov     rax, [rax+18h]
0x18001d538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d53d  mov     rcx, [rbp+3Fh]; this
0x18001d541  test    eax, eax
0x18001d543  js      loc_18001DA81
0x18001d549  mov     rcx, [rbp+37h+arg_0]
0x18001d54d  mov     rax, [rcx]
0x18001d550  mov     r9d, [rbp+37h+arg_20]
0x18001d554  mov     r8, r15
0x18001d557  lea     rdx, GUID_MTFCORE_CUSTOMDATA
0x18001d55e  mov     rax, [rax+18h]
0x18001d562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d567  mov     rcx, [rbp+3Fh]; this
0x18001d56b  test    eax, eax
0x18001d56d  js      loc_18001D9AF
0x18001d573  jmp     loc_18001D95B
0x18001d578  test    r14, r14
0x18001d57b  jnz     short loc_18001D597
0x18001d57d  test    r15, r15
0x18001d580  jnz     short loc_18001D597
0x18001d582  cmp     [rbp+37h+arg_20], r12d
0x18001d586  jnz     short loc_18001D597
0x18001d588  cmp     [rbp+37h+arg_28], r12
0x18001d58c  jnz     short loc_18001D597
0x18001d58e  cmp     [rbp+37h+arg_38], r12
0x18001d592  jnz     short loc_18001D597
0x18001d594  mov     bl, r12b
0x18001d597  mov     rcx, [rbp+3Fh]; this
0x18001d59b  test    bl, bl
0x18001d59d  jnz     loc_18001DA96
0x18001d5a3  mov     rcx, [rbp+3Fh]; this
0x18001d5a7  mov     r8, [rbp+37h+arg_30]
0x18001d5ab  test    r8, r8
0x18001d5ae  jz      loc_18001DAA8
0x18001d5b4  mov     rcx, [rbp+37h+arg_0]
0x18001d5b8  mov     rax, [rcx]
0x18001d5bb  lea     rdx, GUID_MTFCORE_CONTEXTPROP
0x18001d5c2  mov     rax, [rax+30h]
0x18001d5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5cb  mov     rcx, [rbp+3Fh]; this
0x18001d5cf  test    eax, eax
0x18001d5d1  js      loc_18001D9C4
0x18001d5d7  jmp     loc_18001D95B
0x18001d5dc  sub     eax, 9
0x18001d5df  jz      short loc_18001D60E
0x18001d5e1  sub     eax, 1
0x18001d5e4  jz      loc_18001D865
0x18001d5ea  sub     eax, 1
0x18001d5ed  jz      loc_18001D9F6
0x18001d5f3  sub     eax, 1
0x18001d5f6  jz      loc_18001D9F6
0x18001d5fc  sub     eax, 1
0x18001d5ff  jz      loc_18001D89B
0x18001d605  cmp     eax, 1
0x18001d608  jnz     loc_18001D9F6
0x18001d60e  test    r14, r14
0x18001d611  jnz     short loc_18001D62D
0x18001d613  test    r15, r15
0x18001d616  jnz     short loc_18001D62D
0x18001d618  cmp     [rbp+37h+arg_20], r12d
0x18001d61c  jnz     short loc_18001D62D
0x18001d61e  cmp     [rbp+37h+arg_30], r12
0x18001d622  jnz     short loc_18001D62D
0x18001d624  cmp     [rbp+37h+arg_38], r12
0x18001d628  jnz     short loc_18001D62D
0x18001d62a  mov     bl, r12b
0x18001d62d  mov     rcx, [rbp+3Fh]; this
0x18001d631  test    bl, bl
0x18001d633  jnz     loc_18001DABA
0x18001d639  mov     rcx, [rbp+3Fh]; this
0x18001d63d  mov     r8, [rbp+37h+arg_28]
0x18001d641  test    r8, r8
0x18001d644  jz      loc_18001DACC
0x18001d64a  mov     rcx, [rbp+37h+arg_0]
0x18001d64e  mov     rax, [rcx]
0x18001d651  lea     rdx, GUID_MTFCORE_PRIMITIVE
0x18001d658  mov     rax, [rax+30h]
0x18001d65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d661  mov     rcx, [rbp+3Fh]; this
0x18001d665  test    eax, eax
0x18001d667  js      loc_18001D9D9
0x18001d66d  jmp     loc_18001D95B
0x18001d672  cmp     eax, 17h
  ... truncated ...
```

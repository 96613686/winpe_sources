# HyperVStorage::ReadFromStream(ISequentialStream *,int,ushort const *)

- ea: `0x140084fe4`
- end: `0x1400858dc`
- name: `?ReadFromStream@HyperVStorage@@QEAAJPEAUISequentialStream@@HPEBG@Z`
- size: `2296`
- prototype: `__int64 __fastcall(HyperVStorage *this, IUnknown *pInputStream, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401ea610`
- `0x1401ea750`

## callees

- `0x140023e30`
- `0x1400261dc`
- `0x1400287a8`
- `0x14002ed00`
- `0x140031c88`
- `0x140036d94`
- `0x140037478`
- `0x140038e4c`
- `0x14003bb08`
- `0x140044054`
- `0x140044b40`
- `0x140046528`
- `0x14004b0ac`
- `0x140050708`
- `0x1400511f4`
- `0x140056500`
- `0x140056ae0`
- `0x140059920`
- `0x14005e7e4`
- `0x140084714`
- `0x140084fe4`
- `0x1400b9ba4`
- `0x1400da390`
- `0x1400db248`
- `0x140132940`
- `0x140133bec`
- `0x140133c54`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008569f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008569f`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1400855e8`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1400855e8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085568`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400855a8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085663`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085568`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400855a8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085663`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x140085092`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x140085092`
- `XmlLite!CreateXmlReader` at `0x140085048`
- `XmlLite!CreateXmlReader` at `0x140085048`

## pseudocode

```c
__int64 __fastcall HyperVStorage::ReadFromStream(
        HyperVStorage *this,
        IUnknown *pInputStream,
        int a3,
        unsigned __int16 *a4)
{
  HRESULT v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // edi
  HyperVStorageOperation *v13; // r13
  char *v14; // r14
  int v16; // eax
  int v17; // eax
  int v18; // eax
  HyperVStorage *v19; // rcx
  int v20; // edi
  HyperVStorage *v21; // rcx
  wchar_t **v22; // rax
  const WCHAR *v23; // rcx
  bool v24; // zf
  unsigned int FixedTypeDataSpace; // esi
  HyperVStorageKeyTableEntry *v26; // r12
  const char *Name; // rax
  __int64 v28; // r8
  const wchar_t *v29; // rcx
  __int64 *p_Src; // rax
  const wchar_t *v31; // rcx
  const wchar_t *v32; // rcx
  const wchar_t *v33; // rcx
  wchar_t **v34; // rdx
  int IsDebugTraceEnabled; // esi
  unsigned __int64 v36; // rdx
  unsigned __int8 v37; // cl
  bool IsEnabled; // al
  char v39; // di
  __int128 *v40; // r9
  LPCWCH *v41; // r8
  wchar_t **v42; // rax
  unsigned __int16 *v43; // rsi
  unsigned int v44; // r12d
  LPCWSTR pwszBaseUri; // [rsp+20h] [rbp-188h]
  int v47; // [rsp+30h] [rbp-178h]
  unsigned int v48; // [rsp+40h] [rbp-168h] BYREF
  int v49; // [rsp+44h] [rbp-164h] BYREF
  int v50; // [rsp+48h] [rbp-160h]
  HyperVStorage *v51; // [rsp+50h] [rbp-158h]
  unsigned __int16 *v52; // [rsp+58h] [rbp-150h]
  HyperVStorageOperation *v53; // [rsp+60h] [rbp-148h]
  unsigned __int16 *v54; // [rsp+68h] [rbp-140h]
  struct _GUID v55; // [rsp+70h] [rbp-138h] BYREF
  _BYTE v56[8]; // [rsp+80h] [rbp-128h] BYREF
  void *v57; // [rsp+88h] [rbp-120h] BYREF
  HyperVStorage *v58; // [rsp+90h] [rbp-118h] BYREF
  void *ppvObject; // [rsp+98h] [rbp-110h] BYREF
  wchar_t *String[2]; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-F8h]
  unsigned __int64 v62; // [rsp+B8h] [rbp-F0h]
  int v63; // [rsp+C0h] [rbp-E8h] BYREF
  int v64; // [rsp+C4h] [rbp-E4h] BYREF
  __int64 Src; // [rsp+C8h] [rbp-E0h] BYREF
  IXmlReaderInput *ppInput; // [rsp+D0h] [rbp-D8h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-D0h] BYREF
  double v68; // [rsp+E0h] [rbp-C8h] BYREF
  LPCWCH lpWideCharStr[2]; // [rsp+E8h] [rbp-C0h] BYREF
  int cchWideChar[4]; // [rsp+F8h] [rbp-B0h]
  __int128 v71; // [rsp+108h] [rbp-A0h] BYREF
  __m128i v72; // [rsp+118h] [rbp-90h]
  __int128 v73; // [rsp+128h] [rbp-80h] BYREF
  __int64 v74; // [rsp+138h] [rbp-70h]
  __int128 v75; // [rsp+140h] [rbp-68h] BYREF
  __m128i si128; // [rsp+150h] [rbp-58h]

  v52 = a4;
  v51 = this;
  v54 = a4;
  v50 = 0;
  ppvObject = 0;
  v8 = CreateXmlReader(&stru_1402E8610, &ppvObject, 0);
  try
  {
    if ( v8 < 0 )
      HvsThrowHResultError(v8);
    ppInput = 0;
    v9 = CreateXmlReaderInputWithEncodingName(
           pInputStream,
           0,
           L"UTF-16",
           1,
           &HyperVStorage::CFG_XML_NAMESPACE_URI,
           &ppInput);
    if ( v9 < 0 )
      HvsThrowHResultError(v9);
    v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(
            ppvObject,
            1,
            (a3 != 0) + 1LL);
    if ( v10 < 0 )
      HvsThrowHResultError(v10);
    v11 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
    if ( v11 < 0 )
      HvsThrowHResultError(v11);
    v12 = 1;
    v49 = 1;
    *(_OWORD *)String = 0;
    v61 = 0;
    v62 = 7;
    LOWORD(String[0]) = 0;
    v64 = 0;
    v67 = 0;
    Src = 0;
    v68 = 0.0;
    v63 = 0;
    v48 = 0;
    v75 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v75) = 0;
    v73 = 0;
    v74 = 0;
    *(_OWORD *)lpWideCharStr = 0;
    *(__m128i *)cchWideChar = si128;
    LOWORD(lpWideCharStr[0]) = 0;
    v71 = 0;
    v72 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v71) = 0;
    LODWORD(v57) = 1;
    v58 = this;
    std::vector<HyperVStorageOperation>::emplace_back<HyperVStorage *,enum HyperVStorageOperationType>(
      (char *)this + 184,
      &v58,
      &v57);
    v13 = (HyperVStorageOperation *)(*((_QWORD *)this + 24) - 88LL);
    v53 = v13;
    v14 = (char *)this + 248;
    if ( a4 )
    {
      v57 = 0;
      if ( !(unsigned int)HyperVStorage::GetOrCreateNode(this, a4, v13, &v57, 0) )
        HvsThrowHResultError(-2147467259);
      v14 = (char *)*((_QWORD *)v57 + 5);
    }
    try
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v16 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v64);
          if ( v16 )
            goto LABEL_102;
          if ( v64 != 1 )
            break;
          v58 = 0;
          v18 = (*(__int64 (__fastcall **)(void *, HyperVStorage **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &v58,
                  0);
          if ( v18 < 0 )
            HvsThrowHResultError(v18);
          std::wstring::assign(lpWideCharStr, v58);
          HyperVStorage::ReadAttributes(v19, (struct IXmlReader *)ppvObject, (enum HyperVStorageKeyType *)&v49);
          v20 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
          HyperVStorage::ReadAttributes(v21, (struct IXmlReader *)ppvObject, (enum HyperVStorageKeyType *)&v49);
          v61 = 0;
          v22 = String;
          if ( v62 > 7 )
            v22 = (wchar_t **)String[0];
          *(_WORD *)v22 = 0;
          v23 = (const WCHAR *)lpWideCharStr;
          if ( *(_QWORD *)&cchWideChar[2] > 7u )
            v23 = lpWideCharStr[0];
          HvsWideToMultiByte(v23, cchWideChar[0]);
          LOBYTE(v47) = 0;
          v14 = *(char **)(*(_QWORD *)(*(__int64 (__fastcall **)(HyperVStorage *, _BYTE *, char *, __int128 *, HyperVStorageOperation *, _DWORD, int))(*(_QWORD *)this + 168LL))(
                                        this,
                                        v56,
                                        v14,
                                        &v71,
                                        v13,
                                        0,
                                        v47)
                         + 40LL);
          v24 = v20 == 0;
          v12 = v49;
          if ( !v24 )
          {
LABEL_32:
            if ( v61 )
            {
              if ( v12 == 1 )
                v12 = 6;
            }
            else if ( v12 - 6 > 1 )
            {
              goto LABEL_74;
            }
            if ( v12 == 6 )
            {
              FixedTypeDataSpace = 2 * v61;
              v48 = 2 * v61;
            }
            else if ( v12 == 7 )
            {
              if ( v61 )
              {
                HyperVStorage::ConvertArrayDataFromString(v61, String, &v73, &v48);
                FixedTypeDataSpace = v48;
              }
              else
              {
                FixedTypeDataSpace = 0;
                v48 = 0;
              }
            }
            else
            {
              FixedTypeDataSpace = HyperVStorageKeyTableEntry::GetFixedTypeDataSpace(v12);
              v48 = FixedTypeDataSpace;
            }
            LODWORD(v57) = HyperVStorageKeyTableEntry::GetRequiredSpaceForData(
                             v12,
                             FixedTypeDataSpace >= 0x800,
                             FixedTypeDataSpace);
            v26 = (HyperVStorageKeyTableEntry *)*((_QWORD *)v14 + 4);
            if ( !v26 || *((_DWORD *)v14 + 6) )
              HvsThrowHResultError(-2147024809);
            Name = HyperVStorageKeyTableEntry::GetName((HyperVStorageKeyTableEntry *)v14);
            v28 = -1;
            do
              ++v28;
            while ( Name[v28] );
            std::string::_Assign<char>(&v71, Name);
            HyperVStorageKeyTableEntry::RemoveChild(v26, (struct HyperVStorageKeyTableEntry *)v14);
            HyperVStorageOperation::RemoveModifiedNode(v13, (struct HyperVStorageKeyTableEntry *)v14);
            (*(void (__fastcall **)(char *, char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8, v14);
            LOBYTE(v47) = 0;
            v57 = *(void **)(*(__int64 (__fastcall **)(HyperVStorage *, struct _GUID *, HyperVStorageKeyTableEntry *, __int128 *, HyperVStorageOperation *, _DWORD, int))(*(_QWORD *)this + 168LL))(
                              this,
                              &v55,
                              v26,
                              &v71,
                              v13,
                              (_DWORD)v57,
                              v47);
            v14 = (char *)*((_QWORD *)v57 + 5);
            switch ( v12 )
            {
              case 3u:
                v29 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v29 = String[0];
                Src = _wtoi64(v29);
                p_Src = &Src;
                break;
              case 4u:
                v31 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v31 = String[0];
                v67 = _wtoi64(v31);
                p_Src = &v67;
                break;
              case 5u:
                v32 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v32 = String[0];
                v68 = _wtof(v32);
                p_Src = (__int64 *)&v68;
                break;
              case 6u:
                p_Src = (__int64 *)String;
                if ( v62 > 7 )
                  p_Src = (__int64 *)String[0];
                break;
              case 7u:
                p_Src = (__int64 *)v73;
                break;
              case 8u:
                v33 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v33 = String[0];
                Src = _wtoi64(v33);
                v63 = 0;
                v34 = String;
                if ( v62 > 7 )
                  v34 = (wchar_t **)String[0];
                if ( !(unsigned int)_o__wcsicmp(L"true", v34) || Src == 1 )
                  v63 = 1;
                p_Src = (__int64 *)&v63;
                break;
              default:
                IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0x4000u);
                IsEnabled = HyperVStorageTrace::IsEnabled(v37, v36);
                v39 = IsEnabled;
                if ( IsDebugTraceEnabled || IsEnabled )
                {
                  if ( dword_1403C1924 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
                  {
                    Init_thread_header(&dword_1403C1924);
                    if ( dword_1403C1924 == -1 )
                    {
                      byte_1403A6B44 = IsDebugTraceEnabled != 0;
                      byte_1403A6B45 = v39;
                      Init_thread_footer(&dword_1403C1924);
                    }
                  }
                  v40 = &v71;
                  if ( v72.m128i_i64[1] > 0xFuLL )
                    v40 = (__int128 *)v71;
                  v41 = lpWideCharStr;
                  if ( *(_QWORD *)&cchWideChar[2] > 7u )
                    v41 = (LPCWCH *)lpWideCharStr[0];
                  HvsDebugTraceInternal(0x4000u, (const struct HvsDebugTraceParameters *)&off_1403A6B30, v41, v40);
                }
                HvsThrowHResultError(-2147024809);
            }
            LODWORD(pwszBaseUri) = FixedTypeDataSpace;
            HyperVStorage::SetNodeValue((int)this, (int)v26, (int)&v57, v12, (size_t)pwszBaseUri, p_Src, (__int64)v13);
LABEL_74:
            v14 = (char *)*((_QWORD *)v14 + 4);
            if ( !v14 )
              HvsThrowHResultError(-2147024809);
            v12 = 1;
            v49 = 1;
            v61 = 0;
            v42 = String;
            if ( v62 > 7 )
              v42 = (wchar_t **)String[0];
            *(_WORD *)v42 = 0;
          }
        }
        switch ( v64 )
        {
          case 3:
          case 4:
LABEL_22:
            v57 = 0;
            v17 = (*(__int64 (__fastcall **)(void *, void **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                    ppvObject,
                    &v57,
                    0);
            if ( v17 < 0 )
              HvsThrowHResultError(v17);
            std::wstring::append(String, v57);
            break;
          case 13:
            if ( v61 )
              goto LABEL_22;
            break;
          case 15:
            goto LABEL_32;
        }
      }
    }
    catch ( ... )
    {
      HyperVStorageOperation::Undo(v53);
      std::vector<HyperVStorageOperation>::pop_back((char *)v51 + 184);
      throw;
    }
LABEL_102:
    if ( v16 < 0 )
      HvsThrowHResultError(v16);
    std::string::~string(&v71);
    std::wstring::_Tidy_deallocate(lpWideCharStr);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v73);
    std::wstring::_Tidy_deallocate(&v75);
    std::wstring::_Tidy_deallocate(String);
    HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&ppInput);
    HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&ppvObject);
    v43 = v52;
  }
  catch ( ... )
  {
    HvsGetHResultForThrownException();
  }
  v44 = v50;
  v55 = *(struct _GUID *)((char *)this + 568);
  HyperVStorageTrace::ReadFromStream(&v55, a3 != 0, v43, v50);
  return v44;
}

```

## disassembly

```asm
0x140084fe4  mov     [rsp+arg_10], r8d
0x140084fe9  push    rbx
0x140084fea  push    rsi
0x140084feb  push    rdi
0x140084fec  push    r12
0x140084fee  push    r13
0x140084ff0  push    r14
0x140084ff2  push    r15
0x140084ff4  sub     rsp, 170h
0x140084ffb  mov     rax, cs:__security_cookie
0x140085002  xor     rax, rsp
0x140085005  mov     [rsp+1A8h+var_48], rax
0x14008500d  mov     rsi, r9
0x140085010  mov     [rsp+1A8h+var_150], r9
0x140085015  mov     r14d, r8d
0x140085018  mov     rdi, rdx
0x14008501b  mov     r15, rcx
0x14008501e  mov     [rsp+1A8h+var_158], rcx
0x140085023  mov     [rsp+1A8h+var_140], r9
0x140085028  xor     ebx, ebx
0x14008502a  mov     [rsp+1A8h+var_160], ebx
0x14008502e  mov     [rsp+1A8h+ppvObject], rbx
0x140085036  xor     r8d, r8d; pMalloc
0x140085039  lea     rdx, [rsp+1A8h+ppvObject]; ppvObject
0x140085041  lea     rcx, stru_1402E8610; riid
0x140085048  call    cs:__imp_CreateXmlReader
0x14008504f  nop     dword ptr [rax+rax+00h]
0x140085054  test    eax, eax
0x140085056  jns     short loc_14008505F
0x140085058  mov     ecx, eax; int
0x14008505a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14008505f  mov     [rsp+1A8h+var_D8], rbx
0x140085067  lea     rax, [rsp+1A8h+var_D8]
0x14008506f  mov     [rsp+1A8h+ppInput], rax; ppInput
0x140085074  lea     rax, ?CFG_XML_NAMESPACE_URI@HyperVStorage@@1QBGB; ushort const near * const HyperVStorage::CFG_XML_NAMESPACE_URI
0x14008507b  mov     [rsp+1A8h+pwszBaseUri], rax; pwszBaseUri
0x140085080  mov     r9d, 1; fEncodingHint
0x140085086  lea     r8, pwszEncodingName; "UTF-16"
0x14008508d  xor     edx, edx; pMalloc
0x14008508f  mov     rcx, rdi; pInputStream
0x140085092  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x140085099  nop     dword ptr [rax+rax+00h]
0x14008509e  test    eax, eax
0x1400850a0  jns     short loc_1400850A9
0x1400850a2  mov     ecx, eax; int
0x1400850a4  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1400850a9  mov     rcx, [rsp+1A8h+ppvObject]
0x1400850b1  mov     r9, [rcx]
0x1400850b4  mov     eax, r14d
0x1400850b7  neg     eax
0x1400850b9  sbb     r8, r8
0x1400850bc  neg     r8
0x1400850bf  inc     r8
0x1400850c2  mov     edx, 1
0x1400850c7  mov     rax, [r9+28h]
0x1400850cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400850d0  test    eax, eax
0x1400850d2  jns     short loc_1400850DB
0x1400850d4  mov     ecx, eax; int
0x1400850d6  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1400850db  mov     rcx, [rsp+1A8h+ppvObject]
0x1400850e3  mov     rax, [rcx]
0x1400850e6  mov     rdx, [rsp+1A8h+var_D8]
0x1400850ee  mov     rax, [rax+18h]
0x1400850f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400850f7  test    eax, eax
0x1400850f9  jns     short loc_140085102
0x1400850fb  mov     ecx, eax; int
0x1400850fd  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140085102  mov     edi, 1
0x140085107  mov     [rsp+1A8h+var_164], edi
0x14008510b  xorps   xmm0, xmm0
0x14008510e  movups  xmmword ptr [rsp+1A8h+String], xmm0
0x140085116  mov     [rsp+1A8h+var_F8], rbx
0x14008511e  mov     [rsp+1A8h+var_F0], 7
0x14008512a  mov     word ptr [rsp+1A8h+String], bx
0x140085132  mov     [rsp+1A8h+var_E4], ebx
0x140085139  mov     [rsp+1A8h+var_D0], rbx
0x140085141  mov     [rsp+1A8h+Src], rbx
0x140085149  movsd   [rsp+1A8h+var_C8], xmm0
0x140085152  mov     [rsp+1A8h+var_E8], ebx
0x140085159  mov     [rsp+1A8h+var_168], ebx
0x14008515d  movups  [rsp+1A8h+var_68], xmm0
0x140085165  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x14008516d  movdqu  [rsp+1A8h+var_58], xmm2
0x140085176  mov     word ptr [rsp+1A8h+var_68], bx
0x14008517e  xorps   xmm1, xmm1
0x140085181  movdqu  [rsp+1A8h+var_80], xmm1
0x14008518a  mov     [rsp+1A8h+var_70], rbx
0x140085192  movups  xmmword ptr [rsp+1A8h+lpWideCharStr], xmm0
0x14008519a  movdqu  xmmword ptr [rsp+1A8h+cchWideChar], xmm2
0x1400851a3  mov     word ptr [rsp+1A8h+lpWideCharStr], bx
0x1400851ab  movups  [rsp+1A8h+var_A0], xmm0
0x1400851b3  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1400851bb  movdqu  [rsp+1A8h+var_90], xmm1
0x1400851c4  mov     byte ptr [rsp+1A8h+var_A0], bl
0x1400851cb  mov     dword ptr [rsp+1A8h+var_120], edi
0x1400851d2  mov     [rsp+1A8h+var_118], r15
0x1400851da  lea     rcx, [r15+0B8h]
0x1400851e1  lea     r8, [rsp+1A8h+var_120]
0x1400851e9  lea     rdx, [rsp+1A8h+var_118]
0x1400851f1  call    ??$emplace_back@PEAVHyperVStorage@@W4HyperVStorageOperationType@@@?$vector@VHyperVStorageOperation@@V?$allocator@VHyperVStorageOperation@@@std@@@std@@QEAAAEAVHyperVStorageOperation@@$$QEAPEAVHyperVStorage@@$$QEAW4HyperVStorageOperationType@@@Z; std::vector<HyperVStorageOperation>::emplace_back<HyperVStorage *,HyperVStorageOperationType>(HyperVStorage * &&,HyperVStorageOperationType &&)
0x1400851f6  mov     r13, [r15+0C0h]
0x1400851fd  sub     r13, 58h ; 'X'
0x140085201  mov     [rsp+1A8h+var_148], r13
0x140085206  lea     r14, [r15+0F8h]
0x14008520d  test    rsi, rsi
0x140085210  jz      short loc_140085253
0x140085212  mov     [rsp+1A8h+var_120], rbx
0x14008521a  mov     byte ptr [rsp+1A8h+var_178], bl
0x14008521e  mov     [rsp+1A8h+pwszBaseUri], rbx
0x140085223  lea     r9, [rsp+1A8h+var_120]
0x14008522b  mov     r8, r13
0x14008522e  mov     rdx, rsi
0x140085231  mov     rcx, r15
0x140085234  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x140085239  test    eax, eax
0x14008523b  jnz     short loc_140085247
0x14008523d  mov     ecx, 80004005h; int
0x140085242  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140085247  mov     rax, [rsp+1A8h+var_120]
0x14008524f  mov     r14, [rax+28h]
0x140085253  mov     rcx, [rsp+1A8h+ppvObject]
0x14008525b  mov     rax, [rcx]
0x14008525e  lea     rdx, [rsp+1A8h+var_E4]
0x140085266  mov     rax, [rax+30h]
0x14008526a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008526f  test    eax, eax
0x140085271  jnz     loc_140085807
0x140085277  mov     ecx, [rsp+1A8h+var_E4]
0x14008527e  sub     ecx, 1
0x140085281  jz      short loc_1400852F5
0x140085283  sub     ecx, 2
0x140085286  jz      short loc_1400852A6
0x140085288  sub     ecx, 1
0x14008528b  jz      short loc_1400852A6
0x14008528d  sub     ecx, 9
0x140085290  jz      short loc_14008529C
0x140085292  cmp     ecx, 2
0x140085295  jnz     short loc_140085253
0x140085297  jmp     loc_140085411
0x14008529c  cmp     [rsp+1A8h+var_F8], rbx
0x1400852a4  jz      short loc_140085253
0x1400852a6  mov     [rsp+1A8h+var_120], rbx
0x1400852ae  mov     rcx, [rsp+1A8h+ppvObject]
0x1400852b6  mov     rax, [rcx]
0x1400852b9  xor     r8d, r8d
0x1400852bc  lea     rdx, [rsp+1A8h+var_120]
0x1400852c4  mov     rax, [rax+80h]
0x1400852cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400852d0  test    eax, eax
0x1400852d2  jns     short loc_1400852DB
0x1400852d4  mov     ecx, eax; int
0x1400852d6  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1400852db  mov     rdx, [rsp+1A8h+var_120]; void *
0x1400852e3  lea     rcx, [rsp+1A8h+String]; Src
0x1400852eb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1400852f0  jmp     loc_140085253
0x1400852f5  mov     [rsp+1A8h+var_118], rbx
0x1400852fd  mov     rcx, [rsp+1A8h+ppvObject]
0x140085305  mov     rax, [rcx]
0x140085308  xor     r8d, r8d
0x14008530b  lea     rdx, [rsp+1A8h+var_118]
0x140085313  mov     rax, [rax+70h]
0x140085317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008531c  test    eax, eax
0x14008531e  jns     short loc_140085327
0x140085320  mov     ecx, eax; int
0x140085322  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140085327  mov     rdx, [rsp+1A8h+var_118]
0x14008532f  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x140085337  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14008533c  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x140085341  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x140085349  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x14008534e  mov     rcx, [rsp+1A8h+ppvObject]
0x140085356  mov     rax, [rcx]
0x140085359  mov     rax, [rax+0A0h]
0x140085360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085365  mov     edi, eax
0x140085367  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x14008536c  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x140085374  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x140085379  mov     [rsp+1A8h+var_F8], rbx
0x140085381  lea     rax, [rsp+1A8h+String]
0x140085389  cmp     [rsp+1A8h+var_F0], 7
0x140085392  cmova   rax, [rsp+1A8h+String]
0x14008539b  mov     [rax], bx
0x14008539e  mov     edx, [rsp+1A8h+cchWideChar]; cchWideChar
0x1400853a5  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x1400853ad  cmp     qword ptr [rsp+1A8h+cchWideChar+8], 7
0x1400853b6  cmova   rcx, [rsp+1A8h+lpWideCharStr]; lpWideCharStr
0x1400853bf  lea     r9, [rsp+1A8h+var_A0]
0x1400853c7  call    ?HvsWideToMultiByte@@YA_KPEBG_KIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; HvsWideToMultiByte(ushort const *,unsigned __int64,uint,std::string &)
0x1400853cc  mov     rax, [r15]
0x1400853cf  mov     byte ptr [rsp+1A8h+var_178], bl
0x1400853d3  mov     dword ptr [rsp+1A8h+ppInput], ebx
0x1400853d7  mov     [rsp+1A8h+pwszBaseUri], r13
0x1400853dc  lea     r9, [rsp+1A8h+var_A0]
0x1400853e4  mov     r8, r14
0x1400853e7  lea     rdx, [rsp+1A8h+var_128]
0x1400853ef  mov     rcx, r15
0x1400853f2  mov     rax, [rax+0A8h]
0x1400853f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400853fe  mov     rax, [rax]
0x140085401  mov     r14, [rax+28h]
0x140085405  test    edi, edi
0x140085407  mov     edi, [rsp+1A8h+var_164]
0x14008540b  jz      loc_140085253
0x140085411  mov     rcx, [rsp+1A8h+var_F8]
0x140085419  test    rcx, rcx
0x14008541c  jz      short loc_14008542A
0x14008541e  cmp     edi, 1
0x140085421  jnz     short loc_140085436
0x140085423  mov     edi, 6
0x140085428  jmp     short loc_140085436
0x14008542a  lea     eax, [rdi-6]
0x14008542d  cmp     eax, 1
0x140085430  ja      loc_1400856F1
0x140085436  cmp     edi, 6
0x140085439  jnz     short loc_140085444
0x14008543b  lea     esi, [rcx+rcx]
0x14008543e  mov     [rsp+1A8h+var_168], esi
0x140085442  jmp     short loc_140085483
0x140085444  cmp     edi, 7
0x140085447  jnz     short loc_140085476
0x140085449  test    rcx, rcx
0x14008544c  jz      short loc_14008546E
0x14008544e  lea     r9, [rsp+1A8h+var_168]
0x140085453  lea     r8, [rsp+1A8h+var_80]
0x14008545b  lea     rdx, [rsp+1A8h+String]
0x140085463  call    ?ConvertArrayDataFromString@HyperVStorage@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@AEAI@Z; HyperVStorage::ConvertArrayDataFromString(std::wstring const &,std::vector<uchar> &,uint &)
0x140085468  mov     esi, [rsp+1A8h+var_168]
0x14008546c  jmp     short loc_140085483
0x14008546e  mov     esi, ebx
0x140085470  mov     [rsp+1A8h+var_168], ebx
0x140085474  jmp     short loc_140085483
0x140085476  mov     ecx, edi
0x140085478  call    ?GetFixedTypeDataSpace@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@@Z; HyperVStorageKeyTableEntry::GetFixedTypeDataSpace(HyperVStorageKeyType)
0x14008547d  mov     esi, eax
0x14008547f  mov     [rsp+1A8h+var_168], eax
0x140085483  mov     edx, ebx
0x140085485  cmp     esi, 800h
0x14008548b  setnb   dl
0x14008548e  mov     r8d, esi
0x140085491  mov     ecx, edi
0x140085493  call    ?GetRequiredSpaceForData@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@HI@Z; HyperVStorageKeyTableEntry::GetRequiredSpaceForData(HyperVStorageKeyType,int,uint)
0x140085498  mov     dword ptr [rsp+1A8h+var_120], eax
0x14008549f  mov     r12, [r14+20h]
0x1400854a3  test    r12, r12
0x1400854a6  jz      loc_1400857CA
0x1400854ac  cmp     [r14+18h], ebx
0x1400854b0  jnz     loc_1400857CA
0x1400854b6  mov     rcx, r14; this
0x1400854b9  call    ?GetName@HyperVStorageKeyTableEntry@@QEBAPEBDXZ; HyperVStorageKeyTableEntry::GetName(void)
0x1400854be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400854c2  inc     r8
0x1400854c5  cmp     [rax+r8], bl
0x1400854c9  jnz     short loc_1400854C2
0x1400854cb  mov     rdx, rax
0x1400854ce  lea     rcx, [rsp+1A8h+var_A0]
0x1400854d6  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1400854db  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x1400854de  mov     rcx, r12; this
0x1400854e1  call    ?RemoveChild@HyperVStorageKeyTableEntry@@QEAAXPEAV1@@Z; HyperVStorageKeyTableEntry::RemoveChild(HyperVStorageKeyTableEntry *)
0x1400854e6  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x1400854e9  mov     rcx, r13; this
0x1400854ec  call    ?RemoveModifiedNode@HyperVStorageOperation@@QEAAXPEAVHyperVStorageKeyTableEntry@@@Z; HyperVStorageOperation::RemoveModifiedNode(HyperVStorageKeyTableEntry *)
0x1400854f1  lea     rcx, [r15+8]
0x1400854f5  mov     rax, [rcx]
0x1400854f8  mov     rdx, r14
0x1400854fb  mov     rax, [rax+8]
0x1400854ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085504  mov     rax, [r15]
0x140085507  mov     byte ptr [rsp+1A8h+var_178], bl
0x14008550b  mov     ecx, dword ptr [rsp+1A8h+var_120]
0x140085512  mov     dword ptr [rsp+1A8h+ppInput], ecx
0x140085516  mov     [rsp+1A8h+pwszBaseUri], r13
0x14008551b  lea     r9, [rsp+1A8h+var_A0]
0x140085523  mov     r8, r12
0x140085526  lea     rdx, [rsp+1A8h+var_138]
0x14008552b  mov     rcx, r15
0x14008552e  mov     rax, [rax+0A8h]
0x140085535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008553a  mov     rax, [rax]
0x14008553d  mov     [rsp+1A8h+var_120], rax
0x140085545  mov     r14, [rax+28h]
0x140085549  cmp     edi, 3
0x14008554c  jnz     short loc_140085589
0x14008554e  lea     rcx, [rsp+1A8h+String]
0x140085556  cmp     [rsp+1A8h+var_F0], 7
0x14008555f  cmova   rcx, [rsp+1A8h+String]; String
0x140085568  call    cs:__imp__wtoi64
0x14008556f  nop     dword ptr [rax+rax+00h]
0x140085574  mov     [rsp+1A8h+Src], rax
0x14008557c  lea     rax, [rsp+1A8h+Src]
0x140085584  jmp     loc_1400856CD
0x140085589  cmp     edi, 4
0x14008558c  jnz     short loc_1400855C9
0x14008558e  lea     rcx, [rsp+1A8h+String]
  ... truncated ...
```

# SingleUserStoredIdentitySnapshot::CaptureIdentity(SingleUserStoredIdentitySnapshot::ThreadContext const *)

- ea: `0x180012e10`
- end: `0x180013b44`
- name: `?CaptureIdentity@SingleUserStoredIdentitySnapshot@@AEAAKPEBUThreadContext@1@@Z`
- size: `3380`
- prototype: `unsigned int __fastcall(SingleUserStoredIdentitySnapshot *__hidden this, const struct SingleUserStoredIdentitySnapshot::ThreadContext *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d3e0`

## callees

- `0x180004738`
- `0x18000a110`
- `0x1800126ec`
- `0x180012984`
- `0x180012dc0`
- `0x180012e10`
- `0x180013b50`
- `0x1800171b0`
- `0x180017200`
- `0x180017230`
- `0x180017330`
- `0x1800369e4`
- `0x18003bf58`
- `0x18003ceb8`
- `0x180041378`
- `0x1800439bc`
- `0x180054a54`
- `0x1800593bc`
- `0x180061c04`
- `0x18006b398`
- `0x180075e60`
- `0x18008251f`
- `0x18008252b`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013514`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013514`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012fc6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012fc6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800136c0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800136e2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013840`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800138b7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013937`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800139cd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800136c0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800136e2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013840`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800138b7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013937`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800139cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001369d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001379b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800137b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001369d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001379b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800137b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800130d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800135d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800130d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800135d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b39`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013012`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013012`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall SingleUserStoredIdentitySnapshot::CaptureIdentity(
        SingleUserStoredIdentitySnapshot *this,
        const struct SingleUserStoredIdentitySnapshot::ThreadContext *a2)
{
  char *v3; // r12
  unsigned __int64 v4; // r14
  __int64 v5; // rax
  WinStoreAuth::AuthenticationInternal *v6; // rcx
  HSTRING *v7; // r8
  int DeviceTicketWithBroker; // eax
  _QWORD *v9; // rbx
  unsigned __int64 v10; // rdi
  _QWORD *v11; // rax
  __int64 v12; // rax
  const char *v13; // r9
  __m128i si128; // xmm6
  __int64 v15; // rdx
  __int64 v16; // r8
  __int128 *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int AllAccountTickets; // eax
  unsigned __int64 i; // rax
  HSTRING *v22; // r12
  PCWSTR v23; // rax
  PCWSTR v24; // r14
  unsigned __int64 v25; // rdi
  PCWSTR v26; // rax
  PCWSTR v27; // r12
  unsigned __int64 v28; // r14
  unsigned __int64 v29; // rax
  void **v30; // r12
  void **v31; // rbx
  __int64 v32; // r10
  unsigned __int64 v33; // r11
  void *v34; // rbx
  __int128 *v35; // r12
  __int64 v36; // r9
  unsigned __int64 v37; // r8
  unsigned __int64 v38; // rax
  unsigned __int64 *v39; // rdx
  unsigned __int64 v40; // rbx
  unsigned __int64 v41; // rax
  char *v42; // r12
  size_t v43; // rbx
  const char *v44; // r9
  char *v46; // r12
  size_t v47; // rbx
  HSTRING *v48; // rdx
  int DeviceTicket; // eax
  PCWSTR v50; // rax
  __int128 *v51; // rdx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v53; // rdi
  _QWORD *v54; // r14
  __int64 v55; // r14
  PCWSTR v56; // rax
  PCWSTR v57; // rax
  __int64 v58; // rax
  __int64 v59; // rbx
  __int64 v60; // rbx
  PCWSTR v61; // rdx
  __int64 v62; // r12
  unsigned __int64 j; // rdi
  HSTRING *v64; // rbx
  int Format; // [rsp+20h] [rbp-188h]
  int Formata; // [rsp+20h] [rbp-188h]
  unsigned __int64 *v67; // [rsp+28h] [rbp-180h]
  char *v68; // [rsp+30h] [rbp-178h]
  unsigned __int64 v69; // [rsp+40h] [rbp-168h] BYREF
  HSTRING string; // [rsp+48h] [rbp-160h] BYREF
  char *v71; // [rsp+50h] [rbp-158h]
  void *v72; // [rsp+58h] [rbp-150h]
  char *v73; // [rsp+60h] [rbp-148h]
  unsigned __int64 v74; // [rsp+68h] [rbp-140h]
  __int64 v75; // [rsp+70h] [rbp-138h]
  __int64 v76; // [rsp+78h] [rbp-130h]
  unsigned __int64 v77; // [rsp+80h] [rbp-128h]
  void *v78; // [rsp+88h] [rbp-120h]
  unsigned __int64 v79; // [rsp+90h] [rbp-118h]
  __int128 v80; // [rsp+98h] [rbp-110h] BYREF
  SingleUserStoredIdentitySnapshot *v81; // [rsp+A8h] [rbp-100h]
  SingleUserStoredIdentitySnapshot *v82; // [rsp+B0h] [rbp-F8h]
  __int128 v83; // [rsp+B8h] [rbp-F0h] BYREF
  __m128i v84; // [rsp+C8h] [rbp-E0h]
  __int128 v85; // [rsp+E0h] [rbp-C8h] BYREF
  __m128i v86; // [rsp+F0h] [rbp-B8h]
  __int128 v87; // [rsp+100h] [rbp-A8h] BYREF
  __m128i v88; // [rsp+110h] [rbp-98h]
  void *Src[2]; // [rsp+120h] [rbp-88h] BYREF
  unsigned __int64 v90; // [rsp+130h] [rbp-78h]
  __int64 v91; // [rsp+138h] [rbp-70h]
  __int128 v92; // [rsp+140h] [rbp-68h] BYREF
  unsigned __int64 v93; // [rsp+150h] [rbp-58h]
  __int64 v94; // [rsp+158h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v81 = this;
  v82 = this;
  v3 = 0;
  v73 = 0;
  v4 = 0;
  v69 = 0;
  v80 = 0;
  v5 = *((_QWORD *)a2 + 2);
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v80 = *(_OWORD *)((char *)a2 + 8);
  StoredIdentitySnapshot::CaptureIdentity(this, &v80);
  if ( *((int *)this + 2) >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    DeviceTicketWithBroker = WinStoreAuth::AuthenticationInternal::GetDeviceTicketWithBroker(v6, (bool)&string, v7);
    if ( DeviceTicketWithBroker >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v53 = StringRawBuffer;
      v54 = (_QWORD *)((char *)this + 272);
      v40 = -1;
      do
        ++v40;
      while ( StringRawBuffer[v40] );
      v41 = *((_QWORD *)this + 37);
      v74 = v41;
      if ( v40 <= v41 )
      {
        if ( v41 <= 7 )
          v46 = (char *)this + 272;
        else
          v46 = (char *)*v54;
        *((_QWORD *)this + 36) = v40;
        v47 = 2 * v40;
        memmove_0(v46, v53, v47);
        *(_WORD *)&v46[v47] = 0;
        v4 = v69;
      }
      else
      {
        if ( v40 > 0x7FFFFFFFFFFFFFFELL )
          std::_Xlength_error("string too long");
        v75 = std::wstring::_Calculate_growth((char *)this + 272, v40);
        v42 = (char *)std::allocator<unsigned short>::allocate((char *)this + 272, v75 + 1);
        *((_QWORD *)this + 36) = v40;
        *((_QWORD *)this + 37) = v75;
        v43 = 2 * v40;
        memcpy_0(v42, v53, v43);
        *(_WORD *)&v42[v43] = 0;
        if ( v74 > 7 )
          std::_Deallocate<16>(*v54, 2 * v74 + 2);
        *v54 = v42;
        v4 = v69;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)DeviceTicketWithBroker,
        Format);
    }
    v9 = (_QWORD *)((char *)this + 48);
    v83 = 0;
    v84 = 0;
    v10 = *((_QWORD *)this + 8);
    if ( *((_QWORD *)this + 9) > 7u )
      v9 = (_QWORD *)*v9;
    if ( v10 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v10 > 7 )
    {
      v55 = std::wstring::_Calculate_growth(*((_QWORD *)this + 8), 7);
      *(_QWORD *)&v83 = std::allocator<unsigned short>::allocate(&v83, v55 + 1);
      v84.m128i_i64[0] = v10;
      v84.m128i_i64[1] = v55;
      memcpy_0((void *)v83, v9, 2 * v10 + 2);
      v4 = v69;
    }
    else
    {
      v84.m128i_i64[0] = *((_QWORD *)this + 8);
      v84.m128i_i64[1] = 7;
      v83 = *(_OWORD *)v9;
    }
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      0x15Fu,
      "SingleUserStoredIdentitySnapshot::CaptureIdentity",
      (wchar_t *)L"Getting user tickets for %s");
    v11 = (_QWORD *)(**(__int64 (__fastcall ***)(SingleUserStoredIdentitySnapshot *))this)(this);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 32LL))(*v11);
    if ( !SetThreadToken(0, *(HANDLE *)(v12 + 8)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
        v13);
    if ( !*((_QWORD *)this + 36) )
    {
      WindowsDeleteString(string);
      string = 0;
      DeviceTicket = WinStoreAuth::AuthenticationInternal::GetDeviceTicket(
                       (WinStoreAuth::AuthenticationInternal *)&string,
                       v48);
      if ( DeviceTicket < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
          (const char *)(unsigned int)DeviceTicket,
          Formata);
      v50 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::assign((char *)this + 272, v50);
    }
    if ( *((_QWORD *)this + 40) )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v85 = 0;
      v86 = si128;
      LOWORD(v85) = 0;
      v87 = 0;
      v88 = si128;
      LOWORD(v87) = 0;
      std::wstring::operator=(&v85, (char *)this + 304);
      if ( *((_DWORD *)this + 84) )
        std::vector<StoredTicket>::push_back((char *)this + 368, &v85);
      else
        std::vector<StoredTicket>::push_back((char *)this + 344, &v85);
      ContentIdString::~ContentIdString((ContentIdString *)&v87);
      ContentIdString::~ContentIdString((ContentIdString *)&v85);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 392);
      v68 = (char *)this + 392;
      v67 = &v69;
      AllAccountTickets = WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(v19, v18, 3);
      *((_DWORD *)this + 3) = AllAccountTickets;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v4 = v69;
      if ( AllAccountTickets >= 0 )
      {
        for ( i = 0; ; i = v75 + 1 )
        {
          v75 = i;
          if ( i >= v4 )
            break;
          v22 = (HSTRING *)&v73[24 * i];
          if ( *(_DWORD *)v22 == 1 )
          {
            v23 = WindowsGetStringRawBuffer(v22[2], 0);
            v24 = v23;
            v92 = 0;
            v93 = 0;
            v94 = 0;
            v25 = -1;
            do
              ++v25;
            while ( v23[v25] );
            if ( v25 > 0x7FFFFFFFFFFFFFFELL )
              std::_Xlength_error("string too long");
            if ( v25 > 7 )
            {
              v59 = std::wstring::_Calculate_growth(v25, 7);
              v79 = v59;
              v72 = (void *)std::allocator<unsigned short>::allocate(&v92, v59 + 1);
              *(_QWORD *)&v92 = v72;
              v93 = v25;
              v94 = v59;
              memcpy_0(v72, v24, 2 * v25);
              *((_WORD *)v72 + v25) = 0;
            }
            else
            {
              v93 = v25;
              v94 = 7;
              memcpy_0(&v92, v23, 2 * v25);
              *((_WORD *)&v92 + v25) = 0;
              v79 = v94;
              v25 = v93;
              v72 = (void *)v92;
            }
            v26 = WindowsGetStringRawBuffer(v22[1], 0);
            v27 = v26;
            *(_OWORD *)Src = 0;
            v90 = 0;
            v91 = 0;
            v28 = -1;
            do
              ++v28;
            while ( v26[v28] );
            if ( v28 > 0x7FFFFFFFFFFFFFFELL )
              std::_Xlength_error("string too long");
            if ( v28 > 7 )
            {
              v60 = std::wstring::_Calculate_growth(v28, 7);
              v77 = v60;
              v78 = (void *)std::allocator<unsigned short>::allocate(Src, v60 + 1);
              Src[0] = v78;
              v90 = v28;
              v91 = v60;
              v61 = v27;
              v30 = (void **)v78;
              memcpy_0(v78, v61, 2 * v28);
              *((_WORD *)v30 + v28) = 0;
              v29 = v77;
            }
            else
            {
              v90 = v28;
              v91 = 7;
              memcpy_0(Src, v26, 2 * v28);
              *((_WORD *)Src + v28) = 0;
              v29 = v91;
              v77 = v91;
              v28 = v90;
              v30 = (void **)Src[0];
              v78 = Src[0];
            }
            v85 = 0;
            v86 = 0;
            v31 = Src;
            if ( v29 > 7 )
              v31 = v30;
            if ( v28 > 0x7FFFFFFFFFFFFFFELL )
              std::_Xlength_error("string too long");
            if ( v28 > 7 )
            {
              v62 = std::wstring::_Calculate_growth(v28, 7);
              v76 = v62;
              v71 = (char *)std::allocator<unsigned short>::allocate(&v85, v62 + 1);
              *(_QWORD *)&v85 = v71;
              v86.m128i_i64[0] = v28;
              v86.m128i_i64[1] = v62;
              memcpy_0(v71, v31, 2 * v28 + 2);
              v34 = (void *)*((_QWORD *)&v85 + 1);
              v33 = v85;
              v32 = v62;
            }
            else
            {
              v86.m128i_i64[0] = v28;
              v32 = 7;
              v76 = 7;
              v86.m128i_i64[1] = 7;
              v33 = (unsigned __int64)*v31;
              *(_QWORD *)&v85 = *v31;
              v34 = v31[1];
              *((_QWORD *)&v85 + 1) = v34;
            }
            v74 = v33;
            v87 = 0;
            v88 = 0;
            v35 = &v92;
            if ( v79 > 7 )
              v35 = (__int128 *)v72;
            if ( v25 > 0x7FFFFFFFFFFFFFFELL )
              std::_Xlength_error("string too long");
            if ( v25 > 7 )
            {
              v71 = (char *)std::wstring::_Calculate_growth(v25, 7);
              *(_QWORD *)&v80 = std::allocator<unsigned short>::allocate(&v87, v71 + 1);
              *(_QWORD *)&v87 = v80;
              v88.m128i_i64[0] = v25;
              v88.m128i_i64[1] = (__int64)v71;
              memcpy_0((void *)v80, v35, 2 * v25 + 2);
              v38 = *((_QWORD *)&v87 + 1);
              v37 = v80;
              v36 = (__int64)v71;
              v32 = v76;
              v33 = v74;
            }
            else
            {
              v88.m128i_i64[0] = v25;
              v36 = 7;
              v88.m128i_i64[1] = 7;
              v37 = *(_QWORD *)v35;
              *(_QWORD *)&v87 = *(_QWORD *)v35;
              v38 = *((_QWORD *)v35 + 1);
              *((_QWORD *)&v87 + 1) = v38;
            }
            v39 = (unsigned __int64 *)*((_QWORD *)this + 44);
            if ( v39 == *((unsigned __int64 **)this + 45) )
            {
              std::vector<StoredTicket>::_Emplace_reallocate<StoredTicket>((char *)this + 344, v39, &v85);
            }
            else
            {
              *v39 = v33;
              v39[1] = (unsigned __int64)v34;
              v39[2] = v28;
              v39[3] = v32;
              v86 = si128;
              LOWORD(v85) = 0;
              v39[4] = v37;
              v39[5] = v38;
              v39[6] = v25;
              v39[7] = v36;
              v88 = si128;
              LOWORD(v87) = 0;
              *((_QWORD *)this + 44) += 64LL;
            }
            ContentIdString::~ContentIdString((ContentIdString *)&v87);
            ContentIdString::~ContentIdString((ContentIdString *)&v85);
            if ( v77 > 7 )
              std::_Deallocate<16>(v78, 2 * v77 + 2);
            if ( v79 > 7 )
              std::_Deallocate<16>(v72, 2 * v79 + 2);
            v4 = v69;
          }
          else if ( *(_DWORD *)v22 == 2 )
          {
            v56 = WindowsGetStringRawBuffer(v22[2], 0);
            std::wstring::wstring(Src, v56);
            v57 = WindowsGetStringRawBuffer(v22[1], 0);
            std::wstring::wstring(&v92, v57);
            v58 = StoredTicket::StoredTicket(&v85, &v92, Src);
            std::vector<StoredTicket>::push_back((char *)this + 368, v58);
            ContentIdString::~ContentIdString((ContentIdString *)&v87);
            ContentIdString::~ContentIdString((ContentIdString *)&v85);
            ContentIdString::~ContentIdString((ContentIdString *)&v92);
            ContentIdString::~ContentIdString((ContentIdString *)Src);
          }
          else
          {
            LODWORD(v67) = *(_DWORD *)v22;
            LogMessage(
              2u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
              0x18Cu,
              "SingleUserStoredIdentitySnapshot::CaptureIdentity",
              (wchar_t *)L"Unexpected ticket provider type %d",
              v67,
              v68);
          }
        }
      }
    }
    RevertToSelf();
    v15 = *((_QWORD *)this + 44);
    v16 = *((_QWORD *)this + 43);
    if ( v16 == v15 && *((_QWORD *)this + 46) == *((_QWORD *)this + 47) )
    {
      v51 = &v83;
      if ( v84.m128i_i64[1] > 7uLL )
        v51 = (__int128 *)v83;
      LODWORD(v68) = *((_DWORD *)this + 3);
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
        0x1A3u,
        "SingleUserStoredIdentitySnapshot::CaptureIdentity",
        (wchar_t *)L"No user tickets captured for %s, so this might not end well. HRESULT of WAM call: 0x%08x.",
        v51,
        v68);
    }
    else
    {
      v17 = &v83;
      if ( v84.m128i_i64[1] > 7uLL )
        v17 = (__int128 *)v83;
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
        0x1A8u,
        "SingleUserStoredIdentitySnapshot::CaptureIdentity",
        (wchar_t *)L"Captured %d MSA tickets and %d AAD tickets for %s",
        (v15 - v16) >> 6,
        (__int64)(*((_QWORD *)this + 47) - *((_QWORD *)this + 46)) >> 6,
        v17);
    }
    if ( v84.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v83, 2 * v84.m128i_i64[1] + 2);
    v84 = si128;
    LOWORD(v83) = 0;
    WindowsDeleteString(string);
    v3 = v73;
  }
  if ( v3 )
  {
    for ( j = 0; j < v4; ++j )
    {
      v64 = (HSTRING *)&v3[24 * j];
      WindowsDeleteString(v64[1]);
      v64[1] = 0;
      WindowsDeleteString(v64[2]);
      v64[2] = 0;
    }
    CoTaskMemFree(v3);
  }
  if ( !SetEvent(*((HANDLE *)this + 33)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      v44);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
    0x1B9u,
    "SingleUserStoredIdentitySnapshot::CaptureIdentity",
    (wchar_t *)L"Identity capture succeeded");
  return 0;
}

```

## disassembly

```asm
0x180012e10  mov     [rsp+arg_10], rbx
0x180012e15  mov     [rsp+arg_18], rsi
0x180012e1a  push    rdi
0x180012e1b  push    r12
0x180012e1d  push    r13
0x180012e1f  push    r14
0x180012e21  push    r15
0x180012e23  sub     rsp, 180h
0x180012e2a  movaps  [rsp+1A8h+var_38], xmm6
0x180012e32  mov     rax, cs:__security_cookie
0x180012e39  xor     rax, rsp
0x180012e3c  mov     [rsp+1A8h+var_40], rax
0x180012e44  mov     rsi, rcx
0x180012e47  mov     [rsp+1A8h+var_100], rcx
0x180012e4f  mov     [rsp+1A8h+var_F8], rcx
0x180012e57  xor     r15d, r15d
0x180012e5a  mov     r12d, r15d
0x180012e5d  mov     [rsp+1A8h+var_148], r15
0x180012e62  mov     r14d, r15d
0x180012e65  mov     [rsp+1A8h+var_168], r15
0x180012e6a  xorps   xmm0, xmm0
0x180012e6d  movdqu  [rsp+1A8h+var_110], xmm0
0x180012e76  mov     rax, [rdx+10h]
0x180012e7a  test    rax, rax
0x180012e7d  jz      short loc_180012E83
0x180012e7f  lock inc dword ptr [rax+8]
0x180012e83  mov     rax, [rdx+8]
0x180012e87  mov     qword ptr [rsp+1A8h+var_110], rax
0x180012e8f  mov     rax, [rdx+10h]
0x180012e93  mov     qword ptr [rsp+1A8h+var_110+8], rax
0x180012e9b  lea     rdx, [rsp+1A8h+var_110]
0x180012ea3  call    ?CaptureIdentity@StoredIdentitySnapshot@@IEAAXV?$shared_ptr@VNexus@@@std@@@Z; StoredIdentitySnapshot::CaptureIdentity(std::shared_ptr<Nexus>)
0x180012ea8  cmp     [rsi+8], r12d
0x180012eac  jl      loc_180013AF9
0x180012eb2  mov     [rsp+1A8h+string], r15
0x180012eb7  xor     ecx, ecx; string
0x180012eb9  call    cs:__imp_WindowsDeleteString
0x180012ebf  mov     [rsp+1A8h+string], r15
0x180012ec4  lea     rdx, [rsp+1A8h+string]; bool
0x180012ec9  call    ?GetDeviceTicketWithBroker@AuthenticationInternal@WinStoreAuth@@YAJ_NPEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::GetDeviceTicketWithBroker(bool,HSTRING__ * *)
0x180012ece  test    eax, eax
0x180012ed0  jns     loc_180013696
0x180012ed6  mov     rcx, [rsp+1A8h]; this
0x180012ede  mov     r9d, eax; char *
0x180012ee1  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180012ee8  mov     edx, 30Eh; void *
0x180012eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ef2  mov     r13, 7FFFFFFFFFFFFFFEh
0x180012efc  lea     rbx, [rsi+30h]
0x180012f00  xorps   xmm0, xmm0
0x180012f03  movups  [rsp+1A8h+var_F0], xmm0
0x180012f0b  xorps   xmm1, xmm1
0x180012f0e  movdqu  [rsp+1A8h+var_E0], xmm1
0x180012f17  mov     rdi, [rbx+10h]
0x180012f1b  cmp     qword ptr [rbx+18h], 7
0x180012f20  jbe     short loc_180012F25
0x180012f22  mov     rbx, [rbx]
0x180012f25  cmp     rdi, r13
0x180012f28  ja      loc_1800136DB
0x180012f2e  cmp     rdi, 7
0x180012f32  ja      loc_1800136E8
0x180012f38  mov     qword ptr [rsp+1A8h+var_E0], rdi
0x180012f40  mov     ecx, 7
0x180012f45  mov     qword ptr [rsp+1A8h+var_E0+8], rcx
0x180012f4d  mov     rdx, [rbx]
0x180012f50  mov     qword ptr [rsp+1A8h+var_F0], rdx
0x180012f58  mov     rax, [rbx+8]
0x180012f5c  mov     qword ptr [rsp+1A8h+var_F0+8], rax
0x180012f64  lea     rax, [rsp+1A8h+var_F0]
0x180012f6c  cmp     rcx, 7
0x180012f70  cmova   rax, rdx
0x180012f74  mov     [rsp+1A8h+var_180], rax
0x180012f79  lea     rax, aGettingUserTic; "Getting user tickets for %s"
0x180012f80  mov     [rsp+1A8h+Format], rax; int
0x180012f85  lea     r9, aSingleuserstor_0; "SingleUserStoredIdentitySnapshot::Captu"...
0x180012f8c  mov     r8d, 15Fh; unsigned int
0x180012f92  lea     rdx, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x180012f99  mov     ecx, 3; unsigned int
0x180012f9e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180012fa3  mov     rax, [rsi]
0x180012fa6  mov     rcx, rsi
0x180012fa9  mov     rax, [rax]
0x180012fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fb1  mov     rcx, [rax]
0x180012fb4  mov     rax, [rcx]
0x180012fb7  mov     rax, [rax+20h]
0x180012fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fc0  mov     rdx, [rax+8]; Token
0x180012fc4  xor     ecx, ecx; Thread
0x180012fc6  call    cs:__imp_SetThreadToken
0x180012fcc  mov     rcx, [rsp+1A8h]; this
0x180012fd4  test    eax, eax
0x180012fd6  jz      loc_180013751
0x180012fdc  cmp     qword ptr [rsi+120h], 0
0x180012fe4  jz      loc_1800135D2
0x180012fea  cmp     qword ptr [rsi+140h], 0
0x180012ff2  jz      loc_1800130E2
0x180012ff8  lea     rdx, [rsi+130h]
0x180012fff  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180013007  cmp     qword ptr [rdx+10h], 0
0x18001300c  jnz     loc_180013A55
0x180013012  call    cs:__imp_RevertToSelf
0x180013018  mov     rdx, [rsi+160h]
0x18001301f  mov     r8, [rsi+158h]
0x180013026  cmp     r8, rdx
0x180013029  jz      loc_18001362D
0x18001302f  lea     rcx, [rsp+1A8h+var_F0]
0x180013037  cmp     qword ptr [rsp+1A8h+var_E0+8], 7
0x180013040  cmova   rcx, qword ptr [rsp+1A8h+var_F0]
0x180013049  mov     rax, [rsi+178h]
0x180013050  sub     rax, [rsi+170h]
0x180013057  sar     rax, 6
0x18001305b  sub     rdx, r8
0x18001305e  sar     rdx, 6
0x180013062  mov     [rsp+1A8h+var_170], rcx
0x180013067  mov     [rsp+1A8h+var_178], rax
0x18001306c  mov     [rsp+1A8h+var_180], rdx
0x180013071  lea     rax, aCapturedDMsaTi; "Captured %d MSA tickets and %d AAD tick"...
0x180013078  mov     [rsp+1A8h+Format], rax; Format
0x18001307d  lea     r9, aSingleuserstor_0; "SingleUserStoredIdentitySnapshot::Captu"...
0x180013084  mov     r8d, 1A8h; unsigned int
0x18001308a  lea     rdx, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x180013091  mov     ecx, 3; unsigned int
0x180013096  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18001309b  nop
0x18001309c  mov     rdx, qword ptr [rsp+1A8h+var_E0+8]
0x1800130a4  cmp     rdx, 7
0x1800130a8  jbe     short loc_1800130BF
0x1800130aa  lea     rdx, ds:2[rdx*2]
0x1800130b2  mov     rcx, qword ptr [rsp+1A8h+var_F0]
0x1800130ba  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800130bf  movdqu  [rsp+1A8h+var_E0], xmm6
0x1800130c8  mov     word ptr [rsp+1A8h+var_F0], r15w
0x1800130d1  mov     rcx, [rsp+1A8h+string]; string
0x1800130d6  call    cs:__imp_WindowsDeleteString
0x1800130dc  nop
0x1800130dd  jmp     loc_180013AF4
0x1800130e2  lea     rbx, [rsi+188h]
0x1800130e9  mov     rcx, rbx
0x1800130ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800130f1  mov     [rsp+1A8h+var_178], rbx
0x1800130f6  lea     rax, [rsp+1A8h+var_168]
0x1800130fb  mov     [rsp+1A8h+var_180], rax
0x180013100  lea     rax, [rsp+1A8h+var_148]
0x180013105  mov     [rsp+1A8h+Format], rax
0x18001310a  mov     r8d, 3
0x180013110  call    ?GetAllAccountTickets@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@W4AccountProviderType@2@_NPEAPEAUTicketHolder@2@PEA_KPEAPEAU?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@3@Z; WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,bool,WinStoreAuth::TicketHolder * *,unsigned __int64 *,Windows::Foundation::Collections::IVector<IInspectable *> * *,bool)
0x180013115  mov     [rsi+0Ch], eax
0x180013118  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180013120  mov     r14, [rsp+1A8h+var_168]
0x180013125  test    eax, eax
0x180013127  js      loc_180013012
0x18001312d  mov     rax, r15
0x180013130  lea     r8, aUnexpectedTick; "Unexpected ticket provider type %d"
0x180013137  mov     [rsp+1A8h+var_138], rax
0x18001313c  cmp     rax, r14
0x18001313f  jnb     loc_180013012
0x180013145  lea     rax, [rax+rax*2]
0x180013149  mov     rcx, [rsp+1A8h+var_148]
0x18001314e  lea     r12, [rcx+rax*8]
0x180013152  mov     edx, [r12]
0x180013156  mov     ecx, edx
0x180013158  sub     ecx, 1
0x18001315b  jnz     loc_180013763
0x180013161  xor     edx, edx; length
0x180013163  mov     rcx, [r12+10h]; string
0x180013168  call    cs:__imp_WindowsGetStringRawBuffer
0x18001316e  mov     r14, rax
0x180013171  xorps   xmm0, xmm0
0x180013174  movups  [rsp+1A8h+var_68], xmm0
0x18001317c  mov     [rsp+1A8h+var_58], r15
0x180013184  mov     [rsp+1A8h+var_50], r15
0x18001318c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180013193  inc     rdi
0x180013196  cmp     word ptr [rax+rdi*2], 0
0x18001319b  jnz     short loc_180013193
0x18001319d  cmp     rdi, r13
0x1800131a0  ja      loc_180013839
0x1800131a6  cmp     rdi, 7
0x1800131aa  ja      loc_180013846
0x1800131b0  mov     [rsp+1A8h+var_58], rdi
0x1800131b8  mov     [rsp+1A8h+var_50], 7
0x1800131c4  lea     rbx, [rdi+rdi]
0x1800131c8  mov     r8, rbx; Size
0x1800131cb  mov     rdx, r14; Src
0x1800131ce  lea     rcx, [rsp+1A8h+var_68]; void *
0x1800131d6  call    memcpy_0
0x1800131db  mov     word ptr [rsp+rbx+1A8h+var_68], r15w
0x1800131e4  mov     rax, [rsp+1A8h+var_50]
0x1800131ec  mov     [rsp+1A8h+var_118], rax
0x1800131f4  mov     rdi, [rsp+1A8h+var_58]
0x1800131fc  mov     rax, qword ptr [rsp+1A8h+var_68]
0x180013204  mov     [rsp+1A8h+var_150], rax
0x180013209  xor     edx, edx; length
0x18001320b  mov     rcx, [r12+8]; string
0x180013210  call    cs:__imp_WindowsGetStringRawBuffer
0x180013216  mov     r12, rax
0x180013219  xorps   xmm0, xmm0
0x18001321c  movups  xmmword ptr [rsp+1A8h+Src], xmm0
0x180013224  mov     [rsp+1A8h+var_78], r15
0x18001322c  mov     [rsp+1A8h+var_70], r15
0x180013234  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001323b  nop     dword ptr [rax+rax+00h]
0x180013240  inc     r14
0x180013243  cmp     word ptr [rax+r14*2], 0
0x180013249  jnz     short loc_180013240
0x18001324b  cmp     r14, r13
0x18001324e  ja      loc_1800138B0
0x180013254  cmp     r14, 7
0x180013258  ja      loc_1800138BD
0x18001325e  mov     [rsp+1A8h+var_78], r14
0x180013266  mov     [rsp+1A8h+var_70], 7
0x180013272  lea     rbx, [r14+r14]
0x180013276  mov     r8, rbx; Size
0x180013279  mov     rdx, r12; Src
0x18001327c  lea     rcx, [rsp+1A8h+Src]; void *
0x180013284  call    memcpy_0
0x180013289  mov     word ptr [rsp+rbx+1A8h+Src], r15w
0x180013292  mov     rax, [rsp+1A8h+var_70]
0x18001329a  mov     [rsp+1A8h+var_128], rax
0x1800132a2  mov     r14, [rsp+1A8h+var_78]
0x1800132aa  mov     r12, [rsp+1A8h+Src]
0x1800132b2  mov     [rsp+1A8h+var_120], r12
0x1800132ba  xorps   xmm0, xmm0
0x1800132bd  movups  [rsp+1A8h+var_C8], xmm0
0x1800132c5  xorps   xmm1, xmm1
0x1800132c8  movdqa  [rsp+1A8h+var_B8], xmm1
0x1800132d1  lea     rbx, [rsp+1A8h+Src]
0x1800132d9  cmp     rax, 7
0x1800132dd  cmova   rbx, r12
0x1800132e1  cmp     r14, r13
0x1800132e4  ja      loc_180013930
0x1800132ea  cmp     r14, 7
0x1800132ee  ja      loc_18001393D
0x1800132f4  mov     qword ptr [rsp+1A8h+var_B8], r14
0x1800132fc  mov     r10d, 7
0x180013302  mov     [rsp+1A8h+var_130], r10
0x180013307  mov     qword ptr [rsp+1A8h+var_B8+8], r10
0x18001330f  mov     r11, [rbx]
0x180013312  mov     qword ptr [rsp+1A8h+var_C8], r11
0x18001331a  mov     rbx, [rbx+8]
0x18001331e  mov     qword ptr [rsp+1A8h+var_C8+8], rbx
0x180013326  mov     [rsp+1A8h+var_140], r11
0x18001332b  xorps   xmm0, xmm0
0x18001332e  movups  [rsp+1A8h+var_A8], xmm0
0x180013336  xorps   xmm1, xmm1
0x180013339  movdqa  [rsp+1A8h+var_98], xmm1
0x180013342  lea     r12, [rsp+1A8h+var_68]
0x18001334a  cmp     [rsp+1A8h+var_118], 7
0x180013353  cmova   r12, [rsp+1A8h+var_150]
0x180013359  cmp     rdi, r13
0x18001335c  ja      loc_1800139C6
0x180013362  cmp     rdi, 7
0x180013366  ja      loc_1800139D3
0x18001336c  mov     qword ptr [rsp+1A8h+var_98], rdi
0x180013374  mov     r9d, 7
0x18001337a  mov     qword ptr [rsp+1A8h+var_98+8], r9
0x180013382  mov     r8, [r12]
0x180013386  mov     qword ptr [rsp+1A8h+var_A8], r8
0x18001338e  mov     rax, [r12+8]
0x180013393  mov     qword ptr [rsp+1A8h+var_A8+8], rax
0x18001339b  lea     rcx, [rsi+158h]
0x1800133a2  mov     rdx, [rcx+8]
0x1800133a6  cmp     rdx, [rcx+10h]
0x1800133aa  jz      loc_18001346B
0x1800133b0  mov     [rdx], r11
0x1800133b3  mov     [rdx+8], rbx
0x1800133b7  mov     [rdx+10h], r14
0x1800133bb  mov     [rdx+18h], r10
0x1800133bf  movdqa  [rsp+1A8h+var_B8], xmm6
0x1800133c8  mov     word ptr [rsp+1A8h+var_C8], r15w
0x1800133d1  mov     [rdx+20h], r8
0x1800133d5  mov     [rdx+28h], rax
0x1800133d9  mov     [rdx+30h], rdi
0x1800133dd  mov     [rdx+38h], r9
0x1800133e1  movdqa  [rsp+1A8h+var_98], xmm6
0x1800133ea  mov     word ptr [rsp+1A8h+var_A8], r15w
0x1800133f3  add     qword ptr [rcx+8], 40h ; '@'
0x1800133f8  lea     rcx, [rsp+1A8h+var_A8]; this
0x180013400  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180013405  lea     rcx, [rsp+1A8h+var_C8]; this
0x18001340d  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180013412  nop
0x180013413  mov     rbx, [rsp+1A8h+var_128]
0x18001341b  cmp     rbx, 7
0x18001341f  jbe     short loc_180013437
0x180013421  lea     rdx, ds:2[rbx*2]
0x180013429  mov     rcx, [rsp+1A8h+var_120]
0x180013431  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013436  nop
0x180013437  mov     rax, [rsp+1A8h+var_118]
0x18001343f  cmp     rax, 7
0x180013443  ja      short loc_180013457
0x180013445  mov     r14, [rsp+1A8h+var_168]
0x18001344a  mov     rax, [rsp+1A8h+var_138]
0x18001344f  inc     rax
0x180013452  jmp     loc_180013130
0x180013457  lea     rdx, ds:2[rax*2]
0x18001345f  mov     rcx, [rsp+1A8h+var_150]
0x180013464  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
  ... truncated ...
```

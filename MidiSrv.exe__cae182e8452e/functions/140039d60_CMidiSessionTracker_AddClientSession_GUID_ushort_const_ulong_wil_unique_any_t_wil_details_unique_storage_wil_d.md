# CMidiSessionTracker::AddClientSession(_GUID,ushort const *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,void * *)

- ea: `0x140039d60`
- end: `0x14003a3b0`
- name: `?AddClientSession@CMidiSessionTracker@@UEAAJU_GUID@@PEBGKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAPEAX@Z`
- size: `1616`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const char *, unsigned int, HANDLE *, __int64)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task`

## callees

- `0x1400018e4`
- `0x14000204c`
- `0x14000317c`
- `0x1400054c0`
- `0x1400054e4`
- `0x1400060ec`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000d634`
- `0x14000dd3c`
- `0x14001440c`
- `0x14001ddc4`
- `0x14001f64c`
- `0x14001fa84`
- `0x14002308c`
- `0x1400389ec`
- `0x14003931c`
- `0x140039d60`
- `0x14003a5e0`
- `0x14003c874`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x14003a18d`
- `msvcp_win!_Xtime_get_ticks` at `0x14003a18d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039edd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039edd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039e38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039e38`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x140039f63`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x140039f63`

## string_xrefs

- `0x140039e79`: `Session already exists. Unable to add new.`
- `0x140039ebc`: `avcore\midi2\service\exe\midisessiontracker.cpp`
- `0x14003a2dd`: `Session created`

## pseudocode

```c
__int64 __fastcall CMidiSessionTracker::AddClientSession(
        __int64 a1,
        const wchar_t *a2,
        const char *a3,
        unsigned int a4,
        HANDLE *a5,
        __int64 a6)
{
  const char *v6; // rbx
  unsigned int v7; // edi
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  _DWORD *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  WCHAR *v17; // r8
  unsigned __int64 v18; // r12
  LPWSTR *v19; // rdx
  _QWORD *v20; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // rdx
  __int64 v23; // rbx
  void **v24; // rdi
  _DWORD *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  _DWORD *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  void **v31; // rax
  _QWORD *v32; // rax
  __int128 v33; // xmm1
  __int64 v34; // r8
  __int64 v35; // rax
  void **v36; // rbx
  _QWORD *v37; // rbx
  __int64 v38; // rax
  _DWORD *v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  void **v42; // rax
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned int v44; // [rsp+60h] [rbp-A0h] BYREF
  int v45[2]; // [rsp+68h] [rbp-98h] BYREF
  const char *v46; // [rsp+70h] [rbp-90h] BYREF
  const char *v47; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  const char *v50; // [rsp+90h] [rbp-70h]
  __int128 v51; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  __int64 ticks; // [rsp+C0h] [rbp-40h]
  __int128 v55; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  void *v58[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v59; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v60; // [rsp+100h] [rbp+0h]
  _QWORD v61[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v62; // [rsp+118h] [rbp+18h] BYREF
  __int128 v63; // [rsp+120h] [rbp+20h]
  __int128 v64; // [rsp+130h] [rbp+30h] BYREF
  __int128 v65; // [rsp+140h] [rbp+40h]
  void *v66[2]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v67; // [rsp+160h] [rbp+60h]
  unsigned __int64 v68; // [rsp+168h] [rbp+68h]
  _OWORD Src[2]; // [rsp+170h] [rbp+70h] BYREF
  LPWSTR lpFilename[2]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v71; // [rsp+1A0h] [rbp+A0h]
  DWORD nSize[2]; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v6 = a3;
  v7 = a4;
  v50 = a3;
  v49 = a6;
  v44 = a4;
  v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    v47 = v6;
    *(_QWORD *)v45 = L"Enter";
    LODWORD(v46) = v7;
    v48 = a2;
    *(_QWORD *)&Src[0] = a1;
    *(_QWORD *)&v64 = "CMidiSessionTracker::AddClientSession";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)v10,
      (__int64)byte_14008AFE9,
      v11,
      v12,
      &v64,
      (__int64)Src,
      v45,
      (__int64)&v48,
      (__int64)&v46,
      &v47);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  Src[0] = *(_OWORD *)a2;
  CMidiSessionTracker::FindSession(a1, &v64, Src, v7);
  if ( (_QWORD)v64 == *(_QWORD *)(a1 + 32) )
  {
    v68 = 7;
    v67 = 0;
    *(_OWORD *)v66 = 0;
    LOWORD(v66[0]) = 0;
    LOWORD(v46) = 0;
    v71 = 0;
    *(_OWORD *)lpFilename = 0;
    *(_QWORD *)nSize = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)lpFilename, &v46, 1u);
    std::wstring::resize(lpFilename);
    v17 = (WCHAR *)lpFilename;
    if ( *(_QWORD *)nSize > 7u )
      v17 = lpFilename[0];
    v18 = -1;
    if ( K32GetModuleFileNameExW(*a5, 0, v17, nSize[0]) )
    {
      v19 = lpFilename;
      if ( *(_QWORD *)nSize > 7u )
        v19 = (LPWSTR *)lpFilename[0];
      v64 = 0;
      v65 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v64, v19, v71);
      v20 = (_QWORD *)std::filesystem::path::filename(&v64, Src);
      if ( v20[3] > 7u )
        v20 = (_QWORD *)*v20;
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)v20 + v22) );
      if ( v22 > v68 )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v66,
          v22,
          v21,
          v20);
      }
      else
      {
        v23 = 2 * v22;
        v67 = v22;
        v24 = v66;
        if ( v68 > 7 )
          v24 = (void **)v66[0];
        memmove_0(v24, v20, 2 * v22);
        *(_WORD *)((char *)v24 + v23) = 0;
        v7 = v44;
        v6 = v50;
      }
      std::wstring::~wstring((char **)Src);
      std::wstring::~wstring((char **)&v64);
    }
    else
    {
      v25 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v25 > 2u )
      {
        *(_QWORD *)&Src[0] = a1;
        *(_QWORD *)&v64 = L"Unable to get current process name";
        *(_QWORD *)v45 = "CMidiSessionTracker::AddClientSession";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (__int64)v25,
          (__int64)word_14008AACA,
          v26,
          v27,
          v45,
          (__int64)Src,
          &v64);
      }
    }
    v28 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v28 > 4u )
    {
      v31 = v66;
      *(_QWORD *)&Src[0] = v6;
      if ( v68 > 7 )
        v31 = (void **)v66[0];
      *(_QWORD *)&v64 = v31;
      v48 = L"Creating new session entry";
      v46 = "CMidiSessionTracker::AddClientSession";
      v44 = v7;
      *(_QWORD *)v45 = a2;
      v47 = (const char *)a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v28,
        (__int64)qword_14008AD00,
        v29,
        v30,
        &v46,
        (__int64)&v47,
        &v48,
        (__int64)v45,
        (__int64)&v44,
        Src,
        &v64);
    }
    v52 = 0;
    v53 = 0;
    v55 = 0;
    ticks = 0;
    *(_OWORD *)v58 = 0;
    v56 = 0;
    v51 = 0;
    v57 = 7;
    LOWORD(v55) = 0;
    v59 = 0;
    v60 = 7;
    LOWORD(v58[0]) = 0;
    v61[0] = 0;
    v61[1] = 0;
    v32 = operator new(0x70u);
    *v32 = v32;
    v32[1] = v32;
    v32[2] = v32;
    *((_WORD *)v32 + 12) = 257;
    v33 = *(_OWORD *)a2;
    v61[0] = v32;
    v62 = 0;
    v51 = v33;
    LODWORD(v52) = v7;
    v63 = 0;
    ticks = _Xtime_get_ticks();
    if ( v6 )
    {
      v64 = 0;
      v65 = 0;
      do
        ++v18;
      while ( *(_WORD *)&v6[2 * v18] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v64, v6, v18);
      v35 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, &v64);
      std::wstring::operator=((char **)v58, v35);
      std::wstring::~wstring((char **)Src);
    }
    else if ( v60 < 7 )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        v58,
        7,
        v34,
        L"Default");
    }
    else
    {
      v36 = v58;
      v59 = 7;
      if ( v60 > 7 )
        v36 = (void **)v58[0];
      memmove_0(v36, L"Default", 0xEu);
      *((_WORD *)v36 + 7) = 0;
    }
    if ( v67 )
      std::wstring::operator=(&v55, v66);
    if ( *(_QWORD *)(a1 + 32) == *(_QWORD *)(a1 + 40) )
    {
      std::vector<MidiSessionEntry>::_Emplace_reallocate<MidiSessionEntry const &>(a1 + 24, *(_QWORD *)(a1 + 32), &v51);
    }
    else
    {
      MidiSessionEntry::MidiSessionEntry(*(MidiSessionEntry **)(a1 + 32), (const struct MidiSessionEntry *)&v51);
      *(_QWORD *)(a1 + 32) += 144LL;
    }
    v37 = (_QWORD *)v49;
    if ( v49 )
    {
      v64 = *(_OWORD *)a2;
      CMidiSessionTracker::FindSession(a1, &v49, &v64, v7);
      v38 = v49;
      *v37 = v49;
      *(_QWORD *)(v38 + 24) = v38;
    }
    v39 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v39 > 4u )
    {
      v42 = v66;
      v44 = v7;
      if ( v68 > 7 )
        v42 = (void **)v66[0];
      v49 = (__int64)v42;
      *(_QWORD *)&v64 = v50;
      *(_QWORD *)v45 = L"Session created";
      v47 = "CMidiSessionTracker::AddClientSession";
      *(_QWORD *)&Src[0] = a2;
      v48 = (const wchar_t *)a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v39,
        (__int64)byte_14008ABF5,
        v40,
        v41,
        &v47,
        (__int64)&v48,
        v45,
        (__int64)Src,
        (__int64)&v44,
        &v64,
        &v49);
    }
    std::vector<unsigned __int64>::~vector<unsigned __int64>(&v62);
    std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>(v61);
    std::wstring::~wstring((char **)v58);
    std::wstring::~wstring((char **)&v55);
    std::wstring::~wstring((char **)lpFilename);
    std::wstring::~wstring((char **)v66);
    if ( a1 != -48 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    return 0;
  }
  else
  {
    v13 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v13 > 2u )
    {
      *(_QWORD *)&Src[0] = a1;
      *(_QWORD *)&v64 = L"Session already exists. Unable to add new.";
      *(_QWORD *)v45 = "CMidiSessionTracker::AddClientSession";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v13,
        (__int64)byte_14008AE05,
        v14,
        v15,
        v45,
        (__int64)Src,
        &v64);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
      (const char *)0x80070057LL,
      v43);
    if ( a1 != -48 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140039d60  push    rbp
0x140039d62  push    rbx
0x140039d63  push    rsi
0x140039d64  push    rdi
0x140039d65  push    r12
0x140039d67  push    r13
0x140039d69  push    r14
0x140039d6b  push    r15
0x140039d6d  lea     rbp, [rsp-0C8h]
0x140039d75  sub     rsp, 1C8h
0x140039d7c  mov     rax, cs:__security_cookie
0x140039d83  xor     rax, rsp
0x140039d86  mov     [rbp+100h+var_50], rax
0x140039d8d  mov     rax, [rbp+100h+arg_28]
0x140039d94  mov     rbx, r8
0x140039d97  mov     r12, [rbp+100h+arg_20]
0x140039d9e  mov     edi, r9d
0x140039da1  mov     [rbp+100h+var_170], rbx
0x140039da5  mov     r13, rdx
0x140039da8  mov     [rbp+100h+var_178], rax
0x140039dac  mov     r14, rcx
0x140039daf  mov     [rsp+200h+var_1A0], r9d
0x140039db4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140039db9  lea     rsi, aCmidisessiontr_11; "CMidiSessionTracker::AddClientSession"
0x140039dc0  mov     rcx, [rax+8]
0x140039dc4  mov     eax, [rcx]
0x140039dc6  cmp     eax, 4
0x140039dc9  jbe     short loc_140039E31
0x140039dcb  lea     rax, aEnter; "Enter"
0x140039dd2  mov     [rsp+200h+var_188], rbx
0x140039dd7  mov     qword ptr [rsp+200h+var_198], rax
0x140039ddc  lea     rdx, byte_14008AFE9
0x140039de3  lea     rax, [rsp+200h+var_188]
0x140039de8  mov     dword ptr [rsp+200h+var_190], edi
0x140039dec  mov     [rsp+200h+var_1B8], rax
0x140039df1  lea     rax, [rsp+200h+var_190]
0x140039df6  mov     [rsp+200h+var_1C0], rax
0x140039dfb  lea     rax, [rbp+100h+var_180]
0x140039dff  mov     [rsp+200h+var_1C8], rax
0x140039e04  lea     rax, [rsp+200h+var_198]
0x140039e09  mov     [rsp+200h+var_1D0], rax
0x140039e0e  lea     rax, [rbp+100h+Src]
0x140039e12  mov     [rsp+200h+var_1D8], rax
0x140039e17  lea     rax, [rbp+100h+var_D0]
0x140039e1b  mov     qword ptr [rsp+200h+var_1E0], rax
0x140039e20  mov     [rbp+100h+var_180], r13
0x140039e24  mov     qword ptr [rbp+100h+Src], r14
0x140039e28  mov     qword ptr [rbp+100h+var_D0], rsi
0x140039e2c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140039e31  lea     r15, [r14+30h]
0x140039e35  mov     rcx, r15; lpCriticalSection
0x140039e38  call    cs:__imp_EnterCriticalSection
0x140039e3e  movups  xmm0, xmmword ptr [r13+0]
0x140039e43  mov     r9d, edi
0x140039e46  lea     r8, [rbp+100h+Src]
0x140039e4a  lea     rdx, [rbp+100h+var_D0]
0x140039e4e  mov     rcx, r14
0x140039e51  movdqu  [rbp+100h+Src], xmm0
0x140039e56  call    ?FindSession@CMidiSessionTracker@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@std@@U_GUID@@K@Z; CMidiSessionTracker::FindSession(_GUID,ulong)
0x140039e5b  mov     rax, [r14+20h]
0x140039e5f  cmp     qword ptr [rbp+100h+var_D0], rax
0x140039e63  jz      loc_140039EEA
0x140039e69  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140039e6e  mov     rcx, [rax+8]
0x140039e72  mov     eax, [rcx]
0x140039e74  cmp     eax, 2
0x140039e77  jbe     short loc_140039EB5
0x140039e79  lea     rax, aSessionAlready; "Session already exists. Unable to add n"...
0x140039e80  mov     qword ptr [rbp+100h+Src], r14
0x140039e84  mov     qword ptr [rbp+100h+var_D0], rax
0x140039e88  lea     rdx, byte_14008AE05
0x140039e8f  lea     rax, [rbp+100h+var_D0]
0x140039e93  mov     qword ptr [rsp+200h+var_198], rsi
0x140039e98  mov     [rsp+200h+var_1D0], rax
0x140039e9d  lea     rax, [rbp+100h+Src]
0x140039ea1  mov     [rsp+200h+var_1D8], rax
0x140039ea6  lea     rax, [rsp+200h+var_198]
0x140039eab  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x140039eb0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140039eb5  mov     rcx, [rbp+108h]; this
0x140039ebc  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x140039ec3  mov     ebx, 80070057h
0x140039ec8  mov     edx, 92h; void *
0x140039ecd  mov     r9d, ebx; char *
0x140039ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039ed5  test    r15, r15
0x140039ed8  jz      short loc_140039EE3
0x140039eda  mov     rcx, r15; lpCriticalSection
0x140039edd  call    cs:__imp_LeaveCriticalSection
0x140039ee3  mov     eax, ebx
0x140039ee5  jmp     loc_14003A38D
0x140039eea  xor     esi, esi
0x140039eec  mov     [rbp+100h+var_98], 7
0x140039ef4  xorps   xmm0, xmm0
0x140039ef7  mov     [rbp+100h+var_A0], rsi
0x140039efb  movups  xmmword ptr [rbp+100h+var_B0], xmm0
0x140039eff  lea     rdx, [rsp+200h+var_190]
0x140039f04  mov     word ptr [rbp+100h+var_B0], si
0x140039f08  lea     r8d, [rsi+1]
0x140039f0c  mov     word ptr [rsp+200h+var_190], si
0x140039f11  lea     rcx, [rbp+100h+lpFilename]
0x140039f18  mov     [rbp+100h+var_60], rsi
0x140039f1f  movups  xmmword ptr [rbp+100h+lpFilename], xmm0
0x140039f26  mov     qword ptr [rbp+100h+nSize], rsi
0x140039f2d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140039f32  mov     edx, 105h
0x140039f37  lea     rcx, [rbp+100h+lpFilename]; Src
0x140039f3e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140039f43  mov     r9, qword ptr [rbp+100h+nSize]; nSize
0x140039f4a  lea     r8, [rbp+100h+lpFilename]
0x140039f51  mov     rcx, [r12]; hProcess
0x140039f55  cmp     r9, 7
0x140039f59  cmova   r8, [rbp+100h+lpFilename]; lpFilename
0x140039f61  xor     edx, edx; hModule
0x140039f63  call    cs:__imp_K32GetModuleFileNameExW
0x140039f69  or      r12, 0FFFFFFFFFFFFFFFFh
0x140039f6d  test    eax, eax
0x140039f6f  jz      loc_14003A026
0x140039f75  cmp     qword ptr [rbp+100h+nSize], 7
0x140039f7d  lea     rdx, [rbp+100h+lpFilename]
0x140039f84  mov     r8, [rbp+100h+var_60]
0x140039f8b  lea     rcx, [rbp+100h+var_D0]
0x140039f8f  cmova   rdx, [rbp+100h+lpFilename]
0x140039f97  xorps   xmm0, xmm0
0x140039f9a  xorps   xmm1, xmm1
0x140039f9d  movups  [rbp+100h+var_D0], xmm0
0x140039fa1  movdqu  [rbp+100h+var_C0], xmm1
0x140039fa6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140039fab  lea     rdx, [rbp+100h+Src]
0x140039faf  lea     rcx, [rbp+100h+var_D0]
0x140039fb3  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x140039fb8  cmp     qword ptr [rax+18h], 7
0x140039fbd  jbe     short loc_140039FC2
0x140039fbf  mov     rax, [rax]
0x140039fc2  mov     rdx, r12
0x140039fc5  inc     rdx
0x140039fc8  cmp     [rax+rdx*2], si
0x140039fcc  jnz     short loc_140039FC5
0x140039fce  cmp     rdx, [rbp+100h+var_98]
0x140039fd2  ja      short loc_14003A006
0x140039fd4  cmp     [rbp+100h+var_98], 7
0x140039fd9  lea     rbx, [rdx+rdx]
0x140039fdd  mov     [rbp+100h+var_A0], rdx
0x140039fe1  lea     rdi, [rbp+100h+var_B0]
0x140039fe5  cmova   rdi, [rbp+100h+var_B0]
0x140039fea  mov     r8, rbx; Size
0x140039fed  mov     rcx, rdi; void *
0x140039ff0  mov     rdx, rax; Src
0x140039ff3  call    memmove_0
0x140039ff8  mov     [rbx+rdi], si
0x140039ffc  mov     edi, [rsp+200h+var_1A0]
0x14003a000  mov     rbx, [rbp+100h+var_170]
0x14003a004  jmp     short loc_14003A012
0x14003a006  mov     r9, rax
0x14003a009  lea     rcx, [rbp+100h+var_B0]
0x14003a00d  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x14003a012  lea     rcx, [rbp+100h+Src]; void *
0x14003a016  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003a01b  lea     rcx, [rbp+100h+var_D0]; void *
0x14003a01f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003a024  jmp     short loc_14003A079
0x14003a026  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003a02b  mov     rcx, [rax+8]
0x14003a02f  mov     eax, [rcx]
0x14003a031  cmp     eax, 2
0x14003a034  jbe     short loc_14003A079
0x14003a036  lea     rax, aUnableToGetCur; "Unable to get current process name"
0x14003a03d  mov     qword ptr [rbp+100h+Src], r14
0x14003a041  mov     qword ptr [rbp+100h+var_D0], rax
0x14003a045  lea     rdx, word_14008AACA
0x14003a04c  lea     rax, aCmidisessiontr_11; "CMidiSessionTracker::AddClientSession"
0x14003a053  mov     qword ptr [rsp+200h+var_198], rax
0x14003a058  lea     rax, [rbp+100h+var_D0]
0x14003a05c  mov     [rsp+200h+var_1D0], rax
0x14003a061  lea     rax, [rbp+100h+Src]
0x14003a065  mov     [rsp+200h+var_1D8], rax
0x14003a06a  lea     rax, [rsp+200h+var_198]
0x14003a06f  mov     qword ptr [rsp+200h+var_1E0], rax
0x14003a074  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003a079  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003a07e  mov     rcx, [rax+8]
0x14003a082  mov     eax, [rcx]
0x14003a084  cmp     eax, 4
0x14003a087  jbe     loc_14003A117
0x14003a08d  cmp     [rbp+100h+var_98], 7
0x14003a092  lea     rax, [rbp+100h+var_B0]
0x14003a096  lea     rdx, qword_14008AD00
0x14003a09d  mov     qword ptr [rbp+100h+Src], rbx
0x14003a0a1  cmova   rax, [rbp+100h+var_B0]
0x14003a0a6  mov     qword ptr [rbp+100h+var_D0], rax
0x14003a0aa  lea     rax, aCreatingNewSes; "Creating new session entry"
0x14003a0b1  mov     [rbp+100h+var_180], rax
0x14003a0b5  lea     rax, aCmidisessiontr_11; "CMidiSessionTracker::AddClientSession"
0x14003a0bc  mov     [rsp+200h+var_190], rax
0x14003a0c1  lea     rax, [rbp+100h+var_D0]
0x14003a0c5  mov     [rsp+200h+var_1B0], rax
0x14003a0ca  lea     rax, [rbp+100h+Src]
0x14003a0ce  mov     [rsp+200h+var_1B8], rax
0x14003a0d3  lea     rax, [rsp+200h+var_1A0]
0x14003a0d8  mov     [rsp+200h+var_1C0], rax
0x14003a0dd  lea     rax, [rsp+200h+var_198]
0x14003a0e2  mov     [rsp+200h+var_1C8], rax
0x14003a0e7  lea     rax, [rbp+100h+var_180]
0x14003a0eb  mov     [rsp+200h+var_1D0], rax
0x14003a0f0  lea     rax, [rsp+200h+var_188]
0x14003a0f5  mov     [rsp+200h+var_1D8], rax
0x14003a0fa  lea     rax, [rsp+200h+var_190]
0x14003a0ff  mov     qword ptr [rsp+200h+var_1E0], rax
0x14003a104  mov     [rsp+200h+var_1A0], edi
0x14003a108  mov     qword ptr [rsp+200h+var_198], r13
0x14003a10d  mov     [rsp+200h+var_188], r14
0x14003a112  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14003a117  mov     eax, 7
0x14003a11c  mov     [rbp+100h+var_150], rsi
0x14003a120  xorps   xmm0, xmm0
0x14003a123  mov     [rbp+100h+var_148], rsi
0x14003a127  movups  [rbp+100h+var_138], xmm0
0x14003a12b  mov     [rbp+100h+var_140], rsi
0x14003a12f  movups  xmmword ptr [rbp+100h+var_118], xmm0
0x14003a133  lea     ecx, [rax+69h]; Size
0x14003a136  mov     [rbp+100h+var_128], rsi
0x14003a13a  movups  [rbp+100h+var_160], xmm0
0x14003a13e  mov     [rbp+100h+var_120], rax
0x14003a142  mov     word ptr [rbp+100h+var_138], si
0x14003a146  mov     [rbp+100h+var_108], rsi
0x14003a14a  mov     [rbp+100h+var_100], rax
0x14003a14e  mov     word ptr [rbp+100h+var_118], si
0x14003a152  mov     [rbp+100h+var_F8], rsi
0x14003a156  mov     [rbp+100h+var_F0], rsi
0x14003a15a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003a15f  xorps   xmm0, xmm0
0x14003a162  mov     [rax], rax
0x14003a165  mov     [rax+8], rax
0x14003a169  mov     [rax+10h], rax
0x14003a16d  mov     word ptr [rax+18h], 101h
0x14003a173  movups  xmm1, xmmword ptr [r13+0]
0x14003a178  mov     [rbp+100h+var_F8], rax
0x14003a17c  mov     [rbp+100h+var_E8], rsi
0x14003a180  movdqu  [rbp+100h+var_160], xmm1
0x14003a185  mov     dword ptr [rbp+100h+var_150], edi
0x14003a188  movdqa  [rbp+100h+var_E0], xmm0
0x14003a18d  call    cs:__imp__Xtime_get_ticks
0x14003a193  mov     [rbp+100h+var_140], rax
0x14003a197  test    rbx, rbx
0x14003a19a  jz      short loc_14003A1E8
0x14003a19c  xorps   xmm0, xmm0
0x14003a19f  xorps   xmm1, xmm1
0x14003a1a2  movups  [rbp+100h+var_D0], xmm0
0x14003a1a6  movdqu  [rbp+100h+var_C0], xmm1
0x14003a1ab  inc     r12
0x14003a1ae  cmp     [rbx+r12*2], si
0x14003a1b3  jnz     short loc_14003A1AB
0x14003a1b5  mov     r8, r12
0x14003a1b8  lea     rcx, [rbp+100h+var_D0]
0x14003a1bc  mov     rdx, rbx
0x14003a1bf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003a1c4  lea     rdx, [rbp+100h+var_D0]; void *
0x14003a1c8  lea     rcx, [rbp+100h+Src]; Src
0x14003a1cc  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x14003a1d1  mov     rdx, rax
0x14003a1d4  lea     rcx, [rbp+100h+var_118]
0x14003a1d8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14003a1dd  lea     rcx, [rbp+100h+Src]; void *
0x14003a1e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003a1e6  jmp     short loc_14003A230
0x14003a1e8  cmp     [rbp+100h+var_100], 7
0x14003a1ed  jb      short loc_14003A21B
0x14003a1ef  lea     rbx, [rbp+100h+var_118]
0x14003a1f3  mov     [rbp+100h+var_108], 7
0x14003a1fb  cmova   rbx, [rbp+100h+var_118]
0x14003a200  lea     rdx, aDefault; "Default"
0x14003a207  mov     rcx, rbx; void *
0x14003a20a  mov     r8d, 0Eh; Size
0x14003a210  call    memmove_0
0x14003a215  mov     [rbx+0Eh], si
0x14003a219  jmp     short loc_14003A230
0x14003a21b  lea     r9, aDefault; "Default"
0x14003a222  mov     edx, 7
0x14003a227  lea     rcx, [rbp+100h+var_118]
0x14003a22b  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x14003a230  cmp     [rbp+100h+var_A0], rsi
0x14003a234  jz      short loc_14003A243
0x14003a236  lea     rdx, [rbp+100h+var_B0]
0x14003a23a  lea     rcx, [rbp+100h+var_138]
0x14003a23e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003a243  mov     rax, [r14+20h]
0x14003a247  cmp     rax, [r14+28h]
0x14003a24b  jz      short loc_14003A263
0x14003a24d  lea     rdx, [rbp+100h+var_160]; struct MidiSessionEntry *
0x14003a251  mov     rcx, rax; this
0x14003a254  call    ??0MidiSessionEntry@@QEAA@AEBU0@@Z; MidiSessionEntry::MidiSessionEntry(MidiSessionEntry const &)
0x14003a259  add     qword ptr [r14+20h], 90h
0x14003a261  jmp     short loc_14003A273
0x14003a263  lea     r8, [rbp+100h+var_160]
0x14003a267  mov     rdx, rax
0x14003a26a  lea     rcx, [r14+18h]
0x14003a26e  call    ??$_Emplace_reallocate@AEBUMidiSessionEntry@@@?$vector@UMidiSessionEntry@@V?$allocator@UMidiSessionEntry@@@std@@@std@@AEAAPEAUMidiSessionEntry@@QEAU2@AEBU2@@Z; std::vector<MidiSessionEntry>::_Emplace_reallocate<MidiSessionEntry const &>(MidiSessionEntry * const,MidiSessionEntry const &)
0x14003a273  mov     rbx, [rbp+100h+var_178]
0x14003a277  test    rbx, rbx
0x14003a27a  jz      short loc_14003A2A4
  ... truncated ...
```

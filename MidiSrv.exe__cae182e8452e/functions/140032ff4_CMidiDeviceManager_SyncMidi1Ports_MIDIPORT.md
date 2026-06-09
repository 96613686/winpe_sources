# CMidiDeviceManager::SyncMidi1Ports(_MIDIPORT *)

- ea: `0x140032ff4`
- end: `0x1400347f7`
- name: `?SyncMidi1Ports@CMidiDeviceManager@@AEAAJPEAU_MIDIPORT@@@Z`
- size: `6147`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this, struct _MIDIPORT *)`
- caller_count: `3`
- callee_count: `56`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140029640`
- `0x1400324c0`
- `0x140034960`

## callees

- `0x14000179c`
- `0x14000298c`
- `0x1400054c0`
- `0x140005528`
- `0x1400060d4`
- `0x1400060ec`
- `0x1400060f8`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x14000c7f4`
- `0x14000cc2c`
- `0x14000cd78`
- `0x140012008`
- `0x140012b5c`
- `0x1400133f0`
- `0x140013528`
- `0x140013a38`
- `0x1400140c4`
- `0x14001440c`
- `0x140014688`
- `0x14001487c`
- `0x140014f04`
- `0x14001bd28`
- `0x14001c390`
- `0x14001dccc`
- `0x14001ecb4`
- `0x14001f95c`
- `0x14001fa84`
- `0x1400216cc`
- `0x1400267d4`
- `0x14002698c`
- `0x140026b34`
- `0x140026ef4`
- `0x1400274d8`
- `0x1400280b8`
- `0x140028c74`
- `0x140029128`
- `0x14002b1a0`
- `0x14002ce1c`
- `0x14002d640`
- `0x14002efd0`
- `0x14002f77c`
- `0x14002fcf0`
- `0x140030250`
- `0x14003182c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400336d5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140034790`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140034797`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400347e9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400347f0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400336d5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140034790`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140034797`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400347e9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400347f0`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x140033cb1`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x140033cb1`

## string_xrefs

- `0x14003387d`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x140033b24`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x140033cc5`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x140033d17`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x1400347ad`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall CMidiDeviceManager::SyncMidi1Ports(CMidiDeviceManager *this, struct _MIDIPORT *a2)
{
  unsigned int *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // eax
  size_t *v8; // rdi
  _QWORD *v9; // rax
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  _QWORD *v13; // rax
  unsigned int i; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  __int128 *v18; // rdx
  __int64 v19; // rcx
  __int128 *v20; // rdx
  __int64 v21; // rcx
  size_t v22; // rdx
  __int64 v23; // rcx
  LPVOID v24; // rax
  _WORD *v25; // rdx
  unsigned __int64 v26; // r8
  __int64 v27; // rax
  wchar_t **v28; // rdx
  int FunctionBlockPortInfo; // eax
  unsigned int updated; // ebx
  __int64 v31; // rdx
  unsigned __int64 v32; // r9
  wchar_t **v33; // rdx
  int GroupTerminalBlockPortInfo; // eax
  unsigned int v35; // edx
  wchar_t **v36; // rdx
  wchar_t **v37; // rdx
  int v38; // r14d
  volatile signed __int32 *v39; // rbx
  unsigned int v40; // edx
  volatile signed __int32 *v41; // rbx
  int Midi1PortNames; // eax
  char v43; // r13
  char *v44; // r15
  int **v45; // rbx
  __int64 v46; // rax
  const wchar_t *v47; // rdx
  const wchar_t *v48; // rcx
  char v49; // di
  _WORD *v50; // r12
  _QWORD *v51; // rcx
  __int64 v52; // r8
  unsigned __int64 v53; // rdx
  char *v54; // r15
  __int64 v55; // rdi
  __int64 *v56; // rcx
  __int64 v57; // rcx
  int v58; // eax
  int v59; // eax
  CMidiDeviceManager *v60; // r12
  _QWORD *v61; // rax
  int v62; // eax
  char *v63; // rcx
  unsigned int v64; // edi
  const wchar_t **v65; // r14
  unsigned int j; // eax
  _OWORD *v67; // rbx
  __int64 v68; // rdx
  _OWORD *v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  int v73; // r9d
  _DWORD *v74; // r10
  const wchar_t *v75; // rcx
  __int64 v76; // rax
  int v77; // eax
  __int64 *v78; // rax
  __int64 v79; // rcx
  const wchar_t *v80; // rdx
  unsigned __int64 v81; // r8
  unsigned __int64 v82; // r8
  wchar_t **v83; // rdx
  void *v84; // rbx
  int v85; // eax
  HANDLE v86; // rax
  __int64 v87; // rbx
  __int64 *v88; // rax
  __int64 v89; // rcx
  const wchar_t *v90; // rdx
  unsigned __int64 v91; // r8
  unsigned __int64 v92; // r8
  wchar_t **v93; // rdx
  __int64 v94; // rax
  __int64 v95; // rax
  void *v96; // rbx
  int v97; // eax
  HANDLE ProcessHeap; // rax
  __int128 *v99; // rcx
  __int64 v100; // rax
  __int128 *v101; // rax
  __int64 v102; // rdx
  _OWORD *v103; // rdx
  __int128 *v104; // rcx
  __int64 v105; // rax
  __int128 *v106; // rax
  __int64 v107; // rdx
  _OWORD *v108; // rdx
  __int64 v109; // rcx
  __int128 *v110; // rax
  unsigned __int64 v111; // rcx
  _QWORD *v112; // rdx
  int v113; // eax
  __int64 *v114; // rcx
  __int64 v115; // rdx
  __int64 v116; // rdx
  int v117; // [rsp+20h] [rbp-E0h]
  int v118; // [rsp+20h] [rbp-E0h]
  __int64 v119; // [rsp+70h] [rbp-90h] BYREF
  const char *v120; // [rsp+78h] [rbp-88h] BYREF
  int v121; // [rsp+80h] [rbp-80h] BYREF
  const char *v122; // [rsp+88h] [rbp-78h] BYREF
  __int128 v123; // [rsp+90h] [rbp-70h] BYREF
  _OWORD *v124; // [rsp+A0h] [rbp-60h]
  volatile signed __int32 *v125; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v126; // [rsp+B0h] [rbp-50h] BYREF
  char v127; // [rsp+B8h] [rbp-48h]
  CMidiDeviceManager *v128; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp-38h] BYREF
  int v130; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t **v131; // [rsp+D8h] [rbp-28h] BYREF
  int SwdPropertyFromDevice; // [rsp+E0h] [rbp-20h] BYREF
  CMidiDeviceManager *v133; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v134[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v135; // [rsp+110h] [rbp+10h] BYREF
  __int128 v136; // [rsp+120h] [rbp+20h]
  __int128 v137; // [rsp+130h] [rbp+30h]
  __int128 v138[2]; // [rsp+140h] [rbp+40h] BYREF
  char *v139; // [rsp+160h] [rbp+60h]
  int v140; // [rsp+168h] [rbp+68h]
  __int128 *v141; // [rsp+170h] [rbp+70h]
  wchar_t *S1[2]; // [rsp+190h] [rbp+90h] BYREF
  size_t N[2]; // [rsp+1A0h] [rbp+A0h]
  DEVPROPGUID fmtid; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 pid; // [rsp+1C0h] [rbp+C0h]
  __int128 v146; // [rsp+1D0h] [rbp+D0h]
  _OWORD v147[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v148; // [rsp+200h] [rbp+100h] BYREF
  int *v149; // [rsp+210h] [rbp+110h]
  unsigned __int64 v150; // [rsp+218h] [rbp+118h]
  wchar_t *S2[3]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int64 v152; // [rsp+238h] [rbp+138h]
  __int128 v153; // [rsp+240h] [rbp+140h] BYREF
  __int128 v154; // [rsp+250h] [rbp+150h]
  __int128 v155; // [rsp+260h] [rbp+160h] BYREF
  __int128 v156; // [rsp+270h] [rbp+170h]
  _OWORD Src[2]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v158; // [rsp+2A0h] [rbp+1A0h] BYREF
  char *v159[4]; // [rsp+2B0h] [rbp+1B0h] BYREF
  char *v160[15]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v161; // [rsp+348h] [rbp+248h]
  int v162; // [rsp+34Ch] [rbp+24Ch]
  volatile signed __int32 **v163; // [rsp+350h] [rbp+250h]
  __int64 v164; // [rsp+358h] [rbp+258h]
  const wchar_t ***v165; // [rsp+360h] [rbp+260h]
  __int64 v166; // [rsp+368h] [rbp+268h]
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  v133 = a2;
  LODWORD(v125) = 0;
  v4 = (unsigned int *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v7 = *v4;
  v8 = (size_t *)((char *)a2 + 40);
  v131 = (const wchar_t **)((char *)a2 + 40);
  if ( v7 <= 4 )
  {
    v131 = (const wchar_t **)((char *)a2 + 40);
  }
  else
  {
    *(_QWORD *)&v147[0] = *v8;
    v9 = (_QWORD *)((char *)a2 + 208);
    if ( *((_QWORD *)a2 + 29) > 7u )
      v9 = (_QWORD *)*v9;
    v126 = v9;
    lpMem = L"Enter";
    v128 = this;
    v120 = "CMidiDeviceManager::SyncMidi1Ports";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&byte_14008920F,
      v5,
      v6,
      &v120,
      (__int64)&v128,
      &lpMem,
      &v126,
      v147);
  }
  if ( !*((_BYTE *)this + 160) )
  {
    v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v10 > 4u )
    {
      *(_QWORD *)&v147[0] = *v8;
      v13 = (_QWORD *)((char *)a2 + 208);
      if ( *((_QWORD *)a2 + 29) > 7u )
        v13 = (_QWORD *)*v13;
      v126 = v13;
      lpMem = L"Exit: Midi 1 ports owned by endpoint builder.";
      v128 = this;
      v120 = "CMidiDeviceManager::SyncMidi1Ports";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v10,
        (__int64)&word_14008A2F6,
        v11,
        v12,
        &v120,
        (__int64)&v128,
        &lpMem,
        &v126,
        v147);
    }
    return 0;
  }
  if ( *((_BYTE *)a2 + 240) )
    return 0;
  __builtin_array_init_helper_eh<std::map<unsigned int,_PORT_INFO>>(v134);
  v148 = 0;
  v149 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v119, (__int64 *)&v148);
  std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)&v148);
  S1[1] = (wchar_t *)0x2A00000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 500";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2800000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 7";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2900000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 14";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2800000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 1";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2800000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 6";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2800000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 3";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2A00000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 180";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2900000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 50";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2A00000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 140";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2A00000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 955";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2A00000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 960";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2900000001LL;
  N[1] = (size_t)L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},16";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  S1[1] = (wchar_t *)0x2900000001LL;
  N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 19";
  S1[0] = (wchar_t *)&S1[1];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v119,
    S1);
  memset(Src, 0, sizeof(Src));
  std::wstring::_Construct<1,unsigned short const *>((char **)Src, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}", 0x26u);
  std::wstring::operator+=(Src, L" ");
  for ( i = 0; i < 0x20; ++i )
  {
    v16 = std::to_wstring(&v155, i + 200);
    std::operator+<unsigned short>(&v148, Src, v16);
    std::wstring::~wstring((char **)&v155);
    v17 = std::to_wstring(v147, i + 300);
    std::operator+<unsigned short>(&v153, Src, v17);
    std::wstring::~wstring((char **)v147);
    v18 = &v148;
    if ( v150 > 7 )
      v18 = (__int128 *)v148;
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    if ( (_DWORD)v19 )
    {
      if ( *((_WORD *)v18 + (unsigned int)v19) )
        abort();
      LODWORD(S1[1]) = 1;
      HIDWORD(S1[1]) = v19;
      N[1] = (size_t)v18;
      S1[0] = (wchar_t *)&S1[1];
    }
    else
    {
      S1[0] = 0;
    }
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
      &v119,
      S1);
    v20 = &v153;
    if ( *((_QWORD *)&v154 + 1) > 7u )
      v20 = (__int128 *)v153;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v20 + v21) );
    if ( (_DWORD)v21 )
    {
      if ( *((_WORD *)v20 + (unsigned int)v21) )
        abort();
      LODWORD(S1[1]) = 1;
      HIDWORD(S1[1]) = v21;
      N[1] = (size_t)v20;
      S1[0] = (wchar_t *)&S1[1];
    }
    else
    {
      S1[0] = 0;
    }
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
      &v119,
      S1);
    std::wstring::~wstring((char **)&v153);
    std::wstring::~wstring((char **)&v148);
  }
  v121 = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v126, &v119);
  v22 = *v8;
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)(v22 + 2 * v23) );
  if ( (_DWORD)v23 )
  {
    if ( *(_WORD *)(v22 + 2LL * (unsigned int)v23) )
      abort();
    LODWORD(S1[1]) = 1;
    HIDWORD(S1[1]) = v23;
    N[1] = v22;
    S1[0] = (wchar_t *)&S1[1];
  }
  else
  {
    S1[0] = 0;
  }
  *(_QWORD *)&v148 = S1;
  *((_QWORD *)&v148 + 1) = &v126;
  v149 = &v121;
  *(_QWORD *)&v147[0] = &qword_1400969F8;
  _InterlockedAdd64(&qword_1400969F8, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      (__int64)&v148,
      &v125,
      (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_1400969F8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_1400969F8, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      (__int64 *)v23,
      (__int64)&v125,
      (__int64)&v148);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v125,
    &v122);
  if ( v125 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v125);
  if ( v127 )
  {
    v24 = v126;
  }
  else
  {
    v24 = 0;
    v126 = 0;
  }
  if ( v24 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v126);
  v25 = (_WORD *)*v8;
  v153 = 0;
  v154 = 0;
  v26 = -1;
  do
    ++v26;
  while ( v25[v26] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v153, v25, v26);
  v27 = std::wstring::wstring((__int64)&v155, (__int64)&v153);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S2, v27);
  std::wstring::~wstring((char **)&v153);
  v120 = v122;
  if ( v122 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v122 + 8LL))(v122);
  v28 = S2;
  if ( v152 > 7 )
    v28 = (wchar_t **)S2[0];
  FunctionBlockPortInfo = CMidiDeviceManager::GetFunctionBlockPortInfo(this, v28, &v120, v134);
  updated = FunctionBlockPortInfo;
  if ( FunctionBlockPortInfo >= 0 )
  {
    v120 = v122;
    if ( v122 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v122 + 8LL))(v122);
    v37 = S2;
    if ( v152 > 7 )
      v37 = (wchar_t **)S2[0];
    updated = CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks(this, v37, &v120, a2);
    if ( (int)(updated + 0x80000000) >= 0 && updated != -2147023728 )
    {
      v31 = 3004;
      goto LABEL_57;
    }
    goto LABEL_87;
  }
  if ( FunctionBlockPortInfo != -2147023728 )
  {
    v31 = 2986;
LABEL_57:
    v32 = updated;
    goto LABEL_58;
  }
  v120 = v122;
  if ( v122 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v122 + 8LL))(v122);
  v33 = S2;
  if ( v152 > 7 )
    v33 = (wchar_t **)S2[0];
  GroupTerminalBlockPortInfo = CMidiDeviceManager::GetGroupTerminalBlockPortInfo(this, v33, &v120, v134);
  updated = GroupTerminalBlockPortInfo;
  if ( GroupTerminalBlockPortInfo >= 0 )
    goto LABEL_87;
  if ( GroupTerminalBlockPortInfo == -2147023728 )
  {
    v120 = v122;
    if ( v122 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v122 + 8LL))(v122);
    v36 = S2;
    if ( v152 > 7 )
      v36 = (wchar_t **)S2[0];
    GroupTerminalBlockPortInfo = CMidiDeviceManager::UseFallbackMidi1PortDefinition(this, v36, &v120, v134);
    updated = GroupTerminalBlockPortInfo;
    if ( GroupTerminalBlockPortInfo < 0 )
    {
      v31 = 2994;
      goto LABEL_72;
    }
LABEL_87:
    v38 = 14;
    *(_QWORD *)&v147[0] = &v120;
    v120 = v122;
    if ( v122 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v122 + 8LL))(v122);
    v39 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x28, v35);
    memcpy_s((void *const)(v39 + 7), 0x50u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 1", 0x50u);
    v125 = v39;
    v147[0] = 0u;
    WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::guid>(&v158, &v125, &v120, v147);
    *(_QWORD *)&v147[0] = &v120;
    v120 = v122;
    if ( v122 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v122 + 8LL))(v122);
    v41 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x28, v40);
    memcpy_s((void *const)(v41 + 7), 0x50u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 3", 0x50u);
    v125 = v41;
    SwdPropertyFromDevice = (unsigned __int8)WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<unsigned char>(
                                               &v125,
                                               &v120,
                                               0);
    v120 = v122;
    if ( v122 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v122 + 8LL))(v122);
    Midi1PortNames = CMidiDeviceManager::GetMidi1PortNames(this, &v120, v134);
    if ( Midi1PortNames < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC7,
        (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)Midi1PortNames);
    v43 = 0;
    v44 = (char *)this + 136;
    v45 = (int **)*((_QWORD *)this + 17);
    while ( v45 != *((int ***)this + 18) )
    {
      if ( !*((_BYTE *)*v45 + 196) )
        goto LABEL_106;
      v46 = std::wstring::wstring((__int64)&v155, (__int64)(*v45 + 52));
      WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v46);
      v38 |= 0x11u;
      v47 = (const wchar_t *)S2;
      if ( v152 > 7 )
        v47 = S2[0];
      v48 = (const wchar_t *)S1;
      if ( N[1] > 7 )
        v48 = S1[0];
      if ( (wchar_t *)N[0] == S2[2] && (!N[0] || !wmemcmp(v48, v47, N[0])) )
        v49 = 1;
      else
LABEL_106:
        v49 = 0;
      if ( (v38 & 1) != 0 )
      {
        v38 &= ~1u;
        std::wstring::~wstring((char **)S1);
      }
      if ( !v49 )
        goto LABEL_125;
      v50 = (_WORD *)*((_QWORD *)*v45 + 5);
      v51 = (_QWORD *)(std::map<unsigned int,_PORT_INFO>::operator[](&v134[**v45], *v45 + 50) + 8);
      v53 = -1;
      do
        ++v53;
      while ( v50[v53] );
      if ( v53 > v51[3] )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v51,
          v53,
          v52,
          v50);
      }
      else
      {
        v54 = v51[3] <= 7u ? (char *)v51 : (char *)*v51;
        v51[2] = v53;
        v55 = 2 * v53;
        memmove_0(v54, v50, 2 * v53);
        *(_WORD *)&v54[v55] = 0;
        v44 = (char *)this + 136;
      }
      if ( *(_BYTE *)(std::map<unsigned int,_PORT_INFO>::operator[](&v134[**v45], *v45 + 50) + 1) )
      {
LABEL_125:
        ++v45;
      }
      else
      {
        v56 = (__int64 *)*((_QWORD *)*v45 + 3);
        if ( v56 )
          v57 = *v56;
        else
          v57 = 0;
        v58 = SwDeviceInterfaceSetState(v57, *((_QWORD *)*v45 + 5), 0);
        if ( v58 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xBDE,
            (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
            (const char *)(unsigned int)v58);
        v45 = *(int ***)std::vector<std::unique_ptr<_MIDIPORT>>::erase(v44, &v126, v45);
        v43 = 1;
      }
    }
    if ( v43 )
    {
      v59 = CMidiDeviceManager::CompactPortNumbers(this);
      if ( v59 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBEA,
          (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
          (const char *)(unsigned int)v59);
    }
    v123 = 0;
    v124 = 0;
    memset_0(v138, 0, 0x48u);
    v130 = 0;
    LODWORD(v138[0]) = 72;
    v60 = v133;
    v61 = (_QWORD *)((char *)v133 + 48);
    if ( *((_QWORD *)v133 + 9) > 7u )
      v61 = (_QWORD *)*v61;
    *((_QWORD *)&v138[0] + 1) = v61;
    v140 = 0;
    v62 = memcmp_0(&GUID_00000000_0000_0000_0000_000000000000, (char *)v133 + 176, 0x10u);
    v63 = v139;
    if ( v62 )
      v63 = (char *)v60 + 176;
    v139 = v63;
    v64 = 0;
    v65 = v131;
    while ( 2 )
    {
      for ( j = 0; ; j = v121 + 1 )
      {
        v121 = j;
        if ( j > 0xF )
          break;
        v67 = &v134[v64];
        if ( *(_BYTE *)(std::map<unsigned int,_PORT_INFO>::operator[](v67, &v121) + 1)
          && *(_QWORD *)(std::map<unsigned int,_PORT_INFO>::operator[](v67, &v121) + 24) )
        {
          v68 = *((_QWORD *)&v123 + 1);
          if ( (_QWORD)v123 == *((_QWORD *)&v123 + 1) )
          {
            v135 = PKEY_MIDI_TransportLayer;
            v136 = 1u;
            *(_QWORD *)&v137 = 0x100000000DLL;
            *((_QWORD *)&v137 + 1) = &v158;
            if ( *((_OWORD **)&v123 + 1) == v124 )
            {
              std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v123, *((_QWORD *)&v123 + 1), &v135);
              v69 = (_OWORD *)*((_QWORD *)&v123 + 1);
            }
            else
            {
              **((_OWORD **)&v123 + 1) = PKEY_MIDI_TransportLayer;
              *(_OWORD *)(v68 + 16) = v136;
              *(_OWORD *)(v68 + 32) = v137;
              v69 = (_OWORD *)(*((_QWORD *)&v123 + 1) + 48LL);
              *((_QWORD *)&v123 + 1) += 48LL;
            }
            fmtid = (DEVPROPGUID)PKEY_MIDI_NativeDataFormat;
            pid = 3u;
            *(_QWORD *)&v146 = 0x100000003LL;
            *((_QWORD *)&v146 + 1) = &SwdPropertyFromDevice;
            if ( v69 == v124 )
            {
              std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v123, v69, &fmtid);
            }
            else
            {
              *v69 = PKEY_MIDI_NativeDataFormat;
              v69[1] = pid;
              v69[2] = v146;
              *((_QWORD *)&v123 + 1) += 48LL;
            }
            v70 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
                    &v122,
                    &v128);
            S1[1] = (wchar_t *)0x2800000001LL;
            N[1] = (size_t)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 6";
            S1[0] = (wchar_t *)&S1[1];
            winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
              v70,
              &v120,
              S1);
            if ( v128 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v128);
            if ( v120 )
            {
              v130 = (unsigned __int8)winrt::unbox_value<unsigned char>(&v120);
              fmtid = (DEVPROPGUID)PKEY_MIDI_SupportedDataFormats;
              pid = 6u;
              *(_QWORD *)&v146 = 0x100000003LL;
              *((_QWORD *)&v146 + 1) = &v130;
              v71 = *((_QWORD *)&v123 + 1);
              if ( *((_OWORD **)&v123 + 1) == v124 )
              {
                std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v123, *((_QWORD *)&v123 + 1), &fmtid);
              }
              else
              {
                **((_OWORD **)&v123 + 1) = PKEY_MIDI_SupportedDataFormats;
                *(_OWORD *)(v71 + 16) = pid;
                *(_OWORD *)(v71 + 32) = v146;
                *((_QWORD *)&v123 + 1) += 48LL;
              }
            }
            if ( v120 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v120);
          }
          v72 = std::map<unsigned int,_PORT_INFO>::operator[](v67, &v121);
          std::wstring::wstring((__int64)&v148, v72 + 48);
          if ( !v149 )
          {
            v74 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
            if ( *v74 > 2u )
            {
              LODWORD(v131) = v121;
              LODWORD(v125) = v64;
              v75 = *v65;
              v133 = this;
              v165 = &v131;
              v166 = 4;
              v163 = &v125;
              v164 = 4;
              if ( v75 )
              {
                v76 = -1;
                do
                  ++v76;
                while ( v75[v76] );
                v77 = 2 * v76 + 2;
              }
              else
              {
                v75 = &::S2;
                v77 = 2;
              }
              v160[14] = (char *)v75;
              v161 = v77;
              v162 = 0;
              v160[12] = (char *)L"No name provided";
              v160[13] = (char *)34;
              v160[10] = (char *)&v133;
              v160[11] = (char *)8;
              v160[8] = "CMidiDeviceManager::SyncMidi1Ports";
              v160[9] = (char *)35;
              tlgWriteTransfer_EventWriteTransfer(v74, &dword_1400893D4, 0, 0);
            }
            if ( v121 )
            {
              v87 = std::to_wstring(&fmtid, (unsigned int)(v121 + 1));
              v88 = (__int64 *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(
                                 &v122,
                                 &v126);
              *(_OWORD *)S1 = 0;
              *(_OWORD *)N = 0;
              v89 = *v88;
              if ( *v88 )
              {
                v90 = *(const wchar_t **)(v89 + 16);
                v91 = *(unsigned int *)(v89 + 4);
              }
              else
              {
                v90 = &::S2;
                v91 = 0;
              }
              std::wstring::_Construct<1,unsigned short const *>((char **)S1, v90, v91);
              v155 = 0;
              v156 = 0;
              v92 = 25;
              if ( N[0] < 0x19 )
                v92 = N[0];
              v93 = S1;
              if ( N[1] > 7 )
                v93 = (wchar_t **)S1[0];
              std::wstring::_Construct<1,unsigned short const *>((char **)&v155, v93, v92);
              v94 = std::operator+<unsigned short>(v160, &v155, L" Gr ");
              v95 = std::operator+<unsigned short>(v159, v94, v87);
              std::wstring::operator=((char **)&v148, v95);
              std::wstring::~wstring(v159);
              std::wstring::~wstring(v160);
              std::wstring::~wstring((char **)&v155);
              std::wstring::~wstring((char **)S1);
              v96 = v126;
              if ( v126 )
              {
                v97 = _InterlockedDecrement((volatile signed __int32 *)v126 + 6);
                if ( v97 )
                {
                  if ( v97 < 0 )
                    abort();
                }
                else
                {
                  ProcessHeap = WINRT_IMPL_GetProcessHeap();
                  WINRT_IMPL_HeapFree(ProcessHeap, 0, v96);
                }
                v126 = 0;
              }
              std::wstring::~wstring((char **)&fmtid);
            }
            else
            {
              v78 = (__int64 *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(
                                 &v122,
                                 &lpMem);
              *(_OWORD *)S1 = 0;
              *(_OWORD *)N = 0;
              v79 = *v78;
              if ( *v78 )
              {
                v80 = *(const wchar_t **)(v79 + 16);
                v81 = *(unsigned int *)(v79 + 4);
              }
              else
              {
                v80 = &::S2;
                v81 = 0;
              }
              std::wstring::_Construct<1,unsigned short const *>((char **)S1, v80, v81);
              v155 = 0;
              v156 = 0;
              v82 = 31;
              if ( N[0] < 0x1F )
                v82 = N[0];
              v83 = S1;
              if ( N[1] > 7 )
                v83 = (wchar_t **)S1[0];
              std::wstring::_Construct<1,unsigned short const *>((char **)&v155, v83, v82);
              std::wstring::operator=((char **)&v148, (__int64)&v155);
              std::wstring::~wstring((char **)&v155);
              std::wstring::~wstring((char **)S1);
              v84 = lpMem;
              if ( lpMem )
              {
                v85 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
                if ( v85 )
                {
                  if ( v85 < 0 )
                    abort();
                }
                else
                {
                  v86 = WINRT_IMPL_GetProcessHeap();
                  WINRT_IMPL_HeapFree(v86, 0, v84);
                }
                lpMem = 0;
              }
            }
          }
          fmtid = DEVPKEY_DeviceInterface_FriendlyName.fmtid;
          pid = DEVPKEY_DeviceInterface_FriendlyName.pid;
          LODWORD(v146) = 18;
          v99 = &v148;
          if ( v150 > 7 )
            v99 = (__int128 *)v148;
          v100 = -1;
          do
            ++v100;
          while ( *((_WORD *)v99 + v100) );
          DWORD1(v146) = 2 * v100 + 2;
          v101 = &v148;
          if ( v150 > 7 )
            v101 = (__int128 *)v148;
          *((_QWORD *)&v146 + 1) = v101;
          v102 = *((_QWORD *)&v123 + 1);
          if ( *((_OWORD **)&v123 + 1) == v124 )
          {
            std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v123, *((_QWORD *)&v123 + 1), &fmtid);
            v103 = (_OWORD *)*((_QWORD *)&v123 + 1);
          }
          else
          {
            **((_OWORD **)&v123 + 1) = DEVPKEY_DeviceInterface_FriendlyName.fmtid;
            *(_OWORD *)(v102 + 16) = pid;
            *(_OWORD *)(v102 + 32) = v146;
            v103 = (_OWORD *)(*((_QWORD *)&v123 + 1) + 48LL);
            *((_QWORD *)&v123 + 1) += 48LL;
          }
          fmtid = (DEVPROPGUID)PKEY_MIDI_CustomPortNumber;
          pid = 0x10u;
          v146 = 0u;
          if ( v103 == v124 )
          {
            std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v123, v103, &fmtid);
          }
          else
          {
            *v103 = PKEY_MIDI_CustomPortNumber;
            v103[1] = pid;
            v103[2] = v146;
            *((_QWORD *)&v123 + 1) += 48LL;
          }
          LOBYTE(v73) = v121;
          CMidiDeviceManager::GetWinMMDeviceInterfaceIdForGroupFromParentEndpoint(
            (_DWORD)this,
            (unsigned int)&v153,
            (unsigned int)&v122,
            v73,
            v64 == 0);
          fmtid = (DEVPROPGUID)PKEY_MIDI_DriverDeviceInterface;
          pid = 0x13u;
          LODWORD(v146) = 18;
          v104 = &v153;
          if ( *((_QWORD *)&v154 + 1) > 7u )
            v104 = (__int128 *)v153;
          v105 = -1;
          do
            ++v105;
          while ( *((_WORD *)v104 + v105) );
          DWORD1(v146) = 2 * v105 + 2;
          v106 = &v153;
          if ( *((_QWORD *)&v154 + 1) > 7u )
            v106 = (__int128 *)v153;
          *((_QWORD *)&v146 + 1) = v106;
          v107 = *((_QWORD *)&v123 + 1);
          if ( *((_OWORD **)&v123 + 1) == v124 )
          {
            std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v123, *((_QWORD *)&v123 + 1), &fmtid);
            v108 = (_OWORD *)*((_QWORD *)&v123 + 1);
          }
          else
          {
            **((_OWORD **)&v123 + 1) = PKEY_MIDI_DriverDeviceInterface;
            *(_OWORD *)(v107 + 16) = pid;
            *(_OWORD *)(v107 + 32) = v146;
            v108 = (_OWORD *)(*((_QWORD *)&v123 + 1) + 48LL);
            *((_QWORD *)&v123 + 1) += 48LL;
          }
          fmtid = (DEVPROPGUID)PKEY_MIDI_PortAssignedGroupIndex;
          pid = 0x12u;
          *(_QWORD *)&v146 = 0x400000007LL;
          *((_QWORD *)&v146 + 1) = &v121;
          if ( v108 == v124 )
          {
            std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v123, v108, &fmtid);
            v109 = *((_QWORD *)&v123 + 1);
          }
          else
          {
            *v108 = PKEY_MIDI_PortAssignedGroupIndex;
            v108[1] = pid;
            v108[2] = v146;
            v109 = *((_QWORD *)&v123 + 1) + 48LL;
            *((_QWORD *)&v123 + 1) += 48LL;
          }
          v110 = &v148;
          if ( v150 > 7 )
            v110 = (__int128 *)v148;
          v141 = v110;
          *(_QWORD *)&v147[0] = 0;
          v111 = 0xAAAAAAAAAAAAAAABuLL * ((v109 - (__int64)v123) >> 4);
          v112 = (_QWORD *)((char *)v60 + 112);
          if ( *((_QWORD *)v60 + 17) > 7u )
            v112 = (_QWORD *)*v112;
          v113 = CMidiDeviceManager::ActivateEndpointInternal(
                   (__int64)this,
                   v112,
                   *v65,
                   1,
                   v121,
                   v64,
                   v111,
                   0,
                   v123,
                   0,
                   v138,
                   0,
                   (void **)v147);
          updated = v113;
          if ( v113 < 0 )
          {
            v116 = 3166;
            goto LABEL_232;
          }
          v114 = *(__int64 **)(*(_QWORD *)&v147[0] + 24LL);
          if ( v114 )
            v115 = *v114;
          else
            v115 = 0;
          v113 = CMidiDeviceManager::AssignPortNumber(
                   this,
                   v115,
                   *(_QWORD *)(*(_QWORD *)&v147[0] + 40LL),
                   (unsigned int)**(_DWORD **)&v147[0]);
          updated = v113;
          if ( v113 < 0 )
          {
            v116 = 3169;
LABEL_232:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v116,
              (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
              (const char *)(unsigned int)v113,
              v118);
            std::wstring::~wstring((char **)&v153);
            std::wstring::~wstring((char **)&v148);
            std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v123);
            goto LABEL_59;
          }
          *((_QWORD *)&v123 + 1) -= 192LL;
          std::wstring::~wstring((char **)&v153);
          std::wstring::~wstring((char **)&v148);
        }
      }
      if ( ++v64 <= 1 )
        continue;
      break;
    }
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v123);
    std::wstring::~wstring((char **)S2);
    if ( v122 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
    std::wstring::~wstring((char **)Src);
    if ( v119 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v119);
    `eh vector destructor iterator'(v134, 0x10u, 2u, std::map<unsigned int,_PORT_INFO>::~map<unsigned int,_PORT_INFO>);
    return 0;
  }
  v31 = 2990;
LABEL_72:
  v32 = (unsigned int)GroupTerminalBlockPortInfo;
LABEL_58:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v31,
    (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
    (const char *)v32,
    v117);
LABEL_59:
  std::wstring::~wstring((char **)S2);
  if ( v122 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
  std::wstring::~wstring((char **)Src);
  if ( v119 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v119);
  `eh vector destructor iterator'(v134, 0x10u, 2u, std::map<unsigned int,_PORT_INFO>::~map<unsigned int,_PORT_INFO>);
  return updated;
}

```

## disassembly

```asm
0x140032ff4  mov     [rsp-8+arg_10], rbx
0x140032ff9  push    rbp
0x140032ffa  push    rsi
0x140032ffb  push    rdi
0x140032ffc  push    r12
0x140032ffe  push    r13
0x140033000  push    r14
0x140033002  push    r15
0x140033004  lea     rbp, [rsp-280h]
0x14003300c  sub     rsp, 380h
0x140033013  mov     rax, cs:__security_cookie
0x14003301a  xor     rax, rsp
0x14003301d  mov     [rbp+2B0h+var_40], rax
0x140033024  mov     r12, rdx
0x140033027  mov     [rbp+2B0h+var_2C8], rdx
0x14003302b  mov     rsi, rcx
0x14003302e  xor     r15d, r15d
0x140033031  mov     dword ptr [rbp+2B0h+var_308], r15d
0x140033035  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003303a  mov     rcx, [rax+8]
0x14003303e  mov     eax, [rcx]
0x140033040  lea     rdi, [r12+28h]
0x140033045  mov     [rbp+2B0h+var_2D8], rdi
0x140033049  lea     rbx, aCmidideviceman_12; "CMidiDeviceManager::SyncMidi1Ports"
0x140033050  cmp     eax, 4
0x140033053  jbe     short loc_1400330C8
0x140033055  mov     rax, [rdi]
0x140033058  mov     [rbp+2B0h+var_1D0], rax
0x14003305f  lea     rax, [r12+0D0h]
0x140033067  cmp     qword ptr [rax+18h], 7
0x14003306c  jbe     short loc_140033071
0x14003306e  mov     rax, [rax]
0x140033071  mov     [rbp+2B0h+var_300], rax
0x140033075  lea     rax, aEnter; "Enter"
0x14003307c  mov     [rbp+2B0h+lpMem], rax
0x140033080  mov     [rbp+2B0h+var_2F0], rsi
0x140033084  mov     [rsp+3B0h+var_338], rbx
0x140033089  lea     rax, [rbp+2B0h+var_1D0]
0x140033090  mov     [rsp+3B0h+var_370], rax
0x140033095  lea     rax, [rbp+2B0h+var_300]
0x140033099  mov     [rsp+3B0h+var_378], rax
0x14003309e  lea     rax, [rbp+2B0h+lpMem]
0x1400330a2  mov     [rsp+3B0h+var_380], rax
0x1400330a7  lea     rax, [rbp+2B0h+var_2F0]
0x1400330ab  mov     [rsp+3B0h+var_388], rax
0x1400330b0  lea     rax, [rsp+3B0h+var_338]
0x1400330b5  mov     qword ptr [rsp+3B0h+var_390], rax
0x1400330ba  lea     rdx, byte_14008920F
0x1400330c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400330c6  jmp     short loc_1400330CC
0x1400330c8  mov     [rbp+2B0h+var_2D8], rdi
0x1400330cc  cmp     [rsi+0A0h], r15b
0x1400330d3  jnz     loc_14003315C
0x1400330d9  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400330de  mov     rcx, [rax+8]
0x1400330e2  mov     eax, [rcx]
0x1400330e4  cmp     eax, 4
0x1400330e7  jbe     short loc_140033166
0x1400330e9  mov     rax, [rdi]
0x1400330ec  mov     [rbp+2B0h+var_1D0], rax
0x1400330f3  lea     rax, [r12+0D0h]
0x1400330fb  cmp     qword ptr [rax+18h], 7
0x140033100  jbe     short loc_140033105
0x140033102  mov     rax, [rax]
0x140033105  mov     [rbp+2B0h+var_300], rax
0x140033109  lea     rax, aExitMidi1Ports; "Exit: Midi 1 ports owned by endpoint bu"...
0x140033110  mov     [rbp+2B0h+lpMem], rax
0x140033114  mov     [rbp+2B0h+var_2F0], rsi
0x140033118  mov     [rsp+3B0h+var_338], rbx
0x14003311d  lea     rax, [rbp+2B0h+var_1D0]
0x140033124  mov     [rsp+3B0h+var_370], rax
0x140033129  lea     rax, [rbp+2B0h+var_300]
0x14003312d  mov     [rsp+3B0h+var_378], rax
0x140033132  lea     rax, [rbp+2B0h+lpMem]
0x140033136  mov     [rsp+3B0h+var_380], rax
0x14003313b  lea     rax, [rbp+2B0h+var_2F0]
0x14003313f  mov     [rsp+3B0h+var_388], rax
0x140033144  lea     rax, [rsp+3B0h+var_338]
0x140033149  mov     qword ptr [rsp+3B0h+var_390], rax
0x14003314e  lea     rdx, word_14008A2F6
0x140033155  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14003315a  jmp     short loc_140033166
0x14003315c  cmp     [r12+0F0h], r15b
0x140033164  jz      short loc_140033192
0x140033166  xor     eax, eax
0x140033168  mov     rcx, [rbp+2B0h+var_40]
0x14003316f  xor     rcx, rsp; StackCookie
0x140033172  call    __security_check_cookie
0x140033177  mov     rbx, [rsp+3B0h+arg_10]
0x14003317f  add     rsp, 380h
0x140033186  pop     r15
0x140033188  pop     r14
0x14003318a  pop     r13
0x14003318c  pop     r12
0x14003318e  pop     rdi
0x14003318f  pop     rsi
0x140033190  pop     rbp
0x140033191  retn
0x140033192  lea     rcx, [rbp+2B0h+var_2C0]
0x140033196  call    ??$__builtin_array_init_helper_eh@V?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@@@YAXPEAV?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@_KP6AXPEAX@Z@Z; __builtin_array_init_helper_eh<std::map<uint,_PORT_INFO>>(std::map<uint,_PORT_INFO> *,unsigned __int64,void (*)(void *))
0x14003319b  nop
0x14003319c  xorps   xmm0, xmm0
0x14003319f  movdqu  [rbp+2B0h+var_1B0], xmm0
0x1400331a7  mov     [rbp+2B0h+var_1A0], r15
0x1400331ae  lea     rdx, [rbp+2B0h+var_1B0]
0x1400331b5  lea     rcx, [rsp+3B0h+var_340]
0x1400331ba  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x1400331bf  nop
0x1400331c0  lea     rcx, [rbp+2B0h+var_1B0]
0x1400331c7  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1400331cc  mov     r13d, 1
0x1400331d2  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x1400331d9  lea     r14d, [r13+29h]
0x1400331dd  mov     dword ptr [rbp+2B0h+S1+0Ch], r14d
0x1400331e4  lea     rax, a3f114a6a11fa4b_9; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400331eb  mov     [rbp+2B0h+N+8], rax
0x1400331f2  lea     rax, [rbp+2B0h+S1+8]
0x1400331f9  mov     [rbp+2B0h+S1], rax
0x140033200  lea     rdx, [rbp+2B0h+S1]
0x140033207  lea     rcx, [rsp+3B0h+var_340]
0x14003320c  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140033211  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x140033218  mov     dword ptr [rbp+2B0h+S1+0Ch], 28h ; '('
0x140033222  lea     rax, a3f114a6a11fa4b_3; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140033229  mov     [rbp+2B0h+N+8], rax
0x140033230  lea     rax, [rbp+2B0h+S1+8]
0x140033237  mov     [rbp+2B0h+S1], rax
0x14003323e  lea     rdx, [rbp+2B0h+S1]
0x140033245  lea     rcx, [rsp+3B0h+var_340]
0x14003324a  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14003324f  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x140033256  lea     ebx, [r13+28h]
0x14003325a  mov     dword ptr [rbp+2B0h+S1+0Ch], ebx
0x140033260  lea     rax, a3f114a6a11fa4b_8; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140033267  mov     [rbp+2B0h+N+8], rax
0x14003326e  lea     rax, [rbp+2B0h+S1+8]
0x140033275  mov     [rbp+2B0h+S1], rax
0x14003327c  lea     rdx, [rbp+2B0h+S1]
0x140033283  lea     rcx, [rsp+3B0h+var_340]
0x140033288  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14003328d  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x140033294  mov     dword ptr [rbp+2B0h+S1+0Ch], 28h ; '('
0x14003329e  lea     rax, a3f114a6a11fa4b_15; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400332a5  mov     [rbp+2B0h+N+8], rax
0x1400332ac  lea     rax, [rbp+2B0h+S1+8]
0x1400332b3  mov     [rbp+2B0h+S1], rax
0x1400332ba  lea     rdx, [rbp+2B0h+S1]
0x1400332c1  lea     rcx, [rsp+3B0h+var_340]
0x1400332c6  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1400332cb  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x1400332d2  mov     dword ptr [rbp+2B0h+S1+0Ch], 28h ; '('
0x1400332dc  lea     rax, a3f114a6a11fa4b_1; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400332e3  mov     [rbp+2B0h+N+8], rax
0x1400332ea  lea     rax, [rbp+2B0h+S1+8]
0x1400332f1  mov     [rbp+2B0h+S1], rax
0x1400332f8  lea     rdx, [rbp+2B0h+S1]
0x1400332ff  lea     rcx, [rsp+3B0h+var_340]
0x140033304  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140033309  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x140033310  mov     dword ptr [rbp+2B0h+S1+0Ch], 28h ; '('
0x14003331a  lea     rax, a3f114a6a11fa4b_11; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140033321  mov     [rbp+2B0h+N+8], rax
0x140033328  lea     rax, [rbp+2B0h+S1+8]
0x14003332f  mov     [rbp+2B0h+S1], rax
0x140033336  lea     rdx, [rbp+2B0h+S1]
0x14003333d  lea     rcx, [rsp+3B0h+var_340]
0x140033342  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140033347  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x14003334e  mov     dword ptr [rbp+2B0h+S1+0Ch], r14d
0x140033355  lea     rax, a3f114a6a11fa4b_2; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14003335c  mov     [rbp+2B0h+N+8], rax
0x140033363  lea     rax, [rbp+2B0h+S1+8]
0x14003336a  mov     [rbp+2B0h+S1], rax
0x140033371  lea     rdx, [rbp+2B0h+S1]
0x140033378  lea     rcx, [rsp+3B0h+var_340]
0x14003337d  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140033382  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x140033389  mov     dword ptr [rbp+2B0h+S1+0Ch], ebx
0x14003338f  lea     rax, a3f114a6a11fa4b_4; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140033396  mov     [rbp+2B0h+N+8], rax
0x14003339d  lea     rax, [rbp+2B0h+S1+8]
0x1400333a4  mov     [rbp+2B0h+S1], rax
0x1400333ab  lea     rdx, [rbp+2B0h+S1]
0x1400333b2  lea     rcx, [rsp+3B0h+var_340]
0x1400333b7  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1400333bc  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x1400333c3  mov     dword ptr [rbp+2B0h+S1+0Ch], r14d
0x1400333ca  lea     rax, a3f114a6a11fa4b_16; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400333d1  mov     [rbp+2B0h+N+8], rax
0x1400333d8  lea     rax, [rbp+2B0h+S1+8]
0x1400333df  mov     [rbp+2B0h+S1], rax
0x1400333e6  lea     rdx, [rbp+2B0h+S1]
0x1400333ed  lea     rcx, [rsp+3B0h+var_340]
0x1400333f2  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1400333f7  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x1400333fe  mov     dword ptr [rbp+2B0h+S1+0Ch], r14d
0x140033405  lea     rax, a3f114a6a11fa4b_12; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14003340c  mov     [rbp+2B0h+N+8], rax
0x140033413  lea     rax, [rbp+2B0h+S1+8]
0x14003341a  mov     [rbp+2B0h+S1], rax
0x140033421  lea     rdx, [rbp+2B0h+S1]
0x140033428  lea     rcx, [rsp+3B0h+var_340]
0x14003342d  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140033432  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x140033439  mov     dword ptr [rbp+2B0h+S1+0Ch], r14d
0x140033440  lea     rax, a3f114a6a11fa4b_10; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140033447  mov     [rbp+2B0h+N+8], rax
0x14003344e  lea     rax, [rbp+2B0h+S1+8]
0x140033455  mov     [rbp+2B0h+S1], rax
0x14003345c  lea     rdx, [rbp+2B0h+S1]
0x140033463  lea     rcx, [rsp+3B0h+var_340]
0x140033468  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14003346d  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x140033474  mov     dword ptr [rbp+2B0h+S1+0Ch], ebx
0x14003347a  lea     rax, a05279cb1002f4e; "{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},"...
0x140033481  mov     [rbp+2B0h+N+8], rax
0x140033488  lea     rax, [rbp+2B0h+S1+8]
0x14003348f  mov     [rbp+2B0h+S1], rax
0x140033496  lea     rdx, [rbp+2B0h+S1]
0x14003349d  lea     rcx, [rsp+3B0h+var_340]
0x1400334a2  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1400334a7  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x1400334ae  mov     dword ptr [rbp+2B0h+S1+0Ch], ebx
0x1400334b4  lea     rax, a3f114a6a11fa4b_14; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400334bb  mov     [rbp+2B0h+N+8], rax
0x1400334c2  lea     rax, [rbp+2B0h+S1+8]
0x1400334c9  mov     [rbp+2B0h+S1], rax
0x1400334d0  lea     rdx, [rbp+2B0h+S1]
0x1400334d7  lea     rcx, [rsp+3B0h+var_340]
0x1400334dc  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1400334e1  xorps   xmm0, xmm0
0x1400334e4  movups  [rbp+2B0h+Src], xmm0
0x1400334eb  xorps   xmm1, xmm1
0x1400334ee  movdqu  [rbp+2B0h+var_120], xmm1
0x1400334f6  lea     r8d, [r13+25h]
0x1400334fa  lea     rdx, sz; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}"
0x140033501  lea     rcx, [rbp+2B0h+Src]
0x140033508  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003350d  nop
0x14003350e  lea     rdx, asc_14007D9A4; " "
0x140033515  lea     rcx, [rbp+2B0h+Src]; Src
0x14003351c  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x140033521  mov     ebx, r15d
0x140033524  or      r14, 0FFFFFFFFFFFFFFFFh
0x140033528  lea     edx, [rbx+0C8h]
0x14003352e  lea     rcx, [rbp+2B0h+var_150]
0x140033535  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@I@Z; std::to_wstring(uint)
0x14003353a  nop
0x14003353b  mov     r8, rax
0x14003353e  lea     rdx, [rbp+2B0h+Src]
0x140033545  lea     rcx, [rbp+2B0h+var_1B0]
0x14003354c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x140033551  nop
0x140033552  lea     rcx, [rbp+2B0h+var_150]; void *
0x140033559  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003355e  lea     edx, [rbx+12Ch]
0x140033564  lea     rcx, [rbp+2B0h+var_1D0]
0x14003356b  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@I@Z; std::to_wstring(uint)
0x140033570  nop
0x140033571  mov     r8, rax
0x140033574  lea     rdx, [rbp+2B0h+Src]
0x14003357b  lea     rcx, [rbp+2B0h+var_170]
0x140033582  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x140033587  nop
0x140033588  lea     rcx, [rbp+2B0h+var_1D0]; void *
0x14003358f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140033594  lea     rdx, [rbp+2B0h+var_1B0]
0x14003359b  cmp     [rbp+2B0h+var_198], 7
0x1400335a3  cmova   rdx, qword ptr [rbp+2B0h+var_1B0]
0x1400335ab  mov     rcx, r14
0x1400335ae  inc     rcx
0x1400335b1  cmp     [rdx+rcx*2], r15w
0x1400335b6  jnz     short loc_1400335AE
0x1400335b8  test    ecx, ecx
0x1400335ba  jnz     short loc_1400335C5
0x1400335bc  mov     [rbp+2B0h+S1], r15
0x1400335c3  jmp     short loc_1400335F4
0x1400335c5  mov     eax, ecx
0x1400335c7  cmp     [rdx+rax*2], r15w
0x1400335cc  jnz     loc_1400347F0
0x1400335d2  mov     dword ptr [rbp+2B0h+S1+8], r13d
0x1400335d9  mov     dword ptr [rbp+2B0h+S1+0Ch], ecx
0x1400335df  mov     [rbp+2B0h+N+8], rdx
0x1400335e6  lea     rax, [rbp+2B0h+S1+8]
0x1400335ed  mov     [rbp+2B0h+S1], rax
0x1400335f4  lea     rdx, [rbp+2B0h+S1]
0x1400335fb  lea     rcx, [rsp+3B0h+var_340]
0x140033600  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140033605  lea     rdx, [rbp+2B0h+var_170]
0x14003360c  cmp     [rbp+2B0h+var_158], 7
0x140033614  cmova   rdx, qword ptr [rbp+2B0h+var_170]
0x14003361c  mov     rcx, r14
0x14003361f  inc     rcx
0x140033622  cmp     [rdx+rcx*2], r15w
0x140033627  jnz     short loc_14003361F
0x140033629  test    ecx, ecx
0x14003362b  jnz     short loc_140033636
0x14003362d  mov     [rbp+2B0h+S1], r15
0x140033634  jmp     short loc_140033665
0x140033636  mov     eax, ecx
  ... truncated ...
```

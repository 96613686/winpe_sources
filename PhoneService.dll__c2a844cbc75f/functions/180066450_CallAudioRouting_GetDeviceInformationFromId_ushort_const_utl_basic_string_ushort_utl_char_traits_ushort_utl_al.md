# CallAudioRouting::_GetDeviceInformationFromId(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,MediaDeviceCapabilities *)

- ea: `0x180066450`
- end: `0x180066eac`
- name: `?_GetDeviceInformationFromId@CallAudioRouting@@EEAAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAW4MediaDeviceCapabilities@@@Z`
- size: `2652`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800048f0`
- `0x180006b44`
- `0x180006e94`
- `0x1800091a8`
- `0x180059684`
- `0x18005cd7c`
- `0x18005f9c0`
- `0x180066450`
- `0x18008d936`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800664c3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800664c3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800664f1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006659a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800664f1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006659a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800664a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006657c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800666de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800667dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800669e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066c0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800664a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006657c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800666de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800667dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800669e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066c0f`

## string_xrefs

- `0x18006650a`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800665fc`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006669b`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180066710`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006675a`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180066818`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800668c1`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006696f`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180066a19`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180066a7f`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180066af0`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180066b62`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_GetDeviceInformationFromId(__int64 a1, const WCHAR *a2, __int64 a3, _DWORD *a4)
{
  int ActivationFactory; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  void (*v10)(void); // rax
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // eax
  BackTraceCollection *v16; // rcx
  const unsigned __int16 *v17; // rcx
  _QWORD *v18; // rcx
  const unsigned __int16 *v19; // rcx
  const unsigned __int16 *v20; // rsi
  __int64 v21; // rbx
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  int v25; // eax
  BackTraceCollection *v26; // rcx
  __int64 v27; // rbx
  HRESULT v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  int v31; // eax
  BackTraceCollection *v32; // rcx
  int v33; // eax
  BackTraceCollection *v34; // rcx
  unsigned int v35; // r8d
  __int64 v36; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // r14
  unsigned __int64 v39; // rdx
  __int64 v40; // r15
  __int64 v41; // rdi
  HRESULT v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  int v45; // eax
  BackTraceCollection *v46; // rcx
  __int64 (__fastcall ***v47)(__int64, GUID *, __int64 *); // rcx
  __int64 v48; // rcx
  __int64 (__fastcall ***v49)(__int64, GUID *, __int64 *); // rdi
  BackTraceCollection *v50; // rcx
  __int64 v51; // rcx
  __int64 (__fastcall ***v52)(__int64, GUID *, __int64 *); // rcx
  __int64 v53; // rcx
  int v54; // eax
  BackTraceCollection *v55; // rcx
  _QWORD *v56; // rcx
  __int64 v57; // rcx
  _QWORD *v58; // rbx
  __int64 v59; // rdi
  HRESULT v60; // eax
  int v61; // edx
  unsigned int v62; // r8d
  int v63; // eax
  BackTraceCollection *v64; // rcx
  __int64 (__fastcall ***v65)(_QWORD, GUID *, _QWORD *); // rcx
  int v66; // eax
  BackTraceCollection *v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rdi
  __int64 (__fastcall *v70)(__int64, HSTRING *); // rbx
  int v71; // eax
  BackTraceCollection *v72; // rcx
  __int64 v73; // r9
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 **v75; // r14
  BackTraceCollection *v76; // rcx
  __int64 v77; // rcx
  __int64 (__fastcall ***v78)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v79; // rcx
  _QWORD *v80; // rbx
  __int64 (__fastcall ***v81)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v82; // rdi
  HRESULT v83; // eax
  int v84; // edx
  unsigned int v85; // r8d
  int v86; // eax
  BackTraceCollection *v87; // rcx
  __int64 v88; // rdx
  __int64 (__fastcall ***v89)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 (__fastcall *v90)(_QWORD, GUID *, __int64 *); // rdi
  int v91; // eax
  BackTraceCollection *v92; // rcx
  int v93; // eax
  BackTraceCollection *v94; // rcx
  _BOOL8 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rcx
  __int64 (__fastcall ***v99)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v100; // rcx
  __int64 v101; // rcx
  __int64 (__fastcall ***v102)(__int64, GUID *, __int64 *); // rcx
  __int64 v103; // rcx
  _QWORD *v104; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-99h] BYREF
  HSTRING v106; // [rsp+58h] [rbp-81h] BYREF
  GUID *p_Buf1; // [rsp+60h] [rbp-79h] BYREF
  const char *v108; // [rsp+68h] [rbp-71h] BYREF
  _QWORD *v109; // [rsp+70h] [rbp-69h] BYREF
  __int64 v110; // [rsp+78h] [rbp-61h] BYREF
  __int64 (__fastcall ***v111)(__int64, GUID *, __int64 *); // [rsp+80h] [rbp-59h] BYREF
  __int64 v112; // [rsp+88h] [rbp-51h] BYREF
  __int64 (__fastcall ***v113)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-49h] BYREF
  __int64 v114; // [rsp+98h] [rbp-41h] BYREF
  _QWORD *v115; // [rsp+A0h] [rbp-39h] BYREF
  HSTRING v116; // [rsp+A8h] [rbp-31h] BYREF
  BackTraceCollection *v117; // [rsp+B0h] [rbp-29h] BYREF
  const unsigned __int16 *v118; // [rsp+B8h] [rbp-21h] BYREF
  GUID Buf1; // [rsp+C0h] [rbp-19h] BYREF
  HSTRING string[2]; // [rsp+D0h] [rbp-9h] BYREF
  __int128 v121; // [rsp+E0h] [rbp+7h]

  p_Buf1 = (GUID *)a3;
  v109 = 0;
  *(_OWORD *)string = 0;
  v121 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Devices.Enumeration.DeviceInformation",
         0x2Du,
         (HSTRING_HEADER *)&string[1],
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string[0], &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v109);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    BackTraceCollection::Capture(v7, ActivationFactory);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 381);
LABEL_5:
    v9 = v109;
    if ( !v109 )
      return v8;
    v109 = 0;
    goto LABEL_7;
  }
  v117 = 0;
  v106 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &v106);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  v15 = RoGetActivationFactory(v106, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v117);
  v16 = v117;
  v8 = v15;
  if ( v15 < 0 )
    goto LABEL_16;
  v118 = 0;
  v8 =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}(v117, &v118);
  if ( (v8 & 0x80000000) != 0 )
  {
    v17 = v118;
    if ( v118 )
    {
      v118 = 0;
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v16 = v117;
LABEL_16:
    if ( v16 )
    {
      v117 = 0;
      (*(void (__fastcall **)(BackTraceCollection *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    BackTraceCollection::Capture(v16, v8);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 384);
    v18 = v109;
    if ( !v109 )
      return v8;
    v109 = 0;
    goto LABEL_20;
  }
  v19 = (const unsigned __int16 *)v117;
  v20 = v118;
  v118 = 0;
  if ( v117 )
  {
    v117 = 0;
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v21 = *(_QWORD *)v20;
  v106 = 0;
  v22 = WindowsCreateStringReference(L"System.Devices.ContainerId", 0x1Au, &hstringHeader, &v106);
  if ( v22 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
    __debugbreak();
  }
  v25 = (*(__int64 (__fastcall **)(const unsigned __int16 *, HSTRING))(v21 + 104))(v20, v106);
  v8 = v25;
  if ( v25 < 0 )
  {
    BackTraceCollection::Capture(v26, v25);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 385);
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_5;
  }
  v27 = *(_QWORD *)v20;
  v106 = 0;
  v28 = WindowsCreateStringReference(L"System.Devices.InterfaceClassGuid", 0x21u, &hstringHeader, &v106);
  if ( v28 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
    __debugbreak();
  }
  v31 = (*(__int64 (__fastcall **)(const unsigned __int16 *, HSTRING))(v27 + 104))(v20, v106);
  v8 = v31;
  if ( v31 < 0 )
  {
    BackTraceCollection::Capture(v32, v31);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 386);
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_5;
  }
  v110 = 0;
  v33 = (**(__int64 (__fastcall ***)(const unsigned __int16 *, GUID *, __int64 *))v20)(
          v20,
          &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e,
          &v110);
  v8 = v33;
  if ( v33 < 0 )
  {
    BackTraceCollection::Capture(v34, v33);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 389);
    v36 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_5;
  }
  v37 = v109;
  v38 = -1;
  v111 = 0;
  v39 = -1;
  v40 = *v109;
  v106 = 0;
  do
    ++v39;
  while ( a2[v39] );
  if ( v39 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v39, v35);
    __debugbreak();
  }
  if ( (int)v39 + 1 < (unsigned int)v39 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v39, v35);
    __debugbreak();
  }
  v41 = v110;
  v42 = WindowsCreateStringReference(a2, v39, &hstringHeader, &v106);
  if ( v42 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
    __debugbreak();
  }
  v45 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, __int64 (__fastcall ****)(__int64, GUID *, __int64 *)))(v40 + 56))(
          v37,
          v106,
          v41,
          &v111);
  v8 = v45;
  if ( v45 < 0 )
  {
    BackTraceCollection::Capture(v46, v45);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 393);
LABEL_40:
    v47 = v111;
    if ( v111 )
    {
      v111 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v47)[2])(v47);
    }
    v48 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(v20);
    v9 = v109;
    if ( !v109 )
      return v8;
    v109 = 0;
LABEL_7:
    v10 = *(void (**)(void))(*v9 + 16LL);
LABEL_8:
    v10();
    return v8;
  }
  v49 = v111;
  v114 = 0;
  v8 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *>(v111);
  if ( (v8 & 0x80000000) != 0
    || (v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), __int64 *))(*v49)[8])(
               v49,
               &v114),
        (v8 & 0x80000000) != 0) )
  {
    BackTraceCollection::Capture(v50, v8);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 396);
LABEL_49:
    v51 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v111;
    if ( v111 )
    {
      v111 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v52)[2])(v52);
    }
    v53 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(v20);
    v18 = v109;
    if ( !v109 )
      return v8;
    v109 = 0;
LABEL_20:
    v10 = *(void (**)(void))(*v18 + 16LL);
    goto LABEL_8;
  }
  v115 = 0;
  v54 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v114 + 88LL))(v114, &v115);
  v8 = v54;
  if ( v54 < 0 )
  {
    BackTraceCollection::Capture(v55, v54);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 399);
LABEL_59:
    v56 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
    }
    v57 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    goto LABEL_40;
  }
  v58 = v115;
  v113 = 0;
  v59 = *v115;
  v106 = 0;
  v60 = WindowsCreateStringReference(L"System.Devices.ContainerId", 0x1Au, &hstringHeader, &v106);
  if ( v60 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v60, v61, v62);
    JUMPOUT(0x180066EABLL);
  }
  v63 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v59 + 48))(v58, v106, &v113);
  v8 = v63;
  if ( v63 < 0 )
  {
    BackTraceCollection::Capture(v64, v63);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 402);
LABEL_66:
    v65 = v113;
    if ( v113 )
    {
      v113 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v65)[2])(v65);
    }
    goto LABEL_59;
  }
  v112 = 0;
  v66 = (**v113)(v113, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v112);
  v8 = v66;
  if ( v66 < 0 )
  {
    BackTraceCollection::Capture(v67, v66);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 404);
    goto LABEL_70;
  }
  v69 = v112;
  v116 = 0;
  v70 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v112 + 152LL);
  WindowsDeleteString(0);
  v116 = 0;
  v71 = v70(v69, &v116);
  v8 = v71;
  if ( v71 < 0 )
  {
    BackTraceCollection::Capture(v72, v71);
    v73 = 407;
LABEL_74:
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v73);
    WindowsDeleteString(v116);
    v116 = 0;
LABEL_70:
    v68 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    goto LABEL_66;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v116, 0);
  if ( StringRawBuffer )
  {
    do
      ++v38;
    while ( StringRawBuffer[v38] );
  }
  v75 = (const unsigned __int16 **)p_Buf1;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(p_Buf1) )
  {
    v8 = -2147024882;
    BackTraceCollection::Capture(v76, -2147024882);
    Log_HREvent_17(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 408);
    WindowsDeleteString(v116);
    v77 = v112;
    v116 = 0;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    }
    v78 = v113;
    if ( v113 )
    {
      v113 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v78)[2])(v78);
    }
    v79 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v79 + 16LL))(v79);
    }
    goto LABEL_49;
  }
  v80 = v115;
  v81 = v113;
  v82 = *v115;
  if ( v113 )
  {
    v113 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v81)[2])(v81);
  }
  v106 = 0;
  v83 = WindowsCreateStringReference(L"System.Devices.InterfaceClassGuid", 0x21u, &hstringHeader, &v106);
  if ( v83 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v83, v84, v85);
    __debugbreak();
  }
  v86 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v82 + 48))(v80, v106, &v113);
  v8 = v86;
  if ( v86 < 0 )
  {
    BackTraceCollection::Capture(v87, v86);
    v73 = 410;
    goto LABEL_74;
  }
  v88 = v112;
  if ( v112 )
  {
    v112 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    v88 = v112;
  }
  v89 = v113;
  v90 = **v113;
  if ( v88 )
  {
    v112 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  }
  v91 = v90(v89, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v112);
  v8 = v91;
  if ( v91 < 0 )
  {
    BackTraceCollection::Capture(v92, v91);
    v73 = 412;
    goto LABEL_74;
  }
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v93 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v112 + 160LL))(v112, &Buf1);
  v8 = v93;
  if ( v93 < 0 )
  {
    BackTraceCollection::Capture(v94, v93);
    v73 = 414;
    goto LABEL_74;
  }
  if ( !memcmp_0(&Buf1, &DEVINTERFACE_AUDIO_RENDER, 0x10u) )
  {
    *a4 = 2;
  }
  else
  {
    v95 = memcmp_0(&Buf1, &DEVINTERFACE_AUDIO_CAPTURE, 0x10u) == 0;
    *a4 = v95;
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v117 = (BackTraceCollection *)a2;
    p_Buf1 = &Buf1;
    v118 = *v75;
    v108 = "CallAudioRouting::_GetDeviceInformationFromId";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
      v95,
      (int)word_1800AA212,
      v96,
      v97,
      (const unsigned __int16 **)&v108,
      (const unsigned __int16 **)&v117,
      &v118,
      (__int64 *)&p_Buf1);
  }
  WindowsDeleteString(v116);
  v98 = v112;
  v116 = 0;
  if ( v112 )
  {
    v112 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
  }
  v99 = v113;
  if ( v113 )
  {
    v113 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v99)[2])(v99);
  }
  v100 = v115;
  if ( v115 )
  {
    v115 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v100 + 16LL))(v100);
  }
  v101 = v114;
  if ( v114 )
  {
    v114 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
  }
  v102 = v111;
  if ( v111 )
  {
    v111 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v102)[2])(v102);
  }
  v103 = v110;
  if ( v110 )
  {
    v110 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
  }
  (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(v20);
  v104 = v109;
  if ( v109 )
  {
    v109 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v104 + 16LL))(v104);
  }
  return 0;
}

```

## disassembly

```asm
0x180066450  mov     [rsp-8+arg_0], rbx
0x180066455  push    rbp
0x180066456  push    rsi
0x180066457  push    rdi
0x180066458  push    r12
0x18006645a  push    r13
0x18006645c  push    r14
0x18006645e  push    r15
0x180066460  lea     rbp, [rsp-27h]
0x180066465  sub     rsp, 100h
0x18006646c  mov     rax, cs:__security_cookie
0x180066473  xor     rax, rsp
0x180066476  mov     [rbp+57h+var_40], rax
0x18006647a  xorps   xmm0, xmm0
0x18006647d  mov     [rbp+57h+var_D0], r8
0x180066481  xor     edi, edi
0x180066483  lea     r8, [rbp+57h+string+8]; hstringHeader
0x180066487  mov     r12, r9
0x18006648a  mov     [rbp+57h+var_C0], rdi
0x18006648e  mov     r13, rdx
0x180066491  lea     r9, [rbp+57h+string]; string
0x180066495  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x18006649c  lea     edx, [rdi+2Dh]; length
0x18006649f  movups  xmmword ptr [rbp+57h+string], xmm0
0x1800664a3  movups  [rbp+57h+var_50], xmm0
0x1800664a7  call    cs:__imp_WindowsCreateStringReference
0x1800664ad  lea     r14d, [rdi+1]
0x1800664b1  test    eax, eax
0x1800664b3  jns     short loc_1800664C9
0x1800664b5  xor     r9d, r9d; lpArguments
0x1800664b8  xor     r8d, r8d; nNumberOfArguments
0x1800664bb  mov     edx, r14d; dwExceptionFlags
0x1800664be  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800664c3  call    cs:__imp_RaiseException
0x1800664c9  mov     rcx, [rbp+57h+var_C0]
0x1800664cd  test    rcx, rcx
0x1800664d0  jz      short loc_1800664E2
0x1800664d2  mov     [rbp+57h+var_C0], rdi
0x1800664d6  mov     rax, [rcx]
0x1800664d9  mov     rax, [rax+10h]
0x1800664dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664e2  mov     rcx, [rbp+57h+string]
0x1800664e6  lea     r8, [rbp+57h+var_C0]
0x1800664ea  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x1800664f1  call    cs:__imp_RoGetActivationFactory
0x1800664f7  mov     ebx, eax
0x1800664f9  test    eax, eax
0x1800664fb  jns     short loc_18006655D
0x1800664fd  mov     edx, eax; int
0x1800664ff  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180066504  mov     r9d, 17Dh
0x18006650a  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180066511  mov     edx, r14d
0x180066514  mov     ecx, ebx
0x180066516  call    Log_HREvent_17
0x18006651b  mov     rcx, [rbp+57h+var_C0]
0x18006651f  test    rcx, rcx
0x180066522  jz      short loc_180066534
0x180066524  mov     [rbp+57h+var_C0], rdi
0x180066528  mov     rax, [rcx]
0x18006652b  mov     rax, [rax+10h]
0x18006652f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066534  mov     eax, ebx
0x180066536  mov     rcx, [rbp+57h+var_40]
0x18006653a  xor     rcx, rsp; StackCookie
0x18006653d  call    __security_check_cookie
0x180066542  mov     rbx, [rsp+130h+arg_0]
0x18006654a  add     rsp, 100h
0x180066551  pop     r15
0x180066553  pop     r14
0x180066555  pop     r13
0x180066557  pop     r12
0x180066559  pop     rdi
0x18006655a  pop     rsi
0x18006655b  pop     rbp
0x18006655c  retn
0x18006655d  lea     r9, [rsp+130h+var_D8]; string
0x180066562  mov     [rbp+57h+var_80], rdi
0x180066566  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x18006656b  mov     [rsp+130h+var_D8], rdi
0x180066570  mov     edx, 2Ch ; ','; length
0x180066575  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18006657c  call    cs:__imp_WindowsCreateStringReference
0x180066582  test    eax, eax
0x180066584  js      loc_180066E79
0x18006658a  mov     rcx, [rsp+130h+var_D8]
0x18006658f  lea     r8, [rbp+57h+var_80]
0x180066593  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18006659a  call    cs:__imp_RoGetActivationFactory
0x1800665a0  mov     rcx, [rbp+57h+var_80]
0x1800665a4  mov     ebx, eax
0x1800665a6  test    eax, eax
0x1800665a8  js      short loc_1800665DA
0x1800665aa  lea     rdx, [rbp+57h+var_78]
0x1800665ae  mov     [rbp+57h+var_78], rdi
0x1800665b2  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}
0x1800665b7  mov     ebx, eax
0x1800665b9  test    eax, eax
0x1800665bb  jns     short loc_18006662A
0x1800665bd  mov     rcx, [rbp+57h+var_78]
0x1800665c1  test    rcx, rcx
0x1800665c4  jz      short loc_1800665D6
0x1800665c6  mov     [rbp+57h+var_78], rdi
0x1800665ca  mov     rax, [rcx]
0x1800665cd  mov     rax, [rax+10h]
0x1800665d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665d6  mov     rcx, [rbp+57h+var_80]
0x1800665da  test    rcx, rcx
0x1800665dd  jz      short loc_1800665EF
0x1800665df  mov     [rbp+57h+var_80], rdi
0x1800665e3  mov     rax, [rcx]
0x1800665e6  mov     rax, [rax+10h]
0x1800665ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665ef  mov     edx, ebx; int
0x1800665f1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800665f6  mov     r9d, 180h
0x1800665fc  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180066603  mov     edx, r14d
0x180066606  mov     ecx, ebx
0x180066608  call    Log_HREvent_17
0x18006660d  mov     rcx, [rbp+57h+var_C0]
0x180066611  test    rcx, rcx
0x180066614  jz      loc_180066534
0x18006661a  mov     [rbp+57h+var_C0], rdi
0x18006661e  mov     rdx, [rcx]
0x180066621  mov     rax, [rdx+10h]
0x180066625  jmp     loc_18006652F
0x18006662a  mov     rcx, [rbp+57h+var_80]
0x18006662e  mov     rsi, [rbp+57h+var_78]
0x180066632  mov     [rbp+57h+var_78], rdi
0x180066636  test    rcx, rcx
0x180066639  jz      short loc_18006664B
0x18006663b  mov     [rbp+57h+var_80], rdi
0x18006663f  mov     rax, [rcx]
0x180066642  mov     rax, [rax+10h]
0x180066646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006664b  mov     rbx, [rsi]
0x18006664e  lea     r9, [rsp+130h+var_D8]; string
0x180066653  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x180066658  mov     [rsp+130h+var_D8], rdi
0x18006665d  mov     edx, 1Ah; length
0x180066662  lea     rcx, sourceString; "System.Devices.ContainerId"
0x180066669  call    cs:__imp_WindowsCreateStringReference
0x18006666f  test    eax, eax
0x180066671  js      loc_180066E81
0x180066677  mov     rdx, [rsp+130h+var_D8]
0x18006667c  mov     rcx, rsi
0x18006667f  mov     rax, [rbx+68h]
0x180066683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066688  mov     ebx, eax
0x18006668a  test    eax, eax
0x18006668c  jns     short loc_1800666C0
0x18006668e  mov     edx, eax; int
0x180066690  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180066695  mov     r9d, 181h
0x18006669b  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800666a2  mov     edx, r14d
0x1800666a5  mov     ecx, ebx
0x1800666a7  call    Log_HREvent_17
0x1800666ac  mov     rdx, [rsi]
0x1800666af  mov     rax, [rdx+10h]
0x1800666b3  mov     rcx, rsi
0x1800666b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666bb  jmp     loc_18006651B
0x1800666c0  mov     rbx, [rsi]
0x1800666c3  lea     r9, [rsp+130h+var_D8]; string
0x1800666c8  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x1800666cd  mov     [rsp+130h+var_D8], rdi
0x1800666d2  mov     edx, 21h ; '!'; length
0x1800666d7  lea     rcx, aSystemDevicesI; "System.Devices.InterfaceClassGuid"
0x1800666de  call    cs:__imp_WindowsCreateStringReference
0x1800666e4  test    eax, eax
0x1800666e6  js      loc_180066E89
0x1800666ec  mov     rdx, [rsp+130h+var_D8]
0x1800666f1  mov     rcx, rsi
0x1800666f4  mov     rax, [rbx+68h]
0x1800666f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666fd  mov     ebx, eax
0x1800666ff  test    eax, eax
0x180066701  jns     short loc_18006672A
0x180066703  mov     edx, eax; int
0x180066705  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006670a  mov     r9d, 182h
0x180066710  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180066717  mov     edx, r14d
0x18006671a  mov     ecx, ebx
0x18006671c  call    Log_HREvent_17
0x180066721  mov     rcx, [rsi]
0x180066724  mov     rax, [rcx+10h]
0x180066728  jmp     short loc_1800666B3
0x18006672a  mov     [rbp+57h+var_B8], rdi
0x18006672e  lea     r8, [rbp+57h+var_B8]
0x180066732  mov     rax, [rsi]
0x180066735  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x18006673c  mov     rcx, rsi
0x18006673f  mov     rax, [rax]
0x180066742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066747  mov     ebx, eax
0x180066749  test    eax, eax
0x18006674b  jns     short loc_180066790
0x18006674d  mov     edx, eax; int
0x18006674f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180066754  mov     r9d, 185h
0x18006675a  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180066761  mov     edx, r14d
0x180066764  mov     ecx, ebx
0x180066766  call    Log_HREvent_17
0x18006676b  mov     rcx, [rbp+57h+var_B8]
0x18006676f  test    rcx, rcx
0x180066772  jz      short loc_180066784
0x180066774  mov     [rbp+57h+var_B8], rdi
0x180066778  mov     rax, [rcx]
0x18006677b  mov     rax, [rax+10h]
0x18006677f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066784  mov     rax, [rsi]
0x180066787  mov     rax, [rax+10h]
0x18006678b  jmp     loc_1800666B3
0x180066790  mov     rbx, [rbp+57h+var_C0]
0x180066794  or      r14, 0FFFFFFFFFFFFFFFFh
0x180066798  mov     [rbp+57h+var_B0], rdi
0x18006679c  mov     rdx, r14
0x18006679f  mov     r15, [rbx]
0x1800667a2  mov     [rsp+130h+var_D8], rdi
0x1800667a7  inc     rdx; int
0x1800667aa  cmp     [r13+rdx*2+0], di
0x1800667b0  jnz     short loc_1800667A7
0x1800667b2  mov     eax, 0FFFFFFFFh
0x1800667b7  cmp     rdx, rax
0x1800667ba  ja      loc_180066E6E
0x1800667c0  lea     eax, [rdx+1]
0x1800667c3  cmp     eax, edx
0x1800667c5  jb      loc_180066E91
0x1800667cb  mov     rdi, [rbp+57h+var_B8]
0x1800667cf  lea     r9, [rsp+130h+var_D8]; string
0x1800667d4  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x1800667d9  mov     rcx, r13; sourceString
0x1800667dc  call    cs:__imp_WindowsCreateStringReference
0x1800667e2  test    eax, eax
0x1800667e4  js      loc_180066E9C
0x1800667ea  mov     rdx, [rsp+130h+var_D8]
0x1800667ef  lea     r9, [rbp+57h+var_B0]
0x1800667f3  mov     rax, [r15+38h]
0x1800667f7  mov     r8, rdi
0x1800667fa  mov     rcx, rbx
0x1800667fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066802  xor     r15d, r15d
0x180066805  mov     ebx, eax
0x180066807  test    eax, eax
0x180066809  jns     short loc_180066881
0x18006680b  mov     edx, eax; int
0x18006680d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180066812  mov     r9d, 189h
0x180066818  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006681f  lea     edx, [r15+1]
0x180066823  mov     ecx, ebx
0x180066825  call    Log_HREvent_17
0x18006682a  mov     rcx, [rbp+57h+var_B0]
0x18006682e  test    rcx, rcx
0x180066831  jz      short loc_180066843
0x180066833  mov     [rbp+57h+var_B0], r15
0x180066837  mov     rax, [rcx]
0x18006683a  mov     rax, [rax+10h]
0x18006683e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066843  mov     rcx, [rbp+57h+var_B8]
0x180066847  test    rcx, rcx
0x18006684a  jz      short loc_18006685C
0x18006684c  mov     [rbp+57h+var_B8], r15
0x180066850  mov     rax, [rcx]
0x180066853  mov     rax, [rax+10h]
0x180066857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006685c  mov     rax, [rsi]
0x18006685f  mov     rcx, rsi
0x180066862  mov     rax, [rax+10h]
0x180066866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006686b  mov     rcx, [rbp+57h+var_C0]
0x18006686f  test    rcx, rcx
0x180066872  jz      loc_180066534
0x180066878  mov     [rbp+57h+var_C0], r15
0x18006687c  jmp     loc_180066528
0x180066881  mov     rdi, [rbp+57h+var_B0]
0x180066885  mov     rcx, rdi
0x180066888  mov     [rbp+57h+var_98], r15
0x18006688c  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180066891  mov     ebx, eax
0x180066893  test    eax, eax
0x180066895  js      short loc_1800668B4
0x180066897  mov     rax, [rdi]
0x18006689a  lea     rdx, [rbp+57h+var_98]
0x18006689e  mov     rcx, rdi
0x1800668a1  mov     rax, [rax+40h]
0x1800668a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668aa  mov     ebx, eax
0x1800668ac  test    eax, eax
0x1800668ae  jns     loc_180066944
0x1800668b4  mov     edx, ebx; int
0x1800668b6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800668bb  mov     r9d, 18Ch
0x1800668c1  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800668c8  mov     edx, 1
0x1800668cd  mov     ecx, ebx
  ... truncated ...
```

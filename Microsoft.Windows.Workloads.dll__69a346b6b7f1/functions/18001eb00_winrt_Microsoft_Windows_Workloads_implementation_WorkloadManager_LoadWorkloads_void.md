# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::LoadWorkloads(void)

- ea: `0x18001eb00`
- end: `0x180021194`
- name: `?LoadWorkloads@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXXZ`
- size: `9876`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *__hidden this)`
- caller_count: `1`
- callee_count: `119`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cc10`

## callees

- `0x1800027c0`
- `0x1800027d0`
- `0x180002850`
- `0x1800029f0`
- `0x180002ad0`
- `0x180003db0`
- `0x1800040a0`
- `0x180004120`
- `0x180004410`
- `0x180004810`
- `0x180004a00`
- `0x180004c10`
- `0x1800056e0`
- `0x1800067b0`
- `0x1800067e0`
- `0x180006810`
- `0x180006840`
- `0x180006870`
- `0x1800068a0`
- `0x180006910`
- `0x18000a350`
- `0x18000c890`
- `0x18000db50`
- `0x18000e420`
- `0x1800101e0`
- `0x180013330`
- `0x180013350`
- `0x1800139b0`
- `0x180013a50`
- `0x180013ac0`
- `0x180013bd0`
- `0x180013e50`
- `0x1800143f0`
- `0x180014df0`
- `0x180014e70`
- `0x180015220`
- `0x180015250`
- `0x180015410`
- `0x1800155c0`
- `0x1800157c0`
- `0x180015df0`
- `0x180017030`
- `0x180017070`
- `0x18001e1f0`
- `0x18001e310`
- `0x18001e7d0`
- `0x18001eb00`
- `0x1800211a0`
- `0x180021210`
- `0x1800212e0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001ed19`
- `KERNEL32!LoadLibraryExW` at `0x18001ed19`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f98b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f992`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f999`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f9a0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020516`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002051d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800205d5`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f76`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f7d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f84`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f8b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f98b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f992`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f999`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001f9a0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020516`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002051d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800205d5`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f76`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f7d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f84`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180020f8b`

## string_xrefs

- `0x180020fb3`: `Error parsing workloads JSON file`
- `0x18001f644`: `ManifestPackage`
- `0x18001f66b`: `ManifestPackage`
- `0x1800210ab`: `' not found in workloads16SchemaCompat_packageFamilyNameToVectorSpaceMap.`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::LoadWorkloads(
        winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *this)
{
  winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *v1; // r13
  int v2; // r12d
  _DWORD *v3; // rbx
  char v4; // si
  char v5; // di
  bool v6; // al
  int v7; // ecx
  unsigned int v8; // ebx
  __int64 DefaultResourceDllPath; // rax
  char *v10; // rsi
  char v11; // r14
  const WCHAR *v12; // rax
  HMODULE Library; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  __int64 v16; // rax
  __int64 v17; // rax
  char v18; // bl
  int v19; // ebx
  const wchar_t *v20; // rax
  const wchar_t *v21; // rax
  _QWORD *NamedString; // rax
  _OWORD *v23; // rax
  __int64 v24; // rax
  int v25; // r15d
  unsigned int v26; // r13d
  int v27; // edi
  int v28; // r12d
  int v29; // eax
  LPVOID v30; // rcx
  int v31; // eax
  LPVOID v32; // r15
  const wchar_t *v33; // rdx
  unsigned __int64 v34; // r8
  __int64 v35; // rcx
  char v36; // al
  size_t v37; // rcx
  bool v38; // bl
  int v39; // eax
  HANDLE v40; // rax
  const wchar_t *v41; // rdx
  unsigned __int64 v42; // r8
  __int64 v43; // rcx
  __int64 *v44; // rax
  __int64 *v45; // rbx
  __int64 *v46; // r14
  const wchar_t *v47; // rcx
  const wchar_t *v48; // rdx
  size_t v49; // rdi
  size_t v50; // rsi
  size_t v51; // r8
  int v52; // eax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  int v56; // eax
  HANDLE v57; // rax
  volatile signed __int32 *v58; // rbx
  _QWORD *v59; // rax
  struct winrt::impl::hstring_header *v60; // rdx
  volatile signed __int32 *v61; // rsi
  int v62; // r12d
  volatile signed __int32 *v63; // rdi
  wchar_t *v64; // r14
  int v65; // eax
  HANDLE ProcessHeap; // rax
  void *v67; // rbx
  int v68; // eax
  HANDLE v69; // rax
  int v70; // eax
  HANDLE v71; // rax
  unsigned int v72; // r15d
  int v73; // r12d
  int v74; // eax
  winrt::impl *v75; // rbx
  int v76; // eax
  int v77; // eax
  unsigned int v78; // eax
  unsigned int v79; // esi
  int v80; // r14d
  int v81; // eax
  struct winrt::impl::hstring_header *v82; // rdx
  volatile signed __int32 *v83; // rbx
  wchar_t *v84; // rdi
  int v85; // eax
  HANDLE v86; // rax
  void *v87; // rbx
  int v88; // eax
  HANDLE v89; // rax
  _QWORD *NamedArray; // rax
  __int64 *v91; // rax
  _QWORD *v92; // rax
  _QWORD *v93; // rax
  const wchar_t *v94; // rax
  const struct IUnknown **v95; // rax
  const wchar_t *v96; // rax
  const struct IUnknown **v97; // rax
  __int64 v98; // rax
  __int64 *v99; // rbx
  struct IUnknownVtbl **v100; // r12
  _QWORD *v101; // rax
  struct winrt::impl::hstring_header *v102; // rdx
  winrt::impl **v103; // r14
  winrt::impl **i; // r13
  struct IUnknownVtbl *lpVtbl; // rdi
  __int64 v106; // rax
  __int64 v107; // rcx
  __int128 v108; // xmm6
  wchar_t *v109; // r15
  wchar_t **v110; // rsi
  struct winrt::impl::hstring_header *v111; // rdx
  ULONG (__stdcall *Release)(IUnknown *); // rcx
  struct IUnknownVtbl *v113; // rdi
  char *v114; // rsi
  volatile signed __int32 *v115; // r14
  _QWORD *v116; // rax
  wchar_t *v117; // rcx
  volatile signed __int32 *v118; // rsi
  struct winrt::impl::hstring_header *v119; // rdx
  __int64 v120; // rax
  volatile signed __int32 *v121; // rcx
  struct IUnknownVtbl *v122; // rdi
  int v123; // eax
  HANDLE v124; // rax
  __int64 **v125; // rax
  __int64 *j; // rax
  __int64 *k; // rax
  unsigned int v128; // r15d
  __int128 v129; // xmm6
  int v130; // eax
  struct IUnknownVtbl *v131; // rbx
  int v132; // eax
  int v133; // eax
  int v134; // eax
  winrt::impl *v135; // r12
  int v136; // eax
  __int64 *v137; // rax
  _QWORD *v138; // rax
  _QWORD *v139; // rax
  size_t *v140; // rbx
  const wchar_t *v141; // rdx
  unsigned __int64 v142; // r8
  size_t v143; // rsi
  __int64 v144; // rcx
  struct IUnknownVtbl *v145; // rsi
  volatile signed __int32 *v146; // rdi
  const wchar_t *v147; // rdx
  unsigned __int64 v148; // r8
  __int64 v149; // rcx
  __int64 *v150; // rax
  __int64 *v151; // rbx
  __int64 *v152; // r13
  const wchar_t *v153; // rcx
  const wchar_t *v154; // rdx
  size_t v155; // r15
  size_t v156; // r14
  size_t v157; // r8
  int v158; // eax
  volatile signed __int32 *v159; // rbx
  const wchar_t *v160; // r14
  struct winrt::impl::hstring_header *v161; // rdx
  struct winrt::impl::hstring_header *v162; // rdx
  __int64 v163; // rax
  winrt::impl *v164; // rcx
  __int64 v165; // rax
  int v166; // eax
  HANDLE v167; // rax
  int v168; // eax
  HANDLE v169; // rax
  int v170; // eax
  HANDLE v171; // rax
  void *v172; // rbx
  int v173; // eax
  HANDLE v174; // rax
  __int64 v175; // rcx
  winrt::hresult *v176; // rax
  unsigned int v177; // eax
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // rax
  __int64 v181; // rax
  const wchar_t *v182; // rax
  winrt::hresult *v183; // rax
  unsigned int v184; // eax
  char *v185; // [rsp+28h] [rbp-E0h]
  char *v186; // [rsp+30h] [rbp-D8h]
  __int64 v187; // [rsp+38h] [rbp-D0h]
  winrt::impl **v188; // [rsp+48h] [rbp-C0h] BYREF
  winrt::impl *v189; // [rsp+50h] [rbp-B8h] BYREF
  volatile signed __int32 *v190; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v191; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v192; // [rsp+70h] [rbp-98h]
  const wchar_t *v193; // [rsp+78h] [rbp-90h]
  struct IUnknownVtbl *v194; // [rsp+80h] [rbp-88h] BYREF
  void *p_lpMem; // [rsp+88h] [rbp-80h] BYREF
  wchar_t **v196; // [rsp+90h] [rbp-78h]
  volatile signed __int32 *v197; // [rsp+98h] [rbp-70h] BYREF
  volatile signed __int32 *v198; // [rsp+A0h] [rbp-68h] BYREF
  volatile signed __int32 *v199[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v200[2]; // [rsp+B8h] [rbp-50h] BYREF
  const wchar_t *v201; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v202; // [rsp+E0h] [rbp-28h]
  _DWORD *v203; // [rsp+E8h] [rbp-20h] BYREF
  _DWORD v204[4]; // [rsp+F0h] [rbp-18h] BYREF
  const wchar_t *v205; // [rsp+100h] [rbp-8h]
  _QWORD v206[2]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v207[4]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v208[4]; // [rsp+138h] [rbp+30h] BYREF
  winrt::impl *v209; // [rsp+158h] [rbp+50h] BYREF
  winrt::impl *v210; // [rsp+160h] [rbp+58h] BYREF
  struct IUnknown v211; // [rsp+168h] [rbp+60h] BYREF
  winrt::impl *v212; // [rsp+170h] [rbp+68h] BYREF
  LPVOID lpMem; // [rsp+178h] [rbp+70h] BYREF
  char v214[8]; // [rsp+180h] [rbp+78h] BYREF
  struct IUnknownVtbl *v215; // [rsp+188h] [rbp+80h] BYREF
  LPVOID v216; // [rsp+190h] [rbp+88h] BYREF
  wchar_t *S2[2]; // [rsp+198h] [rbp+90h] BYREF
  size_t N; // [rsp+1A8h] [rbp+A0h]
  const wchar_t *v219; // [rsp+1B0h] [rbp+A8h]
  wchar_t *v220; // [rsp+1B8h] [rbp+B0h] BYREF
  volatile signed __int32 **v221; // [rsp+1C0h] [rbp+B8h] BYREF
  wchar_t *v222[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  size_t v223; // [rsp+1D8h] [rbp+D0h]
  const wchar_t *v224; // [rsp+1E0h] [rbp+D8h]
  winrt::impl *v225; // [rsp+1E8h] [rbp+E0h] BYREF
  LPVOID v226; // [rsp+1F0h] [rbp+E8h] BYREF
  LPVOID v227; // [rsp+1F8h] [rbp+F0h] BYREF
  void (__fastcall ***v228)(_QWORD, __int64 *, __int64 *); // [rsp+200h] [rbp+F8h] BYREF
  __int64 v229; // [rsp+208h] [rbp+100h] BYREF
  volatile signed __int32 *v230; // [rsp+210h] [rbp+108h] BYREF
  volatile signed __int32 *v231; // [rsp+218h] [rbp+110h] BYREF
  void *v232[2]; // [rsp+220h] [rbp+118h] BYREF
  __int64 v233; // [rsp+230h] [rbp+128h]
  const wchar_t *v234; // [rsp+238h] [rbp+130h]
  __int64 v235; // [rsp+240h] [rbp+138h] BYREF
  _QWORD v236[2]; // [rsp+248h] [rbp+140h] BYREF
  void (__fastcall ***v237)(_QWORD, __int64 *, __int64 *); // [rsp+258h] [rbp+150h] BYREF
  void (__fastcall ***v238)(_QWORD, __int64 *, __int64 *); // [rsp+260h] [rbp+158h] BYREF
  _QWORD v239[2]; // [rsp+268h] [rbp+160h] BYREF
  _OWORD v240[2]; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v241[32]; // [rsp+298h] [rbp+190h] BYREF
  _BYTE v242[16]; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v243; // [rsp+2C8h] [rbp+1C0h]
  __int64 v244; // [rsp+2D8h] [rbp+1D0h] BYREF
  void *v245; // [rsp+2E0h] [rbp+1D8h]
  char v246[40]; // [rsp+2F0h] [rbp+1E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+360h] [rbp+258h]

  v1 = this;
  v197 = (volatile signed __int32 *)this;
  v2 = 0;
  LODWORD(v189) = 0;
  v227 = 0;
  std::string::string(v242);
  LODWORD(v188) = 0;
  v3 = (_DWORD *)((char *)v1 + 184);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60663426>::GetImpl'::`2'::impl)
    || !(unsigned __int8)winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::TryGetHardwareInfoFromBroker(
                           (_DWORD)v1,
                           (int)v1 + 184,
                           (unsigned int)&v227,
                           (unsigned int)v242,
                           (__int64)&v188) )
  {
    v4 = 0;
    goto LABEL_6;
  }
  v4 = 1;
  if ( !v243 )
  {
LABEL_6:
    v5 = 0;
    winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DetectNpu(v1);
    goto LABEL_7;
  }
  v5 = 1;
  LODWORD(v189) = *v3;
  TraceLogger::WorkloadManagerLoadWorkloadsUsingBrokerNpuType<unsigned int>((int *)&v189);
LABEL_7:
  v6 = IsRunningOnArm64();
  v7 = 4;
  if ( v6 )
    v7 = 16;
  LODWORD(v189) = v7;
  std::set<std::wstring>::__autoclassinit2(v236);
  std::map<std::wstring,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem>::map<std::wstring,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem>(v236);
  switch ( *v3 )
  {
    case 0:
      goto LABEL_18;
    case 1:
      v8 = 2 * (unsigned __int8)std::operator==<char>((char *)v1 + 192) + 1003;
      goto LABEL_19;
    case 2:
      v8 = 1001;
      goto LABEL_19;
    case 3:
      v8 = 1002;
      goto LABEL_19;
  }
  if ( *v3 != 4 )
  {
LABEL_18:
    v8 = 1000;
    goto LABEL_19;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::AssertEnabled(`wil::Feature<__WilFeatureTraits_Feature_57003568>::GetImpl'::`2'::impl);
  v8 = 1004;
LABEL_19:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60663426>::GetImpl'::`2'::impl)
    && v4
    && (_DWORD)v188
    && *((_QWORD *)v1 + 11)
    && (DefaultResourceDllPath = winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetDefaultResourceDllPath((__int64)S2),
        v2 = 1,
        v10 = (char *)v1 + 72,
        (unsigned __int8)std::operator!=<wchar_t>((char *)v1 + 72, DefaultResourceDllPath)) )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v10 = (char *)v1 + 72;
  }
  if ( (v2 & 1) != 0 )
  {
    v2 &= ~1u;
    std::wstring::_Tidy_deallocate((__int64)S2);
  }
  if ( v11 )
  {
    v5 = 0;
    v8 = (unsigned int)v188;
  }
  std::string::string(v241);
  if ( v5 )
  {
    std::string::operator=(v241, v242);
  }
  else
  {
    std::string::string(S2);
    v12 = (const WCHAR *)std::wstring::c_str(v10);
    Library = LoadLibraryExW(v12, 0, 0);
    v227 = Library;
    if ( !Library )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x196, v14, v15);
    v16 = winrt::Microsoft::Windows::Workloads::implementation::readResourceContent(&v191, Library, v8);
    std::string::operator=(S2, v16);
    std::string::_Tidy_deallocate((__int64)&v191);
    v17 = winrt::Microsoft::Windows::Workloads::implementation::removeBOMAndConvert(&v191, S2);
    std::string::operator=(v241, v17);
    std::string::_Tidy_deallocate((__int64)&v191);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(&v227);
    std::string::_Tidy_deallocate((__int64)S2);
  }
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v235);
  S2[0] = *(wchar_t **)winrt::to_hstring<std::string,0>(&v227, v241);
  v18 = winrt::Windows::Data::Json::JsonObject::TryParse(
          (const struct winrt::param::hstring *)S2,
          (struct winrt::Windows::Data::Json::JsonObject *)&v235);
  std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v227);
  if ( !v18 )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"Error parsing workloads JSON file");
    v176 = winrt::hresult::hresult((winrt::hresult *)&v189, -2147418113);
    winrt::hresult_error::hresult_error(S2, *(unsigned int *)v176, &v191);
    throw (winrt::hresult_error *)S2;
  }
  std::unordered_map<winrt::hstring,winrt::guid>::__autoclassinit2(&v244);
  std::unordered_map<winrt::hstring,winrt::guid>::unordered_map<winrt::hstring,winrt::guid>(&v244);
  winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"Packages");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
    &v235,
    &v237,
    S2);
  std::set<std::wstring>::__autoclassinit2(v239);
  std::set<std::wstring>::set<std::wstring>(v239);
  v222[0] = (wchar_t *)&v237;
  LODWORD(v222[1]) = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
    &v237,
    (__int64)v200);
  v19 = DWORD2(v200[0]);
  if ( DWORD2(v200[0]) )
  {
    do
    {
      winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*((__int64)v222, &v209);
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
        (__int64 *)&v209,
        &v188);
      winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"FamilyName");
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
        (__int64 *)&v188,
        &v220,
        &v191);
      winrt::param::hstring::hstring((winrt::param::hstring *)&v203, L"Deprecated");
      if ( (unsigned __int8)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(
                              (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v188,
                              &v203) )
      {
        v20 = winrt::hstring::c_str((winrt::hstring *)&v220);
        std::wstring::wstring(S2, v20);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
          v239,
          v240,
          S2);
        std::wstring::_Tidy_deallocate((__int64)S2);
      }
      else
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"Version");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
          (__int64 *)&v188,
          &v221,
          S2);
        winrt::Microsoft::Windows::Management::Deployment::PackageSetItem::PackageSetItem((winrt::Microsoft::Windows::Management::Deployment::PackageSetItem *)&v215);
        S2[0] = v220;
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(
          &v215,
          S2);
        v216 = 0;
        v21 = winrt::hstring::c_str((winrt::hstring *)&v221);
        v186 = (char *)&v216 + 6;
        v185 = (char *)&v216 + 4;
        swscanf_s(v21, L"%hu.%hu.%hu.%hu", &v216, (char *)&v216 + 2);
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::MinVersion(
          &v215,
          &v216);
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::ProcessorArchitectureFilter(
          &v215,
          &v189);
        winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"VectorSpaceId");
        if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v188,
                                S2) )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"PreferredVectorSpace");
          if ( (unsigned __int8)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(
                                  (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v188,
                                  &v191) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"VectorSpaceId");
            NamedString = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                            (__int64 *)&v188,
                            &v227,
                            S2);
            v200[0] = *(_OWORD *)winrt::hstring::operator std::wstring_view(NamedString, &v201);
            winrt::guid::guid(v232, v200);
            std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v227);
            v23 = (_OWORD *)std::unordered_map<winrt::hstring,winrt::guid>::operator[](&v244, &v220);
            *v23 = *(_OWORD *)v232;
          }
        }
        v24 = std::make_pair<winrt::hstring &,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem &>(
                &p_lpMem,
                &v220,
                &v215);
        std::map<std::wstring,winrt::Microsoft::Windows::Workloads::ApiInfo>::insert<std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,0>(
          v236,
          v206,
          v24);
        std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload>::~pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload>(&p_lpMem);
        if ( v215 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v215);
        std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v221);
      }
      std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v220);
      if ( v188 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v188);
      if ( v209 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v209);
      ++LODWORD(v222[1]);
    }
    while ( LODWORD(v222[1]) != v19 );
  }
  winrt::param::hstring::hstring((winrt::param::hstring *)v207, L"Workloads");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
    &v235,
    &v238,
    v207);
  v232[0] = &v238;
  LODWORD(v232[1]) = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
    &v238,
    (__int64)&v201);
  v25 = v202;
  if ( (_DWORD)v202 )
  {
    while ( 1 )
    {
      winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*((__int64)v232, &v221);
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
        (__int64 *)&v221,
        &v226);
      winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"Id");
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
        (__int64 *)&v226,
        &v212,
        S2);
      winrt::Microsoft::Windows::Management::Deployment::PackageSet::PackageSet((winrt::Microsoft::Windows::Management::Deployment::PackageSet *)&v220);
      S2[0] = (wchar_t *)v212;
      winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSet<winrt::Microsoft::Windows::Management::Deployment::IPackageSet>::Id(
        &v220,
        S2);
      v200[0] = *(_OWORD *)winrt::hstring::operator std::wstring_view(&v212, v240);
      winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetUupUri(&v225);
      winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"Packages");
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
        (__int64 *)&v226,
        &v228,
        S2);
      winrt::hstring::hstring((winrt::hstring *)&v216, &Src);
      v26 = 0;
      winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
        &v228,
        (__int64)&p_lpMem);
      v27 = (int)v196;
      if ( (_DWORD)v196 )
        break;
LABEL_111:
      v1 = (winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *)v197;
      v58 = v197 + 4;
      lpMem = (LPVOID)(v197 + 4);
      if ( v197 != (volatile signed __int32 *)-16LL )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v197 + 4);
      v59 = winrt::impl::create_and_initialize<winrt::Microsoft::Windows::Workloads::implementation::Workload,winrt::Microsoft::Windows::Workloads::WorkloadManager &,winrt::hstring &,winrt::Microsoft::Windows::Management::Deployment::PackageSet &,winrt::hstring &>(
              (LPVOID **)&lpMem,
              &v212,
              (__int64 *)&v220,
              (winrt::impl **)&v216);
      v61 = (volatile signed __int32 *)(v59 + 2);
      if ( !v59 )
        v61 = 0;
      v190 = v61;
      v62 = v2 | 0x40;
      v63 = (volatile signed __int32 *)v212;
      v222[0] = (wchar_t *)winrt::impl::duplicate_hstring(v212, v60);
      v222[1] = (wchar_t *)v61;
      if ( v61 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
      v2 = v62 | 0x400;
      std::_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Workloads::Workload,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::Workload>>,0>>::_Emplace<std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload>>(
        (char *)v1 + 112,
        v206,
        v222);
      if ( v222[1] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v222[1]);
      v64 = v222[0];
      if ( v222[0] )
      {
        v65 = _InterlockedDecrement((volatile signed __int32 *)v222[0] + 6);
        if ( v65 )
        {
          if ( v65 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v64);
        }
        v222[0] = 0;
      }
      if ( v61 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v190);
      if ( v58 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      v67 = v216;
      if ( v216 )
      {
        v68 = _InterlockedDecrement((volatile signed __int32 *)v216 + 6);
        if ( v68 )
        {
          if ( v68 < 0 )
            abort();
          v216 = 0;
        }
        else
        {
          v69 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v69, 0, v67);
          v216 = 0;
        }
      }
      if ( v228 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v228);
      if ( v225 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v225);
      if ( v220 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v220);
      if ( v63 )
      {
        v70 = _InterlockedDecrement(v63 + 6);
        if ( v70 )
        {
          if ( v70 < 0 )
            abort();
        }
        else
        {
          v71 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v71, 0, (LPVOID)v63);
        }
        v212 = 0;
      }
      if ( v226 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v226);
      if ( v221 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v221);
      if ( ++LODWORD(v232[1]) == v25 )
        goto LABEL_154;
    }
    while ( 1 )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
        &v228,
        &v229,
        v26);
      v28 = v2 | 0x80;
      lpMem = 0;
      v29 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v229 + 96LL))(v229, &lpMem);
      if ( v29 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v29);
      }
      v30 = lpMem;
      v209 = (winrt::impl *)lpMem;
      v204[0] = 1;
      v204[1] = 10;
      v205 = L"FamilyName";
      v203 = v204;
      lpMem = 0;
      v31 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *, LPVOID *))(*(_QWORD *)v209 + 80LL))(v30, v204, &lpMem);
      if ( v31 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v31);
      }
      v32 = lpMem;
      v198 = (volatile signed __int32 *)lpMem;
      v2 = v28 | 0x300;
      if ( lpMem )
        v33 = (const wchar_t *)*((_QWORD *)lpMem + 2);
      else
        v33 = &Src;
      v191 = 0;
      v192 = 0;
      v193 = 0;
      v34 = -1;
      do
        ++v34;
      while ( v33[v34] );
      std::wstring::_Construct<1,wchar_t const *>(&v191, v33, v34);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
        v239,
        S2,
        &v191);
      v36 = std::_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Workloads::Workload,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::Workload>>,0>>::_Lower_bound_duplicate<std::wstring>(
              v35,
              N,
              &v191);
      v37 = v239[0];
      if ( v36 )
        v37 = N;
      v38 = v37 != v239[0];
      std::wstring::_Tidy_deallocate((__int64)&v191);
      if ( v38 )
      {
        if ( v32 )
        {
          v39 = _InterlockedDecrement((volatile signed __int32 *)v32 + 6);
          if ( v39 )
          {
            if ( v39 < 0 )
              goto LABEL_150;
          }
          else
          {
            v40 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v40, 0, lpMem);
          }
        }
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v209);
        if ( !v229 )
          goto LABEL_109;
        goto LABEL_108;
      }
      if ( v32 )
        v41 = (const wchar_t *)*((_QWORD *)v32 + 2);
      else
        v41 = &Src;
      *(_OWORD *)S2 = 0;
      N = 0;
      v219 = 0;
      v42 = -1;
      do
        ++v42;
      while ( v41[v42] );
      std::wstring::_Construct<1,wchar_t const *>(S2, v41, v42);
      v44 = (__int64 *)v236[0];
      v45 = *(__int64 **)(v236[0] + 8LL);
      v46 = (__int64 *)v236[0];
      if ( !*((_BYTE *)v45 + 25) )
      {
        while ( 1 )
        {
          v47 = (const wchar_t *)(v45 + 4);
          v48 = (const wchar_t *)S2;
          if ( (unsigned __int64)v219 > 7 )
            v48 = S2[0];
          v49 = v45[6];
          if ( (unsigned __int64)v45[7] > 7 )
            v47 = *(const wchar_t **)v47;
          v50 = N;
          v51 = v45[6];
          if ( N < v49 )
            v51 = N;
          v52 = wmemcmp(v47, v48, v51);
          if ( v52 )
          {
            if ( v52 < 0 )
              goto LABEL_103;
          }
          else if ( v49 < v50 )
          {
LABEL_103:
            v45 = (__int64 *)v45[2];
            goto LABEL_82;
          }
          v46 = v45;
          v45 = (__int64 *)*v45;
LABEL_82:
          if ( *((_BYTE *)v45 + 25) )
          {
            v44 = (__int64 *)v236[0];
            v27 = (int)v196;
            break;
          }
        }
      }
      if ( !*((_BYTE *)v46 + 25) )
      {
        if ( !(unsigned __int8)std::less<std::wstring>::operator()(v43, S2, v46 + 4) )
          goto LABEL_88;
        v44 = (__int64 *)v236[0];
      }
      v46 = v44;
LABEL_88:
      std::wstring::_Tidy_deallocate((__int64)S2);
      if ( v46 != (__int64 *)v236[0] )
      {
        winrt::Windows::Foundation::IUnknown::IUnknown(
          (winrt::Windows::Foundation::IUnknown *)&v188,
          (const struct IUnknown *)v46 + 8);
        winrt::Microsoft::Windows::Management::Deployment::PackageSetItem::PackageSetItem((winrt::Microsoft::Windows::Management::Deployment::PackageSetItem *)&v215);
        S2[0] = *(wchar_t **)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(
                               &v188,
                               &v227);
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(
          &v215,
          S2);
        std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v227);
        v53 = winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::MinVersion(
                &v188,
                v199);
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::MinVersion(
          &v215,
          v53);
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageUri(
          &v215,
          &v225);
        LODWORD(v189) = winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::ProcessorArchitectureFilter(&v188);
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::ProcessorArchitectureFilter(
          &v215,
          &v189);
        winrt::Microsoft::Windows::Management::Deployment::PackageSetItem::operator=(&v188, &v215);
        v54 = winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSet<winrt::Microsoft::Windows::Management::Deployment::IPackageSet>::Items(
                &v220,
                &v210);
        winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem>,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem>::Append(
          v54,
          &v188);
        if ( v210 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v210);
        if ( !v216 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"ManifestPackage");
          if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                  (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v209,
                                  S2) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"ManifestPackage");
            if ( (unsigned __int8)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
                                    (__int64 *)&v209,
                                    (__int64 *)&v191) )
            {
              v55 = winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(
                      &v188,
                      &v211);
              winrt::hstring::operator=(&v216, v55);
              std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v211);
            }
          }
        }
        if ( v215 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v215);
        if ( v188 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v188);
      }
      if ( v32 )
      {
        v56 = _InterlockedDecrement((volatile signed __int32 *)v32 + 6);
        if ( v56 )
        {
          if ( v56 < 0 )
LABEL_150:
            abort();
        }
        else
        {
          v57 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v57, 0, lpMem);
        }
      }
      if ( v209 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v209);
      if ( !v229 )
        goto LABEL_109;
LABEL_108:
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v229);
LABEL_109:
      if ( ++v26 == v27 )
      {
        v25 = v202;
        goto LABEL_111;
      }
    }
  }
LABEL_154:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_iCxz8Qnks>::GetImpl'::`2'::impl) )
  {
    std::set<std::wstring>::__autoclassinit2(v232);
    std::set<std::wstring>::set<std::wstring>(v232);
    winrt::param::hstring::hstring((winrt::param::hstring *)&v203, L"ApiInfos");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
      &v235,
      &v228,
      &v203);
    v72 = 0;
    winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
      &v228,
      (__int64)v200);
    v73 = DWORD2(v200[0]);
    if ( DWORD2(v200[0]) )
    {
      do
      {
        winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
          &v228,
          &v220,
          v72);
        v210 = 0;
        v74 = (*(__int64 (__fastcall **)(wchar_t *, winrt::impl **))(*(_QWORD *)v220 + 96LL))(v220, &v210);
        if ( v74 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v74);
        }
        v75 = v210;
        v189 = v210;
        *((_QWORD *)&v191 + 1) = 0xC00000001LL;
        v193 = L"ApiClassName";
        *(_QWORD *)&v191 = (char *)&v191 + 8;
        v210 = 0;
        v76 = (*(__int64 (__fastcall **)(winrt::impl *, char *, winrt::impl **))(*(_QWORD *)v189 + 80LL))(
                v189,
                (char *)&v191 + 8,
                &v210);
        if ( v76 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v76);
        }
        v226 = v210;
        S2[1] = (wchar_t *)0x1000000001LL;
        v219 = L"RequiredSessions";
        S2[0] = (wchar_t *)&S2[1];
        v214[0] = 0;
        v210 = 0;
        (**(void (__fastcall ***)(winrt::impl *, __int64 *, winrt::impl **))v75)(
          v75,
          winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,
          &v210);
        v227 = v210;
        v77 = (*(__int64 (__fastcall **)(winrt::impl *, wchar_t *, char *))(*(_QWORD *)v210 + 64LL))(v210, S2[0], v214);
        if ( v77 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v77);
        }
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v227);
        if ( v214[0] )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v222, L"RequiredSessions");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
            (__int64 *)&v189,
            &v212,
            v222);
          std::vector<winrt::hstring>::__autoclassinit2(S2);
          *(_OWORD *)S2 = 0;
          N = 0;
          v78 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v212);
          std::vector<winrt::hstring>::reserve(S2, v78);
          v79 = 0;
          winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
            (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v212,
            (__int64)v200);
          v80 = DWORD2(v200[0]);
          if ( DWORD2(v200[0]) )
          {
            do
            {
              winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
                (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v212,
                &v221,
                v79);
              v210 = 0;
              v81 = (*((__int64 (__fastcall **)(volatile signed __int32 **, winrt::impl **))*v221 + 8))(v221, &v210);
              if ( v81 < 0 )
              {
                _mm_lfence();
                winrt::throw_hresult((unsigned int)v81);
              }
              v83 = (volatile signed __int32 *)v210;
              v84 = S2[1];
              if ( S2[1] == (wchar_t *)N )
              {
                std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(S2, S2[1], &v210);
                v83 = (volatile signed __int32 *)v210;
              }
              else
              {
                *(_QWORD *)v84 = winrt::impl::duplicate_hstring(v210, v82);
                S2[1] += 4;
              }
              if ( v83 )
              {
                v85 = _InterlockedDecrement(v83 + 6);
                if ( v85 )
                {
                  if ( v85 < 0 )
                    abort();
                }
                else
                {
                  v86 = WINRT_IMPL_GetProcessHeap();
                  WINRT_IMPL_HeapFree(v86, 0, (LPVOID)v83);
                }
              }
              if ( v221 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v221);
              ++v79;
            }
            while ( v79 != v80 );
          }
          std::_Tree<std::_Tmap_traits<winrt::hstring,std::vector<winrt::hstring>,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,std::vector<winrt::hstring>>>,0>>::_Emplace<winrt::hstring &,std::vector<winrt::hstring> &>(
            v232,
            v240,
            &v226,
            S2);
          std::vector<winrt::hstring>::_Tidy(S2);
          if ( v212 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v212);
        }
        else
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"SessionClassName");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
            (__int64 *)&v189,
            &v211,
            S2);
          winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"Workload");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
            (__int64 *)&v189,
            &v190,
            &v191);
          v209 = 0;
          winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"SessionPackages");
          if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                  (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v189,
                                  S2) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"SessionPackages");
            NamedArray = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                           (__int64 *)&v189,
                           &v188,
                           &v191);
            v91 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
                    (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))NamedArray,
                    &v215,
                    0);
            winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
              v91,
              &v225);
            if ( v215 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v215);
            if ( v188 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v188);
            winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"PackageFamilyName");
            v92 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                    (__int64 *)&v225,
                    &v197,
                    S2);
            winrt::hstring::operator=(&v209, v92);
            std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(&v197);
            if ( v225 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v225);
          }
          else
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"SessionPackage");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v189,
                                     S2) )
            {
              v177 = wil::verify_hresult<long>(2147549183LL);
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x239,
                (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Workloads\\WorkloadManager.cpp",
                (const char *)v177,
                (int)"ApiInfo object must contain either a SessionPackages array or a SessionPackage string.",
                v186);
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"SessionPackage");
            v93 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                    (__int64 *)&v189,
                    &v194,
                    &v191);
            winrt::hstring::operator=(&v209, v93);
            std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v194);
          }
          v94 = winrt::hstring::c_str((winrt::hstring *)&v190);
          std::wstring::wstring(S2, v94);
          v95 = (const struct IUnknown **)std::_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Workloads::Workload,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::Workload>>,0>>::find(
                                            (char *)v1 + 112,
                                            &v198,
                                            S2);
          winrt::Windows::Foundation::IUnknown::IUnknown((winrt::Windows::Foundation::IUnknown *)&v216, *v95 + 8);
          std::wstring::_Tidy_deallocate((__int64)S2);
          v96 = winrt::hstring::c_str((winrt::hstring *)&v209);
          std::wstring::wstring(S2, v96);
          v97 = (const struct IUnknown **)std::_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem>>,0>>::find(
                                            v236,
                                            v199,
                                            S2);
          winrt::Windows::Foundation::IUnknown::IUnknown((winrt::Windows::Foundation::IUnknown *)&lpMem, *v97 + 8);
          std::wstring::_Tidy_deallocate((__int64)S2);
          *(_OWORD *)v222 = 0;
          std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::guid>>>>::__autoclassinit2(&v231);
          std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::find(
            &v244,
            &v231,
            (__int64 *)&v209);
          if ( v231 == v245 )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)S2, L"VectorSpaceId");
            if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                    (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v189,
                                    S2) )
            {
              winrt::param::hstring::hstring((winrt::param::hstring *)&v191, L"VectorSpaceId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                (__int64 *)&v189,
                &v230,
                &v191);
              *(_OWORD *)v222 = *(_OWORD *)winrt::hstring::operator std::wstring_view(&v230, &v201);
              *(_OWORD *)v222 = *(_OWORD *)winrt::guid::guid(v206, v222);
              std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(&v230);
            }
          }
          else
          {
            *(_OWORD *)v222 = *(_OWORD *)(v231 + 6);
          }
          winrt::make<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::hstring &,winrt::hstring &,winrt::Microsoft::Windows::Workloads::Workload &,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem &,winrt::guid &,std::nullptr_t>(
            (unsigned int)&v229,
            (unsigned int)&v226,
            (unsigned int)&v211,
            (unsigned int)&v216,
            (__int64)&lpMem,
            (__int64)v222,
            v187);
          v98 = std::make_pair<winrt::hstring &,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem &>(
                  &p_lpMem,
                  &v226,
                  &v229);
          std::map<std::wstring,winrt::Microsoft::Windows::Workloads::ApiInfo>::insert<std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,0>(
            (char *)v1 + 128,
            v207,
            v98);
          std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload>::~pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload>(&p_lpMem);
          if ( v229 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v229);
          if ( lpMem )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
          if ( v216 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v216);
          std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v209);
          std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(&v190);
          std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>((volatile signed __int32 **)&v211);
        }
        v87 = v226;
        if ( v226 )
        {
          v88 = _InterlockedDecrement((volatile signed __int32 *)v226 + 6);
          if ( v88 )
          {
            if ( v88 < 0 )
              abort();
          }
          else
          {
            v89 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v89, 0, v87);
          }
        }
        if ( v189 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v189);
        if ( v220 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v220);
        ++v72;
      }
      while ( v72 != v73 );
    }
    v99 = *(__int64 **)v232[0];
    if ( !*(_BYTE *)(*(_QWORD *)v232[0] + 25LL) )
    {
      v100 = (struct IUnknownVtbl **)((char *)v1 + 128);
      do
      {
        v222[0] = 0;
        v222[1] = 0;
        v101 = operator new(0x30u);
        *v101 = v101;
        v101[1] = v101;
        v101[2] = v101;
        *((_WORD *)v101 + 12) = 257;
        v222[0] = (wchar_t *)v101;
        v103 = (winrt::impl **)v99[5];
        for ( i = (winrt::impl **)v99[6]; v103 != i; ++v103 )
        {
          v211.lpVtbl = 0;
          std::find_if_std::_Tree_iterator_std::_Tree_val_std::_Tree_simple_types_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const__winrt::Microsoft::Windows::Workloads::ApiInfo_________lambda_36f1798e29a85619ddf8af9287a6a690___(
            &v211,
            (*v100)->QueryInterface,
            *v100,
            v103);
          lpVtbl = v211.lpVtbl;
          if ( v211.lpVtbl == *v100 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x264,
              (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Workloads\\WorkloadManager.cpp",
              (const char *)0x8000FFFFLL,
              (int)v185);
          v106 = std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(
                   v222,
                   &v191,
                   v103);
          v108 = *(_OWORD *)v106;
          N = *(_QWORD *)(v106 + 16);
          if ( *(_BYTE *)(N + 25)
            || (unsigned __int8)std::less<winrt::hstring>::operator()(v107, (__int64 *)v103, (__int64 *)(N + 32)) )
          {
            if ( v222[1] == (wchar_t *)0x555555555555555LL )
              std::_Throw_tree_length_error();
            v109 = v222[0];
            p_lpMem = v222;
            v196 = 0;
            v110 = (wchar_t **)operator new(0x30u);
            v196 = v110;
            v110[4] = (wchar_t *)winrt::impl::duplicate_hstring(*v103, v111);
            Release = lpVtbl[2].Release;
            v110[5] = (wchar_t *)Release;
            if ( Release )
              (*(void (__fastcall **)(ULONG (__stdcall *)(IUnknown *)))(*(_QWORD *)Release + 8LL))(Release);
            *v110 = v109;
            v110[1] = v109;
            v110[2] = v109;
            *((_WORD *)v110 + 12) = 0;
            v196 = 0;
            v200[0] = v108;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(
              v222,
              (__int64)v200,
              (__int64)v110);
          }
        }
        v113 = (struct IUnknownVtbl *)winrt::impl::duplicate_hstring((winrt::impl *)v99[4], v102);
        v211.lpVtbl = v113;
        v114 = (char *)operator new(0x40u);
        v198 = (volatile signed __int32 *)v114;
        v115 = (volatile signed __int32 *)(v114 + 16);
        *((_QWORD *)v114 + 2) = &winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable';
        *((_QWORD *)v114 + 3) = &winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable';
        *((_QWORD *)v114 + 4) = &winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        *((_QWORD *)v114 + 1) = 1;
        *((_DWORD *)v114 + 10) = 0;
        *(_QWORD *)v114 = &winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>::`vftable';
        *((_QWORD *)v114 + 6) = 0;
        *((_QWORD *)v114 + 7) = 0;
        v116 = operator new(0x30u);
        *v116 = v116;
        v116[1] = v116;
        v116[2] = v116;
        *((_WORD *)v116 + 12) = 257;
        *((_QWORD *)v114 + 6) = v116;
        *((wchar_t **)v114 + 6) = v222[0];
        v222[0] = (wchar_t *)v116;
        v117 = (wchar_t *)*((_QWORD *)v114 + 7);
        *((wchar_t **)v114 + 7) = v222[1];
        v222[1] = v117;
        *(_QWORD *)v114 = &winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>::`vftable';
        v194 = (struct IUnknownVtbl *)(v114 + 16);
        v118 = (volatile signed __int32 *)operator new(0x90u);
        v199[0] = v118;
        v227 = &v190;
        v190 = v115;
        if ( v115 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v115 + 8LL))(v115);
        v197 = (volatile signed __int32 *)&v230;
        v230 = 0;
        v221 = &v231;
        v231 = 0;
        v226 = &v210;
        v201 = &Src;
        v202 = 0;
        winrt::hstring::hstring(&v210, (__int64)&v201);
        v225 = winrt::impl::duplicate_hstring((winrt::impl *)v113, v119);
        v200[0] = 0;
        v120 = winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo>::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo>(
                 (_DWORD)v118,
                 (unsigned int)&v225,
                 (unsigned int)&v210,
                 (unsigned int)&v231,
                 (__int64)&v230,
                 (__int64)v200,
                 (__int64)&v190);
        v121 = (volatile signed __int32 *)(v120 + 16);
        if ( !v120 )
          v121 = 0;
        v221 = (volatile signed __int32 **)v121;
        std::_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Emplace<winrt::hstring &,winrt::Microsoft::Windows::Workloads::ApiInfo &>(
          v100,
          v240,
          &v211,
          &v221);
        if ( v221 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v221);
        if ( v115 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v194);
        v122 = v211.lpVtbl;
        if ( v211.lpVtbl )
        {
          v123 = _InterlockedDecrement((volatile signed __int32 *)&v211.lpVtbl[1]);
          if ( v123 )
          {
            if ( v123 < 0 )
              abort();
          }
          else
          {
            v124 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v124, 0, v122);
          }
        }
        std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::~_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>(v222);
        v125 = (__int64 **)v99[2];
        if ( *((_BYTE *)v125 + 25) )
        {
          for ( j = (__int64 *)v99[1]; !*((_BYTE *)j + 25); j = (__int64 *)j[1] )
          {
            if ( v99 != (__int64 *)j[2] )
              break;
            v99 = j;
          }
          v99 = j;
        }
        else
        {
          v99 = (__int64 *)v99[2];
          for ( k = *v125; !*((_BYTE *)k + 25); k = (__int64 *)*k )
            v99 = k;
        }
      }
      while ( !*((_BYTE *)v99 + 25) );
    }
    if ( v228 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v228);
    std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,std::vector<winrt::hstring>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<winrt::hstring const,std::vector<winrt::hstring>>,void *>>>(
      v232,
      v232,
      *((_QWORD *)v232[0] + 1));
    operator delete(v232[0]);
    goto LABEL_328;
  }
  winrt::param::hstring::hstring((winrt::param::hstring *)v208, L"ApiInfos");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
    &v235,
    &v228,
    v208);
  v128 = 0;
  LODWORD(v188) = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
    &v228,
    (__int64)v200);
  if ( DWORD2(v200[0]) )
  {
    v129 = v240[0];
    while ( 1 )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
        &v228,
        &v229,
        v128);
      v211.lpVtbl = 0;
      v130 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v229 + 96LL))(v229, &v211);
      if ( v130 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v130);
      }
      v131 = v211.lpVtbl;
      v215 = v211.lpVtbl;
      v222[1] = (wchar_t *)0xC00000001LL;
      v224 = L"ApiClassName";
      v222[0] = (wchar_t *)&v222[1];
      v225 = 0;
      v132 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, wchar_t **, winrt::impl **))v211.lpVtbl->QueryInterface
              + 10))(
               v211.lpVtbl,
               &v222[1],
               &v225);
      if ( v132 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v132);
      }
      v227 = v225;
      v232[1] = (void *)0x1000000001LL;
      v234 = L"SessionClassName";
      v232[0] = &v232[1];
      v209 = 0;
      v133 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, void **, winrt::impl **))v131->QueryInterface + 10))(
               v131,
               &v232[1],
               &v209);
      if ( v133 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v133);
      }
      v207[0] = v209;
      v222[1] = (wchar_t *)0x800000001LL;
      v224 = L"Workload";
      v222[0] = (wchar_t *)&v222[1];
      v212 = 0;
      v134 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, wchar_t **, winrt::impl **))v131->QueryInterface + 10))(
               v131,
               &v222[1],
               &v212);
      if ( v134 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v134);
      }
      v135 = v212;
      v206[0] = v212;
      v216 = 0;
      v222[1] = (wchar_t *)0xF00000001LL;
      v224 = L"SessionPackages";
      v222[0] = (wchar_t *)&v222[1];
      v214[0] = 0;
      v211.lpVtbl = 0;
      (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, struct IUnknown *))v131->QueryInterface)(
        v131,
        winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,
        &v211);
      v194 = v211.lpVtbl;
      v136 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, wchar_t *, char *))v211.lpVtbl->QueryInterface + 8))(
               v211.lpVtbl,
               v222[0],
               v214);
      if ( v136 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v136);
      }
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v194);
      if ( v214[0] )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v222, L"SessionPackages");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          (__int64 *)&v215,
          &v226,
          v222);
        v137 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
                 (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v226,
                 &v190,
                 0);
        winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
          v137,
          &v221);
        if ( v190 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v190);
        winrt::param::hstring::hstring((winrt::param::hstring *)v222, L"PackageFamilyName");
        v138 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                 (__int64 *)&v221,
                 v199,
                 v222);
        winrt::hstring::operator=(&v216, v138);
        std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(v199);
        std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::guid>>>>::__autoclassinit2(&v230);
        std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::find(
          &v244,
          &v230,
          (__int64 *)&v216);
        if ( v230 == v245 )
        {
          if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v226) > 1 )
          {
            v178 = std::wstring::wstring(&v203, &v216);
            v180 = std::operator+<wchar_t>(&v191, v179, v178);
            v181 = std::operator+<wchar_t>(
                     v208,
                     v180,
                     L"' not found in workloads16SchemaCompat_packageFamilyNameToVectorSpaceMap.");
            std::operator+<wchar_t>(
              v240,
              v181,
              L" This indicates that this package is not the package with the preferred vector space");
            std::filesystem::path::~path((std::filesystem::path *)v208);
            std::filesystem::path::~path((std::filesystem::path *)&v191);
            std::filesystem::path::~path((std::filesystem::path *)&v203);
            v182 = (const wchar_t *)std::wstring::c_str(v240);
            winrt::param::hstring::hstring((winrt::param::hstring *)v200, v182);
            v183 = winrt::hresult::hresult((winrt::hresult *)&v189, -2147418113);
            winrt::hresult_error::hresult_error(S2, *(unsigned int *)v183, v200);
            throw (winrt::hresult_error *)S2;
          }
        }
        else
        {
          v129 = *(_OWORD *)(v230 + 6);
        }
        if ( v221 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v221);
        if ( v226 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v226);
      }
      else
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v222, L"SessionPackage");
        if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                 (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v215,
                                 v222) )
        {
          v184 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x2A7,
            (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Workloads\\WorkloadManager.cpp",
            (const char *)v184,
            (int)"ApiInfo object must contain either a SessionPackages array or a SessionPackage string.",
            v186);
        }
        winrt::param::hstring::hstring((winrt::param::hstring *)v232, L"SessionPackage");
        v139 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                 (__int64 *)&v215,
                 &v198,
                 v232);
        winrt::hstring::operator=(&v216, v139);
        std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(&v198);
        winrt::param::hstring::hstring((winrt::param::hstring *)v222, L"VectorSpaceId");
        if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v215,
                                v222) )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v232, L"VectorSpaceId");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
            (__int64 *)&v215,
            &v231,
            v232);
          *(_OWORD *)v222 = *(_OWORD *)winrt::hstring::operator std::wstring_view(&v231, &v203);
          v129 = *(_OWORD *)winrt::guid::guid(&v191, v222);
          std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(&v231);
        }
      }
      v140 = (size_t *)((char *)v1 + 112);
      if ( v135 )
        v141 = (const wchar_t *)*((_QWORD *)v135 + 2);
      else
        v141 = &Src;
      *(_OWORD *)v232 = 0;
      v233 = 0;
      v234 = 0;
      v142 = -1;
      do
        ++v142;
      while ( v141[v142] );
      std::wstring::_Construct<1,wchar_t const *>(v232, v141, v142);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
        v140,
        v222,
        v232);
      v143 = v223;
      if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Workloads::Workload,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::Workload>>,0>>::_Lower_bound_duplicate<std::wstring>(
                               v144,
                               v223,
                               v232) )
        v143 = *v140;
      v145 = *(struct IUnknownVtbl **)(v143 + 64);
      v211.lpVtbl = v145;
      if ( v145 )
        (*((void (__fastcall **)(struct IUnknownVtbl *))v145->QueryInterface + 1))(v145);
      std::wstring::_Tidy_deallocate((__int64)v232);
      v146 = (volatile signed __int32 *)v216;
      if ( v216 )
        v147 = (const wchar_t *)*((_QWORD *)v216 + 2);
      else
        v147 = &Src;
      *(_OWORD *)v222 = 0;
      v223 = 0;
      v224 = 0;
      v148 = -1;
      do
        ++v148;
      while ( v147[v148] );
      std::wstring::_Construct<1,wchar_t const *>(v222, v147, v148);
      v150 = (__int64 *)v236[0];
      v151 = *(__int64 **)(v236[0] + 8LL);
      v152 = (__int64 *)v236[0];
      if ( !*((_BYTE *)v151 + 25) )
      {
        while ( 1 )
        {
          v153 = (const wchar_t *)(v151 + 4);
          v154 = (const wchar_t *)v222;
          if ( (unsigned __int64)v224 > 7 )
            v154 = v222[0];
          v155 = v151[6];
          if ( (unsigned __int64)v151[7] > 7 )
            v153 = *(const wchar_t **)v153;
          v156 = v223;
          v157 = v151[6];
          if ( v223 < v155 )
            v157 = v223;
          v158 = wmemcmp(v153, v154, v157);
          if ( v158 )
          {
            if ( v158 < 0 )
              goto LABEL_306;
          }
          else if ( v155 < v156 )
          {
LABEL_306:
            v151 = (__int64 *)v151[2];
            goto LABEL_284;
          }
          v152 = v151;
          v151 = (__int64 *)*v151;
LABEL_284:
          if ( *((_BYTE *)v151 + 25) )
          {
            v150 = (__int64 *)v236[0];
            v128 = (unsigned int)v188;
            break;
          }
        }
      }
      if ( *((_BYTE *)v152 + 25) )
        goto LABEL_289;
      if ( (unsigned __int8)std::less<std::wstring>::operator()(v149, v222, v152 + 4) )
        break;
LABEL_290:
      v159 = (volatile signed __int32 *)v152[8];
      v194 = (struct IUnknownVtbl *)v159;
      if ( v159 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v159 + 8LL))(v159);
      std::wstring::_Tidy_deallocate((__int64)v222);
      v160 = (const wchar_t *)operator new(0x90u);
      v201 = v160;
      v188 = &v210;
      v210 = (winrt::impl *)v159;
      if ( v159 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v159 + 8LL))(v159);
      p_lpMem = &lpMem;
      winrt::Windows::Foundation::IUnknown::IUnknown((winrt::Windows::Foundation::IUnknown *)&lpMem, &v211);
      v232[0] = &v220;
      v220 = (wchar_t *)winrt::impl::duplicate_hstring(v209, v161);
      v189 = winrt::impl::duplicate_hstring(v225, v162);
      *(_OWORD *)v222 = v129;
      v163 = winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo>::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo>(
               (_DWORD)v160,
               (unsigned int)&v189,
               (unsigned int)&v220,
               (unsigned int)&lpMem,
               (__int64)&v210,
               (__int64)v222);
      v164 = (winrt::impl *)(v163 + 16);
      if ( !v163 )
        v164 = 0;
      v225 = v164;
      v1 = (winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *)v197;
      v165 = std::make_pair<winrt::hstring &,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem &>(
               v240,
               &v227,
               &v225);
      std::map<std::wstring,winrt::Microsoft::Windows::Workloads::ApiInfo>::insert<std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,0>(
        (char *)v1 + 128,
        S2,
        v165);
      std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload>::~pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload>(v240);
      if ( v225 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v225);
      if ( v159 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v194);
      if ( v145 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v211);
      if ( v146 )
      {
        v166 = _InterlockedDecrement(v146 + 6);
        if ( v166 )
        {
          if ( v166 < 0 )
            abort();
        }
        else
        {
          v167 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v167, 0, (LPVOID)v146);
        }
        v135 = v212;
      }
      if ( v135 )
      {
        v168 = _InterlockedDecrement((volatile signed __int32 *)v135 + 6);
        if ( v168 )
        {
          if ( v168 < 0 )
            abort();
        }
        else
        {
          v169 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v169, 0, v212);
        }
      }
      if ( v209 )
      {
        v170 = _InterlockedDecrement((volatile signed __int32 *)v209 + 6);
        if ( v170 )
        {
          if ( v170 < 0 )
            abort();
        }
        else
        {
          v171 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v171, 0, v209);
        }
      }
      v172 = v227;
      if ( v227 )
      {
        v173 = _InterlockedDecrement((volatile signed __int32 *)v227 + 6);
        if ( v173 )
        {
          if ( v173 < 0 )
            abort();
        }
        else
        {
          v174 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v174, 0, v172);
        }
      }
      if ( v215 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v215);
      if ( v229 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v229);
      LODWORD(v188) = ++v128;
      if ( v128 == DWORD2(v200[0]) )
        goto LABEL_326;
    }
    v150 = (__int64 *)v236[0];
LABEL_289:
    v152 = v150;
    goto LABEL_290;
  }
LABEL_326:
  if ( v228 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v228);
LABEL_328:
  if ( v238 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v238);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v239);
  if ( v237 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v237);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::guid>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::guid>>>>>>(v246);
  std::_List_node<std::pair<winrt::hstring const,winrt::guid>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<winrt::hstring const,winrt::guid>,void *>>>(
    v175,
    v245);
  operator delete(v245);
  if ( v235 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v235);
  std::string::_Tidy_deallocate((__int64)v241);
  std::_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>(v236);
  std::string::_Tidy_deallocate((__int64)v242);
}

```

## disassembly

```asm
0x18001eb00  mov     rax, rsp
0x18001eb03  mov     [rax+10h], rbx
0x18001eb07  mov     [rax+18h], rsi
0x18001eb0b  mov     [rax+20h], rdi
0x18001eb0f  push    rbp
0x18001eb10  push    r12
0x18001eb12  push    r13
0x18001eb14  push    r14
0x18001eb16  push    r15
0x18001eb18  lea     rbp, [rax-258h]
0x18001eb1f  sub     rsp, 330h
0x18001eb26  movaps  xmmword ptr [rax-38h], xmm6
0x18001eb2a  mov     rax, cs:__security_cookie
0x18001eb31  xor     rax, rsp
0x18001eb34  mov     [rbp+250h+var_40], rax
0x18001eb3b  mov     r13, rcx
0x18001eb3e  mov     [rbp+250h+var_2C0], rcx
0x18001eb42  xor     ebx, ebx
0x18001eb44  mov     r12d, ebx
0x18001eb47  mov     dword ptr [rsp+350h+var_308], ebx
0x18001eb4b  mov     [rbp+250h+var_160], rbx
0x18001eb52  lea     rcx, [rbp+250h+var_A0]
0x18001eb59  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18001eb5e  nop
0x18001eb5f  mov     dword ptr [rsp+350h+var_310], ebx
0x18001eb63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60663426@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60663426@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426> `wil::Feature<__WilFeatureTraits_Feature_60663426>::GetImpl(void)'::`2'::impl
0x18001eb6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60663426@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426>::__private_IsEnabled(void)
0x18001eb6f  lea     rbx, [r13+0B8h]
0x18001eb76  test    al, al
0x18001eb78  jz      short loc_18001EBC4
0x18001eb7a  lea     rax, [rsp+350h+var_310]
0x18001eb7f  mov     qword ptr [rsp+350h+var_330], rax
0x18001eb84  lea     r9, [rbp+250h+var_A0]
0x18001eb8b  lea     r8, [rbp+250h+var_160]
0x18001eb92  mov     rdx, rbx
0x18001eb95  mov     rcx, r13
0x18001eb98  call    ?TryGetHardwareInfoFromBroker@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAA_NPEAW4NpuType@3456@PEA_KPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAI@Z; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::TryGetHardwareInfoFromBroker(winrt::Microsoft::Windows::Workloads::NpuType *,unsigned __int64 *,std::string *,uint *)
0x18001eb9d  test    al, al
0x18001eb9f  jz      short loc_18001EBC4
0x18001eba1  mov     sil, 1
0x18001eba4  cmp     [rbp+250h+var_90], 0
0x18001ebac  jz      short loc_18001EBC7
0x18001ebae  movzx   edi, sil
0x18001ebb2  mov     eax, [rbx]
0x18001ebb4  mov     dword ptr [rsp+350h+var_308], eax
0x18001ebb8  lea     rcx, [rsp+350h+var_308]
0x18001ebbd  call    ??$WorkloadManagerLoadWorkloadsUsingBrokerNpuType@I@TraceLogger@@SAX$$QEAI@Z; TraceLogger::WorkloadManagerLoadWorkloadsUsingBrokerNpuType<uint>(uint &&)
0x18001ebc2  jmp     short loc_18001EBD2
0x18001ebc4  xor     sil, sil
0x18001ebc7  xor     dil, dil
0x18001ebca  mov     rcx, r13; this
0x18001ebcd  call    ?DetectNpu@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXXZ; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DetectNpu(void)
0x18001ebd2  call    ?IsRunningOnArm64@@YA_NXZ; IsRunningOnArm64(void)
0x18001ebd7  mov     ecx, 4
0x18001ebdc  mov     edx, 10h
0x18001ebe1  test    al, al
0x18001ebe3  cmovnz  ecx, edx
0x18001ebe6  mov     dword ptr [rsp+350h+var_308], ecx
0x18001ebea  lea     rcx, [rbp+250h+var_110]
0x18001ebf1  call    ?__autoclassinit2@?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX_K@Z; std::set<std::wstring>::__autoclassinit2(unsigned __int64)
0x18001ebf6  lea     rcx, [rbp+250h+var_110]
0x18001ebfd  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem>::map<std::wstring,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem>(void)
0x18001ec02  nop
0x18001ec03  mov     ecx, [rbx]
0x18001ec05  test    ecx, ecx
0x18001ec07  jz      short loc_18001EC56
0x18001ec09  sub     ecx, 1
0x18001ec0c  jz      short loc_18001EC3E
0x18001ec0e  sub     ecx, 1
0x18001ec11  jz      short loc_18001EC37
0x18001ec13  sub     ecx, 1
0x18001ec16  jz      short loc_18001EC30
0x18001ec18  cmp     ecx, 1
0x18001ec1b  jnz     short loc_18001EC56
0x18001ec1d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57003568@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57003568@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568> `wil::Feature<__WilFeatureTraits_Feature_57003568>::GetImpl(void)'::`2'::impl
0x18001ec24  call    ?AssertEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57003568@@@details@wil@@QEAAXXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::AssertEnabled(void)
0x18001ec29  mov     ebx, 3ECh
0x18001ec2e  jmp     short loc_18001EC5B
0x18001ec30  mov     ebx, 3EAh
0x18001ec35  jmp     short loc_18001EC5B
0x18001ec37  mov     ebx, 3E9h
0x18001ec3c  jmp     short loc_18001EC5B
0x18001ec3e  lea     rcx, [r13+0C0h]
0x18001ec45  call    ??$?8DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD@Z; std::operator==<char>(std::string const &,char const * const)
0x18001ec4a  movzx   eax, al
0x18001ec4d  lea     ebx, ds:3EBh[rax*2]
0x18001ec54  jmp     short loc_18001EC5B
0x18001ec56  mov     ebx, 3E8h
0x18001ec5b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60663426@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60663426@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426> `wil::Feature<__WilFeatureTraits_Feature_60663426>::GetImpl(void)'::`2'::impl
0x18001ec62  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60663426@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426>::__private_IsEnabled(void)
0x18001ec67  test    al, al
0x18001ec69  jz      short loc_18001ECA9
0x18001ec6b  test    sil, sil
0x18001ec6e  jz      short loc_18001ECA9
0x18001ec70  cmp     dword ptr [rsp+350h+var_310], 0
0x18001ec75  jz      short loc_18001ECA9
0x18001ec77  cmp     qword ptr [r13+58h], 0
0x18001ec7c  jz      short loc_18001ECA9
0x18001ec7e  lea     rcx, [rbp+250h+S2]
0x18001ec85  call    ?GetDefaultResourceDllPath@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetDefaultResourceDllPath(void)
0x18001ec8a  mov     r12d, 1
0x18001ec90  lea     rsi, [r13+48h]
0x18001ec94  mov     rdx, rax
0x18001ec97  mov     rcx, rsi
0x18001ec9a  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator!=<wchar_t>(std::wstring const &,std::wstring const &)
0x18001ec9f  test    al, al
0x18001eca1  jz      short loc_18001ECA9
0x18001eca3  movzx   r14d, r12b
0x18001eca7  jmp     short loc_18001ECB0
0x18001eca9  xor     r14b, r14b
0x18001ecac  lea     rsi, [r13+48h]
0x18001ecb0  test    r12b, 1
0x18001ecb4  jz      short loc_18001ECC6
0x18001ecb6  and     r12d, 0FFFFFFFEh
0x18001ecba  lea     rcx, [rbp+250h+S2]
0x18001ecc1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ecc6  test    r14b, r14b
0x18001ecc9  jz      short loc_18001ECD2
0x18001eccb  xor     dil, dil
0x18001ecce  mov     ebx, dword ptr [rsp+350h+var_310]
0x18001ecd2  lea     rcx, [rbp+250h+var_C0]
0x18001ecd9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18001ecde  nop
0x18001ecdf  test    dil, dil
0x18001ece2  jz      short loc_18001ECFC
0x18001ece4  lea     rdx, [rbp+250h+var_A0]
0x18001eceb  lea     rcx, [rbp+250h+var_C0]
0x18001ecf2  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18001ecf7  jmp     loc_18001EDA3
0x18001ecfc  lea     rcx, [rbp+250h+S2]
0x18001ed03  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18001ed08  nop
0x18001ed09  mov     rcx, rsi
0x18001ed0c  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18001ed11  mov     rcx, rax; lpLibFileName
0x18001ed14  xor     r8d, r8d; dwFlags
0x18001ed17  xor     edx, edx; hFile
0x18001ed19  call    cs:__imp_LoadLibraryExW
0x18001ed1f  mov     [rbp+250h+var_160], rax
0x18001ed26  mov     rcx, [rbp+258h]; this
0x18001ed2d  test    rax, rax
0x18001ed30  jz      loc_180020FA8
0x18001ed36  mov     r8d, ebx
0x18001ed39  mov     rdx, rax
0x18001ed3c  lea     rcx, [rsp+350h+var_300+8]
0x18001ed41  call    winrt__Microsoft__Windows__Workloads__implementation__readResourceContent
0x18001ed46  mov     rdx, rax
0x18001ed49  lea     rcx, [rbp+250h+S2]
0x18001ed50  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001ed55  lea     rcx, [rsp+350h+var_300+8]
0x18001ed5a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001ed5f  lea     rdx, [rbp+250h+S2]
0x18001ed66  lea     rcx, [rsp+350h+var_300+8]
0x18001ed6b  call    winrt__Microsoft__Windows__Workloads__implementation__removeBOMAndConvert
0x18001ed70  mov     rdx, rax
0x18001ed73  lea     rcx, [rbp+250h+var_C0]
0x18001ed7a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001ed7f  lea     rcx, [rsp+350h+var_300+8]
0x18001ed84  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001ed89  nop
0x18001ed8a  lea     rcx, [rbp+250h+var_160]
0x18001ed91  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(void)
0x18001ed96  nop
0x18001ed97  lea     rcx, [rbp+250h+S2]
0x18001ed9e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001eda3  lea     rcx, [rbp+250h+var_118]; this
0x18001edaa  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18001edaf  nop
0x18001edb0  lea     rdx, [rbp+250h+var_C0]
0x18001edb7  lea     rcx, [rbp+250h+var_160]
0x18001edbe  call    ??$to_hstring@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@winrt@@YA?AUhstring@0@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; winrt::to_hstring<std::string,0>(std::string const &)
0x18001edc3  nop
0x18001edc4  mov     rax, [rax]
0x18001edc7  mov     [rbp+250h+S2], rax
0x18001edce  lea     rdx, [rbp+250h+var_118]; struct winrt::Windows::Data::Json::JsonObject *
0x18001edd5  lea     rcx, [rbp+250h+S2]; struct winrt::param::hstring *
0x18001eddc  call    ?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z; winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)
0x18001ede1  movzx   ebx, al
0x18001ede4  lea     rcx, [rbp+250h+var_160]
0x18001edeb  call    ??1?$pair@Uhstring@winrt@@UPackageVersion@ApplicationModel@Windows@2@@std@@QEAA@XZ; std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(void)
0x18001edf0  test    bl, bl
0x18001edf2  jz      loc_180020FB3
0x18001edf8  lea     rcx, [rbp+250h+var_80]
0x18001edff  call    ?__autoclassinit2@?$unordered_map@Uhstring@winrt@@Uguid@2@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@5@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@@std@@QEAAX_K@Z; std::unordered_map<winrt::hstring,winrt::guid>::__autoclassinit2(unsigned __int64)
0x18001ee04  lea     rcx, [rbp+250h+var_80]
0x18001ee0b  call    ??0?$unordered_map@Uhstring@winrt@@Uguid@2@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@5@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@@std@@QEAA@XZ; std::unordered_map<winrt::hstring,winrt::guid>::unordered_map<winrt::hstring,winrt::guid>(void)
0x18001ee10  nop
0x18001ee11  lea     rdx, aPackages; "Packages"
0x18001ee18  lea     rcx, [rbp+250h+S2]; this
0x18001ee1f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001ee24  lea     r8, [rbp+250h+S2]
0x18001ee2b  lea     rdx, [rbp+250h+var_100]
0x18001ee32  lea     rcx, [rbp+250h+var_118]
0x18001ee39  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x18001ee3e  nop
0x18001ee3f  lea     rcx, [rbp+250h+var_F0]
0x18001ee46  call    ?__autoclassinit2@?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX_K@Z; std::set<std::wstring>::__autoclassinit2(unsigned __int64)
0x18001ee4b  lea     rcx, [rbp+250h+var_F0]
0x18001ee52  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18001ee57  nop
0x18001ee58  lea     rax, [rbp+250h+var_100]
0x18001ee5f  mov     [rbp+250h+var_190], rax
0x18001ee66  xor     esi, esi
0x18001ee68  mov     dword ptr [rbp+250h+var_190+8], esi
0x18001ee6e  lea     rdx, [rbp+250h+var_2A0]
0x18001ee72  lea     rcx, [rbp+250h+var_100]
0x18001ee79  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(void)
0x18001ee7e  lea     r14, aFamilyname_0; "FamilyName"
0x18001ee85  mov     ebx, dword ptr [rbp+250h+var_2A0+8]
0x18001ee88  test    ebx, ebx
0x18001ee8a  jz      loc_18001F171
0x18001ee90  lea     rdx, [rbp+250h+var_200]
0x18001ee94  lea     rcx, [rbp+250h+var_190]
0x18001ee9b  call    ??D?$fast_iterator@UJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA?AUIJsonValue@Json@Data@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(void)
0x18001eea0  nop
0x18001eea1  lea     rdx, [rsp+350h+var_310]
0x18001eea6  lea     rcx, [rbp+250h+var_200]
0x18001eeaa  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x18001eeaf  nop
0x18001eeb0  mov     rdx, r14; wchar_t *
0x18001eeb3  lea     rcx, [rsp+350h+var_300+8]; this
0x18001eeb8  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001eebd  lea     r8, [rsp+350h+var_300+8]
0x18001eec2  lea     rdx, [rbp+250h+var_1A0]
0x18001eec9  lea     rcx, [rsp+350h+var_310]
0x18001eece  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x18001eed3  nop
0x18001eed4  lea     rdx, aDeprecated; "Deprecated"
0x18001eedb  lea     rcx, [rbp+250h+var_270]; this
0x18001eedf  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001eee4  lea     rdx, [rbp+250h+var_270]
0x18001eee8  lea     rcx, [rsp+350h+var_310]
0x18001eeed  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)
0x18001eef2  test    al, al
0x18001eef4  jz      short loc_18001EF3E
0x18001eef6  lea     rcx, [rbp+250h+var_1A0]; this
0x18001eefd  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001ef02  mov     rdx, rax
0x18001ef05  lea     rcx, [rbp+250h+S2]
0x18001ef0c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ef11  nop
0x18001ef12  lea     r8, [rbp+250h+S2]
0x18001ef19  lea     rdx, [rbp+250h+var_E0]
0x18001ef20  lea     rcx, [rbp+250h+var_F0]
0x18001ef27  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18001ef2c  nop
0x18001ef2d  lea     rcx, [rbp+250h+S2]
0x18001ef34  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ef39  jmp     loc_18001F12B
0x18001ef3e  lea     rdx, aVersion; "Version"
0x18001ef45  lea     rcx, [rbp+250h+S2]; this
0x18001ef4c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001ef51  lea     r8, [rbp+250h+S2]
0x18001ef58  lea     rdx, [rbp+250h+var_198]
0x18001ef5f  lea     rcx, [rsp+350h+var_310]
0x18001ef64  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x18001ef69  nop
0x18001ef6a  lea     rcx, [rbp+250h+var_1D0]; this
0x18001ef71  call    ??0PackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::Management::Deployment::PackageSetItem::PackageSetItem(void)
0x18001ef76  nop
0x18001ef77  mov     rax, [rbp+250h+var_1A0]
0x18001ef7e  mov     [rbp+250h+S2], rax
0x18001ef85  lea     rdx, [rbp+250h+S2]
0x18001ef8c  lea     rcx, [rbp+250h+var_1D0]
0x18001ef93  call    ?PackageFamilyName@?$consume_Microsoft_Windows_Management_Deployment_IPackageSetItem@UIPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(winrt::param::hstring const &)
0x18001ef98  mov     [rbp+250h+var_1C8], rsi
0x18001ef9f  lea     rcx, [rbp+250h+var_198]; this
0x18001efa6  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001efab  mov     rcx, rax; Buffer
0x18001efae  lea     rax, [rbp+250h+var_1C8+6]
0x18001efb5  mov     [rsp+350h+var_328], rax; char *
0x18001efba  lea     rax, [rbp+250h+var_1C8+4]
0x18001efc1  mov     qword ptr [rsp+350h+var_330], rax; int
0x18001efc6  lea     r9, [rbp+250h+var_1C8+2]
0x18001efcd  lea     r8, [rbp+250h+var_1C8]
0x18001efd4  lea     rdx, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x18001efdb  call    swscanf_s
0x18001efe0  lea     rdx, [rbp+250h+var_1C8]
0x18001efe7  lea     rcx, [rbp+250h+var_1D0]
0x18001efee  call    ?MinVersion@?$consume_Microsoft_Windows_Management_Deployment_IPackageSetItem@UIPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUPackageVersion@ApplicationModel@Windows@3@@Z; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::MinVersion(winrt::Windows::ApplicationModel::PackageVersion const &)
0x18001eff3  lea     rdx, [rsp+350h+var_308]
0x18001eff8  lea     rcx, [rbp+250h+var_1D0]
0x18001efff  call    ?ProcessorArchitectureFilter@?$consume_Microsoft_Windows_Management_Deployment_IPackageSetItem@UIPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBW4PackageDependencyProcessorArchitectures@DynamicDependency@ApplicationModel@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::ProcessorArchitectureFilter(winrt::Microsoft::Windows::ApplicationModel::DynamicDependency::PackageDependencyProcessorArchitectures const &)
0x18001f004  lea     rdx, aVectorspaceid; "VectorSpaceId"
0x18001f00b  lea     rcx, [rbp+250h+S2]; this
0x18001f012  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001f017  lea     rdx, [rbp+250h+S2]
0x18001f01e  lea     rcx, [rsp+350h+var_310]
0x18001f023  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18001f028  test    al, al
0x18001f02a  jz      loc_18001F0D1
0x18001f030  lea     rdx, aPreferredvecto; "PreferredVectorSpace"
0x18001f037  lea     rcx, [rsp+350h+var_300+8]; this
0x18001f03c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001f041  lea     rdx, [rsp+350h+var_300+8]
0x18001f046  lea     rcx, [rsp+350h+var_310]
0x18001f04b  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)
0x18001f050  test    al, al
0x18001f052  jz      loc_18001F0D1
0x18001f058  lea     rdx, aVectorspaceid; "VectorSpaceId"
  ... truncated ...
```

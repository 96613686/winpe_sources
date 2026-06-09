# ProviderEntryPoint::GetUiaNode(UiaClientState *,HWND__ *,UiaNodeType,InProcProxyRequest,long,long,bool,IUiaNode * *,ElementExtraInfo *,IClientConnection * *,std::optional<ElementCompletionInfo> *)

- ea: `0x180094d28`
- end: `0x180096bec`
- name: `?GetUiaNode@ProviderEntryPoint@@AEAAJPEAVUiaClientState@@PEAUHWND__@@W4UiaNodeType@@UInProcProxyRequest@@JJ_NPEAPEAVIUiaNode@@PEAUElementExtraInfo@@PEAPEAVIClientConnection@@PEAV?$optional@UElementCompletionInfo@@@std@@@Z`
- size: `7876`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, char, __int64, __int64, __int64, ElementCompletionInfo *)`
- caller_count: `4`
- callee_count: `77`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180093be0`
- `0x180094c90`
- `0x18010f844`
- `0x180124450`

## callees

- `0x180006830`
- `0x18000a1a8`
- `0x18000b790`
- `0x18000f680`
- `0x1800220f0`
- `0x180022140`
- `0x18002e42c`
- `0x18002f580`
- `0x180032724`
- `0x1800386b8`
- `0x18003b150`
- `0x18003c820`
- `0x18004cb90`
- `0x18004f144`
- `0x1800502c4`
- `0x18005a9e4`
- `0x18005bad0`
- `0x18005c908`
- `0x18005efa0`
- `0x18005fa48`
- `0x180061aec`
- `0x1800697bc`
- `0x180069c44`
- `0x180083ed0`
- `0x180093850`
- `0x180093bb4`
- `0x180093cc8`
- `0x1800946c0`
- `0x1800948b8`
- `0x1800948e8`
- `0x1800949e8`
- `0x180094a14`
- `0x180094b98`
- `0x180094d28`
- `0x180097018`
- `0x18009756c`
- `0x1800978a4`
- `0x1800979fc`
- `0x1800984e0`
- `0x180098590`
- `0x18009a990`
- `0x18009e080`
- `0x1800b3338`
- `0x1800cb620`
- `0x1800d9490`
- `0x1800db428`
- `0x18010ce3c`
- `0x18010f844`
- `0x18010feac`
- `0x18012104c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180095ddc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180095ddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009524a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009524a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800952ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800952ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180095db7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180095db7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095bed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095bed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095bfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009566a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096842`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009566a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800956df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800956df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b63`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x1800969d0`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x1800969d0`
- `ntdll!RtlFreeUnicodeString` at `0x180096a04`
- `ntdll!RtlFreeUnicodeString` at `0x180096a04`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x1800956c4`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x1800956c4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180095211`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180095211`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x180094de2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x180094de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180095aeb`
- `OLEAUT32!__imp_SysFreeString` at `0x180095aeb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180095734`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180095734`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800956fa`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800956fa`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800965aa`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800965cb`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800965aa`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800965cb`
- `RPCRT4!UuidCreateSequential` at `0x1800952d7`
- `RPCRT4!UuidCreateSequential` at `0x1800952d7`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180095b81`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180095ee8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009605f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009614e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009625a`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800966c3`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180096745`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180095b81`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180095ee8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009605f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009614e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009625a`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800966c3`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180096745`

## string_xrefs

- `0x1800951c6`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180095359`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180095442`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180095ea3`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180096026`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800960e0`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180096593`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180096678`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800966a8`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800966ef`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180096772`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180096795`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800967b9`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180096ad6`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x180095338`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x180096bb6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180096bc8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180096bda`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800965f2`: `OpenProcessTokenHelper`
- `0x180096699`: `GetPlatformSpecificSecurityAttributes`
- `0x180096a2b`: `CreateChannelBasedConnection`
- `0x180096017`: `StringCchPrintf(connectionString, objectPath)`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall ProviderEntryPoint::GetUiaNode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        int a7,
        unsigned __int8 a8,
        _QWORD *a9,
        struct IUnknown **a10,
        _QWORD *a11,
        ElementCompletionInfo *a12)
{
  _QWORD *v14; // r14
  HWND v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rbx
  _DWORD *v18; // rbx
  struct NavigationHelperProxyOneCore *v19; // r10
  int v20; // ecx
  __int64 ProcessIdentityForHwnd; // rax
  __int64 v22; // rbx
  _OWORD *v23; // rcx
  __int128 *v24; // rcx
  __int128 *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  const struct ProcessIdentity *v28; // r13
  unsigned int v29; // edi
  unsigned int v30; // r12d
  char v31; // si
  _BYTE *v32; // rbx
  int v33; // edi
  struct NavigationHelperProxyOneCore *v34; // rcx
  DWORD WindowThreadProcessId; // ebx
  char v36; // bl
  __int64 v37; // rcx
  int v38; // eax
  int v39; // ebx
  _BYTE *v40; // rax
  int v41; // eax
  int HwndFromViewId; // ebx
  char v43; // r13
  unsigned __int64 v44; // rsi
  ICreateErrorInfo *v45; // rcx
  unsigned __int64 v46; // rsi
  ICreateErrorInfo *v47; // rcx
  wil::details *hEvent; // rbx
  char v49; // r12
  DWORD CurrentProcessId; // eax
  int v51; // edx
  unsigned int v52; // ecx
  void *v53; // rsi
  signed int LastError; // esi
  int v55; // edx
  int v56; // r8d
  IErrorInfo *v57; // rax
  IErrorInfo *v58; // rdi
  ICreateErrorInfo *v59; // rcx
  char v60; // r13
  int v61; // eax
  __int64 v62; // r8
  __int64 v63; // r9
  int ChannelBasedConnection; // edi
  int v65; // edi
  __int64 v66; // rcx
  __int64 v67; // r13
  int v68; // eax
  int v69; // r12d
  BOOL v70; // edi
  struct HwndProviderTypeCache *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  unsigned int v74; // edx
  struct IUnknown **v75; // rdi
  char v76; // al
  unsigned int v77; // edx
  __int64 v78; // rcx
  const char *v79; // r9
  const char *v80; // r9
  const char *v81; // r9
  LPVOID v82; // rcx
  struct NavigationHelperProxyOneCore *v83; // rcx
  void *v84; // rbx
  HANDLE ProcessHeap; // rax
  int v87; // edi
  int i; // ebx
  const unsigned __int16 *v89; // rcx
  int v90; // r8d
  const unsigned __int16 *v91; // r9
  __int64 v92; // rcx
  struct NavigationHelperProxyOneCore *v93; // rcx
  void *v94; // rdx
  LPVOID lpSecurityDescriptor; // rcx
  struct NavigationHelperProxyOneCore *v96; // rcx
  __int64 v97; // rcx
  void *v98; // rdx
  __int64 v99; // rcx
  LPVOID v100; // rcx
  struct NavigationHelperProxyOneCore *v101; // rcx
  struct HwndProviderTypeCache *Instance; // rax
  __int64 v103; // rdx
  __int64 v104; // rax
  void *v105; // rdx
  __int64 v106; // rcx
  LPVOID v107; // rcx
  struct NavigationHelperProxyOneCore *v108; // rcx
  void *v109; // rdx
  wil::details **v110; // rdi
  int v111; // ecx
  __int64 ProcessIdentityForEndpoint; // rax
  const wchar_t *v113; // rdx
  char v114; // dl
  void *v115; // rcx
  NavigationHelperProxyOneCore *v116; // r10
  int v117; // eax
  unsigned int v118; // eax
  int v119; // eax
  unsigned int ViewId; // eax
  __int64 v121; // r10
  __int64 ProcessIdentityForView; // rax
  __int64 v123; // rbx
  void *v124; // rdi
  char *v125; // rbx
  void *v126; // rdi
  int v127; // edi
  const char *v128; // rax
  __int64 v129; // rdx
  _QWORD *v130; // rax
  void *p_Uuid; // [rsp+20h] [rbp-110h]
  int Data2; // [rsp+20h] [rbp-110h]
  __int64 v133; // [rsp+20h] [rbp-110h]
  __int64 v134; // [rsp+20h] [rbp-110h]
  int v135; // [rsp+20h] [rbp-110h]
  char *v136; // [rsp+28h] [rbp-108h]
  char *v137; // [rsp+28h] [rbp-108h]
  char *v138; // [rsp+28h] [rbp-108h]
  char ExistingConnection; // [rsp+B0h] [rbp-80h] BYREF
  char v140; // [rsp+B1h] [rbp-7Fh] BYREF
  _WORD v141[7]; // [rsp+B2h] [rbp-7Eh] BYREF
  struct NavigationHelperProxyOneCore *v142; // [rsp+C0h] [rbp-70h] BYREF
  _QWORD *v143; // [rsp+C8h] [rbp-68h] BYREF
  int v144; // [rsp+D0h] [rbp-60h]
  ICreateErrorInfo *pperrinfo[2]; // [rsp+E0h] [rbp-50h] BYREF
  int v146; // [rsp+F0h] [rbp-40h]
  unsigned __int64 v147; // [rsp+100h] [rbp-30h] BYREF
  int v148[2]; // [rsp+108h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+110h] [rbp-20h] BYREF
  HANDLE v150; // [rsp+118h] [rbp-18h] BYREF
  unsigned int v151; // [rsp+120h] [rbp-10h] BYREF
  char v152; // [rsp+124h] [rbp-Ch]
  _QWORD v153[2]; // [rsp+128h] [rbp-8h] BYREF
  int v154; // [rsp+138h] [rbp+8h]
  wil::details *v155; // [rsp+140h] [rbp+10h] BYREF
  struct _SECURITY_ATTRIBUTES v156; // [rsp+148h] [rbp+18h] BYREF
  int v157; // [rsp+160h] [rbp+30h]
  int Data1; // [rsp+164h] [rbp+34h]
  __int64 v159; // [rsp+168h] [rbp+38h]
  __int64 v160; // [rsp+170h] [rbp+40h]
  __int64 v161; // [rsp+178h] [rbp+48h] BYREF
  __int64 v162; // [rsp+180h] [rbp+50h]
  __int64 v163; // [rsp+188h] [rbp+58h]
  __int64 v164; // [rsp+190h] [rbp+60h]
  _QWORD *v165; // [rsp+198h] [rbp+68h]
  struct IUnknown **v166; // [rsp+1A0h] [rbp+70h]
  __int128 v167; // [rsp+1B0h] [rbp+80h] BYREF
  _BYTE v168[16]; // [rsp+1C0h] [rbp+90h] BYREF
  LPVOID lpMem; // [rsp+1D0h] [rbp+A0h]
  char v170; // [rsp+1D8h] [rbp+A8h]
  _BYTE v171[48]; // [rsp+1E0h] [rbp+B0h] BYREF
  UUID Uuid; // [rsp+210h] [rbp+E0h] BYREF
  __m128i si128; // [rsp+220h] [rbp+F0h]
  struct IUnknown *v174; // [rsp+230h] [rbp+100h] BYREF
  char v175; // [rsp+238h] [rbp+108h]
  GUID v176; // [rsp+23Ch] [rbp+10Ch]
  BSTR bstrString; // [rsp+250h] [rbp+120h]
  struct IUnknown *v178; // [rsp+258h] [rbp+128h] BYREF
  __int128 v179; // [rsp+260h] [rbp+130h]
  struct IUnknown *v180; // [rsp+270h] [rbp+140h]
  __int64 v181; // [rsp+278h] [rbp+148h]
  char v182; // [rsp+280h] [rbp+150h]
  __int64 v183; // [rsp+290h] [rbp+160h] BYREF
  int v184; // [rsp+298h] [rbp+168h]
  __int128 v185; // [rsp+29Ch] [rbp+16Ch]
  void **v186; // [rsp+2B0h] [rbp+180h] BYREF
  int v187; // [rsp+2B8h] [rbp+188h] BYREF
  char v188; // [rsp+2BCh] [rbp+18Ch]
  int v189; // [rsp+2E0h] [rbp+1B0h] BYREF
  const char *v190; // [rsp+2E8h] [rbp+1B8h]
  __int64 v191; // [rsp+2F0h] [rbp+1C0h]
  char v192; // [rsp+2F8h] [rbp+1C8h]
  int v193; // [rsp+300h] [rbp+1D0h]
  _BYTE v194[152]; // [rsp+308h] [rbp+1D8h] BYREF
  __int128 v195; // [rsp+3A0h] [rbp+270h]
  int v196; // [rsp+3B0h] [rbp+280h]
  __int64 v197; // [rsp+3B8h] [rbp+288h]
  int *v198; // [rsp+3C0h] [rbp+290h]
  __int64 v199; // [rsp+3C8h] [rbp+298h]
  __int64 v200; // [rsp+3D0h] [rbp+2A0h]
  void ***v201; // [rsp+3D8h] [rbp+2A8h]
  __int64 v202; // [rsp+3E0h] [rbp+2B0h]
  int v203; // [rsp+3E8h] [rbp+2B8h]
  int *v204; // [rsp+3F0h] [rbp+2C0h]
  char v205; // [rsp+3F8h] [rbp+2C8h]
  void *Block[5]; // [rsp+400h] [rbp+2D0h] BYREF
  __int64 v207; // [rsp+428h] [rbp+2F8h]
  const unsigned __int16 *v208; // [rsp+430h] [rbp+300h]
  __int64 v209; // [rsp+438h] [rbp+308h]
  __int128 v210; // [rsp+440h] [rbp+310h] BYREF
  __int128 v211; // [rsp+450h] [rbp+320h]
  char v212; // [rsp+460h] [rbp+330h]
  __int128 v213; // [rsp+468h] [rbp+338h] BYREF
  __int64 v214; // [rsp+478h] [rbp+348h]
  __int64 v215; // [rsp+480h] [rbp+350h]
  char v216; // [rsp+488h] [rbp+358h]
  unsigned __int16 v217[12]; // [rsp+490h] [rbp+360h] BYREF
  _BYTE v218[40]; // [rsp+4A8h] [rbp+378h] BYREF
  _BYTE v219[40]; // [rsp+4D0h] [rbp+3A0h] BYREF
  _BYTE v220[296]; // [rsp+4F8h] [rbp+3C8h] BYREF
  unsigned __int16 Src[200]; // [rsp+620h] [rbp+4F0h] BYREF
  unsigned __int16 v222; // [rsp+7B0h] [rbp+680h] BYREF
  char v223; // [rsp+7B2h] [rbp+682h] BYREF
  unsigned __int16 v224[2000]; // [rsp+1750h] [rbp+1620h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2748h] [rbp+2618h]

  v144 = a4;
  v164 = a3;
  v159 = a2;
  v166 = a10;
  *(_QWORD *)&v167 = a5;
  v165 = a9;
  v160 = (__int64)a11;
  v163 = (__int64)a12;
  v14 = 0;
  *a9 = 0;
  if ( a11 )
    *a11 = 0;
  LOBYTE(v213) = 0;
  if ( a12 && *((_BYTE *)a12 + 104) )
  {
    ElementCompletionInfo::~ElementCompletionInfo(a12);
    *((_BYTE *)a12 + 104) = 0;
  }
  std::_Optional_destruct_base<ElementCompletionInfo,0>::~_Optional_destruct_base<ElementCompletionInfo,0>(Block);
  if ( !*(_DWORD *)(a1 + 40) )
  {
    v15 = *(HWND *)(a1 + 24);
    if ( v15 == GetDesktopWindow() )
      return 0;
  }
  v187 = 0;
  v188 = 0;
  v192 = 0;
  v189 = 0;
  v190 = "ProviderEntryPointActivity";
  v191 = 0;
  v193 = 0;
  v195 = 0;
  memset_0(v194, 0, sizeof(v194));
  v196 = 1;
  v197 = 0;
  v198 = &v187;
  v199 = 0;
  v200 = 0;
  v201 = &v186;
  v202 = 0;
  v203 = 0;
  v204 = &v189;
  v205 = 0;
  v186 = &UiaProvider::ProviderEntryPointActivity::`vftable';
  UiaProvider::ProviderEntryPointActivity::StartActivity(
    (UiaProvider::ProviderEntryPointActivity *)&v186,
    "GetUiaNode",
    (const struct ProviderEntryPoint *)a1);
  UiaImportantTraceLoggingProvider::WatchCurrentThread(v168, v16, a1);
  v17 = a2 + 16;
  if ( a2
    && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v17 + 56LL) + 880LL)
    && !ProviderEntryPoint::IsOnThreadHwnd((ProviderEntryPoint *)a1) )
  {
    v33 = 0;
LABEL_188:
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)v168);
    v186 = &UiaProvider::ProviderEntryPointActivity::`vftable';
    wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v186);
    wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v186);
    return (unsigned int)v33;
  }
  v148[0] = 0;
  v148[1] = 0;
  v142 = 0;
  NavigationHelperProxyOneCore::GetInstance(&v142);
  if ( a2 )
  {
    v18 = *(_DWORD **)(*(_QWORD *)v17 + 56LL);
    *(_QWORD *)&Uuid.Data1 = v18;
    if ( v18 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v18 + 8LL))(v18);
    if ( v18[216] >= 0x80000u )
    {
      LOBYTE(v148[0]) = 1;
      v33 = (*(__int64 (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v18 + 480LL))(v18, &v148[1]);
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x247,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
          (const char *)(unsigned int)v33,
          (int)"get_ConnectionTimeout",
          v136);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v18 + 16LL))(v18);
        v34 = v142;
        if ( v142 )
        {
          v142 = 0;
          (*(void (__fastcall **)(__int64))(*((_QWORD *)v34 + 2) + 16LL))((__int64)v34 + 16);
        }
        goto LABEL_188;
      }
    }
    else
    {
      LOBYTE(v148[0]) = 0;
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( !BasicUiaUtils::s_isDesktop || *(_DWORD *)(a1 + 40) != 1 )
  {
LABEL_20:
    v19 = v142;
    goto LABEL_21;
  }
  v19 = v142;
  if ( v142 )
  {
    v162 = 0;
    ProviderEntryPoint::GetViewId((ProviderEntryPoint *)a1);
    HwndFromViewId = NavigationHelperProxyOneCore::GetHwndFromViewId(v116);
    if ( HwndFromViewId < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x251,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)(unsigned int)HwndFromViewId,
        (int)"GetHwndFromViewId",
        v136);
      goto LABEL_214;
    }
    *(_DWORD *)(a1 + 40) = 0;
    *(_QWORD *)(a1 + 24) = v162;
    goto LABEL_20;
  }
LABEL_21:
  if ( !*(_BYTE *)(a1 + 216) )
  {
    LODWORD(Block[0]) = 0;
    BYTE4(Block[2]) = 0;
    LOBYTE(v209) = 0;
    v212 = 0;
    v216 = 0;
    v20 = *(_DWORD *)(a1 + 40);
    if ( v20 )
    {
      v111 = v20 - 1;
      if ( v111 )
      {
        if ( v111 != 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x782,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
            (const char *)0x8000FFFFLL,
            (int)p_Uuid);
        *(_OWORD *)pperrinfo = *(_OWORD *)(a1 + 44);
        v146 = *(_DWORD *)(a1 + 60);
        Uuid = *(UUID *)(a1 + 24);
        ProcessIdentityForEndpoint = ProviderEntryPoint::ProcessIdentityCacheHelper::GetProcessIdentityForEndpoint(
                                       a1 + 224,
                                       v217,
                                       &Uuid,
                                       pperrinfo);
        ProcessIdentity::operator=(Block, ProcessIdentityForEndpoint);
        std::optional<std::wstring>::~optional<std::wstring>(v220);
        std::optional<std::wstring>::~optional<std::wstring>(v219);
        std::optional<std::wstring>::~optional<std::wstring>(v218);
      }
      else
      {
        if ( !v19 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x778,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
            (const char *)0x80070057LL,
            (int)p_Uuid);
        Uuid = *(UUID *)(a1 + 44);
        si128.m128i_i32[0] = *(_DWORD *)(a1 + 60);
        ViewId = ProviderEntryPoint::GetViewId((ProviderEntryPoint *)a1);
        p_Uuid = &Uuid;
        ProcessIdentityForView = ProviderEntryPoint::ProcessIdentityCacheHelper::GetProcessIdentityForView(
                                   a1 + 224,
                                   v217,
                                   v121,
                                   ViewId);
        ProcessIdentity::operator=(Block, ProcessIdentityForView);
        ProcessIdentity::~ProcessIdentity((ProcessIdentity *)v217);
      }
    }
    else
    {
      Uuid = *(UUID *)(a1 + 44);
      si128.m128i_i32[0] = *(_DWORD *)(a1 + 60);
      ProcessIdentityForHwnd = ProviderEntryPoint::ProcessIdentityCacheHelper::GetProcessIdentityForHwnd(
                                 a1 + 224,
                                 v217,
                                 *(_QWORD *)(a1 + 24),
                                 &Uuid);
      v22 = ProcessIdentityForHwnd;
      LODWORD(Block[0]) = *(_DWORD *)ProcessIdentityForHwnd;
      *(_OWORD *)((char *)Block + 4) = *(_OWORD *)(ProcessIdentityForHwnd + 4);
      BYTE4(Block[2]) = *(_BYTE *)(ProcessIdentityForHwnd + 20);
      *(_WORD *)((char *)&Block[2] + 5) = *(_WORD *)(ProcessIdentityForHwnd + 21);
      HIBYTE(Block[2]) = *(_BYTE *)(ProcessIdentityForHwnd + 23);
      v23 = (_OWORD *)(ProcessIdentityForHwnd + 24);
      if ( *(_BYTE *)(ProcessIdentityForHwnd + 56) )
      {
        if ( (_BYTE)v209 )
        {
          std::wstring::operator=(&Block[3], ProcessIdentityForHwnd + 24);
        }
        else
        {
          *(_OWORD *)&Block[3] = 0;
          v207 = 0;
          v208 = 0;
          *(_OWORD *)&Block[3] = *v23;
          v207 = *(_QWORD *)(ProcessIdentityForHwnd + 40);
          v208 = *(const unsigned __int16 **)(ProcessIdentityForHwnd + 48);
          *(_QWORD *)(ProcessIdentityForHwnd + 40) = 0;
          *(_QWORD *)(ProcessIdentityForHwnd + 48) = 7;
          *(_WORD *)v23 = 0;
          LOBYTE(v209) = 1;
        }
      }
      else if ( (_BYTE)v209 )
      {
        std::wstring::_Tidy_deallocate(&Block[3]);
        LOBYTE(v209) = 0;
      }
      v24 = (__int128 *)(v22 + 64);
      if ( *(_BYTE *)(v22 + 96) )
      {
        if ( v212 )
        {
          std::wstring::operator=(&v210, v22 + 64);
        }
        else
        {
          v210 = 0;
          v211 = 0;
          v210 = *v24;
          v211 = *(_OWORD *)(v22 + 80);
          *(_QWORD *)(v22 + 80) = 0;
          *(_QWORD *)(v22 + 88) = 7;
          *(_WORD *)v24 = 0;
          v212 = 1;
        }
      }
      else if ( v212 )
      {
        std::wstring::_Tidy_deallocate(&v210);
        v212 = 0;
      }
      v25 = (__int128 *)(v22 + 104);
      if ( *(_BYTE *)(v22 + 136) )
      {
        if ( v216 )
        {
          std::wstring::operator=(&v213, v22 + 104);
        }
        else
        {
          v213 = 0;
          v214 = 0;
          v215 = 0;
          v213 = *v25;
          v214 = *(_QWORD *)(v22 + 120);
          v215 = *(_QWORD *)(v22 + 128);
          *(_QWORD *)(v22 + 120) = 0;
          *(_QWORD *)(v22 + 128) = 7;
          *(_WORD *)v25 = 0;
          v216 = 1;
        }
      }
      else if ( v216 )
      {
        std::wstring::_Tidy_deallocate(&v213);
        v216 = 0;
      }
      if ( v220[32] )
        std::wstring::_Tidy_deallocate(v220);
      if ( v219[32] )
        std::wstring::_Tidy_deallocate(v219);
      if ( v218[32] )
        std::wstring::_Tidy_deallocate(v218);
    }
    v26 = a1 + 72;
    if ( *(_BYTE *)(a1 + 216) )
    {
      ProcessIdentity::operator=(v26, Block);
    }
    else
    {
      ProcessIdentity::ProcessIdentity(v26, Block);
      *(_BYTE *)(v27 + 144) = 1;
    }
    if ( v216 )
      std::wstring::_Tidy_deallocate(&v213);
    if ( v212 )
      std::wstring::_Tidy_deallocate(&v210);
    if ( (_BYTE)v209 )
      std::wstring::_Tidy_deallocate(&Block[3]);
  }
  v28 = (const struct ProcessIdentity *)(a1 + 72);
  v29 = *(_DWORD *)(a1 + 72);
  v157 = v29;
  if ( v29 == -1 )
  {
    wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v186);
    HwndFromViewId = 0;
    goto LABEL_214;
  }
  v30 = v29;
  v151 = v29;
  v31 = 0;
  v152 = 0;
  v32 = (_BYTE *)(a1 + 44);
  v153[0] = *(_QWORD *)(a1 + 44);
  v153[1] = *(_QWORD *)(a1 + 52);
  v154 = *(_DWORD *)(a1 + 60);
  v143 = 0;
  if ( *(_BYTE *)(a1 + 60) )
    goto LABEL_50;
  if ( !*(_DWORD *)(a1 + 40) )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)(a1 + 24), 0);
    v36 = WindowThreadProcessId == GetCurrentThreadId();
LABEL_56:
    v140 = v36;
    if ( v36 )
    {
      ExistingConnection = 0;
      goto LABEL_64;
    }
    v32 = (_BYTE *)(a1 + 44);
    goto LABEL_58;
  }
  if ( *(_DWORD *)(a1 + 40) == 1 && v29 == GetCurrentProcessId() )
  {
    v140 = 0;
    v118 = ProviderEntryPoint::GetViewId((ProviderEntryPoint *)a1);
    v119 = anonymous_namespace_::CurrentThreadCoreWindowMatchesViewId(v118, &v140);
    if ( v119 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F5,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)(unsigned int)v119,
        (int)p_Uuid);
    v36 = v140;
    goto LABEL_56;
  }
LABEL_50:
  v140 = 0;
LABEL_58:
  v143 = 0;
  *(_QWORD *)&Uuid.Data1 = &ChannelBasedClientConnectionManager::_classLock;
  EnterCriticalSection(&ChannelBasedClientConnectionManager::_classLock);
  v14 = (_QWORD *)qword_18039F640;
  if ( !qword_18039F640 )
    goto LABEL_63;
  while ( 1 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v14 + 64LL))(v14) != v29 )
      goto LABEL_60;
    v40 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD *, ICreateErrorInfo **))(*v14 + 104LL))(v14, pperrinfo);
    if ( v32[16] )
      break;
    if ( !v40[16] )
      goto LABEL_61;
LABEL_60:
    v14 = (_QWORD *)v14[7];
    if ( !v14 )
      goto LABEL_61;
  }
  if ( !v40[16] || memcmp_0(v32, v40, 0x10u) )
    goto LABEL_60;
LABEL_61:
  v28 = (const struct ProcessIdentity *)(a1 + 72);
  if ( v14 )
    (*(void (__fastcall **)(_QWORD *))(*v14 + 8LL))(v14);
LABEL_63:
  v143 = v14;
  ExistingConnection = v14 != 0;
  LeaveCriticalSection(&ChannelBasedClientConnectionManager::_classLock);
  if ( !v14 )
  {
    ChannelBasedClientConnectionManager::LockNewConnection(v37, v29, v153);
    v31 = 1;
    v152 = 1;
    v143 = 0;
    ExistingConnection = ChannelBasedClientConnectionManager::FindExistingConnection(v97, v29, v32, &v143);
    if ( ExistingConnection )
    {
      AutoReleaseConnectionLock::~AutoReleaseConnectionLock((AutoReleaseConnectionLock *)&v151);
      v31 = v152;
    }
    v30 = v151;
    v14 = v143;
  }
LABEL_64:
  if ( *(_DWORD *)(a1 + 40) == 1 )
  {
    v87 = *(_DWORD *)(a1 + 24);
    AcquireSRWLockShared(&ProviderEntryPoint::s_inaccessibleViewIdsLock);
    for ( i = 0; i < (int)qword_18039DFF8; ++i )
    {
      if ( *((_DWORD *)ProviderEntryPoint::s_inaccessibleViewIds + i) == v87 )
        goto LABEL_180;
    }
    i = -1;
LABEL_180:
    ReleaseSRWLockShared(&ProviderEntryPoint::s_inaccessibleViewIdsLock);
    if ( i < 0 )
    {
      v29 = v157;
      goto LABEL_65;
    }
    Error::ProcessError(v89, v87, v90, v91);
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    if ( v31 )
      ChannelBasedClientConnectionManager::UnlockNewConnection(v92, v30, v153);
    v93 = v142;
    if ( v142 )
    {
      v142 = 0;
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v93 + 2) + 16LL))((__int64)v93 + 16);
    }
    v33 = -2147220991;
    goto LABEL_188;
  }
LABEL_65:
  Uuid = 0;
  UuidCreateSequential(&Uuid);
  if ( *(_DWORD *)(a1 + 40) )
  {
    LODWORD(v136) = Uuid.Data3;
    Data2 = Uuid.Data2;
    v41 = StringCchPrintfW(v217, 0xC8u, L"%x-%x-%x-%x%x-%x%x%x%x%x%x", Uuid.Data1);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BE,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)(unsigned int)v41,
        Data2);
    Data1 = 0;
    p_Uuid = v217;
    v117 = StringCchPrintfW(Src, 0xC8u, L"%ws_%ws", L"%ws");
    if ( v117 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C0,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)(unsigned int)v117,
        (int)v217);
    goto LABEL_78;
  }
  Data1 = Uuid.Data1;
  if ( !Uuid.Data1 )
  {
    Src[0] = 0;
    goto LABEL_77;
  }
  v136 = (char *)Uuid.Data1;
  LODWORD(p_Uuid) = v29;
  v38 = StringCchPrintfW(Src, 0xC8u, L"%ws_%d_%04Ix", L"%ws");
  v39 = v38;
  if ( v38 >= 0 )
  {
LABEL_77:
    v39 = 0;
    goto LABEL_69;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x62,
    (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
    (const char *)(unsigned int)v38,
    v29);
LABEL_69:
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6B9,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)v39,
      (int)p_Uuid);
LABEL_78:
  v156.lpSecurityDescriptor = 0;
  HwndFromViewId = UiaUtils::GetPlatformSpecificSecurityAttributes(v28, &v156);
  if ( HwndFromViewId < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x295,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)HwndFromViewId,
      (int)"GetPlatformSpecificSecurityAttributes",
      v136);
    if ( v156.lpSecurityDescriptor )
    {
      FreeTransientObjectSecurityDescriptor();
      v156.lpSecurityDescriptor = 0;
    }
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v143);
    AutoReleaseConnectionLock::~AutoReleaseConnectionLock((AutoReleaseConnectionLock *)&v151);
    goto LABEL_214;
  }
  if ( !byte_1803A1918 || !BasicUiaUtils::IsOneCore() || (v43 = 1, (NtCurrentPeb()->BitField & 0x20) != 0) )
    v43 = 0;
  Uuid = 0;
  si128 = 0;
  v44 = -1;
  do
    ++v44;
  while ( Src[v44] );
  if ( v44 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v44 > 7 )
  {
    v123 = std::wstring::_Calculate_growth(v44, 7, 0x7FFFFFFFFFFFFFFELL);
    v124 = (void *)std::allocator<unsigned short>::allocate(&Uuid, v123 + 1);
    *(_QWORD *)&Uuid.Data1 = v124;
    si128.m128i_i64[0] = v44;
    si128.m128i_i64[1] = v123;
    memcpy_0(v124, Src, 2 * v44);
    *((_WORD *)v124 + v44) = 0;
  }
  else
  {
    si128.m128i_i64[0] = v44;
    si128.m128i_i64[1] = 7;
    memcpy_0(&Uuid, Src, 2 * v44);
    *((_WORD *)&Uuid.Data1 + v44) = 0;
  }
  LOBYTE(p_Uuid) = v43;
  ProviderEntryPoint::CreateConnectionEvent(&v150, &v156, &Uuid, 0, p_Uuid);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v147 = 2 * si128.m128i_i64[1] + 2;
    v45 = *(ICreateErrorInfo **)&Uuid.Data1;
    pperrinfo[0] = *(ICreateErrorInfo **)&Uuid.Data1;
    if ( v147 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)pperrinfo, &v147);
      v45 = pperrinfo[0];
    }
    operator delete(v45);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Uuid.Data1) = 0;
  memset(Block, 0, 32);
  v46 = -1;
  do
    ++v46;
  while ( Src[v46] );
  if ( v46 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v46 > 7 )
  {
    v125 = (char *)std::wstring::_Calculate_growth(v46, 7, 0x7FFFFFFFFFFFFFFELL);
    v126 = (void *)std::allocator<unsigned short>::allocate(Block, v125 + 1);
    Block[0] = v126;
    Block[2] = (void *)v46;
    Block[3] = v125;
    memcpy_0(v126, Src, 2 * v46);
    *((_WORD *)v126 + v46) = 0;
  }
  else
  {
    Block[2] = (void *)v46;
    Block[3] = (void *)7;
    memcpy_0(Block, Src, 2 * v46);
    *((_WORD *)Block + v46) = 0;
  }
  LOBYTE(v133) = v43;
  ProviderEntryPoint::CreateConnectionEvent(&hObject, &v156, Block, 2, v133);
  if ( Block[3] > (void *)7 )
  {
    v147 = 2 * (__int64)Block[3] + 2;
    v47 = (ICreateErrorInfo *)Block[0];
    pperrinfo[0] = (ICreateErrorInfo *)Block[0];
    if ( v147 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)pperrinfo, &v147);
      v47 = pperrinfo[0];
    }
    operator delete(v47);
  }
  *(__m128i *)&Block[2] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  hEvent = 0;
  v155 = 0;
  v49 = ExistingConnection;
  if ( !ExistingConnection && !*(_BYTE *)(a1 + 60) )
  {
    std::wstring::wstring(Block, Src);
    LOBYTE(v134) = v43;
    v110 = (wil::details **)ProviderEntryPoint::CreateConnectionEvent(&Uuid, &v156, Block, 1, v134);
    if ( &v155 != v110 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &v155,
        *v110);
      *v110 = 0;
      hEvent = v155;
    }
    if ( *(_QWORD *)&Uuid.Data1 )
      wil::details::CloseHandle(*(wil::details **)&Uuid.Data1, v109);
    std::wstring::_Tidy_deallocate(Block);
  }
  CurrentProcessId = GetCurrentProcessId();
  v53 = OpenProcessTokenHelper(v52, v51, CurrentProcessId);
  *(_QWORD *)&Uuid.Data1 = v53;
  if ( !v53 )
  {
    LastError = GetLastError();
    pperrinfo[0] = 0;
    if ( CreateErrorInfo(pperrinfo) >= 0 )
    {
      ((void (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo[0]->lpVtbl->SetDescription)(
        pperrinfo[0],
        L"Hooking into LowBox server");
      v57 = (IErrorInfo *)QI<IErrorInfo>(pperrinfo[0]);
      v58 = v57;
      if ( v57 )
        SetErrorInfo(0, v57);
      if ( v58 )
        ((void (__fastcall *)(IErrorInfo *))v58->lpVtbl->Release)(v58);
    }
    v59 = pperrinfo[0];
    if ( pperrinfo[0] )
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo[0]->lpVtbl->Release)(pperrinfo[0]);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) != 0 )
    {
      LODWORD(pperrinfo[0]) = LastError;
      Block[2] = (void *)L"OpenProcessTokenHelper";
      Block[3] = (void *)46;
      Block[4] = pperrinfo;
      v207 = 4;
      v208 = L"Hooking into LowBox server";
      v209 = 54;
      McGenEventWrite_EventWriteTransfer(v59, Error_OtherError);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, v56, LastError, (__int64)L"Hooking into LowBox server");
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    AutoCleanupInfo<void *>::SafeRelease(&Uuid);
    if ( LastError >= 0 )
      goto LABEL_209;
LABEL_122:
    v33 = StringCchPrintfW(&v222, 0x7D0u, L"!%ws", Src);
    if ( v33 >= 0 )
      goto LABEL_123;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)v33,
      (int)"StringCchPrintf(connectionString)",
      v136);
    if ( hEvent )
      wil::details::CloseHandle(hEvent, v94);
    if ( hObject )
      wil::details::CloseHandle((wil::details *)hObject, v94);
    if ( v150 )
      wil::details::CloseHandle((wil::details *)v150, v94);
    lpSecurityDescriptor = v156.lpSecurityDescriptor;
    if ( v156.lpSecurityDescriptor )
    {
      FreeTransientObjectSecurityDescriptor();
      v156.lpSecurityDescriptor = 0;
    }
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    if ( v152 )
      ChannelBasedClientConnectionManager::UnlockNewConnection(lpSecurityDescriptor, v151, v153);
    v96 = v142;
    if ( v142 )
    {
      v142 = 0;
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v96 + 2) + 16LL))((__int64)v96 + 16);
    }
    goto LABEL_188;
  }
  LODWORD(v147) = 0;
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( BasicUiaUtils::s_isDesktop )
  {
    if ( !(unsigned int)GetAppContainerNamedObjectPath(v53, 0, 2000, v224, &v147) )
    {
LABEL_105:
      if ( v53 != (void *)-1LL )
        CloseHandle(v53);
      goto LABEL_122;
    }
  }
  else
  {
    *(_OWORD *)pperrinfo = 0;
    RtlGetAppContainerNamedObjectPath(v53, 0, 0, pperrinfo);
    if ( !pperrinfo[1] )
      goto LABEL_105;
    LODWORD(v147) = LOWORD(pperrinfo[0]);
    v127 = StringCchCopyNW(v224, 0x7D0u, (const unsigned __int16 *)pperrinfo[1], LOWORD(pperrinfo[0]));
    RtlFreeUnicodeString((PUNICODE_STRING)pperrinfo);
    if ( v127 < 0 )
      goto LABEL_105;
  }
  if ( !(_DWORD)v147 )
    goto LABEL_105;
  AutoCleanupInfo<void *>::SafeRelease(&Uuid);
LABEL_209:
  ChannelBasedConnection = StringCchPrintfW(&v222, 0x7D0u, L"!%ws\\%ws", v224, Src);
  if ( ChannelBasedConnection < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)ChannelBasedConnection,
      (int)"StringCchPrintf(connectionString, objectPath)",
      v136);
    goto LABEL_211;
  }
LABEL_123:
  LOBYTE(v141[0]) = 0;
  memset(Block, 0, 32);
  v183 = 0;
  v184 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
  v185 = *(_OWORD *)((char *)&Block[1] + 4);
  *(_QWORD *)&v141[3] = 0;
  v174 = 0;
  v175 &= 0xC0u;
  v176 = GUID_NULL;
  bstrString = 0;
  v182 = 0;
  v161 = 0;
  ExistingConnection = 1;
  v60 = v140;
  v61 = ProviderEntryPoint::ConnectToProvider(
          a1,
          (int)&v222,
          Data1,
          v148[0],
          (__int64)v150,
          (__int64)hObject,
          hEvent,
          v140,
          v49,
          v157,
          v159,
          v144,
          v164,
          (__int64)v14,
          (__int64)v141,
          (__int64)&v141[3],
          (__int64)&v174,
          (__int64)&v161,
          (__int64)&v183,
          (__int64)&ExistingConnection,
          v160,
          v163);
  ChannelBasedConnection = v61;
  if ( v61 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)v61,
      v135);
    ElementExtraInfo::~ElementExtraInfo((ElementExtraInfo *)&v174);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141[3]);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v155);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hObject);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v150);
    if ( !v156.lpSecurityDescriptor )
      goto LABEL_213;
    goto LABEL_212;
  }
  v33 = 0;
  if ( !ExistingConnection )
  {
    if ( !v60 && !*(_DWORD *)(a1 + 40) && !v144 )
    {
      Instance = HwndProviderTypeCache::GetInstance();
      if ( *(_DWORD *)(a1 + 40) )
        v103 = 0;
      else
        v103 = *(_QWORD *)(a1 + 24);
      HwndProviderTypeCache::InsertHwnd(Instance, v103, a1 + 44, 1);
    }
    v104 = *(_QWORD *)&v141[3];
    *(_QWORD *)&v141[3] = 0;
    *v165 = v104;
    ElementExtraInfo::operator=(v166, &v174);
    wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v186);
    ElementExtraInfo::~ElementExtraInfo((ElementExtraInfo *)&v174);
    v106 = *(_QWORD *)&v141[3];
    if ( *(_QWORD *)&v141[3] )
    {
      *(_QWORD *)&v141[3] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
    }
    if ( hEvent )
      wil::details::CloseHandle(hEvent, v105);
    if ( hObject )
      wil::details::CloseHandle((wil::details *)hObject, v105);
    if ( v150 )
      wil::details::CloseHandle((wil::details *)v150, v105);
    v107 = v156.lpSecurityDescriptor;
    if ( v156.lpSecurityDescriptor )
    {
      FreeTransientObjectSecurityDescriptor();
      v156.lpSecurityDescriptor = 0;
    }
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    if ( v152 )
      ChannelBasedClientConnectionManager::UnlockNewConnection(v107, v151, v153);
    v108 = v142;
    if ( v142 )
    {
      v142 = 0;
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v108 + 2) + 16LL))((__int64)v108 + 16);
    }
    goto LABEL_188;
  }
  if ( v49 )
    goto LABEL_126;
  v143 = 0;
  if ( v14 )
    (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
  v113 = L"Non-UIA";
  if ( !v144 )
    v113 = L"UIA";
  std::wstring::wstring(Block, v113);
  v114 = *(_BYTE *)(a1 + 60);
  if ( v114 )
  {
    pperrinfo[0] = 0;
    pperrinfo[1] = (ICreateErrorInfo *)v161;
  }
  else
  {
    *(_QWORD *)&Uuid.Data1 = hEvent;
    *(_QWORD *)Uuid.Data4 = 0;
  }
  v115 = &Uuid;
  if ( v114 )
    v115 = pperrinfo;
  ChannelBasedConnection = ChannelBasedClientConnectionManager::CreateChannelBasedConnection(
                             (_DWORD)v115,
                             (int)a1 + 72,
                             (unsigned int)&v223,
                             v159,
                             (__int64)v115,
                             *(__int64 *)v148,
                             (__int64)Block,
                             (__int64)&v143);
  std::wstring::_Tidy_deallocate(Block);
  if ( ChannelBasedConnection < 0 )
  {
    v128 = "CreateChannelBasedConnection";
    v129 = 784;
    goto LABEL_324;
  }
  v14 = v143;
LABEL_126:
  v65 = v144;
  if ( v144 == 3 )
    goto LABEL_144;
  v66 = *(_QWORD *)&v141[3];
  if ( *(_QWORD *)&v141[3] )
  {
    *(_QWORD *)&v141[3] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  }
  v167 = *(_OWORD *)v167;
  v67 = v163;
  LOBYTE(v63) = v141[0];
  LOBYTE(v62) = v49 ^ 1;
  v68 = LocalUiaNodeProxy::RealRemoteNodeFromProviderEntryPoint(
          v14,
          a1,
          v62,
          v63,
          v65,
          a6,
          a7,
          v164,
          &v167,
          *(_QWORD *)v148,
          a8,
          &v141[3],
          &v174,
          &v183,
          v163);
  v33 = v68;
  if ( v68 == -2147219455 )
  {
    v33 = -2147220991;
    Error::GeneralProviderError(0, L"RemoteNodeFromHwnd", -2147220991, 0, 421, 0);
    goto LABEL_217;
  }
  if ( v68 < 0 )
  {
LABEL_217:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)v33,
      (int)"RemoteNodeFromProviderEntryPoint",
      v137);
    ElementExtraInfo::~ElementExtraInfo((ElementExtraInfo *)&v174);
    v99 = *(_QWORD *)&v141[3];
    if ( *(_QWORD *)&v141[3] )
    {
      *(_QWORD *)&v141[3] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
    }
    if ( hEvent )
      wil::details::CloseHandle(hEvent, v98);
    if ( hObject )
      wil::details::CloseHandle((wil::details *)hObject, v98);
    if ( v150 )
      wil::details::CloseHandle((wil::details *)v150, v98);
    v100 = v156.lpSecurityDescriptor;
    if ( v156.lpSecurityDescriptor )
    {
      FreeTransientObjectSecurityDescriptor();
      v156.lpSecurityDescriptor = 0;
    }
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    if ( v152 )
      ChannelBasedClientConnectionManager::UnlockNewConnection(v100, v151, v153);
    v101 = v142;
    if ( v142 )
    {
      v142 = 0;
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v101 + 2) + 16LL))((__int64)v101 + 16);
    }
    goto LABEL_188;
  }
  if ( v183 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141[3]);
    v69 = v144;
    ChannelBasedConnection = ProviderEntryPoint::GetCrossMachineUiaNode(
                               (ProviderEntryPoint *)a1,
                               v159,
                               (__int64)&v141[3],
                               (__int64)&v174,
                               v160,
                               v67);
    if ( ChannelBasedConnection >= 0 )
      goto LABEL_133;
    v128 = "GetCrossMachineUiaNode via RemoteNodeFromProviderEntryPoint";
    v129 = 828;
LABEL_324:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v129,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)ChannelBasedConnection,
      (int)v128,
      v138);
    ElementExtraInfo::~ElementExtraInfo((ElementExtraInfo *)&v174);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141[3]);
LABEL_211:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v155);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hObject);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v150);
    if ( !v156.lpSecurityDescriptor )
      goto LABEL_213;
LABEL_212:
    FreeTransientObjectSecurityDescriptor();
    v156.lpSecurityDescriptor = 0;
LABEL_213:
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v143);
    AutoReleaseConnectionLock::~AutoReleaseConnectionLock((AutoReleaseConnectionLock *)&v151);
    HwndFromViewId = ChannelBasedConnection;
LABEL_214:
    Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalRelease(&v142);
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)v168);
    UiaProvider::ProviderEntryPointActivity::~ProviderEntryPointActivity((UiaProvider::ProviderEntryPointActivity *)&v186);
    return (unsigned int)HwndFromViewId;
  }
  v69 = v144;
LABEL_133:
  if ( !*(_DWORD *)(a1 + 40) && !v69 )
  {
    v70 = *(_QWORD *)&v141[3] == 0;
    v71 = HwndProviderTypeCache::GetInstance();
    if ( *(_DWORD *)(a1 + 40) )
      v72 = 0;
    else
      v72 = *(_QWORD *)(a1 + 24);
    HwndProviderTypeCache::InsertHwnd(v71, v72, a1 + 44, v70);
  }
  v73 = *(_QWORD *)&v141[3];
  *(_QWORD *)&v141[3] = 0;
  *v165 = v73;
  v74 = (unsigned int)v174;
  v75 = v166;
  if ( *v166 != v174 )
    ATL::AtlComPtrAssign(v166, v174);
  *((_BYTE *)v75 + 8) = v175;
  *(GUID *)((char *)v75 + 12) = v176;
  if ( bstrString && (int)HrSysAllocString(bstrString, (unsigned __int16 **)v75 + 4) < 0 )
    *(GUID *)((char *)v75 + 12) = GUID_NULL;
  v76 = *((_BYTE *)v75 + 80);
  if ( v182 )
  {
    if ( v76 )
    {
      v75[5] = v178;
      *((_OWORD *)v75 + 3) = v179;
      v75[8] = v180;
      wil::com_ptr_t<ProviderEntryPoint,wil::err_exception_policy>::operator=(v75 + 9, v181);
    }
    else
    {
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v75 + 5,
        &v178);
    }
  }
  else if ( v76 )
  {
    CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)(v75 + 5), v74);
    *((_BYTE *)v75 + 80) = 0;
  }
LABEL_144:
  if ( v160 && !*(_QWORD *)v160 )
  {
    v130 = v14;
    v14 = 0;
    v143 = 0;
    *(_QWORD *)v160 = v130;
  }
  wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v186);
  if ( v182 )
    CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)&v178, v77);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v174);
  v78 = *(_QWORD *)&v141[3];
  if ( *(_QWORD *)&v141[3] )
  {
    *(_QWORD *)&v141[3] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  }
  if ( hEvent && !CloseHandle(hEvent) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v79);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v80);
  if ( v150 && !CloseHandle(v150) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v81);
  v82 = v156.lpSecurityDescriptor;
  if ( v156.lpSecurityDescriptor )
  {
    FreeTransientObjectSecurityDescriptor();
    v156.lpSecurityDescriptor = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
  if ( v152 )
    ChannelBasedClientConnectionManager::UnlockNewConnection(v82, v151, v153);
  v83 = v142;
  if ( v142 )
  {
    v142 = 0;
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v83 + 2) + 16LL))((__int64)v83 + 16);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v171);
  if ( v170 )
  {
    v84 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v84);
    v170 = 0;
  }
  lpMem = 0;
  v186 = &UiaProvider::ProviderEntryPointActivity::`vftable';
  wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v186);
  wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v186);
  return 0;
}

```

## disassembly

```asm
0x180094d28  push    rbp
0x180094d2a  push    rbx
0x180094d2b  push    rsi
0x180094d2c  push    rdi
0x180094d2d  push    r12
0x180094d2f  push    r13
0x180094d31  push    r14
0x180094d33  push    r15
0x180094d35  lea     rbp, [rsp-25D8h]
0x180094d3d  mov     eax, 2708h
0x180094d42  call    _alloca_probe
0x180094d47  sub     rsp, rax
0x180094d4a  mov     rax, cs:__security_cookie
0x180094d51  xor     rax, rsp
0x180094d54  mov     [rbp+2610h+var_50], rax
0x180094d5b  mov     [rbp+2610h+var_2670], r9d
0x180094d5f  mov     [rbp+2610h+var_25B0], r8
0x180094d63  mov     rdi, rdx
0x180094d66  mov     [rbp+2610h+var_25D8], rdx
0x180094d6a  mov     r15, rcx
0x180094d6d  mov     rax, [rbp+2610h+arg_48]
0x180094d74  mov     [rbp+2610h+var_25A0], rax
0x180094d78  mov     rax, [rbp+2610h+arg_20]
0x180094d7f  mov     qword ptr [rbp+2610h+var_2590], rax
0x180094d86  mov     rcx, [rbp+2610h+arg_40]
0x180094d8d  mov     [rbp+2610h+var_25A8], rcx
0x180094d91  mov     rax, [rbp+2610h+arg_50]
0x180094d98  mov     [rbp+2610h+var_25D0], rax
0x180094d9c  mov     rbx, [rbp+2610h+arg_58]
0x180094da3  mov     [rbp+2610h+var_25B8], rbx
0x180094da7  xor     r14d, r14d
0x180094daa  mov     [rcx], r14
0x180094dad  test    rax, rax
0x180094db0  jnz     loc_180096754
0x180094db6  mov     byte ptr [rbp+2610h+var_22D8], r14b
0x180094dbd  test    rbx, rbx
0x180094dc0  jz      short loc_180094DCC
0x180094dc2  cmp     [rbx+68h], r14b
0x180094dc6  jnz     loc_180095E7C
0x180094dcc  lea     rcx, [rbp+2610h+Block]
0x180094dd3  call    ??1?$_Optional_destruct_base@UElementCompletionInfo@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<ElementCompletionInfo,0>::~_Optional_destruct_base<ElementCompletionInfo,0>(void)
0x180094dd8  cmp     [r15+28h], r14d
0x180094ddc  jnz     short loc_180094DF1
0x180094dde  mov     rbx, [r15+18h]
0x180094de2  call    cs:__imp_GetDesktopWindow
0x180094de8  cmp     rbx, rax
0x180094deb  jz      loc_180095C35
0x180094df1  mov     [rbp+2610h+var_2488], r14d
0x180094df8  mov     [rbp+2610h+var_2484], r14b
0x180094dff  mov     [rbp+2610h+var_2448], r14b
0x180094e06  mov     [rbp+2610h+var_2460], r14d
0x180094e0d  lea     rax, aProviderentryp; "ProviderEntryPointActivity"
0x180094e14  mov     [rbp+2610h+var_2458], rax
0x180094e1b  mov     [rbp+2610h+var_2450], r14
0x180094e22  mov     [rbp+2610h+var_2440], r14d
0x180094e29  xorps   xmm0, xmm0
0x180094e2c  movdqa  [rbp+2610h+var_23A0], xmm0
0x180094e34  xor     edx, edx; Val
0x180094e36  mov     r8d, 98h; Size
0x180094e3c  lea     rcx, [rbp+2610h+var_2438]; void *
0x180094e43  call    memset_0
0x180094e48  mov     [rbp+2610h+var_2390], 1
0x180094e52  xor     eax, eax
0x180094e54  mov     [rbp+2610h+var_2388], rax
0x180094e5b  lea     rax, [rbp+2610h+var_2488]
0x180094e62  mov     [rbp+2610h+var_2380], rax
0x180094e69  mov     [rbp+2610h+var_2378], r14
0x180094e70  mov     [rbp+2610h+var_2370], r14
0x180094e77  lea     rax, [rbp+2610h+var_2490]
0x180094e7e  mov     [rbp+2610h+var_2368], rax
0x180094e85  mov     [rbp+2610h+var_2360], r14
0x180094e8c  mov     [rbp+2610h+var_2358], r14d
0x180094e93  lea     rax, [rbp+2610h+var_2460]
0x180094e9a  mov     [rbp+2610h+var_2350], rax
0x180094ea1  mov     [rbp+2610h+var_2348], r14b
0x180094ea8  lea     rax, ??_7ProviderEntryPointActivity@UiaProvider@@6B@; const UiaProvider::ProviderEntryPointActivity::`vftable'
0x180094eaf  mov     [rbp+2610h+var_2490], rax
0x180094eb6  mov     r8, r15; struct ProviderEntryPoint *
0x180094eb9  lea     rdx, aGetuianode; "GetUiaNode"
0x180094ec0  lea     rcx, [rbp+2610h+var_2490]; this
0x180094ec7  call    ?StartActivity@ProviderEntryPointActivity@UiaProvider@@QEAAXPEBDAEBVProviderEntryPoint@@@Z; UiaProvider::ProviderEntryPointActivity::StartActivity(char const *,ProviderEntryPoint const &)
0x180094ecc  nop
0x180094ecd  mov     r8, r15
0x180094ed0  lea     rcx, [rbp+2610h+var_2580]
0x180094ed7  call    ?WatchCurrentThread@UiaImportantTraceLoggingProvider@@SA?AVActivityThreadWatcher@wil@@PEBDAEBVProviderEntryPoint@@@Z; UiaImportantTraceLoggingProvider::WatchCurrentThread(char const *,ProviderEntryPoint const &)
0x180094edc  nop
0x180094edd  lea     rbx, [rdi+10h]
0x180094ee1  test    rdi, rdi
0x180094ee4  jz      short loc_180094EFA
0x180094ee6  mov     rax, [rbx]
0x180094ee9  mov     rcx, [rax+38h]
0x180094eed  cmp     [rcx+370h], r14b
0x180094ef4  jnz     loc_1800960A8
0x180094efa  mov     byte ptr [rbp+2610h+var_2638], r14b
0x180094efe  xor     eax, eax
0x180094f00  mov     word ptr [rbp+2610h+var_2638+1], ax
0x180094f04  mov     byte ptr [rbp+2610h+var_2638+3], al
0x180094f07  mov     [rbp+2610h+var_2638+4], r14d
0x180094f0b  mov     [rbp+2610h+var_2680], r14
0x180094f0f  lea     rcx, [rbp+2610h+var_2680]; struct NavigationHelperProxyOneCore **
0x180094f13  call    ?GetInstance@NavigationHelperProxyOneCore@@SAJPEAPEAV1@@Z; NavigationHelperProxyOneCore::GetInstance(NavigationHelperProxyOneCore * *)
0x180094f18  test    rdi, rdi
0x180094f1b  jz      short loc_180094F64
0x180094f1d  mov     rax, [rbx]
0x180094f20  mov     rbx, [rax+38h]
0x180094f24  mov     qword ptr [rbp+2610h+Uuid.Data1], rbx
0x180094f2b  test    rbx, rbx
0x180094f2e  jz      short loc_180094F40
0x180094f30  mov     rax, [rbx]
0x180094f33  mov     rcx, rbx
0x180094f36  mov     rax, [rax+8]
0x180094f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094f3f  nop
0x180094f40  cmp     dword ptr [rbx+360h], 80000h
0x180094f4a  jnb     loc_18009518C
0x180094f50  mov     byte ptr [rbp+2610h+var_2638], r14b
0x180094f54  mov     rax, [rbx]
0x180094f57  mov     rcx, rbx
0x180094f5a  mov     rax, [rax+10h]
0x180094f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094f63  nop
0x180094f64  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180094f6a  nop
0x180094f6b  test    al, al
0x180094f6d  jz      loc_1800965A5
0x180094f73  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, r14b; bool BasicUiaUtils::s_isDesktop
0x180094f7a  jz      short loc_180094F87
0x180094f7c  cmp     dword ptr [r15+28h], 1
0x180094f81  jz      loc_1800964FC
0x180094f87  mov     r10, [rbp+2610h+var_2680]
0x180094f8b  mov     edi, 7
0x180094f90  cmp     [r15+0D8h], r14b
0x180094f97  jnz     loc_180095127
0x180094f9d  mov     dword ptr [rbp+2610h+Block], r14d
0x180094fa4  mov     [rbp+2610h+var_232C], r14b
0x180094fab  mov     byte ptr [rbp+2610h+var_2308], r14b
0x180094fb2  mov     [rbp+2610h+var_22E0], r14b
0x180094fb9  mov     [rbp+2610h+var_22B8], r14b
0x180094fc0  mov     ecx, [r15+28h]
0x180094fc4  test    ecx, ecx
0x180094fc6  jnz     loc_1800963BE
0x180094fcc  movups  xmm0, xmmword ptr [r15+2Ch]
0x180094fd1  movaps  xmmword ptr [rbp+2610h+Uuid.Data1], xmm0
0x180094fd8  mov     eax, [r15+3Ch]
0x180094fdc  mov     dword ptr [rbp+2610h+var_2520], eax
0x180094fe2  lea     rcx, [r15+0E0h]
0x180094fe9  lea     r9, [rbp+2610h+Uuid]
0x180094ff0  mov     r8, [r15+18h]
0x180094ff4  lea     rdx, [rbp+2610h+var_22B0]
0x180094ffb  call    ?GetProcessIdentityForHwnd@ProcessIdentityCacheHelper@ProviderEntryPoint@@QEAA?AUProcessIdentity@@PEAUHWND__@@V?$optional@U_GUID@@@std@@@Z; ProviderEntryPoint::ProcessIdentityCacheHelper::GetProcessIdentityForHwnd(HWND__ *,std::optional<_GUID>)
0x180095000  mov     rbx, rax
0x180095003  mov     ecx, [rax]
0x180095005  mov     dword ptr [rbp+2610h+Block], ecx
0x18009500b  movups  xmm0, xmmword ptr [rax+4]
0x18009500f  movdqu  xmmword ptr [rbp+2610h+Block+4], xmm0
0x180095017  mov     cl, [rax+14h]
0x18009501a  mov     [rbp+2610h+var_232C], cl
0x180095020  movzx   ecx, word ptr [rax+15h]
0x180095024  mov     [rbp+2610h+var_232B], cx
0x18009502b  mov     cl, [rax+17h]
0x18009502e  mov     [rbp+2610h+var_2329], cl
0x180095034  lea     rcx, [rax+18h]
0x180095038  cmp     [rcx+20h], r14b
0x18009503c  jnz     loc_180095C6F
0x180095042  cmp     byte ptr [rbp+2610h+var_2308], r14b
0x180095049  jnz     loc_180095F3D
0x18009504f  lea     rcx, [rbx+40h]
0x180095053  cmp     [rcx+20h], r14b
0x180095057  jnz     loc_180095CD7
0x18009505d  cmp     [rbp+2610h+var_22E0], r14b
0x180095064  jnz     loc_180095F55
0x18009506a  lea     rcx, [rbx+68h]
0x18009506e  cmp     [rcx+20h], r14b
0x180095072  jnz     loc_180095D3C
0x180095078  cmp     [rbp+2610h+var_22B8], r14b
0x18009507f  jnz     loc_180095F6D
0x180095085  cmp     [rbp+2610h+var_2228], r14b
0x18009508c  jz      short loc_18009509A
0x18009508e  lea     rcx, [rbp+2610h+var_2248]
0x180095095  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009509a  cmp     [rbp+2610h+var_2250], r14b
0x1800950a1  jz      short loc_1800950AF
0x1800950a3  lea     rcx, [rbp+2610h+var_2270]
0x1800950aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800950af  cmp     [rbp+2610h+var_2278], r14b
0x1800950b6  jz      short loc_1800950C4
0x1800950b8  lea     rcx, [rbp+2610h+var_2298]
0x1800950bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800950c4  lea     rcx, [r15+48h]
0x1800950c8  lea     rdx, [rbp+2610h+Block]
0x1800950cf  cmp     [rcx+90h], r14b
0x1800950d6  jnz     loc_180096443
0x1800950dc  call    ??0ProcessIdentity@@QEAA@$$QEAU0@@Z; ProcessIdentity::ProcessIdentity(ProcessIdentity &&)
0x1800950e1  mov     byte ptr [rcx+90h], 1
0x1800950e8  cmp     [rbp+2610h+var_22B8], r14b
0x1800950ef  jz      short loc_1800950FD
0x1800950f1  lea     rcx, [rbp+2610h+var_22D8]
0x1800950f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800950fd  cmp     [rbp+2610h+var_22E0], r14b
0x180095104  jz      short loc_180095112
0x180095106  lea     rcx, [rbp+2610h+var_2300]
0x18009510d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180095112  cmp     byte ptr [rbp+2610h+var_2308], r14b
0x180095119  jz      short loc_180095127
0x18009511b  lea     rcx, [rbp+2610h+var_2328]
0x180095122  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180095127  lea     r13, [r15+48h]
0x18009512b  mov     edi, [r13+0]
0x18009512f  mov     [rbp+2610h+var_25E0], edi
0x180095132  cmp     edi, 0FFFFFFFFh
0x180095135  jz      loc_18009682E
0x18009513b  mov     r12d, edi
0x18009513e  mov     [rbp+2610h+var_2620], edi
0x180095141  mov     sil, r14b
0x180095144  mov     [rbp+2610h+var_261C], r14b
0x180095148  lea     rbx, [r15+2Ch]
0x18009514c  mov     rax, [rbx]
0x18009514f  mov     [rbp+2610h+var_2618], rax
0x180095153  movsd   xmm0, qword ptr [rbx+8]
0x180095158  movsd   [rbp+2610h+var_2610], xmm0
0x18009515d  mov     eax, [rbx+10h]
0x180095160  mov     [rbp+2610h+var_2608], eax
0x180095163  mov     [rbp+2610h+var_2678], r14
0x180095167  xor     eax, eax
0x180095169  cmp     [r15+3Ch], al
0x18009516d  jnz     short loc_180095184
0x18009516f  cmp     [r15+28h], eax
0x180095173  jz      loc_18009520B
0x180095179  cmp     dword ptr [r15+28h], 1
0x18009517e  jz      loc_180096842
0x180095184  mov     [rbp+2610h+var_268F], al
0x180095187  jmp     loc_180095235
0x18009518c  mov     byte ptr [rbp+2610h+var_2638], 1
0x180095190  mov     rax, [rbx]
0x180095193  lea     rdx, [rbp+2610h+var_2638+4]
0x180095197  mov     rcx, rbx
0x18009519a  mov     rax, [rax+1E0h]
0x1800951a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800951a6  mov     edi, eax
0x1800951a8  test    eax, eax
0x1800951aa  jns     loc_180094F54
0x1800951b0  mov     rcx, [rbp+2618h]; this
0x1800951b7  lea     rax, aGetConnectiont; "get_ConnectionTimeout"
0x1800951be  mov     [rsp+2740h+var_2720], rax; int
0x1800951c3  mov     r9d, edi; char *
0x1800951c6  lea     r8, aOnecoreWindows_131; "onecore\\windows\\accessibletech\\uiaut"...
0x1800951cd  mov     edx, 247h; void *
0x1800951d2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800951d7  nop
0x1800951d8  mov     rax, [rbx]
0x1800951db  mov     rcx, rbx
0x1800951de  mov     rax, [rax+10h]
0x1800951e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800951e7  nop
0x1800951e8  mov     rcx, [rbp+2610h+var_2680]
0x1800951ec  test    rcx, rcx
0x1800951ef  jz      short loc_180095206
0x1800951f1  mov     [rbp+2610h+var_2680], r14
0x1800951f5  add     rcx, 10h
0x1800951f9  mov     rax, [rcx]
0x1800951fc  mov     rax, [rax+10h]
0x180095200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095205  nop
0x180095206  jmp     loc_180095E42
0x18009520b  xor     edx, edx; lpdwProcessId
0x18009520d  mov     rcx, [r15+18h]; hWnd
0x180095211  call    cs:__imp_GetWindowThreadProcessId
0x180095217  mov     ebx, eax
0x180095219  call    cs:__imp_GetCurrentThreadId
0x18009521f  cmp     ebx, eax
0x180095221  setz    bl
0x180095224  mov     [rbp+2610h+var_268F], bl
0x180095227  xor     eax, eax
0x180095229  test    bl, bl
0x18009522b  jnz     loc_180095DA4
0x180095231  lea     rbx, [r15+2Ch]
0x180095235  mov     [rbp+2610h+var_2678], rax
0x180095239  lea     rax, ?_classLock@ChannelBasedClientConnectionManager@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ChannelBasedClientConnectionManager::_classLock
0x180095240  mov     qword ptr [rbp+2610h+Uuid.Data1], rax
0x180095247  mov     rcx, rax; lpCriticalSection
0x18009524a  call    cs:__imp_EnterCriticalSection
0x180095250  nop
0x180095251  mov     r14, cs:qword_18039F640
0x180095258  test    r14, r14
0x18009525b  jz      short loc_180095298
0x18009525d  xor     r13d, r13d
0x180095260  mov     rax, [r14]
0x180095263  mov     rcx, r14
0x180095266  mov     rax, [rax+40h]
0x18009526a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009526f  cmp     eax, edi
0x180095271  jz      loc_18009536B
0x180095277  mov     r14, [r14+38h]
0x18009527b  test    r14, r14
0x18009527e  jnz     short loc_180095260
0x180095280  test    r14, r14
0x180095283  lea     r13, [r15+48h]
0x180095287  jz      short loc_180095298
0x180095289  mov     rax, [r14]
0x18009528c  mov     rcx, r14
  ... truncated ...
```

# AppReadiness::User::ExecutePreInstalledConfigTaskOrUpdateTaskForPackage(AppReadiness::TaskType,StateRepository::Cache::Entity::Package_NoThrow &,__int64)

- ea: `0x18004da98`
- end: `0x18004e068`
- name: `?ExecutePreInstalledConfigTaskOrUpdateTaskForPackage@User@AppReadiness@@IEAAXW4TaskType@2@AEAVPackage_NoThrow@Entity@Cache@StateRepository@@_J@Z`
- size: `1488`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005ac6c`

## callees

- `0x18000e4a0`
- `0x180015b70`
- `0x180019ff0`
- `0x180028814`
- `0x18002a970`
- `0x18002bf58`
- `0x18002ecbc`
- `0x18002f4bc`
- `0x18002f820`
- `0x18002ff94`
- `0x1800305a8`
- `0x180030914`
- `0x180038f14`
- `0x18003e210`
- `0x18003e234`
- `0x18003eab8`
- `0x18003eca8`
- `0x180049310`
- `0x18004be20`
- `0x18004bed8`
- `0x18004bf60`
- `0x18004c1c8`
- `0x18004da98`
- `0x18004e0a0`
- `0x18004e168`
- `0x180079010`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004dbc5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004dbc5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df51`

## string_xrefs

- `0x18004df84`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004df99`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004dfae`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004dfc3`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004dfd8`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004dfed`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004e002`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004e017`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004e02c`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004e041`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004e056`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18004dccf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18004dc01`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18004dc98`: `windows.preInstalledConfigTask`
- `0x18004dc9f`: `windows.updateTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall AppReadiness::User::ExecutePreInstalledConfigTaskOrUpdateTaskForPackage(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned __int64 a4)
{
  struct StateRepository::Cache::Manager_NoThrow *v8; // r14
  int v9; // eax
  bool v10; // bl
  int v11; // eax
  int v12; // eax
  int v13; // eax
  bool v14; // si
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // ebx
  int v19; // eax
  const unsigned __int16 *v20; // r9
  int v21; // eax
  __int64 v22; // rdx
  int v23; // ebx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  void *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  _QWORD *v32; // rdx
  int v33; // eax
  AppReadiness::TaskContext *v34; // rbx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  int *v38; // [rsp+20h] [rbp-E0h]
  bool v39; // [rsp+30h] [rbp-D0h] BYREF
  bool v40; // [rsp+31h] [rbp-CFh] BYREF
  int v41; // [rsp+32h] [rbp-CEh] BYREF
  AppReadiness::TaskContext *v42; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  int v44; // [rsp+48h] [rbp-B8h]
  __int64 v45; // [rsp+50h] [rbp-B0h]
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+60h] [rbp-A0h]
  __int64 v48; // [rsp+68h] [rbp-98h]
  __int128 v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+88h] [rbp-78h]
  __int128 v52; // [rsp+90h] [rbp-70h]
  __int128 v53; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+B0h] [rbp-50h]
  int v55; // [rsp+B8h] [rbp-48h]
  __int128 v56; // [rsp+C0h] [rbp-40h] BYREF
  int v57; // [rsp+D0h] [rbp-30h]
  __int64 v58; // [rsp+D8h] [rbp-28h]
  __int128 v59; // [rsp+E0h] [rbp-20h]
  __int128 v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+100h] [rbp+0h]
  __int64 v62[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v63; // [rsp+120h] [rbp+20h]
  __int64 v64; // [rsp+128h] [rbp+28h]
  __int128 v65; // [rsp+130h] [rbp+30h]
  __int128 v66; // [rsp+140h] [rbp+40h]
  __int128 v67; // [rsp+150h] [rbp+50h]
  __int128 v68; // [rsp+160h] [rbp+60h]
  _BYTE v69[32]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v70[7]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD *v71; // [rsp+1C8h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  if ( *(_DWORD *)(a3 + 24) != 1 )
  {
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v8 = (struct StateRepository::Cache::Manager_NoThrow *)(a1 + 440);
    v9 = StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(
           (struct StateRepository::Cache::Manager_NoThrow *)(a1 + 440),
           *(_QWORD *)(a3 + 16),
           (struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v43);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x405,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v9,
        (int)v38);
    v39 = 0;
    v10 = 0;
    v40 = 0;
    v11 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v43, 5, a3, &v39);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v11,
        (int)v38);
LABEL_10:
    v14 = v39;
    while ( v14 && !v10 )
    {
      if ( *(_DWORD *)(a3 + 24) == 1 )
      {
        v12 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(v8, a4, *(_QWORD *)a3, &v40);
        if ( v12 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x411,
            (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            (const char *)(unsigned int)v12,
            (int)v38);
        v10 = v40;
        if ( v40 )
          continue;
      }
      ++v44;
      v13 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v43, 5, a3, &v39);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x416,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v13,
          (int)v38);
      goto LABEL_10;
    }
    v15 = v43;
    v43 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
  }
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v16 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
          (StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *)&v46,
          (struct StateRepository::Cache::Manager_NoThrow *)(a1 + 440),
          *(_QWORD *)a3);
  v18 = v16;
  if ( v16 >= 0 )
    v18 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v16,
      (int)v38);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x41D,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      (const char *)(unsigned int)v18,
      (int)v38);
  *(_OWORD *)v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v40 = 0;
  v19 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v46, v17, v62, &v40);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x421,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      (const char *)(unsigned int)v19,
      (int)v38);
  while ( v40 )
  {
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v20 = L"windows.updateTask";
    if ( a2 != 2 )
      v20 = L"windows.preInstalledConfigTask";
    v21 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
            (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v43,
            (struct StateRepository::Cache::Manager_NoThrow *)(a1 + 440),
            v62[0],
            v20);
    v23 = v21;
    if ( v21 >= 0 )
      v23 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B9,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
        (const char *)(unsigned int)v21,
        (int)v38);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x426,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v23,
        (int)v38);
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v39 = 0;
    v24 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(&v43, v22, &v49, &v39);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x42A,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v24,
        (int)v38);
    while ( v39 )
    {
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
      LOBYTE(v41) = 0;
      v38 = &v41;
      v27 = StateRepository::Cache::Entity::Activation_NoThrow::Get(a1 + 440, v52, v26, &v56);
      if ( v27 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x431,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v27,
          (int)&v41);
      if ( !(_BYTE)v41 )
        MicrosoftTelemetryAssertTriggeredNoArgs(retaddr);
      v28 = operator new(0x48u);
      memset_0(v28, 0, 0x48u);
      std::wstring::wstring((__int64)v28 + 8);
      std::wstring::wstring((__int64)v28 + 40);
      v42 = (AppReadiness::TaskContext *)v28;
      v29 = std::wstring::wstring((__int64)v69, *(_QWORD *)(a3 + 8));
      std::wstring::operator=((char *)v42 + 8, v29);
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v69);
      v30 = std::wstring::wstring((__int64)v69, *((__int64 *)&v59 + 1));
      std::wstring::operator=((char *)v42 + 40, v30);
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v69);
      *(_DWORD *)v42 = a2;
      v70[0] = off_18007D630;
      v70[1] = &v42;
      v71 = v70;
      AppReadiness::User::ExecuteUnderContext(a1, (__int64)v70);
      if ( v71 )
      {
        v32 = v70;
        LOBYTE(v32) = v71 != v70;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v71 + 32LL))(v71, v32);
      }
      v42 = 0;
      ++v44;
      v33 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(&v43, v31, &v49, &v39);
      if ( v33 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x440,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v33,
          (int)&v41);
      v34 = v42;
      v42 = 0;
      if ( v34 )
      {
        AppReadiness::TaskContext::~TaskContext(v34);
        operator delete(v34, 0x48u);
      }
      StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v56);
    }
    ++v47;
    v35 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v46, v25, v62, &v40);
    if ( v35 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x443,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v35,
        (int)v38);
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v49);
    v36 = v43;
    v43 = 0;
    if ( v36 )
      SRCacheContext_Close(v36);
  }
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v62);
  v37 = v46;
  v46 = 0;
  if ( v37 )
    SRCacheContext_Close(v37);
}

```

## disassembly

```asm
0x18004da98  mov     [rsp-8+arg_8], rbx
0x18004da9d  push    rbp
0x18004da9e  push    rsi
0x18004da9f  push    rdi
0x18004daa0  push    r12
0x18004daa2  push    r13
0x18004daa4  push    r14
0x18004daa6  push    r15
0x18004daa8  lea     rbp, [rsp-0E0h]
0x18004dab0  sub     rsp, 1E0h
0x18004dab7  mov     rax, cs:__security_cookie
0x18004dabe  xor     rax, rsp
0x18004dac1  mov     [rbp+110h+var_40], rax
0x18004dac8  mov     r15, r9
0x18004dacb  mov     rdi, r8
0x18004dace  mov     r12d, edx
0x18004dad1  mov     r13, rcx
0x18004dad4  xor     r14d, r14d
0x18004dad7  cmp     dword ptr [r8+18h], 1
0x18004dadc  jz      loc_18004DBCB
0x18004dae2  mov     [rsp+210h+var_1D0], r14
0x18004dae7  mov     [rsp+210h+var_1C8], r14d
0x18004daec  mov     [rsp+210h+var_1C0], r14
0x18004daf1  lea     r14, [rcx+1B8h]
0x18004daf8  lea     r8, [rsp+210h+var_1D0]; struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *
0x18004dafd  mov     rdx, [rdi+10h]; __int64
0x18004db01  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18004db04  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x18004db09  mov     rcx, [rbp+118h]; this
0x18004db10  test    eax, eax
0x18004db12  js      loc_18004DFD5
0x18004db18  mov     [rsp+210h+var_1E0], 0
0x18004db1d  xor     bl, bl
0x18004db1f  mov     [rsp+210h+var_1DF], bl
0x18004db23  lea     r9, [rsp+210h+var_1E0]
0x18004db28  mov     r8, rdi
0x18004db2b  mov     edx, 5
0x18004db30  lea     rcx, [rsp+210h+var_1D0]
0x18004db35  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18004db3a  mov     rcx, [rbp+118h]; this
0x18004db41  test    eax, eax
0x18004db43  js      loc_18004DF96
0x18004db49  jmp     short loc_18004DBA9
0x18004db4b  test    bl, bl
0x18004db4d  jnz     short loc_18004DBB3
0x18004db4f  cmp     dword ptr [rdi+18h], 1
0x18004db53  jnz     short loc_18004DB7F
0x18004db55  lea     r9, [rsp+210h+var_1DF]; bool *
0x18004db5a  mov     r8, [rdi]; __int64
0x18004db5d  mov     rdx, r15; __int64
0x18004db60  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18004db63  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x18004db68  mov     rcx, [rbp+118h]; this
0x18004db6f  test    eax, eax
0x18004db71  js      loc_18004DFEA
0x18004db77  mov     bl, [rsp+210h+var_1DF]
0x18004db7b  test    bl, bl
0x18004db7d  jnz     short loc_18004DBAE
0x18004db7f  inc     [rsp+210h+var_1C8]
0x18004db83  lea     r9, [rsp+210h+var_1E0]
0x18004db88  mov     r8, rdi
0x18004db8b  mov     edx, 5
0x18004db90  lea     rcx, [rsp+210h+var_1D0]
0x18004db95  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18004db9a  mov     rcx, [rbp+118h]; this
0x18004dba1  test    eax, eax
0x18004dba3  js      loc_18004DFFF
0x18004dba9  mov     sil, [rsp+210h+var_1E0]
0x18004dbae  test    sil, sil
0x18004dbb1  jnz     short loc_18004DB4B
0x18004dbb3  mov     rcx, [rsp+210h+var_1D0]
0x18004dbb8  xor     r14d, r14d
0x18004dbbb  mov     [rsp+210h+var_1D0], r14
0x18004dbc0  test    rcx, rcx
0x18004dbc3  jz      short loc_18004DBCB
0x18004dbc5  call    cs:__imp_SRCacheContext_Close
0x18004dbcb  mov     [rsp+210h+var_1B8], r14
0x18004dbd0  mov     [rsp+210h+var_1B0], r14d
0x18004dbd5  mov     [rsp+210h+var_1A8], r14
0x18004dbda  lea     rsi, [r13+1B8h]
0x18004dbe1  mov     r8, [rdi]; __int64
0x18004dbe4  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18004dbe7  lea     rcx, [rsp+210h+var_1B8]; this
0x18004dbec  call    ?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)
0x18004dbf1  mov     ebx, eax
0x18004dbf3  test    eax, eax
0x18004dbf5  jns     short loc_18004DC14
0x18004dbf7  mov     rcx, [rbp+118h]; this
0x18004dbfe  mov     r9d, eax; char *
0x18004dc01  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004dc08  mov     edx, 47Bh; void *
0x18004dc0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dc12  jmp     short loc_18004DC17
0x18004dc14  mov     ebx, r14d
0x18004dc17  mov     rcx, [rbp+118h]; this
0x18004dc1e  test    ebx, ebx
0x18004dc20  js      loc_18004E014
0x18004dc26  xorps   xmm0, xmm0
0x18004dc29  movdqa  xmmword ptr [rbp+110h+var_100], xmm0
0x18004dc2e  mov     [rbp+110h+var_F0], 0
0x18004dc36  mov     [rbp+110h+var_E8], r14
0x18004dc3a  movdqa  [rbp+110h+var_E0], xmm0
0x18004dc3f  xorps   xmm1, xmm1
0x18004dc42  movdqa  [rbp+110h+var_D0], xmm1
0x18004dc47  movdqa  [rbp+110h+var_C0], xmm0
0x18004dc4c  movdqa  [rbp+110h+var_B0], xmm1
0x18004dc51  mov     [rsp+210h+var_1DF], r14b
0x18004dc56  lea     r9, [rsp+210h+var_1DF]
0x18004dc5b  lea     r8, [rbp+110h+var_100]
0x18004dc5f  lea     rcx, [rsp+210h+var_1B8]
0x18004dc64  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18004dc69  mov     rcx, [rbp+118h]; this
0x18004dc70  test    eax, eax
0x18004dc72  js      loc_18004E029
0x18004dc78  cmp     [rsp+210h+var_1DF], r14b
0x18004dc7d  jz      loc_18004DF38
0x18004dc83  mov     r15d, 48h ; 'H'
0x18004dc89  mov     [rsp+210h+var_1D0], r14
0x18004dc8e  mov     [rsp+210h+var_1C8], r14d
0x18004dc93  mov     [rsp+210h+var_1C0], r14
0x18004dc98  lea     rax, aWindowsPreinst_0; "windows.preInstalledConfigTask"
0x18004dc9f  lea     r9, aWindowsUpdatet_0; "windows.updateTask"
0x18004dca6  cmp     r12d, 2
0x18004dcaa  cmovnz  r9, rax; unsigned __int16 *
0x18004dcae  mov     r8, [rbp+110h+var_100]; __int64
0x18004dcb2  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18004dcb5  lea     rcx, [rsp+210h+var_1D0]; this
0x18004dcba  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x18004dcbf  mov     ebx, eax
0x18004dcc1  test    eax, eax
0x18004dcc3  jns     short loc_18004DCE2
0x18004dcc5  mov     rcx, [rbp+118h]; this
0x18004dccc  mov     r9d, eax; char *
0x18004dccf  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004dcd6  mov     edx, 3B9h; void *
0x18004dcdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dce0  jmp     short loc_18004DCE5
0x18004dce2  mov     ebx, r14d
0x18004dce5  mov     rcx, [rbp+118h]; this
0x18004dcec  test    ebx, ebx
0x18004dcee  js      loc_18004DFC0
0x18004dcf4  xorps   xmm0, xmm0
0x18004dcf7  movdqa  [rsp+210h+var_1A0], xmm0
0x18004dcfd  mov     [rbp+110h+var_190], 0
0x18004dd05  mov     [rbp+110h+var_188], r14
0x18004dd09  movdqa  [rbp+110h+var_180], xmm0
0x18004dd0e  xorps   xmm1, xmm1
0x18004dd11  movdqa  [rbp+110h+var_170], xmm1
0x18004dd16  mov     [rbp+110h+var_160], r14
0x18004dd1a  mov     [rbp+110h+var_158], r14d
0x18004dd1e  mov     [rsp+210h+var_1E0], r14b
0x18004dd23  lea     r9, [rsp+210h+var_1E0]
0x18004dd28  lea     r8, [rsp+210h+var_1A0]
0x18004dd2d  lea     rcx, [rsp+210h+var_1D0]
0x18004dd32  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x18004dd37  mov     rcx, [rbp+118h]; this
0x18004dd3e  test    eax, eax
0x18004dd40  js      loc_18004DFAB
0x18004dd46  jmp     loc_18004DEE0
0x18004dd4b  xorps   xmm0, xmm0
0x18004dd4e  movdqa  [rbp+110h+var_150], xmm0
0x18004dd53  mov     [rbp+110h+var_140], r14d
0x18004dd57  mov     [rbp+110h+var_138], r14
0x18004dd5b  movdqa  [rbp+110h+var_130], xmm0
0x18004dd60  xorps   xmm1, xmm1
0x18004dd63  movdqa  [rbp+110h+var_120], xmm1
0x18004dd68  mov     [rbp+110h+var_110], r14
0x18004dd6c  mov     byte ptr [rsp+210h+var_1DE], r14b
0x18004dd71  lea     rax, [rsp+210h+var_1DE]
0x18004dd76  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x18004dd7b  lea     r9, [rbp+110h+var_150]
0x18004dd7f  mov     rdx, qword ptr [rbp+110h+var_180]
0x18004dd83  mov     rcx, rsi
0x18004dd86  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18004dd8b  mov     rcx, [rbp+118h]; this
0x18004dd92  test    eax, eax
0x18004dd94  js      loc_18004E053
0x18004dd9a  cmp     byte ptr [rsp+210h+var_1DE], r14b
0x18004dd9f  jnz     short loc_18004DDA6
0x18004dda1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "activationFound")
0x18004dda6  mov     rcx, r15; Size
0x18004dda9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ddae  mov     rbx, rax
0x18004ddb1  mov     r8, r15; Size
0x18004ddb4  xor     edx, edx; Val
0x18004ddb6  mov     rcx, rax; void *
0x18004ddb9  call    memset_0
0x18004ddbe  lea     rcx, [rbx+8]
0x18004ddc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004ddc7  lea     rcx, [rbx+28h]
0x18004ddcb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004ddd0  mov     [rsp+210h+var_1D8], rbx
0x18004ddd5  mov     rdx, [rdi+8]
0x18004ddd9  lea     rcx, [rbp+110h+var_A0]
0x18004dddd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004dde2  mov     rcx, [rsp+210h+var_1D8]
0x18004dde7  add     rcx, 8
0x18004ddeb  mov     rdx, rax
0x18004ddee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004ddf3  lea     rcx, [rbp+110h+var_A0]
0x18004ddf7  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18004ddfc  mov     rdx, qword ptr [rbp+110h+var_130+8]
0x18004de00  lea     rcx, [rbp+110h+var_A0]
0x18004de04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004de09  mov     rcx, [rsp+210h+var_1D8]
0x18004de0e  add     rcx, 28h ; '('
0x18004de12  mov     rdx, rax
0x18004de15  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004de1a  lea     rcx, [rbp+110h+var_A0]
0x18004de1e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18004de23  mov     rax, [rsp+210h+var_1D8]
0x18004de28  mov     [rax], r12d
0x18004de2b  lea     rax, off_18007D630
0x18004de32  mov     [rbp+110h+var_80], rax
0x18004de39  lea     rax, [rsp+210h+var_1D8]
0x18004de3e  mov     [rbp+110h+var_78], rax
0x18004de45  lea     rax, [rbp+110h+var_80]
0x18004de4c  mov     [rbp+110h+var_48], rax
0x18004de53  lea     rdx, [rbp+110h+var_80]
0x18004de5a  mov     rcx, r13
0x18004de5d  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18004de62  nop
0x18004de63  mov     rcx, [rbp+110h+var_48]
0x18004de6a  test    rcx, rcx
0x18004de6d  jz      short loc_18004DE88
0x18004de6f  mov     rax, [rcx]
0x18004de72  lea     rdx, [rbp+110h+var_80]
0x18004de79  cmp     rcx, rdx
0x18004de7c  setnz   dl
0x18004de7f  mov     rax, [rax+20h]
0x18004de83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de88  mov     [rsp+210h+var_1D8], r14
0x18004de8d  inc     [rsp+210h+var_1C8]
0x18004de91  lea     r9, [rsp+210h+var_1E0]
0x18004de96  lea     r8, [rsp+210h+var_1A0]
0x18004de9b  lea     rcx, [rsp+210h+var_1D0]
0x18004dea0  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x18004dea5  mov     rcx, [rbp+118h]; this
0x18004deac  test    eax, eax
0x18004deae  js      loc_18004E03E
0x18004deb4  mov     rbx, [rsp+210h+var_1D8]
0x18004deb9  mov     [rsp+210h+var_1D8], r14
0x18004debe  test    rbx, rbx
0x18004dec1  jz      short loc_18004DED7
0x18004dec3  mov     rcx, rbx; this
0x18004dec6  call    ??1TaskContext@AppReadiness@@QEAA@XZ; AppReadiness::TaskContext::~TaskContext(void)
0x18004decb  mov     rdx, r15; unsigned __int64
0x18004dece  mov     rcx, rbx; void *
0x18004ded1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004ded6  nop
0x18004ded7  lea     rcx, [rbp+110h+var_150]; this
0x18004dedb  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18004dee0  cmp     [rsp+210h+var_1E0], r14b
0x18004dee5  jnz     loc_18004DD4B
0x18004deeb  inc     [rsp+210h+var_1B0]
0x18004deef  lea     r9, [rsp+210h+var_1DF]
0x18004def4  lea     r8, [rbp+110h+var_100]
0x18004def8  lea     rcx, [rsp+210h+var_1B8]
0x18004defd  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18004df02  mov     rcx, [rbp+118h]; this
0x18004df09  test    eax, eax
0x18004df0b  js      short loc_18004DF81
0x18004df0d  lea     rcx, [rsp+210h+var_1A0]; this
0x18004df12  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18004df17  nop
0x18004df18  mov     rcx, [rsp+210h+var_1D0]
0x18004df1d  mov     [rsp+210h+var_1D0], r14
0x18004df22  test    rcx, rcx
0x18004df25  jz      short loc_18004DF2D
0x18004df27  call    cs:__imp_SRCacheContext_Close
0x18004df2d  cmp     [rsp+210h+var_1DF], r14b
0x18004df32  jnz     loc_18004DC89
0x18004df38  lea     rcx, [rbp+110h+var_100]; this
0x18004df3c  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18004df41  nop
0x18004df42  mov     rcx, [rsp+210h+var_1B8]
0x18004df47  mov     [rsp+210h+var_1B8], r14
0x18004df4c  test    rcx, rcx
0x18004df4f  jz      short loc_18004DF57
0x18004df51  call    cs:__imp_SRCacheContext_Close
0x18004df57  mov     rcx, [rbp+110h+var_40]
0x18004df5e  xor     rcx, rsp; StackCookie
0x18004df61  call    __security_check_cookie
0x18004df66  mov     rbx, [rsp+210h+arg_8]
0x18004df6e  add     rsp, 1E0h
0x18004df75  pop     r15
0x18004df77  pop     r14
0x18004df79  pop     r13
0x18004df7b  pop     r12
0x18004df7d  pop     rdi
0x18004df7e  pop     rsi
0x18004df7f  pop     rbp
0x18004df80  retn
0x18004df81  mov     r9d, eax; char *
0x18004df84  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18004df8b  mov     edx, 443h; void *
0x18004df90  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004df96  mov     r9d, eax; char *
0x18004df99  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18004dfa0  mov     edx, 40Ch; void *
  ... truncated ...
```

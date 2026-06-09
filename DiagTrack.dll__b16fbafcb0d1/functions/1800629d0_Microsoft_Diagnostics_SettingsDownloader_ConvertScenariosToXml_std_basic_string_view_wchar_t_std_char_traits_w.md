# Microsoft::Diagnostics::SettingsDownloader::ConvertScenariosToXml(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,void *,ulong)

- ea: `0x1800629d0`
- end: `0x180064c20`
- name: `?ConvertScenariosToXml@SettingsDownloader@Diagnostics@Microsoft@@CAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAXK@Z`
- size: `8784`
- prototype: ``
- caller_count: `1`
- callee_count: `69`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180121fa0`

## callees

- `0x18001df2c`
- `0x18002110c`
- `0x180024e08`
- `0x18002afd8`
- `0x18002b318`
- `0x18002b7c0`
- `0x18002b95c`
- `0x18002be90`
- `0x18002cae0`
- `0x18002cb04`
- `0x18002df00`
- `0x18003119c`
- `0x180038010`
- `0x180038524`
- `0x180061180`
- `0x1800624ac`
- `0x18006266c`
- `0x1800626a8`
- `0x1800629d0`
- `0x180064c28`
- `0x180064e34`
- `0x180064e6c`
- `0x180064e8c`
- `0x180064eb0`
- `0x180064ee4`
- `0x180064f58`
- `0x18006509c`
- `0x18006a7a0`
- `0x180094c38`
- `0x180097b6c`
- `0x18009c7e4`
- `0x1800bc658`
- `0x1800d3790`
- `0x1800f7eb8`
- `0x18011bf68`
- `0x18019cf74`
- `0x18019ec8c`
- `0x18019ede0`
- `0x1801a0848`
- `0x1801a0af0`
- `0x1801a0b30`
- `0x1801a0c18`
- `0x1801a0c94`
- `0x1801a0d40`
- `0x1801a1010`
- `0x1801a1b34`
- `0x1801a1b7c`
- `0x1801a2510`
- `0x1801a2a98`
- `0x1801a3548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180062dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180062dd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063871`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006387c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063871`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006387c`
- `ntdll!NtSetInformationFile` at `0x180063825`
- `ntdll!NtSetInformationFile` at `0x180063866`
- `ntdll!NtSetInformationFile` at `0x180063825`
- `ntdll!NtSetInformationFile` at `0x180063866`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062afd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063b03`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062afd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063b03`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180062b94`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006375b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180064058`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006470a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180062b94`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006375b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180064058`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006470a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180062ba5`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006376c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180064101`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800647cf`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180062ba5`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006376c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180064101`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800647cf`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800638fd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800648b4`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800638fd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800648b4`
- `CRYPT32!CryptStringToBinaryA` at `0x180063666`
- `CRYPT32!CryptStringToBinaryA` at `0x180063666`

## string_xrefs

- `0x180062a81`: `.temp`
- `0x180062a90`: `.temp`
- `0x180063aa0`: `.temp`
- `0x180062b2c`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180062f2e`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180062ff7`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063782`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063998`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063b45`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063c4f`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063c7a`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063cbf`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063d07`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063d59`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063dae`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063ecf`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006406e`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064117`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800641e2`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800642c5`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006437b`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064496`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006457b`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006463f`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064720`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800647e5`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800648d9`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800649dd`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064a50`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064ac3`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064b40`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064bae`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180062c11`: `<?xml version="1.0" encoding="utf-8" ?><diagrules><scenarios>`
- `0x180063fc9`: `.json`
- `0x18006400b`: `.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall Microsoft::Diagnostics::SettingsDownloader::ConvertScenariosToXml(
        _QWORD *a1,
        void *a2,
        unsigned int a3)
{
  __int64 v3; // rsi
  int v5; // r14d
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rbx
  const WCHAR *v12; // rcx
  HANDLE FileW; // rax
  const char *v14; // r9
  unsigned int LastError; // ebx
  const char *v16; // r9
  __int64 result; // rax
  const char *v18; // r9
  const char *v19; // r9
  int v20; // eax
  unsigned int v21; // ebx
  _QWORD *v22; // r13
  unsigned int v23; // r15d
  int v24; // eax
  unsigned int v25; // ebx
  unsigned __int8 v26; // r12
  unsigned __int8 v27; // di
  DWORD v28; // esi
  unsigned int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // eax
  unsigned int v34; // ebx
  unsigned __int8 v35; // al
  unsigned __int64 v36; // rdx
  _QWORD *v37; // rcx
  unsigned __int64 v38; // rax
  _QWORD *v39; // rcx
  int v40; // ebx
  int v41; // edi
  __int64 v42; // r8
  unsigned __int64 v43; // rcx
  __int128 *v44; // rax
  unsigned __int8 *v45; // rax
  unsigned __int8 v46; // dl
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  struct Microsoft::Diagnostics::MemoryMappedStream *v51; // rdi
  struct Microsoft::Diagnostics::MemoryMappedStream *v52; // rbx
  __int64 v53; // r8
  unsigned int v54; // edi
  __int128 *v55; // rcx
  char *v56; // rdx
  __int64 v57; // rbx
  __int64 v58; // rdx
  __int64 v59; // r9
  __int64 v60; // rax
  unsigned __int8 *v61; // rbx
  _QWORD *v62; // rax
  __int64 v63; // r8
  __int64 v64; // rax
  unsigned __int8 v65; // dl
  __int64 v66; // r8
  _QWORD *v67; // rax
  __int64 v68; // r8
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // r9
  __int64 v74; // r8
  const char *v75; // r9
  int v76; // eax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  unsigned int v80; // ebx
  __int64 v81; // rax
  _QWORD *v82; // r12
  int v83; // eax
  __int64 v84; // rcx
  unsigned int v85; // ebx
  HANDLE v86; // rdi
  const char *v87; // r9
  const char *v88; // r9
  unsigned int v89; // ebx
  __int64 v90; // rcx
  const WCHAR *v91; // rdx
  const WCHAR *v92; // rcx
  BOOL v93; // ebx
  const char *v94; // r9
  __int64 v95; // rcx
  unsigned int v96; // ebx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rax
  const WCHAR *v100; // rcx
  HANDLE v101; // rax
  const char *v102; // r9
  __int64 v103; // rdi
  unsigned int v104; // ebx
  __int64 v105; // r9
  __int64 v106; // rax
  unsigned int v107; // ebx
  unsigned int v108; // ebx
  __int64 v109; // rbx
  _QWORD *v110; // rax
  __int64 last_of; // rax
  __int64 v112; // rax
  __int64 v113; // rax
  _QWORD *v114; // rcx
  __int64 v115; // rax
  const char *v116; // r9
  unsigned int v117; // ebx
  const char *v118; // r9
  unsigned int v119; // ebx
  int v120; // eax
  unsigned int v121; // ebx
  struct Microsoft::Diagnostics::MemoryMappedStream *v122; // rdi
  int v123; // eax
  unsigned int v124; // ebx
  __int64 v125; // rax
  __int128 *v126; // rdx
  int v127; // eax
  unsigned int v128; // ebx
  __int64 v129; // rsi
  int v130; // eax
  __int64 v131; // rcx
  unsigned int v132; // ebx
  HANDLE v133; // rdi
  const char *v134; // r9
  unsigned int v135; // ebx
  const char *v136; // r9
  unsigned int v137; // ebx
  const WCHAR *v138; // rcx
  BOOL v139; // ebx
  const char *v140; // r9
  unsigned int v141; // ebx
  unsigned int v142; // ebx
  unsigned int v143; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-508h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-508h]
  char v146[8]; // [rsp+40h] [rbp-4E8h] BYREF
  char v147[8]; // [rsp+48h] [rbp-4E0h] BYREF
  __int64 v148; // [rsp+50h] [rbp-4D8h] BYREF
  struct Microsoft::Diagnostics::MemoryMappedStream *v149; // [rsp+58h] [rbp-4D0h] BYREF
  unsigned int v150; // [rsp+60h] [rbp-4C8h] BYREF
  _QWORD *v151; // [rsp+68h] [rbp-4C0h] BYREF
  char v152[8]; // [rsp+70h] [rbp-4B8h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp-4B0h] BYREF
  DWORD pcbBinary[2]; // [rsp+80h] [rbp-4A8h] BYREF
  unsigned int v155; // [rsp+88h] [rbp-4A0h]
  struct Microsoft::Diagnostics::MemoryMappedStream *v156; // [rsp+90h] [rbp-498h] BYREF
  char v157[8]; // [rsp+98h] [rbp-490h] BYREF
  __int64 v158; // [rsp+A0h] [rbp-488h] BYREF
  int v159; // [rsp+A8h] [rbp-480h] BYREF
  int v160; // [rsp+ACh] [rbp-47Ch]
  int v161; // [rsp+B0h] [rbp-478h]
  _BYTE *v162; // [rsp+B8h] [rbp-470h]
  struct Microsoft::Diagnostics::MemoryMappedStream *v163; // [rsp+C0h] [rbp-468h] BYREF
  _QWORD *v164; // [rsp+C8h] [rbp-460h]
  _BYTE *v165; // [rsp+D0h] [rbp-458h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-448h] BYREF
  _IO_STATUS_BLOCK *p_IoStatusBlock; // [rsp+F0h] [rbp-438h]
  char v168[8]; // [rsp+F8h] [rbp-430h] BYREF
  char v169[8]; // [rsp+100h] [rbp-428h] BYREF
  HANDLE v170; // [rsp+108h] [rbp-420h]
  __int128 v171; // [rsp+110h] [rbp-418h] BYREF
  __int64 v172; // [rsp+120h] [rbp-408h]
  __int64 v173; // [rsp+128h] [rbp-400h]
  char v174[8]; // [rsp+130h] [rbp-3F8h] BYREF
  __int64 v175; // [rsp+138h] [rbp-3F0h]
  _QWORD v176[2]; // [rsp+150h] [rbp-3D8h] BYREF
  _BYTE v177[56]; // [rsp+170h] [rbp-3B8h] BYREF
  __int64 (__fastcall ***v178)(_QWORD, _BYTE *); // [rsp+1A8h] [rbp-380h]
  _BYTE v179[56]; // [rsp+1B0h] [rbp-378h] BYREF
  _BYTE v180[56]; // [rsp+1E8h] [rbp-340h] BYREF
  _BYTE v181[56]; // [rsp+220h] [rbp-308h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+258h] [rbp-2D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+290h] [rbp-298h] BYREF
  __int128 v184; // [rsp+2A0h] [rbp-288h]
  _QWORD v185[2]; // [rsp+2B0h] [rbp-278h] BYREF
  unsigned __int64 v186; // [rsp+2C0h] [rbp-268h]
  unsigned __int64 v187; // [rsp+2C8h] [rbp-260h]
  __int128 v188; // [rsp+2D0h] [rbp-258h] BYREF
  unsigned __int64 v189; // [rsp+2E0h] [rbp-248h]
  unsigned __int64 v190; // [rsp+2E8h] [rbp-240h]
  LPCWSTR lpExistingFileName[3]; // [rsp+2F0h] [rbp-238h] BYREF
  unsigned __int64 v192; // [rsp+308h] [rbp-220h]
  _QWORD v193[4]; // [rsp+310h] [rbp-218h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+330h] [rbp-1F8h] BYREF
  __int128 v195; // [rsp+340h] [rbp-1E8h]
  _QWORD v196[8]; // [rsp+350h] [rbp-1D8h] BYREF
  _QWORD v197[2]; // [rsp+390h] [rbp-198h] BYREF
  _BYTE Src[56]; // [rsp+3B0h] [rbp-178h] BYREF
  __int64 v199; // [rsp+3E8h] [rbp-140h]
  _BYTE v200[64]; // [rsp+3F0h] [rbp-138h] BYREF
  int v201; // [rsp+430h] [rbp-F8h]
  _BYTE v202[168]; // [rsp+438h] [rbp-F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  v3 = a3;
  v155 = a3;
  v164 = a1;
  v5 = 0;
  LODWORD(v162) = 0;
  v160 = 0;
  v149 = 0;
  v156 = 0;
  try
  {
    v6 = Microsoft::Diagnostics::MemoryMappedStream::Create(&v156, a2, 2u);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)(unsigned int)v6,
        dwCreationDisposition);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      return v7;
    }
    v149 = v156;
    *(_OWORD *)lpFileName = 0;
    v184 = 0;
    std::wstring::_Construct<1,wchar_t *>(lpFileName, *a1, a1[1]);
    std::_WChar_traits<wchar_t>::length(L".temp", v8, v9, v10);
    std::wstring::_Append<wchar_t>(lpFileName);
    v152[0] = 0;
    v170 = (HANDLE)-1LL;
    v11 = -1;
    hFile = (HANDLE)-1LL;
    v12 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v184 + 1) > 7u )
      v12 = lpFileName[0];
    FileW = CreateFileW(v12, 0xC0010000, 1u, 0, 2u, 0x100u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        FileW);
      v11 = (__int64)hFile;
    }
    if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2E3,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                    v14);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      return LastError;
    }
    if ( !SetFilePointerEx((HANDLE)v11, (LARGE_INTEGER)(v3 + 87), 0, 0) )
    {
      v107 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2EC,
               (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
               v18);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      return v107;
    }
    if ( !SetEndOfFile((HANDLE)v11) )
    {
      v108 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2ED,
               (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
               v19);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      return v108;
    }
    v151 = 0;
    *(_QWORD *)pcbBinary = 0;
    v20 = Microsoft::Diagnostics::MemoryMappedStream::Create(
            (struct Microsoft::Diagnostics::MemoryMappedStream **)pcbBinary,
            (void *)v11,
            4u);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)(unsigned int)v20,
        dwCreationDispositiona);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      return v21;
    }
    v22 = *(_QWORD **)pcbBinary;
    v151 = *(_QWORD **)pcbBinary;
    v146[0] = 0;
    v159 = 0;
    v150 = 0;
    v23 = 61;
    v24 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, unsigned int *))(**(_QWORD **)pcbBinary + 32LL))(
            *(_QWORD *)pcbBinary,
            "<?xml version=\"1.0\" encoding=\"utf-8\" ?><diagrules><scenarios>",
            61,
            &v150);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x300,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)(unsigned int)v24,
        dwCreationDispositiona);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      return v25;
    }
    if ( v150 != 61 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x301,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)0x8007000DLL,
        dwCreationDispositiona);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      return 2147942413LL;
    }
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 61;
    v161 = 61;
    std::wstring::wstring(v185);
    LODWORD(v163) = 0;
    v147[0] = 0;
    nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v148,
      0);
    while ( !(*(unsigned int (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, char *, __int64, int *))(*(_QWORD *)v156 + 24LL))(
               v156,
               v146,
               1,
               &v159) )
    {
      v5 += v159;
      if ( v26 < 2u )
      {
        if ( v146[0] == 123 )
          ++v26;
      }
      else if ( v27 == 2 )
      {
        v35 = v146[0];
        if ( v146[0] != 123 )
          goto LABEL_26;
        v38 = std::_WChar_traits<wchar_t>::length(L"UtcSetting:", v30, v31, v32);
        v39 = v185;
        if ( v187 > 7 )
          v39 = (_QWORD *)v185[0];
        if ( v186 >= v38 )
        {
          if ( (unsigned int)_o__wcsnicmp(v39, L"UtcSetting:", v38) )
            goto LABEL_25;
          v40 = 1;
          v41 = 0;
          v188 = 0;
          v189 = 0;
          v190 = 0;
          std::string::_Construct<1,char const *>(&v188, "{", 1);
          do
          {
            if ( (*(unsigned int (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, char *, __int64, int *))(*(_QWORD *)v156 + 24LL))(
                   v156,
                   v146,
                   1,
                   &v159) )
            {
              break;
            }
            v43 = v189;
            if ( v189 >= v190 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(
                &v188,
                v190,
                v42,
                (unsigned __int8)v146[0]);
            }
            else
            {
              ++v189;
              v44 = &v188;
              if ( v190 > 0xF )
                v44 = (__int128 *)v188;
              *((_BYTE *)v44 + v43) = v146[0];
              *((_BYTE *)v44 + v43 + 1) = 0;
            }
            LODWORD(v163) = (_DWORD)v163 + 1;
            ++v5;
            if ( v146[0] == 123 )
            {
              ++v40;
            }
            else if ( v146[0] == 125 )
            {
              ++v41;
            }
          }
          while ( v40 != v41 );
          if ( nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::size(v147) )
          {
            v178 = 0;
            v165 = v177;
            v168[0] = 0;
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
              v169,
              0);
            v54 = (unsigned int)v162 | 1;
            v160 = (unsigned int)v162 | 1;
            v162 = Src;
            v199 = 0;
            if ( v178 )
              v199 = (**v178)(v178, Src);
            v162 = Src;
            if ( v190 <= 0xF )
            {
              v56 = (char *)&v188 + v189;
              v55 = &v188;
            }
            else
            {
              v55 = (__int128 *)v188;
              v56 = (char *)(v188 + v189);
            }
            v193[0] = v55;
            v193[1] = v56;
            v57 = std::function<void (unsigned long)>::function<void (unsigned long)>(v196, Src);
            p_IoStatusBlock = (_IO_STATUS_BLOCK *)v57;
            std::function<bool (int,enum nlohmann::json_abi_v3_11_2::detail::parse_event_t,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> &)>::function<bool (int,enum nlohmann::json_abi_v3_11_2::detail::parse_event_t,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> &)>(
              v200,
              v57);
            v201 = 0;
            nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>(
              v202,
              v193);
            v202[152] = 1;
            v201 = nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v202);
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(v57);
            LODWORD(v162) = v54 | 2;
            v160 = v54 | 2;
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(Src);
            nlohmann::json_abi_v3_11_2::detail::parser<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::parse(
              v200,
              v58,
              v168);
            nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::~lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>(v202);
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(v200);
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(v177);
            nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
              lpNewFileName,
              v168);
            nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_begin(lpNewFileName);
            while ( 1 )
            {
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                v196,
                v168);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v196);
              if ( (unsigned __int8)nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator==<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>,0>(
                                      lpNewFileName,
                                      v196) )
                break;
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::key(lpNewFileName);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                v174,
                v147);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v174);
              if ( v147[0] == 1 )
                v175 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>>,0>>::find(
                                    v148,
                                    v157,
                                    v59);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                v196,
                v147);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v196);
              if ( (unsigned __int8)nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator==<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>,0>(
                                      v174,
                                      v196) )
              {
                p_IoStatusBlock = &IoStatusBlock;
                v60 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator*(lpNewFileName);
                v61 = (unsigned __int8 *)nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>(
                                           &IoStatusBlock,
                                           v60);
                v62 = (_QWORD *)nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::key(lpNewFileName);
                v171 = 0;
                v172 = 0;
                v173 = 0;
                v63 = v62[2];
                if ( v62[3] > 0xFu )
                  v62 = (_QWORD *)*v62;
                std::string::_Construct<2,char const *>(&v171, v62, v63);
                v64 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::operator[](
                        v147,
                        &v171);
                v65 = *(_BYTE *)v64;
                *(_BYTE *)v64 = *v61;
                *v61 = v65;
                v66 = *(_QWORD *)(v64 + 8);
                *(_QWORD *)(v64 + 8) = *((_QWORD *)v61 + 1);
                *((_QWORD *)v61 + 1) = v66;
                nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
                  v61 + 8,
                  *v61);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator++(lpNewFileName);
              }
              else
              {
                v67 = (_QWORD *)nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::key(lpNewFileName);
                v171 = 0;
                v172 = 0;
                v173 = 0;
                v68 = v67[2];
                if ( v67[3] > 0xFu )
                  v67 = (_QWORD *)*v67;
                std::string::_Construct<2,char const *>(&v171, v67, v68);
                v69 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::operator[](
                        v147,
                        &v171);
                v70 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator->(lpNewFileName);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  v176,
                  v70);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v176);
                v71 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator->(lpNewFileName);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  v197,
                  v71);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_begin(v197);
                v72 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator->(v174);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  v196,
                  v72);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v196);
                if ( *(_BYTE *)v69 != 2 )
                {
                  v164 = (_QWORD *)nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::type_name(v69);
                  nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[26],char const *>(Src);
                  nlohmann::json_abi_v3_11_2::detail::type_error::create<std::nullptr_t,0>(
                    (nlohmann::json_abi_v3_11_2::detail::type_error *)pExceptionObject,
                    309);
                  throw (nlohmann::json_abi_v3_11_2::detail::type_error *)pExceptionObject;
                }
                if ( v196[0] != v69 )
                {
                  std::string::string(v196, "iterator does not fit current value");
                  nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,0>(
                    (nlohmann::json_abi_v3_11_2::detail::exception *)v179,
                    202);
                  throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)v179;
                }
                if ( v197[0] != v176[0] )
                {
                  std::string::string(v196, "iterators do not fit");
                  nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,0>(
                    (nlohmann::json_abi_v3_11_2::detail::exception *)v180,
                    210);
                  throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)v180;
                }
                if ( v197[0] == v69 )
                {
                  std::string::string(v196, "passed iterators may not belong to container");
                  nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,0>(
                    (nlohmann::json_abi_v3_11_2::detail::exception *)v181,
                    211);
                  throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)v181;
                }
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  Src,
                  v69);
                std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::_Insert_counted_range<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>(
                  *(_QWORD *)(v69 + 8),
                  v196[2],
                  v74,
                  (v73 - v74) >> 4);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator++(lpNewFileName);
              }
            }
            LODWORD(v162) = (unsigned int)v162 & 0xFFFFFFFE;
            v160 = (int)v162;
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
              v169,
              (unsigned __int8)v168[0]);
          }
          else
          {
            v178 = 0;
            v45 = (unsigned __int8 *)nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::parse<std::string &>(
                                       lpExistingFileName,
                                       &v188,
                                       v177);
            v46 = v147[0];
            v147[0] = *v45;
            *v45 = v46;
            v47 = v148;
            v148 = *((_QWORD *)v45 + 1);
            *((_QWORD *)v45 + 1) = v47;
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
              v45 + 8,
              *v45);
          }
          v27 = 0;
          v53 = std::_WChar_traits<wchar_t>::length(&::Src, v48, v49, v50);
          std::wstring::_Assign<wchar_t>(v185, &::Src, v53);
          std::string::_Tidy_deallocate(&v188);
          v29 = v161;
        }
      }
      else if ( v27 < 3u )
      {
LABEL_25:
        v35 = v146[0];
LABEL_26:
        if ( v35 == 34 )
        {
          ++v27;
        }
        else if ( v27 == 1 )
        {
          v36 = v186;
          v37 = v185;
          if ( v186 >= v187 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(
              v185,
              v186,
              v187,
              (unsigned int)(char)v35);
          }
          else
          {
            ++v186;
            if ( v187 > 7 )
              v37 = (_QWORD *)v185[0];
            *(_DWORD *)((char *)v37 + 2 * v36) = (unsigned __int16)(char)v35;
          }
        }
      }
      else if ( v146[0] == 34 )
      {
        pcbBinary[0] = v28;
        if ( !CryptStringToBinaryA((LPCSTR)(v22[1] + v29), v28, 1u, (BYTE *)(v22[1] + v29), pcbBinary, 0, 0) )
        {
          v96 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x38D,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                  v75);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v148,
            (unsigned __int8)v147[0]);
          std::wstring::_Tidy_deallocate(v185);
          if ( v22 )
            std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v97, v22);
          AutoDeleteFile::Close((AutoDeleteFile *)v152);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          std::wstring::_Tidy_deallocate(lpFileName);
          if ( v156 )
            std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v98, v156);
          return v96;
        }
        v23 += pcbBinary[0] - v28;
        v76 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(*v22 + 40LL))(v22, v23, 0, 0);
        v80 = v76;
        if ( v76 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x394,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
            (const char *)(unsigned int)v76,
            dwCreationDispositiona);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v148,
            (unsigned __int8)v147[0]);
          std::wstring::_Tidy_deallocate(v185);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
          AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
          std::wstring::_Tidy_deallocate(lpFileName);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
          return v80;
        }
        v29 = v23;
        v161 = v23;
        v27 = 0;
        v28 = 0;
        v81 = std::_WChar_traits<wchar_t>::length(&::Src, v77, v78, v79);
        std::wstring::_Assign<wchar_t>(v185, &::Src, v81);
      }
      else
      {
        v33 = (*(__int64 (__fastcall **)(_QWORD *, char *, __int64, unsigned int *))(*v22 + 32LL))(v22, v146, 1, &v150);
        v34 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x378,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
            (const char *)(unsigned int)v33,
            dwCreationDispositiona);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v148,
            (unsigned __int8)v147[0]);
          std::wstring::_Tidy_deallocate(v185);
          if ( v22 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v22 + 1);
            operator delete(v22, (const struct std::nothrow_t *)0x20);
          }
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && !v152[0] )
          {
            IoStatusBlock = 0;
            NtSetInformationFile(
              hFile,
              &IoStatusBlock,
              `AutoDeleteFile::MarkFileForDelete'::`2'::disposition,
              1u,
              FileDispositionInformation);
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            -1);
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hFile);
          std::wstring::_Tidy_deallocate(lpFileName);
          v51 = v156;
          if ( v156 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)v156 + 8);
            operator delete(v51, (const struct std::nothrow_t *)0x20);
          }
          return v34;
        }
        if ( v150 != 1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x379,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
            (const char *)0x8007000DLL,
            dwCreationDispositiona);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v148,
            (unsigned __int8)v147[0]);
          std::wstring::_Tidy_deallocate(v185);
          if ( v22 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v22 + 1);
            operator delete(v22, (const struct std::nothrow_t *)0x20);
          }
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && !v152[0] )
          {
            IoStatusBlock = 0;
            NtSetInformationFile(
              hFile,
              &IoStatusBlock,
              `AutoDeleteFile::MarkFileForDelete'::`2'::disposition,
              1u,
              FileDispositionInformation);
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            -1);
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hFile);
          std::wstring::_Tidy_deallocate(lpFileName);
          v52 = v156;
          if ( v156 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)v156 + 8);
            operator delete(v52, (const struct std::nothrow_t *)0x20);
          }
          return 2147942413LL;
        }
        ++v23;
        ++v28;
        v29 = v161;
      }
    }
    v82 = v164;
    if ( (_DWORD)v163 )
    {
      v103 = -1;
      v109 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(*v164, v164[1], -1, 92);
      std::wstring::wstring(v193, v82);
      if ( v109 != -1 )
      {
        v110 = (_QWORD *)std::wstring_view::substr(v82, &IoStatusBlock, v109, -1);
        std::wstring::_Assign<wchar_t>(v193, *v110, v110[1]);
      }
      last_of = std::wstring::find_last_of(v193, 46);
      if ( last_of == -1 )
      {
        v115 = std::operator+<wchar_t>(v196, v193, L".json");
        std::wstring::operator=(v193, v115);
        v114 = v196;
      }
      else
      {
        v112 = std::wstring::substr(v193, v197, 0, last_of);
        v113 = std::operator+<wchar_t>(v196, v112, L".json");
        std::wstring::operator=(v193, v113);
        std::wstring::_Tidy_deallocate(v196);
        v114 = v197;
      }
      std::wstring::_Tidy_deallocate(v114);
      std::wstring::wstring(v196, L"\\");
      IoStatusBlock = *(_IO_STATUS_BLOCK *)&off_1803857F0;
      v99 = Microsoft::Diagnostics::operator+(v197);
      std::operator+<wchar_t>(lpExistingFileName, v99, v193);
      std::wstring::_Tidy_deallocate(v197);
      std::wstring::_Tidy_deallocate(v196);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpExistingFileName);
      std::wstring::append(lpExistingFileName, L".temp");
      v157[0] = 0;
      v158 = -1;
      v100 = (const WCHAR *)lpExistingFileName;
      if ( v192 > 7 )
        v100 = lpExistingFileName[0];
      v101 = CreateFileW(v100, 0xC0010000, 1u, 0, 2u, 0x100u, 0);
      if ( v101 != (HANDLE)-1LL )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v158,
          v101);
        v103 = v158;
        v170 = (HANDLE)v158;
      }
      if ( (unsigned __int64)(v103 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v104 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3C2,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v102);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v104;
      }
      if ( !SetFilePointerEx((HANDLE)v103, (LARGE_INTEGER)(v155 + 62LL), 0, 0) )
      {
        v117 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3C5,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v116);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v117;
      }
      if ( !SetEndOfFile((HANDLE)v103) )
      {
        v119 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3C6,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v118);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v119;
      }
      *(_QWORD *)pcbBinary = 0;
      v163 = 0;
      v120 = Microsoft::Diagnostics::MemoryMappedStream::Create(&v163, (void *)v103, 4u);
      v121 = v120;
      if ( v120 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3CA,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v120,
          dwCreationDispositiona);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v121;
      }
      v122 = v163;
      *(_QWORD *)pcbBinary = v163;
      v123 = (*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, const char *, __int64, unsigned int *))(*(_QWORD *)v163 + 32LL))(
               v163,
               "{ \"refreshInterval\": null, \"queryUrl\" : null, \"settings\" : ",
               59,
               &v150);
      v124 = v123;
      if ( v123 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3CF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v123,
          dwCreationDispositiona);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v124;
      }
      if ( v150 != 59 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D0,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)0x8007000DLL,
          dwCreationDispositiona);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return 2147942413LL;
      }
      v125 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::dump(
               v147,
               v196);
      std::string::string(&v188, v125);
      std::string::_Tidy_deallocate(v196);
      v126 = &v188;
      if ( v190 > 0xF )
        v126 = (__int128 *)v188;
      v127 = (*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, __int128 *, _QWORD, unsigned int *))(*(_QWORD *)v122 + 32LL))(
               v122,
               v126,
               (unsigned int)v189,
               &v150);
      v128 = v127;
      if ( v127 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D5,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v127,
          dwCreationDispositiona);
        std::string::_Tidy_deallocate(&v188);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v128;
      }
      v129 = v150;
      v130 = (*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, const char *, __int64, unsigned int *))(*(_QWORD *)v122 + 32LL))(
               v122,
               "}",
               1,
               &v150);
      v132 = v130;
      if ( v130 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v130,
          dwCreationDispositiona);
        std::string::_Tidy_deallocate(&v188);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v132;
      }
      if ( v150 != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)0x8007000DLL,
          dwCreationDispositiona);
        std::string::_Tidy_deallocate(&v188);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return 2147942413LL;
      }
      *(_QWORD *)pcbBinary = 0;
      if ( v122 )
        std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v131, v122);
      v133 = v170;
      if ( !SetFilePointerEx(v170, (LARGE_INTEGER)(v129 + 60), 0, 0) )
      {
        v135 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3DD,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v134);
        std::string::_Tidy_deallocate(&v188);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v135;
      }
      if ( !SetEndOfFile(v133) )
      {
        v137 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3DE,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v136);
        std::string::_Tidy_deallocate(&v188);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v137;
      }
      v157[0] = 1;
      AutoDeleteFile::Close((AutoDeleteFile *)v157);
      v105 = std::wstring::find_last_of(lpExistingFileName, 46);
      v106 = std::wstring::substr(lpExistingFileName, v197, 0, v105);
      if ( *(_QWORD *)(v106 + 24) > 7u )
        v106 = *(_QWORD *)v106;
      v138 = (const WCHAR *)lpExistingFileName;
      if ( v192 > 7 )
        v138 = lpExistingFileName[0];
      v139 = MoveFileExW(v138, (LPCWSTR)v106, 1u);
      std::wstring::_Tidy_deallocate(v197);
      if ( !v139 )
      {
        v141 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3E3,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v140);
        std::string::_Tidy_deallocate(&v188);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v193);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        return v141;
      }
      std::string::_Tidy_deallocate(&v188);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v157);
      std::wstring::_Tidy_deallocate(lpExistingFileName);
      std::wstring::_Tidy_deallocate(v193);
    }
    if ( v5 == v155 )
    {
      v83 = (*(__int64 (__fastcall **)(_QWORD *, const char *, __int64, unsigned int *))(*v22 + 32LL))(
              v22,
              "</scenarios></diagrules>",
              24,
              &v150);
      v85 = v83;
      if ( v83 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EA,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v83,
          dwCreationDispositiona);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        result = v85;
      }
      else if ( v150 == 24 )
      {
        v151 = 0;
        if ( v22 )
          std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v84, v22);
        v86 = hFile;
        if ( SetFilePointerEx(hFile, (LARGE_INTEGER)(v23 + 24), 0, 0) )
        {
          if ( SetEndOfFile(v86) )
          {
            v152[0] = 1;
            AutoDeleteFile::Close((AutoDeleteFile *)v152);
            *(_OWORD *)lpNewFileName = 0;
            v195 = 0;
            std::wstring::_Construct<1,wchar_t *>(lpNewFileName, *v82, v82[1]);
            v91 = (const WCHAR *)lpNewFileName;
            if ( *((_QWORD *)&v195 + 1) > 7u )
              v91 = lpNewFileName[0];
            v92 = (const WCHAR *)lpFileName;
            if ( *((_QWORD *)&v184 + 1) > 7u )
              v92 = lpFileName[0];
            v93 = MoveFileExW(v92, v91, 1u);
            std::wstring::_Tidy_deallocate(lpNewFileName);
            if ( v93 )
            {
              nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
                &v148,
                (unsigned __int8)v147[0]);
              std::wstring::_Tidy_deallocate(v185);
              AutoDeleteFile::Close((AutoDeleteFile *)v152);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
              std::wstring::_Tidy_deallocate(lpFileName);
              if ( v156 )
                std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v95, v156);
              result = 0;
            }
            else
            {
              v143 = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x3F7,
                       (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                       v94);
              nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
                &v148,
                (unsigned __int8)v147[0]);
              std::wstring::_Tidy_deallocate(v185);
              std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
              AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
              result = v143;
            }
          }
          else
          {
            v89 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3F2,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                    v88);
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
              &v148,
              (unsigned __int8)v147[0]);
            std::wstring::_Tidy_deallocate(v185);
            AutoDeleteFile::Close((AutoDeleteFile *)v152);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            std::wstring::_Tidy_deallocate(lpFileName);
            if ( v156 )
              std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v90, v156);
            result = v89;
          }
        }
        else
        {
          v142 = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x3F1,
                   (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                   v87);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v148,
            (unsigned __int8)v147[0]);
          std::wstring::_Tidy_deallocate(v185);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
          AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
          std::wstring::_Tidy_deallocate(lpFileName);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
          result = v142;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EB,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)0x8007000DLL,
          dwCreationDispositiona);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v148,
          (unsigned __int8)v147[0]);
        std::wstring::_Tidy_deallocate(v185);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
        result = 2147942413LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E7,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)0x8007000DLL,
        dwCreationDispositiona);
      nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        &v148,
        (unsigned __int8)v147[0]);
      std::wstring::_Tidy_deallocate(v185);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v151);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v152);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v149);
      result = 2147942413LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3FB,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800629d0  push    rbx
0x1800629d2  push    rsi
0x1800629d3  push    rdi
0x1800629d4  push    r12
0x1800629d6  push    r13
0x1800629d8  push    r14
0x1800629da  push    r15
0x1800629dc  sub     rsp, 4F0h
0x1800629e3  mov     rax, cs:__security_cookie
0x1800629ea  xor     rax, rsp
0x1800629ed  mov     [rsp+528h+var_48], rax
0x1800629f5  mov     esi, r8d
0x1800629f8  mov     [rsp+528h+var_4A0], esi
0x1800629ff  mov     rdi, rcx
0x180062a02  mov     [rsp+528h+var_460], rcx
0x180062a0a  xor     r14d, r14d
0x180062a0d  mov     eax, r14d
0x180062a10  mov     dword ptr [rsp+528h+var_470], eax
0x180062a17  mov     [rsp+528h+var_47C], eax
0x180062a1e  mov     [rsp+528h+var_4D0], r14
0x180062a23  mov     [rsp+528h+var_498], r14
0x180062a2b  mov     r8d, 2; unsigned int
0x180062a31  lea     rcx, [rsp+528h+var_498]; struct Microsoft::Diagnostics::MemoryMappedStream **
0x180062a39  call    ?Create@MemoryMappedStream@Diagnostics@Microsoft@@SAJPEAPEAV123@PEAXK@Z; Microsoft::Diagnostics::MemoryMappedStream::Create(Microsoft::Diagnostics::MemoryMappedStream * *,void *,ulong)
0x180062a3e  mov     ebx, eax
0x180062a40  test    eax, eax
0x180062a42  js      loc_180063C44
0x180062a48  mov     rdx, [rsp+528h+var_498]
0x180062a50  mov     [rsp+528h+var_4D0], rdx
0x180062a55  xorps   xmm0, xmm0
0x180062a58  movups  xmmword ptr [rsp+528h+lpFileName], xmm0
0x180062a60  xorps   xmm1, xmm1
0x180062a63  movdqu  [rsp+528h+var_288], xmm1
0x180062a6c  mov     r8, [rdi+8]
0x180062a70  mov     rdx, [rdi]
0x180062a73  lea     rcx, [rsp+528h+lpFileName]
0x180062a7b  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180062a80  nop
0x180062a81  lea     rcx, aTemp; ".temp"
0x180062a88  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180062a8d  mov     r8, rax
0x180062a90  lea     rdx, aTemp; ".temp"
0x180062a97  lea     rcx, [rsp+528h+lpFileName]; Src
0x180062a9f  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180062aa4  mov     [rsp+528h+var_4B8], r14b
0x180062aa9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180062ab0  mov     [rsp+528h+var_420], rax
0x180062ab8  mov     rbx, rax
0x180062abb  mov     [rsp+528h+hFile], rax
0x180062ac0  lea     rcx, [rsp+528h+lpFileName]
0x180062ac8  cmp     qword ptr [rsp+528h+var_288+8], 7
0x180062ad1  cmova   rcx, [rsp+528h+lpFileName]; lpFileName
0x180062ada  mov     [rsp+528h+hTemplateFile], r14; hTemplateFile
0x180062adf  mov     [rsp+528h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x180062ae7  mov     [rsp+528h+dwCreationDisposition], 2; int
0x180062aef  xor     r9d, r9d; lpSecurityAttributes
0x180062af2  mov     edx, 0C0010000h; dwDesiredAccess
0x180062af7  mov     r8d, 1; dwShareMode
0x180062afd  call    cs:__imp_CreateFileW
0x180062b03  cmp     rax, rbx
0x180062b06  jz      short loc_180062B1A
0x180062b08  mov     rdx, rax
0x180062b0b  lea     rcx, [rsp+528h+hFile]
0x180062b10  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180062b15  mov     rbx, [rsp+528h+hFile]
0x180062b1a  lea     rax, [rbx-1]
0x180062b1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180062b22  jbe     short loc_180062B87
0x180062b24  mov     rcx, [rsp+528h]; this
0x180062b2c  lea     r8, aOnecoreBaseTel_259; "onecore\\base\\telemetry\\utc\\service"...
0x180062b33  mov     edx, 2E3h; void *
0x180062b38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180062b3d  mov     ebx, eax
0x180062b3f  lea     rcx, [rsp+528h+var_4B8]; this
0x180062b44  call    ??1AutoDeleteFile@@QEAA@XZ; AutoDeleteFile::~AutoDeleteFile(void)
0x180062b49  nop
0x180062b4a  lea     rcx, [rsp+528h+lpFileName]
0x180062b52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062b57  nop
0x180062b58  lea     rcx, [rsp+528h+var_4D0]
0x180062b5d  call    ??1?$unique_ptr@VMemoryMappedStream@Diagnostics@Microsoft@@U?$default_delete@VMemoryMappedStream@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(void)
0x180062b62  mov     eax, ebx
0x180062b64  mov     rcx, [rsp+528h+var_48]
0x180062b6c  xor     rcx, rsp; StackCookie
0x180062b6f  call    __security_check_cookie
0x180062b74  add     rsp, 4F0h
0x180062b7b  pop     r15
0x180062b7d  pop     r14
0x180062b7f  pop     r13
0x180062b81  pop     r12
0x180062b83  pop     rdi
0x180062b84  pop     rsi
0x180062b85  pop     rbx
0x180062b86  retn
0x180062b87  lea     rdx, [rsi+57h]; liDistanceToMove
0x180062b8b  xor     r9d, r9d; dwMoveMethod
0x180062b8e  xor     r8d, r8d; lpNewFilePointer
0x180062b91  mov     rcx, rbx; hFile
0x180062b94  call    cs:__imp_SetFilePointerEx
0x180062b9a  test    eax, eax
0x180062b9c  jz      loc_180063C72
0x180062ba2  mov     rcx, rbx; hFile
0x180062ba5  call    cs:__imp_SetEndOfFile
0x180062bab  test    eax, eax
0x180062bad  jz      loc_180063CB7
0x180062bb3  mov     [rsp+528h+var_4C0], r14
0x180062bb8  mov     qword ptr [rsp+528h+pcbBinary], r14
0x180062bc0  mov     r8d, 4; unsigned int
0x180062bc6  mov     rdx, rbx; void *
0x180062bc9  lea     rcx, [rsp+528h+pcbBinary]; struct Microsoft::Diagnostics::MemoryMappedStream **
0x180062bd1  call    ?Create@MemoryMappedStream@Diagnostics@Microsoft@@SAJPEAPEAV123@PEAXK@Z; Microsoft::Diagnostics::MemoryMappedStream::Create(Microsoft::Diagnostics::MemoryMappedStream * *,void *,ulong)
0x180062bd6  mov     ebx, eax
0x180062bd8  test    eax, eax
0x180062bda  js      loc_180063CFC
0x180062be0  mov     r13, qword ptr [rsp+528h+pcbBinary]
0x180062be8  mov     [rsp+528h+var_4C0], r13
0x180062bed  mov     [rsp+528h+var_4E8], 0
0x180062bf2  mov     [rsp+528h+var_480], r14d
0x180062bfa  mov     [rsp+528h+var_4C8], r14d
0x180062bff  mov     rax, [r13+0]
0x180062c03  lea     r9, [rsp+528h+var_4C8]
0x180062c08  mov     r15d, 3Dh ; '='
0x180062c0e  mov     r8d, r15d
0x180062c11  lea     rdx, aXmlVersion10En_2; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180062c18  mov     rcx, r13
0x180062c1b  mov     rax, [rax+20h]
0x180062c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c24  mov     ebx, eax
0x180062c26  test    eax, eax
0x180062c28  js      loc_180063D4E
0x180062c2e  cmp     [rsp+528h+var_4C8], r15d
0x180062c33  jnz     loc_180063DA0
0x180062c39  xor     r12b, r12b
0x180062c3c  xor     dil, dil
0x180062c3f  xor     esi, esi
0x180062c41  mov     ebx, r15d
0x180062c44  mov     [rsp+528h+var_478], ebx
0x180062c4b  lea     rcx, [rsp+528h+var_278]; void *
0x180062c53  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180062c58  nop
0x180062c59  mov     dword ptr [rsp+528h+var_468], esi
0x180062c60  mov     [rsp+528h+var_4E0], sil
0x180062c65  xor     edx, edx
0x180062c67  lea     rcx, [rsp+528h+var_4D8]
0x180062c6c  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEAA@W4value_t@detail@23@@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::json_abi_v3_11_2::detail::value_t)
0x180062c71  nop
0x180062c72  mov     rcx, [rsp+528h+var_498]
0x180062c7a  mov     rax, [rcx]
0x180062c7d  lea     r9, [rsp+528h+var_480]
0x180062c85  mov     r8d, 1
0x180062c8b  lea     rdx, [rsp+528h+var_4E8]
0x180062c90  mov     rax, [rax+18h]
0x180062c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c99  test    eax, eax
0x180062c9b  jnz     loc_1800636DA
0x180062ca1  add     r14d, [rsp+528h+var_480]
0x180062ca9  cmp     r12b, 2
0x180062cad  jb      short loc_180062D10
0x180062caf  cmp     dil, 2
0x180062cb3  jz      loc_180062D89
0x180062cb9  cmp     dil, 3
0x180062cbd  jb      short loc_180062D23
0x180062cbf  mov     r8d, 1; dwFlags
0x180062cc5  cmp     [rsp+528h+var_4E8], 22h ; '"'
0x180062cca  jz      loc_18006363B
0x180062cd0  mov     rax, [r13+0]
0x180062cd4  lea     r9, [rsp+528h+var_4C8]
0x180062cd9  lea     rdx, [rsp+528h+var_4E8]
0x180062cde  mov     rcx, r13
0x180062ce1  mov     rax, [rax+20h]
0x180062ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062cea  mov     ebx, eax
0x180062cec  test    eax, eax
0x180062cee  js      loc_180062F23
0x180062cf4  cmp     [rsp+528h+var_4C8], 1
0x180062cf9  jnz     loc_180062FE9
0x180062cff  inc     r15d
0x180062d02  inc     esi
0x180062d04  mov     ebx, [rsp+528h+var_478]
0x180062d0b  jmp     loc_180062C72
0x180062d10  cmp     [rsp+528h+var_4E8], 7Bh ; '{'
0x180062d15  jnz     loc_180062C72
0x180062d1b  inc     r12b
0x180062d1e  jmp     loc_180062C72
0x180062d23  movzx   eax, [rsp+528h+var_4E8]
0x180062d28  cmp     al, 22h ; '"'
0x180062d2a  jz      loc_180062F1B
0x180062d30  cmp     dil, 1
0x180062d34  jnz     loc_180062C72
0x180062d3a  movsx   r9d, al
0x180062d3e  mov     rdx, [rsp+528h+var_268]
0x180062d46  mov     r8, [rsp+528h+var_260]
0x180062d4e  lea     rcx, [rsp+528h+var_278]
0x180062d56  cmp     rdx, r8
0x180062d59  jnb     loc_180063986
0x180062d5f  lea     rax, [rdx+1]
0x180062d63  mov     [rsp+528h+var_268], rax
0x180062d6b  cmp     r8, 7
0x180062d6f  cmova   rcx, [rsp+528h+var_278]
0x180062d78  mov     [rcx+rdx*2], r9w
0x180062d7d  xor     eax, eax
0x180062d7f  mov     [rcx+rdx*2+2], ax
0x180062d84  jmp     loc_180062C72
0x180062d89  movzx   eax, [rsp+528h+var_4E8]
0x180062d8e  cmp     al, 7Bh ; '{'
0x180062d90  jnz     short loc_180062D28
0x180062d92  lea     rcx, aUtcsetting; "UtcSetting:"
0x180062d99  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180062d9e  lea     rcx, [rsp+528h+var_278]
0x180062da6  cmp     [rsp+528h+var_260], 7
0x180062daf  cmova   rcx, [rsp+528h+var_278]
0x180062db8  cmp     [rsp+528h+var_268], rax
0x180062dc0  jb      loc_180062C72
0x180062dc6  mov     r8, rax
0x180062dc9  lea     rdx, aUtcsetting; "UtcSetting:"
0x180062dd0  call    cs:__imp__o__wcsnicmp
0x180062dd6  test    eax, eax
0x180062dd8  jnz     loc_180062D23
0x180062dde  mov     ebx, 1
0x180062de3  xor     eax, eax
0x180062de5  mov     edi, eax
0x180062de7  xorps   xmm0, xmm0
0x180062dea  movups  [rsp+528h+var_258], xmm0
0x180062df2  mov     [rsp+528h+var_248], rax
0x180062dfa  mov     [rsp+528h+var_240], rax
0x180062e02  mov     r8d, ebx
0x180062e05  lea     rdx, asc_180395B50; "{"
0x180062e0c  lea     rcx, [rsp+528h+var_258]
0x180062e14  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180062e19  nop
0x180062e1a  mov     rcx, [rsp+528h+var_498]
0x180062e22  mov     rax, [rcx]
0x180062e25  lea     r9, [rsp+528h+var_480]
0x180062e2d  mov     r8d, 1
0x180062e33  lea     rdx, [rsp+528h+var_4E8]
0x180062e38  mov     rax, [rax+18h]
0x180062e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e41  test    eax, eax
0x180062e43  jnz     short loc_180062EB3
0x180062e45  movzx   r9d, [rsp+528h+var_4E8]
0x180062e4b  mov     rcx, [rsp+528h+var_248]
0x180062e53  mov     rdx, [rsp+528h+var_240]
0x180062e5b  cmp     rcx, rdx
0x180062e5e  jnb     loc_180063974
0x180062e64  lea     rax, [rcx+1]
0x180062e68  mov     [rsp+528h+var_248], rax
0x180062e70  lea     rax, [rsp+528h+var_258]
0x180062e78  cmp     rdx, 0Fh
0x180062e7c  cmova   rax, qword ptr [rsp+528h+var_258]
0x180062e85  mov     [rcx+rax], r9b
0x180062e89  mov     byte ptr [rcx+rax+1], 0
0x180062e8e  inc     dword ptr [rsp+528h+var_468]
0x180062e95  inc     r14d
0x180062e98  movzx   eax, [rsp+528h+var_4E8]
0x180062e9d  cmp     al, 7Bh ; '{'
0x180062e9f  jz      loc_1800630B5
0x180062ea5  cmp     al, 7Dh ; '}'
0x180062ea7  jnz     short loc_180062EAB
0x180062ea9  inc     edi
0x180062eab  cmp     ebx, edi
0x180062ead  jnz     loc_180062E1A
0x180062eb3  lea     rcx, [rsp+528h+var_4E0]
0x180062eb8  call    ?size@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBA_KXZ; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::size(void)
0x180062ebd  test    rax, rax
0x180062ec0  jnz     loc_18006312A
0x180062ec6  mov     [rsp+528h+var_380], rax
0x180062ece  lea     r8, [rsp+528h+var_3B8]
0x180062ed6  lea     rdx, [rsp+528h+var_258]
0x180062ede  lea     rcx, [rsp+528h+lpExistingFileName]
0x180062ee6  call    ??$parse@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@SA?AV012@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@detail@json_abi_v3_11_2@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@34@@Z@4@_N2@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::parse<std::string &>(std::string &,std::function<bool (int,nlohmann::json_abi_v3_11_2::detail::parse_event_t,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> &)>,bool,bool)
0x180062eeb  movzx   edx, [rsp+528h+var_4E0]
0x180062ef0  movzx   ecx, byte ptr [rax]
0x180062ef3  mov     [rsp+528h+var_4E0], cl
0x180062ef7  mov     [rax], dl
0x180062ef9  mov     r8, [rsp+528h+var_4D8]
0x180062efe  lea     rcx, [rax+8]
0x180062f02  mov     rdx, [rcx]
0x180062f05  mov     [rsp+528h+var_4D8], rdx
0x180062f0a  mov     [rcx], r8
0x180062f0d  movzx   edx, byte ptr [rax]
0x180062f10  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::json_abi_v3_11_2::detail::value_t)
0x180062f15  nop
0x180062f16  jmp     loc_1800630EA
0x180062f1b  inc     dil
0x180062f1e  jmp     loc_180062C72
0x180062f23  mov     rcx, [rsp+528h]; this
0x180062f2b  mov     r9d, ebx; char *
0x180062f2e  lea     r8, aOnecoreBaseTel_259; "onecore\\base\\telemetry\\utc\\service"...
0x180062f35  mov     edx, 378h; void *
0x180062f3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062f3f  nop
0x180062f40  movzx   edx, [rsp+528h+var_4E0]
0x180062f45  lea     rcx, [rsp+528h+var_4D8]
0x180062f4a  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::json_abi_v3_11_2::detail::value_t)
0x180062f4f  nop
0x180062f50  lea     rcx, [rsp+528h+var_278]
0x180062f58  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062f5d  nop
0x180062f5e  test    r13, r13
0x180062f61  jz      short loc_180062F7A
  ... truncated ...
```

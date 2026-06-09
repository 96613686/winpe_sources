# CScenarioCtrlContainerServicing::GetPathToTopLevelPackage(wil::basic_zstring_view<wchar_t>)

- ea: `0x1800638e4`
- end: `0x18006412e`
- name: `?GetPathToTopLevelPackage@CScenarioCtrlContainerServicing@@AEAA?AV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@_N@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `2122`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180060534`

## callees

- `0x1800059d0`
- `0x1800089e0`
- `0x18001270c`
- `0x180012b08`
- `0x180012d94`
- `0x18001fd10`
- `0x180020254`
- `0x180023b20`
- `0x1800638e4`
- `0x180067684`
- `0x180077664`
- `0x180094d0c`
- `0x18009b6b0`
- `0x18009f0b0`
- `0x1800acd88`
- `0x1801417cc`
- `0x180150bfc`
- `0x1801def30`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180063c33`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180063c33`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180063e7d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180063e7d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180063c05`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180063c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063e94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063e94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063ea9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063ea9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180063ca5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180063e6d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180063ca5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180063e6d`

## string_xrefs

- `0x1800640a1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x1800640b6`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x1800640cb`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x1800640dd`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x1800640f2`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x180064107`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x18006411c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x180063bfe`: `pkeyhelper.dll`
- `0x180063c29`: `GetCompositionEditionForVirtualEdition`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CScenarioCtrlContainerServicing::GetPathToTopLevelPackage(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v5; // eax
  void (__fastcall ***v6)(_QWORD); // rsi
  __int64 v7; // r15
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int128 *v12; // r11
  unsigned __int64 v13; // r12
  char v14; // r8
  wchar_t *v15; // rcx
  __int64 v16; // rdx
  char v17; // r10
  wchar_t *v18; // r9
  __int64 v19; // rax
  int v20; // eax
  bool v21; // sf
  char v22; // al
  __int128 *p_Src; // rax
  wchar_t *v25; // r12
  __int64 v26; // rax
  unsigned int v27; // ebx
  __int64 v28; // rax
  __int64 v29; // rcx
  int Value; // eax
  HMODULE Library; // rax
  const char *v32; // r9
  HMODULE v33; // rbx
  FARPROC ProcAddress; // rax
  const char *v35; // r9
  int v36; // eax
  void *v37; // rcx
  __int64 v38; // rdx
  int v39; // eax
  _QWORD *v40; // r8
  const wchar_t *v41; // r9
  const wchar_t *v42; // rcx
  int SingleFile; // eax
  wchar_t *v44; // rax
  __int64 v45; // rax
  unsigned int v46; // edi
  _OWORD *v47; // rdi
  HLOCAL v48; // rcx
  __int64 v49; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rdi
  __int64 v55; // rax
  __int64 v56; // rax
  unsigned int v57; // r15d
  __int64 *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // r15
  __int64 v61; // rbx
  __int64 v62; // r12
  __int64 v63; // r13
  int v64; // [rsp+28h] [rbp-E0h]
  int v65; // [rsp+28h] [rbp-E0h]
  int v66; // [rsp+28h] [rbp-E0h]
  wchar_t *p_hMem; // [rsp+48h] [rbp-C0h] BYREF
  wchar_t *v68; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v69; // [rsp+58h] [rbp-B0h]
  __int64 v70; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v71; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v72; // [rsp+70h] [rbp-98h]
  wchar_t *v73; // [rsp+78h] [rbp-90h]
  __int64 v74; // [rsp+80h] [rbp-88h] BYREF
  wchar_t *v75[6]; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v76[2]; // [rsp+B8h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp-30h] BYREF
  __int128 Src; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v79; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v80; // [rsp+F8h] [rbp-10h]
  _QWORD v81[2]; // [rsp+100h] [rbp-8h] BYREF
  wchar_t *v82; // [rsp+110h] [rbp+8h]
  unsigned __int64 v83; // [rsp+118h] [rbp+10h]
  __int128 v84; // [rsp+120h] [rbp+18h] BYREF
  __int128 v85; // [rsp+130h] [rbp+28h] BYREF
  __m128i si128; // [rsp+140h] [rbp+38h]
  wchar_t *v87[4]; // [rsp+150h] [rbp+48h] BYREF
  wchar_t *v88[4]; // [rsp+170h] [rbp+68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v75[5] = (wchar_t *)-2LL;
  p_hMem = (wchar_t *)a1;
  v75[0] = (wchar_t *)a2;
  v74 = 0;
  v5 = LoadActionList(0, *a3, a3, &v74);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
      (const char *)(unsigned int)v5,
      v64);
  v6 = (void (__fastcall ***)(_QWORD))v74;
  if ( *(_DWORD *)(v74 + 52) == 23 )
  {
    v7 = *(_QWORD *)(v74 + 88);
    v8 = v7 + 168LL * *(unsigned int *)(v74 + 96);
    if ( v7 != v8 )
    {
      v9 = -1;
      while ( 1 )
      {
        if ( *(_DWORD *)(v7 + 88) != 11 )
          goto LABEL_31;
        v10 = *(_QWORD *)(v7 + 40);
        if ( !v10 )
          goto LABEL_31;
        Src = 0;
        v79 = 0;
        v80 = 0;
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(v10 + 2 * v11) );
        std::wstring::_Construct<1,wchar_t const *>(&Src, v10, v11);
        std::wstring::_Append<wchar_t>(&Src);
        v12 = (__int128 *)Src;
        v13 = v80;
        v14 = 0;
        if ( v80 <= 7 )
          break;
        v15 = (wchar_t *)Src;
        if ( (_QWORD)Src )
          goto LABEL_13;
        v15 = p_hMem;
        v16 = (__int64)p_hMem;
        v17 = 0;
LABEL_16:
        v18 = *(wchar_t **)(v7 + 56);
        if ( v18 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          v14 = 1;
        }
        else
        {
          v18 = p_hMem;
          v19 = (__int64)p_hMem;
        }
        if ( v17 )
        {
          if ( v14 )
          {
            v71 = 2 * v19;
            v72 = 2 * v19 + 2;
            v73 = v18;
            v81[0] = 2 * v16;
            v81[1] = 2 * v16 + 2;
            v82 = v15;
            LODWORD(hMem) = 0;
            v20 = Windows::StringUtil::Rtl::CompareStringsByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                    v81,
                    &v71,
                    &hMem);
            if ( (_DWORD)hMem || (v21 = v20 < 0, v22 = 1, v21) )
              v22 = 0;
            v13 = v80;
            v12 = (__int128 *)Src;
            goto LABEL_29;
          }
        }
        else if ( !v14 )
        {
          goto LABEL_34;
        }
        v22 = 0;
LABEL_29:
        if ( v22 )
        {
LABEL_34:
          p_Src = &Src;
          if ( v13 > 7 )
            p_Src = v12;
          v71 = (__int64)p_Src;
          v72 = v79;
          v25 = p_hMem;
          v26 = *((_QWORD *)p_hMem + 1);
          v27 = 0;
          if ( v26 )
            v27 = *(_DWORD *)(v26 - 4);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          p_hMem = (wchar_t *)*((_QWORD *)p_hMem + 1);
          v68 = (wchar_t *)v27;
          CreatePath(v88, (__int64)&p_hMem, &v71);
          v70 = 0;
          v28 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v70);
          Value = CRegUtilT<wchar_t *,CRegType,0,1>::GetValue(
                    v29,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                    L"EditionId",
                    v28);
          if ( Value < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1FA,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
              (const char *)(unsigned int)Value,
              v64);
          Library = LoadLibraryExW(L"pkeyhelper.dll", 0, 0);
          v33 = Library;
          v71 = (__int64)Library;
          if ( !Library )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x1FD,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
              v32);
          ProcAddress = GetProcAddress(Library, "GetCompositionEditionForVirtualEdition");
          if ( !ProcAddress )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x200,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
              v35);
          hMem = 0;
          p_hMem = (wchar_t *)&hMem;
          v68 = 0;
          LOBYTE(v69) = 1;
          v36 = ((__int64 (__fastcall *)(__int64, wchar_t **))ProcAddress)(v70, &v68);
          if ( v36 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x203,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
              (const char *)(unsigned int)v36,
              v64);
          if ( (_BYTE)v69 )
          {
            v37 = *(void **)p_hMem;
            *(_QWORD *)p_hMem = v68;
            if ( v37 )
              LocalFree(v37);
          }
          v38 = *(_QWORD *)(v7 + 16);
          v84 = 0;
          v85 = 0;
          do
            ++v9;
          while ( *(_WORD *)(v38 + 2 * v9) );
          std::wstring::_Construct<1,wchar_t const *>(&v84, v38, v9);
          p_hMem = 0;
          v75[0] = 0;
          v39 = ShredStringIdIntoAttributes(
                  *(wchar_t **)(v7 + 16),
                  0x7Eu,
                  0,
                  0,
                  (const wchar_t **)&p_hMem,
                  0,
                  (const wchar_t **)v75);
          if ( v39 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x209,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
              (const char *)(unsigned int)v39,
              v65);
          wil::str_printf<std::wstring>(
            v81,
            L"Microsoft-Windows-%wsEdition~31bf3856ad364e35~%ws~~%ws.mum",
            hMem,
            p_hMem,
            v75[0]);
          v40 = v81;
          if ( v83 > 7 )
            v40 = (_QWORD *)v81[0];
          wil::str_printf<std::wstring>(v87, L"windows\\servicing\\packages\\%ws", v40);
          v41 = (const wchar_t *)v87;
          if ( v87[3] > (wchar_t *)7 )
            v41 = v87[0];
          v42 = (const wchar_t *)v88;
          if ( v88[3] > (wchar_t *)7 )
            v42 = v88[0];
          SingleFile = CbsEsdExtractSingleFile(v42, 3u, *((const wchar_t **)v25 + 1), v41, 1);
          if ( SingleFile < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x211,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
              (const char *)(unsigned int)SingleFile,
              v66);
          v44 = (wchar_t *)v81;
          if ( v83 > 7 )
            v44 = (wchar_t *)v81[0];
          p_hMem = v44;
          v68 = v82;
          v45 = *((_QWORD *)v25 + 1);
          v46 = 0;
          if ( v45 )
            v46 = *(_DWORD *)(v45 - 4);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v75[0] = *((wchar_t **)v25 + 1);
          v75[1] = (wchar_t *)v46;
          v47 = CreatePath(v76, (__int64)v75, &p_hMem);
          *(_BYTE *)a2 = 0;
          std::wstring::wstring(a2 + 8, &v84);
          *(_OWORD *)(a2 + 40) = 0;
          *(_QWORD *)(a2 + 56) = 0;
          *(_QWORD *)(a2 + 64) = 0;
          *(_OWORD *)(a2 + 40) = *v47;
          *(_OWORD *)(a2 + 56) = v47[1];
          *(_WORD *)v47 = 0;
          *((_QWORD *)v47 + 2) = 0;
          *((_QWORD *)v47 + 3) = 7;
          std::wstring::~wstring(v76);
          std::wstring::~wstring(v87);
          std::wstring::~wstring(v81);
          std::wstring::~wstring(&v84);
          v48 = hMem;
          hMem = 0;
          if ( v48 )
            LocalFree(v48);
          FreeLibrary(v33);
          v49 = v70;
          if ( v70 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, (LPVOID)(v49 - 4));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          std::wstring::~wstring(v88);
          std::wstring::~wstring(&Src);
          if ( v6 )
            goto LABEL_64;
          return a2;
        }
        std::wstring::~wstring(&Src);
LABEL_31:
        v7 += 168;
        if ( v7 == v8 )
          goto LABEL_32;
      }
      v15 = (wchar_t *)&Src;
LABEL_13:
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v17 = 1;
      goto LABEL_16;
    }
LABEL_32:
    LogAdapter::TraceInfo<>("Unexpected scenario. Nothing to do for now.");
    *(_BYTE *)a2 = 0;
    *(_OWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    *(_QWORD *)(a2 + 32) = 0;
    std::wstring::_Construct<1,wchar_t const *>(a2 + 8, &String2, 0);
    *(_OWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    std::wstring::_Construct<1,wchar_t const *>(a2 + 40, &String2, 0);
    (**v6)(v6);
    return a2;
  }
  if ( *(_DWORD *)(v74 + 52) != 1 )
    goto LABEL_32;
  v51 = *(_QWORD *)(v74 + 88);
  v52 = v51 + 168LL * *(unsigned int *)(v74 + 96);
  while ( 1 )
  {
    if ( v51 == v52 )
    {
      LogAdapter::TraceInfo<>("No LCU present. Nothing to do for now.");
      *(_BYTE *)a2 = 0;
      *(_OWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      std::wstring::_Construct<1,wchar_t const *>(a2 + 8, &String2, 0);
      *(_OWORD *)(a2 + 40) = 0;
      *(_QWORD *)(a2 + 56) = 0;
      *(_QWORD *)(a2 + 64) = 0;
      std::wstring::_Construct<1,wchar_t const *>(a2 + 40, &String2, 0);
      (**v6)(v6);
      return a2;
    }
    if ( *(_DWORD *)(v51 + 88) == 6 )
      break;
    v51 += 168;
  }
  v53 = *(_QWORD *)(*(_QWORD *)(v51 + 112) + 24LL);
  v71 = v53;
  v54 = -1;
  v55 = -1;
  do
    ++v55;
  while ( *(_WORD *)(v53 + 2 * v55) );
  v72 = v55;
  v56 = *(_QWORD *)(a1 + 8);
  v57 = 0;
  if ( v56 )
    v57 = *(_DWORD *)(v56 - 4);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  p_hMem = *(wchar_t **)(a1 + 8);
  v68 = (wchar_t *)v57;
  v58 = (__int64 *)CreatePath(v75, (__int64)&p_hMem, &v71);
  LOBYTE(v84) = 1;
  v59 = *(_QWORD *)(v51 + 16);
  *((_QWORD *)&v84 + 1) = v59;
  v85 = 0;
  v60 = *v58;
  *(_QWORD *)&v85 = *v58;
  v61 = v58[1];
  *((_QWORD *)&v85 + 1) = v61;
  v62 = v58[2];
  si128.m128i_i64[0] = v62;
  v63 = v58[3];
  si128.m128i_i64[1] = v63;
  *(_WORD *)v58 = 0;
  v58[2] = 0;
  v58[3] = 7;
  *(_BYTE *)a2 = 1;
  *(_OWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  do
    ++v54;
  while ( *(_WORD *)(v59 + 2 * v54) );
  std::wstring::_Construct<1,wchar_t const *>(a2 + 8, v59, v54);
  *(_QWORD *)(a2 + 40) = v60;
  *(_QWORD *)(a2 + 48) = v61;
  *(_QWORD *)(a2 + 56) = v62;
  *(_QWORD *)(a2 + 64) = v63;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v85) = 0;
  std::wstring::~wstring(&v85);
  std::wstring::~wstring(v75);
  if ( v6 )
LABEL_64:
    (**v6)(v6);
  return a2;
}

```

## disassembly

```asm
0x1800638e4  mov     rax, rsp
0x1800638e7  push    rbp
0x1800638e8  push    rsi
0x1800638e9  push    rdi
0x1800638ea  push    r12
0x1800638ec  push    r13
0x1800638ee  push    r14
0x1800638f0  push    r15
0x1800638f2  lea     rbp, [rax-0C8h]
0x1800638f9  sub     rsp, 190h
0x180063900  mov     [rbp+0C0h+var_118], 0FFFFFFFFFFFFFFFEh
0x180063908  mov     [rax+20h], rbx
0x18006390c  mov     rax, cs:__security_cookie
0x180063913  xor     rax, rsp
0x180063916  mov     [rbp+0C0h+var_38], rax
0x18006391d  mov     r14, rdx
0x180063920  mov     r13, rcx
0x180063923  mov     [rsp+1C0h+var_180], rcx
0x180063928  mov     [rbp+0C0h+var_140], rdx
0x18006392c  xor     r12d, r12d
0x18006392f  mov     [rsp+1C0h+var_148], r12
0x180063934  lea     r9, [rsp+1C0h+var_148]
0x180063939  mov     rdx, [r8]
0x18006393c  xor     ecx, ecx
0x18006393e  call    LoadActionList
0x180063943  mov     rcx, [rbp+0C8h]; this
0x18006394a  test    eax, eax
0x18006394c  js      loc_1800640B3
0x180063952  mov     rsi, [rsp+1C0h+var_148]
0x180063957  cmp     dword ptr [rsi+34h], 17h
0x18006395b  jnz     loc_180063EEE
0x180063961  mov     r15, [rsi+58h]
0x180063965  mov     eax, [rsi+60h]
0x180063968  imul    rbx, rax, 0A8h
0x18006396f  add     rbx, r15
0x180063972  cmp     r15, rbx
0x180063975  jz      loc_180063AD4
0x18006397b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006397f  lea     r13d, [r12+7]
0x180063984  cmp     dword ptr [r15+58h], 0Bh
0x180063989  jnz     loc_180063AC4
0x18006398f  mov     rdx, [r15+28h]
0x180063993  test    rdx, rdx
0x180063996  jz      loc_180063AC4
0x18006399c  xorps   xmm0, xmm0
0x18006399f  movups  [rbp+0C0h+Src], xmm0
0x1800639a3  mov     [rbp+0C0h+var_D8], r12
0x1800639a7  mov     [rbp+0C0h+var_D0], r12
0x1800639ab  mov     r8, rdi
0x1800639ae  inc     r8
0x1800639b1  cmp     [rdx+r8*2], r12w
0x1800639b6  jnz     short loc_1800639AE
0x1800639b8  lea     rcx, [rbp+0C0h+Src]
0x1800639bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800639c1  nop
0x1800639c2  mov     r8d, 4
0x1800639c8  lea     rdx, aEsd; ".esd"
0x1800639cf  lea     rcx, [rbp+0C0h+Src]; Src
0x1800639d3  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800639d8  mov     r11, qword ptr [rbp+0C0h+Src]
0x1800639dc  mov     r12, [rbp+0C0h+var_D0]
0x1800639e0  xor     r8d, r8d
0x1800639e3  cmp     r12, r13
0x1800639e6  jbe     short loc_1800639FF
0x1800639e8  mov     rcx, r11
0x1800639eb  test    r11, r11
0x1800639ee  jnz     short loc_180063A03
0x1800639f0  mov     rcx, [rsp+1C0h+var_180]
0x1800639f5  mov     rdx, [rsp+1C0h+var_180]
0x1800639fa  mov     r10b, r8b
0x1800639fd  jmp     short loc_180063A13
0x1800639ff  lea     rcx, [rbp+0C0h+Src]
0x180063a03  mov     rdx, rdi
0x180063a06  inc     rdx
0x180063a09  cmp     [rcx+rdx*2], r8w
0x180063a0e  jnz     short loc_180063A06
0x180063a10  mov     r10b, 1
0x180063a13  mov     r9, [r15+38h]
0x180063a17  test    r9, r9
0x180063a1a  jz      short loc_180063A2E
0x180063a1c  mov     rax, rdi
0x180063a1f  inc     rax
0x180063a22  cmp     [r9+rax*2], r8w
0x180063a27  jnz     short loc_180063A1F
0x180063a29  mov     r8b, 1
0x180063a2c  jmp     short loc_180063A38
0x180063a2e  mov     r9, [rsp+1C0h+var_180]
0x180063a33  mov     rax, [rsp+1C0h+var_180]
0x180063a38  test    r10b, r10b
0x180063a3b  jz      short loc_180063AA1
0x180063a3d  xor     r10d, r10d
0x180063a40  test    r8b, r8b
0x180063a43  jz      short loc_180063AAD
0x180063a45  add     rax, rax
0x180063a48  mov     [rsp+1C0h+var_160], rax
0x180063a4d  add     rax, 2
0x180063a51  mov     [rsp+1C0h+var_158], rax
0x180063a56  mov     [rsp+1C0h+var_150], r9
0x180063a5b  lea     rax, [rdx+rdx]
0x180063a5f  mov     [rbp+0C0h+var_C8], rax
0x180063a63  add     rax, 2
0x180063a67  mov     [rbp+0C0h+var_C0], rax
0x180063a6b  mov     [rbp+0C0h+var_B8], rcx
0x180063a6f  mov     dword ptr [rbp+0C0h+hMem], r10d
0x180063a73  lea     r8, [rbp+0C0h+hMem]
0x180063a77  lea     rdx, [rsp+1C0h+var_160]
0x180063a7c  lea     rcx, [rbp+0C0h+var_C8]
0x180063a80  call    ??$CompareStringsByOrdinalCaseInvariant@U_LUNICODE_STRING@@U1@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@0PEAH@Z; Windows::StringUtil::Rtl::CompareStringsByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &,int *)
0x180063a85  xor     r10d, r10d
0x180063a88  cmp     dword ptr [rbp+0C0h+hMem], r10d
0x180063a8c  jnz     short loc_180063A94
0x180063a8e  test    eax, eax
0x180063a90  mov     al, 1
0x180063a92  jns     short loc_180063A97
0x180063a94  mov     al, r10b
0x180063a97  mov     r12, [rbp+0C0h+var_D0]
0x180063a9b  mov     r11, qword ptr [rbp+0C0h+Src]
0x180063a9f  jmp     short loc_180063AB0
0x180063aa1  cmp     r10b, r8b
0x180063aa4  jz      loc_180063B64
0x180063aaa  xor     r10d, r10d
0x180063aad  mov     al, r10b
0x180063ab0  test    al, al
0x180063ab2  jnz     loc_180063B67
0x180063ab8  lea     rcx, [rbp+0C0h+Src]; void *
0x180063abc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180063ac1  xor     r12d, r12d
0x180063ac4  add     r15, 0A8h
0x180063acb  cmp     r15, rbx
0x180063ace  jnz     loc_180063984
0x180063ad4  lea     rcx, aUnexpectedScen; "Unexpected scenario. Nothing to do for "...
0x180063adb  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180063ae0  mov     [r14], r12b
0x180063ae3  lea     rcx, [r14+8]
0x180063ae7  xorps   xmm0, xmm0
0x180063aea  movups  xmmword ptr [rcx], xmm0
0x180063aed  mov     [rcx+10h], r12
0x180063af1  mov     [rcx+18h], r12
0x180063af5  xor     r8d, r8d
0x180063af8  lea     rdx, String2
0x180063aff  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180063b04  nop
0x180063b05  lea     rcx, [r14+28h]
0x180063b09  xorps   xmm0, xmm0
0x180063b0c  movups  xmmword ptr [rcx], xmm0
0x180063b0f  mov     [rcx+10h], r12
0x180063b13  mov     [rcx+18h], r12
0x180063b17  xor     r8d, r8d
0x180063b1a  lea     rdx, String2
0x180063b21  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180063b26  nop
0x180063b27  mov     rax, [rsi]
0x180063b2a  mov     rcx, rsi
0x180063b2d  mov     rax, [rax]
0x180063b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b35  nop
0x180063b36  mov     rax, r14
0x180063b39  mov     rcx, [rbp+0C0h+var_38]
0x180063b40  xor     rcx, rsp; StackCookie
0x180063b43  call    __security_check_cookie
0x180063b48  mov     rbx, [rsp+1C0h+arg_18]
0x180063b50  add     rsp, 190h
0x180063b57  pop     r15
0x180063b59  pop     r14
0x180063b5b  pop     r13
0x180063b5d  pop     r12
0x180063b5f  pop     rdi
0x180063b60  pop     rsi
0x180063b61  pop     rbp
0x180063b62  retn
0x180063b64  xor     r10d, r10d
0x180063b67  lea     rax, [rbp+0C0h+Src]
0x180063b6b  cmp     r12, r13
0x180063b6e  cmova   rax, r11
0x180063b72  mov     [rsp+1C0h+var_160], rax
0x180063b77  mov     rax, [rbp+0C0h+var_D8]
0x180063b7b  mov     [rsp+1C0h+var_158], rax
0x180063b80  mov     r12, [rsp+1C0h+var_180]
0x180063b85  mov     rax, [r12+8]
0x180063b8a  test    rax, rax
0x180063b8d  mov     ebx, r10d
0x180063b90  jz      short loc_180063B95
0x180063b92  mov     ebx, [rax-4]
0x180063b95  xor     ecx, ecx
0x180063b97  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180063b9c  mov     rax, [r12+8]
0x180063ba1  mov     [rsp+1C0h+var_180], rax
0x180063ba6  mov     eax, ebx
0x180063ba8  mov     [rsp+1C0h+var_178], rax
0x180063bad  lea     r8, [rsp+1C0h+var_160]
0x180063bb2  lea     rdx, [rsp+1C0h+var_180]
0x180063bb7  lea     rcx, [rbp+0C0h+var_58]
0x180063bbb  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180063bc0  nop
0x180063bc1  mov     [rsp+1C0h+var_168], 0
0x180063bca  lea     rcx, [rsp+1C0h+var_168]
0x180063bcf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x180063bd4  mov     r9, rax
0x180063bd7  lea     r8, aEditionid; "EditionId"
0x180063bde  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180063be5  call    ?GetValue@?$CRegUtilT@PEA_WUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAPEA_WPEAK@Z; CRegUtilT<wchar_t *,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,ulong *)
0x180063bea  mov     rcx, [rbp+0C8h]; this
0x180063bf1  test    eax, eax
0x180063bf3  js      loc_1800640C8
0x180063bf9  xor     r8d, r8d; dwFlags
0x180063bfc  xor     edx, edx; hFile
0x180063bfe  lea     rcx, aPkeyhelperDll; "pkeyhelper.dll"
0x180063c05  call    cs:__imp_LoadLibraryExW
0x180063c0c  nop     dword ptr [rax+rax+00h]
0x180063c11  mov     rbx, rax
0x180063c14  mov     [rsp+1C0h+var_160], rax
0x180063c19  mov     rcx, [rbp+0C8h]; this
0x180063c20  test    rax, rax
0x180063c23  jz      loc_1800640A1
0x180063c29  lea     rdx, aGetcomposition; "GetCompositionEditionForVirtualEdition"
0x180063c30  mov     rcx, rax; hModule
0x180063c33  call    cs:__imp_GetProcAddress
0x180063c3a  nop     dword ptr [rax+rax+00h]
0x180063c3f  mov     rcx, [rbp+0C8h]; this
0x180063c46  xor     edx, edx
0x180063c48  test    rax, rax
0x180063c4b  jz      loc_1800640DD
0x180063c51  mov     [rbp+0C0h+hMem], rdx
0x180063c55  lea     rcx, [rbp+0C0h+hMem]
0x180063c59  mov     [rsp+1C0h+var_180], rcx
0x180063c5e  mov     [rsp+1C0h+var_178], rdx
0x180063c63  mov     byte ptr [rsp+1C0h+var_170], 1
0x180063c68  lea     rdx, [rsp+1C0h+var_178]
0x180063c6d  mov     rcx, [rsp+1C0h+var_168]
0x180063c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c77  mov     rcx, [rbp+0C8h]; this
0x180063c7e  xor     r8d, r8d
0x180063c81  test    eax, eax
0x180063c83  js      loc_1800640EF
0x180063c89  cmp     byte ptr [rsp+1C0h+var_170], r8b
0x180063c8e  jz      short loc_180063CB4
0x180063c90  mov     rdx, [rsp+1C0h+var_180]
0x180063c95  mov     rcx, [rdx]; hMem
0x180063c98  mov     rax, [rsp+1C0h+var_178]
0x180063c9d  mov     [rdx], rax
0x180063ca0  test    rcx, rcx
0x180063ca3  jz      short loc_180063CB4
0x180063ca5  call    cs:__imp_LocalFree
0x180063cac  nop     dword ptr [rax+rax+00h]
0x180063cb1  xor     r8d, r8d
0x180063cb4  mov     rdx, [r15+10h]
0x180063cb8  xorps   xmm0, xmm0
0x180063cbb  movups  [rbp+0C0h+var_A8], xmm0
0x180063cbf  xorps   xmm1, xmm1
0x180063cc2  movdqu  [rbp+0C0h+var_98], xmm1
0x180063cc7  inc     rdi
0x180063cca  cmp     [rdx+rdi*2], r8w
0x180063ccf  jnz     short loc_180063CC7
0x180063cd1  mov     r8, rdi
0x180063cd4  lea     rcx, [rbp+0C0h+var_A8]
0x180063cd8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180063cdd  nop
0x180063cde  xor     ecx, ecx
0x180063ce0  mov     [rsp+1C0h+var_180], rcx
0x180063ce5  mov     [rbp+0C0h+var_140], rcx
0x180063ce9  lea     edx, [rcx+7Eh]; wchar_t
0x180063cec  lea     rax, [rbp+0C0h+var_140]
0x180063cf0  mov     [rsp+30h], rax; wchar_t **
0x180063cf5  mov     [rsp+1C0h+var_198], rcx; wchar_t **
0x180063cfa  lea     rax, [rsp+1C0h+var_180]
0x180063cff  mov     [rsp+1C0h+var_1A0], rax; int
0x180063d04  xor     r9d, r9d; wchar_t **
0x180063d07  xor     r8d, r8d; wchar_t **
0x180063d0a  mov     rcx, [r15+10h]; wchar_t *
0x180063d0e  call    ?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z; ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)
0x180063d13  mov     rcx, [rbp+0C8h]; this
0x180063d1a  xor     r15d, r15d
0x180063d1d  test    eax, eax
0x180063d1f  js      loc_180064104
0x180063d25  mov     rax, [rbp+0C0h+var_140]
0x180063d29  mov     [rsp+1C0h+var_1A0], rax
0x180063d2e  mov     r9, [rsp+1C0h+var_180]
0x180063d33  mov     r8, [rbp+0C0h+hMem]
0x180063d37  lea     rdx, aMicrosoftWindo_15; "Microsoft-Windows-%wsEdition~31bf3856ad"...
0x180063d3e  lea     rcx, [rbp+0C0h+var_C8]
0x180063d42  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180063d47  nop
0x180063d48  lea     r8, [rbp+0C0h+var_C8]
0x180063d4c  cmp     [rbp+0C0h+var_B0], r13
0x180063d50  cmova   r8, [rbp+0C0h+var_C8]
0x180063d55  lea     rdx, aWindowsServici_0; "windows\\servicing\\packages\\%ws"
0x180063d5c  lea     rcx, [rbp+0C0h+var_78]
0x180063d60  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180063d65  nop
0x180063d66  lea     r9, [rbp+0C0h+var_78]
0x180063d6a  cmp     [rbp+0C0h+var_60], r13
0x180063d6e  cmova   r9, [rbp+0C0h+var_78]; wchar_t *
0x180063d73  lea     rcx, [rbp+0C0h+var_58]
0x180063d77  cmp     [rbp+0C0h+var_40], r13
0x180063d7e  cmova   rcx, [rbp+0C0h+var_58]; wchar_t *
0x180063d83  mov     byte ptr [rsp+1C0h+var_1A0], 1; int
0x180063d88  mov     r8, [r12+8]; wchar_t *
0x180063d8d  lea     edx, [r15+3]; unsigned int
0x180063d91  call    ?CbsEsdExtractSingleFile@@YAJPEB_WK00_N@Z; CbsEsdExtractSingleFile(wchar_t const *,ulong,wchar_t const *,wchar_t const *,bool)
0x180063d96  mov     rcx, [rbp+0C8h]; this
  ... truncated ...
```

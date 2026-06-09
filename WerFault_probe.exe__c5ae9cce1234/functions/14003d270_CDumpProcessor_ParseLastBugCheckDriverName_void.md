# CDumpProcessor::ParseLastBugCheckDriverName(void)

- ea: `0x14003d270`
- end: `0x14003d7ce`
- name: `?ParseLastBugCheckDriverName@CDumpProcessor@@AEAAXXZ`
- size: `1374`
- prototype: `void __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x14003d7d4`

## callees

- `0x140002470`
- `0x140002728`
- `0x14000cc58`
- `0x14000e6dc`
- `0x140034d9c`
- `0x14003bc28`
- `0x14003d270`
- `0x14005b7dc`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14003d674`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14003d674`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d7ac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d7ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d34b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d34b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003d311`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003d311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d356`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003d2fc`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003d2fc`

## string_xrefs

- `0x14003d383`: `UtilDebugCreateEx failed for IDebugClient4`
- `0x14003d3ee`: `OpenDumpFileWide failed for %ws`
- `0x14003d629`: `ReadTagged failed`
- `0x14003d64b`: `ReadTagged returned wrong information`
- `0x14003d341`: `DebugCreateEx`
- `0x14003d30a`: `dbgeng.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CDumpProcessor::ParseLastBugCheckDriverName(CDumpProcessor *this)
{
  HMODULE Library; // rbx
  const char *v3; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v6; // sf
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rsi
  int v11; // edi
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  size_t v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  wil::details *v20; // [rsp+20h] [rbp-89h]
  wil::details *v21; // [rsp+20h] [rbp-89h]
  char *v22; // [rsp+30h] [rbp-79h]
  unsigned int v23; // [rsp+40h] [rbp-69h] BYREF
  __int64 v24; // [rsp+48h] [rbp-61h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-59h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-51h] BYREF
  __int64 v27; // [rsp+60h] [rbp-49h] BYREF
  __int64 v28; // [rsp+68h] [rbp-41h] BYREF
  wchar_t *Source; // [rsp+70h] [rbp-39h] BYREF
  wchar_t *v30; // [rsp+78h] [rbp-31h]
  _WORD v31[8]; // [rsp+80h] [rbp-29h] BYREF
  HMODULE v32; // [rsp+90h] [rbp-19h]
  __int64 v33; // [rsp+98h] [rbp-11h] BYREF
  __int64 *v34; // [rsp+A0h] [rbp-9h]
  __int128 Buf1; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+108h] [rbp+5Fh]

  Buf1 = 0;
  Library = 0;
  v32 = 0;
  v25 = 0;
  v27 = 0;
  v24 = 0;
  Source = v31;
  v30 = v31;
  v31[0] = 0;
  v23 = 0;
  v26 = 0;
  v28 = 0;
  v3 = (const char *)*((_QWORD *)this + 22);
  if ( !v3 || !*(_WORD *)v3 )
  {
    LODWORD(v20) = -2147024894;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::ParseLastBugCheckDriverName",
      v20,
      (int)"No dump file to get header from",
      v22);
    goto LABEL_42;
  }
  SetEnvironmentVariableW(L"DBGENG_NO_BUGCHECK_ANALYSIS", L"1");
  Library = LoadLibraryExW(L"dbgeng.dll", 0, 0x800u);
  v32 = Library;
  if ( !Library )
  {
    LODWORD(v20) = -2147024770;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::ParseLastBugCheckDriverName",
      v20,
      (int)"UtilLoadDbgEng failed",
      v22);
    goto LABEL_42;
  }
  v25 = 0;
  ProcAddress = GetProcAddress(Library, "DebugCreateEx");
  if ( ProcAddress )
  {
    LastError = ((__int64 (__fastcall *)(GUID *, __int64, _QWORD))ProcAddress)(
                  &GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e,
                  688136,
                  &v25);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v6 = LastError < 0;
LABEL_9:
  if ( v6 )
  {
    LODWORD(v20) = LastError;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::ParseLastBugCheckDriverName",
      v20,
      (int)"UtilDebugCreateEx failed for IDebugClient4",
      v22);
  }
  else
  {
    v7 = tlx::queryinterface_unique<IDebugControl,IDebugClient4>(&v27, v25);
    if ( v7 >= 0 )
    {
      v8 = (*v25)[60](v25, (GUID *)v3, 0);
      if ( v8 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v27 + 744LL))(v27, 0, 0xFFFFFFFFLL);
        if ( v9 >= 0 )
        {
          v10 = **v25;
          v33 = 0;
          v34 = &v24;
          v24 = 0;
          v11 = v10(v25, &GUID_d98ada1f_29e9_4ef5_a6c0_e53349883212, &v33);
          if ( v33 )
          {
            v12 = *v34;
            *v34 = v33;
            if ( v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          if ( v11 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 248LL))(v24, &v28);
            if ( v13 >= 0 )
            {
              while ( 1 )
              {
                v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, unsigned int *))(*(_QWORD *)v24 + 256LL))(
                        v24,
                        v28,
                        &Buf1,
                        &v23);
                if ( v14 )
                  break;
                if ( !memcmp_0(&Buf1, &BUGCHECK_DRIVER_DATA_GUID, 0x10u) )
                  goto LABEL_28;
              }
              LODWORD(v20) = v14;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x151,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                "CDumpProcessor::ParseLastBugCheckDriverName",
                v20,
                (int)"GetNextTagged finished",
                v22);
              v23 = 0;
LABEL_28:
              v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 264LL))(v24, v28);
              if ( v15 >= 0 )
              {
                if ( v23 )
                {
                  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                          &Source,
                                          ((unsigned __int64)v23 >> 1) + 1) )
                  {
                    v16 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, wchar_t *, unsigned int, unsigned int *))(*(_QWORD *)v24 + 240LL))(
                            v24,
                            &BUGCHECK_DRIVER_DATA_GUID,
                            0,
                            Source,
                            v23,
                            &v26);
                    if ( v16 >= 0 )
                    {
                      if ( v26 <= v23 )
                      {
                        v17 = wcsnlen(Source, v30 - Source);
                        if ( v17 > v30 - Source )
                          __int2c();
                        v30 = &Source[v17];
                        *v30 = 0;
                        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(
                          (char *)this + 8432,
                          &Source);
                      }
                      else
                      {
                        LODWORD(v21) = -2147467259;
                        wil::details::in1diag4::Log_HrMsg(
                          retaddr,
                          (void *)0x181,
                          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                          "CDumpProcessor::ParseLastBugCheckDriverName",
                          v21,
                          (int)"ReadTagged returned wrong information",
                          v22);
                      }
                    }
                    else
                    {
                      LODWORD(v21) = v16;
                      wil::details::in1diag4::Log_HrMsg(
                        retaddr,
                        (void *)0x17A,
                        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                        "CDumpProcessor::ParseLastBugCheckDriverName",
                        v21,
                        (int)"ReadTagged failed",
                        v22);
                    }
                  }
                  else
                  {
                    LODWORD(v20) = -2147024882;
                    wil::details::in1diag4::Log_HrMsg(
                      retaddr,
                      (void *)0x16E,
                      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                      "CDumpProcessor::ParseLastBugCheckDriverName",
                      v20,
                      (int)"Unable to allocate memory for BugCheckDriverName",
                      v22);
                  }
                }
              }
              else
              {
                LODWORD(v20) = v15;
                wil::details::in1diag4::Log_HrMsg(
                  retaddr,
                  (void *)0x162,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                  "CDumpProcessor::ParseLastBugCheckDriverName",
                  v20,
                  (int)"EndEnumTagged failed",
                  v22);
              }
            }
            else
            {
              LODWORD(v20) = v13;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x145,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                "CDumpProcessor::ParseLastBugCheckDriverName",
                v20,
                (int)"StartEnumTagged failed",
                v22);
            }
          }
          else
          {
            LODWORD(v20) = v11;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x13D,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
              "CDumpProcessor::ParseLastBugCheckDriverName",
              v20,
              (int)"QueryInterface failed for IDebugDataSpace4",
              v22);
          }
        }
        else
        {
          LODWORD(v20) = v9;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x132,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
            "CDumpProcessor::ParseLastBugCheckDriverName",
            v20,
            (int)"WaitForEvent failed",
            v22);
        }
      }
      else
      {
        LODWORD(v20) = v8;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x129,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
          "CDumpProcessor::ParseLastBugCheckDriverName",
          v20,
          (int)"OpenDumpFileWide failed for %ws",
          v3);
      }
    }
    else
    {
      LODWORD(v20) = v7;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
        "CDumpProcessor::ParseLastBugCheckDriverName",
        v20,
        (int)"QueryInterface failed for IDebugControl",
        v22);
    }
  }
LABEL_42:
  v18 = v24;
  v24 = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = v27;
  v27 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v25 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v25)[26])(v25, 0);
  if ( Source != v31 )
    operator delete(Source, (const struct std::nothrow_t *)&std::nothrow);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v25 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v25)[2])(v25);
  if ( Library )
    FreeLibrary(Library);
}

```

## disassembly

```asm
0x14003d270  push    rbp
0x14003d272  push    rbx
0x14003d273  push    rsi
0x14003d274  push    rdi
0x14003d275  push    r14
0x14003d277  push    r15
0x14003d279  lea     rbp, [rsp-2Fh]
0x14003d27e  sub     rsp, 0D8h
0x14003d285  mov     rax, cs:__security_cookie
0x14003d28c  xor     rax, rsp
0x14003d28f  mov     [rbp+57h+var_40], rax
0x14003d293  mov     r14, rcx
0x14003d296  xorps   xmm0, xmm0
0x14003d299  movups  [rbp+57h+Buf1], xmm0
0x14003d29d  xor     r15d, r15d
0x14003d2a0  mov     ebx, r15d
0x14003d2a3  mov     [rbp+57h+var_70], rbx
0x14003d2a7  mov     [rbp+57h+var_B0], r15
0x14003d2ab  mov     [rbp+57h+var_A0], r15
0x14003d2af  mov     [rbp+57h+var_B8], r15
0x14003d2b3  lea     rax, [rbp+57h+var_80]
0x14003d2b7  mov     [rbp+57h+Source], rax
0x14003d2bb  lea     rax, [rbp+57h+var_80]
0x14003d2bf  mov     [rbp+57h+var_88], rax
0x14003d2c3  mov     [rbp+57h+var_80], r15w
0x14003d2c8  mov     [rbp+57h+var_C0], r15d
0x14003d2cc  mov     [rbp+57h+var_A8], r15d
0x14003d2d0  mov     [rbp+57h+var_98], r15
0x14003d2d4  mov     rdi, [rcx+0B0h]
0x14003d2db  test    rdi, rdi
0x14003d2de  jz      loc_14003D6C8
0x14003d2e4  cmp     [rdi], r15w
0x14003d2e8  jz      loc_14003D6C8
0x14003d2ee  lea     rdx, a1; "1"
0x14003d2f5  lea     rcx, aDbgengNoBugche; "DBGENG_NO_BUGCHECK_ANALYSIS"
0x14003d2fc  call    cs:__imp_SetEnvironmentVariableW
0x14003d302  xor     edx, edx; hFile
0x14003d304  mov     r8d, 800h; dwFlags
0x14003d30a  lea     rcx, aDbgengDll; "dbgeng.dll"
0x14003d311  call    cs:__imp_LoadLibraryExW
0x14003d317  mov     rbx, rax
0x14003d31a  mov     [rbp+57h+var_70], rax
0x14003d31e  test    rax, rax
0x14003d321  jz      loc_14003D6AD
0x14003d327  mov     rcx, [rbp+57h+var_B0]
0x14003d32b  mov     [rbp+57h+var_B0], r15
0x14003d32f  test    rcx, rcx
0x14003d332  jz      short loc_14003D341
0x14003d334  mov     rax, [rcx]
0x14003d337  mov     rax, [rax+10h]
0x14003d33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d340  nop
0x14003d341  lea     rdx, aDebugcreateex; "DebugCreateEx"
0x14003d348  mov     rcx, rbx; hModule
0x14003d34b  call    cs:__imp_GetProcAddress
0x14003d351  test    rax, rax
0x14003d354  jnz     short loc_14003D36A
0x14003d356  call    cs:__imp_GetLastError
0x14003d35c  test    eax, eax
0x14003d35e  jle     short loc_14003D381
0x14003d360  movzx   eax, ax
0x14003d363  or      eax, 80070000h
0x14003d368  jmp     short loc_14003D37F
0x14003d36a  lea     r8, [rbp+57h+var_B0]
0x14003d36e  mov     edx, 0A8008h
0x14003d373  lea     rcx, _GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e
0x14003d37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d37f  test    eax, eax
0x14003d381  jns     short loc_14003D39D
0x14003d383  lea     rdx, aUtildebugcreat; "UtilDebugCreateEx failed for IDebugClie"...
0x14003d38a  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003d38f  mov     dword ptr [rsp+100h+var_E0], eax
0x14003d393  mov     edx, 116h
0x14003d398  jmp     loc_14003D6E1
0x14003d39d  mov     rdx, [rbp+57h+var_B0]
0x14003d3a1  lea     rcx, [rbp+57h+var_A0]
0x14003d3a5  call    ??$queryinterface_unique@UIDebugControl@@UIDebugClient4@@@tlx@@YAJPEAV?$unique_ptr@UIDebugControl@@Urelease_delete@tlx@@@utl@@AEAUIDebugClient4@@AEBU_GUID@@@Z; tlx::queryinterface_unique<IDebugControl,IDebugClient4>(utl::unique_ptr<IDebugControl,tlx::release_delete> *,IDebugClient4 &,_GUID const &)
0x14003d3aa  test    eax, eax
0x14003d3ac  jns     short loc_14003D3C8
0x14003d3ae  lea     rdx, aQueryinterface_1; "QueryInterface failed for IDebugControl"
0x14003d3b5  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003d3ba  mov     dword ptr [rsp+100h+var_E0], eax
0x14003d3be  mov     edx, 121h
0x14003d3c3  jmp     loc_14003D6E1
0x14003d3c8  mov     rcx, [rbp+57h+var_B0]
0x14003d3cc  mov     rax, [rcx]
0x14003d3cf  xor     r8d, r8d
0x14003d3d2  mov     rdx, rdi
0x14003d3d5  mov     rax, [rax+1E0h]
0x14003d3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d3e1  test    eax, eax
0x14003d3e3  jns     short loc_14003D41B
0x14003d3e5  mov     rcx, [rbp+5Fh]; this
0x14003d3e9  mov     [rsp+100h+var_D0], rdi; char *
0x14003d3ee  lea     rdx, aOpendumpfilewi; "OpenDumpFileWide failed for %ws"
0x14003d3f5  mov     qword ptr [rsp+100h+var_D8], rdx; int
0x14003d3fa  mov     dword ptr [rsp+100h+var_E0], eax; wil::details *
0x14003d3fe  lea     r9, aCdumpprocessor_7; "CDumpProcessor::ParseLastBugCheckDriver"...
0x14003d405  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003d40c  mov     edx, 129h; void *
0x14003d411  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d416  jmp     loc_14003D6F9
0x14003d41b  mov     rcx, [rbp+57h+var_A0]
0x14003d41f  mov     rax, [rcx]
0x14003d422  or      r8d, 0FFFFFFFFh
0x14003d426  xor     edx, edx
0x14003d428  mov     rax, [rax+2E8h]
0x14003d42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d434  test    eax, eax
0x14003d436  jns     short loc_14003D452
0x14003d438  lea     rdx, aWaitforeventFa; "WaitForEvent failed"
0x14003d43f  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003d444  mov     dword ptr [rsp+100h+var_E0], eax
0x14003d448  mov     edx, 132h
0x14003d44d  jmp     loc_14003D6E1
0x14003d452  mov     rdi, [rbp+57h+var_B0]
0x14003d456  mov     rax, [rdi]
0x14003d459  mov     rsi, [rax]
0x14003d45c  mov     [rbp+57h+var_68], r15
0x14003d460  lea     rax, [rbp+57h+var_B8]
0x14003d464  mov     [rbp+57h+var_60], rax
0x14003d468  mov     rcx, [rbp+57h+var_B8]
0x14003d46c  mov     [rbp+57h+var_B8], r15
0x14003d470  test    rcx, rcx
0x14003d473  jz      short loc_14003D482
0x14003d475  mov     rax, [rcx]
0x14003d478  mov     rax, [rax+10h]
0x14003d47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d481  nop
0x14003d482  lea     r8, [rbp+57h+var_68]
0x14003d486  lea     rdx, _GUID_d98ada1f_29e9_4ef5_a6c0_e53349883212
0x14003d48d  mov     rcx, rdi
0x14003d490  mov     rax, rsi
0x14003d493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d498  mov     edi, eax
0x14003d49a  mov     rax, [rbp+57h+var_68]
0x14003d49e  test    rax, rax
0x14003d4a1  jz      short loc_14003D4BF
0x14003d4a3  mov     rdx, [rbp+57h+var_60]
0x14003d4a7  mov     rcx, [rdx]
0x14003d4aa  mov     [rdx], rax
0x14003d4ad  test    rcx, rcx
0x14003d4b0  jz      short loc_14003D4BF
0x14003d4b2  mov     rax, [rcx]
0x14003d4b5  mov     rax, [rax+10h]
0x14003d4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d4be  nop
0x14003d4bf  test    edi, edi
0x14003d4c1  jns     short loc_14003D4DD
0x14003d4c3  lea     rax, aQueryinterface_0; "QueryInterface failed for IDebugDataSpa"...
0x14003d4ca  mov     qword ptr [rsp+100h+var_D8], rax
0x14003d4cf  mov     dword ptr [rsp+100h+var_E0], edi
0x14003d4d3  mov     edx, 13Dh
0x14003d4d8  jmp     loc_14003D6E1
0x14003d4dd  mov     rcx, [rbp+57h+var_B8]
0x14003d4e1  mov     rax, [rcx]
0x14003d4e4  lea     rdx, [rbp+57h+var_98]
0x14003d4e8  mov     rax, [rax+0F8h]
0x14003d4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d4f4  test    eax, eax
0x14003d4f6  jns     short loc_14003D512
0x14003d4f8  lea     rdx, aStartenumtagge; "StartEnumTagged failed"
0x14003d4ff  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003d504  mov     dword ptr [rsp+100h+var_E0], eax
0x14003d508  mov     edx, 145h
0x14003d50d  jmp     loc_14003D6E1
0x14003d512  mov     rcx, [rbp+57h+var_B8]
0x14003d516  mov     rax, [rcx]
0x14003d519  lea     r9, [rbp+57h+var_C0]
0x14003d51d  lea     r8, [rbp+57h+Buf1]
0x14003d521  mov     rdx, [rbp+57h+var_98]
0x14003d525  mov     rax, [rax+100h]
0x14003d52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d531  test    eax, eax
0x14003d533  jnz     short loc_14003D54F
0x14003d535  lea     r8d, [rax+10h]; Size
0x14003d539  lea     rdx, BUGCHECK_DRIVER_DATA_GUID; Buf2
0x14003d540  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14003d544  call    memcmp_0
0x14003d549  test    eax, eax
0x14003d54b  jnz     short loc_14003D512
0x14003d54d  jmp     short loc_14003D57F
0x14003d54f  mov     rcx, [rbp+5Fh]; this
0x14003d553  lea     rdx, aGetnexttaggedF; "GetNextTagged finished"
0x14003d55a  mov     qword ptr [rsp+100h+var_D8], rdx; int
0x14003d55f  mov     dword ptr [rsp+100h+var_E0], eax; wil::details *
0x14003d563  lea     r9, aCdumpprocessor_7; "CDumpProcessor::ParseLastBugCheckDriver"...
0x14003d56a  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003d571  mov     edx, 151h; void *
0x14003d576  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d57b  mov     [rbp+57h+var_C0], r15d
0x14003d57f  mov     rcx, [rbp+57h+var_B8]
0x14003d583  mov     rax, [rcx]
0x14003d586  mov     rdx, [rbp+57h+var_98]
0x14003d58a  mov     rax, [rax+108h]
0x14003d591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d596  test    eax, eax
0x14003d598  jns     short loc_14003D5B4
0x14003d59a  lea     rdx, aEndenumtaggedF; "EndEnumTagged failed"
0x14003d5a1  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003d5a6  mov     dword ptr [rsp+100h+var_E0], eax
0x14003d5aa  mov     edx, 162h
0x14003d5af  jmp     loc_14003D6E1
0x14003d5b4  mov     eax, [rbp+57h+var_C0]
0x14003d5b7  test    eax, eax
0x14003d5b9  jz      loc_14003D6F9
0x14003d5bf  mov     edx, eax
0x14003d5c1  shr     rdx, 1
0x14003d5c4  inc     rdx
0x14003d5c7  lea     rcx, [rbp+57h+Source]
0x14003d5cb  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14003d5d0  test    al, al
0x14003d5d2  jnz     short loc_14003D5F2
0x14003d5d4  lea     rax, aUnableToAlloca; "Unable to allocate memory for BugCheckD"...
0x14003d5db  mov     qword ptr [rsp+100h+var_D8], rax
0x14003d5e0  mov     dword ptr [rsp+100h+var_E0], 8007000Eh
0x14003d5e8  mov     edx, 16Eh
0x14003d5ed  jmp     loc_14003D6E1
0x14003d5f2  mov     rcx, [rbp+57h+var_B8]
0x14003d5f6  mov     r8d, [rbp+57h+var_C0]
0x14003d5fa  mov     rax, [rcx]
0x14003d5fd  lea     r9, [rbp+57h+var_A8]
0x14003d601  mov     qword ptr [rsp+100h+var_D8], r9
0x14003d606  mov     dword ptr [rsp+100h+var_E0], r8d
0x14003d60b  mov     r9, [rbp+57h+Source]
0x14003d60f  xor     r8d, r8d
0x14003d612  lea     rdx, BUGCHECK_DRIVER_DATA_GUID
0x14003d619  mov     rax, [rax+0F0h]
0x14003d620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d625  test    eax, eax
0x14003d627  jns     short loc_14003D643
0x14003d629  lea     rdx, aReadtaggedFail; "ReadTagged failed"
0x14003d630  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003d635  mov     dword ptr [rsp+100h+var_E0], eax
0x14003d639  mov     edx, 17Ah
0x14003d63e  jmp     loc_14003D6E1
0x14003d643  mov     eax, [rbp+57h+var_C0]
0x14003d646  cmp     [rbp+57h+var_A8], eax
0x14003d649  jbe     short loc_14003D666
0x14003d64b  lea     rax, aReadtaggedRetu; "ReadTagged returned wrong information"
0x14003d652  mov     qword ptr [rsp+100h+var_D8], rax
0x14003d657  mov     dword ptr [rsp+100h+var_E0], 80004005h
0x14003d65f  mov     edx, 181h
0x14003d664  jmp     short loc_14003D6E1
0x14003d666  mov     rcx, [rbp+57h+Source]; Source
0x14003d66a  mov     rdx, [rbp+57h+var_88]
0x14003d66e  sub     rdx, rcx
0x14003d671  sar     rdx, 1; MaxCount
0x14003d674  call    cs:__imp_wcsnlen
0x14003d67a  mov     rcx, [rbp+57h+var_88]
0x14003d67e  mov     rdx, [rbp+57h+Source]
0x14003d682  sub     rcx, rdx
0x14003d685  sar     rcx, 1
0x14003d688  cmp     rax, rcx
0x14003d68b  jbe     short loc_14003D68F
0x14003d68d  int     2Ch; Windows NT - assertion failure
0x14003d68f  lea     rcx, [rdx+rax*2]
0x14003d693  mov     [rbp+57h+var_88], rcx
0x14003d697  mov     [rcx], r15w
0x14003d69b  lea     rcx, [r14+20F0h]
0x14003d6a2  lea     rdx, [rbp+57h+Source]
0x14003d6a6  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14003d6ab  jmp     short loc_14003D6F9
0x14003d6ad  lea     rax, aUtilloaddbgeng; "UtilLoadDbgEng failed"
0x14003d6b4  mov     qword ptr [rsp+100h+var_D8], rax
0x14003d6b9  mov     dword ptr [rsp+100h+var_E0], 8007007Eh
0x14003d6c1  mov     edx, 104h
0x14003d6c6  jmp     short loc_14003D6E1
0x14003d6c8  lea     rax, aNoDumpFileToGe; "No dump file to get header from"
0x14003d6cf  mov     qword ptr [rsp+100h+var_D8], rax; int
0x14003d6d4  mov     dword ptr [rsp+100h+var_E0], 80070002h; wil::details *
0x14003d6dc  mov     edx, 0F2h; void *
0x14003d6e1  lea     r9, aCdumpprocessor_7; "CDumpProcessor::ParseLastBugCheckDriver"...
0x14003d6e8  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003d6ef  mov     rcx, [rbp+5Fh]; this
0x14003d6f3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d6f8  nop
0x14003d6f9  mov     rcx, [rbp+57h+var_B8]
0x14003d6fd  mov     [rbp+57h+var_B8], r15
0x14003d701  test    rcx, rcx
0x14003d704  jz      short loc_14003D713
0x14003d706  mov     rax, [rcx]
0x14003d709  mov     rax, [rax+10h]
0x14003d70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d712  nop
0x14003d713  mov     rcx, [rbp+57h+var_A0]
0x14003d717  mov     [rbp+57h+var_A0], r15
0x14003d71b  test    rcx, rcx
0x14003d71e  jz      short loc_14003D72D
0x14003d720  mov     rax, [rcx]
0x14003d723  mov     rax, [rax+10h]
0x14003d727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d72c  nop
0x14003d72d  mov     rcx, [rbp+57h+var_B0]
0x14003d731  test    rcx, rcx
0x14003d734  jz      short loc_14003D748
0x14003d736  mov     rax, [rcx]
0x14003d739  xor     edx, edx
0x14003d73b  mov     rax, [rax+0D0h]
0x14003d742  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```

# CDumpProcessor::ParseLastBugCheckDriverName(void)

- ea: `0x14003fc70`
- end: `0x1400401f6`
- name: `?ParseLastBugCheckDriverName@CDumpProcessor@@AEAAXXZ`
- size: `1414`
- prototype: `void __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1400401fc`

## callees

- `0x140002490`
- `0x140002748`
- `0x14000cf48`
- `0x14000e9d4`
- `0x1400372dc`
- `0x14003e500`
- `0x14003fc70`
- `0x14005f57c`
- `0x140061010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004008f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004008f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400401cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400401cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003fd57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003fd57`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003fd17`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003fd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fd68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fd68`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003fcfc`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003fcfc`

## string_xrefs

- `0x14003fd9b`: `UtilDebugCreateEx failed for IDebugClient4`
- `0x14003fe06`: `OpenDumpFileWide failed for %ws`
- `0x140040041`: `ReadTagged failed`
- `0x140040063`: `ReadTagged returned wrong information`
- `0x14003fd4d`: `DebugCreateEx`
- `0x14003fd10`: `dbgeng.dll`

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
      (void *)0xEE,
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
      (void *)0x100,
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
      (void *)0x112,
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
                if ( !memcmp_0(&Buf1, BUGCHECK_DRIVER_DATA_GUID, 0x10u) )
                  goto LABEL_28;
              }
              LODWORD(v20) = v14;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x14D,
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
                    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, wchar_t *, unsigned int, unsigned int *))(*(_QWORD *)v24 + 240LL))(
                            v24,
                            BUGCHECK_DRIVER_DATA_GUID,
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
                          (void *)0x17D,
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
                        (void *)0x176,
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
                      (void *)0x16A,
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
                  (void *)0x15E,
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
                (void *)0x141,
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
              (void *)0x139,
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
            (void *)0x12E,
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
          (void *)0x125,
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
        (void *)0x11D,
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
0x14003fc70  push    rbp
0x14003fc72  push    rbx
0x14003fc73  push    rsi
0x14003fc74  push    rdi
0x14003fc75  push    r14
0x14003fc77  push    r15
0x14003fc79  lea     rbp, [rsp-2Fh]
0x14003fc7e  sub     rsp, 0D8h
0x14003fc85  mov     rax, cs:__security_cookie
0x14003fc8c  xor     rax, rsp
0x14003fc8f  mov     [rbp+57h+var_40], rax
0x14003fc93  mov     r14, rcx
0x14003fc96  xorps   xmm0, xmm0
0x14003fc99  movups  [rbp+57h+Buf1], xmm0
0x14003fc9d  xor     r15d, r15d
0x14003fca0  mov     ebx, r15d
0x14003fca3  mov     [rbp+57h+var_70], rbx
0x14003fca7  mov     [rbp+57h+var_B0], r15
0x14003fcab  mov     [rbp+57h+var_A0], r15
0x14003fcaf  mov     [rbp+57h+var_B8], r15
0x14003fcb3  lea     rax, [rbp+57h+var_80]
0x14003fcb7  mov     [rbp+57h+Source], rax
0x14003fcbb  lea     rax, [rbp+57h+var_80]
0x14003fcbf  mov     [rbp+57h+var_88], rax
0x14003fcc3  mov     [rbp+57h+var_80], r15w
0x14003fcc8  mov     [rbp+57h+var_C0], r15d
0x14003fccc  mov     [rbp+57h+var_A8], r15d
0x14003fcd0  mov     [rbp+57h+var_98], r15
0x14003fcd4  mov     rdi, [rcx+0B0h]
0x14003fcdb  test    rdi, rdi
0x14003fcde  jz      loc_1400400E9
0x14003fce4  cmp     [rdi], r15w
0x14003fce8  jz      loc_1400400E9
0x14003fcee  lea     rdx, a1; "1"
0x14003fcf5  lea     rcx, aDbgengNoBugche; "DBGENG_NO_BUGCHECK_ANALYSIS"
0x14003fcfc  call    cs:__imp_SetEnvironmentVariableW
0x14003fd03  nop     dword ptr [rax+rax+00h]
0x14003fd08  xor     edx, edx; hFile
0x14003fd0a  mov     r8d, 800h; dwFlags
0x14003fd10  lea     rcx, aDbgengDll; "dbgeng.dll"
0x14003fd17  call    cs:__imp_LoadLibraryExW
0x14003fd1e  nop     dword ptr [rax+rax+00h]
0x14003fd23  mov     rbx, rax
0x14003fd26  mov     [rbp+57h+var_70], rax
0x14003fd2a  test    rax, rax
0x14003fd2d  jz      loc_1400400CE
0x14003fd33  mov     rcx, [rbp+57h+var_B0]
0x14003fd37  mov     [rbp+57h+var_B0], r15
0x14003fd3b  test    rcx, rcx
0x14003fd3e  jz      short loc_14003FD4D
0x14003fd40  mov     rax, [rcx]
0x14003fd43  mov     rax, [rax+10h]
0x14003fd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fd4c  nop
0x14003fd4d  lea     rdx, aDebugcreateex; "DebugCreateEx"
0x14003fd54  mov     rcx, rbx; hModule
0x14003fd57  call    cs:__imp_GetProcAddress
0x14003fd5e  nop     dword ptr [rax+rax+00h]
0x14003fd63  test    rax, rax
0x14003fd66  jnz     short loc_14003FD82
0x14003fd68  call    cs:__imp_GetLastError
0x14003fd6f  nop     dword ptr [rax+rax+00h]
0x14003fd74  test    eax, eax
0x14003fd76  jle     short loc_14003FD99
0x14003fd78  movzx   eax, ax
0x14003fd7b  or      eax, 80070000h
0x14003fd80  jmp     short loc_14003FD97
0x14003fd82  lea     r8, [rbp+57h+var_B0]
0x14003fd86  mov     edx, 0A8008h
0x14003fd8b  lea     rcx, _GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e
0x14003fd92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fd97  test    eax, eax
0x14003fd99  jns     short loc_14003FDB5
0x14003fd9b  lea     rdx, aUtildebugcreat; "UtilDebugCreateEx failed for IDebugClie"...
0x14003fda2  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003fda7  mov     dword ptr [rsp+100h+var_E0], eax
0x14003fdab  mov     edx, 112h
0x14003fdb0  jmp     loc_140040102
0x14003fdb5  mov     rdx, [rbp+57h+var_B0]
0x14003fdb9  lea     rcx, [rbp+57h+var_A0]
0x14003fdbd  call    ??$queryinterface_unique@UIDebugControl@@UIDebugClient4@@@tlx@@YAJPEAV?$unique_ptr@UIDebugControl@@Urelease_delete@tlx@@@utl@@AEAUIDebugClient4@@AEBU_GUID@@@Z; tlx::queryinterface_unique<IDebugControl,IDebugClient4>(utl::unique_ptr<IDebugControl,tlx::release_delete> *,IDebugClient4 &,_GUID const &)
0x14003fdc2  test    eax, eax
0x14003fdc4  jns     short loc_14003FDE0
0x14003fdc6  lea     rdx, aQueryinterface_1; "QueryInterface failed for IDebugControl"
0x14003fdcd  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003fdd2  mov     dword ptr [rsp+100h+var_E0], eax
0x14003fdd6  mov     edx, 11Dh
0x14003fddb  jmp     loc_140040102
0x14003fde0  mov     rcx, [rbp+57h+var_B0]
0x14003fde4  mov     rax, [rcx]
0x14003fde7  xor     r8d, r8d
0x14003fdea  mov     rdx, rdi
0x14003fded  mov     rax, [rax+1E0h]
0x14003fdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fdf9  test    eax, eax
0x14003fdfb  jns     short loc_14003FE33
0x14003fdfd  mov     rcx, [rbp+5Fh]; this
0x14003fe01  mov     [rsp+100h+var_D0], rdi; char *
0x14003fe06  lea     rdx, aOpendumpfilewi; "OpenDumpFileWide failed for %ws"
0x14003fe0d  mov     qword ptr [rsp+100h+var_D8], rdx; int
0x14003fe12  mov     dword ptr [rsp+100h+var_E0], eax; wil::details *
0x14003fe16  lea     r9, aCdumpprocessor_7; "CDumpProcessor::ParseLastBugCheckDriver"...
0x14003fe1d  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003fe24  mov     edx, 125h; void *
0x14003fe29  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003fe2e  jmp     loc_14004011A
0x14003fe33  mov     rcx, [rbp+57h+var_A0]
0x14003fe37  mov     rax, [rcx]
0x14003fe3a  or      r8d, 0FFFFFFFFh
0x14003fe3e  xor     edx, edx
0x14003fe40  mov     rax, [rax+2E8h]
0x14003fe47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fe4c  test    eax, eax
0x14003fe4e  jns     short loc_14003FE6A
0x14003fe50  lea     rdx, aWaitforeventFa; "WaitForEvent failed"
0x14003fe57  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003fe5c  mov     dword ptr [rsp+100h+var_E0], eax
0x14003fe60  mov     edx, 12Eh
0x14003fe65  jmp     loc_140040102
0x14003fe6a  mov     rdi, [rbp+57h+var_B0]
0x14003fe6e  mov     rax, [rdi]
0x14003fe71  mov     rsi, [rax]
0x14003fe74  mov     [rbp+57h+var_68], r15
0x14003fe78  lea     rax, [rbp+57h+var_B8]
0x14003fe7c  mov     [rbp+57h+var_60], rax
0x14003fe80  mov     rcx, [rbp+57h+var_B8]
0x14003fe84  mov     [rbp+57h+var_B8], r15
0x14003fe88  test    rcx, rcx
0x14003fe8b  jz      short loc_14003FE9A
0x14003fe8d  mov     rax, [rcx]
0x14003fe90  mov     rax, [rax+10h]
0x14003fe94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fe99  nop
0x14003fe9a  lea     r8, [rbp+57h+var_68]
0x14003fe9e  lea     rdx, _GUID_d98ada1f_29e9_4ef5_a6c0_e53349883212
0x14003fea5  mov     rcx, rdi
0x14003fea8  mov     rax, rsi
0x14003feab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003feb0  mov     edi, eax
0x14003feb2  mov     rax, [rbp+57h+var_68]
0x14003feb6  test    rax, rax
0x14003feb9  jz      short loc_14003FED7
0x14003febb  mov     rdx, [rbp+57h+var_60]
0x14003febf  mov     rcx, [rdx]
0x14003fec2  mov     [rdx], rax
0x14003fec5  test    rcx, rcx
0x14003fec8  jz      short loc_14003FED7
0x14003feca  mov     rax, [rcx]
0x14003fecd  mov     rax, [rax+10h]
0x14003fed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fed6  nop
0x14003fed7  test    edi, edi
0x14003fed9  jns     short loc_14003FEF5
0x14003fedb  lea     rax, aQueryinterface_0; "QueryInterface failed for IDebugDataSpa"...
0x14003fee2  mov     qword ptr [rsp+100h+var_D8], rax
0x14003fee7  mov     dword ptr [rsp+100h+var_E0], edi
0x14003feeb  mov     edx, 139h
0x14003fef0  jmp     loc_140040102
0x14003fef5  mov     rcx, [rbp+57h+var_B8]
0x14003fef9  mov     rax, [rcx]
0x14003fefc  lea     rdx, [rbp+57h+var_98]
0x14003ff00  mov     rax, [rax+0F8h]
0x14003ff07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ff0c  test    eax, eax
0x14003ff0e  jns     short loc_14003FF2A
0x14003ff10  lea     rdx, aStartenumtagge; "StartEnumTagged failed"
0x14003ff17  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003ff1c  mov     dword ptr [rsp+100h+var_E0], eax
0x14003ff20  mov     edx, 141h
0x14003ff25  jmp     loc_140040102
0x14003ff2a  mov     rcx, [rbp+57h+var_B8]
0x14003ff2e  mov     rax, [rcx]
0x14003ff31  lea     r9, [rbp+57h+var_C0]
0x14003ff35  lea     r8, [rbp+57h+Buf1]
0x14003ff39  mov     rdx, [rbp+57h+var_98]
0x14003ff3d  mov     rax, [rax+100h]
0x14003ff44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ff49  test    eax, eax
0x14003ff4b  jnz     short loc_14003FF67
0x14003ff4d  lea     r8d, [rax+10h]; Size
0x14003ff51  lea     rdx, BUGCHECK_DRIVER_DATA_GUID; Buf2
0x14003ff58  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14003ff5c  call    memcmp_0
0x14003ff61  test    eax, eax
0x14003ff63  jnz     short loc_14003FF2A
0x14003ff65  jmp     short loc_14003FF97
0x14003ff67  mov     rcx, [rbp+5Fh]; this
0x14003ff6b  lea     rdx, aGetnexttaggedF; "GetNextTagged finished"
0x14003ff72  mov     qword ptr [rsp+100h+var_D8], rdx; int
0x14003ff77  mov     dword ptr [rsp+100h+var_E0], eax; wil::details *
0x14003ff7b  lea     r9, aCdumpprocessor_7; "CDumpProcessor::ParseLastBugCheckDriver"...
0x14003ff82  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ff89  mov     edx, 14Dh; void *
0x14003ff8e  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ff93  mov     [rbp+57h+var_C0], r15d
0x14003ff97  mov     rcx, [rbp+57h+var_B8]
0x14003ff9b  mov     rax, [rcx]
0x14003ff9e  mov     rdx, [rbp+57h+var_98]
0x14003ffa2  mov     rax, [rax+108h]
0x14003ffa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ffae  test    eax, eax
0x14003ffb0  jns     short loc_14003FFCC
0x14003ffb2  lea     rdx, aEndenumtaggedF; "EndEnumTagged failed"
0x14003ffb9  mov     qword ptr [rsp+100h+var_D8], rdx
0x14003ffbe  mov     dword ptr [rsp+100h+var_E0], eax
0x14003ffc2  mov     edx, 15Eh
0x14003ffc7  jmp     loc_140040102
0x14003ffcc  mov     eax, [rbp+57h+var_C0]
0x14003ffcf  test    eax, eax
0x14003ffd1  jz      loc_14004011A
0x14003ffd7  mov     edx, eax
0x14003ffd9  shr     rdx, 1
0x14003ffdc  inc     rdx
0x14003ffdf  lea     rcx, [rbp+57h+Source]
0x14003ffe3  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14003ffe8  test    al, al
0x14003ffea  jnz     short loc_14004000A
0x14003ffec  lea     rax, aUnableToAlloca; "Unable to allocate memory for BugCheckD"...
0x14003fff3  mov     qword ptr [rsp+100h+var_D8], rax
0x14003fff8  mov     dword ptr [rsp+100h+var_E0], 8007000Eh
0x140040000  mov     edx, 16Ah
0x140040005  jmp     loc_140040102
0x14004000a  mov     rcx, [rbp+57h+var_B8]
0x14004000e  mov     r8d, [rbp+57h+var_C0]
0x140040012  mov     rax, [rcx]
0x140040015  lea     r9, [rbp+57h+var_A8]
0x140040019  mov     qword ptr [rsp+100h+var_D8], r9
0x14004001e  mov     dword ptr [rsp+100h+var_E0], r8d
0x140040023  mov     r9, [rbp+57h+Source]
0x140040027  xor     r8d, r8d
0x14004002a  lea     rdx, BUGCHECK_DRIVER_DATA_GUID
0x140040031  mov     rax, [rax+0F0h]
0x140040038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004003d  test    eax, eax
0x14004003f  jns     short loc_14004005B
0x140040041  lea     rdx, aReadtaggedFail; "ReadTagged failed"
0x140040048  mov     qword ptr [rsp+100h+var_D8], rdx
0x14004004d  mov     dword ptr [rsp+100h+var_E0], eax
0x140040051  mov     edx, 176h
0x140040056  jmp     loc_140040102
0x14004005b  mov     eax, [rbp+57h+var_C0]
0x14004005e  cmp     [rbp+57h+var_A8], eax
0x140040061  jbe     short loc_140040081
0x140040063  lea     rax, aReadtaggedRetu; "ReadTagged returned wrong information"
0x14004006a  mov     qword ptr [rsp+100h+var_D8], rax
0x14004006f  mov     dword ptr [rsp+100h+var_E0], 80004005h
0x140040077  mov     edx, 17Dh
0x14004007c  jmp     loc_140040102
0x140040081  mov     rcx, [rbp+57h+Source]; Source
0x140040085  mov     rdx, [rbp+57h+var_88]
0x140040089  sub     rdx, rcx
0x14004008c  sar     rdx, 1; MaxCount
0x14004008f  call    cs:__imp_wcsnlen
0x140040096  nop     dword ptr [rax+rax+00h]
0x14004009b  mov     rcx, [rbp+57h+var_88]
0x14004009f  mov     rdx, [rbp+57h+Source]
0x1400400a3  sub     rcx, rdx
0x1400400a6  sar     rcx, 1
0x1400400a9  cmp     rax, rcx
0x1400400ac  jbe     short loc_1400400B0
0x1400400ae  int     2Ch; Windows NT - assertion failure
0x1400400b0  lea     rcx, [rdx+rax*2]
0x1400400b4  mov     [rbp+57h+var_88], rcx
0x1400400b8  mov     [rcx], r15w
0x1400400bc  lea     rcx, [r14+20F0h]
0x1400400c3  lea     rdx, [rbp+57h+Source]
0x1400400c7  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1400400cc  jmp     short loc_14004011A
0x1400400ce  lea     rax, aUtilloaddbgeng; "UtilLoadDbgEng failed"
0x1400400d5  mov     qword ptr [rsp+100h+var_D8], rax
0x1400400da  mov     dword ptr [rsp+100h+var_E0], 8007007Eh
0x1400400e2  mov     edx, 100h
0x1400400e7  jmp     short loc_140040102
0x1400400e9  lea     rax, aNoDumpFileToGe; "No dump file to get header from"
0x1400400f0  mov     qword ptr [rsp+100h+var_D8], rax; int
0x1400400f5  mov     dword ptr [rsp+100h+var_E0], 80070002h; wil::details *
0x1400400fd  mov     edx, 0EEh; void *
0x140040102  lea     r9, aCdumpprocessor_7; "CDumpProcessor::ParseLastBugCheckDriver"...
0x140040109  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x140040110  mov     rcx, [rbp+5Fh]; this
0x140040114  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140040119  nop
0x14004011a  mov     rcx, [rbp+57h+var_B8]
0x14004011e  mov     [rbp+57h+var_B8], r15
0x140040122  test    rcx, rcx
0x140040125  jz      short loc_140040134
0x140040127  mov     rax, [rcx]
0x14004012a  mov     rax, [rax+10h]
0x14004012e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040133  nop
0x140040134  mov     rcx, [rbp+57h+var_A0]
0x140040138  mov     [rbp+57h+var_A0], r15
0x14004013c  test    rcx, rcx
0x14004013f  jz      short loc_14004014E
0x140040141  mov     rax, [rcx]
0x140040144  mov     rax, [rax+10h]
0x140040148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004014d  nop
0x14004014e  mov     rcx, [rbp+57h+var_B0]
0x140040152  test    rcx, rcx
  ... truncated ...
```

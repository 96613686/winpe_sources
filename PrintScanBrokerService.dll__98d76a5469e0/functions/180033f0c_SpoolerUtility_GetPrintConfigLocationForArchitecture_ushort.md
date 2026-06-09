# SpoolerUtility::_GetPrintConfigLocationForArchitecture(ushort)

- ea: `0x180033f0c`
- end: `0x180034185`
- name: `?_GetPrintConfigLocationForArchitecture@SpoolerUtility@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `633`
- prototype: `const WCHAR *__fastcall(const WCHAR *lpNewFileName, unsigned __int16)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033d00`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x180006b48`
- `0x18000f8a8`
- `0x18000f97c`
- `0x180012498`
- `0x18001d020`
- `0x1800273f0`
- `0x18002b28c`
- `0x180032e6c`
- `0x180032ecc`
- `0x180033f0c`
- `0x18003418c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180033f64`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180033f64`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800340d5`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800340d5`

## string_xrefs

- `0x180033f76`: `GetSystemWindowsDirectory failed!`
- `0x18003402b`: `\System32\`
- `0x18003410a`: `\system32\spool\drivers\x64\3\PrintConfig.dll`
- `0x180034113`: `\system32\spool\drivers\W32X86\3\PrintConfig.dll`
- `0x180033ff7`: `PrintConfig.dll`
- `0x180034040`: `PrintConfig.dll`
- `0x180034081`: `PrintConfig.dll`
- `0x180033f86`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x1800340f7`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180034173`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x1800340e7`: `CopyFile failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const WCHAR *__fastcall SpoolerUtility::_GetPrintConfigLocationForArchitecture(
        const WCHAR *lpNewFileName,
        unsigned __int16 a2)
{
  int v2; // ebx
  UINT SystemWindowsDirectoryW; // eax
  __int64 v5; // rax
  __int64 v6; // rax
  _BYTE *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  const WCHAR *v12; // rdx
  const WCHAR *v13; // rcx
  BOOL v14; // eax
  const wchar_t *v15; // rdx
  unsigned int v17; // eax
  const char *v18; // [rsp+28h] [rbp-D8h]
  const char *v19; // [rsp+28h] [rbp-D8h]
  _BYTE v20[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v2 = a2;
  memset_0(Buffer, 0, 0x208u);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xD6,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)(SystemWindowsDirectoryW == 0),
    (bool)"GetSystemWindowsDirectory failed!",
    v18);
  SpoolerUtility::_GetPrintConfigPackagePath(lpExistingFileName, (unsigned __int16)v2);
  std::wstring::wstring(lpNewFileName, Buffer);
  switch ( v2 )
  {
    case 0:
      v15 = L"\\system32\\spool\\drivers\\W32X86\\3\\PrintConfig.dll";
      goto LABEL_18;
    case 9:
      v15 = L"\\system32\\spool\\drivers\\x64\\3\\PrintConfig.dll";
LABEL_18:
      std::wstring::append(lpNewFileName, v15);
      goto LABEL_19;
    case 10:
      v10 = std::operator+<unsigned short>(v20, lpNewFileName, L"\\SysWOW64\\");
      v11 = std::operator+<unsigned short>(v21, v10, L"PrintConfig.dll");
      std::wstring::operator=(lpNewFileName, v11);
      std::wstring::_Tidy_deallocate(v21);
      break;
    case 12:
      v8 = std::operator+<unsigned short>(v20, lpNewFileName, L"\\System32\\");
      v9 = std::operator+<unsigned short>(v21, v8, L"PrintConfig.dll");
      std::wstring::operator=(lpNewFileName, v9);
      std::wstring::_Tidy_deallocate(v21);
      break;
    case 13:
      v5 = std::operator+<unsigned short>(v21, lpNewFileName, L"\\SysArm32\\");
      v6 = std::operator+<unsigned short>(v20, v5, L"PrintConfig.dll");
      std::wstring::operator=(lpNewFileName, v6);
      std::wstring::_Tidy_deallocate(v20);
      v7 = v21;
      goto LABEL_10;
    default:
      v17 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
        (const char *)v17,
        (int)"Invalid architecture!",
        v19);
  }
  v7 = v20;
LABEL_10:
  std::wstring::_Tidy_deallocate(v7);
  if ( *((_QWORD *)lpNewFileName + 3) <= 7u )
    v12 = lpNewFileName;
  else
    v12 = *(const WCHAR **)lpNewFileName;
  v13 = (const WCHAR *)lpExistingFileName;
  if ( lpExistingFileName[3] > (LPCWSTR)7 )
    v13 = lpExistingFileName[0];
  v14 = CopyFileW(v13, v12, 0);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xF9,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)!v14,
    (bool)"CopyFile failed!",
    v19);
LABEL_19:
  std::wstring::_Tidy_deallocate(lpExistingFileName);
  return lpNewFileName;
}

```

## disassembly

```asm
0x180033f0c  mov     [rsp-8+arg_8], rbx
0x180033f11  mov     [rsp-8+arg_10], rdi
0x180033f16  push    rbp
0x180033f17  lea     rbp, [rsp-1C0h]
0x180033f1f  sub     rsp, 2C0h
0x180033f26  mov     rax, cs:__security_cookie
0x180033f2d  xor     rax, rsp
0x180033f30  mov     [rbp+1C0h+var_10], rax
0x180033f37  movzx   ebx, dx
0x180033f3a  mov     rdi, rcx
0x180033f3d  mov     [rsp+2C0h+var_288], rcx
0x180033f42  mov     [rsp+2C0h+var_290], 0
0x180033f4a  xor     edx, edx; Val
0x180033f4c  mov     r8d, 208h; Size
0x180033f52  lea     rcx, [rbp+1C0h+Buffer]; void *
0x180033f56  call    memset_0
0x180033f5b  mov     edx, 104h; uSize
0x180033f60  lea     rcx, [rbp+1C0h+Buffer]; lpBuffer
0x180033f64  call    cs:__imp_GetSystemWindowsDirectoryW
0x180033f6a  test    eax, eax
0x180033f6c  setz    al
0x180033f6f  mov     rcx, [rbp+1C8h]; this
0x180033f76  lea     rdx, aGetsystemwindo; "GetSystemWindowsDirectory failed!"
0x180033f7d  mov     qword ptr [rsp+2C0h+var_2A0], rdx; bool
0x180033f82  movzx   r9d, al; char *
0x180033f86  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033f8d  mov     edx, 0D6h; void *
0x180033f92  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180033f97  movzx   edx, bx
0x180033f9a  lea     rcx, [rbp+1C0h+lpExistingFileName]
0x180033f9e  call    ?_GetPrintConfigPackagePath@SpoolerUtility@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z; SpoolerUtility::_GetPrintConfigPackagePath(ushort)
0x180033fa3  nop
0x180033fa4  lea     rdx, [rbp+1C0h+Buffer]
0x180033fa8  mov     rcx, rdi
0x180033fab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033fb0  mov     [rsp+2C0h+var_290], 1
0x180033fb8  mov     ecx, ebx
0x180033fba  test    ebx, ebx
0x180033fbc  jz      loc_180034113
0x180033fc2  sub     ecx, 9
0x180033fc5  jz      loc_18003410A
0x180033fcb  sub     ecx, 1
0x180033fce  jz      loc_18003406C
0x180033fd4  sub     ecx, 2
0x180033fd7  jz      short loc_18003402B
0x180033fd9  cmp     ecx, 1
0x180033fdc  jnz     loc_180034153
0x180033fe2  lea     r8, aSysarm32; "\\SysArm32\\"
0x180033fe9  mov     rdx, rdi
0x180033fec  lea     rcx, [rsp+2C0h+var_260]
0x180033ff1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180033ff6  nop
0x180033ff7  lea     r8, aPrintconfigDll; "PrintConfig.dll"
0x180033ffe  mov     rdx, rax
0x180034001  lea     rcx, [rsp+2C0h+var_280]
0x180034006  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003400b  mov     rdx, rax
0x18003400e  mov     rcx, rdi
0x180034011  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034016  lea     rcx, [rsp+2C0h+var_280]
0x18003401b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034020  nop
0x180034021  lea     rcx, [rsp+2C0h+var_260]
0x180034026  jmp     loc_1800340B0
0x18003402b  lea     r8, aSystem32; "\\System32\\"
0x180034032  mov     rdx, rdi
0x180034035  lea     rcx, [rsp+2C0h+var_280]
0x18003403a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003403f  nop
0x180034040  lea     r8, aPrintconfigDll; "PrintConfig.dll"
0x180034047  mov     rdx, rax
0x18003404a  lea     rcx, [rsp+2C0h+var_260]
0x18003404f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180034054  mov     rdx, rax
0x180034057  mov     rcx, rdi
0x18003405a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003405f  lea     rcx, [rsp+2C0h+var_260]
0x180034064  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034069  nop
0x18003406a  jmp     short loc_1800340AB
0x18003406c  lea     r8, aSyswow64; "\\SysWOW64\\"
0x180034073  mov     rdx, rdi
0x180034076  lea     rcx, [rsp+2C0h+var_280]
0x18003407b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180034080  nop
0x180034081  lea     r8, aPrintconfigDll; "PrintConfig.dll"
0x180034088  mov     rdx, rax
0x18003408b  lea     rcx, [rsp+2C0h+var_260]
0x180034090  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180034095  mov     rdx, rax
0x180034098  mov     rcx, rdi
0x18003409b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800340a0  lea     rcx, [rsp+2C0h+var_260]
0x1800340a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800340aa  nop
0x1800340ab  lea     rcx, [rsp+2C0h+var_280]
0x1800340b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800340b5  cmp     qword ptr [rdi+18h], 7
0x1800340ba  jbe     short loc_1800340C1
0x1800340bc  mov     rdx, [rdi]
0x1800340bf  jmp     short loc_1800340C4
0x1800340c1  mov     rdx, rdi; lpNewFileName
0x1800340c4  lea     rcx, [rbp+1C0h+lpExistingFileName]
0x1800340c8  cmp     [rbp+1C0h+var_228], 7
0x1800340cd  cmova   rcx, [rbp+1C0h+lpExistingFileName]; lpExistingFileName
0x1800340d2  xor     r8d, r8d; bFailIfExists
0x1800340d5  call    cs:__imp_CopyFileW
0x1800340db  test    eax, eax
0x1800340dd  setz    al
0x1800340e0  mov     rcx, [rbp+1C8h]; this
0x1800340e7  lea     rdx, aCopyfileFailed; "CopyFile failed!"
0x1800340ee  mov     qword ptr [rsp+2C0h+var_2A0], rdx; bool
0x1800340f3  movzx   r9d, al; char *
0x1800340f7  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x1800340fe  mov     edx, 0F9h; void *
0x180034103  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180034108  jmp     short loc_180034123
0x18003410a  lea     rdx, aSystem32SpoolD; "\\system32\\spool\\drivers\\x64\\3\\Pri"...
0x180034111  jmp     short loc_18003411A
0x180034113  lea     rdx, aSystem32SpoolD_0; "\\system32\\spool\\drivers\\W32X86\\3\\"...
0x18003411a  mov     rcx, rdi
0x18003411d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180034122  nop
0x180034123  lea     rcx, [rbp+1C0h+lpExistingFileName]
0x180034127  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003412c  mov     rax, rdi
0x18003412f  mov     rcx, [rbp+1C0h+var_10]
0x180034136  xor     rcx, rsp; StackCookie
0x180034139  call    __security_check_cookie
0x18003413e  lea     r11, [rsp+2C0h+var_s0]
0x180034146  mov     rbx, [r11+18h]
0x18003414a  mov     rdi, [r11+20h]
0x18003414e  mov     rsp, r11
0x180034151  pop     rbp
0x180034152  retn
0x180034153  mov     ecx, 80070057h
0x180034158  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003415d  mov     r9d, eax; char *
0x180034160  mov     rcx, [rbp+1C8h]; this
0x180034167  lea     rax, aInvalidArchite; "Invalid architecture!"
0x18003416e  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180034173  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x18003417a  mov     edx, 0F3h; void *
0x18003417f  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```

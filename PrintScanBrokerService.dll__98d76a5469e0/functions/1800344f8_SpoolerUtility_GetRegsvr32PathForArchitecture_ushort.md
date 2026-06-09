# SpoolerUtility::_GetRegsvr32PathForArchitecture(ushort)

- ea: `0x1800344f8`
- end: `0x1800346ed`
- name: `?_GetRegsvr32PathForArchitecture@SpoolerUtility@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `501`
- prototype: `__int64 __fastcall(__int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180033d00`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x180006b48`
- `0x18000f8a8`
- `0x180012498`
- `0x18001d020`
- `0x1800273f0`
- `0x18002b28c`
- `0x180032e6c`
- `0x180032ecc`
- `0x1800344f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180034550`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180034550`

## string_xrefs

- `0x180034562`: `GetSystemWindowsDirectory failed!`
- `0x18003464b`: `\System32\`
- `0x180034572`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x1800346db`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`

## pseudocode

```c
__int64 __fastcall SpoolerUtility::_GetRegsvr32PathForArchitecture(__int64 a1, unsigned __int16 a2)
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
  unsigned int v13; // eax
  const char *v14; // [rsp+28h] [rbp-D8h]
  const char *v15; // [rsp+28h] [rbp-D8h]
  _BYTE v16[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v2 = a2;
  memset_0(Buffer, 0, 0x208u);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x105,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)(SystemWindowsDirectoryW == 0),
    (bool)"GetSystemWindowsDirectory failed!",
    v14);
  std::wstring::wstring(a1, Buffer);
  switch ( v2 )
  {
    case 0:
    case 9:
      goto LABEL_8;
    case 10:
      v8 = std::operator+<unsigned short>(v16, a1, L"\\SysWOW64\\");
      v9 = std::operator+<unsigned short>(v17, v8, L"regsvr32.exe");
      std::wstring::operator=(a1, v9);
      std::wstring::_Tidy_deallocate(v17);
LABEL_9:
      v7 = v16;
      goto LABEL_10;
    case 12:
LABEL_8:
      v10 = std::operator+<unsigned short>(v16, a1, L"\\System32\\");
      v11 = std::operator+<unsigned short>(v17, v10, L"regsvr32.exe");
      std::wstring::operator=(a1, v11);
      std::wstring::_Tidy_deallocate(v17);
      goto LABEL_9;
  }
  if ( v2 != 13 )
  {
    v13 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
      (const char *)v13,
      (int)"Invalid architecture!",
      v15);
  }
  v5 = std::operator+<unsigned short>(v17, a1, L"\\SysArm32\\");
  v6 = std::operator+<unsigned short>(v16, v5, L"regsvr32.exe");
  std::wstring::operator=(a1, v6);
  std::wstring::_Tidy_deallocate(v16);
  v7 = v17;
LABEL_10:
  std::wstring::_Tidy_deallocate(v7);
  return a1;
}

```

## disassembly

```asm
0x1800344f8  mov     [rsp-8+arg_8], rbx
0x1800344fd  mov     [rsp-8+arg_10], rdi
0x180034502  push    rbp
0x180034503  lea     rbp, [rsp-1A0h]
0x18003450b  sub     rsp, 2A0h
0x180034512  mov     rax, cs:__security_cookie
0x180034519  xor     rax, rsp
0x18003451c  mov     [rbp+1A0h+var_10], rax
0x180034523  movzx   ebx, dx
0x180034526  mov     rdi, rcx
0x180034529  mov     [rsp+2A0h+var_268], rcx
0x18003452e  mov     [rsp+2A0h+var_270], 0
0x180034536  xor     edx, edx; Val
0x180034538  mov     r8d, 208h; Size
0x18003453e  lea     rcx, [rbp+1A0h+Buffer]; void *
0x180034542  call    memset_0
0x180034547  mov     edx, 104h; uSize
0x18003454c  lea     rcx, [rbp+1A0h+Buffer]; lpBuffer
0x180034550  call    cs:__imp_GetSystemWindowsDirectoryW
0x180034556  test    eax, eax
0x180034558  setz    al
0x18003455b  mov     rcx, [rbp+1A8h]; this
0x180034562  lea     rdx, aGetsystemwindo; "GetSystemWindowsDirectory failed!"
0x180034569  mov     qword ptr [rsp+2A0h+var_280], rdx; bool
0x18003456e  movzx   r9d, al; char *
0x180034572  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180034579  mov     edx, 105h; void *
0x18003457e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180034583  lea     rdx, [rbp+1A0h+Buffer]
0x180034587  mov     rcx, rdi
0x18003458a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003458f  mov     [rsp+2A0h+var_270], 1
0x180034597  mov     ecx, ebx
0x180034599  test    ebx, ebx
0x18003459b  jz      loc_18003464B
0x1800345a1  sub     ecx, 9
0x1800345a4  jz      loc_18003464B
0x1800345aa  sub     ecx, 1
0x1800345ad  jz      short loc_18003460A
0x1800345af  sub     ecx, 2
0x1800345b2  jz      loc_18003464B
0x1800345b8  cmp     ecx, 1
0x1800345bb  jnz     loc_1800346BB
0x1800345c1  lea     r8, aSysarm32; "\\SysArm32\\"
0x1800345c8  mov     rdx, rdi
0x1800345cb  lea     rcx, [rsp+2A0h+var_240]
0x1800345d0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800345d5  nop
0x1800345d6  lea     r8, aRegsvr32Exe; "regsvr32.exe"
0x1800345dd  mov     rdx, rax
0x1800345e0  lea     rcx, [rsp+2A0h+var_260]
0x1800345e5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800345ea  mov     rdx, rax
0x1800345ed  mov     rcx, rdi
0x1800345f0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800345f5  lea     rcx, [rsp+2A0h+var_260]
0x1800345fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800345ff  nop
0x180034600  lea     rcx, [rsp+2A0h+var_240]
0x180034605  jmp     loc_18003468F
0x18003460a  lea     r8, aSyswow64; "\\SysWOW64\\"
0x180034611  mov     rdx, rdi
0x180034614  lea     rcx, [rsp+2A0h+var_260]
0x180034619  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003461e  nop
0x18003461f  lea     r8, aRegsvr32Exe; "regsvr32.exe"
0x180034626  mov     rdx, rax
0x180034629  lea     rcx, [rsp+2A0h+var_240]
0x18003462e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180034633  mov     rdx, rax
0x180034636  mov     rcx, rdi
0x180034639  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003463e  lea     rcx, [rsp+2A0h+var_240]
0x180034643  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034648  nop
0x180034649  jmp     short loc_18003468A
0x18003464b  lea     r8, aSystem32; "\\System32\\"
0x180034652  mov     rdx, rdi
0x180034655  lea     rcx, [rsp+2A0h+var_260]
0x18003465a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003465f  nop
0x180034660  lea     r8, aRegsvr32Exe; "regsvr32.exe"
0x180034667  mov     rdx, rax
0x18003466a  lea     rcx, [rsp+2A0h+var_240]
0x18003466f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180034674  mov     rdx, rax
0x180034677  mov     rcx, rdi
0x18003467a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003467f  lea     rcx, [rsp+2A0h+var_240]
0x180034684  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034689  nop
0x18003468a  lea     rcx, [rsp+2A0h+var_260]
0x18003468f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034694  mov     rax, rdi
0x180034697  mov     rcx, [rbp+1A0h+var_10]
0x18003469e  xor     rcx, rsp; StackCookie
0x1800346a1  call    __security_check_cookie
0x1800346a6  lea     r11, [rsp+2A0h+var_s0]
0x1800346ae  mov     rbx, [r11+18h]
0x1800346b2  mov     rdi, [r11+20h]
0x1800346b6  mov     rsp, r11
0x1800346b9  pop     rbp
0x1800346ba  retn
0x1800346bb  mov     ecx, 80070057h
0x1800346c0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800346c5  mov     r9d, eax; char *
0x1800346c8  mov     rcx, [rbp+1A8h]; this
0x1800346cf  lea     rax, aInvalidArchite; "Invalid architecture!"
0x1800346d6  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800346db  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x1800346e2  mov     edx, 117h; void *
0x1800346e7  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```

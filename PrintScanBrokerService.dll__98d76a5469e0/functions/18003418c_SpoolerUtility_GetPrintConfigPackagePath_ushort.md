# SpoolerUtility::_GetPrintConfigPackagePath(ushort)

- ea: `0x18003418c`
- end: `0x1800344ef`
- name: `?_GetPrintConfigPackagePath@SpoolerUtility@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `867`
- prototype: `__int64 __fastcall(__int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180033f0c`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x1800061ec`
- `0x180006b48`
- `0x18000f8a8`
- `0x180012498`
- `0x18001cfd4`
- `0x18001d020`
- `0x1800273f0`
- `0x18002b28c`
- `0x180032e6c`
- `0x180032ecc`
- `0x18003418c`
- `0x18003470c`

## import_xrefs

- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x180034261`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x180034261`

## string_xrefs

- `0x180034387`: `PrintConfig.dll`
- `0x1800343cb`: `PrintConfig.dll`
- `0x180034414`: `PrintConfig.dll`
- `0x180034455`: `PrintConfig.dll`
- `0x180034283`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180034309`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x1800344dd`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x1800342f3`: `SetupGetInfDriverStoreLocation returned an unexpected path!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpoolerUtility::_GetPrintConfigPackagePath(__int64 a1, unsigned __int16 a2)
{
  int v2; // esi
  struct _SP_ALTPLATFORM_INFO_V2 *p_AlternatePlatformInfo; // rbx
  BOOL InfDriverStoreLocationW; // eax
  __int64 v6; // r8
  _QWORD *v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v20; // eax
  const char *RequiredSizea; // [rsp+28h] [rbp-D8h]
  const char *RequiredSize; // [rsp+28h] [rbp-D8h]
  char *v23; // [rsp+30h] [rbp-D0h]
  _BYTE v25[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[32]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v27[4]; // [rsp+80h] [rbp-80h] BYREF
  _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v29[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v2 = a2;
  memset(&AlternatePlatformInfo, 0, sizeof(AlternatePlatformInfo));
  memset(v29, 0, 28);
  if ( a2 == 10 )
  {
    AlternatePlatformInfo.cbSize = 28;
    AlternatePlatformInfo.Platform = 2;
    AlternatePlatformInfo.ProcessorArchitecture = 0;
    p_AlternatePlatformInfo = &AlternatePlatformInfo;
  }
  else
  {
    p_AlternatePlatformInfo = 0;
    if ( a2 == 13 )
    {
      *(_QWORD *)&v29[0] = 0x20000001CLL;
      LOWORD(v29[1]) = 5;
      p_AlternatePlatformInfo = (struct _SP_ALTPLATFORM_INFO_V2 *)v29;
    }
  }
  memset_0(ReturnBuffer, 0, 0x208u);
  InfDriverStoreLocationW = SetupGetInfDriverStoreLocationW(
                              L"prnms003.inf",
                              p_AlternatePlatformInfo,
                              0,
                              ReturnBuffer,
                              0x104u,
                              0);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xAF,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)!InfDriverStoreLocationW,
    (bool)"SetupGetInfDriverStoreLocation failed!",
    RequiredSizea);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  LODWORD(v23) = 1;
  std::wstring::wstring(v27, ReturnBuffer);
  v7 = v27;
  if ( v27[3] > 7u )
    v7 = (_QWORD *)v27[0];
  v8 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v7, v27[2], v6, 92);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xB5,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)0x8000FFFFLL,
    v8 == -1,
    (bool)"SetupGetInfDriverStoreLocation returned an unexpected path!",
    v23,
    a1);
  v9 = std::wstring::substr(v27, v25, 0, v8);
  std::wstring::operator=(a1, v9);
  std::wstring::_Tidy_deallocate(v25);
  switch ( v2 )
  {
    case 0:
      goto LABEL_16;
    case 5:
LABEL_13:
      v10 = std::operator+<unsigned short>(v25, a1, L"\\arm\\");
      v11 = std::operator+<unsigned short>(v26, v10, L"PrintConfig.dll");
      std::wstring::operator=(a1, v11);
      std::wstring::_Tidy_deallocate(v26);
LABEL_17:
      v14 = v25;
      goto LABEL_18;
    case 9:
      v15 = std::operator+<unsigned short>(v25, a1, L"\\amd64\\");
      v16 = std::operator+<unsigned short>(v26, v15, L"PrintConfig.dll");
      std::wstring::operator=(a1, v16);
      std::wstring::_Tidy_deallocate(v26);
      goto LABEL_17;
    case 10:
LABEL_16:
      v17 = std::operator+<unsigned short>(v25, a1, L"\\I386\\");
      v18 = std::operator+<unsigned short>(v26, v17, L"PrintConfig.dll");
      std::wstring::operator=(a1, v18);
      std::wstring::_Tidy_deallocate(v26);
      goto LABEL_17;
  }
  if ( v2 != 12 )
  {
    if ( v2 != 13 )
    {
      v20 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
        (const char *)v20,
        (int)"Invalid architecture!",
        RequiredSize);
    }
    goto LABEL_13;
  }
  v12 = std::operator+<unsigned short>(v26, a1, L"\\arm64\\");
  v13 = std::operator+<unsigned short>(v25, v12, L"PrintConfig.dll");
  std::wstring::operator=(a1, v13);
  std::wstring::_Tidy_deallocate(v25);
  v14 = v26;
LABEL_18:
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v27);
  return a1;
}

```

## disassembly

```asm
0x18003418c  mov     [rsp-8+arg_8], rbx
0x180034191  mov     [rsp-8+arg_10], rsi
0x180034196  push    rbp
0x180034197  push    rdi
0x180034198  push    r12
0x18003419a  lea     rbp, [rsp-200h]
0x1800341a2  sub     rsp, 300h
0x1800341a9  mov     rax, cs:__security_cookie
0x1800341b0  xor     rax, rsp
0x1800341b3  mov     [rbp+210h+var_20], rax
0x1800341ba  movzx   esi, dx
0x1800341bd  mov     rdi, rcx
0x1800341c0  mov     [rsp+310h+var_2D8], rcx
0x1800341c5  mov     dword ptr [rsp+310h+var_2E0], 0
0x1800341cd  xorps   xmm0, xmm0
0x1800341d0  xor     eax, eax
0x1800341d2  movups  xmmword ptr [rbp+210h+AlternatePlatformInfo.cbSize], xmm0
0x1800341d6  movups  xmmword ptr [rbp+210h+AlternatePlatformInfo.MinorVersion], xmm0
0x1800341da  xorps   xmm1, xmm1
0x1800341dd  movups  [rbp+210h+var_250], xmm1
0x1800341e1  movups  [rbp+210h+var_250+0Ch], xmm1
0x1800341e5  mov     eax, 0Ah
0x1800341ea  lea     r12d, [rax-5]
0x1800341ee  cmp     ax, si
0x1800341f1  jnz     short loc_18003420D
0x1800341f3  mov     [rbp+210h+AlternatePlatformInfo.cbSize], 1Ch
0x1800341fa  mov     [rbp+210h+AlternatePlatformInfo.Platform], 2
0x180034201  xor     eax, eax
0x180034203  mov     [rbp+210h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x180034207  lea     rbx, [rbp+210h+AlternatePlatformInfo]
0x18003420b  jmp     short loc_18003422E
0x18003420d  xor     ebx, ebx
0x18003420f  lea     eax, [rbx+0Dh]
0x180034212  cmp     ax, si
0x180034215  jnz     short loc_18003422E
0x180034217  mov     dword ptr [rbp+210h+var_250], 1Ch
0x18003421e  mov     dword ptr [rbp+210h+var_250+4], 2
0x180034225  mov     [rbp+210h+var_240], r12w
0x18003422a  lea     rbx, [rbp+210h+var_250]
0x18003422e  xor     edx, edx; Val
0x180034230  mov     r8d, 208h; Size
0x180034236  lea     rcx, [rbp+210h+ReturnBuffer]; void *
0x18003423a  call    memset_0
0x18003423f  mov     [rsp+310h+RequiredSize], 0; char *
0x180034248  mov     [rsp+310h+ReturnBufferSize], 104h; ReturnBufferSize
0x180034250  lea     r9, [rbp+210h+ReturnBuffer]; ReturnBuffer
0x180034254  xor     r8d, r8d; LocaleName
0x180034257  mov     rdx, rbx; AlternatePlatformInfo
0x18003425a  lea     rcx, FileName; "prnms003.inf"
0x180034261  call    cs:__imp_SetupGetInfDriverStoreLocationW
0x180034267  test    eax, eax
0x180034269  setz    al
0x18003426c  mov     rcx, [rbp+218h]; this
0x180034273  lea     rdx, aSetupgetinfdri; "SetupGetInfDriverStoreLocation failed!"
0x18003427a  mov     qword ptr [rsp+310h+ReturnBufferSize], rdx; bool
0x18003427f  movzx   r9d, al; char *
0x180034283  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x18003428a  mov     edx, 0AFh; void *
0x18003428f  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180034294  xorps   xmm0, xmm0
0x180034297  movups  xmmword ptr [rdi], xmm0
0x18003429a  mov     qword ptr [rdi+10h], 0
0x1800342a2  mov     qword ptr [rdi+18h], 7
0x1800342aa  xor     eax, eax
0x1800342ac  mov     [rdi], ax
0x1800342af  mov     dword ptr [rsp+310h+var_2E0], 1; char *
0x1800342b7  lea     rdx, [rbp+210h+ReturnBuffer]
0x1800342bb  lea     rcx, [rbp+210h+var_290]
0x1800342bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800342c4  nop
0x1800342c5  lea     rcx, [rbp+210h+var_290]
0x1800342c9  cmp     [rbp+210h+var_278], 7
0x1800342ce  cmova   rcx, [rbp+210h+var_290]
0x1800342d3  mov     r9d, 5Ch ; '\'
0x1800342d9  mov     rdx, [rbp+210h+var_280]
0x1800342dd  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1800342e2  mov     rbx, rax
0x1800342e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800342e9  setz    dl
0x1800342ec  mov     rcx, [rbp+218h]; this
0x1800342f3  lea     rax, aSetupgetinfdri_0; "SetupGetInfDriverStoreLocation returned"...
0x1800342fa  mov     [rsp+310h+RequiredSize], rax; char *
0x1800342ff  mov     byte ptr [rsp+310h+ReturnBufferSize], dl; char
0x180034303  mov     r9d, 8000FFFFh; char *
0x180034309  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180034310  mov     edx, 0B5h; void *
0x180034315  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003431a  mov     r9, rbx
0x18003431d  xor     r8d, r8d
0x180034320  lea     rdx, [rsp+310h+var_2D0]
0x180034325  lea     rcx, [rbp+210h+var_290]
0x180034329  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18003432e  mov     rdx, rax
0x180034331  mov     rcx, rdi
0x180034334  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034339  lea     rcx, [rsp+310h+var_2D0]
0x18003433e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034343  mov     ecx, esi
0x180034345  test    esi, esi
0x180034347  jz      loc_180034440
0x18003434d  sub     ecx, r12d
0x180034350  jz      short loc_180034372
0x180034352  sub     ecx, 4
0x180034355  jz      loc_1800343FF
0x18003435b  sub     ecx, 1
0x18003435e  jz      loc_180034440
0x180034364  sub     ecx, 2
0x180034367  jz      short loc_1800343B6
0x180034369  cmp     ecx, 1
0x18003436c  jnz     loc_1800344BD
0x180034372  lea     r8, aArm; "\\arm\\"
0x180034379  mov     rdx, rdi
0x18003437c  lea     rcx, [rsp+310h+var_2D0]
0x180034381  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180034386  nop
0x180034387  lea     r8, aPrintconfigDll; "PrintConfig.dll"
0x18003438e  mov     rdx, rax
0x180034391  lea     rcx, [rsp+310h+var_2B0]
0x180034396  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003439b  mov     rdx, rax
0x18003439e  mov     rcx, rdi
0x1800343a1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800343a6  lea     rcx, [rsp+310h+var_2B0]
0x1800343ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800343b0  nop
0x1800343b1  jmp     loc_18003447F
0x1800343b6  lea     r8, aArm64; "\\arm64\\"
0x1800343bd  mov     rdx, rdi
0x1800343c0  lea     rcx, [rsp+310h+var_2B0]
0x1800343c5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800343ca  nop
0x1800343cb  lea     r8, aPrintconfigDll; "PrintConfig.dll"
0x1800343d2  mov     rdx, rax
0x1800343d5  lea     rcx, [rsp+310h+var_2D0]
0x1800343da  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800343df  mov     rdx, rax
0x1800343e2  mov     rcx, rdi
0x1800343e5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800343ea  lea     rcx, [rsp+310h+var_2D0]
0x1800343ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800343f4  nop
0x1800343f5  lea     rcx, [rsp+310h+var_2B0]
0x1800343fa  jmp     loc_180034484
0x1800343ff  lea     r8, aAmd64; "\\amd64\\"
0x180034406  mov     rdx, rdi
0x180034409  lea     rcx, [rsp+310h+var_2D0]
0x18003440e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180034413  nop
0x180034414  lea     r8, aPrintconfigDll; "PrintConfig.dll"
0x18003441b  mov     rdx, rax
0x18003441e  lea     rcx, [rsp+310h+var_2B0]
0x180034423  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180034428  mov     rdx, rax
0x18003442b  mov     rcx, rdi
0x18003442e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034433  lea     rcx, [rsp+310h+var_2B0]
0x180034438  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003443d  nop
0x18003443e  jmp     short loc_18003447F
0x180034440  lea     r8, aI386; "\\I386\\"
0x180034447  mov     rdx, rdi
0x18003444a  lea     rcx, [rsp+310h+var_2D0]
0x18003444f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180034454  nop
0x180034455  lea     r8, aPrintconfigDll; "PrintConfig.dll"
0x18003445c  mov     rdx, rax
0x18003445f  lea     rcx, [rsp+310h+var_2B0]
0x180034464  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180034469  mov     rdx, rax
0x18003446c  mov     rcx, rdi
0x18003446f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034474  lea     rcx, [rsp+310h+var_2B0]
0x180034479  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003447e  nop
0x18003447f  lea     rcx, [rsp+310h+var_2D0]
0x180034484  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034489  nop
0x18003448a  lea     rcx, [rbp+210h+var_290]
0x18003448e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034493  mov     rax, rdi
0x180034496  mov     rcx, [rbp+210h+var_20]
0x18003449d  xor     rcx, rsp; StackCookie
0x1800344a0  call    __security_check_cookie
0x1800344a5  lea     r11, [rsp+310h+var_10]
0x1800344ad  mov     rbx, [r11+28h]
0x1800344b1  mov     rsi, [r11+30h]
0x1800344b5  mov     rsp, r11
0x1800344b8  pop     r12
0x1800344ba  pop     rdi
0x1800344bb  pop     rbp
0x1800344bc  retn
0x1800344bd  mov     ecx, 80070057h
0x1800344c2  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800344c7  mov     r9d, eax; char *
0x1800344ca  mov     rcx, [rbp+218h]; this
0x1800344d1  lea     rax, aInvalidArchite; "Invalid architecture!"
0x1800344d8  mov     qword ptr [rsp+310h+ReturnBufferSize], rax; int
0x1800344dd  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x1800344e4  mov     edx, 0CAh; void *
0x1800344e9  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```

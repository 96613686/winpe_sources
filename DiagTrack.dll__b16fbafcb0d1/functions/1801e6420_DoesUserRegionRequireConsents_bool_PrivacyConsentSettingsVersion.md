# DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)

- ea: `0x1801e6420`
- end: `0x1801e6632`
- name: `?DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(bool *, enum PrivacyConsentSettingsVersion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801203ec`

## callees

- `0x180064e8c`
- `0x180122f48`
- `0x1801e6420`
- `0x18020aac0`
- `0x18020ba94`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e65c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e65c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e65a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e65a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65eb`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1801e647a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1801e647a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoesUserRegionRequireConsents(bool *a1, enum PrivacyConsentSettingsVersion *a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  __int64 v9; // rcx
  wchar_t **i; // rdi
  const WCHAR *v11; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v13; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v15; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  __int64 v17; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Globalization.GeographicRegion",
    0x27u,
    0x26u);
  v15 = 0;
  v17 = 0;
  v3 = RoActivateInstance(v19, &v17);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v15 = v17;
    }
    else
    {
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(
             v17,
             &GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903,
             &v15);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\privacyconsenthelpers.h",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
    v4 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return (unsigned int)v3;
  }
  string = 0;
  v6 = v15;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(v6, &string);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\privacyconsenthelpers.h",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    WindowsDeleteString(string);
    string = 0;
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return (unsigned int)v3;
  }
  for ( i = &`DoesUserRegionRequireConsents'::`2'::RegionPrivacyRequirements; i != &off_1803857D0; i += 2 )
  {
    v11 = *i;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, v11, -1, 1) == 2 )
    {
      *a1 = 1;
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_19;
    }
  }
  *a1 = 0;
  WindowsDeleteString(string);
  string = 0;
LABEL_19:
  v13 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1801e6420  mov     [rsp-18h+arg_8], rbx
0x1801e6425  mov     [rsp-18h+arg_10], rsi
0x1801e642a  push    rbp
0x1801e642b  push    rdi
0x1801e642c  push    r14
0x1801e642e  mov     rbp, rsp
0x1801e6431  sub     rsp, 70h
0x1801e6435  mov     rax, cs:__security_cookie
0x1801e643c  xor     rax, rsp
0x1801e643f  mov     [rbp+var_8], rax
0x1801e6443  mov     rsi, rcx
0x1801e6446  xor     r14d, r14d
0x1801e6449  mov     [rbp+var_40], r14
0x1801e644d  mov     [rbp+var_10], r14
0x1801e6451  lea     r9d, [r14+26h]; unsigned int
0x1801e6455  lea     r8d, [r14+27h]; unsigned int
0x1801e6459  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QB_WB; "Windows.Globalization.GeographicRegion"
0x1801e6460  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e6464  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x1801e6469  nop
0x1801e646a  mov     [rbp+var_40], r14
0x1801e646e  mov     [rbp+var_30], r14
0x1801e6472  lea     rdx, [rbp+var_30]
0x1801e6476  mov     rcx, [rbp+var_10]
0x1801e647a  call    cs:__imp_RoActivateInstance
0x1801e6480  mov     ebx, eax
0x1801e6482  test    eax, eax
0x1801e6484  js      short loc_1801E64D8
0x1801e6486  lea     r8d, [r14+10h]; Size
0x1801e648a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1801e6491  lea     rcx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903; Buf1
0x1801e6498  call    memcmp_0
0x1801e649d  test    eax, eax
0x1801e649f  jnz     short loc_1801E64AB
0x1801e64a1  mov     rax, [rbp+var_30]
0x1801e64a5  mov     [rbp+var_40], rax
0x1801e64a9  jmp     short loc_1801E64D8
0x1801e64ab  mov     rcx, [rbp+var_30]
0x1801e64af  mov     rax, [rcx]
0x1801e64b2  lea     r8, [rbp+var_40]
0x1801e64b6  lea     rdx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903
0x1801e64bd  mov     rax, [rax]
0x1801e64c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e64c5  mov     ebx, eax
0x1801e64c7  mov     rcx, [rbp+var_30]
0x1801e64cb  mov     rax, [rcx]
0x1801e64ce  mov     rax, [rax+10h]
0x1801e64d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e64d7  nop
0x1801e64d8  test    ebx, ebx
0x1801e64da  jns     short loc_1801E6516
0x1801e64dc  mov     rcx, [rbp+18h]; this
0x1801e64e0  mov     r9d, ebx; char *
0x1801e64e3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1801e64ea  mov     edx, 0CFh; void *
0x1801e64ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e64f4  nop
0x1801e64f5  mov     rcx, [rbp+var_40]
0x1801e64f9  test    rcx, rcx
0x1801e64fc  jz      short loc_1801E650F
0x1801e64fe  mov     [rbp+var_40], r14
0x1801e6502  mov     rax, [rcx]
0x1801e6505  mov     rax, [rax+10h]
0x1801e6509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e650e  nop
0x1801e650f  mov     eax, ebx
0x1801e6511  jmp     loc_1801E6611
0x1801e6516  mov     [rbp+string], r14
0x1801e651a  mov     rdi, [rbp+var_40]
0x1801e651e  mov     rax, [rdi]
0x1801e6521  mov     rbx, [rax+40h]
0x1801e6525  xor     ecx, ecx; string
0x1801e6527  call    cs:__imp_WindowsDeleteString
0x1801e652d  mov     [rbp+string], r14
0x1801e6531  lea     rdx, [rbp+string]
0x1801e6535  mov     rcx, rdi
0x1801e6538  mov     rax, rbx
0x1801e653b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6540  mov     ebx, eax
0x1801e6542  test    eax, eax
0x1801e6544  jns     short loc_1801E6589
0x1801e6546  mov     rcx, [rbp+18h]; this
0x1801e654a  mov     r9d, eax; char *
0x1801e654d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1801e6554  mov     edx, 0D2h; void *
0x1801e6559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e655e  nop
0x1801e655f  mov     rcx, [rbp+string]; string
0x1801e6563  call    cs:__imp_WindowsDeleteString
0x1801e6569  mov     [rbp+string], r14
0x1801e656d  mov     rcx, [rbp+var_40]
0x1801e6571  test    rcx, rcx
0x1801e6574  jz      short loc_1801E6587
0x1801e6576  mov     [rbp+var_40], r14
0x1801e657a  mov     rax, [rcx]
0x1801e657d  mov     rax, [rax+10h]
0x1801e6581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6586  nop
0x1801e6587  jmp     short loc_1801E650F
0x1801e6589  lea     rdi, ?RegionPrivacyRequirements@?1??DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z@4QBU_unnamed_type_RegionPrivacyRequirements_@?1??1@YAJ01@Z@B; `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::_unnamed_type_RegionPrivacyRequirements_ const near * const `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::RegionPrivacyRequirements
0x1801e6590  lea     rax, off_1803857D0; "SettingsBaseUrl"
0x1801e6597  cmp     rdi, rax
0x1801e659a  jz      short loc_1801E65E4
0x1801e659c  mov     rbx, [rdi]
0x1801e659f  xor     edx, edx; length
0x1801e65a1  mov     rcx, [rbp+string]; string
0x1801e65a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e65ab  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x1801e65b3  or      r9d, 0FFFFFFFFh; cchCount2
0x1801e65b7  mov     r8, rbx; lpString2
0x1801e65ba  or      edx, r9d; cchCount1
0x1801e65bd  mov     rcx, rax; lpString1
0x1801e65c0  call    cs:__imp_CompareStringOrdinal
0x1801e65c6  cmp     eax, 2
0x1801e65c9  jz      short loc_1801E65D1
0x1801e65cb  add     rdi, 10h
0x1801e65cf  jmp     short loc_1801E6590
0x1801e65d1  mov     byte ptr [rsi], 1
0x1801e65d4  mov     rcx, [rbp+string]; string
0x1801e65d8  call    cs:__imp_WindowsDeleteString
0x1801e65de  mov     [rbp+string], r14
0x1801e65e2  jmp     short loc_1801E65F5
0x1801e65e4  mov     [rsi], r14b
0x1801e65e7  mov     rcx, [rbp+string]; string
0x1801e65eb  call    cs:__imp_WindowsDeleteString
0x1801e65f1  mov     [rbp+string], r14
0x1801e65f5  mov     rcx, [rbp+var_40]
0x1801e65f9  test    rcx, rcx
0x1801e65fc  jz      short loc_1801E660F
0x1801e65fe  mov     [rbp+var_40], r14
0x1801e6602  mov     rax, [rcx]
0x1801e6605  mov     rax, [rax+10h]
0x1801e6609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e660e  nop
0x1801e660f  xor     eax, eax
0x1801e6611  mov     rcx, [rbp+var_8]
0x1801e6615  xor     rcx, rsp; StackCookie
0x1801e6618  call    __security_check_cookie
0x1801e661d  lea     r11, [rsp+70h+var_s0]
0x1801e6622  mov     rbx, [r11+28h]
0x1801e6626  mov     rsi, [r11+30h]
0x1801e662a  mov     rsp, r11
0x1801e662d  pop     r14
0x1801e662f  pop     rdi
0x1801e6630  pop     rbp
0x1801e6631  retn
```

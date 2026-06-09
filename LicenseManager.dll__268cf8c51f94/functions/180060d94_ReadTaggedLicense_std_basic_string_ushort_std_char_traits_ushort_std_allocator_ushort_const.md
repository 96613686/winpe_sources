# ReadTaggedLicense(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180060d94`
- end: `0x180060f22`
- name: `?ReadTaggedLicense@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z`
- size: `398`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18005fec0`
- `0x180095bb0`

## callees

- `0x180004644`
- `0x180013b50`
- `0x1800178e0`
- `0x1800593bc`
- `0x180060d94`
- `0x180061094`
- `0x180090f34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180060e13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180060eeb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180060e13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180060eeb`

## string_xrefs

- `0x180060e34`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`
- `0x180060e7a`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`
- `0x180060e94`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`
- `0x180060efc`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`
- `0x180060e6d`: `ReadTaggedLicense`
- `0x180060e61`: `Read value for license tagged %s, but the value type was not REG_SZ (it was %d).`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReadTaggedLicense(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  BYTE *v6; // rax
  unsigned int v7; // eax
  unsigned int lpData; // [rsp+20h] [rbp-30h]
  int lpDatab; // [rsp+20h] [rbp-30h]
  unsigned int lpDataa; // [rsp+20h] [rbp-30h]
  HKEY hKey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD cbData; // [rsp+78h] [rbp+28h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+88h] [rbp+38h]

  v16 = 1;
  OpenTaggedLicensesKey(hKey, 0x20019u);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v16 = 1;
  Type = 0;
  cbData = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const WCHAR **)a2;
  v5 = RegQueryValueExW(hKey[0], v4, 0, &Type, 0, &cbData);
  if ( v5 != 2 )
  {
    if ( v5 != 234 && v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)v5,
        lpData);
    if ( Type != 1 )
    {
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const WCHAR **)a2;
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        0x35u,
        "ReadTaggedLicense",
        (wchar_t *)L"Read value for license tagged %s, but the value type was not REG_SZ (it was %d).",
        a2,
        Type);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)0x8007000DLL,
        lpDatab);
    }
    std::wstring::resize(a1, cbData + 1, 0);
    if ( *(_QWORD *)(a1 + 24) <= 7u )
      v6 = (BYTE *)a1;
    else
      v6 = *(BYTE **)a1;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    v7 = RegQueryValueExW(hKey[0], a2, 0, &Type, v6, &cbData);
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)v7,
        lpDataa);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return a1;
}

```

## disassembly

```asm
0x180060d94  mov     [rsp-18h+arg_0], rcx
0x180060d99  push    rbp
0x180060d9a  push    rbx
0x180060d9b  push    rdi
0x180060d9c  mov     rbp, rsp
0x180060d9f  sub     rsp, 50h
0x180060da3  mov     rbx, rdx
0x180060da6  mov     rdi, rcx
0x180060da9  mov     [rbp+arg_18], 1
0x180060db0  mov     edx, 20019h; samDesired
0x180060db5  lea     rcx, [rbp+hKey]; phkResult
0x180060db9  call    ?OpenTaggedLicensesKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; OpenTaggedLicensesKey(ulong)
0x180060dbe  nop
0x180060dbf  xorps   xmm0, xmm0
0x180060dc2  movups  xmmword ptr [rdi], xmm0
0x180060dc5  mov     qword ptr [rdi+10h], 0
0x180060dcd  mov     qword ptr [rdi+18h], 7
0x180060dd5  xor     eax, eax
0x180060dd7  mov     [rdi], ax
0x180060dda  mov     [rbp+arg_18], 1
0x180060de1  mov     [rbp+Type], eax
0x180060de4  mov     [rbp+cbData], eax
0x180060de7  cmp     qword ptr [rbx+18h], 7
0x180060dec  jbe     short loc_180060DF3
0x180060dee  mov     rdx, [rbx]
0x180060df1  jmp     short loc_180060DF6
0x180060df3  mov     rdx, rbx; lpValueName
0x180060df6  lea     rax, [rbp+cbData]
0x180060dfa  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180060dff  mov     [rsp+50h+lpData], 0; unsigned int
0x180060e08  lea     r9, [rbp+Type]; lpType
0x180060e0c  xor     r8d, r8d; lpReserved
0x180060e0f  mov     rcx, [rbp+hKey]; hKey
0x180060e13  call    cs:__imp_RegQueryValueExW
0x180060e19  cmp     eax, 2
0x180060e1c  jz      loc_180060F0E
0x180060e22  cmp     eax, 0EAh
0x180060e27  jz      short loc_180060E46
0x180060e29  mov     rcx, [rbp+18h]; this
0x180060e2d  test    eax, eax
0x180060e2f  jz      short loc_180060E46
0x180060e31  mov     r9d, eax; char *
0x180060e34  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x180060e3b  mov     edx, 30h ; '0'; void *
0x180060e40  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180060e46  mov     eax, [rbp+Type]
0x180060e49  cmp     eax, 1
0x180060e4c  jz      short loc_180060EA6
0x180060e4e  cmp     qword ptr [rbx+18h], 7
0x180060e53  jbe     short loc_180060E58
0x180060e55  mov     rbx, [rbx]
0x180060e58  mov     [rsp+50h+var_20], eax
0x180060e5c  mov     [rsp+50h+lpcbData], rbx
0x180060e61  lea     rax, aReadValueForLi; "Read value for license tagged %s, but t"...
0x180060e68  mov     [rsp+50h+lpData], rax; int
0x180060e6d  lea     r9, aReadtaggedlice; "ReadTaggedLicense"
0x180060e74  mov     r8d, 35h ; '5'; unsigned int
0x180060e7a  lea     rdx, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x180060e81  lea     ecx, [r8-32h]; unsigned int
0x180060e85  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180060e8a  mov     rcx, [rbp+18h]; this
0x180060e8e  mov     r9d, 8007000Dh; char *
0x180060e94  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x180060e9b  mov     edx, 36h ; '6'; void *
0x180060ea0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060ea6  xor     r8d, r8d
0x180060ea9  mov     edx, [rbp+cbData]
0x180060eac  inc     edx
0x180060eae  mov     rcx, rdi
0x180060eb1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180060eb6  cmp     qword ptr [rdi+18h], 7
0x180060ebb  jbe     short loc_180060EC2
0x180060ebd  mov     rax, [rdi]
0x180060ec0  jmp     short loc_180060EC5
0x180060ec2  mov     rax, rdi
0x180060ec5  cmp     qword ptr [rbx+18h], 7
0x180060eca  jbe     short loc_180060ECF
0x180060ecc  mov     rbx, [rbx]
0x180060ecf  lea     rcx, [rbp+cbData]
0x180060ed3  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x180060ed8  mov     [rsp+50h+lpData], rax; unsigned int
0x180060edd  lea     r9, [rbp+Type]; lpType
0x180060ee1  xor     r8d, r8d; lpReserved
0x180060ee4  mov     rdx, rbx; lpValueName
0x180060ee7  mov     rcx, [rbp+hKey]; hKey
0x180060eeb  call    cs:__imp_RegQueryValueExW
0x180060ef1  mov     rcx, [rbp+18h]; this
0x180060ef5  test    eax, eax
0x180060ef7  jz      short loc_180060F0E
0x180060ef9  mov     r9d, eax; char *
0x180060efc  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x180060f03  mov     edx, 3Ah ; ':'; void *
0x180060f08  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180060f0e  lea     rcx, [rbp+hKey]
0x180060f12  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180060f17  mov     rax, rdi
0x180060f1a  add     rsp, 50h
0x180060f1e  pop     rdi
0x180060f1f  pop     rbx
0x180060f20  pop     rbp
0x180060f21  retn
```

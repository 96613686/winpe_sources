# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x180033c58`
- end: `0x180033da9`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `337`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002ece0`

## callees

- `0x180007c78`
- `0x180018280`
- `0x180028790`
- `0x180033c58`
- `0x1800383a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033c99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033c99`

## string_xrefs

- `0x180033cb8`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180033d09`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180033cee`: `ExtensionClass`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HKEY *v3; // rdi
  unsigned int v5; // ebx
  HKEY v7; // rcx
  int RegValue; // ebx
  __int64 v9; // rdx
  HKEY v10; // rcx
  HKEY v11; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  char *v14; // [rsp+30h] [rbp-20h] BYREF
  HKEY v15; // [rsp+38h] [rbp-18h] BYREF
  char v16; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v18; // [rsp+70h] [rbp+20h] BYREF
  int v19; // [rsp+88h] [rbp+38h] BYREF

  v15 = 0;
  v3 = (HKEY *)((char *)this + 8);
  v14 = (char *)this + 8;
  v16 = 1;
  v5 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &v15);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v14);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xE0,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
             (const char *)v5,
             phkResult);
  v7 = *v3;
  v18 = 256;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               v7,
               L"ExtensionClass",
               2u,
               (char *)this + 24,
               &v18);
  if ( RegValue < 0 )
  {
    v9 = 227;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)(unsigned int)RegValue,
      phkResulta);
    return (unsigned int)RegValue;
  }
  v10 = *v3;
  v19 = 0;
  v18 = 4;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               v10,
               L"Test",
               0x10u,
               &v19,
               &v18);
  if ( RegValue < 0 )
  {
    v9 = 231;
    goto LABEL_5;
  }
  v11 = *v3;
  v18 = 4;
  *((_BYTE *)this + 16) = v19 != 0;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               v11,
               L"VelocityFeatureId",
               0x10u,
               (char *)this + 20,
               &v18);
  if ( RegValue < 0 )
  {
    v9 = 235;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180033c58  mov     [rsp-18h+arg_8], rbx
0x180033c5d  push    rbp
0x180033c5e  push    rsi
0x180033c5f  push    rdi
0x180033c60  mov     rbp, rsp
0x180033c63  sub     rsp, 50h
0x180033c67  and     [rbp+var_18], 0
0x180033c6c  lea     rdi, [rcx+8]
0x180033c70  mov     rsi, rcx
0x180033c73  mov     [rbp+var_20], rdi
0x180033c77  mov     rax, r8
0x180033c7a  mov     [rbp+var_10], 1
0x180033c7e  mov     r10, rdx
0x180033c81  lea     rcx, [rbp+var_18]
0x180033c85  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x180033c8a  mov     r9d, 20019h; samDesired
0x180033c90  mov     rcx, r10; hKey
0x180033c93  xor     r8d, r8d; ulOptions
0x180033c96  mov     rdx, rax; lpSubKey
0x180033c99  call    cs:__imp_RegOpenKeyExW
0x180033ca0  nop     dword ptr [rax+rax+00h]
0x180033ca5  lea     rcx, [rbp+var_20]
0x180033ca9  mov     ebx, eax
0x180033cab  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180033cb0  test    ebx, ebx
0x180033cb2  jz      short loc_180033CD1
0x180033cb4  mov     rcx, [rbp+18h]; this
0x180033cb8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180033cbf  mov     r9d, ebx; char *
0x180033cc2  mov     edx, 0E0h; void *
0x180033cc7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033ccc  jmp     loc_180033D9B
0x180033cd1  mov     rcx, [rdi]; HKEY
0x180033cd4  lea     rax, [rbp+arg_0]
0x180033cd8  lea     r9, [rsi+18h]; void *
0x180033cdc  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180033ce1  mov     r8d, 2; unsigned int
0x180033ce7  mov     [rbp+arg_0], 100h
0x180033cee  lea     rdx, aExtensionclass; "ExtensionClass"
0x180033cf5  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180033cfa  mov     ebx, eax
0x180033cfc  test    eax, eax
0x180033cfe  jns     short loc_180033D1C
0x180033d00  mov     edx, 0E3h; void *
0x180033d05  mov     rcx, [rbp+18h]; this
0x180033d09  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180033d10  mov     r9d, ebx; char *
0x180033d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033d18  mov     eax, ebx
0x180033d1a  jmp     short loc_180033D9B
0x180033d1c  mov     rcx, [rdi]; HKEY
0x180033d1f  lea     rax, [rbp+arg_0]
0x180033d23  and     [rbp+arg_18], 0
0x180033d27  lea     r9, [rbp+arg_18]; void *
0x180033d2b  mov     r8d, 10h; unsigned int
0x180033d31  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180033d36  lea     rdx, aTest; "Test"
0x180033d3d  mov     [rbp+arg_0], 4
0x180033d44  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180033d49  mov     ebx, eax
0x180033d4b  test    eax, eax
0x180033d4d  jns     short loc_180033D56
0x180033d4f  mov     edx, 0E7h
0x180033d54  jmp     short loc_180033D05
0x180033d56  cmp     [rbp+arg_18], 0
0x180033d5a  lea     r9, [rsi+14h]; void *
0x180033d5e  mov     rcx, [rdi]; HKEY
0x180033d61  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x180033d68  setnz   al
0x180033d6b  mov     [rbp+arg_0], 4
0x180033d72  mov     [rsi+10h], al
0x180033d75  mov     r8d, 10h; unsigned int
0x180033d7b  lea     rax, [rbp+arg_0]
0x180033d7f  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180033d84  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180033d89  mov     ebx, eax
0x180033d8b  test    eax, eax
0x180033d8d  jns     short loc_180033D99
0x180033d8f  mov     edx, 0EBh
0x180033d94  jmp     loc_180033D05
0x180033d99  xor     eax, eax
0x180033d9b  mov     rbx, [rsp+50h+arg_8]
0x180033da0  add     rsp, 50h
0x180033da4  pop     rdi
0x180033da5  pop     rsi
0x180033da6  pop     rbp
0x180033da7  retn
```

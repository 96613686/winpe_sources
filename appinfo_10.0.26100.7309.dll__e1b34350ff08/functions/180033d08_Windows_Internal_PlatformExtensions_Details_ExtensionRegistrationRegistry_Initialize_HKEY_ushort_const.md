# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x180033d08`
- end: `0x180033e59`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `337`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d6c0`

## callees

- `0x180007c78`
- `0x180018530`
- `0x180027150`
- `0x180033d08`
- `0x180038a48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033d49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033d49`

## string_xrefs

- `0x180033d68`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180033db9`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180033d9e`: `ExtensionClass`

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
0x180033d08  mov     [rsp-18h+arg_8], rbx
0x180033d0d  push    rbp
0x180033d0e  push    rsi
0x180033d0f  push    rdi
0x180033d10  mov     rbp, rsp
0x180033d13  sub     rsp, 50h
0x180033d17  and     [rbp+var_18], 0
0x180033d1c  lea     rdi, [rcx+8]
0x180033d20  mov     rsi, rcx
0x180033d23  mov     [rbp+var_20], rdi
0x180033d27  mov     rax, r8
0x180033d2a  mov     [rbp+var_10], 1
0x180033d2e  mov     r10, rdx
0x180033d31  lea     rcx, [rbp+var_18]
0x180033d35  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x180033d3a  mov     r9d, 20019h; samDesired
0x180033d40  mov     rcx, r10; hKey
0x180033d43  xor     r8d, r8d; ulOptions
0x180033d46  mov     rdx, rax; lpSubKey
0x180033d49  call    cs:__imp_RegOpenKeyExW
0x180033d50  nop     dword ptr [rax+rax+00h]
0x180033d55  lea     rcx, [rbp+var_20]
0x180033d59  mov     ebx, eax
0x180033d5b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180033d60  test    ebx, ebx
0x180033d62  jz      short loc_180033D81
0x180033d64  mov     rcx, [rbp+18h]; this
0x180033d68  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180033d6f  mov     r9d, ebx; char *
0x180033d72  mov     edx, 0E0h; void *
0x180033d77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033d7c  jmp     loc_180033E4B
0x180033d81  mov     rcx, [rdi]; HKEY
0x180033d84  lea     rax, [rbp+arg_0]
0x180033d88  lea     r9, [rsi+18h]; void *
0x180033d8c  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180033d91  mov     r8d, 2; unsigned int
0x180033d97  mov     [rbp+arg_0], 100h
0x180033d9e  lea     rdx, aExtensionclass; "ExtensionClass"
0x180033da5  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180033daa  mov     ebx, eax
0x180033dac  test    eax, eax
0x180033dae  jns     short loc_180033DCC
0x180033db0  mov     edx, 0E3h; void *
0x180033db5  mov     rcx, [rbp+18h]; this
0x180033db9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180033dc0  mov     r9d, ebx; char *
0x180033dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033dc8  mov     eax, ebx
0x180033dca  jmp     short loc_180033E4B
0x180033dcc  mov     rcx, [rdi]; HKEY
0x180033dcf  lea     rax, [rbp+arg_0]
0x180033dd3  and     [rbp+arg_18], 0
0x180033dd7  lea     r9, [rbp+arg_18]; void *
0x180033ddb  mov     r8d, 10h; unsigned int
0x180033de1  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180033de6  lea     rdx, aTest; "Test"
0x180033ded  mov     [rbp+arg_0], 4
0x180033df4  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180033df9  mov     ebx, eax
0x180033dfb  test    eax, eax
0x180033dfd  jns     short loc_180033E06
0x180033dff  mov     edx, 0E7h
0x180033e04  jmp     short loc_180033DB5
0x180033e06  cmp     [rbp+arg_18], 0
0x180033e0a  lea     r9, [rsi+14h]; void *
0x180033e0e  mov     rcx, [rdi]; HKEY
0x180033e11  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x180033e18  setnz   al
0x180033e1b  mov     [rbp+arg_0], 4
0x180033e22  mov     [rsi+10h], al
0x180033e25  mov     r8d, 10h; unsigned int
0x180033e2b  lea     rax, [rbp+arg_0]
0x180033e2f  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180033e34  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180033e39  mov     ebx, eax
0x180033e3b  test    eax, eax
0x180033e3d  jns     short loc_180033E49
0x180033e3f  mov     edx, 0EBh
0x180033e44  jmp     loc_180033DB5
0x180033e49  xor     eax, eax
0x180033e4b  mov     rbx, [rsp+50h+arg_8]
0x180033e50  add     rsp, 50h
0x180033e54  pop     rdi
0x180033e55  pop     rsi
0x180033e56  pop     rbp
0x180033e57  retn
```

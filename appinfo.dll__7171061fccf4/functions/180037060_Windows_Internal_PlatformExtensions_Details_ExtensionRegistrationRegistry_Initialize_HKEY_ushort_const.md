# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x180037060`
- end: `0x1800371b3`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `339`
- prototype: `__int64 __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180031e20`

## callees

- `0x18000720c`
- `0x180018dbc`
- `0x18002affc`
- `0x180037060`
- `0x18003b7b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800370a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800370a4`

## string_xrefs

- `0x1800370bd`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18003710e`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x1800370f3`: `ExtensionClass`

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

  v3 = (HKEY *)((char *)this + 8);
  v15 = 0;
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
0x180037060  mov     [rsp-18h+arg_8], rbx
0x180037065  push    rbp
0x180037066  push    rsi
0x180037067  push    rdi
0x180037068  mov     rbp, rsp
0x18003706b  sub     rsp, 50h
0x18003706f  lea     rdi, [rcx+8]
0x180037073  mov     [rbp+var_18], 0
0x18003707b  mov     rsi, rcx
0x18003707e  mov     [rbp+var_20], rdi
0x180037082  mov     rax, r8
0x180037085  mov     [rbp+var_10], 1
0x180037089  mov     r10, rdx
0x18003708c  lea     rcx, [rbp+var_18]
0x180037090  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x180037095  mov     r9d, 20019h; samDesired
0x18003709b  mov     rcx, r10; hKey
0x18003709e  xor     r8d, r8d; ulOptions
0x1800370a1  mov     rdx, rax; lpSubKey
0x1800370a4  call    cs:__imp_RegOpenKeyExW
0x1800370aa  lea     rcx, [rbp+var_20]
0x1800370ae  mov     ebx, eax
0x1800370b0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800370b5  test    ebx, ebx
0x1800370b7  jz      short loc_1800370D6
0x1800370b9  mov     rcx, [rbp+18h]; this
0x1800370bd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x1800370c4  mov     r9d, ebx; char *
0x1800370c7  mov     edx, 0E0h; void *
0x1800370cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800370d1  jmp     loc_1800371A6
0x1800370d6  mov     rcx, [rdi]; HKEY
0x1800370d9  lea     rax, [rbp+arg_0]
0x1800370dd  lea     r9, [rsi+18h]; void *
0x1800370e1  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800370e6  mov     r8d, 2; unsigned int
0x1800370ec  mov     [rbp+arg_0], 100h
0x1800370f3  lea     rdx, aExtensionclass; "ExtensionClass"
0x1800370fa  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x1800370ff  mov     ebx, eax
0x180037101  test    eax, eax
0x180037103  jns     short loc_180037124
0x180037105  mov     edx, 0E3h; void *
0x18003710a  mov     rcx, [rbp+18h]; this
0x18003710e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180037115  mov     r9d, ebx; char *
0x180037118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003711d  mov     eax, ebx
0x18003711f  jmp     loc_1800371A6
0x180037124  mov     rcx, [rdi]; HKEY
0x180037127  lea     rax, [rbp+arg_0]
0x18003712b  lea     r9, [rbp+arg_18]; void *
0x18003712f  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180037134  mov     r8d, 10h; unsigned int
0x18003713a  mov     [rbp+arg_18], 0
0x180037141  lea     rdx, aTest; "Test"
0x180037148  mov     [rbp+arg_0], 4
0x18003714f  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180037154  mov     ebx, eax
0x180037156  test    eax, eax
0x180037158  jns     short loc_180037161
0x18003715a  mov     edx, 0E7h
0x18003715f  jmp     short loc_18003710A
0x180037161  cmp     [rbp+arg_18], 0
0x180037165  lea     r9, [rsi+14h]; void *
0x180037169  mov     rcx, [rdi]; HKEY
0x18003716c  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x180037173  setnz   al
0x180037176  mov     [rbp+arg_0], 4
0x18003717d  mov     [rsi+10h], al
0x180037180  mov     r8d, 10h; unsigned int
0x180037186  lea     rax, [rbp+arg_0]
0x18003718a  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x18003718f  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180037194  mov     ebx, eax
0x180037196  test    eax, eax
0x180037198  jns     short loc_1800371A4
0x18003719a  mov     edx, 0EBh
0x18003719f  jmp     loc_18003710A
0x1800371a4  xor     eax, eax
0x1800371a6  mov     rbx, [rsp+50h+arg_8]
0x1800371ab  add     rsp, 50h
0x1800371af  pop     rdi
0x1800371b0  pop     rsi
0x1800371b1  pop     rbp
0x1800371b2  retn
```

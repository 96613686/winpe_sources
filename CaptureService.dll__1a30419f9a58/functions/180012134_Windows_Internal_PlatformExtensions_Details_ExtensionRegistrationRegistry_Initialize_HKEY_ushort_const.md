# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x180012134`
- end: `0x180012287`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `339`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180010700`

## callees

- `0x18000907c`
- `0x18000de44`
- `0x180012134`
- `0x180014800`
- `0x180017494`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012178`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012178`

## string_xrefs

- `0x1800121c7`: `ExtensionClass`
- `0x180012191`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800121e2`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
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
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
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
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)RegValue,
      phkResulta);
    return RegValue;
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
0x180012134  mov     [rsp-18h+arg_8], rbx
0x180012139  push    rbp
0x18001213a  push    rsi
0x18001213b  push    rdi
0x18001213c  mov     rbp, rsp
0x18001213f  sub     rsp, 50h
0x180012143  lea     rdi, [rcx+8]
0x180012147  mov     [rbp+var_18], 0
0x18001214f  mov     rsi, rcx
0x180012152  mov     [rbp+var_20], rdi
0x180012156  mov     rax, r8
0x180012159  mov     [rbp+var_10], 1
0x18001215d  mov     r10, rdx
0x180012160  lea     rcx, [rbp+var_18]
0x180012164  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x180012169  mov     r9d, 20019h; samDesired
0x18001216f  mov     rcx, r10; hKey
0x180012172  xor     r8d, r8d; ulOptions
0x180012175  mov     rdx, rax; lpSubKey
0x180012178  call    cs:__imp_RegOpenKeyExW
0x18001217e  lea     rcx, [rbp+var_20]
0x180012182  mov     ebx, eax
0x180012184  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180012189  test    ebx, ebx
0x18001218b  jz      short loc_1800121AA
0x18001218d  mov     rcx, [rbp+18h]; this
0x180012191  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180012198  mov     r9d, ebx; char *
0x18001219b  mov     edx, 0E0h; void *
0x1800121a0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800121a5  jmp     loc_18001227A
0x1800121aa  mov     rcx, [rdi]; HKEY
0x1800121ad  lea     rax, [rbp+arg_0]
0x1800121b1  lea     r9, [rsi+18h]; void *
0x1800121b5  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800121ba  mov     r8d, 2; unsigned int
0x1800121c0  mov     [rbp+arg_0], 100h
0x1800121c7  lea     rdx, aExtensionclass; "ExtensionClass"
0x1800121ce  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x1800121d3  mov     ebx, eax
0x1800121d5  test    eax, eax
0x1800121d7  jns     short loc_1800121F8
0x1800121d9  mov     edx, 0E3h; void *
0x1800121de  mov     rcx, [rbp+18h]; this
0x1800121e2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800121e9  mov     r9d, ebx; char *
0x1800121ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800121f1  mov     eax, ebx
0x1800121f3  jmp     loc_18001227A
0x1800121f8  mov     rcx, [rdi]; HKEY
0x1800121fb  lea     rax, [rbp+arg_0]
0x1800121ff  lea     r9, [rbp+arg_18]; void *
0x180012203  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180012208  mov     r8d, 10h; unsigned int
0x18001220e  mov     [rbp+arg_18], 0
0x180012215  lea     rdx, aTest; "Test"
0x18001221c  mov     [rbp+arg_0], 4
0x180012223  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180012228  mov     ebx, eax
0x18001222a  test    eax, eax
0x18001222c  jns     short loc_180012235
0x18001222e  mov     edx, 0E7h
0x180012233  jmp     short loc_1800121DE
0x180012235  cmp     [rbp+arg_18], 0
0x180012239  lea     r9, [rsi+14h]; void *
0x18001223d  mov     rcx, [rdi]; HKEY
0x180012240  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x180012247  setnz   al
0x18001224a  mov     [rbp+arg_0], 4
0x180012251  mov     [rsi+10h], al
0x180012254  mov     r8d, 10h; unsigned int
0x18001225a  lea     rax, [rbp+arg_0]
0x18001225e  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180012263  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x180012268  mov     ebx, eax
0x18001226a  test    eax, eax
0x18001226c  jns     short loc_180012278
0x18001226e  mov     edx, 0EBh
0x180012273  jmp     loc_1800121DE
0x180012278  xor     eax, eax
0x18001227a  mov     rbx, [rsp+50h+arg_8]
0x18001227f  add     rsp, 50h
0x180012283  pop     rdi
0x180012284  pop     rsi
0x180012285  pop     rbp
0x180012286  retn
```

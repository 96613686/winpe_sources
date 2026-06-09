# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x180033fc8`
- end: `0x180034119`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `337`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d790`

## callees

- `0x180007c78`
- `0x180018530`
- `0x180027220`
- `0x180033fc8`
- `0x180038d88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034009`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034009`

## string_xrefs

- `0x180034028`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180034079`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18003405e`: `ExtensionClass`

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
0x180033fc8  mov     [rsp-18h+arg_8], rbx
0x180033fcd  push    rbp
0x180033fce  push    rsi
0x180033fcf  push    rdi
0x180033fd0  mov     rbp, rsp
0x180033fd3  sub     rsp, 50h
0x180033fd7  and     [rbp+var_18], 0
0x180033fdc  lea     rdi, [rcx+8]
0x180033fe0  mov     rsi, rcx
0x180033fe3  mov     [rbp+var_20], rdi
0x180033fe7  mov     rax, r8
0x180033fea  mov     [rbp+var_10], 1
0x180033fee  mov     r10, rdx
0x180033ff1  lea     rcx, [rbp+var_18]
0x180033ff5  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x180033ffa  mov     r9d, 20019h; samDesired
0x180034000  mov     rcx, r10; hKey
0x180034003  xor     r8d, r8d; ulOptions
0x180034006  mov     rdx, rax; lpSubKey
0x180034009  call    cs:__imp_RegOpenKeyExW
0x180034010  nop     dword ptr [rax+rax+00h]
0x180034015  lea     rcx, [rbp+var_20]
0x180034019  mov     ebx, eax
0x18003401b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180034020  test    ebx, ebx
0x180034022  jz      short loc_180034041
0x180034024  mov     rcx, [rbp+18h]; this
0x180034028  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003402f  mov     r9d, ebx; char *
0x180034032  mov     edx, 0E0h; void *
0x180034037  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003403c  jmp     loc_18003410B
0x180034041  mov     rcx, [rdi]; HKEY
0x180034044  lea     rax, [rbp+arg_0]
0x180034048  lea     r9, [rsi+18h]; void *
0x18003404c  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180034051  mov     r8d, 2; unsigned int
0x180034057  mov     [rbp+arg_0], 100h
0x18003405e  lea     rdx, aExtensionclass; "ExtensionClass"
0x180034065  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x18003406a  mov     ebx, eax
0x18003406c  test    eax, eax
0x18003406e  jns     short loc_18003408C
0x180034070  mov     edx, 0E3h; void *
0x180034075  mov     rcx, [rbp+18h]; this
0x180034079  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180034080  mov     r9d, ebx; char *
0x180034083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034088  mov     eax, ebx
0x18003408a  jmp     short loc_18003410B
0x18003408c  mov     rcx, [rdi]; HKEY
0x18003408f  lea     rax, [rbp+arg_0]
0x180034093  and     [rbp+arg_18], 0
0x180034097  lea     r9, [rbp+arg_18]; void *
0x18003409b  mov     r8d, 10h; unsigned int
0x1800340a1  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x1800340a6  lea     rdx, aTest; "Test"
0x1800340ad  mov     [rbp+arg_0], 4
0x1800340b4  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x1800340b9  mov     ebx, eax
0x1800340bb  test    eax, eax
0x1800340bd  jns     short loc_1800340C6
0x1800340bf  mov     edx, 0E7h
0x1800340c4  jmp     short loc_180034075
0x1800340c6  cmp     [rbp+arg_18], 0
0x1800340ca  lea     r9, [rsi+14h]; void *
0x1800340ce  mov     rcx, [rdi]; HKEY
0x1800340d1  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x1800340d8  setnz   al
0x1800340db  mov     [rbp+arg_0], 4
0x1800340e2  mov     [rsi+10h], al
0x1800340e5  mov     r8d, 10h; unsigned int
0x1800340eb  lea     rax, [rbp+arg_0]
0x1800340ef  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x1800340f4  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x1800340f9  mov     ebx, eax
0x1800340fb  test    eax, eax
0x1800340fd  jns     short loc_180034109
0x1800340ff  mov     edx, 0EBh
0x180034104  jmp     loc_180034075
0x180034109  xor     eax, eax
0x18003410b  mov     rbx, [rsp+50h+arg_8]
0x180034110  add     rsp, 50h
0x180034114  pop     rdi
0x180034115  pop     rsi
0x180034116  pop     rbp
0x180034117  retn
```

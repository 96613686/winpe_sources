# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x180040228`
- end: `0x18004037b`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `339`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18003f810`

## callees

- `0x180006eac`
- `0x18002b748`
- `0x18003e854`
- `0x180040228`
- `0x180042ae0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004026c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004026c`

## string_xrefs

- `0x180040285`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800402d6`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800402bb`: `ExtensionClass`

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
0x180040228  mov     [rsp-18h+arg_8], rbx
0x18004022d  push    rbp
0x18004022e  push    rsi
0x18004022f  push    rdi
0x180040230  mov     rbp, rsp
0x180040233  sub     rsp, 50h
0x180040237  lea     rdi, [rcx+8]
0x18004023b  mov     [rbp+var_18], 0
0x180040243  mov     rsi, rcx
0x180040246  mov     [rbp+var_20], rdi
0x18004024a  mov     rax, r8
0x18004024d  mov     [rbp+var_10], 1
0x180040251  mov     r10, rdx
0x180040254  lea     rcx, [rbp+var_18]
0x180040258  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x18004025d  mov     r9d, 20019h; samDesired
0x180040263  mov     rcx, r10; hKey
0x180040266  xor     r8d, r8d; ulOptions
0x180040269  mov     rdx, rax; lpSubKey
0x18004026c  call    cs:__imp_RegOpenKeyExW
0x180040272  lea     rcx, [rbp+var_20]
0x180040276  mov     ebx, eax
0x180040278  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18004027d  test    ebx, ebx
0x18004027f  jz      short loc_18004029E
0x180040281  mov     rcx, [rbp+18h]; this
0x180040285  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18004028c  mov     r9d, ebx; char *
0x18004028f  mov     edx, 0E0h; void *
0x180040294  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040299  jmp     loc_18004036E
0x18004029e  mov     rcx, [rdi]; HKEY
0x1800402a1  lea     rax, [rbp+arg_0]
0x1800402a5  lea     r9, [rsi+18h]; void *
0x1800402a9  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800402ae  mov     r8d, 2; unsigned int
0x1800402b4  mov     [rbp+arg_0], 100h
0x1800402bb  lea     rdx, aExtensionclass; "ExtensionClass"
0x1800402c2  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x1800402c7  mov     ebx, eax
0x1800402c9  test    eax, eax
0x1800402cb  jns     short loc_1800402EC
0x1800402cd  mov     edx, 0E3h; void *
0x1800402d2  mov     rcx, [rbp+18h]; this
0x1800402d6  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800402dd  mov     r9d, ebx; char *
0x1800402e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402e5  mov     eax, ebx
0x1800402e7  jmp     loc_18004036E
0x1800402ec  mov     rcx, [rdi]; HKEY
0x1800402ef  lea     rax, [rbp+arg_0]
0x1800402f3  lea     r9, [rbp+arg_18]; void *
0x1800402f7  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x1800402fc  mov     r8d, 10h; unsigned int
0x180040302  mov     [rbp+arg_18], 0
0x180040309  lea     rdx, aTest; "Test"
0x180040310  mov     [rbp+arg_0], 4
0x180040317  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x18004031c  mov     ebx, eax
0x18004031e  test    eax, eax
0x180040320  jns     short loc_180040329
0x180040322  mov     edx, 0E7h
0x180040327  jmp     short loc_1800402D2
0x180040329  cmp     [rbp+arg_18], 0
0x18004032d  lea     r9, [rsi+14h]; void *
0x180040331  mov     rcx, [rdi]; HKEY
0x180040334  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x18004033b  setnz   al
0x18004033e  mov     [rbp+arg_0], 4
0x180040345  mov     [rsi+10h], al
0x180040348  mov     r8d, 10h; unsigned int
0x18004034e  lea     rax, [rbp+arg_0]
0x180040352  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x180040357  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x18004035c  mov     ebx, eax
0x18004035e  test    eax, eax
0x180040360  jns     short loc_18004036C
0x180040362  mov     edx, 0EBh
0x180040367  jmp     loc_1800402D2
0x18004036c  xor     eax, eax
0x18004036e  mov     rbx, [rsp+50h+arg_8]
0x180040373  add     rsp, 50h
0x180040377  pop     rdi
0x180040378  pop     rsi
0x180040379  pop     rbp
0x18004037a  retn
```

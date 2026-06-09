# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x14000e760`
- end: `0x14000e8b3`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `339`
- prototype: `int __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c730`

## callees

- `0x140008f70`
- `0x14000e760`
- `0x1400136fc`
- `0x140013720`
- `0x140016e40`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000e7a4`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e7a4`

## string_xrefs

- `0x14000e7bd`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x14000e80e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x14000e7f3`: `ExtensionClass`

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
0x14000e760  mov     [rsp-18h+arg_8], rbx
0x14000e765  push    rbp
0x14000e766  push    rsi
0x14000e767  push    rdi
0x14000e768  mov     rbp, rsp
0x14000e76b  sub     rsp, 50h
0x14000e76f  lea     rdi, [rcx+8]
0x14000e773  mov     [rbp+var_18], 0
0x14000e77b  mov     rsi, rcx
0x14000e77e  mov     [rbp+var_20], rdi
0x14000e782  mov     rax, r8
0x14000e785  mov     [rbp+var_10], 1
0x14000e789  mov     r10, rdx
0x14000e78c  lea     rcx, [rbp+var_18]
0x14000e790  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x14000e795  mov     r9d, 20019h; samDesired
0x14000e79b  mov     rcx, r10; hKey
0x14000e79e  xor     r8d, r8d; ulOptions
0x14000e7a1  mov     rdx, rax; lpSubKey
0x14000e7a4  call    cs:__imp_RegOpenKeyExW
0x14000e7aa  lea     rcx, [rbp+var_20]
0x14000e7ae  mov     ebx, eax
0x14000e7b0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14000e7b5  test    ebx, ebx
0x14000e7b7  jz      short loc_14000E7D6
0x14000e7b9  mov     rcx, [rbp+18h]; this
0x14000e7bd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000e7c4  mov     r9d, ebx; char *
0x14000e7c7  mov     edx, 0E0h; void *
0x14000e7cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000e7d1  jmp     loc_14000E8A6
0x14000e7d6  mov     rcx, [rdi]; HKEY
0x14000e7d9  lea     rax, [rbp+arg_0]
0x14000e7dd  lea     r9, [rsi+18h]; void *
0x14000e7e1  mov     qword ptr [rsp+50h+phkResult], rax; int
0x14000e7e6  mov     r8d, 2; unsigned int
0x14000e7ec  mov     [rbp+arg_0], 100h
0x14000e7f3  lea     rdx, aExtensionclass; "ExtensionClass"
0x14000e7fa  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x14000e7ff  mov     ebx, eax
0x14000e801  test    eax, eax
0x14000e803  jns     short loc_14000E824
0x14000e805  mov     edx, 0E3h; void *
0x14000e80a  mov     rcx, [rbp+18h]; this
0x14000e80e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000e815  mov     r9d, ebx; char *
0x14000e818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e81d  mov     eax, ebx
0x14000e81f  jmp     loc_14000E8A6
0x14000e824  mov     rcx, [rdi]; HKEY
0x14000e827  lea     rax, [rbp+arg_0]
0x14000e82b  lea     r9, [rbp+arg_18]; void *
0x14000e82f  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x14000e834  mov     r8d, 10h; unsigned int
0x14000e83a  mov     [rbp+arg_18], 0
0x14000e841  lea     rdx, aTest; "Test"
0x14000e848  mov     [rbp+arg_0], 4
0x14000e84f  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x14000e854  mov     ebx, eax
0x14000e856  test    eax, eax
0x14000e858  jns     short loc_14000E861
0x14000e85a  mov     edx, 0E7h
0x14000e85f  jmp     short loc_14000E80A
0x14000e861  cmp     [rbp+arg_18], 0
0x14000e865  lea     r9, [rsi+14h]; void *
0x14000e869  mov     rcx, [rdi]; HKEY
0x14000e86c  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x14000e873  setnz   al
0x14000e876  mov     [rbp+arg_0], 4
0x14000e87d  mov     [rsi+10h], al
0x14000e880  mov     r8d, 10h; unsigned int
0x14000e886  lea     rax, [rbp+arg_0]
0x14000e88a  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x14000e88f  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x14000e894  mov     ebx, eax
0x14000e896  test    eax, eax
0x14000e898  jns     short loc_14000E8A4
0x14000e89a  mov     edx, 0EBh
0x14000e89f  jmp     loc_14000E80A
0x14000e8a4  xor     eax, eax
0x14000e8a6  mov     rbx, [rsp+50h+arg_8]
0x14000e8ab  add     rsp, 50h
0x14000e8af  pop     rdi
0x14000e8b0  pop     rsi
0x14000e8b1  pop     rbp
0x14000e8b2  retn
```

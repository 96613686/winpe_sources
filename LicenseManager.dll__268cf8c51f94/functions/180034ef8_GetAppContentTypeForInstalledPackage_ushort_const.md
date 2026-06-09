# GetAppContentTypeForInstalledPackage(ushort const *)

- ea: `0x180034ef8`
- end: `0x1800351f7`
- name: `?GetAppContentTypeForInstalledPackage@@YA?AW4AppContentType@@PEBG@Z`
- size: `767`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180034930`
- `0x180034b30`
- `0x18006bf60`
- `0x1800928d0`
- `0x180092ba0`

## callees

- `0x180013b50`
- `0x180034ef8`
- `0x180035200`
- `0x1800352d0`
- `0x1800593bc`
- `0x180075e60`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034fa3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800351f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034fa3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800351f0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180034f28`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180034f28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180034f8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180034f8d`

## string_xrefs

- `0x18003510f`: `GetAppContentTypeForInstalledPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetAppContentTypeForInstalledPackage(const WCHAR *a1)
{
  unsigned __int64 v3; // rdx
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int Format; // [rsp+20h] [rbp-49h]
  int Formata; // [rsp+20h] [rbp-49h]
  int v17; // [rsp+40h] [rbp-29h] BYREF
  int v18; // [rsp+44h] [rbp-25h] BYREF
  int v19; // [rsp+48h] [rbp-21h] BYREF
  __int64 v20; // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+58h] [rbp-11h] BYREF
  __int64 v22; // [rsp+60h] [rbp-9h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1h] BYREF
  __int64 v24; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v18 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v18, 0);
  if ( v18 == 5 )
    return 0;
  GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(&v23);
  string = 0;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 > 0xFFFFFFFF || (int)v3 + 1 < (unsigned int)v3 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1800351F6LL);
  }
  v4 = WindowsCreateStringReference(a1, v3, &hstringHeader, &string);
  if ( v4 < 0 )
    RaiseException(v4, 1u, 0, 0);
  v20 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v23 + 176LL))(v23, string, &v20);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v5,
      Format);
  v17 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 128LL))(v20, &v17);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v6,
      Format);
  if ( v17 == 16 )
  {
    v7 = 4;
  }
  else
  {
    v19 = 0;
    v24 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 976LL))(v20, &v24);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        (const char *)(unsigned int)v8,
        Format);
    v21 = 0;
    GetActivationFactory<Windows::Internal::StateRepository::ITargetDeviceFamilyStatics>(&v22);
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, v24, &v21);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        (const char *)(unsigned int)v9,
        Format);
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 88LL))(v21, &v19);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        (const char *)(unsigned int)v10,
        Format);
    if ( v17 != 1 && v17 != 2 && v17 != 4 && v17 != 8 && v17 != 32 )
    {
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        0x12Cu,
        "GetAppContentTypeForInstalledPackage",
        (wchar_t *)L"Unhandled package type=%d for package full name=[%ws].\n");
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        (const char *)0x80070032LL,
        Formata);
    }
    if ( v19 == 1 )
    {
      v7 = 1;
    }
    else if ( (unsigned int)(v19 - 11) < 2 )
    {
      v7 = 6;
    }
    else
    {
      v7 = 3;
    }
    v11 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  v13 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  string = 0;
  v14 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return v7;
}

```

## disassembly

```asm
0x180034ef8  push    rbp
0x180034efa  push    rbx
0x180034efb  push    rsi
0x180034efc  push    rdi
0x180034efd  lea     rbp, [rsp-3Fh]
0x180034f02  sub     rsp, 0A8h
0x180034f09  mov     rax, cs:__security_cookie
0x180034f10  xor     rax, rsp
0x180034f13  mov     [rbp+57h+var_28], rax
0x180034f17  mov     rdi, rcx
0x180034f1a  xor     esi, esi
0x180034f1c  mov     [rbp+57h+var_7C], esi
0x180034f1f  xor     r8d, r8d
0x180034f22  lea     rdx, [rbp+57h+var_7C]
0x180034f26  xor     ecx, ecx
0x180034f28  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180034f2e  cmp     [rbp+57h+var_7C], 5
0x180034f32  jnz     short loc_180034F4E
0x180034f34  xor     eax, eax
0x180034f36  mov     rcx, [rbp+57h+var_28]
0x180034f3a  xor     rcx, rsp; StackCookie
0x180034f3d  call    __security_check_cookie
0x180034f42  add     rsp, 0A8h
0x180034f49  pop     rdi
0x180034f4a  pop     rsi
0x180034f4b  pop     rbx
0x180034f4c  pop     rbp
0x180034f4d  retn
0x180034f4e  lea     rcx, [rbp+57h+var_58]
0x180034f52  call    ??$GetActivationFactory@UIPackageStatics@StateRepository@Internal@Windows@@@@YA?AV?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEBG@Z; GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(ushort const *)
0x180034f57  nop
0x180034f58  mov     [rbp+57h+string], rsi
0x180034f5c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180034f60  inc     rdx; length
0x180034f63  cmp     [rdi+rdx*2], si
0x180034f67  jnz     short loc_180034F60
0x180034f69  mov     eax, 0FFFFFFFFh
0x180034f6e  cmp     rdx, rax
0x180034f71  ja      loc_1800351E1
0x180034f77  lea     eax, [rdx+1]
0x180034f7a  cmp     eax, edx
0x180034f7c  jb      loc_1800351E1
0x180034f82  lea     r9, [rbp+57h+string]; string
0x180034f86  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180034f8a  mov     rcx, rdi; sourceString
0x180034f8d  call    cs:__imp_WindowsCreateStringReference
0x180034f93  test    eax, eax
0x180034f95  jns     short loc_180034FAA
0x180034f97  xor     r9d, r9d; lpArguments
0x180034f9a  xor     r8d, r8d; nNumberOfArguments
0x180034f9d  lea     edx, [r9+1]; dwExceptionFlags
0x180034fa1  mov     ecx, eax; dwExceptionCode
0x180034fa3  call    cs:__imp_RaiseException
0x180034fa9  nop
0x180034faa  mov     [rbp+57h+var_70], rsi
0x180034fae  mov     rcx, [rbp+57h+var_58]
0x180034fb2  mov     rax, [rcx]
0x180034fb5  lea     r8, [rbp+57h+var_70]
0x180034fb9  mov     rdx, [rbp+57h+string]
0x180034fbd  mov     rax, [rax+0B0h]
0x180034fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fc9  mov     rcx, [rbp+5Fh]; this
0x180034fcd  test    eax, eax
0x180034fcf  jns     short loc_180034FE6
0x180034fd1  mov     r9d, eax; char *
0x180034fd4  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x180034fdb  mov     edx, 0F8h; void *
0x180034fe0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034fe6  mov     [rbp+57h+var_80], esi
0x180034fe9  mov     rcx, [rbp+57h+var_70]
0x180034fed  mov     rax, [rcx]
0x180034ff0  lea     rdx, [rbp+57h+var_80]
0x180034ff4  mov     rax, [rax+80h]
0x180034ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035000  mov     rcx, [rbp+5Fh]; this
0x180035004  test    eax, eax
0x180035006  jns     short loc_18003501D
0x180035008  mov     r9d, eax; char *
0x18003500b  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x180035012  mov     edx, 0FBh; void *
0x180035017  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003501d  cmp     [rbp+57h+var_80], 10h
0x180035021  jnz     short loc_18003502D
0x180035023  mov     ebx, 4
0x180035028  jmp     loc_1800351A2
0x18003502d  mov     [rbp+57h+var_78], esi
0x180035030  mov     [rbp+57h+var_50], rsi
0x180035034  mov     rcx, [rbp+57h+var_70]
0x180035038  mov     rax, [rcx]
0x18003503b  lea     rdx, [rbp+57h+var_50]
0x18003503f  mov     rax, [rax+3D0h]
0x180035046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003504b  mov     rcx, [rbp+5Fh]; this
0x18003504f  test    eax, eax
0x180035051  jns     short loc_180035068
0x180035053  mov     r9d, eax; char *
0x180035056  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003505d  mov     edx, 107h; void *
0x180035062  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035068  mov     [rbp+57h+var_68], rsi
0x18003506c  lea     rcx, [rbp+57h+var_60]
0x180035070  call    ??$GetActivationFactory@UITargetDeviceFamilyStatics@StateRepository@Internal@Windows@@@@YA?AV?$ComPtr@UITargetDeviceFamilyStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEBG@Z; GetActivationFactory<Windows::Internal::StateRepository::ITargetDeviceFamilyStatics>(ushort const *)
0x180035075  nop
0x180035076  mov     rcx, [rbp+57h+var_60]
0x18003507a  mov     rax, [rcx]
0x18003507d  lea     r8, [rbp+57h+var_68]
0x180035081  mov     rdx, [rbp+57h+var_50]
0x180035085  mov     rax, [rax+48h]
0x180035089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003508e  mov     rcx, [rbp+5Fh]; this
0x180035092  test    eax, eax
0x180035094  jns     short loc_1800350AB
0x180035096  mov     r9d, eax; char *
0x180035099  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800350a0  mov     edx, 10Ch; void *
0x1800350a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800350ab  mov     rcx, [rbp+57h+var_68]
0x1800350af  mov     rax, [rcx]
0x1800350b2  lea     rdx, [rbp+57h+var_78]
0x1800350b6  mov     rax, [rax+58h]
0x1800350ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350bf  mov     rcx, [rbp+5Fh]; this
0x1800350c3  test    eax, eax
0x1800350c5  jns     short loc_1800350DC
0x1800350c7  mov     r9d, eax; char *
0x1800350ca  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800350d1  mov     edx, 10Eh; void *
0x1800350d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800350dc  mov     ecx, [rbp+57h+var_80]
0x1800350df  mov     eax, ecx
0x1800350e1  sub     eax, 1
0x1800350e4  jz      short loc_180035149
0x1800350e6  sub     eax, 1
0x1800350e9  jz      short loc_180035149
0x1800350eb  sub     eax, 2
0x1800350ee  jz      short loc_180035149
0x1800350f0  sub     eax, 4
0x1800350f3  jz      short loc_180035149
0x1800350f5  cmp     eax, 18h
0x1800350f8  jz      short loc_180035149
0x1800350fa  mov     [rsp+0C0h+var_90], rdi
0x1800350ff  mov     [rsp+0C0h+var_98], ecx
0x180035103  lea     rax, aUnhandledPacka; "Unhandled package type=%d for package f"...
0x18003510a  mov     [rsp+0C0h+Format], rax; int
0x18003510f  lea     r9, aGetappcontentt; "GetAppContentTypeForInstalledPackage"
0x180035116  mov     r8d, 12Ch; unsigned int
0x18003511c  lea     rdx, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x180035123  mov     ecx, 1; unsigned int
0x180035128  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18003512d  mov     rcx, [rbp+5Fh]; this
0x180035131  mov     r9d, 80070032h; char *
0x180035137  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003513e  mov     edx, 12Dh; void *
0x180035143  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035149  mov     ecx, [rbp+57h+var_78]
0x18003514c  sub     ecx, 1
0x18003514f  jz      short loc_180035169
0x180035151  sub     ecx, 0Ah
0x180035154  jz      short loc_180035162
0x180035156  cmp     ecx, 1
0x180035159  jz      short loc_180035162
0x18003515b  mov     ebx, 3
0x180035160  jmp     short loc_18003516E
0x180035162  mov     ebx, 6
0x180035167  jmp     short loc_18003516E
0x180035169  mov     ebx, 1
0x18003516e  mov     rcx, [rbp+57h+var_60]
0x180035172  test    rcx, rcx
0x180035175  jz      short loc_180035188
0x180035177  mov     [rbp+57h+var_60], rsi
0x18003517b  mov     rax, [rcx]
0x18003517e  mov     rax, [rax+10h]
0x180035182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035187  nop
0x180035188  mov     rcx, [rbp+57h+var_68]
0x18003518c  test    rcx, rcx
0x18003518f  jz      short loc_1800351A2
0x180035191  mov     [rbp+57h+var_68], rsi
0x180035195  mov     rax, [rcx]
0x180035198  mov     rax, [rax+10h]
0x18003519c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351a1  nop
0x1800351a2  mov     rcx, [rbp+57h+var_70]
0x1800351a6  test    rcx, rcx
0x1800351a9  jz      short loc_1800351BC
0x1800351ab  mov     [rbp+57h+var_70], rsi
0x1800351af  mov     rax, [rcx]
0x1800351b2  mov     rax, [rax+10h]
0x1800351b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351bb  nop
0x1800351bc  mov     [rbp+57h+string], rsi
0x1800351c0  mov     rcx, [rbp+57h+var_58]
0x1800351c4  test    rcx, rcx
0x1800351c7  jz      short loc_1800351DA
0x1800351c9  mov     [rbp+57h+var_58], rsi
0x1800351cd  mov     rdx, [rcx]
0x1800351d0  mov     rax, [rdx+10h]
0x1800351d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351d9  nop
0x1800351da  mov     eax, ebx
0x1800351dc  jmp     loc_180034F36
0x1800351e1  xor     r9d, r9d; lpArguments
0x1800351e4  xor     r8d, r8d; nNumberOfArguments
0x1800351e7  lea     edx, [r9+1]; dwExceptionFlags
0x1800351eb  mov     ecx, 80070216h; dwExceptionCode
0x1800351f0  call    cs:__imp_RaiseException
```

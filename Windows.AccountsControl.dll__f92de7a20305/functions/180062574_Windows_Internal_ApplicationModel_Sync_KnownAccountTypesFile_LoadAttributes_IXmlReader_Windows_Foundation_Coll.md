# Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAttributes(IXmlReader *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> *)

- ea: `0x180062574`
- end: `0x180062723`
- name: `?LoadAttributes@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUIXmlReader@@PEAV?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@4Collections@Foundation@5@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062ac4`

## callees

- `0x180006eac`
- `0x180007f68`
- `0x1800181ec`
- `0x180062574`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006261b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006261b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006262f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006262f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAttributes(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  int i; // eax
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  const WCHAR *v10; // rbx
  __int64 (__fastcall *v11)(__int64 *, HSTRING, char *); // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64 *, _QWORD, __int64, _BYTE *); // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdx
  int v19; // [rsp+20h] [rbp-39h]
  char v20; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v21[7]; // [rsp+31h] [rbp-28h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-21h] BYREF
  PCWSTR sourceString; // [rsp+40h] [rbp-19h] BYREF
  HSTRING string; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER v26; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  for ( i = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 64))(a2);
        ;
        i = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 72))(a2) )
  {
    v6 = i;
    if ( i )
      break;
    v7 = *a2;
    sourceString = 0;
    if ( (*(int (__fastcall **)(__int64 *, PCWSTR *, _QWORD))(v7 + 112))(a2, &sourceString, 0) >= 0 )
    {
      v8 = *a3;
      v9 = -1;
      v10 = sourceString;
      v20 = 0;
      length[0] = 0;
      v11 = *(__int64 (__fastcall **)(__int64 *, HSTRING, char *))(v8 + 64);
      do
        ++v9;
      while ( sourceString[v9] );
      if ( (int)ULongLongToUInt(v9, length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(v10, length[0], &hstringHeader, &string);
      v6 = v11(a3, string, &v20);
      if ( v6 < 0 )
      {
        v17 = 390;
        goto LABEL_15;
      }
      if ( v20 )
      {
        v12 = *a2;
        *(_QWORD *)length = 0;
        if ( (*(int (__fastcall **)(__int64 *, UINT32 *, _QWORD))(v12 + 128))(a2, length, 0) >= 0 )
        {
          v13 = *a3;
          v21[0] = 0;
          v14 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _BYTE *))(v13 + 80);
          v15 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference((HSTRING_HEADER *)&string) + 24);
          v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v26);
          v6 = v14(a3, *(_QWORD *)(v16 + 24), v15, v21);
          if ( v6 < 0 )
          {
            v17 = 398;
LABEL_15:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\knownaccounttypesfile.cpp",
              (const char *)(unsigned int)v6,
              v19);
            return (unsigned int)v6;
          }
        }
      }
    }
  }
  if ( i < 0 )
  {
    v17 = 406;
    goto LABEL_15;
  }
  return 0;
}

```

## disassembly

```asm
0x180062574  mov     [rsp-8+arg_0], rbx
0x180062579  push    rbp
0x18006257a  push    rsi
0x18006257b  push    rdi
0x18006257c  push    r14
0x18006257e  push    r15
0x180062580  lea     rbp, [rsp-37h]
0x180062585  sub     rsp, 90h
0x18006258c  mov     rax, cs:__security_cookie
0x180062593  xor     rax, rsp
0x180062596  mov     [rbp+57h+var_28], rax
0x18006259a  mov     rax, [rdx]
0x18006259d  mov     rcx, rdx
0x1800625a0  mov     r14, r8
0x1800625a3  mov     rsi, rdx
0x1800625a6  mov     rax, [rax+40h]
0x1800625aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625af  xor     r15d, r15d
0x1800625b2  mov     ebx, eax
0x1800625b4  test    eax, eax
0x1800625b6  jnz     loc_1800626F5
0x1800625bc  mov     rax, [rsi]
0x1800625bf  lea     rdx, [rbp+57h+sourceString]
0x1800625c3  xor     r8d, r8d
0x1800625c6  mov     [rbp+57h+sourceString], r15
0x1800625ca  mov     rcx, rsi
0x1800625cd  mov     rax, [rax+70h]
0x1800625d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625d6  test    eax, eax
0x1800625d8  js      loc_1800626BE
0x1800625de  mov     rax, [r14]
0x1800625e1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800625e5  mov     rbx, [rbp+57h+sourceString]
0x1800625e9  mov     [rbp+57h+var_80], r15b
0x1800625ed  mov     [rbp+57h+length], r15d
0x1800625f1  mov     rdi, [rax+40h]
0x1800625f5  inc     rcx; unsigned __int64
0x1800625f8  cmp     [rbx+rcx*2], r15w
0x1800625fd  jnz     short loc_1800625F5
0x1800625ff  lea     rdx, [rbp+57h+length]; unsigned int *
0x180062603  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180062608  test    eax, eax
0x18006260a  jns     short loc_180062621
0x18006260c  xor     r9d, r9d; lpArguments
0x18006260f  xor     r8d, r8d; nNumberOfArguments
0x180062612  mov     ecx, 0C000000Dh; dwExceptionCode
0x180062617  lea     edx, [r9+1]; dwExceptionFlags
0x18006261b  call    cs:__imp_RaiseException
0x180062621  mov     edx, [rbp+57h+length]; length
0x180062624  lea     r9, [rbp+57h+string]; string
0x180062628  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006262c  mov     rcx, rbx; sourceString
0x18006262f  call    cs:__imp_WindowsCreateStringReference
0x180062635  mov     rdx, [rbp+57h+string]
0x180062639  lea     r8, [rbp+57h+var_80]
0x18006263d  mov     rcx, r14
0x180062640  mov     rax, rdi
0x180062643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062648  mov     ebx, eax
0x18006264a  test    eax, eax
0x18006264c  js      loc_1800626D9
0x180062652  cmp     [rbp+57h+var_80], r15b
0x180062656  jz      short loc_1800626BE
0x180062658  mov     rax, [rsi]
0x18006265b  lea     rdx, [rbp+57h+length]
0x18006265f  xor     r8d, r8d
0x180062662  mov     qword ptr [rbp+57h+length], r15
0x180062666  mov     rcx, rsi
0x180062669  mov     rax, [rax+80h]
0x180062670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062675  test    eax, eax
0x180062677  js      short loc_1800626BE
0x180062679  mov     rax, [r14]
0x18006267c  lea     rdx, [rbp+57h+length]
0x180062680  lea     rcx, [rbp+57h+string]; hstringHeader
0x180062684  mov     [rbp+57h+var_7F], r15b
0x180062688  mov     rdi, [rax+50h]
0x18006268c  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x180062691  lea     rdx, [rbp+57h+sourceString]
0x180062695  lea     rcx, [rbp+57h+var_48]; hstringHeader
0x180062699  mov     rbx, [rax+18h]
0x18006269d  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x1800626a2  lea     r9, [rbp+57h+var_7F]
0x1800626a6  mov     r8, rbx
0x1800626a9  mov     rcx, r14
0x1800626ac  mov     rdx, [rax+18h]
0x1800626b0  mov     rax, rdi
0x1800626b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626b8  mov     ebx, eax
0x1800626ba  test    eax, eax
0x1800626bc  js      short loc_1800626D2
0x1800626be  mov     rax, [rsi]
0x1800626c1  mov     rcx, rsi
0x1800626c4  mov     rax, [rax+48h]
0x1800626c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626cd  jmp     loc_1800625B2
0x1800626d2  mov     edx, 18Eh
0x1800626d7  jmp     short loc_1800626DE
0x1800626d9  mov     edx, 186h; void *
0x1800626de  mov     rcx, [rbp+5Fh]; this
0x1800626e2  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800626e9  mov     r9d, ebx; char *
0x1800626ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800626f1  mov     eax, ebx
0x1800626f3  jmp     short loc_180062700
0x1800626f5  jns     short loc_1800626FE
0x1800626f7  mov     edx, 196h
0x1800626fc  jmp     short loc_1800626DE
0x1800626fe  xor     eax, eax
0x180062700  mov     rcx, [rbp+57h+var_28]
0x180062704  xor     rcx, rsp; StackCookie
0x180062707  call    __security_check_cookie
0x18006270c  mov     rbx, [rsp+0B0h+arg_0]
0x180062714  add     rsp, 90h
0x18006271b  pop     r15
0x18006271d  pop     r14
0x18006271f  pop     rdi
0x180062720  pop     rsi
0x180062721  pop     rbp
0x180062722  retn
```

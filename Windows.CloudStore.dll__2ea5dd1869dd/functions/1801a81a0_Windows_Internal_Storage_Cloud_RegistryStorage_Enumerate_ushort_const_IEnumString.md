# Windows::Internal::Storage::Cloud::RegistryStorage::Enumerate(ushort const *,IEnumString * *)

- ea: `0x1801a81a0`
- end: `0x1801a83ea`
- name: `?Enumerate@RegistryStorage@Cloud@Storage@Internal@Windows@@UEAAJPEBGPEAPEAUIEnumString@@@Z`
- size: `586`
- prototype: `int(Windows::Internal::Storage::Cloud::RegistryStorage *__hidden this, const unsigned __int16 *, struct IEnumString **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f4b4`
- `0x18003e670`
- `0x18003f6c4`
- `0x180085df8`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801201a0`
- `0x1801a8174`
- `0x1801a81a0`
- `0x1801c273c`
- `0x1801c27ec`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a827f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a827f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801a82ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801a82ff`

## string_xrefs

- `0x1801a81f5`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x1801a8238`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x1801a8297`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x1801a8335`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x1801a837b`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Storage::Cloud::RegistryStorage::Enumerate(
        HKEY *this,
        const unsigned __int16 *a2,
        struct IEnumString **a3)
{
  int KeyName; // eax
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  DWORD i; // ebx
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct CSimpleEnumString *v21; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  *a3 = 0;
  KeyName = Windows::Internal::Storage::Cloud::RegistryStorage::GetKeyName(a2, SubKey, (unsigned __int64)a3);
  v6 = KeyName;
  if ( KeyName >= 0 )
  {
    v21 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    v8 = CSimpleEnumString_CreateInstance(v7, &v21);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
        (const char *)(unsigned int)v8,
        phkResult);
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      return v6;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v9 = RegOpenKeyExW(this[2], SubKey, 0, 8u, &hKey);
    if ( v9 != 2 )
    {
      if ( v9 )
      {
        v10 = 125;
LABEL_8:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v10,
               (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
               (const char *)v9,
               phkResulta);
LABEL_9:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_23;
      }
      for ( i = 0; ; ++i )
      {
        cchName[0] = 260;
        v9 = RegEnumKeyExW(hKey, i, Name, cchName, 0, 0, 0, 0);
        if ( v9 == 259 )
          break;
        if ( v9 )
        {
          v10 = 135;
          goto LABEL_8;
        }
        v12 = CSimpleEnumString::AddString(v21, Name);
        v13 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x88,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
            (const char *)(unsigned int)v12,
            phkResulta);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          v6 = v13;
          goto LABEL_23;
        }
      }
    }
    v14 = (*(__int64 (__fastcall **)(struct CSimpleEnumString *))(*(_QWORD *)v21 + 40LL))(v21);
    v6 = v14;
    if ( v14 >= 0 )
    {
      v14 = Microsoft::WRL::ComPtr<CSimpleEnumString>::CopyTo(&v21, v15, a3);
      v6 = v14;
      if ( v14 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v6 = 0;
        goto LABEL_23;
      }
      v16 = 141;
    }
    else
    {
      v16 = 140;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
      (const char *)(unsigned int)v14,
      phkResulta);
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x74,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
    (const char *)(unsigned int)KeyName,
    phkResult);
  return v6;
}

```

## disassembly

```asm
0x1801a81a0  mov     [rsp-8+arg_18], rbx
0x1801a81a5  push    rbp
0x1801a81a6  push    rsi
0x1801a81a7  push    rdi
0x1801a81a8  lea     rbp, [rsp-390h]
0x1801a81b0  sub     rsp, 490h
0x1801a81b7  mov     rax, cs:__security_cookie
0x1801a81be  xor     rax, rsp
0x1801a81c1  mov     [rbp+3A0h+var_20], rax
0x1801a81c8  mov     rsi, r8
0x1801a81cb  mov     rax, rdx
0x1801a81ce  mov     rdi, rcx
0x1801a81d1  mov     qword ptr [r8], 0
0x1801a81d8  lea     rdx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x1801a81dd  mov     rcx, rax; unsigned __int16 *
0x1801a81e0  call    ?GetKeyName@RegistryStorage@Cloud@Storage@Internal@Windows@@CAJPEBGPEAG_K@Z; Windows::Internal::Storage::Cloud::RegistryStorage::GetKeyName(ushort const *,ushort *,unsigned __int64)
0x1801a81e5  mov     ebx, eax
0x1801a81e7  test    eax, eax
0x1801a81e9  jns     short loc_1801A820B
0x1801a81eb  mov     rcx, [rbp+3A8h]; this
0x1801a81f2  mov     r9d, eax; char *
0x1801a81f5  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a81fc  mov     edx, 74h ; 't'; void *
0x1801a8201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8206  jmp     loc_1801A83C6
0x1801a820b  mov     [rsp+4A0h+var_458], 0
0x1801a8214  lea     rcx, [rsp+4A0h+var_458]
0x1801a8219  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a821e  lea     rdx, [rsp+4A0h+var_458]; struct CSimpleEnumString **
0x1801a8223  call    ?CSimpleEnumString_CreateInstance@@YAJHPEAPEAVCSimpleEnumString@@@Z; CSimpleEnumString_CreateInstance(int,CSimpleEnumString * *)
0x1801a8228  mov     ebx, eax
0x1801a822a  test    eax, eax
0x1801a822c  jns     short loc_1801A824E
0x1801a822e  mov     rcx, [rbp+3A8h]; this
0x1801a8235  mov     r9d, eax; char *
0x1801a8238  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a823f  mov     edx, 77h ; 'w'; void *
0x1801a8244  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8249  jmp     loc_1801A83BC
0x1801a824e  mov     [rsp+4A0h+hKey], 0
0x1801a8257  xor     edx, edx
0x1801a8259  lea     rcx, [rsp+4A0h+hKey]
0x1801a825e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801a8263  lea     rax, [rsp+4A0h+hKey]
0x1801a8268  mov     [rsp+4A0h+phkResult], rax; int
0x1801a826d  mov     r9d, 8; samDesired
0x1801a8273  xor     r8d, r8d; ulOptions
0x1801a8276  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x1801a827b  mov     rcx, [rdi+10h]; hKey
0x1801a827f  call    cs:__imp_RegOpenKeyExW
0x1801a8285  cmp     eax, 2
0x1801a8288  jz      loc_1801A835F
0x1801a828e  test    eax, eax
0x1801a8290  jz      short loc_1801A82BE
0x1801a8292  mov     edx, 7Dh ; '}'; void *
0x1801a8297  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a829e  mov     r9d, eax; char *
0x1801a82a1  mov     rcx, [rbp+3A8h]; this
0x1801a82a8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801a82ad  mov     ebx, eax
0x1801a82af  lea     rcx, [rsp+4A0h+hKey]
0x1801a82b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a82b9  jmp     loc_1801A83BC
0x1801a82be  xor     ebx, ebx
0x1801a82c0  mov     [rsp+4A0h+cchName], 104h
0x1801a82c8  mov     [rsp+4A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1801a82d1  mov     [rsp+4A0h+lpcchClass], 0; lpcchClass
0x1801a82da  mov     [rsp+4A0h+lpClass], 0; lpClass
0x1801a82e3  mov     [rsp+4A0h+phkResult], 0; int
0x1801a82ec  lea     r9, [rsp+4A0h+cchName]; lpcchName
0x1801a82f1  lea     r8, [rbp+3A0h+Name]; lpName
0x1801a82f8  mov     edx, ebx; dwIndex
0x1801a82fa  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1801a82ff  call    cs:__imp_RegEnumKeyExW
0x1801a8305  cmp     eax, 103h
0x1801a830a  jz      short loc_1801A835F
0x1801a830c  test    eax, eax
0x1801a830e  jnz     short loc_1801A8355
0x1801a8310  lea     rdx, [rbp+3A0h+Name]; unsigned __int16 *
0x1801a8317  mov     rcx, [rsp+4A0h+var_458]; this
0x1801a831c  call    ?AddString@CSimpleEnumString@@QEAAJPEBG@Z; CSimpleEnumString::AddString(ushort const *)
0x1801a8321  mov     edi, eax
0x1801a8323  test    eax, eax
0x1801a8325  js      short loc_1801A832B
0x1801a8327  inc     ebx
0x1801a8329  jmp     short loc_1801A82C0
0x1801a832b  mov     rcx, [rbp+3A8h]; this
0x1801a8332  mov     r9d, edi; char *
0x1801a8335  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a833c  mov     edx, 88h; void *
0x1801a8341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8346  nop
0x1801a8347  lea     rcx, [rsp+4A0h+hKey]
0x1801a834c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a8351  mov     ebx, edi
0x1801a8353  jmp     short loc_1801A83BC
0x1801a8355  mov     edx, 87h
0x1801a835a  jmp     loc_1801A8297
0x1801a835f  mov     rcx, [rsp+4A0h+var_458]
0x1801a8364  mov     rax, [rcx]
0x1801a8367  mov     rax, [rax+28h]
0x1801a836b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8370  mov     ebx, eax
0x1801a8372  test    eax, eax
0x1801a8374  jns     short loc_1801A8396
0x1801a8376  mov     edx, 8Ch; void *
0x1801a837b  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a8382  mov     r9d, eax; char *
0x1801a8385  mov     rcx, [rbp+3A8h]; this
0x1801a838c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8391  jmp     loc_1801A82AF
0x1801a8396  mov     r8, rsi
0x1801a8399  lea     rcx, [rsp+4A0h+var_458]
0x1801a839e  call    ?CopyTo@?$ComPtr@VCSimpleEnumString@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<CSimpleEnumString>::CopyTo(_GUID const &,void * *)
0x1801a83a3  mov     ebx, eax
0x1801a83a5  test    eax, eax
0x1801a83a7  jns     short loc_1801A83B0
0x1801a83a9  mov     edx, 8Dh
0x1801a83ae  jmp     short loc_1801A837B
0x1801a83b0  lea     rcx, [rsp+4A0h+hKey]
0x1801a83b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a83ba  xor     ebx, ebx
0x1801a83bc  lea     rcx, [rsp+4A0h+var_458]
0x1801a83c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a83c6  mov     eax, ebx
0x1801a83c8  mov     rcx, [rbp+3A0h+var_20]
0x1801a83cf  xor     rcx, rsp; StackCookie
0x1801a83d2  call    __security_check_cookie
0x1801a83d7  mov     rbx, [rsp+4A0h+arg_18]
0x1801a83df  add     rsp, 490h
0x1801a83e6  pop     rdi
0x1801a83e7  pop     rsi
0x1801a83e8  pop     rbp
0x1801a83e9  retn
```

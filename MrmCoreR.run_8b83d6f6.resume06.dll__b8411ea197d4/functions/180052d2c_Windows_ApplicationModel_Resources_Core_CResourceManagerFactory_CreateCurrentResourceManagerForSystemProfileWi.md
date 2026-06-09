# Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_CreateCurrentResourceManagerForSystemProfileWithPackageName(ushort const *)

- ea: `0x180052d2c`
- end: `0x1800530bd`
- name: `?_CreateCurrentResourceManagerForSystemProfileWithPackageName@CResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@AEAAJPEBG@Z`
- size: `913`
- prototype: `int(Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008958`
- `0x180072b60`

## callees

- `0x18000892c`
- `0x18000af60`
- `0x18000b46c`
- `0x18002c8d0`
- `0x18003490c`
- `0x180034d84`
- `0x180035680`
- `0x1800364a8`
- `0x1800371a8`
- `0x180052d2c`
- `0x1800530c4`
- `0x180053468`
- `0x180083978`
- `0x1800862f0`
- `0x18008679c`
- `0x1800867dc`
- `0x1800c5010`

## import_xrefs

- `KERNELBASE!GetPackagePathByFullName` at `0x180052d82`
- `KERNELBASE!GetPackagePathByFullName` at `0x180052dd5`
- `KERNELBASE!GetPackagePathByFullName` at `0x180052d82`
- `KERNELBASE!GetPackagePathByFullName` at `0x180052dd5`

## string_xrefs

- `0x180052e05`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180052f4a`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180052fa0`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x18005300c`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180053072`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_CreateCurrentResourceManagerForSystemProfileWithPackageName(
        Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *this,
        const unsigned __int16 *a2)
{
  UINT32 v3; // edi
  PWSTR v4; // rsi
  unsigned int PackagePathByFullName; // eax
  __int64 unique; // rax
  PWSTR v7; // r14
  PWSTR v8; // rbx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  unsigned int v12; // edi
  __int64 v14; // r9
  __int64 v15; // rcx
  PWSTR v16; // rax
  __int64 v17; // r8
  const wchar_t *v18; // rax
  __int64 v19; // rdx
  WCHAR *i; // r8
  wchar_t v21; // cx
  WCHAR *v22; // rcx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v23; // rax
  Microsoft::Resources::Runtime::CResourceManagerInternal *v24; // rdi
  __int64 v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *v29; // rcx
  unsigned int v30; // edx
  struct IResourceManager *v31; // rcx
  const struct std::nothrow_t *v32; // rdx
  int v33; // eax
  struct IResourceManager *v34; // rcx
  unsigned int v35; // [rsp+20h] [rbp-E0h]
  UINT32 pathLength; // [rsp+30h] [rbp-D0h] BYREF
  struct IResourceManager *v37; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR v38; // [rsp+40h] [rbp-C0h] BYREF
  void **v39; // [rsp+48h] [rbp-B8h] BYREF
  Microsoft::Resources::Runtime::CResourceManagerInternal *v40; // [rsp+50h] [rbp-B0h]
  WCHAR path[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v3 = 260;
  pathLength = 260;
  v4 = 0;
  v38 = 0;
  PackagePathByFullName = GetPackagePathByFullName(a2, &pathLength, path);
  if ( PackagePathByFullName == 122 )
  {
    unique = wil::make_unique_nothrow<unsigned short [0]>(&v39, pathLength + 15LL);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v38, unique);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v39);
    v4 = v38;
    if ( !v38 )
    {
      v9 = -2147024882;
      v10 = 931;
      goto LABEL_46;
    }
    v7 = v38;
    v3 = pathLength + 15;
    PackagePathByFullName = GetPackagePathByFullName(a2, &pathLength, v38);
    v8 = v4;
  }
  else
  {
    v8 = 0;
    v7 = path;
  }
  if ( !PackagePathByFullName )
  {
    v14 = 2147483646;
    if ( v3 - 1 > 0x7FFFFFFE )
    {
      v9 = -2147024809;
    }
    else
    {
      v15 = v3;
      v16 = v7;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      v9 = v15 == 0 ? 0x80070057 : 0;
      if ( v15 )
        v17 = v3 - v15;
      else
        v17 = 0;
      if ( v15 )
      {
        v18 = L"\\resources.pri";
        v19 = v3 - v17;
        for ( i = &v7[v17]; v19; --v19 )
        {
          if ( !v14 )
            break;
          v21 = *v18;
          if ( !*v18 )
            break;
          ++v18;
          *i++ = v21;
          --v14;
        }
        v9 = v19 == 0 ? 0x8007007A : 0;
        v22 = i - 1;
        if ( v19 )
          v22 = i;
        *v22 = 0;
        if ( v19 )
        {
          v23 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)operator new(
                                                                             0xC8u,
                                                                             (const struct std::nothrow_t *)&std::nothrow);
          v39 = (void **)v23;
          if ( v23 )
            v24 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)Microsoft::Resources::Runtime::CResourceManagerInternal::CResourceManagerInternal(v23);
          else
            v24 = 0;
          v39 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
          v40 = v24;
          if ( v24 )
          {
            v35 = 0;
            v27 = Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeWithProfile(v24, 8, v7, 0);
            v9 = v27;
            if ( v27 >= 0 )
            {
              v37 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v37);
              v28 = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceManager,Windows::ApplicationModel::Resources::Core::IResourceManager,Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal> &>(
                      &v37,
                      &v39);
              v9 = v28;
              if ( v28 >= 0 )
              {
                v40 = 0;
                v33 = Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_WriteToLifetimeStore(
                        v29,
                        v37);
                v9 = v33;
                if ( v33 >= 0 )
                {
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v37);
                  v39 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
                  Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v39);
                  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v38);
                  return 0;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3BE,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
                  (const char *)(unsigned int)v33,
                  0);
                v34 = v37;
                if ( v37 )
                {
                  v37 = 0;
                  ((void (__fastcall *)(struct IResourceManager *))v34->lpVtbl->Release)(v34);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3B9,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
                  (const char *)(unsigned int)v28,
                  0);
                v31 = v37;
                if ( v37 )
                {
                  v37 = 0;
                  ((void (__fastcall *)(struct IResourceManager *))v31->lpVtbl->Release)(v31);
                }
                Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v24, v30);
              }
              if ( v4 )
                operator delete(v4, v32);
              return v9;
            }
            v25 = (unsigned int)v27;
            v26 = 950;
          }
          else
          {
            v9 = -2147024882;
            v25 = 2147942414LL;
            v26 = 945;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
            (const char *)v25,
            v35);
          v39 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v39);
LABEL_47:
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v38);
          return v9;
        }
      }
    }
    v10 = 942;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
      (const char *)v9,
      v35);
    goto LABEL_47;
  }
  v12 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x3AB,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
          (const char *)PackagePathByFullName,
          v35);
  if ( v8 )
    operator delete(v8, v11);
  return v12;
}

```

## disassembly

```asm
0x180052d2c  mov     [rsp-8+arg_0], rbx
0x180052d31  mov     [rsp-8+arg_10], rsi
0x180052d36  push    rbp
0x180052d37  push    rdi
0x180052d38  push    r12
0x180052d3a  push    r14
0x180052d3c  push    r15
0x180052d3e  lea     rbp, [rsp-180h]
0x180052d46  sub     rsp, 280h
0x180052d4d  mov     rax, cs:__security_cookie
0x180052d54  xor     rax, rsp
0x180052d57  mov     [rbp+1A0h+var_30], rax
0x180052d5e  mov     rbx, rdx
0x180052d61  mov     edi, 104h
0x180052d66  mov     [rsp+2A0h+pathLength], edi
0x180052d6a  xor     r15d, r15d
0x180052d6d  mov     esi, r15d
0x180052d70  mov     [rsp+2A0h+var_260], r15
0x180052d75  lea     r8, [rsp+2A0h+path]; path
0x180052d7a  lea     rdx, [rsp+2A0h+pathLength]; pathLength
0x180052d7f  mov     rcx, rbx; packageFullName
0x180052d82  call    cs:__imp_GetPackagePathByFullName
0x180052d88  cmp     eax, 7Ah ; 'z'
0x180052d8b  jnz     short loc_180052DEF
0x180052d8d  mov     edx, [rsp+2A0h+pathLength]
0x180052d91  add     rdx, 0Fh
0x180052d95  lea     rcx, [rsp+2A0h+var_258]
0x180052d9a  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180052d9f  mov     rdx, rax
0x180052da2  lea     rcx, [rsp+2A0h+var_260]
0x180052da7  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180052dac  lea     rcx, [rsp+2A0h+var_258]
0x180052db1  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180052db6  mov     rsi, [rsp+2A0h+var_260]
0x180052dbb  test    rsi, rsi
0x180052dbe  jz      short loc_180052DE0
0x180052dc0  mov     r14, rsi
0x180052dc3  mov     edi, [rsp+2A0h+pathLength]
0x180052dc7  add     edi, 0Fh
0x180052dca  mov     r8, rsi; path
0x180052dcd  lea     rdx, [rsp+2A0h+pathLength]; pathLength
0x180052dd2  mov     rcx, rbx; packageFullName
0x180052dd5  call    cs:__imp_GetPackagePathByFullName
0x180052ddb  mov     rbx, rsi
0x180052dde  jmp     short loc_180052DF7
0x180052de0  mov     ebx, 8007000Eh
0x180052de5  mov     edx, 3A3h
0x180052dea  jmp     loc_18005306F
0x180052def  mov     rbx, r15
0x180052df2  lea     r14, [rsp+2A0h+path]
0x180052df7  test    eax, eax
0x180052df9  jz      short loc_180052E2C
0x180052dfb  mov     rcx, [rbp+1A8h]; this
0x180052e02  mov     r9d, eax; char *
0x180052e05  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180052e0c  mov     edx, 3ABh; void *
0x180052e11  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180052e16  mov     edi, eax
0x180052e18  test    rbx, rbx
0x180052e1b  jz      short loc_180052E25
0x180052e1d  mov     rcx, rbx; void *
0x180052e20  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180052e25  mov     eax, edi
0x180052e27  jmp     loc_180053092
0x180052e2c  lea     eax, [rdi-1]
0x180052e2f  mov     r9d, 7FFFFFFEh
0x180052e35  cmp     eax, r9d
0x180052e38  ja      loc_180053065
0x180052e3e  mov     edx, edi
0x180052e40  mov     ecx, edi
0x180052e42  mov     rax, r14
0x180052e45  mov     r8d, edi
0x180052e48  cmp     [rax], r15w
0x180052e4c  jz      short loc_180052E58
0x180052e4e  add     rax, 2
0x180052e52  sub     rcx, 1
0x180052e56  jnz     short loc_180052E48
0x180052e58  mov     rax, rcx
0x180052e5b  neg     rax
0x180052e5e  sbb     ebx, ebx
0x180052e60  not     ebx
0x180052e62  and     ebx, 80070057h
0x180052e68  test    rcx, rcx
0x180052e6b  jz      short loc_180052E72
0x180052e6d  sub     r8, rcx
0x180052e70  jmp     short loc_180052E75
0x180052e72  mov     r8, r15
0x180052e75  test    rcx, rcx
0x180052e78  jz      loc_18005306A
0x180052e7e  lea     rax, aResourcesPri_0; "\\resources.pri"
0x180052e85  sub     rdx, r8
0x180052e88  lea     r8, [r14+r8*2]
0x180052e8c  jz      short loc_180052EB0
0x180052e8e  test    r9, r9
0x180052e91  jz      short loc_180052EB0
0x180052e93  movzx   ecx, word ptr [rax]
0x180052e96  test    cx, cx
0x180052e99  jz      short loc_180052EB0
0x180052e9b  add     rax, 2
0x180052e9f  mov     [r8], cx
0x180052ea3  add     r8, 2
0x180052ea7  dec     r9
0x180052eaa  sub     rdx, 1
0x180052eae  jnz     short loc_180052E8E
0x180052eb0  mov     rax, rdx
0x180052eb3  neg     rax
0x180052eb6  sbb     ebx, ebx
0x180052eb8  not     ebx
0x180052eba  and     ebx, 8007007Ah
0x180052ec0  lea     rcx, [r8-2]
0x180052ec4  test    rdx, rdx
0x180052ec7  cmovnz  rcx, r8
0x180052ecb  mov     [rcx], r15w
0x180052ecf  jz      loc_18005306A
0x180052ed5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180052edc  mov     ecx, 0C8h; unsigned __int64
0x180052ee1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180052ee6  mov     [rsp+2A0h+var_258], rax
0x180052eeb  test    rax, rax
0x180052eee  jz      short loc_180052EFD
0x180052ef0  mov     rcx, rax; this
0x180052ef3  call    ??0CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::CResourceManagerInternal::CResourceManagerInternal(void)
0x180052ef8  mov     rdi, rax
0x180052efb  jmp     short loc_180052F00
0x180052efd  mov     rdi, r15
0x180052f00  lea     r12, ??_7?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable'
0x180052f07  mov     [rsp+2A0h+var_258], r12
0x180052f0c  mov     [rsp+2A0h+var_250], rdi
0x180052f11  test    rdi, rdi
0x180052f14  jnz     short loc_180052F25
0x180052f16  mov     ebx, 8007000Eh
0x180052f1b  mov     r9d, ebx
0x180052f1e  mov     edx, 3B1h
0x180052f23  jmp     short loc_180052F4A
0x180052f25  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180052f2a  xor     r9d, r9d
0x180052f2d  mov     r8, r14
0x180052f30  lea     edx, [r9+8]
0x180052f34  mov     rcx, rdi
0x180052f37  call    ?InitializeWithProfile@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJW4ProfileType@MrmProfile@34@PEBG11@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeWithProfile(Microsoft::Resources::MrmProfile::ProfileType,ushort const *,ushort const *,ushort const *)
0x180052f3c  mov     ebx, eax
0x180052f3e  test    eax, eax
0x180052f40  jns     short loc_180052F72
0x180052f42  mov     r9d, eax; char *
0x180052f45  mov     edx, 3B6h; void *
0x180052f4a  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180052f51  mov     rcx, [rbp+1A8h]; this
0x180052f58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052f5d  nop
0x180052f5e  mov     [rsp+2A0h+var_258], r12
0x180052f63  lea     rcx, [rsp+2A0h+var_258]
0x180052f68  call    ?Release@?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@QEAAXXZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(void)
0x180052f6d  jmp     loc_180053086
0x180052f72  mov     [rsp+2A0h+var_268], r15
0x180052f77  lea     rcx, [rsp+2A0h+var_268]
0x180052f7c  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180052f81  lea     rdx, [rsp+2A0h+var_258]
0x180052f86  lea     rcx, [rsp+2A0h+var_268]
0x180052f8b  call    ??$MakeAndInitialize@VCResourceManager@Core@Resources@ApplicationModel@Windows@@UIResourceManager@2345@AEAV?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@3Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIResourceManager@Core@Resources@ApplicationModel@Windows@@AEAV?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@52@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceManager,Windows::ApplicationModel::Resources::Core::IResourceManager,Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal> &>(Windows::ApplicationModel::Resources::Core::IResourceManager * *,Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal> &)
0x180052f90  mov     ebx, eax
0x180052f92  test    eax, eax
0x180052f94  jns     short loc_180052FED
0x180052f96  mov     rcx, [rbp+1A8h]; this
0x180052f9d  mov     r9d, eax; char *
0x180052fa0  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180052fa7  mov     edx, 3B9h; void *
0x180052fac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052fb1  nop
0x180052fb2  mov     rcx, [rsp+2A0h+var_268]
0x180052fb7  test    rcx, rcx
0x180052fba  jz      short loc_180052FCE
0x180052fbc  mov     [rsp+2A0h+var_268], r15
0x180052fc1  mov     rax, [rcx]
0x180052fc4  mov     rax, [rax+10h]
0x180052fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fcd  nop
0x180052fce  mov     rcx, rdi; this
0x180052fd1  call    ??_GCResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(uint)
0x180052fd6  nop
0x180052fd7  test    rsi, rsi
0x180052fda  jz      loc_180053090
0x180052fe0  mov     rcx, rsi; void *
0x180052fe3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180052fe8  jmp     loc_180053090
0x180052fed  mov     [rsp+2A0h+var_250], r15
0x180052ff2  mov     rdx, [rsp+2A0h+var_268]; struct IResourceManager *
0x180052ff7  call    ?_WriteToLifetimeStore@CResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@AEAAJPEAUIResourceManager@2345@@Z; Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_WriteToLifetimeStore(Windows::ApplicationModel::Resources::Core::IResourceManager *)
0x180052ffc  mov     ebx, eax
0x180052ffe  test    eax, eax
0x180053000  jns     short loc_18005303C
0x180053002  mov     rcx, [rbp+1A8h]; this
0x180053009  mov     r9d, eax; char *
0x18005300c  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180053013  mov     edx, 3BEh; void *
0x180053018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005301d  nop
0x18005301e  mov     rcx, [rsp+2A0h+var_268]
0x180053023  test    rcx, rcx
0x180053026  jz      short loc_18005303A
0x180053028  mov     [rsp+2A0h+var_268], r15
0x18005302d  mov     rax, [rcx]
0x180053030  mov     rax, [rax+10h]
0x180053034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053039  nop
0x18005303a  jmp     short loc_180052FD7
0x18005303c  lea     rcx, [rsp+2A0h+var_268]
0x180053041  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180053046  nop
0x180053047  mov     [rsp+2A0h+var_258], r12
0x18005304c  lea     rcx, [rsp+2A0h+var_258]
0x180053051  call    ?Release@?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@QEAAXXZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(void)
0x180053056  nop
0x180053057  lea     rcx, [rsp+2A0h+var_260]
0x18005305c  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180053061  xor     eax, eax
0x180053063  jmp     short loc_180053092
0x180053065  mov     ebx, 80070057h
0x18005306a  mov     edx, 3AEh; void *
0x18005306f  mov     r9d, ebx; char *
0x180053072  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180053079  mov     rcx, [rbp+1A8h]; this
0x180053080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053085  nop
0x180053086  lea     rcx, [rsp+2A0h+var_260]
0x18005308b  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180053090  mov     eax, ebx
0x180053092  mov     rcx, [rbp+1A0h+var_30]
0x180053099  xor     rcx, rsp; StackCookie
0x18005309c  call    __security_check_cookie
0x1800530a1  lea     r11, [rsp+2A0h+var_20]
0x1800530a9  mov     rbx, [r11+30h]
0x1800530ad  mov     rsi, [r11+40h]
0x1800530b1  mov     rsp, r11
0x1800530b4  pop     r15
0x1800530b6  pop     r14
0x1800530b8  pop     r12
0x1800530ba  pop     rdi
0x1800530bb  pop     rbp
0x1800530bc  retn
```

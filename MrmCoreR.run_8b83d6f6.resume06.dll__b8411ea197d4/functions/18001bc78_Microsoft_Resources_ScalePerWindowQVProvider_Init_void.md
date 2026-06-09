# Microsoft::Resources::ScalePerWindowQVProvider::Init(void)

- ea: `0x18001bc78`
- end: `0x18001be79`
- name: `?Init@ScalePerWindowQVProvider@Resources@Microsoft@@IEAAJXZ`
- size: `513`
- prototype: `__int64 __fastcall(Microsoft::Resources::ScalePerWindowQVProvider *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001bba0`

## callees

- `0x18001bc78`
- `0x18001be80`
- `0x18001beac`
- `0x18002c8d0`
- `0x1800862f0`
- `0x1800867dc`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001be6e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001be6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bcb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bcb1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001bcda`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001bcda`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::ScalePerWindowQVProvider::Init(
        Microsoft::Resources::ScalePerWindowQVProvider *this)
{
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, struct Windows::UI::Core::ICoreWindow **); // rbx
  int v7; // eax
  Microsoft::Resources::CoreWindowContainer *v8; // rax
  struct Windows::UI::Core::ICoreWindow *v9; // rcx
  __int64 v10; // rcx
  struct Windows::UI::Core::ICoreWindow *v12; // rcx
  __int64 v13; // rcx
  struct Windows::UI::Core::ICoreWindow *v14; // rcx
  __int64 v15; // [rsp+20h] [rbp-48h] BYREF
  struct Windows::UI::Core::ICoreWindow *v16; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v15 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(&v15);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v15);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientproviders.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v15);
    goto LABEL_19;
  }
  v5 = v15;
  v16 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, struct Windows::UI::Core::ICoreWindow **))(*(_QWORD *)v15 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(&v16);
  v7 = v6(v5, &v16);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientproviders.cpp",
      (const char *)(unsigned int)v7,
      v15);
    v14 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Core::ICoreWindow *))(*(_QWORD *)v14 + 16LL))(v14);
    }
LABEL_19:
    v13 = v15;
    if ( !v15 )
      return v4;
    goto LABEL_16;
  }
  v8 = (Microsoft::Resources::CoreWindowContainer *)operator new(0x10u, (const struct std::nothrow_t *)&unk_1800DD86E);
  if ( v8 )
    v8 = (Microsoft::Resources::CoreWindowContainer *)Microsoft::Resources::CoreWindowContainer::CoreWindowContainer(
                                                        v8,
                                                        v16);
  *((_QWORD *)this + 10) = v8;
  if ( !v8 )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientproviders.cpp",
      (const char *)0x8007000ELL,
      v15);
    v12 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Core::ICoreWindow *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v15;
    if ( !v15 )
      return v4;
LABEL_16:
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return v4;
  }
  v9 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(struct Windows::UI::Core::ICoreWindow *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18001bc78  push    rbp
0x18001bc7a  push    rbx
0x18001bc7b  push    rsi
0x18001bc7c  push    rdi
0x18001bc7d  mov     rbp, rsp
0x18001bc80  sub     rsp, 68h
0x18001bc84  mov     rax, cs:__security_cookie
0x18001bc8b  xor     rax, rsp
0x18001bc8e  mov     [rbp+var_18], rax
0x18001bc92  mov     rsi, rcx
0x18001bc95  mov     [rbp+var_48], 0
0x18001bc9d  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x18001bca4  mov     edx, 1Ah; length
0x18001bca9  lea     r9, [rbp+string]; string
0x18001bcad  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001bcb1  call    cs:__imp_WindowsCreateStringReference
0x18001bcb7  test    eax, eax
0x18001bcb9  js      loc_18001BE5F
0x18001bcbf  mov     rbx, [rbp+string]
0x18001bcc3  lea     rcx, [rbp+var_48]
0x18001bcc7  call    ?InternalRelease@?$ComPtr@UIPackageManagerRepairAclsInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(void)
0x18001bccc  lea     r8, [rbp+var_48]
0x18001bcd0  mov     rcx, rbx
0x18001bcd3  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x18001bcda  call    cs:__imp_RoGetActivationFactory
0x18001bce0  mov     ebx, eax
0x18001bce2  test    eax, eax
0x18001bce4  js      loc_18001BDF6
0x18001bcea  mov     rdi, [rbp+var_48]
0x18001bcee  lea     rcx, [rbp+var_40]
0x18001bcf2  mov     [rbp+var_40], 0
0x18001bcfa  mov     rax, [rdi]
0x18001bcfd  mov     rbx, [rax+30h]
0x18001bd01  call    ?InternalRelease@?$ComPtr@UIPackageManagerRepairAclsInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(void)
0x18001bd06  lea     rdx, [rbp+var_40]
0x18001bd0a  mov     rcx, rdi
0x18001bd0d  mov     rax, rbx
0x18001bd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd15  mov     ebx, eax
0x18001bd17  test    eax, eax
0x18001bd19  js      loc_18001BE28
0x18001bd1f  lea     rdx, unk_1800DD86E; struct std::nothrow_t *
0x18001bd26  mov     ecx, 10h; unsigned __int64
0x18001bd2b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bd30  test    rax, rax
0x18001bd33  jz      short loc_18001BD41
0x18001bd35  mov     rdx, [rbp+var_40]; struct Windows::UI::Core::ICoreWindow *
0x18001bd39  mov     rcx, rax; this
0x18001bd3c  call    ??0CoreWindowContainer@Resources@Microsoft@@QEAA@PEAUICoreWindow@Core@UI@Windows@@@Z; Microsoft::Resources::CoreWindowContainer::CoreWindowContainer(Windows::UI::Core::ICoreWindow *)
0x18001bd41  mov     [rsi+50h], rax
0x18001bd45  test    rax, rax
0x18001bd48  jz      short loc_18001BD9B
0x18001bd4a  mov     rcx, [rbp+var_40]
0x18001bd4e  test    rcx, rcx
0x18001bd51  jz      short loc_18001BD67
0x18001bd53  mov     [rbp+var_40], 0
0x18001bd5b  mov     rax, [rcx]
0x18001bd5e  mov     rax, [rax+10h]
0x18001bd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd67  mov     rcx, [rbp+var_48]
0x18001bd6b  test    rcx, rcx
0x18001bd6e  jz      short loc_18001BD84
0x18001bd70  mov     [rbp+var_48], 0
0x18001bd78  mov     rax, [rcx]
0x18001bd7b  mov     rax, [rax+10h]
0x18001bd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd84  xor     eax, eax
0x18001bd86  mov     rcx, [rbp+var_18]
0x18001bd8a  xor     rcx, rsp; StackCookie
0x18001bd8d  call    __security_check_cookie
0x18001bd92  add     rsp, 68h
0x18001bd96  pop     rdi
0x18001bd97  pop     rsi
0x18001bd98  pop     rbx
0x18001bd99  pop     rbp
0x18001bd9a  retn
0x18001bd9b  mov     rcx, [rbp+20h]; this
0x18001bd9f  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001bda6  mov     ebx, 8007000Eh
0x18001bdab  mov     edx, 1A0h; void *
0x18001bdb0  mov     r9d, ebx; char *
0x18001bdb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bdb8  mov     rcx, [rbp+var_40]
0x18001bdbc  test    rcx, rcx
0x18001bdbf  jz      short loc_18001BDD5
0x18001bdc1  mov     [rbp+var_40], 0
0x18001bdc9  mov     rax, [rcx]
0x18001bdcc  mov     rax, [rax+10h]
0x18001bdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd5  mov     rcx, [rbp+var_48]
0x18001bdd9  test    rcx, rcx
0x18001bddc  jz      short loc_18001BDF2
0x18001bdde  mov     [rbp+var_48], 0
0x18001bde6  mov     rdx, [rcx]
0x18001bde9  mov     rax, [rdx+10h]
0x18001bded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdf2  mov     eax, ebx
0x18001bdf4  jmp     short loc_18001BD86
0x18001bdf6  mov     rcx, [rbp+20h]; this
0x18001bdfa  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001be01  mov     r9d, ebx; char *
0x18001be04  mov     edx, 199h; void *
0x18001be09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be0e  mov     rcx, [rbp+var_48]
0x18001be12  test    rcx, rcx
0x18001be15  jz      short loc_18001BDF2
0x18001be17  mov     [rbp+var_48], 0
0x18001be1f  mov     rax, [rcx]
0x18001be22  mov     rax, [rax+10h]
0x18001be26  jmp     short loc_18001BDED
0x18001be28  mov     rcx, [rbp+20h]; this
0x18001be2c  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001be33  mov     r9d, ebx; char *
0x18001be36  mov     edx, 19Dh; void *
0x18001be3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be40  mov     rcx, [rbp+var_40]
0x18001be44  test    rcx, rcx
0x18001be47  jz      short loc_18001BE0E
0x18001be49  mov     [rbp+var_40], 0
0x18001be51  mov     rax, [rcx]
0x18001be54  mov     rax, [rax+10h]
0x18001be58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be5d  jmp     short loc_18001BE0E
0x18001be5f  xor     r9d, r9d; lpArguments
0x18001be62  xor     r8d, r8d; nNumberOfArguments
0x18001be65  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001be6a  lea     edx, [r9+1]; dwExceptionFlags
0x18001be6e  call    cs:__imp_RaiseException
0x18001be74  jmp     loc_18001BCBF
```

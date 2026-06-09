# AppReadiness::Groups::OnDemandSyncGroup::SyncFrameworkPackages(Microsoft::WRL::Wrappers::HString &,Microsoft::WRL::Wrappers::HString &)

- ea: `0x18002a500`
- end: `0x18002a8d4`
- name: `?SyncFrameworkPackages@OnDemandSyncGroup@Groups@AppReadiness@@AEAAXAEAVHString@Wrappers@WRL@Microsoft@@0@Z`
- size: `980`
- prototype: `void __fastcall(AppReadiness::Groups::OnDemandSyncGroup *__hidden this, struct Microsoft::WRL::Wrappers::HString *, struct Microsoft::WRL::Wrappers::HString *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180032450`

## callees

- `0x180002958`
- `0x18002a500`
- `0x18002a970`
- `0x18003e210`
- `0x180049310`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a7c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a7c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a84e`

## string_xrefs

- `0x18002a57e`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002a5b5`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002a707`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002a71c`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002a731`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002a769`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002a8ad`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002a8c2`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall AppReadiness::Groups::OnDemandSyncGroup::SyncFrameworkPackages(
        AppReadiness::Groups::OnDemandSyncGroup *this,
        struct Microsoft::WRL::Wrappers::HString *a2,
        struct Microsoft::WRL::Wrappers::HString *a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64, _QWORD); // rbx
  int v8; // eax
  int v9; // eax
  unsigned int i; // esi
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64, _QWORD); // rbx
  int v19; // eax
  int v20; // eax
  unsigned int j; // esi
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // eax
  __int64 v26; // rax
  _QWORD *v27; // rdx
  HSTRING string; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-91h] BYREF
  unsigned int v30; // [rsp+3Ch] [rbp-8Dh] BYREF
  __int64 v31; // [rsp+40h] [rbp-89h] BYREF
  int v32[2]; // [rsp+48h] [rbp-81h] BYREF
  int v33[2]; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v34[7]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD *v35; // [rsp+98h] [rbp-31h]
  _QWORD v36[7]; // [rsp+A0h] [rbp-29h] BYREF
  _QWORD *v37; // [rsp+D8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  *(_QWORD *)v33 = 0;
  v6 = *((_QWORD *)this + 46);
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v6 + 584LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v33);
  v8 = v7(v6, *(_QWORD *)a3, 2, *(_QWORD *)a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v8,
      (int)v33);
  v29 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v33 + 56LL))(*(_QWORD *)v33, &v29);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v9,
      (int)v33);
  for ( i = 0; i < v29; ++i )
  {
    v31 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v33 + 48LL))(*(_QWORD *)v33, i, &v31);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v11,
        (int)v33);
    string = 0;
    v12 = v31;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, &string);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v14,
        (int)v33);
    v15 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 112LL))((char *)this + 8);
    v34[0] = off_18007AED0;
    v34[1] = this;
    v34[2] = &string;
    v35 = v34;
    AppReadiness::User::ExecuteUnderContext(v15, (__int64)v34);
    if ( v35 )
    {
      v16 = v34;
      LOBYTE(v16) = v35 != v34;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v35 + 32LL))(v35, v16);
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  }
  *(_QWORD *)v32 = 0;
  v17 = *((_QWORD *)this + 46);
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v17 + 584LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
  v19 = v18(v17, *(_QWORD *)a2, 2, *(_QWORD *)a3);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v19,
      (int)v32);
  v30 = 0;
  v20 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v32 + 56LL))(*(_QWORD *)v32, &v30);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v20,
      (int)v32);
  for ( j = 0; j < v30; ++j )
  {
    v31 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v32 + 48LL))(*(_QWORD *)v32, j, &v31);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v22,
        (int)v32);
    string = 0;
    v23 = v31;
    v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v25 = v24(v23, &string);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v25,
        (int)v32);
    v26 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 112LL))((char *)this + 8);
    v36[0] = off_18007AF00;
    v36[1] = this;
    v36[2] = &string;
    v37 = v36;
    AppReadiness::User::ExecuteUnderContext(v26, (__int64)v36);
    if ( v37 )
    {
      v27 = v36;
      LOBYTE(v27) = v37 != v36;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v37 + 32LL))(v37, v27);
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v33);
}

```

## disassembly

```asm
0x18002a500  mov     [rsp-8+arg_18], rbx
0x18002a505  push    rbp
0x18002a506  push    rsi
0x18002a507  push    rdi
0x18002a508  push    r12
0x18002a50a  push    r13
0x18002a50c  push    r14
0x18002a50e  push    r15
0x18002a510  lea     rbp, [rsp-27h]
0x18002a515  sub     rsp, 0F0h
0x18002a51c  mov     rax, cs:__security_cookie
0x18002a523  xor     rax, rsp
0x18002a526  mov     [rbp+57h+var_40], rax
0x18002a52a  mov     r12, r8
0x18002a52d  mov     r15, rdx
0x18002a530  mov     r14, rcx
0x18002a533  xor     r13d, r13d
0x18002a536  mov     qword ptr [rbp+57h+var_D0], r13
0x18002a53a  mov     rdi, [rcx+170h]
0x18002a541  mov     rax, [rdi]
0x18002a544  mov     rbx, [rax+248h]
0x18002a54b  lea     rcx, [rbp+57h+var_D0]
0x18002a54f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a554  lea     rax, [rbp+57h+var_D0]
0x18002a558  mov     qword ptr [rsp+120h+var_100], rax; int
0x18002a55d  mov     r9, [r15]
0x18002a560  lea     r8d, [r13+2]
0x18002a564  mov     rdx, [r12]
0x18002a568  mov     rcx, rdi
0x18002a56b  mov     rax, rbx
0x18002a56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a573  mov     rcx, [rbp+5Fh]; this
0x18002a577  test    eax, eax
0x18002a579  jns     short loc_18002A590
0x18002a57b  mov     r9d, eax; char *
0x18002a57e  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a585  mov     edx, 0C2h; void *
0x18002a58a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a590  mov     [rsp+120h+var_E8], r13d
0x18002a595  mov     rcx, qword ptr [rbp+57h+var_D0]
0x18002a599  mov     rax, [rcx]
0x18002a59c  lea     rdx, [rsp+120h+var_E8]
0x18002a5a1  mov     rax, [rax+38h]
0x18002a5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5aa  mov     rcx, [rbp+5Fh]; this
0x18002a5ae  test    eax, eax
0x18002a5b0  jns     short loc_18002A5C7
0x18002a5b2  mov     r9d, eax; char *
0x18002a5b5  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a5bc  mov     edx, 0C5h; void *
0x18002a5c1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a5c7  mov     esi, r13d
0x18002a5ca  cmp     [rsp+120h+var_E8], r13d
0x18002a5cf  jbe     loc_18002A6BA
0x18002a5d5  mov     [rsp+120h+var_E0], r13
0x18002a5da  mov     rcx, qword ptr [rbp+57h+var_D0]
0x18002a5de  mov     rax, [rcx]
0x18002a5e1  lea     r8, [rsp+120h+var_E0]
0x18002a5e6  mov     edx, esi
0x18002a5e8  mov     rax, [rax+30h]
0x18002a5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5f1  mov     rcx, [rbp+5Fh]; this
0x18002a5f5  test    eax, eax
0x18002a5f7  js      loc_18002A72E
0x18002a5fd  mov     [rsp+120h+string], r13
0x18002a602  mov     rdi, [rsp+120h+var_E0]
0x18002a607  mov     rax, [rdi]
0x18002a60a  mov     rbx, [rax+70h]
0x18002a60e  xor     ecx, ecx; string
0x18002a610  call    cs:__imp_WindowsDeleteString
0x18002a616  mov     [rsp+120h+string], r13
0x18002a61b  lea     rdx, [rsp+120h+string]
0x18002a620  mov     rcx, rdi
0x18002a623  mov     rax, rbx
0x18002a626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a62b  mov     rcx, [rbp+5Fh]; this
0x18002a62f  test    eax, eax
0x18002a631  js      loc_18002A719
0x18002a637  lea     rcx, [r14+8]
0x18002a63b  mov     rax, [rcx]
0x18002a63e  mov     rax, [rax+70h]
0x18002a642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a647  lea     rcx, off_18007AED0
0x18002a64e  mov     [rbp+57h+var_C0], rcx
0x18002a652  mov     [rbp+57h+var_B8], r14
0x18002a656  lea     rcx, [rsp+120h+string]
0x18002a65b  mov     [rbp+57h+var_B0], rcx
0x18002a65f  lea     rcx, [rbp+57h+var_C0]
0x18002a663  mov     [rbp+57h+var_88], rcx
0x18002a667  lea     rdx, [rbp+57h+var_C0]
0x18002a66b  mov     rcx, rax
0x18002a66e  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18002a673  nop
0x18002a674  mov     rcx, [rbp+57h+var_88]
0x18002a678  test    rcx, rcx
0x18002a67b  jz      short loc_18002A694
0x18002a67d  mov     rax, [rcx]
0x18002a680  lea     rdx, [rbp+57h+var_C0]
0x18002a684  cmp     rcx, rdx
0x18002a687  setnz   dl
0x18002a68a  mov     rax, [rax+20h]
0x18002a68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a693  nop
0x18002a694  mov     rcx, [rsp+120h+string]; string
0x18002a699  call    cs:__imp_WindowsDeleteString
0x18002a69f  mov     [rsp+120h+string], r13
0x18002a6a4  lea     rcx, [rsp+120h+var_E0]
0x18002a6a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a6ae  inc     esi
0x18002a6b0  cmp     esi, [rsp+120h+var_E8]
0x18002a6b4  jb      loc_18002A5D5
0x18002a6ba  mov     qword ptr [rsp+120h+var_D8], r13
0x18002a6bf  mov     rdi, [r14+170h]
0x18002a6c6  mov     rax, [rdi]
0x18002a6c9  mov     rbx, [rax+248h]
0x18002a6d0  lea     rcx, [rsp+120h+var_D8]
0x18002a6d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a6da  lea     rax, [rsp+120h+var_D8]
0x18002a6df  mov     qword ptr [rsp+120h+var_100], rax; int
0x18002a6e4  mov     r9, [r12]
0x18002a6e8  mov     r8d, 2
0x18002a6ee  mov     rdx, [r15]
0x18002a6f1  mov     rcx, rdi
0x18002a6f4  mov     rax, rbx
0x18002a6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6fc  mov     rcx, [rbp+5Fh]; this
0x18002a700  test    eax, eax
0x18002a702  jns     short loc_18002A743
0x18002a704  mov     r9d, eax; char *
0x18002a707  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a70e  mov     edx, 0E8h; void *
0x18002a713  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a719  mov     r9d, eax; char *
0x18002a71c  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a723  mov     edx, 0CDh; void *
0x18002a728  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a72e  mov     r9d, eax; char *
0x18002a731  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a738  mov     edx, 0CAh; void *
0x18002a73d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a743  mov     [rsp+120h+var_E4], r13d
0x18002a748  mov     rcx, qword ptr [rsp+120h+var_D8]
0x18002a74d  mov     rax, [rcx]
0x18002a750  lea     rdx, [rsp+120h+var_E4]
0x18002a755  mov     rax, [rax+38h]
0x18002a759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a75e  mov     rcx, [rbp+5Fh]; this
0x18002a762  test    eax, eax
0x18002a764  jns     short loc_18002A77B
0x18002a766  mov     r9d, eax; char *
0x18002a769  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a770  mov     edx, 0EBh; void *
0x18002a775  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a77b  mov     esi, r13d
0x18002a77e  cmp     [rsp+120h+var_E4], r13d
0x18002a783  jbe     loc_18002A86F
0x18002a789  mov     [rsp+120h+var_E0], r13
0x18002a78e  mov     rcx, qword ptr [rsp+120h+var_D8]
0x18002a793  mov     rax, [rcx]
0x18002a796  lea     r8, [rsp+120h+var_E0]
0x18002a79b  mov     edx, esi
0x18002a79d  mov     rax, [rax+30h]
0x18002a7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7a6  mov     rcx, [rbp+5Fh]; this
0x18002a7aa  test    eax, eax
0x18002a7ac  js      loc_18002A8BF
0x18002a7b2  mov     [rsp+120h+string], r13
0x18002a7b7  mov     rdi, [rsp+120h+var_E0]
0x18002a7bc  mov     rax, [rdi]
0x18002a7bf  mov     rbx, [rax+70h]
0x18002a7c3  xor     ecx, ecx; string
0x18002a7c5  call    cs:__imp_WindowsDeleteString
0x18002a7cb  mov     [rsp+120h+string], r13
0x18002a7d0  lea     rdx, [rsp+120h+string]
0x18002a7d5  mov     rcx, rdi
0x18002a7d8  mov     rax, rbx
0x18002a7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7e0  mov     rcx, [rbp+5Fh]; this
0x18002a7e4  test    eax, eax
0x18002a7e6  js      loc_18002A8AA
0x18002a7ec  lea     rcx, [r14+8]
0x18002a7f0  mov     rax, [rcx]
0x18002a7f3  mov     rax, [rax+70h]
0x18002a7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7fc  lea     rcx, off_18007AF00
0x18002a803  mov     [rbp+57h+var_80], rcx
0x18002a807  mov     [rbp+57h+var_78], r14
0x18002a80b  lea     rcx, [rsp+120h+string]
0x18002a810  mov     [rbp+57h+var_70], rcx
0x18002a814  lea     rcx, [rbp+57h+var_80]
0x18002a818  mov     [rbp+57h+var_48], rcx
0x18002a81c  lea     rdx, [rbp+57h+var_80]
0x18002a820  mov     rcx, rax
0x18002a823  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18002a828  nop
0x18002a829  mov     rcx, [rbp+57h+var_48]
0x18002a82d  test    rcx, rcx
0x18002a830  jz      short loc_18002A849
0x18002a832  mov     rax, [rcx]
0x18002a835  lea     rdx, [rbp+57h+var_80]
0x18002a839  cmp     rcx, rdx
0x18002a83c  setnz   dl
0x18002a83f  mov     rax, [rax+20h]
0x18002a843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a848  nop
0x18002a849  mov     rcx, [rsp+120h+string]; string
0x18002a84e  call    cs:__imp_WindowsDeleteString
0x18002a854  mov     [rsp+120h+string], r13
0x18002a859  lea     rcx, [rsp+120h+var_E0]
0x18002a85e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a863  inc     esi
0x18002a865  cmp     esi, [rsp+120h+var_E4]
0x18002a869  jb      loc_18002A789
0x18002a86f  lea     rcx, [rsp+120h+var_D8]
0x18002a874  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a879  nop
0x18002a87a  lea     rcx, [rbp+57h+var_D0]
0x18002a87e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a883  mov     rcx, [rbp+57h+var_40]
0x18002a887  xor     rcx, rsp; StackCookie
0x18002a88a  call    __security_check_cookie
0x18002a88f  mov     rbx, [rsp+120h+arg_18]
0x18002a897  add     rsp, 0F0h
0x18002a89e  pop     r15
0x18002a8a0  pop     r14
0x18002a8a2  pop     r13
0x18002a8a4  pop     r12
0x18002a8a6  pop     rdi
0x18002a8a7  pop     rsi
0x18002a8a8  pop     rbp
0x18002a8a9  retn
0x18002a8aa  mov     r9d, eax; char *
0x18002a8ad  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a8b4  mov     edx, 0F3h; void *
0x18002a8b9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a8bf  mov     r9d, eax; char *
0x18002a8c2  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002a8c9  mov     edx, 0F0h; void *
0x18002a8ce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

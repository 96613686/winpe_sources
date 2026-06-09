# AppReadiness::Groups::OnDemandSyncGroup::SyncRemovedPackages(Microsoft::WRL::Wrappers::HString &,Microsoft::WRL::Wrappers::HString &)

- ea: `0x18006391c`
- end: `0x180063baa`
- name: `?SyncRemovedPackages@OnDemandSyncGroup@Groups@AppReadiness@@AEAAXAEAVHString@Wrappers@WRL@Microsoft@@0@Z`
- size: `654`
- prototype: `void __fastcall(AppReadiness::Groups::OnDemandSyncGroup *__hidden this, struct Microsoft::WRL::Wrappers::HString *, struct Microsoft::WRL::Wrappers::HString *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032450`

## callees

- `0x180002958`
- `0x18000e4a0`
- `0x180028114`
- `0x180028814`
- `0x18003e210`
- `0x180049310`
- `0x18006391c`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063b13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063b13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063a8b`

## string_xrefs

- `0x18006398d`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800639c5`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180063b6e`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180063b83`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180063b98`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall AppReadiness::Groups::OnDemandSyncGroup::SyncRemovedPackages(
        AppReadiness::Groups::OnDemandSyncGroup *this,
        struct Microsoft::WRL::Wrappers::HString *a2,
        struct Microsoft::WRL::Wrappers::HString *a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  int v8; // eax
  int v9; // eax
  unsigned int i; // esi
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  AppReadiness::User *v16; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 *v18; // rdi
  __int64 v19; // rbx
  int v20; // eax
  int v21; // [rsp+20h] [rbp-39h]
  unsigned int v22; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  __int64 v24; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v25; // [rsp+48h] [rbp-11h] BYREF
  __int64 v26; // [rsp+50h] [rbp-9h] BYREF
  __int64 v27; // [rsp+58h] [rbp-1h] BYREF
  __int64 v28[4]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v24 = 0;
  v6 = *((_QWORD *)this + 46);
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v6 + 576LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v8 = v7(v6, *(_QWORD *)a2, *(_QWORD *)a3, &v24);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v8,
      v21);
  v22 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 56LL))(v24, &v22);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v9,
      v21);
  for ( i = 0; i < v22; ++i )
  {
    v27 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL))(v24, i, &v27);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v11,
        v21);
    v26 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 72LL))(v27, &v26);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v12,
        v21);
    string = 0;
    v13 = v26;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 88LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v15,
        v21);
    v16 = (AppReadiness::User *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 112LL))((char *)this + 8);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring((__int64)v28, (__int64)StringRawBuffer);
    AppReadiness::User::CreateTaskFor(v16, &v25, v28, 2u, 0);
    std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v28);
    v18 = v25;
    v19 = *v25;
    v20 = (*(__int64 (__fastcall **)(__int64 *))(*v25 + 144))(v25);
    (*(void (__fastcall **)(__int64 *, _QWORD))(v19 + 128))(v18, v20 | 0x200000u);
    (*(void (__fastcall **)(AppReadiness::Groups::OnDemandSyncGroup *, __int64 *))(*(_QWORD *)this + 24LL))(this, v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
}

```

## disassembly

```asm
0x18006391c  mov     [rsp-8+arg_18], rbx
0x180063921  push    rbp
0x180063922  push    rsi
0x180063923  push    rdi
0x180063924  push    r14
0x180063926  push    r15
0x180063928  lea     rbp, [rsp-37h]
0x18006392d  sub     rsp, 90h
0x180063934  mov     rax, cs:__security_cookie
0x18006393b  xor     rax, rsp
0x18006393e  mov     [rbp+57h+var_30], rax
0x180063942  mov     r14, r8
0x180063945  mov     rsi, rdx
0x180063948  mov     r15, rcx
0x18006394b  mov     [rbp+57h+var_70], 0
0x180063953  mov     rdi, [rcx+170h]
0x18006395a  mov     rax, [rdi]
0x18006395d  mov     rbx, [rax+240h]
0x180063964  lea     rcx, [rbp+57h+var_70]
0x180063968  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006396d  lea     r9, [rbp+57h+var_70]
0x180063971  mov     r8, [r14]
0x180063974  mov     rdx, [rsi]
0x180063977  mov     rcx, rdi
0x18006397a  mov     rax, rbx
0x18006397d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063982  mov     rcx, [rbp+5Fh]; this
0x180063986  test    eax, eax
0x180063988  jns     short loc_18006399F
0x18006398a  mov     r9d, eax; char *
0x18006398d  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180063994  mov     edx, 0A2h; void *
0x180063999  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006399f  mov     [rbp+57h+var_80], 0
0x1800639a6  mov     rcx, [rbp+57h+var_70]
0x1800639aa  mov     rax, [rcx]
0x1800639ad  lea     rdx, [rbp+57h+var_80]
0x1800639b1  mov     rax, [rax+38h]
0x1800639b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639ba  mov     rcx, [rbp+5Fh]; this
0x1800639be  test    eax, eax
0x1800639c0  jns     short loc_1800639D7
0x1800639c2  mov     r9d, eax; char *
0x1800639c5  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800639cc  mov     edx, 0A5h; void *
0x1800639d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800639d7  xor     esi, esi
0x1800639d9  cmp     [rbp+57h+var_80], esi
0x1800639dc  jbe     loc_180063B3F
0x1800639e2  mov     [rbp+57h+var_58], 0
0x1800639ea  mov     rcx, [rbp+57h+var_70]
0x1800639ee  mov     rax, [rcx]
0x1800639f1  lea     r8, [rbp+57h+var_58]
0x1800639f5  mov     edx, esi
0x1800639f7  mov     rax, [rax+30h]
0x1800639fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a00  mov     rcx, [rbp+5Fh]; this
0x180063a04  test    eax, eax
0x180063a06  js      loc_180063B95
0x180063a0c  mov     [rbp+57h+var_60], 0
0x180063a14  mov     rcx, [rbp+57h+var_58]
0x180063a18  mov     rax, [rcx]
0x180063a1b  lea     rdx, [rbp+57h+var_60]
0x180063a1f  mov     rax, [rax+48h]
0x180063a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a28  mov     rcx, [rbp+5Fh]; this
0x180063a2c  test    eax, eax
0x180063a2e  js      loc_180063B80
0x180063a34  mov     [rbp+57h+string], 0
0x180063a3c  mov     rdi, [rbp+57h+var_60]
0x180063a40  mov     rax, [rdi]
0x180063a43  mov     rbx, [rax+58h]
0x180063a47  xor     ecx, ecx; string
0x180063a49  call    cs:__imp_WindowsDeleteString
0x180063a4f  mov     [rbp+57h+string], 0
0x180063a57  lea     rdx, [rbp+57h+string]
0x180063a5b  mov     rcx, rdi
0x180063a5e  mov     rax, rbx
0x180063a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a66  mov     rcx, [rbp+5Fh]; this
0x180063a6a  test    eax, eax
0x180063a6c  js      loc_180063B6B
0x180063a72  lea     rcx, [r15+8]
0x180063a76  mov     rax, [rcx]
0x180063a79  mov     rax, [rax+70h]
0x180063a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a82  mov     rbx, rax
0x180063a85  xor     edx, edx; length
0x180063a87  mov     rcx, [rbp+57h+string]; string
0x180063a8b  call    cs:__imp_WindowsGetStringRawBuffer
0x180063a91  mov     rdx, rax
0x180063a94  lea     rcx, [rbp+57h+var_50]
0x180063a98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180063a9d  nop
0x180063a9e  mov     [rsp+0B0h+var_90], 0; int
0x180063aa6  mov     r9d, 2
0x180063aac  lea     r8, [rbp+57h+var_50]
0x180063ab0  lea     rdx, [rbp+57h+var_68]
0x180063ab4  mov     rcx, rbx; this
0x180063ab7  call    ?CreateTaskFor@User@AppReadiness@@QEAA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@2@W4APPREADINESS_TASK_FLAGS@@@Z; AppReadiness::User::CreateTaskFor(std::wstring const &,AppReadiness::Storage::PackageOperation,APPREADINESS_TASK_FLAGS)
0x180063abc  nop
0x180063abd  lea     rcx, [rbp+57h+var_50]
0x180063ac1  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180063ac6  mov     rdi, [rbp+57h+var_68]
0x180063aca  mov     rbx, [rdi]
0x180063acd  mov     rcx, rdi
0x180063ad0  mov     rax, [rbx+90h]
0x180063ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063adc  bts     eax, 15h
0x180063ae0  mov     edx, eax
0x180063ae2  mov     rcx, rdi
0x180063ae5  mov     rax, [rbx+80h]
0x180063aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063af1  mov     rax, [r15]
0x180063af4  mov     rdx, [rbp+57h+var_68]
0x180063af8  mov     rcx, r15
0x180063afb  mov     rax, [rax+18h]
0x180063aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b04  nop
0x180063b05  lea     rcx, [rbp+57h+var_68]
0x180063b09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063b0e  nop
0x180063b0f  mov     rcx, [rbp+57h+string]; string
0x180063b13  call    cs:__imp_WindowsDeleteString
0x180063b19  mov     [rbp+57h+string], 0
0x180063b21  lea     rcx, [rbp+57h+var_60]
0x180063b25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063b2a  nop
0x180063b2b  lea     rcx, [rbp+57h+var_58]
0x180063b2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063b34  inc     esi
0x180063b36  cmp     esi, [rbp+57h+var_80]
0x180063b39  jb      loc_1800639E2
0x180063b3f  lea     rcx, [rbp+57h+var_70]
0x180063b43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063b48  mov     rcx, [rbp+57h+var_30]
0x180063b4c  xor     rcx, rsp; StackCookie
0x180063b4f  call    __security_check_cookie
0x180063b54  mov     rbx, [rsp+0B0h+arg_18]
0x180063b5c  add     rsp, 90h
0x180063b63  pop     r15
0x180063b65  pop     r14
0x180063b67  pop     rdi
0x180063b68  pop     rsi
0x180063b69  pop     rbp
0x180063b6a  retn
0x180063b6b  mov     r9d, eax; char *
0x180063b6e  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180063b75  mov     edx, 0B0h; void *
0x180063b7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180063b80  mov     r9d, eax; char *
0x180063b83  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180063b8a  mov     edx, 0ADh; void *
0x180063b8f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180063b95  mov     r9d, eax; char *
0x180063b98  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180063b9f  mov     edx, 0AAh; void *
0x180063ba4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

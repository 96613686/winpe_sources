# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>(winrt::Windows::Management::Update::IWindowsUpdateAdministrator,winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus)

- ea: `0x180025a70`
- end: `0x180025b5e`
- name: `??0?$heap_implements@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@UIWindowsUpdateAdministrator@Update@Management@Windows@2@W4WindowsUpdateAdministratorStatus@4562@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800259f0`

## callees

- `0x180017c3c`
- `0x18001e7a4`
- `0x180025a70`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>(
        __int64 a1,
        __int64 *a2,
        int a3)
{
  __int64 (__fastcall ***v6)(_QWORD, __int64 *, _QWORD *); // rax
  _QWORD *v7; // rsi
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rax
  signed int v9; // eax
  __int64 v10; // r8
  _QWORD v12[3]; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-18h] BYREF
  __int128 v14; // [rsp+40h] [rbp-10h]
  __int64 (__fastcall ***v15)(_QWORD, __int64 *, _QWORD *); // [rsp+98h] [rbp+48h] BYREF

  v6 = (__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *))*a2;
  *a2 = 0;
  v15 = v6;
  v12[1] = &v15;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateGetAdministratorResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable';
  v7 = (_QWORD *)(a1 + 24);
  v12[2] = a1 + 24;
  v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
  if ( v15 )
  {
    v12[0] = 0;
    v13 = 0;
    v14 = 0;
    v9 = (**v15)(v15, winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>, v12);
    if ( v9 < 0 )
      winrt::throw_hresult(v9, &v13, v10);
    *v7 = v12[0];
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
  }
  else
  {
    *v7 = 0;
  }
  *(_DWORD *)(a1 + 32) = a3;
  if ( v8 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v15);
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable';
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return a1;
}

```

## disassembly

```asm
0x180025a70  mov     [rsp-28h+arg_8], rdx
0x180025a75  mov     [rsp-28h+arg_0], rcx
0x180025a7a  push    rbp
0x180025a7b  push    rbx
0x180025a7c  push    rsi
0x180025a7d  push    rdi
0x180025a7e  push    r14
0x180025a80  mov     rbp, rsp
0x180025a83  sub     rsp, 50h
0x180025a87  mov     r14d, r8d
0x180025a8a  mov     rdi, rdx
0x180025a8d  mov     rbx, rcx
0x180025a90  mov     rax, [rdx]
0x180025a93  and     qword ptr [rdx], 0
0x180025a97  mov     [rbp+arg_18], rax
0x180025a9b  lea     rax, [rbp+arg_18]
0x180025a9f  mov     [rbp+var_28], rax
0x180025aa3  lea     rax, ??_7?$produce@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateGetAdministratorResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateGetAdministratorResult>::`vftable'
0x180025aaa  mov     [rcx+10h], rax
0x180025aae  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180025ab5  mov     qword ptr [rcx+8], 1
0x180025abd  lea     rax, ??_7WindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable'
0x180025ac4  mov     [rcx], rax
0x180025ac7  lea     rsi, [rcx+18h]
0x180025acb  mov     [rbp+var_20], rsi
0x180025acf  mov     rax, [rbp+arg_18]
0x180025ad3  test    rax, rax
0x180025ad6  jnz     short loc_180025ADD
0x180025ad8  and     [rsi], rax
0x180025adb  jmp     short loc_180025B19
0x180025add  and     [rbp+var_30], 0
0x180025ae2  and     [rbp+var_18], 0
0x180025ae6  xorps   xmm0, xmm0
0x180025ae9  movdqu  [rbp+var_10], xmm0
0x180025aee  mov     rcx, [rax]
0x180025af1  mov     r9, [rcx]
0x180025af4  lea     r8, [rbp+var_30]
0x180025af8  lea     rdx, ??$guid_v@UIWindowsUpdateAdministrator@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>
0x180025aff  mov     rcx, rax
0x180025b02  mov     rax, r9
0x180025b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b0a  test    eax, eax
0x180025b0c  js      short loc_180025B52
0x180025b0e  mov     rax, [rbp+var_30]
0x180025b12  mov     [rsi], rax
0x180025b15  mov     rax, [rbp+arg_18]
0x180025b19  mov     [rbx+20h], r14d
0x180025b1d  test    rax, rax
0x180025b20  jz      short loc_180025B2B
0x180025b22  lea     rcx, [rbp+arg_18]
0x180025b26  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025b2b  lea     rax, ??_7WindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable'
0x180025b32  mov     [rbx], rax
0x180025b35  cmp     qword ptr [rdi], 0
0x180025b39  jz      short loc_180025B43
0x180025b3b  mov     rcx, rdi
0x180025b3e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025b43  mov     rax, rbx
0x180025b46  add     rsp, 50h
0x180025b4a  pop     r14
0x180025b4c  pop     rdi
0x180025b4d  pop     rsi
0x180025b4e  pop     rbx
0x180025b4f  pop     rbp
0x180025b50  retn
0x180025b52  lea     rdx, [rbp+var_18]
0x180025b56  mov     ecx, eax
0x180025b58  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

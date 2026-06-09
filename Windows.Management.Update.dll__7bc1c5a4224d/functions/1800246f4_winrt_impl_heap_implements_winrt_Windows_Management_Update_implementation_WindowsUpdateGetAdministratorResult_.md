# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>(winrt::Windows::Management::Update::IWindowsUpdateAdministrator,winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus)

- ea: `0x1800246f4`
- end: `0x1800247de`
- name: `??0?$heap_implements@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@UIWindowsUpdateAdministrator@Update@Management@Windows@2@W4WindowsUpdateAdministratorStatus@4562@@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024674`

## callees

- `0x180016fe4`
- `0x18001d50c`
- `0x1800246f4`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult>(
        __int64 a1,
        _QWORD *a2,
        int a3)
{
  __int64 (__fastcall ***v6)(_QWORD, __int64 *, _QWORD *); // rax
  __int64 (__fastcall ***v7)(_QWORD, __int64 *, _QWORD *); // rcx
  int v8; // eax
  _QWORD v10[2]; // [rsp+20h] [rbp-30h] BYREF
  int v11; // [rsp+30h] [rbp-20h] BYREF
  __int128 v12; // [rsp+38h] [rbp-18h]
  __int64 (__fastcall ***v13)(_QWORD, __int64 *, _QWORD *); // [rsp+98h] [rbp+48h] BYREF

  v6 = (__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *))*a2;
  *a2 = 0;
  v13 = v6;
  v10[1] = &v13;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateGetAdministratorResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable';
  v7 = v13;
  if ( v13 )
  {
    v10[0] = 0;
    v11 = 0;
    v12 = 0;
    v8 = (**v13)(v13, winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>, v10);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v11);
    *(_QWORD *)(a1 + 24) = v10[0];
    v7 = v13;
  }
  else
  {
    *(_QWORD *)(a1 + 24) = 0;
  }
  *(_DWORD *)(a1 + 32) = a3;
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable';
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return a1;
}

```

## disassembly

```asm
0x1800246f4  mov     [rsp-28h+arg_8], rdx
0x1800246f9  mov     [rsp-28h+arg_0], rcx
0x1800246fe  push    rbp
0x1800246ff  push    rbx
0x180024700  push    rsi
0x180024701  push    rdi
0x180024702  push    r14
0x180024704  mov     rbp, rsp
0x180024707  sub     rsp, 50h
0x18002470b  mov     r14d, r8d
0x18002470e  mov     rdi, rdx
0x180024711  mov     rbx, rcx
0x180024714  mov     rax, [rdx]
0x180024717  mov     qword ptr [rdx], 0
0x18002471e  mov     [rbp+arg_18], rax
0x180024722  lea     rax, [rbp+arg_18]
0x180024726  mov     [rbp+var_28], rax
0x18002472a  lea     rax, ??_7?$produce@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateGetAdministratorResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateGetAdministratorResult>::`vftable'
0x180024731  mov     [rcx+10h], rax
0x180024735  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002473c  mov     qword ptr [rcx+8], 1
0x180024744  lea     rax, ??_7WindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable'
0x18002474b  mov     [rcx], rax
0x18002474e  mov     rcx, [rbp+arg_18]
0x180024752  test    rcx, rcx
0x180024755  jnz     short loc_18002475D
0x180024757  mov     [rbx+18h], rcx
0x18002475b  jmp     short loc_18002479A
0x18002475d  mov     [rbp+var_30], 0
0x180024765  mov     [rbp+var_20], 0
0x18002476c  xorps   xmm0, xmm0
0x18002476f  movdqu  [rbp+var_18], xmm0
0x180024774  mov     rax, [rcx]
0x180024777  lea     r8, [rbp+var_30]
0x18002477b  lea     rdx, ??$guid_v@UIWindowsUpdateAdministrator@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>
0x180024782  mov     rax, [rax]
0x180024785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002478a  test    eax, eax
0x18002478c  js      short loc_1800247D2
0x18002478e  mov     rax, [rbp+var_30]
0x180024792  mov     [rbx+18h], rax
0x180024796  mov     rcx, [rbp+arg_18]
0x18002479a  mov     [rbx+20h], r14d
0x18002479e  test    rcx, rcx
0x1800247a1  jz      short loc_1800247AC
0x1800247a3  lea     rcx, [rbp+arg_18]
0x1800247a7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800247ac  lea     rax, ??_7WindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult::`vftable'
0x1800247b3  mov     [rbx], rax
0x1800247b6  cmp     qword ptr [rdi], 0
0x1800247ba  jz      short loc_1800247C4
0x1800247bc  mov     rcx, rdi
0x1800247bf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800247c4  mov     rax, rbx
0x1800247c7  add     rsp, 50h
0x1800247cb  pop     r14
0x1800247cd  pop     rdi
0x1800247ce  pop     rsi
0x1800247cf  pop     rbx
0x1800247d0  pop     rbp
0x1800247d1  retn
0x1800247d2  lea     rdx, [rbp+var_20]
0x1800247d6  mov     ecx, eax
0x1800247d8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetApplicableSoftwareUpdates(void)

- ea: `0x180026324`
- end: `0x1800263db`
- name: `?GetApplicableSoftwareUpdates@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800263f0`

## callees

- `0x180016fe4`
- `0x18001d50c`
- `0x180026324`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetApplicableSoftwareUpdates(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  __int64 v7; // r8
  unsigned int v9; // [rsp+28h] [rbp-18h] BYREF
  __int128 v10; // [rsp+30h] [rbp-10h]
  __int64 v11; // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF

  v12 = 0;
  v4 = *a1;
  if ( v4 )
  {
    v11 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int128 *, __int64 *))v4)(
           v4,
           &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>,
           &v11);
    v4 = v11;
  }
  else
  {
    v5 = 0;
    v11 = 0;
  }
  v9 = 0;
  v10 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v9, a3);
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v12);
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v9, v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x180026324  mov     [rsp-8+arg_8], rbx
0x180026329  push    rbp
0x18002632a  mov     rbp, rsp
0x18002632d  sub     rsp, 40h
0x180026331  mov     rbx, rdx
0x180026334  mov     [rbp+arg_10], 0
0x18002633c  mov     rcx, [rcx]
0x18002633f  test    rcx, rcx
0x180026342  jnz     short loc_18002634C
0x180026344  xor     eax, eax
0x180026346  mov     [rbp+arg_0], rax
0x18002634a  jmp     short loc_180026372
0x18002634c  mov     [rbp+arg_0], 0
0x180026354  mov     rax, [rcx]
0x180026357  lea     r8, [rbp+arg_0]
0x18002635b  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180026362  mov     rax, [rax]
0x180026365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002636a  mov     rcx, [rbp+arg_0]
0x18002636e  mov     [rbp+arg_0], rcx
0x180026372  mov     [rbp+var_18], 0
0x180026379  xorps   xmm0, xmm0
0x18002637c  movdqu  [rbp+var_10], xmm0
0x180026381  test    eax, eax
0x180026383  js      short loc_1800263CF
0x180026385  mov     [rbp+var_18], 0
0x18002638c  movdqu  [rbp+var_10], xmm0
0x180026391  mov     rax, [rcx]
0x180026394  lea     rdx, [rbp+arg_10]
0x180026398  mov     rax, [rax+40h]
0x18002639c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263a1  test    eax, eax
0x1800263a3  js      short loc_1800263C3
0x1800263a5  lea     rcx, [rbp+arg_0]
0x1800263a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800263ae  mov     rax, [rbp+arg_10]
0x1800263b2  mov     [rbx], rax
0x1800263b5  mov     rax, rbx
0x1800263b8  mov     rbx, [rsp+40h+arg_8]
0x1800263bd  add     rsp, 40h
0x1800263c1  pop     rbp
0x1800263c2  retn
0x1800263c3  lea     rdx, [rbp+var_18]
0x1800263c7  mov     ecx, eax
0x1800263c9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800263cf  lea     rdx, [rbp+var_18]
0x1800263d3  mov     ecx, eax
0x1800263d5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

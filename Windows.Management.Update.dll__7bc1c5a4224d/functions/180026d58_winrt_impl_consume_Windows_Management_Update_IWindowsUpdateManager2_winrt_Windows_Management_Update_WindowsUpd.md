# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(void)

- ea: `0x180026d58`
- end: `0x180026e20`
- name: `?ProviderIds@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027310`

## callees

- `0x180016fe4`
- `0x18001d50c`
- `0x180026d58`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  __int64 v7; // r8
  unsigned int v9; // [rsp+28h] [rbp-18h] BYREF
  __int128 v10; // [rsp+30h] [rbp-10h]
  int v11; // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  __int64 v13; // [rsp+68h] [rbp+28h] BYREF

  v11 = 0;
  v13 = 0;
  v4 = *a1;
  if ( v4 )
  {
    v12 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int128 *, __int64 *))v4)(
           v4,
           &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>,
           &v12);
    v4 = v12;
  }
  else
  {
    v5 = 0;
    v12 = 0;
  }
  v9 = 0;
  v10 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v9, a3);
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v4 + 56LL))(v4, &v11, &v13);
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v9, v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  *(_QWORD *)a2 = v13;
  *(_DWORD *)(a2 + 8) = v11;
  return a2;
}

```

## disassembly

```asm
0x180026d58  mov     [rsp-8+arg_8], rbx
0x180026d5d  push    rbp
0x180026d5e  mov     rbp, rsp
0x180026d61  sub     rsp, 40h
0x180026d65  mov     rbx, rdx
0x180026d68  mov     [rbp+arg_0], 0
0x180026d6f  mov     [rbp+arg_18], 0
0x180026d77  mov     rcx, [rcx]
0x180026d7a  test    rcx, rcx
0x180026d7d  jnz     short loc_180026D87
0x180026d7f  xor     eax, eax
0x180026d81  mov     [rbp+arg_10], rax
0x180026d85  jmp     short loc_180026DAD
0x180026d87  mov     [rbp+arg_10], 0
0x180026d8f  mov     rax, [rcx]
0x180026d92  lea     r8, [rbp+arg_10]
0x180026d96  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180026d9d  mov     rax, [rax]
0x180026da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026da5  mov     rcx, [rbp+arg_10]
0x180026da9  mov     [rbp+arg_10], rcx
0x180026dad  mov     [rbp+var_18], 0
0x180026db4  xorps   xmm0, xmm0
0x180026db7  movdqu  [rbp+var_10], xmm0
0x180026dbc  test    eax, eax
0x180026dbe  js      short loc_180026E14
0x180026dc0  mov     [rbp+var_18], 0
0x180026dc7  movdqu  [rbp+var_10], xmm0
0x180026dcc  mov     rax, [rcx]
0x180026dcf  lea     r8, [rbp+arg_18]
0x180026dd3  lea     rdx, [rbp+arg_0]
0x180026dd7  mov     rax, [rax+38h]
0x180026ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026de0  test    eax, eax
0x180026de2  js      short loc_180026E08
0x180026de4  lea     rcx, [rbp+arg_10]
0x180026de8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026ded  mov     rax, [rbp+arg_18]
0x180026df1  mov     [rbx], rax
0x180026df4  mov     eax, [rbp+arg_0]
0x180026df7  mov     [rbx+8], eax
0x180026dfa  mov     rax, rbx
0x180026dfd  mov     rbx, [rsp+40h+arg_8]
0x180026e02  add     rsp, 40h
0x180026e06  pop     rbp
0x180026e07  retn
0x180026e08  lea     rdx, [rbp+var_18]
0x180026e0c  mov     ecx, eax
0x180026e0e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180026e14  lea     rdx, [rbp+var_18]
0x180026e18  mov     ecx, eax
0x180026e1a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

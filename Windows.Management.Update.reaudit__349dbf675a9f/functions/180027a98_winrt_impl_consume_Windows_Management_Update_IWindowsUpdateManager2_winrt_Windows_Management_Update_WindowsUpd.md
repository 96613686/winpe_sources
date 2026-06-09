# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(winrt::param::hstring const &)

- ea: `0x180027a98`
- end: `0x180027b58`
- name: `?GetProvider@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027b60`

## callees

- `0x180017c3c`
- `0x18001e7a4`
- `0x180027a98`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(
        __int64 (__fastcall ****a1)(_QWORD, __int128 *, __int64 *),
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 (__fastcall ***v5)(_QWORD, __int128 *, __int64 *); // rcx
  signed int v6; // eax
  __int64 v7; // rdi
  signed int v8; // eax
  __int64 v9; // r8
  __int64 v11; // [rsp+28h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+30h] [rbp-20h] BYREF
  __int128 v13; // [rsp+38h] [rbp-18h]
  __int64 v14; // [rsp+70h] [rbp+20h] BYREF
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF

  v11 = 0;
  v5 = *a1;
  if ( v5 )
  {
    v14 = 0;
    v6 = (**v5)(v5, &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>, &v14);
    v7 = v14;
    v15 = v14;
  }
  else
  {
    v6 = 0;
    v15 = 0;
    v7 = 0;
  }
  v12 = 0;
  v13 = 0;
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v12, (__int64)a3);
  v12 = 0;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 48LL))(v7, *a3, &v11);
  if ( v8 < 0 )
    winrt::throw_hresult(v8, &v12, v9);
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x180027a98  mov     [rsp-18h+arg_8], rbx
0x180027a9d  push    rbp
0x180027a9e  push    rsi
0x180027a9f  push    rdi
0x180027aa0  mov     rbp, rsp
0x180027aa3  sub     rsp, 50h
0x180027aa7  mov     rsi, r8
0x180027aaa  mov     rbx, rdx
0x180027aad  and     [rbp+var_28], 0
0x180027ab2  mov     rcx, [rcx]
0x180027ab5  test    rcx, rcx
0x180027ab8  jnz     short loc_180027AC4
0x180027aba  xor     eax, eax
0x180027abc  and     [rbp+arg_18], rax
0x180027ac0  xor     edi, edi
0x180027ac2  jmp     short loc_180027AE7
0x180027ac4  and     [rbp+arg_0], 0
0x180027ac9  mov     rax, [rcx]
0x180027acc  lea     r8, [rbp+arg_0]
0x180027ad0  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180027ad7  mov     rax, [rax]
0x180027ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027adf  mov     rdi, [rbp+arg_0]
0x180027ae3  mov     [rbp+arg_18], rdi
0x180027ae7  and     [rbp+var_20], 0
0x180027aeb  xorps   xmm0, xmm0
0x180027aee  movdqu  [rbp+var_18], xmm0
0x180027af3  test    eax, eax
0x180027af5  js      short loc_180027B4C
0x180027af7  and     [rbp+var_20], 0
0x180027afb  movdqu  [rbp+var_18], xmm0
0x180027b00  mov     rax, [rdi]
0x180027b03  lea     r8, [rbp+var_28]
0x180027b07  mov     rdx, [rsi]
0x180027b0a  mov     rcx, rdi
0x180027b0d  mov     rax, [rax+30h]
0x180027b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b16  test    eax, eax
0x180027b18  js      short loc_180027B40
0x180027b1a  test    rdi, rdi
0x180027b1d  jz      short loc_180027B28
0x180027b1f  lea     rcx, [rbp+arg_18]
0x180027b23  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027b28  mov     rax, [rbp+var_28]
0x180027b2c  mov     [rbx], rax
0x180027b2f  mov     rax, rbx
0x180027b32  mov     rbx, [rsp+50h+arg_8]
0x180027b37  add     rsp, 50h
0x180027b3b  pop     rdi
0x180027b3c  pop     rsi
0x180027b3d  pop     rbp
0x180027b3e  retn
0x180027b40  lea     rdx, [rbp+var_20]
0x180027b44  mov     ecx, eax
0x180027b46  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180027b4c  lea     rdx, [rbp+var_20]
0x180027b50  mov     ecx, eax
0x180027b52  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

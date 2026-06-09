# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(winrt::Windows::Management::Update::WindowsUpdateManagerScanOptions const &)

- ea: `0x180026be8`
- end: `0x180026caf`
- name: `?PerformScan@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUWindowsUpdateManagerScanOptions@Update@Management@Windows@3@@Z`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026cc0`

## callees

- `0x180016fe4`
- `0x18001d50c`
- `0x180026be8`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  signed int v6; // eax
  signed int v7; // eax
  __int64 v8; // r8
  unsigned int v10; // [rsp+28h] [rbp-18h] BYREF
  __int128 v11; // [rsp+30h] [rbp-10h]
  __int64 v12; // [rsp+50h] [rbp+10h] BYREF
  __int64 v13; // [rsp+68h] [rbp+28h] BYREF

  v13 = 0;
  v5 = *a1;
  if ( v5 )
  {
    v12 = 0;
    v6 = (**(__int64 (__fastcall ***)(__int64, __int128 *, __int64 *))v5)(
           v5,
           &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>,
           &v12);
    v5 = v12;
  }
  else
  {
    v6 = 0;
    v12 = 0;
  }
  v10 = 0;
  v11 = 0;
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v10, (__int64)a3);
  v10 = 0;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 72LL))(v5, *a3, &v13);
  if ( v7 < 0 )
    winrt::throw_hresult(v7, &v10, v8);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  *a2 = v13;
  return a2;
}

```

## disassembly

```asm
0x180026be8  mov     [rsp-8+arg_8], rbx
0x180026bed  mov     [rsp-8+arg_10], rdi
0x180026bf2  push    rbp
0x180026bf3  mov     rbp, rsp
0x180026bf6  sub     rsp, 40h
0x180026bfa  mov     rdi, r8
0x180026bfd  mov     rbx, rdx
0x180026c00  mov     [rbp+arg_18], 0
0x180026c08  mov     rcx, [rcx]
0x180026c0b  test    rcx, rcx
0x180026c0e  jnz     short loc_180026C18
0x180026c10  xor     eax, eax
0x180026c12  mov     [rbp+arg_0], rax
0x180026c16  jmp     short loc_180026C3E
0x180026c18  mov     [rbp+arg_0], 0
0x180026c20  mov     rax, [rcx]
0x180026c23  lea     r8, [rbp+arg_0]
0x180026c27  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180026c2e  mov     rax, [rax]
0x180026c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c36  mov     rcx, [rbp+arg_0]
0x180026c3a  mov     [rbp+arg_0], rcx
0x180026c3e  mov     [rbp+var_18], 0
0x180026c45  xorps   xmm0, xmm0
0x180026c48  movdqu  [rbp+var_10], xmm0
0x180026c4d  test    eax, eax
0x180026c4f  js      short loc_180026CA3
0x180026c51  mov     [rbp+var_18], 0
0x180026c58  movdqu  [rbp+var_10], xmm0
0x180026c5d  mov     rax, [rcx]
0x180026c60  lea     r8, [rbp+arg_18]
0x180026c64  mov     rdx, [rdi]
0x180026c67  mov     rax, [rax+48h]
0x180026c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c70  test    eax, eax
0x180026c72  js      short loc_180026C97
0x180026c74  lea     rcx, [rbp+arg_0]
0x180026c78  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026c7d  mov     rax, [rbp+arg_18]
0x180026c81  mov     [rbx], rax
0x180026c84  mov     rax, rbx
0x180026c87  mov     rbx, [rsp+40h+arg_8]
0x180026c8c  mov     rdi, [rsp+40h+arg_10]
0x180026c91  add     rsp, 40h
0x180026c95  pop     rbp
0x180026c96  retn
0x180026c97  lea     rdx, [rbp+var_18]
0x180026c9b  mov     ecx, eax
0x180026c9d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180026ca3  lea     rdx, [rbp+var_18]
0x180026ca7  mov     ecx, eax
0x180026ca9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

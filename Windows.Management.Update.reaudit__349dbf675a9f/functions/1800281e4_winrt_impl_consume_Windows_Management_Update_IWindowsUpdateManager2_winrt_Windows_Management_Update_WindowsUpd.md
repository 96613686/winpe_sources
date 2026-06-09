# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(void)

- ea: `0x1800281e4`
- end: `0x1800282a3`
- name: `?ProviderIds@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028770`

## callees

- `0x180017c3c`
- `0x18001e7a4`
- `0x1800281e4`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(
        __int64 (__fastcall ****a1)(_QWORD, __int128 *, __int64 *),
        __int64 a2,
        __int64 a3)
{
  __int64 (__fastcall ***v4)(_QWORD, __int128 *, __int64 *); // rcx
  signed int v5; // eax
  __int64 v6; // rdi
  signed int v7; // eax
  __int64 v8; // r8
  __int64 v10; // [rsp+28h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+30h] [rbp-20h] BYREF
  __int128 v12; // [rsp+38h] [rbp-18h]
  int v13; // [rsp+70h] [rbp+20h] BYREF
  __int64 v14; // [rsp+80h] [rbp+30h] BYREF
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  v10 = 0;
  v4 = *a1;
  if ( v4 )
  {
    v14 = 0;
    v5 = (**v4)(v4, &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>, &v14);
    v6 = v14;
    v15 = v14;
  }
  else
  {
    v5 = 0;
    v15 = 0;
    v6 = 0;
  }
  v11 = 0;
  v12 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v11, a3);
  v11 = 0;
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v6 + 56LL))(v6, &v13, &v10);
  if ( v7 < 0 )
    winrt::throw_hresult(v7, &v11, v8);
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  *(_QWORD *)a2 = v10;
  *(_DWORD *)(a2 + 8) = v13;
  return a2;
}

```

## disassembly

```asm
0x1800281e4  push    rbp
0x1800281e6  push    rbx
0x1800281e7  push    rdi
0x1800281e8  mov     rbp, rsp
0x1800281eb  sub     rsp, 50h
0x1800281ef  mov     rbx, rdx
0x1800281f2  and     [rbp+arg_0], 0
0x1800281f6  and     [rbp+var_28], 0
0x1800281fb  mov     rcx, [rcx]
0x1800281fe  test    rcx, rcx
0x180028201  jnz     short loc_18002820D
0x180028203  xor     eax, eax
0x180028205  and     [rbp+arg_18], rax
0x180028209  xor     edi, edi
0x18002820b  jmp     short loc_180028230
0x18002820d  and     [rbp+arg_10], 0
0x180028212  mov     rax, [rcx]
0x180028215  lea     r8, [rbp+arg_10]
0x180028219  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180028220  mov     rax, [rax]
0x180028223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028228  mov     rdi, [rbp+arg_10]
0x18002822c  mov     [rbp+arg_18], rdi
0x180028230  and     [rbp+var_20], 0
0x180028234  xorps   xmm0, xmm0
0x180028237  movdqu  [rbp+var_18], xmm0
0x18002823c  test    eax, eax
0x18002823e  js      short loc_180028297
0x180028240  and     [rbp+var_20], 0
0x180028244  movdqu  [rbp+var_18], xmm0
0x180028249  mov     rax, [rdi]
0x18002824c  lea     r8, [rbp+var_28]
0x180028250  lea     rdx, [rbp+arg_0]
0x180028254  mov     rcx, rdi
0x180028257  mov     rax, [rax+38h]
0x18002825b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028260  test    eax, eax
0x180028262  js      short loc_18002828B
0x180028264  test    rdi, rdi
0x180028267  jz      short loc_180028272
0x180028269  lea     rcx, [rbp+arg_18]
0x18002826d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028272  mov     rax, [rbp+var_28]
0x180028276  mov     [rbx], rax
0x180028279  mov     eax, [rbp+arg_0]
0x18002827c  mov     [rbx+8], eax
0x18002827f  mov     rax, rbx
0x180028282  add     rsp, 50h
0x180028286  pop     rdi
0x180028287  pop     rbx
0x180028288  pop     rbp
0x180028289  retn
0x18002828b  lea     rdx, [rbp+var_20]
0x18002828f  mov     ecx, eax
0x180028291  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028297  lea     rdx, [rbp+var_20]
0x18002829b  mov     ecx, eax
0x18002829d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

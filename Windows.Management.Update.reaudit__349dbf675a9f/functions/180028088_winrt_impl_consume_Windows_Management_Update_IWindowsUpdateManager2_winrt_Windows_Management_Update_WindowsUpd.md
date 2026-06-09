# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(winrt::Windows::Management::Update::WindowsUpdateManagerScanOptions const &)

- ea: `0x180028088`
- end: `0x180028148`
- name: `?PerformScan@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUWindowsUpdateManagerScanOptions@Update@Management@Windows@3@@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028150`

## callees

- `0x180017c3c`
- `0x18001e7a4`
- `0x180028088`
- `0x18002c010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(
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
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 72LL))(v7, *a3, &v11);
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
0x180028088  mov     [rsp-18h+arg_8], rbx
0x18002808d  push    rbp
0x18002808e  push    rsi
0x18002808f  push    rdi
0x180028090  mov     rbp, rsp
0x180028093  sub     rsp, 50h
0x180028097  mov     rsi, r8
0x18002809a  mov     rbx, rdx
0x18002809d  and     [rbp+var_28], 0
0x1800280a2  mov     rcx, [rcx]
0x1800280a5  test    rcx, rcx
0x1800280a8  jnz     short loc_1800280B4
0x1800280aa  xor     eax, eax
0x1800280ac  and     [rbp+arg_18], rax
0x1800280b0  xor     edi, edi
0x1800280b2  jmp     short loc_1800280D7
0x1800280b4  and     [rbp+arg_0], 0
0x1800280b9  mov     rax, [rcx]
0x1800280bc  lea     r8, [rbp+arg_0]
0x1800280c0  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x1800280c7  mov     rax, [rax]
0x1800280ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280cf  mov     rdi, [rbp+arg_0]
0x1800280d3  mov     [rbp+arg_18], rdi
0x1800280d7  and     [rbp+var_20], 0
0x1800280db  xorps   xmm0, xmm0
0x1800280de  movdqu  [rbp+var_18], xmm0
0x1800280e3  test    eax, eax
0x1800280e5  js      short loc_18002813C
0x1800280e7  and     [rbp+var_20], 0
0x1800280eb  movdqu  [rbp+var_18], xmm0
0x1800280f0  mov     rax, [rdi]
0x1800280f3  lea     r8, [rbp+var_28]
0x1800280f7  mov     rdx, [rsi]
0x1800280fa  mov     rcx, rdi
0x1800280fd  mov     rax, [rax+48h]
0x180028101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028106  test    eax, eax
0x180028108  js      short loc_180028130
0x18002810a  test    rdi, rdi
0x18002810d  jz      short loc_180028118
0x18002810f  lea     rcx, [rbp+arg_18]
0x180028113  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028118  mov     rax, [rbp+var_28]
0x18002811c  mov     [rbx], rax
0x18002811f  mov     rax, rbx
0x180028122  mov     rbx, [rsp+50h+arg_8]
0x180028127  add     rsp, 50h
0x18002812b  pop     rdi
0x18002812c  pop     rsi
0x18002812d  pop     rbp
0x18002812e  retn
0x180028130  lea     rdx, [rbp+var_20]
0x180028134  mov     ecx, eax
0x180028136  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002813c  lea     rdx, [rbp+var_20]
0x180028140  mov     ecx, eax
0x180028142  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

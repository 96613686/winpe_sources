# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetApplicableSoftwareUpdates(void)

- ea: `0x1800277cc`
- end: `0x18002787d`
- name: `?GetApplicableSoftwareUpdates@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027890`

## callees

- `0x180017c3c`
- `0x18001e7a4`
- `0x1800277cc`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetApplicableSoftwareUpdates(
        __int64 (__fastcall ****a1)(_QWORD, __int128 *, __int64 *),
        _QWORD *a2,
        __int64 a3)
{
  __int64 (__fastcall ***v4)(_QWORD, __int128 *, __int64 *); // rcx
  signed int v5; // eax
  __int64 v6; // rdi
  signed int v7; // eax
  __int64 v8; // r8
  unsigned int v10; // [rsp+28h] [rbp-18h] BYREF
  __int128 v11; // [rsp+30h] [rbp-10h]
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  __int64 v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  v4 = *a1;
  if ( v4 )
  {
    v12 = 0;
    v5 = (**v4)(v4, &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>, &v12);
    v6 = v12;
    v13 = v12;
  }
  else
  {
    v5 = 0;
    v13 = 0;
    v6 = 0;
  }
  v10 = 0;
  v11 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v10, a3);
  v10 = 0;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 64LL))(v6, &v14);
  if ( v7 < 0 )
    winrt::throw_hresult(v7, &v10, v8);
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
  *a2 = v14;
  return a2;
}

```

## disassembly

```asm
0x1800277cc  push    rbp
0x1800277ce  push    rbx
0x1800277cf  push    rdi
0x1800277d0  mov     rbp, rsp
0x1800277d3  sub     rsp, 40h
0x1800277d7  mov     rbx, rdx
0x1800277da  and     [rbp+arg_18], 0
0x1800277df  mov     rcx, [rcx]
0x1800277e2  test    rcx, rcx
0x1800277e5  jnz     short loc_1800277F1
0x1800277e7  xor     eax, eax
0x1800277e9  and     [rbp+arg_10], rax
0x1800277ed  xor     edi, edi
0x1800277ef  jmp     short loc_180027814
0x1800277f1  and     [rbp+arg_0], 0
0x1800277f6  mov     rax, [rcx]
0x1800277f9  lea     r8, [rbp+arg_0]
0x1800277fd  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180027804  mov     rax, [rax]
0x180027807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002780c  mov     rdi, [rbp+arg_0]
0x180027810  mov     [rbp+arg_10], rdi
0x180027814  and     [rbp+var_18], 0
0x180027818  xorps   xmm0, xmm0
0x18002781b  movdqu  [rbp+var_10], xmm0
0x180027820  test    eax, eax
0x180027822  js      short loc_180027871
0x180027824  and     [rbp+var_18], 0
0x180027828  movdqu  [rbp+var_10], xmm0
0x18002782d  mov     rax, [rdi]
0x180027830  lea     rdx, [rbp+arg_18]
0x180027834  mov     rcx, rdi
0x180027837  mov     rax, [rax+40h]
0x18002783b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027840  test    eax, eax
0x180027842  js      short loc_180027865
0x180027844  test    rdi, rdi
0x180027847  jz      short loc_180027852
0x180027849  lea     rcx, [rbp+arg_10]
0x18002784d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027852  mov     rax, [rbp+arg_18]
0x180027856  mov     [rbx], rax
0x180027859  mov     rax, rbx
0x18002785c  add     rsp, 40h
0x180027860  pop     rdi
0x180027861  pop     rbx
0x180027862  pop     rbp
0x180027863  retn
0x180027865  lea     rdx, [rbp+var_18]
0x180027869  mov     ecx, eax
0x18002786b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180027871  lea     rdx, [rbp+var_18]
0x180027875  mov     ecx, eax
0x180027877  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

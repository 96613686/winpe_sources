# winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(winrt::param::hstring const &)

- ea: `0x180026600`
- end: `0x1800266c7`
- name: `?GetProvider@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800266d0`

## callees

- `0x180016fe4`
- `0x18001d50c`
- `0x180026600`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(
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
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, *a3, &v13);
  if ( v7 < 0 )
    winrt::throw_hresult(v7, &v10, v8);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  *a2 = v13;
  return a2;
}

```

## disassembly

```asm
0x180026600  mov     [rsp-8+arg_8], rbx
0x180026605  mov     [rsp-8+arg_10], rdi
0x18002660a  push    rbp
0x18002660b  mov     rbp, rsp
0x18002660e  sub     rsp, 40h
0x180026612  mov     rdi, r8
0x180026615  mov     rbx, rdx
0x180026618  mov     [rbp+arg_18], 0
0x180026620  mov     rcx, [rcx]
0x180026623  test    rcx, rcx
0x180026626  jnz     short loc_180026630
0x180026628  xor     eax, eax
0x18002662a  mov     [rbp+arg_0], rax
0x18002662e  jmp     short loc_180026656
0x180026630  mov     [rbp+arg_0], 0
0x180026638  mov     rax, [rcx]
0x18002663b  lea     r8, [rbp+arg_0]
0x18002663f  lea     rdx, ??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180026646  mov     rax, [rax]
0x180026649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002664e  mov     rcx, [rbp+arg_0]
0x180026652  mov     [rbp+arg_0], rcx
0x180026656  mov     [rbp+var_18], 0
0x18002665d  xorps   xmm0, xmm0
0x180026660  movdqu  [rbp+var_10], xmm0
0x180026665  test    eax, eax
0x180026667  js      short loc_1800266BB
0x180026669  mov     [rbp+var_18], 0
0x180026670  movdqu  [rbp+var_10], xmm0
0x180026675  mov     rax, [rcx]
0x180026678  lea     r8, [rbp+arg_18]
0x18002667c  mov     rdx, [rdi]
0x18002667f  mov     rax, [rax+30h]
0x180026683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026688  test    eax, eax
0x18002668a  js      short loc_1800266AF
0x18002668c  lea     rcx, [rbp+arg_0]
0x180026690  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026695  mov     rax, [rbp+arg_18]
0x180026699  mov     [rbx], rax
0x18002669c  mov     rax, rbx
0x18002669f  mov     rbx, [rsp+40h+arg_8]
0x1800266a4  mov     rdi, [rsp+40h+arg_10]
0x1800266a9  add     rsp, 40h
0x1800266ad  pop     rbp
0x1800266ae  retn
0x1800266af  lea     rdx, [rbp+var_18]
0x1800266b3  mov     ecx, eax
0x1800266b5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800266bb  lea     rdx, [rbp+var_18]
0x1800266bf  mov     ecx, eax
0x1800266c1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

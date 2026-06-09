# _lambda_b806adfb745e058df68578b199533233_::operator()_winrt::Windows::Internal::Shell::AppRestore::RestorableApp_

- ea: `0x1800751b8`
- end: `0x180075275`
- name: `_lambda_b806adfb745e058df68578b199533233_::operator()_winrt::Windows::Internal::Shell::AppRestore::RestorableApp_`
- size: `189`
- prototype: `__int64 __fastcall(winrt::hstring *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180075704`

## callees

- `0x180012b84`
- `0x180012c0c`
- `0x1800388d4`
- `0x18003cebc`
- `0x1800751b8`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180075200`
- `KERNEL32!CompareStringOrdinal` at `0x180075247`
- `KERNEL32!CompareStringOrdinal` at `0x180075200`
- `KERNEL32!CompareStringOrdinal` at `0x180075247`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall lambda_b806adfb745e058df68578b199533233_::operator()_winrt::Windows::Internal::Shell::AppRestore::RestorableApp_(
        winrt::hstring *this,
        __int64 a2)
{
  const WCHAR *v4; // rax
  LPCWCH v5; // r10
  bool v6; // bl
  const WCHAR *v7; // rax
  LPCWCH v8; // r10
  char v10; // [rsp+40h] [rbp+8h] BYREF
  char v11; // [rsp+50h] [rbp+18h] BYREF

  winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::TelemetryId(
    a2,
    &v11);
  winrt::hstring::c_str(this);
  v4 = winrt::hstring::c_str((winrt::hstring *)&v11);
  if ( CompareStringOrdinal(v5, -1, v4, -1, 1) == 2 )
  {
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
      a2,
      &v10);
    winrt::hstring::c_str((winrt::hstring *)((char *)this + 8));
    v7 = winrt::hstring::c_str((winrt::hstring *)&v10);
    v6 = CompareStringOrdinal(v8, -1, v7, -1, 1) == 2;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v10);
  }
  else
  {
    v6 = 0;
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v11);
  return v6;
}

```

## disassembly

```asm
0x1800751b8  mov     [rsp+arg_8], rbx
0x1800751bd  push    rdi
0x1800751be  sub     rsp, 30h
0x1800751c2  mov     rbx, rdx
0x1800751c5  mov     rdi, rcx
0x1800751c8  lea     rdx, [rsp+38h+arg_10]
0x1800751cd  mov     rcx, rbx
0x1800751d0  call    ?TelemetryId@?$consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::TelemetryId(void)
0x1800751d5  nop
0x1800751d6  mov     rcx, rdi; this
0x1800751d9  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800751de  mov     r10, rax
0x1800751e1  lea     rcx, [rsp+38h+arg_10]; this
0x1800751e6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800751eb  mov     r8, rax; lpString2
0x1800751ee  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800751f6  or      r9d, 0FFFFFFFFh; cchCount2
0x1800751fa  or      edx, r9d; cchCount1
0x1800751fd  mov     rcx, r10; lpString1
0x180075200  call    cs:__imp_CompareStringOrdinal
0x180075206  cmp     eax, 2
0x180075209  jz      short loc_18007520F
0x18007520b  xor     ebx, ebx
0x18007520d  jmp     short loc_18007525E
0x18007520f  lea     rdx, [rsp+38h+arg_0]
0x180075214  mov     rcx, rbx
0x180075217  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(void)
0x18007521c  lea     rcx, [rdi+8]; this
0x180075220  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180075225  mov     r10, rax
0x180075228  lea     rcx, [rsp+38h+arg_0]; this
0x18007522d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180075232  mov     r8, rax; lpString2
0x180075235  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18007523d  or      r9d, 0FFFFFFFFh; cchCount2
0x180075241  or      edx, r9d; cchCount1
0x180075244  mov     rcx, r10; lpString1
0x180075247  call    cs:__imp_CompareStringOrdinal
0x18007524d  cmp     eax, 2
0x180075250  setz    bl
0x180075253  lea     rcx, [rsp+38h+arg_0]
0x180075258  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18007525d  nop
0x18007525e  lea     rcx, [rsp+38h+arg_10]
0x180075263  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180075268  mov     al, bl
0x18007526a  mov     rbx, [rsp+38h+arg_8]
0x18007526f  add     rsp, 30h
0x180075273  pop     rdi
0x180075274  retn
```

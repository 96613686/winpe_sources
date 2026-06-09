# wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS)

- ea: `0x1800123b0`
- end: `0x180012426`
- name: `??$wait_for_completion@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z`
- size: `118`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014c20`

## callees

- `0x18000cd18`
- `0x180011c14`
- `0x1800123b0`
- `0x180024010`

## string_xrefs

- `0x180012414`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(
        _QWORD *a1,
        __int64 a2)
{
  int v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v4 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(a2);
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 64LL))(a2, a1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v4,
      1);
  return a1;
}

```

## disassembly

```asm
0x1800123b0  mov     rax, rsp
0x1800123b3  mov     [rax+10h], rbx
0x1800123b7  mov     [rax+8], rcx
0x1800123bb  push    rdi
0x1800123bc  sub     rsp, 30h
0x1800123c0  mov     rdi, rdx
0x1800123c3  mov     rbx, rcx
0x1800123c6  mov     dword ptr [rax-18h], 0
0x1800123cd  mov     qword ptr [rcx], 0
0x1800123d4  mov     dword ptr [rax-18h], 1
0x1800123db  mov     rcx, rdx
0x1800123de  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x1800123e3  test    eax, eax
0x1800123e5  js      short loc_1800123FA
0x1800123e7  mov     rax, [rdi]
0x1800123ea  mov     rdx, rbx
0x1800123ed  mov     rcx, rdi
0x1800123f0  mov     rax, [rax+40h]
0x1800123f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123f9  nop
0x1800123fa  test    eax, eax
0x1800123fc  js      short loc_18001240C
0x1800123fe  mov     rax, rbx
0x180012401  mov     rbx, [rsp+38h+arg_8]
0x180012406  add     rsp, 30h
0x18001240a  pop     rdi
0x18001240b  retn
0x18001240c  mov     rcx, [rsp+38h]; this
0x180012411  mov     r9d, eax; char *
0x180012414  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001241b  mov     edx, 71Bh; void *
0x180012420  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

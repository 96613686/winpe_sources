# winrt::com_array<winrt::Windows::Foundation::IInspectable>::~com_array<winrt::Windows::Foundation::IInspectable>(void)

- ea: `0x18000ade0`
- end: `0x18000ae3d`
- name: `??1?$com_array@UIInspectable@Foundation@Windows@winrt@@@winrt@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d496`

## callees

- `0x1800040a0`
- `0x18000ade0`
- `0x180039899`

## pseudocode

```c
void __fastcall winrt::com_array<winrt::Windows::Foundation::IInspectable>::~com_array<winrt::Windows::Foundation::IInspectable>(
        __int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *i; // rdi

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = &v1[*(unsigned int *)(a1 + 8)]; v1 != i; ++v1 )
    {
      if ( *v1 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1);
    }
    CoTaskMemFree_0(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000ade0  mov     [rsp+arg_10], rbx
0x18000ade5  push    rsi
0x18000ade6  sub     rsp, 20h
0x18000adea  mov     rbx, [rcx]
0x18000aded  mov     rsi, rcx
0x18000adf0  test    rbx, rbx
0x18000adf3  jz      short loc_18000AE32
0x18000adf5  mov     eax, [rcx+8]
0x18000adf8  mov     [rsp+28h+arg_8], rdi
0x18000adfd  lea     rdi, [rbx+rax*8]
0x18000ae01  cmp     rbx, rdi
0x18000ae04  jz      short loc_18000AE1D
0x18000ae06  cmp     qword ptr [rbx], 0
0x18000ae0a  jz      short loc_18000AE14
0x18000ae0c  mov     rcx, rbx
0x18000ae0f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ae14  add     rbx, 8
0x18000ae18  cmp     rbx, rdi
0x18000ae1b  jnz     short loc_18000AE06
0x18000ae1d  mov     rcx, [rsi]; pv
0x18000ae20  call    CoTaskMemFree_0
0x18000ae25  mov     rdi, [rsp+28h+arg_8]
0x18000ae2a  xor     eax, eax
0x18000ae2c  mov     [rsi], rax
0x18000ae2f  mov     [rsi+8], eax
0x18000ae32  mov     rbx, [rsp+28h+arg_10]
0x18000ae37  add     rsp, 20h
0x18000ae3b  pop     rsi
0x18000ae3c  retn
```

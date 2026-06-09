# winrt::com_array<winrt::Windows::Foundation::IInspectable>::~com_array<winrt::Windows::Foundation::IInspectable>(void)

- ea: `0x1800099a0`
- end: `0x1800099fd`
- name: `??1?$com_array@UIInspectable@Foundation@Windows@winrt@@@winrt@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001deaa`

## callees

- `0x180003840`
- `0x1800099a0`
- `0x1800162c2`

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
0x1800099a0  mov     [rsp+arg_10], rbx
0x1800099a5  push    rsi
0x1800099a6  sub     rsp, 20h
0x1800099aa  mov     rbx, [rcx]
0x1800099ad  mov     rsi, rcx
0x1800099b0  test    rbx, rbx
0x1800099b3  jz      short loc_1800099F2
0x1800099b5  mov     eax, [rcx+8]
0x1800099b8  mov     [rsp+28h+arg_8], rdi
0x1800099bd  lea     rdi, [rbx+rax*8]
0x1800099c1  cmp     rbx, rdi
0x1800099c4  jz      short loc_1800099DD
0x1800099c6  cmp     qword ptr [rbx], 0
0x1800099ca  jz      short loc_1800099D4
0x1800099cc  mov     rcx, rbx
0x1800099cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800099d4  add     rbx, 8
0x1800099d8  cmp     rbx, rdi
0x1800099db  jnz     short loc_1800099C6
0x1800099dd  mov     rcx, [rsi]; pv
0x1800099e0  call    CoTaskMemFree_0
0x1800099e5  mov     rdi, [rsp+28h+arg_8]
0x1800099ea  xor     eax, eax
0x1800099ec  mov     [rsi], rax
0x1800099ef  mov     [rsi+8], eax
0x1800099f2  mov     rbx, [rsp+28h+arg_10]
0x1800099f7  add     rsp, 20h
0x1800099fb  pop     rsi
0x1800099fc  retn
```

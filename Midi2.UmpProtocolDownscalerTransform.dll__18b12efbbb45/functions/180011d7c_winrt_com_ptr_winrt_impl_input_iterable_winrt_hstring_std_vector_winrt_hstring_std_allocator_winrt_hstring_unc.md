# winrt::com_ptr<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>>>::unconditional_release_ref(void)

- ea: `0x180011d7c`
- end: `0x180011db2`
- name: `?unconditional_release_ref@?$com_ptr@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d860`

## callees

- `0x180011d7c`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>>::unconditional_release_ref(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // r8
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    *((_DWORD *)v1 + 2) = 1;
    return (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v1 + 8LL))(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180011d7c  sub     rsp, 28h
0x180011d80  mov     r8, [rcx]
0x180011d83  or      eax, 0FFFFFFFFh
0x180011d86  mov     qword ptr [rcx], 0
0x180011d8d  lock xadd [r8+8], eax
0x180011d93  cmp     eax, 1
0x180011d96  jnz     short loc_180011DAD
0x180011d98  mov     edx, eax
0x180011d9a  mov     [r8+8], eax
0x180011d9e  mov     rax, [r8]
0x180011da1  mov     rcx, r8
0x180011da4  mov     rax, [rax+8]
0x180011da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dad  add     rsp, 28h
0x180011db1  retn
```

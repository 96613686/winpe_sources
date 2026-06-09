# winrt::com_ptr<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>>>::unconditional_release_ref(void)

- ea: `0x1800103d8`
- end: `0x180010419`
- name: `?unconditional_release_ref@?$com_ptr@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `65`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a930`

## callees

- `0x18000ffa0`
- `0x1800103d8`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // r8
  __int64 result; // rax
  __int64 v3; // r8

  v1 = *a1;
  *a1 = 0;
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 8), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    result = std::_Atomic_storage<unsigned int,4>::store();
    if ( v3 )
      return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800103d8  sub     rsp, 28h
0x1800103dc  mov     r8, [rcx]
0x1800103df  or      eax, 0FFFFFFFFh
0x1800103e2  mov     qword ptr [rcx], 0
0x1800103e9  lea     rcx, [r8+8]
0x1800103ed  lock xadd [rcx], eax
0x1800103f1  cmp     eax, 1
0x1800103f4  jnz     short loc_180010414
0x1800103f6  call    ?store@?$_Atomic_storage@I$03@std@@QEAAXIW4memory_order@2@@Z; std::_Atomic_storage<uint,4>::store(uint,std::memory_order)
0x1800103fb  test    r8, r8
0x1800103fe  jz      short loc_180010414
0x180010400  mov     rax, [r8]
0x180010403  mov     edx, 1
0x180010408  mov     rcx, r8
0x18001040b  mov     rax, [rax+8]
0x18001040f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010414  add     rsp, 28h
0x180010418  retn
```

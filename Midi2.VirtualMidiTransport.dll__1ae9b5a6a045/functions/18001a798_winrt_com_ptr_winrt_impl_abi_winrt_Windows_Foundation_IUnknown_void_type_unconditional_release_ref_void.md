# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x18001a798`
- end: `0x18001a7b1`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012510`
- `0x180012f70`
- `0x1800130d0`
- `0x1800134d0`
- `0x1800135f4`
- `0x180013b20`
- `0x18001408c`
- `0x1800141c4`
- `0x180014278`
- `0x180014638`
- `0x180015ae4`
- `0x180018460`
- `0x1800199b4`
- `0x18001a010`
- `0x18001a65c`
- `0x18001bb50`
- `0x18001bcfc`
- `0x18001bea8`
- `0x18001c008`
- `0x18001c12c`
- `0x18001c250`
- `0x18001c494`
- `0x18001c828`
- `0x18001c8f4`
- `0x18001c9a8`
- `0x18001ca5c`
- `0x18001caf8`
- `0x18001cd1c`
- `0x18001cdf4`
- `0x18001cec4`
- `0x18001d184`
- `0x18001d4f4`
- `0x18001d5b0`
- `0x18001d680`
- `0x1800207c7`
- `0x1800208cb`
- `0x1800209cf`

## callees

- `0x180021010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18001a798  mov     rdx, [rcx]
0x18001a79b  mov     qword ptr [rcx], 0
0x18001a7a2  mov     rcx, rdx
0x18001a7a5  mov     rax, [rdx]
0x18001a7a8  mov     rax, [rax+10h]
0x18001a7ac  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

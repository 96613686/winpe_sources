# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x180010420`
- end: `0x180010432`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `18`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f95c`

## callees

- `0x18000e310`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  return winrt::impl::weak_ref<1,1>::Release(v2);
}

```

## disassembly

```asm
0x180010420  mov     rax, rcx
0x180010423  mov     rcx, [rcx]; void *
0x180010426  mov     qword ptr [rax], 0
0x18001042d  jmp     ?Release@?$weak_ref@$00$00@impl@winrt@@UEAAIXZ; winrt::impl::weak_ref<1,1>::Release(void)
```

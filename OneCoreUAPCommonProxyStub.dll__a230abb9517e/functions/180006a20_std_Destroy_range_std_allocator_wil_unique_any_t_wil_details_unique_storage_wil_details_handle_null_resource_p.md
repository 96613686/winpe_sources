# std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &)

- ea: `0x180006a20`
- end: `0x180006a51`
- name: `??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@@Z`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800035ec`
- `0x180006be8`
- `0x180006e94`
- `0x1800075b8`

## callees

- `0x1800029a0`
- `0x180006a20`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v3);
      v3 += 8;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180006a20  cmp     rcx, rdx
0x180006a23  jz      short locret_180006A50
0x180006a25  mov     [rsp+arg_0], rbx
0x180006a2a  push    rdi
0x180006a2b  sub     rsp, 20h
0x180006a2f  mov     rdi, rdx
0x180006a32  mov     rbx, rcx
0x180006a35  mov     rcx, rbx
0x180006a38  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006a3d  add     rbx, 8
0x180006a41  cmp     rbx, rdi
0x180006a44  jnz     short loc_180006A35
0x180006a46  mov     rbx, [rsp+28h+arg_0]
0x180006a4b  add     rsp, 20h
0x180006a4f  pop     rdi
0x180006a50  retn
```

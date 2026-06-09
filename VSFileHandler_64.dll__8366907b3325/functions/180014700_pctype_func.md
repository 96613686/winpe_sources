# __pctype_func

- ea: `0x180014700`
- end: `0x18001472f`
- name: `__pctype_func`
- size: `47`
- prototype: `const unsigned __int16 *__cdecl()`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000fcac`
- `0x180017ff8`
- `0x18001f9b8`
- `0x180022924`
- `0x1800239fc`

## callees

- `0x1800102a4`
- `0x180010cf0`

## pseudocode

```c
const unsigned __int16 *__cdecl _pctype_func()
{
  __int64 v0; // rax
  const unsigned __int16 **v2; // [rsp+30h] [rbp+8h] BYREF

  v0 = _acrt_getptd();
  v2 = *(const unsigned __int16 ***)(v0 + 144);
  _acrt_update_locale_info(v0, (__int64 *)&v2);
  return *v2;
}

```

## disassembly

```asm
0x180014700  sub     rsp, 28h
0x180014704  call    __acrt_getptd
0x180014709  lea     rdx, [rsp+28h+arg_0]
0x18001470e  mov     rcx, [rax+90h]
0x180014715  mov     [rsp+28h+arg_0], rcx
0x18001471a  mov     rcx, rax
0x18001471d  call    __acrt_update_locale_info
0x180014722  mov     rax, [rsp+28h+arg_0]
0x180014727  mov     rax, [rax]
0x18001472a  add     rsp, 28h
0x18001472e  retn
```

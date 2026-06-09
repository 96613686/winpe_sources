# _DllMainCRTStartupForGS2

- ea: `0x180015418`
- end: `0x180015430`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015c70`

## callees

- `0x180015418`
- `0x1800155c0`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartupForGS2(__int64 a1, int a2)
{
  if ( a2 == 1 )
    _security_init_cookie();
  return 1;
}

```

## disassembly

```asm
0x180015418  sub     rsp, 28h
0x18001541c  cmp     edx, 1
0x18001541f  jnz     short loc_180015426
0x180015421  call    __security_init_cookie
0x180015426  mov     eax, 1
0x18001542b  add     rsp, 28h
0x18001542f  retn
```

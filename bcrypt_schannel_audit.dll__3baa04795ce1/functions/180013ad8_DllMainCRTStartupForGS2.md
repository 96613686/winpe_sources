# _DllMainCRTStartupForGS2

- ea: `0x180013ad8`
- end: `0x180013af0`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a4e0`

## callees

- `0x180013ad8`
- `0x180013c80`

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
0x180013ad8  sub     rsp, 28h
0x180013adc  cmp     edx, 1
0x180013adf  jnz     short loc_180013AE6
0x180013ae1  call    __security_init_cookie
0x180013ae6  mov     eax, 1
0x180013aeb  add     rsp, 28h
0x180013aef  retn
```

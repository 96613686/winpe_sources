# _abort

- ea: `0x40f51a`
- end: `0x40f55d`
- name: `_abort`
- size: `67`
- prototype: `void __cdecl __noreturn()`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x40d7cc`
- `0x40f45f`
- `0x40f9a9`
- `0x40fa66`
- `0x4109f4`
- `0x411ad9`

## callees

- `0x40dca8`
- `0x40ed57`
- `0x40f51a`
- `0x4121b1`
- `0x4121f6`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x40f536`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40f536`

## pseudocode

```c
void __cdecl __noreturn abort()
{
  if ( __acrt_get_sigabrt_handler() )
    raise(22);
  if ( (byte_417040 & 2) != 0 )
  {
    if ( IsProcessorFeaturePresent(0x17u) )
      __fastfail(7u);
    __acrt_call_reportfault(3, 1073741845, 1);
  }
  _exit(3);
}

```

## disassembly

```asm
0x40f51a  call    ___acrt_get_sigabrt_handler
0x40f51f  test    eax, eax
0x40f521  jz      short loc_40F52B
0x40f523  push    16h; Signal
0x40f525  call    _raise
0x40f52a  pop     ecx
0x40f52b  test    byte_417040, 2
0x40f532  jz      short loc_40F556
0x40f534  push    17h; ProcessorFeature
0x40f536  call    ds:IsProcessorFeaturePresent
0x40f53c  test    eax, eax
0x40f53e  jz      short loc_40F545
0x40f540  push    7
0x40f542  pop     ecx
0x40f543  int     29h; Win8: RtlFailFast(ecx)
0x40f545  push    1
0x40f547  push    40000015h
0x40f54c  push    3
0x40f54e  call    ___acrt_call_reportfault
0x40f553  add     esp, 0Ch
0x40f556  push    3; Code
0x40f558  call    __exit
```

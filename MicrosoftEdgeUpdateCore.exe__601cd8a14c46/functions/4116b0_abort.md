# _abort

- ea: `0x4116b0`
- end: `0x4116f3`
- name: `_abort`
- size: `67`
- prototype: `void __cdecl __noreturn()`
- caller_count: `16`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x40e8fc`
- `0x40ee60`
- `0x40ee7c`
- `0x40f117`
- `0x40f240`
- `0x40f37e`
- `0x40f497`
- `0x40f85a`
- `0x40fdbc`
- `0x40fe5d`
- `0x40ff45`
- `0x411615`
- `0x413a39`
- `0x413af6`
- `0x414814`
- `0x416b01`

## callees

- `0x4101bd`
- `0x4108dd`
- `0x4116b0`
- `0x41563b`
- `0x415680`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x4116cc`
- `KERNEL32!IsProcessorFeaturePresent` at `0x4116cc`

## pseudocode

```c
void __cdecl __noreturn abort()
{
  if ( __acrt_get_sigabrt_handler() )
    raise(22);
  if ( (byte_43D058 & 2) != 0 )
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
0x4116b0  call    ___acrt_get_sigabrt_handler
0x4116b5  test    eax, eax
0x4116b7  jz      short loc_4116C1
0x4116b9  push    16h; Signal
0x4116bb  call    _raise
0x4116c0  pop     ecx
0x4116c1  test    byte_43D058, 2
0x4116c8  jz      short loc_4116EC
0x4116ca  push    17h; ProcessorFeature
0x4116cc  call    ds:IsProcessorFeaturePresent
0x4116d2  test    eax, eax
0x4116d4  jz      short loc_4116DB
0x4116d6  push    7
0x4116d8  pop     ecx
0x4116d9  int     29h; Win8: RtlFailFast(ecx)
0x4116db  push    1
0x4116dd  push    40000015h
0x4116e2  push    3
0x4116e4  call    ___acrt_call_reportfault
0x4116e9  add     esp, 0Ch
0x4116ec  push    3; Code
0x4116ee  call    __exit
```

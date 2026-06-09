# _guard_dispatch_icall_nop

- ea: `0x18006ccc0`
- end: `0x18006ccc2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `646`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000ae68`
- `0x18000af70`
- `0x18000b0c0`
- `0x18000b128`
- `0x18000b330`
- `0x18000b3a0`
- `0x18000b3f8`
- `0x18000b450`
- `0x18000b5e0`
- `0x18000b850`
- `0x18000b978`
- `0x18000b9fc`
- `0x18000bb04`
- `0x18000bba4`
- `0x18000be4c`
- `0x18000c2e4`
- `0x18000c670`
- `0x18000ec6c`
- `0x18000ede8`
- `0x180011224`
- `0x180011320`
- `0x1800113b0`
- `0x1800118b8`
- `0x180011bc8`
- `0x180011ee8`
- `0x180012200`
- `0x180012518`
- `0x18001282c`
- `0x180012b50`
- `0x180012e60`
- `0x18001318c`
- `0x1800134a4`
- `0x1800137e0`
- `0x1800138e4`
- `0x180013960`
- `0x180013a70`
- `0x180013c40`
- `0x180013ea0`
- `0x1800144d0`
- `0x180014530`
- `0x180014720`
- `0x180014798`
- `0x180014884`
- `0x1800148c8`
- `0x180014938`
- `0x180014990`
- `0x180014a30`
- `0x180014a74`
- `0x180014ce8`
- `0x180014e70`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x18006ccc0  jmp     rax
```

# j__guard_dispatch_icall

- ea: `0x180039010`
- end: `0x180039015`
- name: `j__guard_dispatch_icall`
- size: `5`
- prototype: ``
- caller_count: `172`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001010`
- `0x180001418`
- `0x1800015bc`
- `0x18000186c`
- `0x180001cac`
- `0x180001cf0`
- `0x180002040`
- `0x180002280`
- `0x1800022dc`
- `0x1800031a0`
- `0x180003740`
- `0x180003938`
- `0x1800050b0`
- `0x1800052e4`
- `0x180006ac4`
- `0x180007890`
- `0x18000a620`
- `0x18000a860`
- `0x18000af10`
- `0x18000b140`
- `0x18000b770`
- `0x18000b860`
- `0x18000baa0`
- `0x18000bbe0`
- `0x18000bdd0`
- `0x18000c050`
- `0x18000c1e0`
- `0x18000c5b0`
- `0x18000c700`
- `0x18000d3f0`
- `0x18000d760`
- `0x18000deb0`
- `0x18000eb10`
- `0x18000edb0`
- `0x180010b40`
- `0x180010cd0`
- `0x180011ce0`
- `0x180011fe0`
- `0x1800123a0`
- `0x1800126f0`
- `0x180012a30`
- `0x180013370`
- `0x1800135e0`
- `0x1800137f0`
- `0x180013910`
- `0x180013ad0`
- `0x180013b50`
- `0x180013e30`
- `0x180014070`
- `0x180018320`

## callees

- `0x180037390`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j__guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180039010  jmp     _guard_dispatch_icall
```

# Kerb3961::ConsistencyFail(ushort const *)

- ea: `0x1800033f4`
- end: `0x180003409`
- name: `?ConsistencyFail@Kerb3961@@YAXPEBG@Z`
- size: `21`
- prototype: `void __fastcall __noreturn(Kerb3961 *__hidden this, const unsigned __int16 *)`
- caller_count: `54`
- callee_count: `1`
- tags: ``

## callers

- `0x180001510`
- `0x180003610`
- `0x1800046e0`
- `0x180004750`
- `0x1800047e4`
- `0x180004b40`
- `0x1800050e0`
- `0x180005480`
- `0x180005ed0`
- `0x180006270`
- `0x180006ac0`
- `0x180007a90`
- `0x1800095b0`
- `0x18000a2a0`
- `0x18000a794`
- `0x18000ab94`
- `0x18000afb0`
- `0x18000b024`
- `0x18000b0f0`
- `0x18000b210`
- `0x18000b3d0`
- `0x18000ba20`
- `0x18000bc90`
- `0x18000bcd0`
- `0x18000c060`
- `0x18000c320`
- `0x18000c4a0`
- `0x18000c4c8`
- `0x18000ca80`
- `0x18000cdb0`
- `0x18000cfd0`
- `0x18000d510`
- `0x18000d6e0`
- `0x18000d960`
- `0x18000db90`
- `0x18000dd60`
- `0x18000de8c`
- `0x18000df98`
- `0x18000e320`
- `0x18000ec30`
- `0x18000f030`
- `0x180010124`
- `0x1800101b8`
- `0x180010f4c`
- `0x1800110c0`
- `0x18001190c`
- `0x180012260`
- `0x180013b00`
- `0x1800166e0`
- `0x1800190d0`

## callees

- `0x180002d18`

## pseudocode

```c
void __fastcall __noreturn Kerb3961::ConsistencyFail(Kerb3961 *this, const unsigned __int16 *a2)
{
  Kerb3961::Logging::Verify::ConsistencyFail(this, a2);
  __fastfail(0x29Cu);
}

```

## disassembly

```asm
0x1800033f4  sub     rsp, 28h
0x1800033f8  call    ?ConsistencyFail@Verify@Logging@Kerb3961@@YAXPEBG@Z; Kerb3961::Logging::Verify::ConsistencyFail(ushort const *)
0x1800033fd  mov     ecx, 29Ch
0x180003402  int     29h; Win8: RtlFailFast(ecx)
0x180003404  add     rsp, 28h
0x180003408  retn
```

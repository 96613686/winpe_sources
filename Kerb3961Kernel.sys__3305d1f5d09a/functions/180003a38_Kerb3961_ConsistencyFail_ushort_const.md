# Kerb3961::ConsistencyFail(ushort const *)

- ea: `0x180003a38`
- end: `0x180003a4e`
- name: `?ConsistencyFail@Kerb3961@@YAXPEBG@Z`
- size: `22`
- prototype: `void __fastcall __noreturn(Kerb3961 *__hidden this, const unsigned __int16 *)`
- caller_count: `39`
- callee_count: `1`
- tags: ``

## callers

- `0x180001170`
- `0x180001580`
- `0x1800015f0`
- `0x180001684`
- `0x180001700`
- `0x180001794`
- `0x180001e7c`
- `0x1800023e0`
- `0x180002cc4`
- `0x180003590`
- `0x180003b10`
- `0x180004700`
- `0x180004f80`
- `0x180005c30`
- `0x1800060f0`
- `0x180006f6c`
- `0x180008840`
- `0x180009040`
- `0x180009da0`
- `0x18000b0c8`
- `0x18000b510`
- `0x18000ba20`
- `0x18000bab0`
- `0x18000bb20`
- `0x18000bfc0`
- `0x18000c000`
- `0x18000c110`
- `0x18000c200`
- `0x18000c230`
- `0x18000d000`
- `0x18000d100`
- `0x18000d3c0`
- `0x18000d580`
- `0x18000d900`
- `0x18000e310`
- `0x18000e6b0`
- `0x18000eec0`
- `0x180010460`
- `0x180010e6c`

## callees

- `0x180011814`

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
0x180003a38  sub     rsp, 28h
0x180003a3c  call    ?ConsistencyFail@Verify@Logging@Kerb3961@@YAXPEBG@Z; Kerb3961::Logging::Verify::ConsistencyFail(ushort const *)
0x180003a41  mov     ecx, 29Ch
0x180003a46  int     29h; Win8: RtlFailFast(ecx)
0x180003a48  add     rsp, 28h
0x180003a4c  retn
```

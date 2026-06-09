# DeleteMediaType(_AMMediaType *)

- ea: `0x180006af0`
- end: `0x180006b11`
- name: `?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z`
- size: `33`
- prototype: `void __fastcall(struct _AMMediaType *pv)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003134`
- `0x180003314`
- `0x180005e00`
- `0x180005fe0`
- `0x18001800c`
- `0x180019d80`
- `0x180019e40`
- `0x180022c80`
- `0x18002bc00`
- `0x18002be40`

## callees

- `0x180006af0`
- `0x180006b18`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006b05`
- `ole32!CoTaskMemFree` at `0x180006b05`

## pseudocode

```c
void __fastcall DeleteMediaType(struct _AMMediaType *pv)
{
  if ( pv )
  {
    FreeMediaType(pv);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180006af0  test    rcx, rcx
0x180006af3  jz      short locret_180006B10
0x180006af5  push    rbx
0x180006af6  sub     rsp, 20h
0x180006afa  mov     rbx, rcx
0x180006afd  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180006b02  mov     rcx, rbx; pv
0x180006b05  call    cs:__imp_CoTaskMemFree
0x180006b0b  add     rsp, 20h
0x180006b0f  pop     rbx
0x180006b10  retn
```

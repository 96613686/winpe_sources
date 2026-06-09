# std::_Facet_Register(std::_Facet_base *)

- ea: `0x18000254c`
- end: `0x180002584`
- name: `?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z`
- size: `56`
- prototype: `void __fastcall(struct std::_Facet_base *)`
- caller_count: `39`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c3c`
- `0x180002d80`
- `0x180002ec4`
- `0x180003008`
- `0x18000314c`
- `0x1800095bc`
- `0x180009700`
- `0x180009844`
- `0x180009988`
- `0x180009acc`
- `0x180009c10`
- `0x180009d54`
- `0x180009e98`
- `0x180009fdc`
- `0x18000a120`
- `0x18000a264`
- `0x18000a3a8`
- `0x18000a4ec`
- `0x18000a630`
- `0x18000a774`
- `0x18000a8b8`
- `0x18000a9fc`
- `0x18000ab40`
- `0x18000ac84`
- `0x18000adc8`
- `0x18000af0c`
- `0x18000b050`
- `0x18000b194`
- `0x18000b2d8`
- `0x18000b41c`
- `0x18000b560`
- `0x18001cc84`
- `0x18001cdc8`
- `0x18001cf0c`
- `0x18001d050`
- `0x18001d194`
- `0x18001d2d8`
- `0x18001d41c`
- `0x18001d560`

## callees

- `0x1800020c4`
- `0x18000254c`

## pseudocode

```c
void __fastcall std::_Facet_Register(struct std::_Facet_base *a1)
{
  _QWORD *v2; // rax

  v2 = operator new(0x10u);
  if ( v2 )
  {
    *v2 = qword_180046590;
    v2[1] = a1;
  }
  qword_180046590 = v2;
}

```

## disassembly

```asm
0x18000254c  push    rbx
0x18000254e  sub     rsp, 20h
0x180002552  mov     rbx, rcx
0x180002555  mov     ecx, 10h; Size
0x18000255a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000255f  mov     [rsp+28h+arg_8], rax
0x180002564  test    rax, rax
0x180002567  jz      short loc_180002577
0x180002569  mov     rdx, cs:qword_180046590
0x180002570  mov     [rax], rdx
0x180002573  mov     [rax+8], rbx
0x180002577  mov     cs:qword_180046590, rax
0x18000257e  add     rsp, 20h
0x180002582  pop     rbx
0x180002583  retn
```

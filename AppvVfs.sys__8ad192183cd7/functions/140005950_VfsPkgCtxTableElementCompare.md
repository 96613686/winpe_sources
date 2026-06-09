# VfsPkgCtxTableElementCompare

- ea: `0x140005950`
- end: `0x1400059a0`
- name: `VfsPkgCtxTableElementCompare`
- size: `80`
- prototype: `__int64 __fastcall(__int64, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005950`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000596c`
- `ntoskrnl!RtlCompareMemory` at `0x14000596c`

## pseudocode

```c
__int64 __fastcall VfsPkgCtxTableElementCompare(__int64 a1, const void *a2, const void *a3)
{
  SIZE_T v5; // rax

  v5 = RtlCompareMemory(a2, a3, 0x20u);
  if ( v5 == 32 )
    return 2;
  else
    return *((_BYTE *)a2 + v5) >= *((_BYTE *)a3 + v5);
}

```

## disassembly

```asm
0x140005950  mov     [rsp+arg_0], rbx
0x140005955  push    rdi
0x140005956  sub     rsp, 20h
0x14000595a  mov     rbx, r8
0x14000595d  mov     rdi, rdx
0x140005960  mov     rdx, rbx; Source2
0x140005963  mov     rcx, rdi; Source1
0x140005966  mov     r8d, 20h ; ' '; Length
0x14000596c  call    cs:__imp_RtlCompareMemory
0x140005973  nop     dword ptr [rax+rax+00h]
0x140005978  mov     r9, rax
0x14000597b  cmp     rax, 20h ; ' '
0x14000597f  jnz     short loc_140005987
0x140005981  lea     eax, [r9-1Eh]
0x140005985  jmp     short loc_140005994
0x140005987  mov     cl, [r9+rbx]
0x14000598b  xor     eax, eax
0x14000598d  cmp     [r9+rdi], cl
0x140005991  setnb   al
0x140005994  mov     rbx, [rsp+28h+arg_0]
0x140005999  add     rsp, 20h
0x14000599d  pop     rdi
0x14000599e  retn
```

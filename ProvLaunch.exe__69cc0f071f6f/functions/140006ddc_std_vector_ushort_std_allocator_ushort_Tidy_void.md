# std::vector<ushort,std::allocator<ushort>>::_Tidy(void)

- ea: `0x140006ddc`
- end: `0x140006e10`
- name: `?_Tidy@?$vector@GV?$allocator@G@std@@@std@@IEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000aa30`
- `0x14000aabd`
- `0x14000ab90`
- `0x14000ad21`

## callees

- `0x140006ddc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140006ded`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006ded`

## pseudocode

```c
void __fastcall std::vector<unsigned short>::_Tidy(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x140006ddc  push    rbx
0x140006dde  sub     rsp, 20h
0x140006de2  mov     rbx, rcx
0x140006de5  mov     rcx, [rcx]
0x140006de8  test    rcx, rcx
0x140006deb  jz      short loc_140006E0A
0x140006ded  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006df3  mov     qword ptr [rbx], 0
0x140006dfa  mov     qword ptr [rbx+8], 0
0x140006e02  mov     qword ptr [rbx+10h], 0
0x140006e0a  add     rsp, 20h
0x140006e0e  pop     rbx
0x140006e0f  retn
```

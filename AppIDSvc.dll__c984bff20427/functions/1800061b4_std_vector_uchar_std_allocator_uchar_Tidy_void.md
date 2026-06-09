# std::vector<uchar,std::allocator<uchar>>::_Tidy(void)

- ea: `0x1800061b4`
- end: `0x1800061e8`
- name: `?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c4e8`
- `0x18000c50c`
- `0x18000c596`
- `0x18000c5af`
- `0x18000c669`
- `0x18000c682`
- `0x18000c9bc`

## callees

- `0x1800061b4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800061c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800061c5`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::_Tidy(__int64 a1)
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
0x1800061b4  push    rbx
0x1800061b6  sub     rsp, 20h
0x1800061ba  mov     rbx, rcx
0x1800061bd  mov     rcx, [rcx]
0x1800061c0  test    rcx, rcx
0x1800061c3  jz      short loc_1800061E2
0x1800061c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800061cb  mov     qword ptr [rbx], 0
0x1800061d2  mov     qword ptr [rbx+8], 0
0x1800061da  mov     qword ptr [rbx+10h], 0
0x1800061e2  add     rsp, 20h
0x1800061e6  pop     rbx
0x1800061e7  retn
```

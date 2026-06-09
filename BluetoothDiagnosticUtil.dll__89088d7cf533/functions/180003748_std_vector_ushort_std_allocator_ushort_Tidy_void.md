# std::vector<ushort,std::allocator<ushort>>::_Tidy(void)

- ea: `0x180003748`
- end: `0x180003783`
- name: `?_Tidy@?$vector@GV?$allocator@G@std@@@std@@IEAAXXZ`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a67d`
- `0x18000a6b5`

## callees

- `0x180003748`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003759`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003759`

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
0x180003748  push    rbx
0x18000374a  sub     rsp, 20h
0x18000374e  mov     rbx, rcx
0x180003751  mov     rcx, [rcx]
0x180003754  test    rcx, rcx
0x180003757  jz      short loc_18000377C
0x180003759  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003760  nop     dword ptr [rax+rax+00h]
0x180003765  mov     qword ptr [rbx], 0
0x18000376c  mov     qword ptr [rbx+8], 0
0x180003774  mov     qword ptr [rbx+10h], 0
0x18000377c  add     rsp, 20h
0x180003780  pop     rbx
0x180003781  retn
```

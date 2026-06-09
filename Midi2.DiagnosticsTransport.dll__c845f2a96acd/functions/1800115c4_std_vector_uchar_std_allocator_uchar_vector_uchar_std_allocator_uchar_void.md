# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x1800115c4`
- end: `0x180011628`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011630`
- `0x1800117e8`
- `0x180012457`

## callees

- `0x1800033f4`
- `0x1800115c4`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::~vector<unsigned char>(char **a1)
{
  char *v1; // rax
  char *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(a1[2] - v1) < 0x1000 )
    {
      v3 = *a1;
    }
    else
    {
      v3 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v3 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x1800115c4  push    rbx
0x1800115c6  sub     rsp, 20h
0x1800115ca  mov     rax, [rcx]
0x1800115cd  mov     rbx, rcx
0x1800115d0  test    rax, rax
0x1800115d3  jz      short loc_180011622
0x1800115d5  mov     rdx, [rcx+10h]
0x1800115d9  sub     rdx, rax
0x1800115dc  cmp     rdx, 1000h
0x1800115e3  jb      short loc_180011603
0x1800115e5  mov     rcx, [rax-8]
0x1800115e9  sub     rax, rcx
0x1800115ec  sub     rax, 8
0x1800115f0  cmp     rax, 1Fh
0x1800115f4  ja      short loc_1800115FC
0x1800115f6  add     rdx, 27h ; '''
0x1800115fa  jmp     short loc_180011606
0x1800115fc  mov     ecx, 5
0x180011601  int     29h; Win8: RtlFailFast(ecx)
0x180011603  mov     rcx, rax; Block
0x180011606  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001160b  mov     qword ptr [rbx], 0
0x180011612  mov     qword ptr [rbx+8], 0
0x18001161a  mov     qword ptr [rbx+10h], 0
0x180011622  add     rsp, 20h
0x180011626  pop     rbx
0x180011627  retn
```

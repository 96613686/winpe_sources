# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x140008530`
- end: `0x140008594`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400083dc`
- `0x140008784`
- `0x14000dbfc`
- `0x14000ecf4`
- `0x14000f54c`
- `0x1400110b8`
- `0x140012394`

## callees

- `0x140001934`
- `0x140008530`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::~vector<unsigned char>(char **a1)
{
  char *v1; // rax
  unsigned __int64 v3; // rdx
  char *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[2] - v1;
    if ( v3 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v4 - 8) > 0x1F )
        __fastfail(5u);
      v3 += 39LL;
    }
    operator delete(v4, v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x140008530  push    rbx
0x140008532  sub     rsp, 20h
0x140008536  mov     rax, [rcx]
0x140008539  mov     rbx, rcx
0x14000853c  test    rax, rax
0x14000853f  jz      short loc_14000858E
0x140008541  mov     rdx, [rcx+10h]
0x140008545  sub     rdx, rax; unsigned __int64
0x140008548  cmp     rdx, 1000h
0x14000854f  jb      short loc_14000856F
0x140008551  mov     rcx, [rax-8]
0x140008555  sub     rax, rcx
0x140008558  sub     rax, 8
0x14000855c  cmp     rax, 1Fh
0x140008560  ja      short loc_140008568
0x140008562  add     rdx, 27h ; '''
0x140008566  jmp     short loc_140008572
0x140008568  mov     ecx, 5
0x14000856d  int     29h; Win8: RtlFailFast(ecx)
0x14000856f  mov     rcx, rax; void *
0x140008572  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008577  mov     qword ptr [rbx], 0
0x14000857e  mov     qword ptr [rbx+8], 0
0x140008586  mov     qword ptr [rbx+10h], 0
0x14000858e  add     rsp, 20h
0x140008592  pop     rbx
0x140008593  retn
```

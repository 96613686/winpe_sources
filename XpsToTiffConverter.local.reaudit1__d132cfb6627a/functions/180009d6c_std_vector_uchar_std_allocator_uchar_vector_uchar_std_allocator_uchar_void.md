# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x180009d6c`
- end: `0x180009dd0`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009f94`
- `0x18000ac30`
- `0x18000c1d0`
- `0x18000d5b2`
- `0x18000d651`
- `0x18000d738`

## callees

- `0x180001a70`
- `0x180009d6c`

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
0x180009d6c  push    rbx
0x180009d6e  sub     rsp, 20h
0x180009d72  mov     rax, [rcx]
0x180009d75  mov     rbx, rcx
0x180009d78  test    rax, rax
0x180009d7b  jz      short loc_180009DCA
0x180009d7d  mov     rdx, [rcx+10h]
0x180009d81  sub     rdx, rax; unsigned __int64
0x180009d84  cmp     rdx, 1000h
0x180009d8b  jb      short loc_180009DAB
0x180009d8d  mov     rcx, [rax-8]
0x180009d91  sub     rax, rcx
0x180009d94  sub     rax, 8
0x180009d98  cmp     rax, 1Fh
0x180009d9c  ja      short loc_180009DA4
0x180009d9e  add     rdx, 27h ; '''
0x180009da2  jmp     short loc_180009DAE
0x180009da4  mov     ecx, 5
0x180009da9  int     29h; Win8: RtlFailFast(ecx)
0x180009dab  mov     rcx, rax; void *
0x180009dae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009db3  mov     qword ptr [rbx], 0
0x180009dba  mov     qword ptr [rbx+8], 0
0x180009dc2  mov     qword ptr [rbx+10h], 0
0x180009dca  add     rsp, 20h
0x180009dce  pop     rbx
0x180009dcf  retn
```

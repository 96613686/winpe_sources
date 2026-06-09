# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x18000a130`
- end: `0x18000a194`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009e3c`
- `0x18000a19c`
- `0x18000c860`
- `0x18000e1a0`
- `0x18000febe`
- `0x18000feea`
- `0x18000ff12`
- `0x180010679`

## callees

- `0x180001b30`
- `0x18000a130`

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
0x18000a130  push    rbx
0x18000a132  sub     rsp, 20h
0x18000a136  mov     rax, [rcx]
0x18000a139  mov     rbx, rcx
0x18000a13c  test    rax, rax
0x18000a13f  jz      short loc_18000A18E
0x18000a141  mov     rdx, [rcx+10h]
0x18000a145  sub     rdx, rax; unsigned __int64
0x18000a148  cmp     rdx, 1000h
0x18000a14f  jb      short loc_18000A16F
0x18000a151  mov     rcx, [rax-8]
0x18000a155  sub     rax, rcx
0x18000a158  sub     rax, 8
0x18000a15c  cmp     rax, 1Fh
0x18000a160  ja      short loc_18000A168
0x18000a162  add     rdx, 27h ; '''
0x18000a166  jmp     short loc_18000A172
0x18000a168  mov     ecx, 5
0x18000a16d  int     29h; Win8: RtlFailFast(ecx)
0x18000a16f  mov     rcx, rax; void *
0x18000a172  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a177  mov     qword ptr [rbx], 0
0x18000a17e  mov     qword ptr [rbx+8], 0
0x18000a186  mov     qword ptr [rbx+10h], 0
0x18000a18e  add     rsp, 20h
0x18000a192  pop     rbx
0x18000a193  retn
```

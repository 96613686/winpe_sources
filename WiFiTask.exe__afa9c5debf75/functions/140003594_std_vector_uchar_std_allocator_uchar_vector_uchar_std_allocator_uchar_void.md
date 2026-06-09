# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x140003594`
- end: `0x1400035f8`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006b40`
- `0x140006eb0`
- `0x14000d3c4`
- `0x14000dd04`
- `0x14000ddf0`
- `0x140010ecf`
- `0x140010f4f`

## callees

- `0x1400016c4`
- `0x140003594`

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
0x140003594  push    rbx
0x140003596  sub     rsp, 20h
0x14000359a  mov     rax, [rcx]
0x14000359d  mov     rbx, rcx
0x1400035a0  test    rax, rax
0x1400035a3  jz      short loc_1400035F2
0x1400035a5  mov     rdx, [rcx+10h]
0x1400035a9  sub     rdx, rax
0x1400035ac  cmp     rdx, 1000h
0x1400035b3  jb      short loc_1400035D3
0x1400035b5  mov     rcx, [rax-8]
0x1400035b9  sub     rax, rcx
0x1400035bc  sub     rax, 8
0x1400035c0  cmp     rax, 1Fh
0x1400035c4  ja      short loc_1400035CC
0x1400035c6  add     rdx, 27h ; '''
0x1400035ca  jmp     short loc_1400035D6
0x1400035cc  mov     ecx, 5
0x1400035d1  int     29h; Win8: RtlFailFast(ecx)
0x1400035d3  mov     rcx, rax; Block
0x1400035d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400035db  mov     qword ptr [rbx], 0
0x1400035e2  mov     qword ptr [rbx+8], 0
0x1400035ea  mov     qword ptr [rbx+10h], 0
0x1400035f2  add     rsp, 20h
0x1400035f6  pop     rbx
0x1400035f7  retn
```

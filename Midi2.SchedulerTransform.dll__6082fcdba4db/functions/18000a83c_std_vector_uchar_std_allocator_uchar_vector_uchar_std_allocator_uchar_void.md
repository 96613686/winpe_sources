# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x18000a83c`
- end: `0x18000a8a0`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a518`
- `0x18000a8a8`
- `0x18000af80`
- `0x18000c1a0`
- `0x18000ceeb`

## callees

- `0x180002024`
- `0x18000a83c`

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
0x18000a83c  push    rbx
0x18000a83e  sub     rsp, 20h
0x18000a842  mov     rax, [rcx]
0x18000a845  mov     rbx, rcx
0x18000a848  test    rax, rax
0x18000a84b  jz      short loc_18000A89A
0x18000a84d  mov     rdx, [rcx+10h]
0x18000a851  sub     rdx, rax
0x18000a854  cmp     rdx, 1000h
0x18000a85b  jb      short loc_18000A87B
0x18000a85d  mov     rcx, [rax-8]
0x18000a861  sub     rax, rcx
0x18000a864  sub     rax, 8
0x18000a868  cmp     rax, 1Fh
0x18000a86c  ja      short loc_18000A874
0x18000a86e  add     rdx, 27h ; '''
0x18000a872  jmp     short loc_18000A87E
0x18000a874  mov     ecx, 5
0x18000a879  int     29h; Win8: RtlFailFast(ecx)
0x18000a87b  mov     rcx, rax; Block
0x18000a87e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a883  mov     qword ptr [rbx], 0
0x18000a88a  mov     qword ptr [rbx+8], 0
0x18000a892  mov     qword ptr [rbx+10h], 0
0x18000a89a  add     rsp, 20h
0x18000a89e  pop     rbx
0x18000a89f  retn
```

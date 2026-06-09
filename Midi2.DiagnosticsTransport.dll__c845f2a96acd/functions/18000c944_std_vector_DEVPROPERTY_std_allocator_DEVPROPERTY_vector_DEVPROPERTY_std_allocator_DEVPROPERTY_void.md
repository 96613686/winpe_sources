# std::vector<_DEVPROPERTY,std::allocator<_DEVPROPERTY>>::~vector<_DEVPROPERTY,std::allocator<_DEVPROPERTY>>(void)

- ea: `0x18000c944`
- end: `0x18000c9c8`
- name: `??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ccf8`
- `0x18000d31c`
- `0x1800123b5`

## callees

- `0x1800033f4`
- `0x18000c944`

## pseudocode

```c
void __fastcall std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(char **a1)
{
  char *v1; // rdx
  char *v3; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(16 * ((a1[2] - v1) >> 4)) < 0x1000 )
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
0x18000c944  push    rbx
0x18000c946  sub     rsp, 20h
0x18000c94a  mov     rdx, [rcx]
0x18000c94d  mov     rbx, rcx
0x18000c950  test    rdx, rdx
0x18000c953  jz      short loc_18000C9C2
0x18000c955  mov     rax, [rcx+10h]
0x18000c959  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18000c963  sub     rax, rdx
0x18000c966  sar     rax, 4
0x18000c96a  imul    rax, rcx
0x18000c96e  lea     rcx, [rax+rax*2]
0x18000c972  shl     rcx, 4
0x18000c976  cmp     rcx, 1000h
0x18000c97d  jb      short loc_18000C99D
0x18000c97f  mov     rax, [rdx-8]
0x18000c983  sub     rdx, rax
0x18000c986  sub     rdx, 8
0x18000c98a  cmp     rdx, 1Fh
0x18000c98e  ja      short loc_18000C996
0x18000c990  add     rcx, 27h ; '''
0x18000c994  jmp     short loc_18000C9A0
0x18000c996  mov     ecx, 5
0x18000c99b  int     29h; Win8: RtlFailFast(ecx)
0x18000c99d  mov     rax, rdx
0x18000c9a0  mov     rdx, rcx
0x18000c9a3  mov     rcx, rax; Block
0x18000c9a6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c9ab  mov     qword ptr [rbx], 0
0x18000c9b2  mov     qword ptr [rbx+8], 0
0x18000c9ba  mov     qword ptr [rbx+10h], 0
0x18000c9c2  add     rsp, 20h
0x18000c9c6  pop     rbx
0x18000c9c7  retn
```

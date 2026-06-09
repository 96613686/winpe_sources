# std::basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(void)

- ea: `0x14000b08c`
- end: `0x14000b163`
- name: `?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ`
- size: `215`
- prototype: `_DWORD *__fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140008180`
- `0x1400081fc`
- `0x140009710`
- `0x14000cd00`

## callees

- `0x140001934`
- `0x14000b08c`

## pseudocode

```c
_DWORD *__fastcall std::basic_stringbuf<unsigned short>::_Tidy(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  char **v4; // rax
  char *v5; // rcx
  char *v6; // rax
  _DWORD *result; // rax

  if ( (*(_BYTE *)(a1 + 112) & 1) != 0 )
  {
    v2 = **(_QWORD **)(a1 + 64);
    if ( v2 )
      v3 = v2 + 2LL * **(int **)(a1 + 88);
    else
      v3 = **(_QWORD **)(a1 + 56) + 2LL * **(int **)(a1 + 80);
    v4 = *(char ***)(a1 + 24);
    v5 = *v4;
    if ( (unsigned __int64)(2 * ((v3 - (__int64)*v4) >> 1)) < 0x1000 )
    {
      v6 = *v4;
    }
    else
    {
      v6 = (char *)*((_QWORD *)v5 - 1);
      if ( (unsigned __int64)(v5 - v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
  }
  **(_QWORD **)(a1 + 24) = 0;
  **(_QWORD **)(a1 + 56) = 0;
  **(_DWORD **)(a1 + 80) = 0;
  **(_QWORD **)(a1 + 32) = 0;
  **(_QWORD **)(a1 + 64) = 0;
  result = *(_DWORD **)(a1 + 88);
  *result = 0;
  *(_DWORD *)(a1 + 112) &= ~1u;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x14000b08c  mov     [rsp+arg_0], rbx
0x14000b091  push    rdi
0x14000b092  sub     rsp, 20h
0x14000b096  test    byte ptr [rcx+70h], 1
0x14000b09a  mov     rbx, rcx
0x14000b09d  jz      short loc_14000B10C
0x14000b09f  mov     rax, [rcx+40h]
0x14000b0a3  mov     rdx, [rax]
0x14000b0a6  test    rdx, rdx
0x14000b0a9  jz      short loc_14000B0B8
0x14000b0ab  mov     rax, [rcx+58h]
0x14000b0af  movsxd  rcx, dword ptr [rax]
0x14000b0b2  lea     rdx, [rdx+rcx*2]
0x14000b0b6  jmp     short loc_14000B0CA
0x14000b0b8  mov     rax, [rcx+50h]
0x14000b0bc  movsxd  rdx, dword ptr [rax]
0x14000b0bf  mov     rax, [rcx+38h]
0x14000b0c3  mov     rcx, [rax]
0x14000b0c6  lea     rdx, [rcx+rdx*2]
0x14000b0ca  mov     rax, [rbx+18h]
0x14000b0ce  mov     rcx, [rax]
0x14000b0d1  sub     rdx, rcx
0x14000b0d4  sar     rdx, 1
0x14000b0d7  add     rdx, rdx; unsigned __int64
0x14000b0da  cmp     rdx, 1000h
0x14000b0e1  jb      short loc_14000B101
0x14000b0e3  mov     rax, [rcx-8]
0x14000b0e7  sub     rcx, rax
0x14000b0ea  sub     rcx, 8
0x14000b0ee  cmp     rcx, 1Fh
0x14000b0f2  ja      short loc_14000B0FA
0x14000b0f4  add     rdx, 27h ; '''
0x14000b0f8  jmp     short loc_14000B104
0x14000b0fa  mov     ecx, 5
0x14000b0ff  int     29h; Win8: RtlFailFast(ecx)
0x14000b101  mov     rax, rcx
0x14000b104  mov     rcx, rax; void *
0x14000b107  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b10c  mov     rax, [rbx+18h]
0x14000b110  mov     qword ptr [rax], 0
0x14000b117  mov     rax, [rbx+38h]
0x14000b11b  mov     qword ptr [rax], 0
0x14000b122  mov     rax, [rbx+50h]
0x14000b126  mov     dword ptr [rax], 0
0x14000b12c  mov     rax, [rbx+20h]
0x14000b130  mov     qword ptr [rax], 0
0x14000b137  mov     rax, [rbx+40h]
0x14000b13b  mov     qword ptr [rax], 0
0x14000b142  mov     rax, [rbx+58h]
0x14000b146  mov     dword ptr [rax], 0
0x14000b14c  and     dword ptr [rbx+70h], 0FFFFFFFEh
0x14000b150  mov     qword ptr [rbx+68h], 0
0x14000b158  mov     rbx, [rsp+28h+arg_0]
0x14000b15d  add     rsp, 20h
0x14000b161  pop     rdi
0x14000b162  retn
```

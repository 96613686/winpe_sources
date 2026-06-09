# DpspFreeDirectoryTable

- ea: `0x180008328`
- end: `0x18000839f`
- name: `DpspFreeDirectoryTable`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015b84`

## callees

- `0x180008328`
- `0x180008ea0`

## pseudocode

```c
__int64 __fastcall DpspFreeDirectoryTable(__int64 a1)
{
  unsigned int i; // ebp
  _QWORD **v3; // rdi
  _QWORD *v4; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rcx
  __int64 result; // rax

  for ( i = 0; i < *(_DWORD *)(a1 + 8); ++i )
  {
    v3 = (_QWORD **)(*(_QWORD *)a1 + 16LL * i);
    v4 = *v3;
    while ( v3 != v4 )
    {
      v5 = (_QWORD *)*v4;
      if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v6 = (_QWORD *)v4[1], (_QWORD *)*v6 != v4) )
        __fastfail(3u);
      v7 = v4;
      *v6 = v5;
      v4 = v5;
      v5[1] = v6;
      WdipFree(v7);
    }
  }
  result = WdipFree(*(_QWORD *)a1);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180008328  push    rbx
0x18000832a  push    rbp
0x18000832b  push    rsi
0x18000832c  push    rdi
0x18000832d  sub     rsp, 28h
0x180008331  xor     ebp, ebp
0x180008333  mov     rbx, rcx
0x180008336  cmp     [rcx+8], ebp
0x180008339  jbe     short loc_180008379
0x18000833b  mov     edi, ebp
0x18000833d  shl     rdi, 4
0x180008341  add     rdi, [rbx]
0x180008344  mov     rsi, [rdi]
0x180008347  jmp     short loc_18000836D
0x180008349  mov     rax, [rsi]
0x18000834c  cmp     [rax+8], rsi
0x180008350  jnz     short loc_180008398
0x180008352  mov     rdx, [rsi+8]
0x180008356  cmp     [rdx], rsi
0x180008359  jnz     short loc_180008398
0x18000835b  mov     rcx, rsi
0x18000835e  mov     [rdx], rax
0x180008361  mov     rsi, rax
0x180008364  mov     [rax+8], rdx
0x180008368  call    WdipFree
0x18000836d  cmp     rdi, rsi
0x180008370  jnz     short loc_180008349
0x180008372  inc     ebp
0x180008374  cmp     ebp, [rbx+8]
0x180008377  jb      short loc_18000833B
0x180008379  mov     rcx, [rbx]
0x18000837c  call    WdipFree
0x180008381  mov     qword ptr [rbx], 0
0x180008388  mov     dword ptr [rbx+8], 0
0x18000838f  add     rsp, 28h
0x180008393  pop     rdi
0x180008394  pop     rsi
0x180008395  pop     rbp
0x180008396  pop     rbx
0x180008397  retn
0x180008398  mov     ecx, 3
0x18000839d  int     29h; Win8: RtlFailFast(ecx)
```

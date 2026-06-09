# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800038c4`
- end: `0x18000395a`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003840`
- `0x180003960`

## callees

- `0x180002238`
- `0x1800038c4`
- `0x180007a90`
- `0x18000bb08`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int v2; // esi
  __int64 v4; // rdi
  void *v5; // rcx

  v1 = *((_DWORD *)this + 4);
  v2 = 0;
  if ( v1 > 0 )
  {
    v4 = 0;
    do
    {
      if ( v4 < 0 || v2 >= v1 || (operator delete(*(void **)(v4 + *(_QWORD *)this)), v2 >= *((_DWORD *)this + 4)) )
        ATL::AtlThrowImpl(-2147483637);
      operator delete(*(void **)(v4 + *((_QWORD *)this + 1)));
      v1 = *((_DWORD *)this + 4);
      ++v2;
      v4 += 8;
    }
    while ( v2 < v1 );
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 1) = 0;
  }
  *((_DWORD *)this + 4) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800038c4  mov     [rsp+arg_0], rbx
0x1800038c9  mov     [rsp+arg_8], rsi
0x1800038ce  push    rdi
0x1800038cf  sub     rsp, 20h
0x1800038d3  mov     eax, [rcx+10h]
0x1800038d6  xor     esi, esi
0x1800038d8  mov     rbx, rcx
0x1800038db  test    eax, eax
0x1800038dd  jle     short loc_180003915
0x1800038df  xor     edi, edi
0x1800038e1  test    rdi, rdi
0x1800038e4  js      short loc_18000394F
0x1800038e6  cmp     esi, eax
0x1800038e8  jge     short loc_18000394F
0x1800038ea  mov     rcx, [rbx]
0x1800038ed  mov     rcx, [rdi+rcx]; Block
0x1800038f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800038f6  cmp     esi, [rbx+10h]
0x1800038f9  jge     short loc_18000394F
0x1800038fb  mov     rcx, [rbx+8]
0x1800038ff  mov     rcx, [rdi+rcx]; Block
0x180003903  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003908  mov     eax, [rbx+10h]
0x18000390b  inc     esi
0x18000390d  add     rdi, 8
0x180003911  cmp     esi, eax
0x180003913  jl      short loc_1800038E1
0x180003915  mov     rcx, [rbx]; Block
0x180003918  test    rcx, rcx
0x18000391b  jz      short loc_180003926
0x18000391d  call    free
0x180003922  and     qword ptr [rbx], 0
0x180003926  mov     rcx, [rbx+8]; Block
0x18000392a  test    rcx, rcx
0x18000392d  jz      short loc_180003939
0x18000392f  call    free
0x180003934  and     qword ptr [rbx+8], 0
0x180003939  and     dword ptr [rbx+10h], 0
0x18000393d  mov     rbx, [rsp+28h+arg_0]
0x180003942  xor     eax, eax
0x180003944  mov     rsi, [rsp+28h+arg_8]
0x180003949  add     rsp, 20h
0x18000394d  pop     rdi
0x18000394e  retn
0x18000394f  mov     ecx, 8000000Bh; int
0x180003954  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

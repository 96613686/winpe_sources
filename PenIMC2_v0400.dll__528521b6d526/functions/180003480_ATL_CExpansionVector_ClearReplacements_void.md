# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003480`
- end: `0x18000351d`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `157`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003370`
- `0x18000343c`
- `0x180003520`
- `0x18000352c`

## callees

- `0x180003480`
- `0x180003828`
- `0x18000ce0c`

## import_xrefs

- `ucrtbase_clr0400!free` at `0x1800034d9`
- `ucrtbase_clr0400!free` at `0x1800034ec`
- `ucrtbase_clr0400!free` at `0x1800034d9`
- `ucrtbase_clr0400!free` at `0x1800034ec`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int v2; // edi
  __int64 v4; // rsi
  void *v5; // rcx

  v1 = *((_DWORD *)this + 4);
  v2 = 0;
  if ( v1 > 0 )
  {
    v4 = 0;
    do
    {
      if ( v4 < 0 || v2 >= v1 || (operator delete(*(void **)(v4 + *(_QWORD *)this)), v2 >= *((_DWORD *)this + 4)) )
      {
        ATL::_AtlRaiseException(0xC000008C, 1u);
        JUMPOUT(0x18000351CLL);
      }
      operator delete(*(void **)(*((_QWORD *)this + 1) + v4));
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
0x180003480  mov     [rsp+arg_0], rbx
0x180003485  mov     [rsp+arg_8], rsi
0x18000348a  push    rdi
0x18000348b  sub     rsp, 20h
0x18000348f  mov     eax, [rcx+10h]
0x180003492  xor     edi, edi
0x180003494  mov     rbx, rcx
0x180003497  test    eax, eax
0x180003499  jle     short loc_1800034D1
0x18000349b  xor     esi, esi
0x18000349d  test    rsi, rsi
0x1800034a0  js      short loc_18000350D
0x1800034a2  cmp     edi, eax
0x1800034a4  jge     short loc_18000350D
0x1800034a6  mov     rcx, [rbx]
0x1800034a9  mov     rcx, [rsi+rcx]; Block
0x1800034ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800034b2  cmp     edi, [rbx+10h]
0x1800034b5  jge     short loc_18000350D
0x1800034b7  mov     rcx, [rbx+8]
0x1800034bb  mov     rcx, [rcx+rsi]; Block
0x1800034bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800034c4  mov     eax, [rbx+10h]
0x1800034c7  inc     edi
0x1800034c9  add     rsi, 8
0x1800034cd  cmp     edi, eax
0x1800034cf  jl      short loc_18000349D
0x1800034d1  mov     rcx, [rbx]; Block
0x1800034d4  test    rcx, rcx
0x1800034d7  jz      short loc_1800034E3
0x1800034d9  call    cs:__imp_free
0x1800034df  and     qword ptr [rbx], 0
0x1800034e3  mov     rcx, [rbx+8]; Block
0x1800034e7  test    rcx, rcx
0x1800034ea  jz      short loc_1800034F7
0x1800034ec  call    cs:__imp_free
0x1800034f2  and     qword ptr [rbx+8], 0
0x1800034f7  and     dword ptr [rbx+10h], 0
0x1800034fb  mov     rbx, [rsp+28h+arg_0]
0x180003500  xor     eax, eax
0x180003502  mov     rsi, [rsp+28h+arg_8]
0x180003507  add     rsp, 20h
0x18000350b  pop     rdi
0x18000350c  retn
0x18000350d  mov     edx, 1; unsigned int
0x180003512  mov     ecx, 0C000008Ch; unsigned int
0x180003517  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

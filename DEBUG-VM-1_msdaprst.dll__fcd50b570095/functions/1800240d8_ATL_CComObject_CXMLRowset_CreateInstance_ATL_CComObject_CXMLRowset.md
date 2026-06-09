# ATL::CComObject<CXMLRowset>::CreateInstance(ATL::CComObject<CXMLRowset> * *)

- ea: `0x1800240d8`
- end: `0x18002417d`
- name: `?CreateInstance@?$CComObject@VCXMLRowset@@@ATL@@SAJPEAPEAV12@@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023bbc`

## callees

- `0x180001d94`
- `0x180020344`
- `0x1800240d8`
- `0x180027ebc`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CXMLRowset>::CreateInstance(CRowset **a1, unsigned int a2)
{
  unsigned int v4; // esi
  CXMLRowset *v5; // rax
  CRowset *v6; // rbx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = -2147024882;
  v5 = (CXMLRowset *)MMMAlloc(0x288u, a2);
  v6 = v5;
  if ( v5 )
  {
    CXMLRowset::CXMLRowset(v5);
    *(_QWORD *)v6 = &ATL::CComObject<CXMLRowset>::`vftable';
    _InterlockedIncrement(&dword_1800454E8);
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    v4 = CRowset::FinalConstruct(v6);
    if ( v4 )
    {
      (*(void (__fastcall **)(CRowset *, __int64))(*(_QWORD *)v6 + 128LL))(v6, 1);
      v6 = 0;
    }
  }
  *a1 = v6;
  return v4;
}

```

## disassembly

```asm
0x1800240d8  mov     [rsp+arg_8], rbx
0x1800240dd  mov     [rsp+arg_10], rsi
0x1800240e2  push    rdi
0x1800240e3  sub     rsp, 30h
0x1800240e7  mov     rdi, rcx
0x1800240ea  test    rcx, rcx
0x1800240ed  jnz     short loc_1800240F6
0x1800240ef  mov     eax, 80004003h
0x1800240f4  jmp     short loc_18002416D
0x1800240f6  mov     qword ptr [rcx], 0
0x1800240fd  mov     esi, 8007000Eh
0x180024102  mov     ecx, 288h; unsigned int
0x180024107  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002410c  mov     rbx, rax
0x18002410f  mov     [rsp+38h+arg_0], rax
0x180024114  test    rax, rax
0x180024117  jz      short loc_180024134
0x180024119  mov     rcx, rax; this
0x18002411c  call    ??0CXMLRowset@@QEAA@XZ; CXMLRowset::CXMLRowset(void)
0x180024121  lea     rax, ??_7?$CComObject@VCXMLRowset@@@ATL@@6B@; const ATL::CComObject<CXMLRowset>::`vftable'
0x180024128  mov     [rbx], rax
0x18002412b  lock inc cs:dword_1800454E8
0x180024132  jmp     short loc_180024136
0x180024134  xor     ebx, ebx
0x180024136  test    rbx, rbx
0x180024139  jz      short loc_180024162
0x18002413b  mov     rcx, rbx; this
0x18002413e  call    ?FinalConstruct@CRowset@@QEAAJXZ; CRowset::FinalConstruct(void)
0x180024143  mov     esi, eax
0x180024145  test    eax, eax
0x180024147  jz      short loc_180024162
0x180024149  mov     r8, [rbx]
0x18002414c  mov     edx, 1
0x180024151  mov     rcx, rbx
0x180024154  mov     rax, [r8+80h]
0x18002415b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024160  xor     ebx, ebx
0x180024162  mov     [rdi], rbx
0x180024165  mov     eax, esi
0x180024167  jmp     short loc_18002416D
0x180024169  mov     eax, [rsp+38h+var_18]
0x18002416d  mov     rbx, [rsp+38h+arg_8]
0x180024172  mov     rsi, [rsp+38h+arg_10]
0x180024177  add     rsp, 30h
0x18002417b  pop     rdi
0x18002417c  retn
```

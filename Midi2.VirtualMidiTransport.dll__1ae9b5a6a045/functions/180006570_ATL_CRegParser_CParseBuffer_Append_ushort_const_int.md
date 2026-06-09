# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180006570`
- end: `0x180006663`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000813c`

## callees

- `0x180006570`
- `0x1800066a8`
- `0x18000ab48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800065c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800065c7`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  errno_t v11; // eax

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 <= *(_DWORD *)this || v6 <= a3 )
    return 0;
  v7 = *((_DWORD *)this + 1);
  if ( v6 >= v7 )
  {
    while ( v7 <= 0x3FFFFFFF )
    {
      v7 *= 2;
      if ( v6 < v7 )
      {
        v8 = 2LL * (unsigned int)v7;
        if ( v8 <= 0xFFFFFFFF )
        {
          v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
          if ( v9 )
          {
            *((_QWORD *)this + 1) = v9;
            *((_DWORD *)this + 1) = v7;
            goto LABEL_9;
          }
        }
        return 0;
      }
    }
    return 0;
  }
LABEL_9:
  if ( *(int *)this < 0 )
    return 0;
  if ( *(_DWORD *)this >= v7 )
    return 0;
  v10 = v7 - *(_DWORD *)this;
  if ( v10 > v7 )
    return 0;
  v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
  if ( v11 )
  {
    if ( v11 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v11 == 22 || v11 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v11 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *(_DWORD *)this += a3;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
  return 1;
}

```

## disassembly

```asm
0x180006570  push    rbx
0x180006572  push    rbp
0x180006573  push    rsi
0x180006574  push    rdi
0x180006575  sub     rsp, 28h
0x180006579  mov     rdi, rcx
0x18000657c  mov     esi, r8d
0x18000657f  lea     ecx, [r8+1]
0x180006583  mov     rbp, rdx
0x180006586  add     ecx, [rdi]
0x180006588  cmp     ecx, [rdi]
0x18000658a  jle     loc_180006637
0x180006590  cmp     ecx, r8d
0x180006593  jle     loc_180006637
0x180006599  mov     ebx, [rdi+4]
0x18000659c  cmp     ecx, ebx
0x18000659e  jl      short loc_1800065D9
0x1800065a0  cmp     ebx, 3FFFFFFFh
0x1800065a6  jg      loc_180006637
0x1800065ac  add     ebx, ebx
0x1800065ae  cmp     ecx, ebx
0x1800065b0  jge     short loc_1800065A0
0x1800065b2  mov     eax, ebx
0x1800065b4  mov     ecx, 0FFFFFFFFh
0x1800065b9  add     rax, rax
0x1800065bc  cmp     rax, rcx
0x1800065bf  ja      short loc_180006637
0x1800065c1  mov     rcx, [rdi+8]; pv
0x1800065c5  mov     edx, eax; cb
0x1800065c7  call    cs:__imp_CoTaskMemRealloc
0x1800065cd  test    rax, rax
0x1800065d0  jz      short loc_180006637
0x1800065d2  mov     [rdi+8], rax
0x1800065d6  mov     [rdi+4], ebx
0x1800065d9  cmp     dword ptr [rdi], 0
0x1800065dc  jl      short loc_180006637
0x1800065de  cmp     [rdi], ebx
0x1800065e0  jge     short loc_180006637
0x1800065e2  mov     ecx, ebx
0x1800065e4  sub     ecx, [rdi]
0x1800065e6  cmp     ecx, ebx
0x1800065e8  jg      short loc_180006637
0x1800065ea  movsxd  rdx, ecx
0x1800065ed  lea     eax, [rsi+rsi]
0x1800065f0  movsxd  rcx, dword ptr [rdi]
0x1800065f3  add     rdx, rdx; DestinationSize
0x1800065f6  movsxd  r9, eax; SourceSize
0x1800065f9  mov     r8, rbp; Source
0x1800065fc  mov     rax, [rdi+8]
0x180006600  lea     rcx, [rax+rcx*2]; Destination
0x180006604  call    memcpy_s
0x180006609  test    eax, eax
0x18000660b  jz      short loc_180006621
0x18000660d  cmp     eax, 0Ch
0x180006610  jz      short loc_180006658
0x180006612  cmp     eax, 16h
0x180006615  jz      short loc_18000664D
0x180006617  cmp     eax, 22h ; '"'
0x18000661a  jz      short loc_18000664D
0x18000661c  cmp     eax, 50h ; 'P'
0x18000661f  jnz     short loc_180006642
0x180006621  add     [rdi], esi
0x180006623  movsxd  rdx, dword ptr [rdi]
0x180006626  xor     eax, eax
0x180006628  mov     rcx, [rdi+8]
0x18000662c  mov     [rcx+rdx*2], ax
0x180006630  mov     eax, 1
0x180006635  jmp     short loc_180006639
0x180006637  xor     eax, eax
0x180006639  add     rsp, 28h
0x18000663d  pop     rdi
0x18000663e  pop     rsi
0x18000663f  pop     rbp
0x180006640  pop     rbx
0x180006641  retn
0x180006642  mov     ecx, 80004005h; int
0x180006647  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000664d  mov     ecx, 80070057h; int
0x180006652  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006658  mov     ecx, 8007000Eh; int
0x18000665d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

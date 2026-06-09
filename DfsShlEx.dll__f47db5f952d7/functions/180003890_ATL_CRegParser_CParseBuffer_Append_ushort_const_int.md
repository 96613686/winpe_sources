# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003890`
- end: `0x180003984`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004e2c`

## callees

- `0x180003890`
- `0x180004328`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003924`
- `msvcrt!memcpy_s` at `0x180003924`
- `ole32!CoTaskMemRealloc` at `0x1800038e7`
- `ole32!CoTaskMemRealloc` at `0x1800038e7`

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
0x180003890  push    rbx
0x180003892  push    rbp
0x180003893  push    rsi
0x180003894  push    rdi
0x180003895  sub     rsp, 28h
0x180003899  mov     rdi, rcx
0x18000389c  mov     esi, r8d
0x18000389f  lea     ecx, [r8+1]
0x1800038a3  mov     rbp, rdx
0x1800038a6  add     ecx, [rdi]
0x1800038a8  cmp     ecx, [rdi]
0x1800038aa  jle     loc_180003958
0x1800038b0  cmp     ecx, r8d
0x1800038b3  jle     loc_180003958
0x1800038b9  mov     ebx, [rdi+4]
0x1800038bc  cmp     ecx, ebx
0x1800038be  jl      short loc_1800038F9
0x1800038c0  cmp     ebx, 3FFFFFFFh
0x1800038c6  jg      loc_180003958
0x1800038cc  add     ebx, ebx
0x1800038ce  cmp     ecx, ebx
0x1800038d0  jge     short loc_1800038C0
0x1800038d2  mov     eax, ebx
0x1800038d4  mov     ecx, 0FFFFFFFFh
0x1800038d9  add     rax, rax
0x1800038dc  cmp     rax, rcx
0x1800038df  ja      short loc_180003958
0x1800038e1  mov     rcx, [rdi+8]; pv
0x1800038e5  mov     edx, eax; cb
0x1800038e7  call    cs:__imp_CoTaskMemRealloc
0x1800038ed  test    rax, rax
0x1800038f0  jz      short loc_180003958
0x1800038f2  mov     [rdi+8], rax
0x1800038f6  mov     [rdi+4], ebx
0x1800038f9  cmp     dword ptr [rdi], 0
0x1800038fc  jl      short loc_180003958
0x1800038fe  cmp     [rdi], ebx
0x180003900  jge     short loc_180003958
0x180003902  mov     ecx, ebx
0x180003904  sub     ecx, [rdi]
0x180003906  cmp     ecx, ebx
0x180003908  jg      short loc_180003958
0x18000390a  movsxd  rdx, ecx
0x18000390d  lea     eax, [rsi+rsi]
0x180003910  movsxd  rcx, dword ptr [rdi]
0x180003913  add     rdx, rdx; DestinationSize
0x180003916  movsxd  r9, eax; SourceSize
0x180003919  mov     r8, rbp; Source
0x18000391c  mov     rax, [rdi+8]
0x180003920  lea     rcx, [rax+rcx*2]; Destination
0x180003924  call    cs:__imp_memcpy_s
0x18000392a  test    eax, eax
0x18000392c  jz      short loc_180003942
0x18000392e  cmp     eax, 0Ch
0x180003931  jz      short loc_180003979
0x180003933  cmp     eax, 16h
0x180003936  jz      short loc_18000396E
0x180003938  cmp     eax, 22h ; '"'
0x18000393b  jz      short loc_18000396E
0x18000393d  cmp     eax, 50h ; 'P'
0x180003940  jnz     short loc_180003963
0x180003942  add     [rdi], esi
0x180003944  movsxd  rdx, dword ptr [rdi]
0x180003947  xor     eax, eax
0x180003949  mov     rcx, [rdi+8]
0x18000394d  mov     [rcx+rdx*2], ax
0x180003951  mov     eax, 1
0x180003956  jmp     short loc_18000395A
0x180003958  xor     eax, eax
0x18000395a  add     rsp, 28h
0x18000395e  pop     rdi
0x18000395f  pop     rsi
0x180003960  pop     rbp
0x180003961  pop     rbx
0x180003962  retn
0x180003963  mov     ecx, 80004005h; int
0x180003968  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000396e  mov     ecx, 80070057h; int
0x180003973  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003979  mov     ecx, 8007000Eh; int
0x18000397e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

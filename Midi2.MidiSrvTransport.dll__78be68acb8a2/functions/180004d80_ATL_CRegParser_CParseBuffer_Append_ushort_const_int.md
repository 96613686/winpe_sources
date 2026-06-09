# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180004d80`
- end: `0x180004e73`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000695c`

## callees

- `0x180004d80`
- `0x180004eb8`
- `0x180009228`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004dd7`

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
0x180004d80  push    rbx
0x180004d82  push    rbp
0x180004d83  push    rsi
0x180004d84  push    rdi
0x180004d85  sub     rsp, 28h
0x180004d89  mov     rdi, rcx
0x180004d8c  mov     esi, r8d
0x180004d8f  lea     ecx, [r8+1]
0x180004d93  mov     rbp, rdx
0x180004d96  add     ecx, [rdi]
0x180004d98  cmp     ecx, [rdi]
0x180004d9a  jle     loc_180004E47
0x180004da0  cmp     ecx, r8d
0x180004da3  jle     loc_180004E47
0x180004da9  mov     ebx, [rdi+4]
0x180004dac  cmp     ecx, ebx
0x180004dae  jl      short loc_180004DE9
0x180004db0  cmp     ebx, 3FFFFFFFh
0x180004db6  jg      loc_180004E47
0x180004dbc  add     ebx, ebx
0x180004dbe  cmp     ecx, ebx
0x180004dc0  jge     short loc_180004DB0
0x180004dc2  mov     eax, ebx
0x180004dc4  mov     ecx, 0FFFFFFFFh
0x180004dc9  add     rax, rax
0x180004dcc  cmp     rax, rcx
0x180004dcf  ja      short loc_180004E47
0x180004dd1  mov     rcx, [rdi+8]; pv
0x180004dd5  mov     edx, eax; cb
0x180004dd7  call    cs:__imp_CoTaskMemRealloc
0x180004ddd  test    rax, rax
0x180004de0  jz      short loc_180004E47
0x180004de2  mov     [rdi+8], rax
0x180004de6  mov     [rdi+4], ebx
0x180004de9  cmp     dword ptr [rdi], 0
0x180004dec  jl      short loc_180004E47
0x180004dee  cmp     [rdi], ebx
0x180004df0  jge     short loc_180004E47
0x180004df2  mov     ecx, ebx
0x180004df4  sub     ecx, [rdi]
0x180004df6  cmp     ecx, ebx
0x180004df8  jg      short loc_180004E47
0x180004dfa  movsxd  rdx, ecx
0x180004dfd  lea     eax, [rsi+rsi]
0x180004e00  movsxd  rcx, dword ptr [rdi]
0x180004e03  add     rdx, rdx; DestinationSize
0x180004e06  movsxd  r9, eax; SourceSize
0x180004e09  mov     r8, rbp; Source
0x180004e0c  mov     rax, [rdi+8]
0x180004e10  lea     rcx, [rax+rcx*2]; Destination
0x180004e14  call    memcpy_s
0x180004e19  test    eax, eax
0x180004e1b  jz      short loc_180004E31
0x180004e1d  cmp     eax, 0Ch
0x180004e20  jz      short loc_180004E68
0x180004e22  cmp     eax, 16h
0x180004e25  jz      short loc_180004E5D
0x180004e27  cmp     eax, 22h ; '"'
0x180004e2a  jz      short loc_180004E5D
0x180004e2c  cmp     eax, 50h ; 'P'
0x180004e2f  jnz     short loc_180004E52
0x180004e31  add     [rdi], esi
0x180004e33  movsxd  rdx, dword ptr [rdi]
0x180004e36  xor     eax, eax
0x180004e38  mov     rcx, [rdi+8]
0x180004e3c  mov     [rcx+rdx*2], ax
0x180004e40  mov     eax, 1
0x180004e45  jmp     short loc_180004E49
0x180004e47  xor     eax, eax
0x180004e49  add     rsp, 28h
0x180004e4d  pop     rdi
0x180004e4e  pop     rsi
0x180004e4f  pop     rbp
0x180004e50  pop     rbx
0x180004e51  retn
0x180004e52  mov     ecx, 80004005h; int
0x180004e57  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004e5d  mov     ecx, 80070057h; int
0x180004e62  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004e68  mov     ecx, 8007000Eh; int
0x180004e6d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

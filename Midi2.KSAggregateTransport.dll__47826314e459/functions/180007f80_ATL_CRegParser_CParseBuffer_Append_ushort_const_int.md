# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180007f80`
- end: `0x180008073`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009c28`

## callees

- `0x180007f80`
- `0x1800080b8`
- `0x18000c9a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007fd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007fd7`

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
0x180007f80  push    rbx
0x180007f82  push    rbp
0x180007f83  push    rsi
0x180007f84  push    rdi
0x180007f85  sub     rsp, 28h
0x180007f89  mov     rdi, rcx
0x180007f8c  mov     esi, r8d
0x180007f8f  lea     ecx, [r8+1]
0x180007f93  mov     rbp, rdx
0x180007f96  add     ecx, [rdi]
0x180007f98  cmp     ecx, [rdi]
0x180007f9a  jle     loc_180008047
0x180007fa0  cmp     ecx, r8d
0x180007fa3  jle     loc_180008047
0x180007fa9  mov     ebx, [rdi+4]
0x180007fac  cmp     ecx, ebx
0x180007fae  jl      short loc_180007FE9
0x180007fb0  cmp     ebx, 3FFFFFFFh
0x180007fb6  jg      loc_180008047
0x180007fbc  add     ebx, ebx
0x180007fbe  cmp     ecx, ebx
0x180007fc0  jge     short loc_180007FB0
0x180007fc2  mov     eax, ebx
0x180007fc4  mov     ecx, 0FFFFFFFFh
0x180007fc9  add     rax, rax
0x180007fcc  cmp     rax, rcx
0x180007fcf  ja      short loc_180008047
0x180007fd1  mov     rcx, [rdi+8]; pv
0x180007fd5  mov     edx, eax; cb
0x180007fd7  call    cs:__imp_CoTaskMemRealloc
0x180007fdd  test    rax, rax
0x180007fe0  jz      short loc_180008047
0x180007fe2  mov     [rdi+8], rax
0x180007fe6  mov     [rdi+4], ebx
0x180007fe9  cmp     dword ptr [rdi], 0
0x180007fec  jl      short loc_180008047
0x180007fee  cmp     [rdi], ebx
0x180007ff0  jge     short loc_180008047
0x180007ff2  mov     ecx, ebx
0x180007ff4  sub     ecx, [rdi]
0x180007ff6  cmp     ecx, ebx
0x180007ff8  jg      short loc_180008047
0x180007ffa  movsxd  rdx, ecx
0x180007ffd  lea     eax, [rsi+rsi]
0x180008000  movsxd  rcx, dword ptr [rdi]
0x180008003  add     rdx, rdx; DestinationSize
0x180008006  movsxd  r9, eax; SourceSize
0x180008009  mov     r8, rbp; Source
0x18000800c  mov     rax, [rdi+8]
0x180008010  lea     rcx, [rax+rcx*2]; Destination
0x180008014  call    memcpy_s
0x180008019  test    eax, eax
0x18000801b  jz      short loc_180008031
0x18000801d  cmp     eax, 0Ch
0x180008020  jz      short loc_180008068
0x180008022  cmp     eax, 16h
0x180008025  jz      short loc_18000805D
0x180008027  cmp     eax, 22h ; '"'
0x18000802a  jz      short loc_18000805D
0x18000802c  cmp     eax, 50h ; 'P'
0x18000802f  jnz     short loc_180008052
0x180008031  add     [rdi], esi
0x180008033  movsxd  rdx, dword ptr [rdi]
0x180008036  xor     eax, eax
0x180008038  mov     rcx, [rdi+8]
0x18000803c  mov     [rcx+rdx*2], ax
0x180008040  mov     eax, 1
0x180008045  jmp     short loc_180008049
0x180008047  xor     eax, eax
0x180008049  add     rsp, 28h
0x18000804d  pop     rdi
0x18000804e  pop     rsi
0x18000804f  pop     rbp
0x180008050  pop     rbx
0x180008051  retn
0x180008052  mov     ecx, 80004005h; int
0x180008057  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000805d  mov     ecx, 80070057h; int
0x180008062  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008068  mov     ecx, 8007000Eh; int
0x18000806d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

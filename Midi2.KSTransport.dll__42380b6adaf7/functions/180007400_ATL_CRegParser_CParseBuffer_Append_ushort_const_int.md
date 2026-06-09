# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180007400`
- end: `0x1800074f3`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800090a8`

## callees

- `0x180007400`
- `0x180007538`
- `0x18000be28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007457`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007457`

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
0x180007400  push    rbx
0x180007402  push    rbp
0x180007403  push    rsi
0x180007404  push    rdi
0x180007405  sub     rsp, 28h
0x180007409  mov     rdi, rcx
0x18000740c  mov     esi, r8d
0x18000740f  lea     ecx, [r8+1]
0x180007413  mov     rbp, rdx
0x180007416  add     ecx, [rdi]
0x180007418  cmp     ecx, [rdi]
0x18000741a  jle     loc_1800074C7
0x180007420  cmp     ecx, r8d
0x180007423  jle     loc_1800074C7
0x180007429  mov     ebx, [rdi+4]
0x18000742c  cmp     ecx, ebx
0x18000742e  jl      short loc_180007469
0x180007430  cmp     ebx, 3FFFFFFFh
0x180007436  jg      loc_1800074C7
0x18000743c  add     ebx, ebx
0x18000743e  cmp     ecx, ebx
0x180007440  jge     short loc_180007430
0x180007442  mov     eax, ebx
0x180007444  mov     ecx, 0FFFFFFFFh
0x180007449  add     rax, rax
0x18000744c  cmp     rax, rcx
0x18000744f  ja      short loc_1800074C7
0x180007451  mov     rcx, [rdi+8]; pv
0x180007455  mov     edx, eax; cb
0x180007457  call    cs:__imp_CoTaskMemRealloc
0x18000745d  test    rax, rax
0x180007460  jz      short loc_1800074C7
0x180007462  mov     [rdi+8], rax
0x180007466  mov     [rdi+4], ebx
0x180007469  cmp     dword ptr [rdi], 0
0x18000746c  jl      short loc_1800074C7
0x18000746e  cmp     [rdi], ebx
0x180007470  jge     short loc_1800074C7
0x180007472  mov     ecx, ebx
0x180007474  sub     ecx, [rdi]
0x180007476  cmp     ecx, ebx
0x180007478  jg      short loc_1800074C7
0x18000747a  movsxd  rdx, ecx
0x18000747d  lea     eax, [rsi+rsi]
0x180007480  movsxd  rcx, dword ptr [rdi]
0x180007483  add     rdx, rdx; DestinationSize
0x180007486  movsxd  r9, eax; SourceSize
0x180007489  mov     r8, rbp; Source
0x18000748c  mov     rax, [rdi+8]
0x180007490  lea     rcx, [rax+rcx*2]; Destination
0x180007494  call    memcpy_s
0x180007499  test    eax, eax
0x18000749b  jz      short loc_1800074B1
0x18000749d  cmp     eax, 0Ch
0x1800074a0  jz      short loc_1800074E8
0x1800074a2  cmp     eax, 16h
0x1800074a5  jz      short loc_1800074DD
0x1800074a7  cmp     eax, 22h ; '"'
0x1800074aa  jz      short loc_1800074DD
0x1800074ac  cmp     eax, 50h ; 'P'
0x1800074af  jnz     short loc_1800074D2
0x1800074b1  add     [rdi], esi
0x1800074b3  movsxd  rdx, dword ptr [rdi]
0x1800074b6  xor     eax, eax
0x1800074b8  mov     rcx, [rdi+8]
0x1800074bc  mov     [rcx+rdx*2], ax
0x1800074c0  mov     eax, 1
0x1800074c5  jmp     short loc_1800074C9
0x1800074c7  xor     eax, eax
0x1800074c9  add     rsp, 28h
0x1800074cd  pop     rdi
0x1800074ce  pop     rsi
0x1800074cf  pop     rbp
0x1800074d0  pop     rbx
0x1800074d1  retn
0x1800074d2  mov     ecx, 80004005h; int
0x1800074d7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800074dd  mov     ecx, 80070057h; int
0x1800074e2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800074e8  mov     ecx, 8007000Eh; int
0x1800074ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

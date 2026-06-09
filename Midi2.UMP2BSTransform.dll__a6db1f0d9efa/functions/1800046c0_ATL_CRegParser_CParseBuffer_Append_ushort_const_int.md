# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800046c0`
- end: `0x1800047b3`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000628c`

## callees

- `0x1800046c0`
- `0x1800047f8`
- `0x180008b08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004717`

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
0x1800046c0  push    rbx
0x1800046c2  push    rbp
0x1800046c3  push    rsi
0x1800046c4  push    rdi
0x1800046c5  sub     rsp, 28h
0x1800046c9  mov     rdi, rcx
0x1800046cc  mov     esi, r8d
0x1800046cf  lea     ecx, [r8+1]
0x1800046d3  mov     rbp, rdx
0x1800046d6  add     ecx, [rdi]
0x1800046d8  cmp     ecx, [rdi]
0x1800046da  jle     loc_180004787
0x1800046e0  cmp     ecx, r8d
0x1800046e3  jle     loc_180004787
0x1800046e9  mov     ebx, [rdi+4]
0x1800046ec  cmp     ecx, ebx
0x1800046ee  jl      short loc_180004729
0x1800046f0  cmp     ebx, 3FFFFFFFh
0x1800046f6  jg      loc_180004787
0x1800046fc  add     ebx, ebx
0x1800046fe  cmp     ecx, ebx
0x180004700  jge     short loc_1800046F0
0x180004702  mov     eax, ebx
0x180004704  mov     ecx, 0FFFFFFFFh
0x180004709  add     rax, rax
0x18000470c  cmp     rax, rcx
0x18000470f  ja      short loc_180004787
0x180004711  mov     rcx, [rdi+8]; pv
0x180004715  mov     edx, eax; cb
0x180004717  call    cs:__imp_CoTaskMemRealloc
0x18000471d  test    rax, rax
0x180004720  jz      short loc_180004787
0x180004722  mov     [rdi+8], rax
0x180004726  mov     [rdi+4], ebx
0x180004729  cmp     dword ptr [rdi], 0
0x18000472c  jl      short loc_180004787
0x18000472e  cmp     [rdi], ebx
0x180004730  jge     short loc_180004787
0x180004732  mov     ecx, ebx
0x180004734  sub     ecx, [rdi]
0x180004736  cmp     ecx, ebx
0x180004738  jg      short loc_180004787
0x18000473a  movsxd  rdx, ecx
0x18000473d  lea     eax, [rsi+rsi]
0x180004740  movsxd  rcx, dword ptr [rdi]
0x180004743  add     rdx, rdx; DestinationSize
0x180004746  movsxd  r9, eax; SourceSize
0x180004749  mov     r8, rbp; Source
0x18000474c  mov     rax, [rdi+8]
0x180004750  lea     rcx, [rax+rcx*2]; Destination
0x180004754  call    memcpy_s
0x180004759  test    eax, eax
0x18000475b  jz      short loc_180004771
0x18000475d  cmp     eax, 0Ch
0x180004760  jz      short loc_1800047A8
0x180004762  cmp     eax, 16h
0x180004765  jz      short loc_18000479D
0x180004767  cmp     eax, 22h ; '"'
0x18000476a  jz      short loc_18000479D
0x18000476c  cmp     eax, 50h ; 'P'
0x18000476f  jnz     short loc_180004792
0x180004771  add     [rdi], esi
0x180004773  movsxd  rdx, dword ptr [rdi]
0x180004776  xor     eax, eax
0x180004778  mov     rcx, [rdi+8]
0x18000477c  mov     [rcx+rdx*2], ax
0x180004780  mov     eax, 1
0x180004785  jmp     short loc_180004789
0x180004787  xor     eax, eax
0x180004789  add     rsp, 28h
0x18000478d  pop     rdi
0x18000478e  pop     rsi
0x18000478f  pop     rbp
0x180004790  pop     rbx
0x180004791  retn
0x180004792  mov     ecx, 80004005h; int
0x180004797  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000479d  mov     ecx, 80070057h; int
0x1800047a2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800047a8  mov     ecx, 8007000Eh; int
0x1800047ad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

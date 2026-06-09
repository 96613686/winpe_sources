# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003cac`
- end: `0x180003da0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000509c`

## callees

- `0x180003cac`
- `0x180004740`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003d40`
- `msvcrt!memcpy_s` at `0x180003d40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003d03`

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
0x180003cac  push    rbx
0x180003cae  push    rbp
0x180003caf  push    rsi
0x180003cb0  push    rdi
0x180003cb1  sub     rsp, 28h
0x180003cb5  mov     rdi, rcx
0x180003cb8  mov     esi, r8d
0x180003cbb  lea     ecx, [r8+1]
0x180003cbf  mov     rbp, rdx
0x180003cc2  add     ecx, [rdi]
0x180003cc4  cmp     ecx, [rdi]
0x180003cc6  jle     loc_180003D74
0x180003ccc  cmp     ecx, r8d
0x180003ccf  jle     loc_180003D74
0x180003cd5  mov     ebx, [rdi+4]
0x180003cd8  cmp     ecx, ebx
0x180003cda  jl      short loc_180003D15
0x180003cdc  cmp     ebx, 3FFFFFFFh
0x180003ce2  jg      loc_180003D74
0x180003ce8  add     ebx, ebx
0x180003cea  cmp     ecx, ebx
0x180003cec  jge     short loc_180003CDC
0x180003cee  mov     eax, ebx
0x180003cf0  mov     ecx, 0FFFFFFFFh
0x180003cf5  add     rax, rax
0x180003cf8  cmp     rax, rcx
0x180003cfb  ja      short loc_180003D74
0x180003cfd  mov     rcx, [rdi+8]; pv
0x180003d01  mov     edx, eax; cb
0x180003d03  call    cs:__imp_CoTaskMemRealloc
0x180003d09  test    rax, rax
0x180003d0c  jz      short loc_180003D74
0x180003d0e  mov     [rdi+8], rax
0x180003d12  mov     [rdi+4], ebx
0x180003d15  cmp     dword ptr [rdi], 0
0x180003d18  jl      short loc_180003D74
0x180003d1a  cmp     [rdi], ebx
0x180003d1c  jge     short loc_180003D74
0x180003d1e  mov     ecx, ebx
0x180003d20  sub     ecx, [rdi]
0x180003d22  cmp     ecx, ebx
0x180003d24  jg      short loc_180003D74
0x180003d26  movsxd  rdx, ecx
0x180003d29  lea     eax, [rsi+rsi]
0x180003d2c  movsxd  rcx, dword ptr [rdi]
0x180003d2f  add     rdx, rdx; DestinationSize
0x180003d32  movsxd  r9, eax; SourceSize
0x180003d35  mov     r8, rbp; Source
0x180003d38  mov     rax, [rdi+8]
0x180003d3c  lea     rcx, [rax+rcx*2]; Destination
0x180003d40  call    cs:__imp_memcpy_s
0x180003d46  test    eax, eax
0x180003d48  jz      short loc_180003D5E
0x180003d4a  cmp     eax, 0Ch
0x180003d4d  jz      short loc_180003D95
0x180003d4f  cmp     eax, 16h
0x180003d52  jz      short loc_180003D8A
0x180003d54  cmp     eax, 22h ; '"'
0x180003d57  jz      short loc_180003D8A
0x180003d59  cmp     eax, 50h ; 'P'
0x180003d5c  jnz     short loc_180003D7F
0x180003d5e  add     [rdi], esi
0x180003d60  movsxd  rdx, dword ptr [rdi]
0x180003d63  xor     eax, eax
0x180003d65  mov     rcx, [rdi+8]
0x180003d69  mov     [rcx+rdx*2], ax
0x180003d6d  mov     eax, 1
0x180003d72  jmp     short loc_180003D76
0x180003d74  xor     eax, eax
0x180003d76  add     rsp, 28h
0x180003d7a  pop     rdi
0x180003d7b  pop     rsi
0x180003d7c  pop     rbp
0x180003d7d  pop     rbx
0x180003d7e  retn
0x180003d7f  mov     ecx, 80004005h; int
0x180003d84  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003d8a  mov     ecx, 80070057h; int
0x180003d8f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003d95  mov     ecx, 8007000Eh; int
0x180003d9a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180002bdc`
- end: `0x180002cd0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003a94`

## callees

- `0x180002bdc`
- `0x180003558`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c70`
- `msvcrt!memcpy_s` at `0x180002c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180002c33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180002c33`

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
0x180002bdc  push    rbx
0x180002bde  push    rbp
0x180002bdf  push    rsi
0x180002be0  push    rdi
0x180002be1  sub     rsp, 28h
0x180002be5  mov     rdi, rcx
0x180002be8  mov     esi, r8d
0x180002beb  lea     ecx, [r8+1]
0x180002bef  mov     rbp, rdx
0x180002bf2  add     ecx, [rdi]
0x180002bf4  cmp     ecx, [rdi]
0x180002bf6  jle     loc_180002CA4
0x180002bfc  cmp     ecx, r8d
0x180002bff  jle     loc_180002CA4
0x180002c05  mov     ebx, [rdi+4]
0x180002c08  cmp     ecx, ebx
0x180002c0a  jl      short loc_180002C45
0x180002c0c  cmp     ebx, 3FFFFFFFh
0x180002c12  jg      loc_180002CA4
0x180002c18  add     ebx, ebx
0x180002c1a  cmp     ecx, ebx
0x180002c1c  jge     short loc_180002C0C
0x180002c1e  mov     eax, ebx
0x180002c20  mov     ecx, 0FFFFFFFFh
0x180002c25  add     rax, rax
0x180002c28  cmp     rax, rcx
0x180002c2b  ja      short loc_180002CA4
0x180002c2d  mov     rcx, [rdi+8]; pv
0x180002c31  mov     edx, eax; cb
0x180002c33  call    cs:__imp_CoTaskMemRealloc
0x180002c39  test    rax, rax
0x180002c3c  jz      short loc_180002CA4
0x180002c3e  mov     [rdi+8], rax
0x180002c42  mov     [rdi+4], ebx
0x180002c45  cmp     dword ptr [rdi], 0
0x180002c48  jl      short loc_180002CA4
0x180002c4a  cmp     [rdi], ebx
0x180002c4c  jge     short loc_180002CA4
0x180002c4e  mov     ecx, ebx
0x180002c50  sub     ecx, [rdi]
0x180002c52  cmp     ecx, ebx
0x180002c54  jg      short loc_180002CA4
0x180002c56  movsxd  rdx, ecx
0x180002c59  lea     eax, [rsi+rsi]
0x180002c5c  movsxd  rcx, dword ptr [rdi]
0x180002c5f  add     rdx, rdx; DestinationSize
0x180002c62  movsxd  r9, eax; SourceSize
0x180002c65  mov     r8, rbp; Source
0x180002c68  mov     rax, [rdi+8]
0x180002c6c  lea     rcx, [rax+rcx*2]; Destination
0x180002c70  call    cs:__imp_memcpy_s
0x180002c76  test    eax, eax
0x180002c78  jz      short loc_180002C8E
0x180002c7a  cmp     eax, 0Ch
0x180002c7d  jz      short loc_180002CC5
0x180002c7f  cmp     eax, 16h
0x180002c82  jz      short loc_180002CBA
0x180002c84  cmp     eax, 22h ; '"'
0x180002c87  jz      short loc_180002CBA
0x180002c89  cmp     eax, 50h ; 'P'
0x180002c8c  jnz     short loc_180002CAF
0x180002c8e  add     [rdi], esi
0x180002c90  movsxd  rdx, dword ptr [rdi]
0x180002c93  xor     eax, eax
0x180002c95  mov     rcx, [rdi+8]
0x180002c99  mov     [rcx+rdx*2], ax
0x180002c9d  mov     eax, 1
0x180002ca2  jmp     short loc_180002CA6
0x180002ca4  xor     eax, eax
0x180002ca6  add     rsp, 28h
0x180002caa  pop     rdi
0x180002cab  pop     rsi
0x180002cac  pop     rbp
0x180002cad  pop     rbx
0x180002cae  retn
0x180002caf  mov     ecx, 80004005h; int
0x180002cb4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002cba  mov     ecx, 80070057h; int
0x180002cbf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002cc5  mov     ecx, 8007000Eh; int
0x180002cca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

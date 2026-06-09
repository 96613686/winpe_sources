# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180006cbc`
- end: `0x180006db0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008ecc`

## callees

- `0x180006cbc`
- `0x180006df4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006d50`
- `msvcrt!memcpy_s` at `0x180006d50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006d13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006d13`

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
0x180006cbc  push    rbx
0x180006cbe  push    rbp
0x180006cbf  push    rsi
0x180006cc0  push    rdi
0x180006cc1  sub     rsp, 28h
0x180006cc5  mov     rdi, rcx
0x180006cc8  mov     esi, r8d
0x180006ccb  lea     ecx, [r8+1]
0x180006ccf  mov     rbp, rdx
0x180006cd2  add     ecx, [rdi]
0x180006cd4  cmp     ecx, [rdi]
0x180006cd6  jle     loc_180006D84
0x180006cdc  cmp     ecx, r8d
0x180006cdf  jle     loc_180006D84
0x180006ce5  mov     ebx, [rdi+4]
0x180006ce8  cmp     ecx, ebx
0x180006cea  jl      short loc_180006D25
0x180006cec  cmp     ebx, 3FFFFFFFh
0x180006cf2  jg      loc_180006D84
0x180006cf8  add     ebx, ebx
0x180006cfa  cmp     ecx, ebx
0x180006cfc  jge     short loc_180006CEC
0x180006cfe  mov     eax, ebx
0x180006d00  mov     ecx, 0FFFFFFFFh
0x180006d05  add     rax, rax
0x180006d08  cmp     rax, rcx
0x180006d0b  ja      short loc_180006D84
0x180006d0d  mov     rcx, [rdi+8]; pv
0x180006d11  mov     edx, eax; cb
0x180006d13  call    cs:__imp_CoTaskMemRealloc
0x180006d19  test    rax, rax
0x180006d1c  jz      short loc_180006D84
0x180006d1e  mov     [rdi+8], rax
0x180006d22  mov     [rdi+4], ebx
0x180006d25  cmp     dword ptr [rdi], 0
0x180006d28  jl      short loc_180006D84
0x180006d2a  cmp     [rdi], ebx
0x180006d2c  jge     short loc_180006D84
0x180006d2e  mov     ecx, ebx
0x180006d30  sub     ecx, [rdi]
0x180006d32  cmp     ecx, ebx
0x180006d34  jg      short loc_180006D84
0x180006d36  movsxd  rdx, ecx
0x180006d39  lea     eax, [rsi+rsi]
0x180006d3c  movsxd  rcx, dword ptr [rdi]
0x180006d3f  add     rdx, rdx; DestinationSize
0x180006d42  movsxd  r9, eax; SourceSize
0x180006d45  mov     r8, rbp; Source
0x180006d48  mov     rax, [rdi+8]
0x180006d4c  lea     rcx, [rax+rcx*2]; Destination
0x180006d50  call    cs:__imp_memcpy_s
0x180006d56  test    eax, eax
0x180006d58  jz      short loc_180006D6E
0x180006d5a  cmp     eax, 0Ch
0x180006d5d  jz      short loc_180006DA5
0x180006d5f  cmp     eax, 16h
0x180006d62  jz      short loc_180006D9A
0x180006d64  cmp     eax, 22h ; '"'
0x180006d67  jz      short loc_180006D9A
0x180006d69  cmp     eax, 50h ; 'P'
0x180006d6c  jnz     short loc_180006D8F
0x180006d6e  add     [rdi], esi
0x180006d70  movsxd  rdx, dword ptr [rdi]
0x180006d73  xor     eax, eax
0x180006d75  mov     rcx, [rdi+8]
0x180006d79  mov     [rcx+rdx*2], ax
0x180006d7d  mov     eax, 1
0x180006d82  jmp     short loc_180006D86
0x180006d84  xor     eax, eax
0x180006d86  add     rsp, 28h
0x180006d8a  pop     rdi
0x180006d8b  pop     rsi
0x180006d8c  pop     rbp
0x180006d8d  pop     rbx
0x180006d8e  retn
0x180006d8f  mov     ecx, 80004005h; int
0x180006d94  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006d9a  mov     ecx, 80070057h; int
0x180006d9f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006da5  mov     ecx, 8007000Eh; int
0x180006daa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

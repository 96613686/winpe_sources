# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180006f80`
- end: `0x180007073`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b6c`

## callees

- `0x180006f80`
- `0x1800070b8`
- `0x18000b3e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006fd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006fd7`

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
0x180006f80  push    rbx
0x180006f82  push    rbp
0x180006f83  push    rsi
0x180006f84  push    rdi
0x180006f85  sub     rsp, 28h
0x180006f89  mov     rdi, rcx
0x180006f8c  mov     esi, r8d
0x180006f8f  lea     ecx, [r8+1]
0x180006f93  mov     rbp, rdx
0x180006f96  add     ecx, [rdi]
0x180006f98  cmp     ecx, [rdi]
0x180006f9a  jle     loc_180007047
0x180006fa0  cmp     ecx, r8d
0x180006fa3  jle     loc_180007047
0x180006fa9  mov     ebx, [rdi+4]
0x180006fac  cmp     ecx, ebx
0x180006fae  jl      short loc_180006FE9
0x180006fb0  cmp     ebx, 3FFFFFFFh
0x180006fb6  jg      loc_180007047
0x180006fbc  add     ebx, ebx
0x180006fbe  cmp     ecx, ebx
0x180006fc0  jge     short loc_180006FB0
0x180006fc2  mov     eax, ebx
0x180006fc4  mov     ecx, 0FFFFFFFFh
0x180006fc9  add     rax, rax
0x180006fcc  cmp     rax, rcx
0x180006fcf  ja      short loc_180007047
0x180006fd1  mov     rcx, [rdi+8]; pv
0x180006fd5  mov     edx, eax; cb
0x180006fd7  call    cs:__imp_CoTaskMemRealloc
0x180006fdd  test    rax, rax
0x180006fe0  jz      short loc_180007047
0x180006fe2  mov     [rdi+8], rax
0x180006fe6  mov     [rdi+4], ebx
0x180006fe9  cmp     dword ptr [rdi], 0
0x180006fec  jl      short loc_180007047
0x180006fee  cmp     [rdi], ebx
0x180006ff0  jge     short loc_180007047
0x180006ff2  mov     ecx, ebx
0x180006ff4  sub     ecx, [rdi]
0x180006ff6  cmp     ecx, ebx
0x180006ff8  jg      short loc_180007047
0x180006ffa  movsxd  rdx, ecx
0x180006ffd  lea     eax, [rsi+rsi]
0x180007000  movsxd  rcx, dword ptr [rdi]
0x180007003  add     rdx, rdx; DestinationSize
0x180007006  movsxd  r9, eax; SourceSize
0x180007009  mov     r8, rbp; Source
0x18000700c  mov     rax, [rdi+8]
0x180007010  lea     rcx, [rax+rcx*2]; Destination
0x180007014  call    memcpy_s
0x180007019  test    eax, eax
0x18000701b  jz      short loc_180007031
0x18000701d  cmp     eax, 0Ch
0x180007020  jz      short loc_180007068
0x180007022  cmp     eax, 16h
0x180007025  jz      short loc_18000705D
0x180007027  cmp     eax, 22h ; '"'
0x18000702a  jz      short loc_18000705D
0x18000702c  cmp     eax, 50h ; 'P'
0x18000702f  jnz     short loc_180007052
0x180007031  add     [rdi], esi
0x180007033  movsxd  rdx, dword ptr [rdi]
0x180007036  xor     eax, eax
0x180007038  mov     rcx, [rdi+8]
0x18000703c  mov     [rcx+rdx*2], ax
0x180007040  mov     eax, 1
0x180007045  jmp     short loc_180007049
0x180007047  xor     eax, eax
0x180007049  add     rsp, 28h
0x18000704d  pop     rdi
0x18000704e  pop     rsi
0x18000704f  pop     rbp
0x180007050  pop     rbx
0x180007051  retn
0x180007052  mov     ecx, 80004005h; int
0x180007057  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000705d  mov     ecx, 80070057h; int
0x180007062  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007068  mov     ecx, 8007000Eh; int
0x18000706d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800058a0`
- end: `0x180005993`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000746c`

## callees

- `0x1800058a0`
- `0x1800059d8`
- `0x180009ce8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800058f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800058f7`

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
0x1800058a0  push    rbx
0x1800058a2  push    rbp
0x1800058a3  push    rsi
0x1800058a4  push    rdi
0x1800058a5  sub     rsp, 28h
0x1800058a9  mov     rdi, rcx
0x1800058ac  mov     esi, r8d
0x1800058af  lea     ecx, [r8+1]
0x1800058b3  mov     rbp, rdx
0x1800058b6  add     ecx, [rdi]
0x1800058b8  cmp     ecx, [rdi]
0x1800058ba  jle     loc_180005967
0x1800058c0  cmp     ecx, r8d
0x1800058c3  jle     loc_180005967
0x1800058c9  mov     ebx, [rdi+4]
0x1800058cc  cmp     ecx, ebx
0x1800058ce  jl      short loc_180005909
0x1800058d0  cmp     ebx, 3FFFFFFFh
0x1800058d6  jg      loc_180005967
0x1800058dc  add     ebx, ebx
0x1800058de  cmp     ecx, ebx
0x1800058e0  jge     short loc_1800058D0
0x1800058e2  mov     eax, ebx
0x1800058e4  mov     ecx, 0FFFFFFFFh
0x1800058e9  add     rax, rax
0x1800058ec  cmp     rax, rcx
0x1800058ef  ja      short loc_180005967
0x1800058f1  mov     rcx, [rdi+8]; pv
0x1800058f5  mov     edx, eax; cb
0x1800058f7  call    cs:__imp_CoTaskMemRealloc
0x1800058fd  test    rax, rax
0x180005900  jz      short loc_180005967
0x180005902  mov     [rdi+8], rax
0x180005906  mov     [rdi+4], ebx
0x180005909  cmp     dword ptr [rdi], 0
0x18000590c  jl      short loc_180005967
0x18000590e  cmp     [rdi], ebx
0x180005910  jge     short loc_180005967
0x180005912  mov     ecx, ebx
0x180005914  sub     ecx, [rdi]
0x180005916  cmp     ecx, ebx
0x180005918  jg      short loc_180005967
0x18000591a  movsxd  rdx, ecx
0x18000591d  lea     eax, [rsi+rsi]
0x180005920  movsxd  rcx, dword ptr [rdi]
0x180005923  add     rdx, rdx; DestinationSize
0x180005926  movsxd  r9, eax; SourceSize
0x180005929  mov     r8, rbp; Source
0x18000592c  mov     rax, [rdi+8]
0x180005930  lea     rcx, [rax+rcx*2]; Destination
0x180005934  call    memcpy_s
0x180005939  test    eax, eax
0x18000593b  jz      short loc_180005951
0x18000593d  cmp     eax, 0Ch
0x180005940  jz      short loc_180005988
0x180005942  cmp     eax, 16h
0x180005945  jz      short loc_18000597D
0x180005947  cmp     eax, 22h ; '"'
0x18000594a  jz      short loc_18000597D
0x18000594c  cmp     eax, 50h ; 'P'
0x18000594f  jnz     short loc_180005972
0x180005951  add     [rdi], esi
0x180005953  movsxd  rdx, dword ptr [rdi]
0x180005956  xor     eax, eax
0x180005958  mov     rcx, [rdi+8]
0x18000595c  mov     [rcx+rdx*2], ax
0x180005960  mov     eax, 1
0x180005965  jmp     short loc_180005969
0x180005967  xor     eax, eax
0x180005969  add     rsp, 28h
0x18000596d  pop     rdi
0x18000596e  pop     rsi
0x18000596f  pop     rbp
0x180005970  pop     rbx
0x180005971  retn
0x180005972  mov     ecx, 80004005h; int
0x180005977  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000597d  mov     ecx, 80070057h; int
0x180005982  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005988  mov     ecx, 8007000Eh; int
0x18000598d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

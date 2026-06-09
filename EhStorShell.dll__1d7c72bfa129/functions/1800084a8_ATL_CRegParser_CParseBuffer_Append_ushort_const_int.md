# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800084a8`
- end: `0x180008568`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008ad8`

## callees

- `0x1800084a8`
- `0x180008570`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000853a`
- `msvcrt!memcpy_s` at `0x18000853a`
- `ole32!CoTaskMemRealloc` at `0x1800084fd`
- `ole32!CoTaskMemRealloc` at `0x1800084fd`

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
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 >= v7 )
    {
      while ( v6 >= v7 )
      {
        if ( v7 > 0x3FFFFFFF )
          return 0;
        v7 *= 2;
      }
      v8 = 2LL * (unsigned int)v7;
      if ( v8 > 0xFFFFFFFF )
        return 0;
      v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
      if ( !v9 )
        return 0;
      *((_QWORD *)this + 1) = v9;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v10 = v7 - *(_DWORD *)this;
      if ( v10 <= v7 )
      {
        v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v11);
        *(_DWORD *)this += a3;
        *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800084a8  push    rbx
0x1800084aa  push    rbp
0x1800084ab  push    rsi
0x1800084ac  push    rdi
0x1800084ad  sub     rsp, 28h
0x1800084b1  mov     rdi, rcx
0x1800084b4  mov     esi, r8d
0x1800084b7  lea     ecx, [r8+1]
0x1800084bb  mov     rbp, rdx
0x1800084be  add     ecx, [rdi]
0x1800084c0  cmp     ecx, [rdi]
0x1800084c2  jle     loc_18000855D
0x1800084c8  cmp     ecx, r8d
0x1800084cb  jle     loc_18000855D
0x1800084d1  mov     ebx, [rdi+4]
0x1800084d4  cmp     ecx, ebx
0x1800084d6  jl      short loc_18000850F
0x1800084d8  cmp     ecx, ebx
0x1800084da  jl      short loc_1800084E8
0x1800084dc  cmp     ebx, 3FFFFFFFh
0x1800084e2  jg      short loc_18000855D
0x1800084e4  add     ebx, ebx
0x1800084e6  jmp     short loc_1800084D8
0x1800084e8  mov     eax, ebx
0x1800084ea  mov     ecx, 0FFFFFFFFh
0x1800084ef  add     rax, rax
0x1800084f2  cmp     rax, rcx
0x1800084f5  ja      short loc_18000855D
0x1800084f7  mov     rcx, [rdi+8]; pv
0x1800084fb  mov     edx, eax; cb
0x1800084fd  call    cs:__imp_CoTaskMemRealloc
0x180008503  test    rax, rax
0x180008506  jz      short loc_18000855D
0x180008508  mov     [rdi+8], rax
0x18000850c  mov     [rdi+4], ebx
0x18000850f  cmp     dword ptr [rdi], 0
0x180008512  jl      short loc_18000855D
0x180008514  cmp     [rdi], ebx
0x180008516  jge     short loc_18000855D
0x180008518  mov     ecx, ebx
0x18000851a  sub     ecx, [rdi]
0x18000851c  cmp     ecx, ebx
0x18000851e  jg      short loc_18000855D
0x180008520  movsxd  rdx, ecx
0x180008523  lea     eax, [rsi+rsi]
0x180008526  movsxd  rcx, dword ptr [rdi]
0x180008529  add     rdx, rdx; DestinationSize
0x18000852c  movsxd  r9, eax; SourceSize
0x18000852f  mov     r8, rbp; Source
0x180008532  mov     rax, [rdi+8]
0x180008536  lea     rcx, [rax+rcx*2]; Destination
0x18000853a  call    cs:__imp_memcpy_s
0x180008540  mov     ecx, eax; int
0x180008542  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180008547  add     [rdi], esi
0x180008549  movsxd  rdx, dword ptr [rdi]
0x18000854c  xor     eax, eax
0x18000854e  mov     rcx, [rdi+8]
0x180008552  mov     [rcx+rdx*2], ax
0x180008556  mov     eax, 1
0x18000855b  jmp     short loc_18000855F
0x18000855d  xor     eax, eax
0x18000855f  add     rsp, 28h
0x180008563  pop     rdi
0x180008564  pop     rsi
0x180008565  pop     rbp
0x180008566  pop     rbx
0x180008567  retn
```

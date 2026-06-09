# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x140004c68`
- end: `0x140004d28`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008428`

## callees

- `0x140004c68`
- `0x140004d30`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140004cfa`
- `msvcrt!memcpy_s` at `0x140004cfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140004cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140004cbd`

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
0x140004c68  push    rbx
0x140004c6a  push    rbp
0x140004c6b  push    rsi
0x140004c6c  push    rdi
0x140004c6d  sub     rsp, 28h
0x140004c71  mov     rdi, rcx
0x140004c74  mov     esi, r8d
0x140004c77  lea     ecx, [r8+1]
0x140004c7b  mov     rbp, rdx
0x140004c7e  add     ecx, [rdi]
0x140004c80  cmp     ecx, [rdi]
0x140004c82  jle     loc_140004D1D
0x140004c88  cmp     ecx, r8d
0x140004c8b  jle     loc_140004D1D
0x140004c91  mov     ebx, [rdi+4]
0x140004c94  cmp     ecx, ebx
0x140004c96  jl      short loc_140004CCF
0x140004c98  cmp     ecx, ebx
0x140004c9a  jl      short loc_140004CA8
0x140004c9c  cmp     ebx, 3FFFFFFFh
0x140004ca2  jg      short loc_140004D1D
0x140004ca4  add     ebx, ebx
0x140004ca6  jmp     short loc_140004C98
0x140004ca8  mov     eax, ebx
0x140004caa  mov     ecx, 0FFFFFFFFh
0x140004caf  add     rax, rax
0x140004cb2  cmp     rax, rcx
0x140004cb5  ja      short loc_140004D1D
0x140004cb7  mov     rcx, [rdi+8]; pv
0x140004cbb  mov     edx, eax; cb
0x140004cbd  call    cs:__imp_CoTaskMemRealloc
0x140004cc3  test    rax, rax
0x140004cc6  jz      short loc_140004D1D
0x140004cc8  mov     [rdi+8], rax
0x140004ccc  mov     [rdi+4], ebx
0x140004ccf  cmp     dword ptr [rdi], 0
0x140004cd2  jl      short loc_140004D1D
0x140004cd4  cmp     [rdi], ebx
0x140004cd6  jge     short loc_140004D1D
0x140004cd8  mov     ecx, ebx
0x140004cda  sub     ecx, [rdi]
0x140004cdc  cmp     ecx, ebx
0x140004cde  jg      short loc_140004D1D
0x140004ce0  movsxd  rdx, ecx
0x140004ce3  lea     eax, [rsi+rsi]
0x140004ce6  movsxd  rcx, dword ptr [rdi]
0x140004ce9  add     rdx, rdx; DestinationSize
0x140004cec  movsxd  r9, eax; SourceSize
0x140004cef  mov     r8, rbp; Source
0x140004cf2  mov     rax, [rdi+8]
0x140004cf6  lea     rcx, [rax+rcx*2]; Destination
0x140004cfa  call    cs:__imp_memcpy_s
0x140004d00  mov     ecx, eax; int
0x140004d02  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140004d07  add     [rdi], esi
0x140004d09  movsxd  rdx, dword ptr [rdi]
0x140004d0c  xor     eax, eax
0x140004d0e  mov     rcx, [rdi+8]
0x140004d12  mov     [rcx+rdx*2], ax
0x140004d16  mov     eax, 1
0x140004d1b  jmp     short loc_140004D1F
0x140004d1d  xor     eax, eax
0x140004d1f  add     rsp, 28h
0x140004d23  pop     rdi
0x140004d24  pop     rsi
0x140004d25  pop     rbp
0x140004d26  pop     rbx
0x140004d27  retn
```

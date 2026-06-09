# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x14001d3d4`
- end: `0x14001d493`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140022414`

## callees

- `0x14000c284`
- `0x14001d3d4`
- `0x14001d49c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x14001d429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x14001d429`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const wchar_t *a2,
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
0x14001d3d4  push    rbx
0x14001d3d6  push    rbp
0x14001d3d7  push    rsi
0x14001d3d8  push    rdi
0x14001d3d9  sub     rsp, 28h
0x14001d3dd  mov     rdi, rcx
0x14001d3e0  mov     esi, r8d
0x14001d3e3  lea     ecx, [r8+1]
0x14001d3e7  mov     rbp, rdx
0x14001d3ea  add     ecx, [rdi]
0x14001d3ec  cmp     ecx, [rdi]
0x14001d3ee  jle     loc_14001D488
0x14001d3f4  cmp     ecx, r8d
0x14001d3f7  jle     loc_14001D488
0x14001d3fd  mov     ebx, [rdi+4]
0x14001d400  cmp     ecx, ebx
0x14001d402  jl      short loc_14001D43B
0x14001d404  cmp     ecx, ebx
0x14001d406  jl      short loc_14001D414
0x14001d408  cmp     ebx, 3FFFFFFFh
0x14001d40e  jg      short loc_14001D488
0x14001d410  add     ebx, ebx
0x14001d412  jmp     short loc_14001D404
0x14001d414  mov     eax, ebx
0x14001d416  mov     ecx, 0FFFFFFFFh
0x14001d41b  add     rax, rax
0x14001d41e  cmp     rax, rcx
0x14001d421  ja      short loc_14001D488
0x14001d423  mov     rcx, [rdi+8]; pv
0x14001d427  mov     edx, eax; cb
0x14001d429  call    cs:__imp_CoTaskMemRealloc
0x14001d42f  test    rax, rax
0x14001d432  jz      short loc_14001D488
0x14001d434  mov     [rdi+8], rax
0x14001d438  mov     [rdi+4], ebx
0x14001d43b  cmp     dword ptr [rdi], 0
0x14001d43e  jl      short loc_14001D488
0x14001d440  cmp     [rdi], ebx
0x14001d442  jge     short loc_14001D488
0x14001d444  mov     ecx, ebx
0x14001d446  sub     ecx, [rdi]
0x14001d448  cmp     ecx, ebx
0x14001d44a  jg      short loc_14001D488
0x14001d44c  movsxd  rdx, ecx
0x14001d44f  lea     eax, [rsi+rsi]
0x14001d452  movsxd  rcx, dword ptr [rdi]
0x14001d455  add     rdx, rdx; DestinationSize
0x14001d458  movsxd  r9, eax; SourceSize
0x14001d45b  mov     r8, rbp; Source
0x14001d45e  mov     rax, [rdi+8]
0x14001d462  lea     rcx, [rax+rcx*2]; Destination
0x14001d466  call    memcpy_s
0x14001d46b  mov     ecx, eax; int
0x14001d46d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14001d472  add     [rdi], esi
0x14001d474  movsxd  rdx, dword ptr [rdi]
0x14001d477  xor     eax, eax
0x14001d479  mov     rcx, [rdi+8]
0x14001d47d  mov     [rcx+rdx*2], ax
0x14001d481  mov     eax, 1
0x14001d486  jmp     short loc_14001D48A
0x14001d488  xor     eax, eax
0x14001d48a  add     rsp, 28h
0x14001d48e  pop     rdi
0x14001d48f  pop     rsi
0x14001d490  pop     rbp
0x14001d491  pop     rbx
0x14001d492  retn
```

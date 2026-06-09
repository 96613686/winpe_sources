# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180009ce0`
- end: `0x180009d9f`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d3ac`

## callees

- `0x180009ce0`
- `0x180009da8`
- `0x1800117b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009d35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009d35`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180009ce0  push    rbx
0x180009ce2  push    rbp
0x180009ce3  push    rsi
0x180009ce4  push    rdi
0x180009ce5  sub     rsp, 28h
0x180009ce9  mov     rdi, rcx
0x180009cec  mov     esi, r8d
0x180009cef  lea     ecx, [r8+1]
0x180009cf3  mov     rbp, rdx
0x180009cf6  add     ecx, [rdi]
0x180009cf8  cmp     ecx, [rdi]
0x180009cfa  jle     loc_180009D94
0x180009d00  cmp     ecx, r8d
0x180009d03  jle     loc_180009D94
0x180009d09  mov     ebx, [rdi+4]
0x180009d0c  cmp     ecx, ebx
0x180009d0e  jl      short loc_180009D47
0x180009d10  cmp     ecx, ebx
0x180009d12  jl      short loc_180009D20
0x180009d14  cmp     ebx, 3FFFFFFFh
0x180009d1a  jg      short loc_180009D94
0x180009d1c  add     ebx, ebx
0x180009d1e  jmp     short loc_180009D10
0x180009d20  mov     eax, ebx
0x180009d22  mov     ecx, 0FFFFFFFFh
0x180009d27  add     rax, rax
0x180009d2a  cmp     rax, rcx
0x180009d2d  ja      short loc_180009D94
0x180009d2f  mov     rcx, [rdi+8]; pv
0x180009d33  mov     edx, eax; cb
0x180009d35  call    cs:__imp_CoTaskMemRealloc
0x180009d3b  test    rax, rax
0x180009d3e  jz      short loc_180009D94
0x180009d40  mov     [rdi+8], rax
0x180009d44  mov     [rdi+4], ebx
0x180009d47  cmp     dword ptr [rdi], 0
0x180009d4a  jl      short loc_180009D94
0x180009d4c  cmp     [rdi], ebx
0x180009d4e  jge     short loc_180009D94
0x180009d50  mov     ecx, ebx
0x180009d52  sub     ecx, [rdi]
0x180009d54  cmp     ecx, ebx
0x180009d56  jg      short loc_180009D94
0x180009d58  movsxd  rdx, ecx
0x180009d5b  lea     eax, [rsi+rsi]
0x180009d5e  movsxd  rcx, dword ptr [rdi]
0x180009d61  add     rdx, rdx; DestinationSize
0x180009d64  movsxd  r9, eax; SourceSize
0x180009d67  mov     r8, rbp; Source
0x180009d6a  mov     rax, [rdi+8]
0x180009d6e  lea     rcx, [rax+rcx*2]; Destination
0x180009d72  call    memcpy_s
0x180009d77  mov     ecx, eax; int
0x180009d79  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009d7e  add     [rdi], esi
0x180009d80  movsxd  rdx, dword ptr [rdi]
0x180009d83  xor     eax, eax
0x180009d85  mov     rcx, [rdi+8]
0x180009d89  mov     [rcx+rdx*2], ax
0x180009d8d  mov     eax, 1
0x180009d92  jmp     short loc_180009D96
0x180009d94  xor     eax, eax
0x180009d96  add     rsp, 28h
0x180009d9a  pop     rdi
0x180009d9b  pop     rsi
0x180009d9c  pop     rbp
0x180009d9d  pop     rbx
0x180009d9e  retn
```

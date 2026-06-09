# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180018024`
- end: `0x1800180e4`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800190d4`

## callees

- `0x18000dd14`
- `0x180018024`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800180b6`
- `msvcrt!memcpy_s` at `0x1800180b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018079`

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
0x180018024  push    rbx
0x180018026  push    rbp
0x180018027  push    rsi
0x180018028  push    rdi
0x180018029  sub     rsp, 28h
0x18001802d  mov     rdi, rcx
0x180018030  mov     esi, r8d
0x180018033  lea     ecx, [r8+1]
0x180018037  mov     rbp, rdx
0x18001803a  add     ecx, [rdi]
0x18001803c  cmp     ecx, [rdi]
0x18001803e  jle     loc_1800180D9
0x180018044  cmp     ecx, r8d
0x180018047  jle     loc_1800180D9
0x18001804d  mov     ebx, [rdi+4]
0x180018050  cmp     ecx, ebx
0x180018052  jl      short loc_18001808B
0x180018054  cmp     ecx, ebx
0x180018056  jl      short loc_180018064
0x180018058  cmp     ebx, 3FFFFFFFh
0x18001805e  jg      short loc_1800180D9
0x180018060  add     ebx, ebx
0x180018062  jmp     short loc_180018054
0x180018064  mov     eax, ebx
0x180018066  mov     ecx, 0FFFFFFFFh
0x18001806b  add     rax, rax
0x18001806e  cmp     rax, rcx
0x180018071  ja      short loc_1800180D9
0x180018073  mov     rcx, [rdi+8]; pv
0x180018077  mov     edx, eax; cb
0x180018079  call    cs:__imp_CoTaskMemRealloc
0x18001807f  test    rax, rax
0x180018082  jz      short loc_1800180D9
0x180018084  mov     [rdi+8], rax
0x180018088  mov     [rdi+4], ebx
0x18001808b  cmp     dword ptr [rdi], 0
0x18001808e  jl      short loc_1800180D9
0x180018090  cmp     [rdi], ebx
0x180018092  jge     short loc_1800180D9
0x180018094  mov     ecx, ebx
0x180018096  sub     ecx, [rdi]
0x180018098  cmp     ecx, ebx
0x18001809a  jg      short loc_1800180D9
0x18001809c  movsxd  rdx, ecx
0x18001809f  lea     eax, [rsi+rsi]
0x1800180a2  movsxd  rcx, dword ptr [rdi]
0x1800180a5  add     rdx, rdx; DestinationSize
0x1800180a8  movsxd  r9, eax; SourceSize
0x1800180ab  mov     r8, rbp; Source
0x1800180ae  mov     rax, [rdi+8]
0x1800180b2  lea     rcx, [rax+rcx*2]; Destination
0x1800180b6  call    cs:__imp_memcpy_s
0x1800180bc  mov     ecx, eax; int
0x1800180be  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800180c3  add     [rdi], esi
0x1800180c5  movsxd  rdx, dword ptr [rdi]
0x1800180c8  xor     eax, eax
0x1800180ca  mov     rcx, [rdi+8]
0x1800180ce  mov     [rcx+rdx*2], ax
0x1800180d2  mov     eax, 1
0x1800180d7  jmp     short loc_1800180DB
0x1800180d9  xor     eax, eax
0x1800180db  add     rsp, 28h
0x1800180df  pop     rdi
0x1800180e0  pop     rsi
0x1800180e1  pop     rbp
0x1800180e2  pop     rbx
0x1800180e3  retn
```

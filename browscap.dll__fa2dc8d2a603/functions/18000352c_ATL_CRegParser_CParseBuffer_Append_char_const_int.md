# ATL::CRegParser::CParseBuffer::Append(char const *,int)

- ea: `0x18000352c`
- end: `0x1800035ff`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBDH@Z`
- size: `211`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002cc8`
- `0x180004a4c`

## callees

- `0x18000352c`
- `0x1800037f4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800035a1`
- `msvcrt!memcpy_s` at `0x1800035a1`
- `ole32!CoTaskMemRealloc` at `0x18000356e`
- `ole32!CoTaskMemRealloc` at `0x18000356e`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(ATL::CRegParser::CParseBuffer *this, const char *a2, int a3)
{
  rsize_t v4; // rsi
  int v6; // ecx
  int v7; // ebx
  LPVOID v8; // rax
  int v9; // eax
  errno_t v10; // eax

  v4 = a3;
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
        v8 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v7);
        if ( !v8 )
          return 0;
        *((_QWORD *)this + 1) = v8;
        *((_DWORD *)this + 1) = v7;
        goto LABEL_8;
      }
    }
    return 0;
  }
LABEL_8:
  if ( *(int *)this < 0 )
    return 0;
  if ( *(_DWORD *)this >= v7 )
    return 0;
  v9 = v7 - *(_DWORD *)this;
  if ( v9 > v7 )
    return 0;
  v10 = memcpy_s((void *const)(*((_QWORD *)this + 1) + *(int *)this), v9, a2, v4);
  if ( v10 )
  {
    if ( v10 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v10 == 22 || v10 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v10 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *(_DWORD *)this += v4;
  *(_BYTE *)(*(int *)this + *((_QWORD *)this + 1)) = 0;
  return 1;
}

```

## disassembly

```asm
0x18000352c  push    rbx
0x18000352e  push    rbp
0x18000352f  push    rsi
0x180003530  push    rdi
0x180003531  sub     rsp, 28h
0x180003535  mov     rdi, rcx
0x180003538  movsxd  rsi, r8d
0x18000353b  mov     rbp, rdx
0x18000353e  lea     ecx, [rsi+1]
0x180003541  add     ecx, [rdi]
0x180003543  cmp     ecx, [rdi]
0x180003545  jle     loc_1800035D3
0x18000354b  cmp     ecx, esi
0x18000354d  jle     loc_1800035D3
0x180003553  mov     ebx, [rdi+4]
0x180003556  cmp     ecx, ebx
0x180003558  jl      short loc_180003580
0x18000355a  cmp     ebx, 3FFFFFFFh
0x180003560  jg      short loc_1800035D3
0x180003562  add     ebx, ebx
0x180003564  cmp     ecx, ebx
0x180003566  jge     short loc_18000355A
0x180003568  mov     rcx, [rdi+8]; pv
0x18000356c  mov     edx, ebx; cb
0x18000356e  call    cs:__imp_CoTaskMemRealloc
0x180003574  test    rax, rax
0x180003577  jz      short loc_1800035D3
0x180003579  mov     [rdi+8], rax
0x18000357d  mov     [rdi+4], ebx
0x180003580  cmp     dword ptr [rdi], 0
0x180003583  jl      short loc_1800035D3
0x180003585  cmp     [rdi], ebx
0x180003587  jge     short loc_1800035D3
0x180003589  mov     eax, ebx
0x18000358b  sub     eax, [rdi]
0x18000358d  cmp     eax, ebx
0x18000358f  jg      short loc_1800035D3
0x180003591  movsxd  rcx, dword ptr [rdi]
0x180003594  mov     r9, rsi; SourceSize
0x180003597  add     rcx, [rdi+8]; Destination
0x18000359b  mov     r8, rbp; Source
0x18000359e  movsxd  rdx, eax; DestinationSize
0x1800035a1  call    cs:__imp_memcpy_s
0x1800035a7  test    eax, eax
0x1800035a9  jz      short loc_1800035BF
0x1800035ab  cmp     eax, 0Ch
0x1800035ae  jz      short loc_1800035F4
0x1800035b0  cmp     eax, 16h
0x1800035b3  jz      short loc_1800035E9
0x1800035b5  cmp     eax, 22h ; '"'
0x1800035b8  jz      short loc_1800035E9
0x1800035ba  cmp     eax, 50h ; 'P'
0x1800035bd  jnz     short loc_1800035DE
0x1800035bf  add     [rdi], esi
0x1800035c1  mov     rax, [rdi+8]
0x1800035c5  movsxd  rcx, dword ptr [rdi]
0x1800035c8  mov     byte ptr [rcx+rax], 0
0x1800035cc  mov     eax, 1
0x1800035d1  jmp     short loc_1800035D5
0x1800035d3  xor     eax, eax
0x1800035d5  add     rsp, 28h
0x1800035d9  pop     rdi
0x1800035da  pop     rsi
0x1800035db  pop     rbp
0x1800035dc  pop     rbx
0x1800035dd  retn
0x1800035de  mov     ecx, 80004005h; int
0x1800035e3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800035e9  mov     ecx, 80070057h; int
0x1800035ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800035f4  mov     ecx, 8007000Eh; int
0x1800035f9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

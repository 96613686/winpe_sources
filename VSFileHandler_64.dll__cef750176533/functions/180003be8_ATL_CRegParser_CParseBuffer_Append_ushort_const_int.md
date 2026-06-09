# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003be8`
- end: `0x180003d19`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `305`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180003d1c`

## callees

- `0x180002238`
- `0x180003be8`
- `0x18000be9c`
- `0x18000bfbc`
- `0x180024220`
- `0x1800245e0`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x180003c55`
- `ole32!CoTaskMemRealloc` at `0x180003c55`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v4; // rbp
  int v6; // ecx
  int v7; // eax
  unsigned __int64 v8; // rdx
  LPVOID v9; // rax
  int v10; // ecx
  int v11; // eax
  size_t v12; // rsi
  void *v13; // rcx
  unsigned __int64 v14; // rdi

  v4 = a3;
  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 <= *(_DWORD *)this || v6 <= a3 )
    return 0;
  v7 = *((_DWORD *)this + 1);
  if ( v6 >= v7 )
  {
    do
    {
      if ( v7 > 0x3FFFFFFF )
        return 0;
      v7 *= 2;
      *((_DWORD *)this + 1) = v7;
    }
    while ( v6 >= v7 );
    v8 = 2LL * (unsigned int)v7;
    if ( v8 > 0xFFFFFFFF )
      return 0;
    v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
    if ( !v9 )
      return 0;
    *((_QWORD *)this + 1) = v9;
  }
  if ( *(int *)this < 0 )
    return 0;
  v10 = *((_DWORD *)this + 1);
  if ( *(_DWORD *)this >= v10 )
    return 0;
  v11 = v10 - *(_DWORD *)this;
  if ( v11 > v10 )
    return 0;
  v12 = 2LL * v11;
  v13 = (void *)(*((_QWORD *)this + 1) + 2LL * *(int *)this);
  v14 = 2 * v4;
  if ( 2 * v4 )
  {
    if ( !v13 )
      goto LABEL_14;
    if ( !a2 || v12 < v14 )
    {
      memset(v13, 0, v12);
      if ( a2 )
      {
        if ( v12 >= v14 )
          goto LABEL_25;
        *errno() = 34;
LABEL_24:
        invalid_parameter_noinfo();
LABEL_25:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_14:
      *errno() = 22;
      goto LABEL_24;
    }
    memmove(v13, a2, 2 * v4);
  }
  *(_DWORD *)this += v4;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
  return 1;
}

```

## disassembly

```asm
0x180003be8  mov     [rsp+arg_0], rbx
0x180003bed  mov     [rsp+arg_8], rbp
0x180003bf2  mov     [rsp+arg_10], rsi
0x180003bf7  push    rdi
0x180003bf8  push    r14
0x180003bfa  push    r15
0x180003bfc  sub     rsp, 20h
0x180003c00  mov     rbx, rcx
0x180003c03  movsxd  rbp, r8d
0x180003c06  mov     r14, rdx
0x180003c09  lea     ecx, [rbp+1]
0x180003c0c  add     ecx, [rbx]
0x180003c0e  cmp     ecx, [rbx]
0x180003c10  jle     loc_180003CDE
0x180003c16  cmp     ecx, ebp
0x180003c18  jle     loc_180003CDE
0x180003c1e  mov     eax, [rbx+4]
0x180003c21  xor     r15d, r15d
0x180003c24  cmp     ecx, eax
0x180003c26  jl      short loc_180003C64
0x180003c28  cmp     eax, 3FFFFFFFh
0x180003c2d  jg      loc_180003CDE
0x180003c33  add     eax, eax
0x180003c35  mov     [rbx+4], eax
0x180003c38  cmp     ecx, eax
0x180003c3a  jge     short loc_180003C28
0x180003c3c  mov     edx, eax
0x180003c3e  mov     eax, 0FFFFFFFFh
0x180003c43  add     rdx, rdx
0x180003c46  cmp     rdx, rax
0x180003c49  ja      loc_180003CDE
0x180003c4f  mov     rcx, [rbx+8]; pv
0x180003c53  mov     edx, edx; cb
0x180003c55  call    cs:__imp_CoTaskMemRealloc
0x180003c5b  test    rax, rax
0x180003c5e  jz      short loc_180003CDE
0x180003c60  mov     [rbx+8], rax
0x180003c64  cmp     [rbx], r15d
0x180003c67  jl      short loc_180003CDE
0x180003c69  mov     ecx, [rbx+4]
0x180003c6c  cmp     [rbx], ecx
0x180003c6e  jge     short loc_180003CDE
0x180003c70  mov     eax, ecx
0x180003c72  sub     eax, [rbx]
0x180003c74  cmp     eax, ecx
0x180003c76  jg      short loc_180003CDE
0x180003c78  movsxd  rcx, dword ptr [rbx]
0x180003c7b  mov     rdi, rbp
0x180003c7e  movsxd  rsi, eax
0x180003c81  mov     rax, [rbx+8]
0x180003c85  add     rsi, rsi
0x180003c88  lea     rcx, [rax+rcx*2]; void *
0x180003c8c  add     rdi, rdi
0x180003c8f  jz      short loc_180003CB8
0x180003c91  test    rcx, rcx
0x180003c94  jnz     short loc_180003CA3
0x180003c96  call    _errno
0x180003c9b  mov     dword ptr [rax], 16h
0x180003ca1  jmp     short loc_180003D09
0x180003ca3  test    r14, r14
0x180003ca6  jz      short loc_180003CCD
0x180003ca8  cmp     rsi, rdi
0x180003cab  jb      short loc_180003CCD
0x180003cad  mov     r8, rdi; Size
0x180003cb0  mov     rdx, r14; Src
0x180003cb3  call    memmove
0x180003cb8  add     [rbx], ebp
0x180003cba  mov     rax, [rbx+8]
0x180003cbe  movsxd  rcx, dword ptr [rbx]
0x180003cc1  mov     [rax+rcx*2], r15w
0x180003cc6  mov     eax, 1
0x180003ccb  jmp     short loc_180003CE0
0x180003ccd  mov     r8, rsi; Size
0x180003cd0  xor     edx, edx; Val
0x180003cd2  call    memset
0x180003cd7  test    r14, r14
0x180003cda  jnz     short loc_180003CF9
0x180003cdc  jmp     short loc_180003C96
0x180003cde  xor     eax, eax
0x180003ce0  mov     rbx, [rsp+38h+arg_0]
0x180003ce5  mov     rbp, [rsp+38h+arg_8]
0x180003cea  mov     rsi, [rsp+38h+arg_10]
0x180003cef  add     rsp, 20h
0x180003cf3  pop     r15
0x180003cf5  pop     r14
0x180003cf7  pop     rdi
0x180003cf8  retn
0x180003cf9  cmp     rsi, rdi
0x180003cfc  jnb     short loc_180003D0E
0x180003cfe  call    _errno
0x180003d03  mov     dword ptr [rax], 22h ; '"'
0x180003d09  call    _invalid_parameter_noinfo
0x180003d0e  mov     ecx, 80070057h; int
0x180003d13  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

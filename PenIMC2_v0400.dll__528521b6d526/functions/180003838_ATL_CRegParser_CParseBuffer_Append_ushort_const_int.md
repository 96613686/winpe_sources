# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003838`
- end: `0x180003981`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `329`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003984`

## callees

- `0x180003838`
- `0x180004484`
- `0x18000e0cc`
- `0x18000e484`

## import_xrefs

- `ucrtbase_clr0400!_errno` at `0x1800038f6`
- `ucrtbase_clr0400!_errno` at `0x180003964`
- `ucrtbase_clr0400!_errno` at `0x1800038f6`
- `ucrtbase_clr0400!_errno` at `0x180003964`
- `ucrtbase_clr0400!_invalid_parameter_noinfo` at `0x180003970`
- `ucrtbase_clr0400!_invalid_parameter_noinfo` at `0x180003970`
- `ole32!CoTaskMemRealloc` at `0x1800038af`
- `ole32!CoTaskMemRealloc` at `0x1800038af`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v3; // eax
  __int64 v5; // rbp
  int v7; // ecx
  int v8; // r8d
  unsigned __int64 v9; // rax
  LPVOID v10; // rax
  int v11; // edx
  int v12; // ecx
  __int64 v13; // r8
  size_t v14; // rdi
  void *v15; // rcx
  unsigned __int64 v16; // rsi
  __int64 result; // rax

  v3 = *(_DWORD *)this;
  v5 = a3;
  v7 = *(_DWORD *)this + a3 + 1;
  if ( v7 <= v3 || v7 <= a3 )
    return 0;
  v8 = *((_DWORD *)this + 1);
  if ( v7 >= v8 )
  {
    do
    {
      if ( v8 > 0x3FFFFFFF )
        return 0;
      v8 *= 2;
      *((_DWORD *)this + 1) = v8;
    }
    while ( v7 >= v8 );
    v9 = 2LL * (unsigned int)v8;
    if ( v9 > 0xFFFFFFFF )
      return 0;
    v10 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v9);
    if ( !v10 )
      return 0;
    *((_QWORD *)this + 1) = v10;
    v3 = *(_DWORD *)this;
  }
  v11 = v3;
  if ( v3 < 0 )
    return 0;
  if ( v3 >= *((_DWORD *)this + 1) )
    return 0;
  v12 = *((_DWORD *)this + 1) - v3;
  if ( v12 > *((_DWORD *)this + 1) )
    return 0;
  v13 = *((_QWORD *)this + 1);
  v14 = 2LL * v12;
  v15 = (void *)(v13 + 2LL * v3);
  v16 = 2 * v5;
  if ( 2 * v5 )
  {
    if ( !v15 )
      goto LABEL_14;
    if ( !a2 || v14 < v16 )
    {
      memset_0(v15, 0, v14);
      if ( a2 )
      {
        if ( v14 >= v16 )
          goto LABEL_25;
        *_errno() = 34;
LABEL_24:
        _invalid_parameter_noinfo();
LABEL_25:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_14:
      *_errno() = 22;
      goto LABEL_24;
    }
    memcpy_0(v15, a2, 2 * v5);
    v11 = *(_DWORD *)this;
    v13 = *((_QWORD *)this + 1);
  }
  *(_DWORD *)this = v11 + v5;
  result = 1;
  *(_WORD *)(v13 + 2LL * (v11 + (int)v5)) = 0;
  return result;
}

```

## disassembly

```asm
0x180003838  mov     [rsp+arg_0], rbx
0x18000383d  mov     [rsp+arg_8], rbp
0x180003842  mov     [rsp+arg_10], rsi
0x180003847  push    rdi
0x180003848  push    r14
0x18000384a  push    r15
0x18000384c  sub     rsp, 20h
0x180003850  mov     eax, [rcx]
0x180003852  mov     rbx, rcx
0x180003855  movsxd  rbp, r8d
0x180003858  mov     r14, rdx
0x18000385b  lea     ecx, [rbp+1]
0x18000385e  add     ecx, eax
0x180003860  cmp     ecx, eax
0x180003862  jle     loc_180003944
0x180003868  cmp     ecx, ebp
0x18000386a  jle     loc_180003944
0x180003870  mov     r8d, [rbx+4]
0x180003874  xor     r15d, r15d
0x180003877  cmp     ecx, r8d
0x18000387a  jl      short loc_1800038C4
0x18000387c  cmp     r8d, 3FFFFFFFh
0x180003883  jg      loc_180003944
0x180003889  add     r8d, r8d
0x18000388c  mov     [rbx+4], r8d
0x180003890  cmp     ecx, r8d
0x180003893  jge     short loc_18000387C
0x180003895  mov     eax, r8d
0x180003898  mov     ecx, 0FFFFFFFFh
0x18000389d  add     rax, rax
0x1800038a0  cmp     rax, rcx
0x1800038a3  ja      loc_180003944
0x1800038a9  mov     rcx, [rbx+8]; pv
0x1800038ad  mov     edx, eax; cb
0x1800038af  call    cs:__imp_CoTaskMemRealloc
0x1800038b5  test    rax, rax
0x1800038b8  jz      loc_180003944
0x1800038be  mov     [rbx+8], rax
0x1800038c2  mov     eax, [rbx]
0x1800038c4  mov     edx, eax
0x1800038c6  test    eax, eax
0x1800038c8  js      short loc_180003944
0x1800038ca  cmp     eax, [rbx+4]
0x1800038cd  jge     short loc_180003944
0x1800038cf  mov     ecx, [rbx+4]
0x1800038d2  sub     ecx, eax
0x1800038d4  cmp     ecx, [rbx+4]
0x1800038d7  jg      short loc_180003944
0x1800038d9  mov     r8, [rbx+8]
0x1800038dd  mov     rsi, rbp
0x1800038e0  movsxd  rdi, ecx
0x1800038e3  cdqe
0x1800038e5  add     rdi, rdi
0x1800038e8  lea     rcx, [r8+rax*2]; void *
0x1800038ec  add     rsi, rsi
0x1800038ef  jz      short loc_18000391F
0x1800038f1  test    rcx, rcx
0x1800038f4  jnz     short loc_180003904
0x1800038f6  call    cs:__imp__errno
0x1800038fc  mov     dword ptr [rax], 16h
0x180003902  jmp     short loc_180003970
0x180003904  test    r14, r14
0x180003907  jz      short loc_180003933
0x180003909  cmp     rdi, rsi
0x18000390c  jb      short loc_180003933
0x18000390e  mov     r8, rsi; Size
0x180003911  mov     rdx, r14; Src
0x180003914  call    memcpy_0
0x180003919  mov     edx, [rbx]
0x18000391b  mov     r8, [rbx+8]
0x18000391f  lea     eax, [rdx+rbp]
0x180003922  movsxd  rcx, eax
0x180003925  mov     [rbx], eax
0x180003927  mov     eax, 1
0x18000392c  mov     [r8+rcx*2], r15w
0x180003931  jmp     short loc_180003946
0x180003933  mov     r8, rdi; Size
0x180003936  xor     edx, edx; Val
0x180003938  call    memset_0
0x18000393d  test    r14, r14
0x180003940  jnz     short loc_18000395F
0x180003942  jmp     short loc_1800038F6
0x180003944  xor     eax, eax
0x180003946  mov     rbx, [rsp+38h+arg_0]
0x18000394b  mov     rbp, [rsp+38h+arg_8]
0x180003950  mov     rsi, [rsp+38h+arg_10]
0x180003955  add     rsp, 20h
0x180003959  pop     r15
0x18000395b  pop     r14
0x18000395d  pop     rdi
0x18000395e  retn
0x18000395f  cmp     rdi, rsi
0x180003962  jnb     short loc_180003976
0x180003964  call    cs:__imp__errno
0x18000396a  mov     dword ptr [rax], 22h ; '"'
0x180003970  call    cs:__imp__invalid_parameter_noinfo
0x180003976  mov     ecx, 80070057h; int
0x18000397b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

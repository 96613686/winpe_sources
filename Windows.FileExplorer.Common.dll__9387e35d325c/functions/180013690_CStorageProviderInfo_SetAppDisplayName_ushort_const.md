# CStorageProviderInfo::SetAppDisplayName(ushort const *)

- ea: `0x180013690`
- end: `0x180013894`
- name: `?SetAppDisplayName@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `516`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000b9b0`
- `0x180013690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800137fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800137fc`

## string_xrefs

- `0x18001381e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetAppDisplayName(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  char *v2; // r14
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r8
  _WORD *v8; // rax
  int v9; // r15d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rcx
  unsigned __int64 v14; // rsi
  LPVOID v15; // rax
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (char *)this + 256;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 256);
    return 0;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    goto LABEL_22;
  v7 = *((_QWORD *)this + 34);
  if ( v7 == -1 )
  {
    if ( *((_QWORD *)this + 33) == -1 )
    {
      if ( *(_QWORD *)v2 )
      {
        do
          ++v4;
        while ( *(_WORD *)(*(_QWORD *)v2 + 2 * v4) );
      }
      else
      {
        v4 = 0;
      }
      *((_QWORD *)this + 33) = v4;
    }
    else
    {
      v4 = *((_QWORD *)this + 33);
    }
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)this + 34) = v7;
  }
  if ( !v7 )
  {
    if ( is_mul_ok(v6, 2u) )
    {
      v8 = CoTaskMemAlloc(2 * v6);
      if ( v8 )
      {
        v9 = 0;
        *((_QWORD *)v2 + 2) = v6;
        *(_QWORD *)v2 = v8;
        *v8 = 0;
      }
      else
      {
        v9 = -2147024882;
      }
      if ( v9 < 0 )
        goto LABEL_36;
      goto LABEL_11;
    }
LABEL_22:
    v9 = -2147024362;
    goto LABEL_23;
  }
  v9 = 0;
  if ( v6 > v7 )
  {
    v14 = 2 * v7;
    if ( is_mul_ok(v7, 2u) )
    {
      if ( v7 > 0x800 )
        v14 = v7 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*(LPVOID *)v2, 2 * v14);
      if ( !v15 )
      {
        v9 = -2147024882;
        goto LABEL_36;
      }
      *((_QWORD *)v2 + 2) = v14;
      *(_QWORD *)v2 = v15;
      goto LABEL_11;
    }
    goto LABEL_22;
  }
LABEL_11:
  if ( v5 != -1 )
  {
    v10 = *(_WORD **)v2;
    if ( v6 > 0x7FFFFFFF )
    {
      *v10 = 0;
    }
    else if ( v5 > 0x7FFFFFFE )
    {
      *v10 = 0;
    }
    else
    {
      v11 = v5;
      do
      {
        if ( !v11 )
          break;
        if ( !*v3 )
          break;
        *v10++ = *v3++;
        --v11;
        --v6;
      }
      while ( v6 );
      v12 = v10 - 1;
      if ( v6 )
        v12 = v10;
      *v12 = 0;
    }
  }
  *((_QWORD *)v2 + 1) = v5;
LABEL_23:
  if ( v9 >= 0 )
    return 0;
LABEL_36:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x46B,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013690  push    rbx
0x180013692  push    rbp
0x180013693  push    rsi
0x180013694  push    rdi
0x180013695  push    r14
0x180013697  push    r15
0x180013699  sub     rsp, 28h
0x18001369d  lea     r14, [rcx+100h]
0x1800136a4  mov     rbx, rdx
0x1800136a7  test    rdx, rdx
0x1800136aa  jz      loc_1800137A7
0x1800136b0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800136b7  mov     rbp, rax
0x1800136ba  nop     word ptr [rax+rax+00h]
0x1800136c0  inc     rbp
0x1800136c3  cmp     word ptr [rdx+rbp*2], 0
0x1800136c8  jnz     short loc_1800136C0
0x1800136ca  lea     rdi, [rbp+1]
0x1800136ce  cmp     rdi, rbp
0x1800136d1  jb      loc_180013789
0x1800136d7  mov     r8, [r14+10h]
0x1800136db  cmp     r8, rax
0x1800136de  jz      loc_180013842
0x1800136e4  test    r8, r8
0x1800136e7  jnz     loc_1800137BC
0x1800136ed  mov     eax, 2
0x1800136f2  mov     [rsp+58h+arg_0], r8
0x1800136f7  mul     rdi
0x1800136fa  test    rdx, rdx
0x1800136fd  jnz     loc_180013789
0x180013703  mov     rcx, rax; cb
0x180013706  call    cs:__imp_CoTaskMemAlloc
0x18001370c  test    rax, rax
0x18001370f  jz      loc_1800137B1
0x180013715  xor     r15d, r15d
0x180013718  mov     [r14+10h], rdi
0x18001371c  xor     ecx, ecx
0x18001371e  mov     [r14], rax
0x180013721  mov     [rax], cx
0x180013724  test    r15d, r15d
0x180013727  js      loc_180013819
0x18001372d  test    rdi, rdi
0x180013730  jz      short loc_180013783
0x180013732  mov     rdx, [r14]
0x180013735  cmp     rdi, 7FFFFFFFh
0x18001373c  ja      loc_180013880
0x180013742  cmp     rbp, 7FFFFFFEh
0x180013749  ja      loc_18001388A
0x18001374f  mov     rcx, rbp
0x180013752  test    rcx, rcx
0x180013755  jz      short loc_180013773
0x180013757  movzx   eax, word ptr [rbx]
0x18001375a  test    ax, ax
0x18001375d  jz      short loc_180013773
0x18001375f  mov     [rdx], ax
0x180013762  add     rbx, 2
0x180013766  add     rdx, 2
0x18001376a  dec     rcx
0x18001376d  sub     rdi, 1
0x180013771  jnz     short loc_180013752
0x180013773  test    rdi, rdi
0x180013776  lea     rcx, [rdx-2]
0x18001377a  cmovnz  rcx, rdx
0x18001377e  xor     eax, eax
0x180013780  mov     [rcx], ax
0x180013783  mov     [r14+8], rbp
0x180013787  jmp     short loc_18001378F
0x180013789  mov     r15d, 80070216h
0x18001378f  test    r15d, r15d
0x180013792  js      loc_180013819
0x180013798  xor     eax, eax
0x18001379a  add     rsp, 28h
0x18001379e  pop     r15
0x1800137a0  pop     r14
0x1800137a2  pop     rdi
0x1800137a3  pop     rsi
0x1800137a4  pop     rbp
0x1800137a5  pop     rbx
0x1800137a6  retn
0x1800137a7  mov     rcx, r14
0x1800137aa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800137af  jmp     short loc_180013798
0x1800137b1  mov     r15d, 8007000Eh
0x1800137b7  jmp     loc_180013724
0x1800137bc  xor     r15d, r15d
0x1800137bf  cmp     rdi, r8
0x1800137c2  jbe     loc_18001372D
0x1800137c8  mov     eax, 2
0x1800137cd  mul     r8
0x1800137d0  mov     rsi, rax
0x1800137d3  test    rdx, rdx
0x1800137d6  jnz     short loc_180013789
0x1800137d8  mov     rcx, rax
0x1800137db  sub     rcx, r8
0x1800137de  cmp     rcx, 800h
0x1800137e5  jbe     short loc_1800137EE
0x1800137e7  lea     rsi, [r8+800h]
0x1800137ee  mov     rcx, [r14]; pv
0x1800137f1  cmp     rdi, rsi
0x1800137f4  cmova   rsi, rdi
0x1800137f8  lea     rdx, [rsi+rsi]; cb
0x1800137fc  call    cs:__imp_CoTaskMemRealloc
0x180013802  test    rax, rax
0x180013805  jz      short loc_180013813
0x180013807  mov     [r14+10h], rsi
0x18001380b  mov     [r14], rax
0x18001380e  jmp     loc_18001372D
0x180013813  mov     r15d, 8007000Eh
0x180013819  mov     rcx, [rsp+58h]; this
0x18001381e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180013825  mov     r9d, r15d; char *
0x180013828  mov     edx, 46Bh; void *
0x18001382d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013832  mov     eax, r15d
0x180013835  add     rsp, 28h
0x180013839  pop     r15
0x18001383b  pop     r14
0x18001383d  pop     rdi
0x18001383e  pop     rsi
0x18001383f  pop     rbp
0x180013840  pop     rbx
0x180013841  retn
0x180013842  mov     rcx, [r14+8]
0x180013846  cmp     rcx, rax
0x180013849  jnz     short loc_180013867
0x18001384b  mov     rcx, [r14]
0x18001384e  test    rcx, rcx
0x180013851  jnz     short loc_180013857
0x180013853  xor     eax, eax
0x180013855  jmp     short loc_180013861
0x180013857  inc     rax
0x18001385a  cmp     word ptr [rcx+rax*2], 0
0x18001385f  jnz     short loc_180013857
0x180013861  mov     [r14+8], rax
0x180013865  jmp     short loc_18001386A
0x180013867  mov     rax, rcx
0x18001386a  lea     r8, [rax+1]
0x18001386e  xor     eax, eax
0x180013870  cmp     [r14], rax
0x180013873  cmovz   r8, rax
0x180013877  mov     [r14+10h], r8
0x18001387b  jmp     loc_1800136E4
0x180013880  xor     eax, eax
0x180013882  mov     [rdx], ax
0x180013885  jmp     loc_180013783
0x18001388a  xor     eax, eax
0x18001388c  mov     [rdx], ax
0x18001388f  jmp     loc_180013783
```

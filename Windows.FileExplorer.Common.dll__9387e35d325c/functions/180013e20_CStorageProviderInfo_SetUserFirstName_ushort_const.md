# CStorageProviderInfo::SetUserFirstName(ushort const *)

- ea: `0x180013e20`
- end: `0x180013fef`
- name: `?SetUserFirstName@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `463`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000b9b0`
- `0x180013e20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013e9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013e9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180013f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180013f6b`

## string_xrefs

- `0x180013f8c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetUserFirstName(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  char *v2; // rdi
  const unsigned __int16 *v3; // r14
  __int64 v4; // rcx
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rsi
  int v7; // ebx
  unsigned __int64 v9; // r8
  _WORD *v10; // rax
  _WORD *v11; // rdx
  unsigned __int64 v12; // rax
  _WORD *v13; // rcx
  unsigned __int64 v14; // rbx
  LPVOID v15; // rax
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (char *)this + 312;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 312);
    return 0;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    goto LABEL_5;
  v9 = *((_QWORD *)v2 + 2);
  if ( v9 == -1 )
  {
    if ( *((_QWORD *)v2 + 1) == -1 )
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
      *((_QWORD *)v2 + 1) = v4;
    }
    else
    {
      v4 = *((_QWORD *)v2 + 1);
    }
    v9 = (v4 + 1) & -(__int64)(*(_QWORD *)v2 != 0);
    *((_QWORD *)v2 + 2) = v9;
  }
  if ( v9 )
  {
    v7 = 0;
    if ( v6 <= v9 )
    {
LABEL_16:
      if ( v7 < 0 )
        goto LABEL_37;
      goto LABEL_17;
    }
    v14 = 2 * v9;
    if ( is_mul_ok(v9, 2u) )
    {
      if ( v9 > 0x800 )
        v14 = v9 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*(LPVOID *)v2, 2 * v14);
      if ( !v15 )
      {
        v7 = -2147024882;
        goto LABEL_37;
      }
      *((_QWORD *)v2 + 2) = v14;
      *(_QWORD *)v2 = v15;
      goto LABEL_13;
    }
LABEL_5:
    v7 = -2147024362;
    goto LABEL_6;
  }
  if ( !is_mul_ok(v6, 2u) )
    goto LABEL_5;
  v10 = CoTaskMemAlloc(2 * v6);
  if ( !v10 )
  {
    v7 = -2147024882;
    goto LABEL_16;
  }
  *((_QWORD *)v2 + 2) = v6;
  *(_QWORD *)v2 = v10;
  *v10 = 0;
LABEL_13:
  v7 = 0;
LABEL_17:
  if ( v5 != -1 )
  {
    v11 = *(_WORD **)v2;
    if ( v6 > 0x7FFFFFFF || v5 > 0x7FFFFFFE )
    {
      *v11 = 0;
    }
    else
    {
      v12 = v5;
      do
      {
        if ( !v12 )
          break;
        if ( !*v3 )
          break;
        *v11++ = *v3++;
        --v12;
        --v6;
      }
      while ( v6 );
      v13 = v11 - 1;
      if ( v6 )
        v13 = v11;
      *v13 = 0;
    }
  }
  *((_QWORD *)v2 + 1) = v5;
LABEL_6:
  if ( v7 >= 0 )
    return 0;
LABEL_37:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A1,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v7,
    v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013e20  push    rbx
0x180013e22  push    rbp
0x180013e23  push    rsi
0x180013e24  push    rdi
0x180013e25  push    r14
0x180013e27  push    r15
0x180013e29  sub     rsp, 28h
0x180013e2d  xor     r15d, r15d
0x180013e30  lea     rdi, [rcx+138h]
0x180013e37  mov     r14, rdx
0x180013e3a  test    rdx, rdx
0x180013e3d  jz      short loc_180013EB5
0x180013e3f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013e43  mov     rbp, rcx
0x180013e46  inc     rbp
0x180013e49  cmp     [rdx+rbp*2], r15w
0x180013e4e  jnz     short loc_180013E46
0x180013e50  lea     rsi, [rbp+1]
0x180013e54  cmp     rsi, rbp
0x180013e57  jnb     short loc_180013E75
0x180013e59  mov     ebx, 80070216h
0x180013e5e  test    ebx, ebx
0x180013e60  js      loc_180013F87
0x180013e66  xor     eax, eax
0x180013e68  add     rsp, 28h
0x180013e6c  pop     r15
0x180013e6e  pop     r14
0x180013e70  pop     rdi
0x180013e71  pop     rsi
0x180013e72  pop     rbp
0x180013e73  pop     rbx
0x180013e74  retn
0x180013e75  mov     r8, [rdi+10h]
0x180013e79  cmp     r8, rcx
0x180013e7c  jz      loc_180013FA7
0x180013e82  test    r8, r8
0x180013e85  jnz     loc_180013F2B
0x180013e8b  lea     eax, [r8+2]
0x180013e8f  mul     rsi
0x180013e92  test    rdx, rdx
0x180013e95  jnz     short loc_180013E59
0x180013e97  mov     rcx, rax; cb
0x180013e9a  call    cs:__imp_CoTaskMemAlloc
0x180013ea0  test    rax, rax
0x180013ea3  jz      short loc_180013EBF
0x180013ea5  mov     [rdi+10h], rsi
0x180013ea9  mov     [rdi], rax
0x180013eac  mov     [rax], r15w
0x180013eb0  mov     ebx, r15d
0x180013eb3  jmp     short loc_180013ECC
0x180013eb5  mov     rcx, rdi
0x180013eb8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013ebd  jmp     short loc_180013E66
0x180013ebf  mov     ebx, 8007000Eh
0x180013ec4  test    ebx, ebx
0x180013ec6  js      loc_180013F87
0x180013ecc  test    rsi, rsi
0x180013ecf  jz      short loc_180013F22
0x180013ed1  mov     rdx, [rdi]
0x180013ed4  cmp     rsi, 7FFFFFFFh
0x180013edb  ja      loc_180013FE6
0x180013ee1  cmp     rbp, 7FFFFFFEh
0x180013ee8  ja      loc_180013FE6
0x180013eee  mov     rax, rbp
0x180013ef1  test    rax, rax
0x180013ef4  jz      short loc_180013F13
0x180013ef6  movzx   ecx, word ptr [r14]
0x180013efa  test    cx, cx
0x180013efd  jz      short loc_180013F13
0x180013eff  mov     [rdx], cx
0x180013f02  add     r14, 2
0x180013f06  add     rdx, 2
0x180013f0a  dec     rax
0x180013f0d  sub     rsi, 1
0x180013f11  jnz     short loc_180013EF1
0x180013f13  test    rsi, rsi
0x180013f16  lea     rcx, [rdx-2]
0x180013f1a  cmovnz  rcx, rdx
0x180013f1e  mov     [rcx], r15w
0x180013f22  mov     [rdi+8], rbp
0x180013f26  jmp     loc_180013E5E
0x180013f2b  mov     ebx, r15d
0x180013f2e  cmp     rsi, r8
0x180013f31  jbe     short loc_180013EC4
0x180013f33  mov     eax, 2
0x180013f38  mul     r8
0x180013f3b  mov     rbx, rax
0x180013f3e  test    rdx, rdx
0x180013f41  jnz     loc_180013E59
0x180013f47  mov     rcx, rax
0x180013f4a  sub     rcx, r8
0x180013f4d  cmp     rcx, 800h
0x180013f54  jbe     short loc_180013F5D
0x180013f56  lea     rbx, [r8+800h]
0x180013f5d  mov     rcx, [rdi]; pv
0x180013f60  cmp     rsi, rbx
0x180013f63  cmova   rbx, rsi
0x180013f67  lea     rdx, [rbx+rbx]; cb
0x180013f6b  call    cs:__imp_CoTaskMemRealloc
0x180013f71  test    rax, rax
0x180013f74  jz      short loc_180013F82
0x180013f76  mov     [rdi+10h], rbx
0x180013f7a  mov     [rdi], rax
0x180013f7d  jmp     loc_180013EB0
0x180013f82  mov     ebx, 8007000Eh
0x180013f87  mov     rcx, [rsp+58h]; this
0x180013f8c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180013f93  mov     r9d, ebx; char *
0x180013f96  mov     edx, 4A1h; void *
0x180013f9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fa0  mov     eax, ebx
0x180013fa2  jmp     loc_180013E68
0x180013fa7  cmp     [rdi+8], rcx
0x180013fab  jnz     short loc_180013FCA
0x180013fad  mov     rax, [rdi]
0x180013fb0  test    rax, rax
0x180013fb3  jnz     short loc_180013FBA
0x180013fb5  mov     rcx, r15
0x180013fb8  jmp     short loc_180013FC4
0x180013fba  inc     rcx
0x180013fbd  cmp     [rax+rcx*2], r15w
0x180013fc2  jnz     short loc_180013FBA
0x180013fc4  mov     [rdi+8], rcx
0x180013fc8  jmp     short loc_180013FCE
0x180013fca  mov     rcx, [rdi+8]
0x180013fce  mov     rax, [rdi]
0x180013fd1  inc     rcx
0x180013fd4  neg     rax
0x180013fd7  sbb     r8, r8
0x180013fda  and     r8, rcx
0x180013fdd  mov     [rdi+10h], r8
0x180013fe1  jmp     loc_180013E82
0x180013fe6  mov     [rdx], r15w
0x180013fea  jmp     loc_180013F22
```

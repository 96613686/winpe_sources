# CStorageProviderInfo::SetCid(ushort const *)

- ea: `0x18000c890`
- end: `0x18000ca94`
- name: `?SetCid@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `516`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000b9b0`
- `0x18000c890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c906`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c906`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c9fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c9fc`

## string_xrefs

- `0x18000ca1e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetCid(CStorageProviderInfo *this, const unsigned __int16 *a2)
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

  v2 = (char *)this + 264;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 264);
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
  v7 = *((_QWORD *)this + 35);
  if ( v7 == -1 )
  {
    if ( *((_QWORD *)this + 34) == -1 )
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
      *((_QWORD *)this + 34) = v4;
    }
    else
    {
      v4 = *((_QWORD *)this + 34);
    }
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)this + 35) = v7;
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
    (void *)0x481,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c890  push    rbx
0x18000c892  push    rbp
0x18000c893  push    rsi
0x18000c894  push    rdi
0x18000c895  push    r14
0x18000c897  push    r15
0x18000c899  sub     rsp, 28h
0x18000c89d  lea     r14, [rcx+108h]
0x18000c8a4  mov     rbx, rdx
0x18000c8a7  test    rdx, rdx
0x18000c8aa  jz      loc_18000C9A7
0x18000c8b0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c8b7  mov     rbp, rax
0x18000c8ba  nop     word ptr [rax+rax+00h]
0x18000c8c0  inc     rbp
0x18000c8c3  cmp     word ptr [rdx+rbp*2], 0
0x18000c8c8  jnz     short loc_18000C8C0
0x18000c8ca  lea     rdi, [rbp+1]
0x18000c8ce  cmp     rdi, rbp
0x18000c8d1  jb      loc_18000C989
0x18000c8d7  mov     r8, [r14+10h]
0x18000c8db  cmp     r8, rax
0x18000c8de  jz      loc_18000CA42
0x18000c8e4  test    r8, r8
0x18000c8e7  jnz     loc_18000C9BC
0x18000c8ed  mov     eax, 2
0x18000c8f2  mov     [rsp+58h+arg_0], r8
0x18000c8f7  mul     rdi
0x18000c8fa  test    rdx, rdx
0x18000c8fd  jnz     loc_18000C989
0x18000c903  mov     rcx, rax; cb
0x18000c906  call    cs:__imp_CoTaskMemAlloc
0x18000c90c  test    rax, rax
0x18000c90f  jz      loc_18000C9B1
0x18000c915  xor     r15d, r15d
0x18000c918  mov     [r14+10h], rdi
0x18000c91c  xor     ecx, ecx
0x18000c91e  mov     [r14], rax
0x18000c921  mov     [rax], cx
0x18000c924  test    r15d, r15d
0x18000c927  js      loc_18000CA19
0x18000c92d  test    rdi, rdi
0x18000c930  jz      short loc_18000C983
0x18000c932  mov     rdx, [r14]
0x18000c935  cmp     rdi, 7FFFFFFFh
0x18000c93c  ja      loc_18000CA80
0x18000c942  cmp     rbp, 7FFFFFFEh
0x18000c949  ja      loc_18000CA8A
0x18000c94f  mov     rcx, rbp
0x18000c952  test    rcx, rcx
0x18000c955  jz      short loc_18000C973
0x18000c957  movzx   eax, word ptr [rbx]
0x18000c95a  test    ax, ax
0x18000c95d  jz      short loc_18000C973
0x18000c95f  mov     [rdx], ax
0x18000c962  add     rbx, 2
0x18000c966  add     rdx, 2
0x18000c96a  dec     rcx
0x18000c96d  sub     rdi, 1
0x18000c971  jnz     short loc_18000C952
0x18000c973  test    rdi, rdi
0x18000c976  lea     rcx, [rdx-2]
0x18000c97a  cmovnz  rcx, rdx
0x18000c97e  xor     eax, eax
0x18000c980  mov     [rcx], ax
0x18000c983  mov     [r14+8], rbp
0x18000c987  jmp     short loc_18000C98F
0x18000c989  mov     r15d, 80070216h
0x18000c98f  test    r15d, r15d
0x18000c992  js      loc_18000CA19
0x18000c998  xor     eax, eax
0x18000c99a  add     rsp, 28h
0x18000c99e  pop     r15
0x18000c9a0  pop     r14
0x18000c9a2  pop     rdi
0x18000c9a3  pop     rsi
0x18000c9a4  pop     rbp
0x18000c9a5  pop     rbx
0x18000c9a6  retn
0x18000c9a7  mov     rcx, r14
0x18000c9aa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000c9af  jmp     short loc_18000C998
0x18000c9b1  mov     r15d, 8007000Eh
0x18000c9b7  jmp     loc_18000C924
0x18000c9bc  xor     r15d, r15d
0x18000c9bf  cmp     rdi, r8
0x18000c9c2  jbe     loc_18000C92D
0x18000c9c8  mov     eax, 2
0x18000c9cd  mul     r8
0x18000c9d0  mov     rsi, rax
0x18000c9d3  test    rdx, rdx
0x18000c9d6  jnz     short loc_18000C989
0x18000c9d8  mov     rcx, rax
0x18000c9db  sub     rcx, r8
0x18000c9de  cmp     rcx, 800h
0x18000c9e5  jbe     short loc_18000C9EE
0x18000c9e7  lea     rsi, [r8+800h]
0x18000c9ee  mov     rcx, [r14]; pv
0x18000c9f1  cmp     rdi, rsi
0x18000c9f4  cmova   rsi, rdi
0x18000c9f8  lea     rdx, [rsi+rsi]; cb
0x18000c9fc  call    cs:__imp_CoTaskMemRealloc
0x18000ca02  test    rax, rax
0x18000ca05  jz      short loc_18000CA13
0x18000ca07  mov     [r14+10h], rsi
0x18000ca0b  mov     [r14], rax
0x18000ca0e  jmp     loc_18000C92D
0x18000ca13  mov     r15d, 8007000Eh
0x18000ca19  mov     rcx, [rsp+58h]; this
0x18000ca1e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000ca25  mov     r9d, r15d; char *
0x18000ca28  mov     edx, 481h; void *
0x18000ca2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca32  mov     eax, r15d
0x18000ca35  add     rsp, 28h
0x18000ca39  pop     r15
0x18000ca3b  pop     r14
0x18000ca3d  pop     rdi
0x18000ca3e  pop     rsi
0x18000ca3f  pop     rbp
0x18000ca40  pop     rbx
0x18000ca41  retn
0x18000ca42  mov     rcx, [r14+8]
0x18000ca46  cmp     rcx, rax
0x18000ca49  jnz     short loc_18000CA67
0x18000ca4b  mov     rcx, [r14]
0x18000ca4e  test    rcx, rcx
0x18000ca51  jnz     short loc_18000CA57
0x18000ca53  xor     eax, eax
0x18000ca55  jmp     short loc_18000CA61
0x18000ca57  inc     rax
0x18000ca5a  cmp     word ptr [rcx+rax*2], 0
0x18000ca5f  jnz     short loc_18000CA57
0x18000ca61  mov     [r14+8], rax
0x18000ca65  jmp     short loc_18000CA6A
0x18000ca67  mov     rax, rcx
0x18000ca6a  lea     r8, [rax+1]
0x18000ca6e  xor     eax, eax
0x18000ca70  cmp     [r14], rax
0x18000ca73  cmovz   r8, rax
0x18000ca77  mov     [r14+10h], r8
0x18000ca7b  jmp     loc_18000C8E4
0x18000ca80  xor     eax, eax
0x18000ca82  mov     [rdx], ax
0x18000ca85  jmp     loc_18000C983
0x18000ca8a  xor     eax, eax
0x18000ca8c  mov     [rdx], ax
0x18000ca8f  jmp     loc_18000C983
```

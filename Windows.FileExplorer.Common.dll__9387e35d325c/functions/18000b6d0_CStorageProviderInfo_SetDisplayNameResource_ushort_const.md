# CStorageProviderInfo::SetDisplayNameResource(ushort const *)

- ea: `0x18000b6d0`
- end: `0x18000b8b2`
- name: `?SetDisplayNameResource@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `482`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b6d0`
- `0x18000b9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b83f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b83f`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetDisplayNameResource(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  char *v2; // r14
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  _WORD *v8; // rax
  int v9; // r8d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rax
  unsigned __int64 v14; // rsi
  LPVOID v15; // rax

  v2 = (char *)this + 120;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 120);
    return 0;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    return 2147942934LL;
  v7 = *((_QWORD *)this + 17);
  if ( v7 == -1 )
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
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)v2 + 2) = v7;
  }
  if ( v7 )
  {
    v9 = 0;
    if ( v6 <= v7 )
      goto LABEL_11;
    v14 = 2 * v7;
    if ( is_mul_ok(v7, 2u) )
    {
      if ( v7 > 0x800 )
        v14 = v7 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*(LPVOID *)v2, 2 * v14);
      if ( !v15 )
        return 2147942414LL;
      *((_QWORD *)v2 + 2) = v14;
      v9 = 0;
      *(_QWORD *)v2 = v15;
      goto LABEL_12;
    }
    return 2147942934LL;
  }
  if ( !is_mul_ok(v6, 2u) )
    return 2147942934LL;
  v8 = CoTaskMemAlloc(2 * v6);
  if ( v8 )
  {
    *((_QWORD *)v2 + 2) = v6;
    v9 = 0;
    *(_QWORD *)v2 = v8;
    *v8 = 0;
LABEL_12:
    if ( v5 != -1 )
    {
      v10 = *(_WORD **)v2;
      if ( v6 > 0x7FFFFFFF || v5 > 0x7FFFFFFE )
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
    return (unsigned int)v9;
  }
  v9 = -2147024882;
LABEL_11:
  if ( v9 >= 0 )
    goto LABEL_12;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b6d0  push    rbx
0x18000b6d2  push    r14
0x18000b6d4  push    r15
0x18000b6d6  sub     rsp, 20h
0x18000b6da  lea     r14, [rcx+78h]
0x18000b6de  mov     rbx, rdx
0x18000b6e1  test    rdx, rdx
0x18000b6e4  jz      loc_18000B7F2
0x18000b6ea  mov     [rsp+38h+arg_8], rbp
0x18000b6ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b6f6  mov     rbp, rax
0x18000b6f9  mov     [rsp+38h+arg_18], rdi
0x18000b6fe  xchg    ax, ax
0x18000b700  inc     rbp
0x18000b703  cmp     word ptr [rdx+rbp*2], 0
0x18000b708  jnz     short loc_18000B700
0x18000b70a  lea     rdi, [rbp+1]
0x18000b70e  cmp     rdi, rbp
0x18000b711  jb      loc_18000B7E4
0x18000b717  mov     rcx, [r14+10h]
0x18000b71b  xor     r15d, r15d
0x18000b71e  cmp     rcx, rax
0x18000b721  jz      loc_18000B86C
0x18000b727  mov     [rsp+38h+arg_10], rsi
0x18000b72c  test    rcx, rcx
0x18000b72f  jnz     loc_18000B80A
0x18000b735  mov     eax, 2
0x18000b73a  mul     rdi
0x18000b73d  test    rdx, rdx
0x18000b740  jnz     loc_18000B7EB
0x18000b746  mov     rcx, rax; cb
0x18000b749  call    cs:__imp_CoTaskMemAlloc
0x18000b74f  test    rax, rax
0x18000b752  jz      short loc_18000B764
0x18000b754  mov     [r14+10h], rdi
0x18000b758  mov     r8d, r15d
0x18000b75b  mov     [r14], rax
0x18000b75e  mov     [rax], r15w
0x18000b762  jmp     short loc_18000B76F
0x18000b764  mov     r8d, 8007000Eh
0x18000b76a  test    r8d, r8d
0x18000b76d  js      short loc_18000B7C8
0x18000b76f  test    rdi, rdi
0x18000b772  jz      short loc_18000B7C4
0x18000b774  mov     rdx, [r14]
0x18000b777  cmp     rdi, 7FFFFFFFh
0x18000b77e  ja      loc_18000B8A9
0x18000b784  cmp     rbp, 7FFFFFFEh
0x18000b78b  ja      loc_18000B8A9
0x18000b791  mov     rcx, rbp
0x18000b794  test    rcx, rcx
0x18000b797  jz      short loc_18000B7B5
0x18000b799  movzx   eax, word ptr [rbx]
0x18000b79c  test    ax, ax
0x18000b79f  jz      short loc_18000B7B5
0x18000b7a1  mov     [rdx], ax
0x18000b7a4  add     rbx, 2
0x18000b7a8  add     rdx, 2
0x18000b7ac  dec     rcx
0x18000b7af  sub     rdi, 1
0x18000b7b3  jnz     short loc_18000B794
0x18000b7b5  test    rdi, rdi
0x18000b7b8  lea     rax, [rdx-2]
0x18000b7bc  cmovnz  rax, rdx
0x18000b7c0  mov     [rax], r15w
0x18000b7c4  mov     [r14+8], rbp
0x18000b7c8  mov     eax, r8d
0x18000b7cb  mov     rsi, [rsp+38h+arg_10]
0x18000b7d0  mov     rbp, [rsp+38h+arg_8]
0x18000b7d5  mov     rdi, [rsp+38h+arg_18]
0x18000b7da  add     rsp, 20h
0x18000b7de  pop     r15
0x18000b7e0  pop     r14
0x18000b7e2  pop     rbx
0x18000b7e3  retn
0x18000b7e4  mov     eax, 80070216h
0x18000b7e9  jmp     short loc_18000B7D0
0x18000b7eb  mov     eax, 80070216h
0x18000b7f0  jmp     short loc_18000B7CB
0x18000b7f2  xor     r15d, r15d
0x18000b7f5  mov     rcx, r14
0x18000b7f8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000b7fd  mov     eax, r15d
0x18000b800  add     rsp, 20h
0x18000b804  pop     r15
0x18000b806  pop     r14
0x18000b808  pop     rbx
0x18000b809  retn
0x18000b80a  mov     r8d, r15d
0x18000b80d  cmp     rdi, rcx
0x18000b810  jbe     loc_18000B76A
0x18000b816  mov     eax, 2
0x18000b81b  mul     rcx
0x18000b81e  mov     rsi, rax
0x18000b821  test    rdx, rdx
0x18000b824  jnz     short loc_18000B7EB
0x18000b826  sub     rax, rcx
0x18000b829  cmp     rax, 800h
0x18000b82f  ja      short loc_18000B854
0x18000b831  mov     rcx, [r14]; pv
0x18000b834  cmp     rdi, rsi
0x18000b837  cmova   rsi, rdi
0x18000b83b  lea     rdx, [rsi+rsi]; cb
0x18000b83f  call    cs:__imp_CoTaskMemRealloc
0x18000b845  test    rax, rax
0x18000b848  jnz     short loc_18000B85D
0x18000b84a  mov     eax, 8007000Eh
0x18000b84f  jmp     loc_18000B7CB
0x18000b854  lea     rsi, [rcx+800h]
0x18000b85b  jmp     short loc_18000B831
0x18000b85d  mov     [r14+10h], rsi
0x18000b861  mov     r8d, r15d
0x18000b864  mov     [r14], rax
0x18000b867  jmp     loc_18000B76F
0x18000b86c  mov     rcx, [r14+8]
0x18000b870  cmp     rcx, rax
0x18000b873  jnz     short loc_18000B892
0x18000b875  mov     rcx, [r14]
0x18000b878  test    rcx, rcx
0x18000b87b  jnz     short loc_18000B882
0x18000b87d  mov     rax, r15
0x18000b880  jmp     short loc_18000B88C
0x18000b882  inc     rax
0x18000b885  cmp     [rcx+rax*2], r15w
0x18000b88a  jnz     short loc_18000B882
0x18000b88c  mov     [r14+8], rax
0x18000b890  jmp     short loc_18000B895
0x18000b892  mov     rax, rcx
0x18000b895  cmp     [r14], r15
0x18000b898  lea     rcx, [rax+1]
0x18000b89c  cmovz   rcx, r15
0x18000b8a0  mov     [r14+10h], rcx
0x18000b8a4  jmp     loc_18000B727
0x18000b8a9  mov     [rdx], r15w
0x18000b8ad  jmp     loc_18000B7C4
```

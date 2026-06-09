# CStorageProviderInfo::SetPackageFullName(ushort const *)

- ea: `0x18000aab0`
- end: `0x18000acb2`
- name: `?SetPackageFullName@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `514`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000aab0`
- `0x18000b9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ab26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ab26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000ac11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000ac11`

## string_xrefs

- `0x18000ac27`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetPackageFullName(CStorageProviderInfo *this, const unsigned __int16 *a2)
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

  v2 = (char *)this + 208;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 208);
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
  v7 = *((_QWORD *)this + 28);
  if ( v7 == -1 )
  {
    if ( *((_QWORD *)this + 27) == -1 )
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
      *((_QWORD *)this + 27) = v4;
    }
    else
    {
      v4 = *((_QWORD *)this + 27);
    }
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)this + 28) = v7;
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
        goto LABEL_35;
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
        goto LABEL_35;
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
LABEL_35:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x453,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000aab0  push    rbx
0x18000aab2  push    rbp
0x18000aab3  push    rsi
0x18000aab4  push    rdi
0x18000aab5  push    r14
0x18000aab7  push    r15
0x18000aab9  sub     rsp, 28h
0x18000aabd  lea     r14, [rcx+0D0h]
0x18000aac4  mov     rbx, rdx
0x18000aac7  test    rdx, rdx
0x18000aaca  jz      loc_18000ABC3
0x18000aad0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000aad7  mov     rbp, rax
0x18000aada  nop     word ptr [rax+rax+00h]
0x18000aae0  inc     rbp
0x18000aae3  cmp     word ptr [rdx+rbp*2], 0
0x18000aae8  jnz     short loc_18000AAE0
0x18000aaea  lea     rdi, [rbp+1]
0x18000aaee  cmp     rdi, rbp
0x18000aaf1  jb      loc_18000ABA9
0x18000aaf7  mov     r8, [r14+10h]
0x18000aafb  cmp     r8, rax
0x18000aafe  jz      loc_18000AC60
0x18000ab04  test    r8, r8
0x18000ab07  jnz     loc_18000ABD8
0x18000ab0d  mov     eax, 2
0x18000ab12  mov     [rsp+58h+arg_0], r8
0x18000ab17  mul     rdi
0x18000ab1a  test    rdx, rdx
0x18000ab1d  jnz     loc_18000ABA9
0x18000ab23  mov     rcx, rax; cb
0x18000ab26  call    cs:__imp_CoTaskMemAlloc
0x18000ab2c  test    rax, rax
0x18000ab2f  jz      loc_18000ABCD
0x18000ab35  xor     r15d, r15d
0x18000ab38  mov     [r14+10h], rdi
0x18000ab3c  xor     ecx, ecx
0x18000ab3e  mov     [r14], rax
0x18000ab41  mov     [rax], cx
0x18000ab44  test    r15d, r15d
0x18000ab47  js      loc_18000AC22
0x18000ab4d  test    rdi, rdi
0x18000ab50  jz      short loc_18000ABA3
0x18000ab52  mov     rdx, [r14]
0x18000ab55  cmp     rdi, 7FFFFFFFh
0x18000ab5c  ja      loc_18000AC9E
0x18000ab62  cmp     rbp, 7FFFFFFEh
0x18000ab69  ja      loc_18000ACA8
0x18000ab6f  mov     rcx, rbp
0x18000ab72  test    rcx, rcx
0x18000ab75  jz      short loc_18000AB93
0x18000ab77  movzx   eax, word ptr [rbx]
0x18000ab7a  test    ax, ax
0x18000ab7d  jz      short loc_18000AB93
0x18000ab7f  mov     [rdx], ax
0x18000ab82  add     rbx, 2
0x18000ab86  add     rdx, 2
0x18000ab8a  dec     rcx
0x18000ab8d  sub     rdi, 1
0x18000ab91  jnz     short loc_18000AB72
0x18000ab93  test    rdi, rdi
0x18000ab96  lea     rcx, [rdx-2]
0x18000ab9a  cmovnz  rcx, rdx
0x18000ab9e  xor     eax, eax
0x18000aba0  mov     [rcx], ax
0x18000aba3  mov     [r14+8], rbp
0x18000aba7  jmp     short loc_18000ABAF
0x18000aba9  mov     r15d, 80070216h
0x18000abaf  test    r15d, r15d
0x18000abb2  js      short loc_18000AC22
0x18000abb4  xor     eax, eax
0x18000abb6  add     rsp, 28h
0x18000abba  pop     r15
0x18000abbc  pop     r14
0x18000abbe  pop     rdi
0x18000abbf  pop     rsi
0x18000abc0  pop     rbp
0x18000abc1  pop     rbx
0x18000abc2  retn
0x18000abc3  mov     rcx, r14
0x18000abc6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000abcb  jmp     short loc_18000ABB4
0x18000abcd  mov     r15d, 8007000Eh
0x18000abd3  jmp     loc_18000AB44
0x18000abd8  xor     r15d, r15d
0x18000abdb  cmp     rdi, r8
0x18000abde  jbe     loc_18000AB4D
0x18000abe4  mov     eax, 2
0x18000abe9  mul     r8
0x18000abec  mov     rsi, rax
0x18000abef  test    rdx, rdx
0x18000abf2  jnz     short loc_18000ABA9
0x18000abf4  mov     rcx, rax
0x18000abf7  sub     rcx, r8
0x18000abfa  cmp     rcx, 800h
0x18000ac01  ja      short loc_18000AC4B
0x18000ac03  mov     rcx, [r14]; pv
0x18000ac06  cmp     rdi, rsi
0x18000ac09  cmova   rsi, rdi
0x18000ac0d  lea     rdx, [rsi+rsi]; cb
0x18000ac11  call    cs:__imp_CoTaskMemRealloc
0x18000ac17  test    rax, rax
0x18000ac1a  jnz     short loc_18000AC54
0x18000ac1c  mov     r15d, 8007000Eh
0x18000ac22  mov     rcx, [rsp+58h]; this
0x18000ac27  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000ac2e  mov     r9d, r15d; char *
0x18000ac31  mov     edx, 453h; void *
0x18000ac36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac3b  mov     eax, r15d
0x18000ac3e  add     rsp, 28h
0x18000ac42  pop     r15
0x18000ac44  pop     r14
0x18000ac46  pop     rdi
0x18000ac47  pop     rsi
0x18000ac48  pop     rbp
0x18000ac49  pop     rbx
0x18000ac4a  retn
0x18000ac4b  lea     rsi, [r8+800h]
0x18000ac52  jmp     short loc_18000AC03
0x18000ac54  mov     [r14+10h], rsi
0x18000ac58  mov     [r14], rax
0x18000ac5b  jmp     loc_18000AB4D
0x18000ac60  mov     rcx, [r14+8]
0x18000ac64  cmp     rcx, rax
0x18000ac67  jnz     short loc_18000AC85
0x18000ac69  mov     rcx, [r14]
0x18000ac6c  test    rcx, rcx
0x18000ac6f  jnz     short loc_18000AC75
0x18000ac71  xor     eax, eax
0x18000ac73  jmp     short loc_18000AC7F
0x18000ac75  inc     rax
0x18000ac78  cmp     word ptr [rcx+rax*2], 0
0x18000ac7d  jnz     short loc_18000AC75
0x18000ac7f  mov     [r14+8], rax
0x18000ac83  jmp     short loc_18000AC88
0x18000ac85  mov     rax, rcx
0x18000ac88  lea     r8, [rax+1]
0x18000ac8c  xor     eax, eax
0x18000ac8e  cmp     [r14], rax
0x18000ac91  cmovz   r8, rax
0x18000ac95  mov     [r14+10h], r8
0x18000ac99  jmp     loc_18000AB04
0x18000ac9e  xor     eax, eax
0x18000aca0  mov     [rdx], ax
0x18000aca3  jmp     loc_18000ABA3
0x18000aca8  xor     eax, eax
0x18000acaa  mov     [rdx], ax
0x18000acad  jmp     loc_18000ABA3
```

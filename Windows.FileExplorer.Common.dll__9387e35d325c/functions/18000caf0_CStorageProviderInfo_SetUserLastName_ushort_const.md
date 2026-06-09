# CStorageProviderInfo::SetUserLastName(ushort const *)

- ea: `0x18000caf0`
- end: `0x18000ccf4`
- name: `?SetUserLastName@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `516`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000b9b0`
- `0x18000caf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000cc5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000cc5c`

## string_xrefs

- `0x18000cc7e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetUserLastName(CStorageProviderInfo *this, const unsigned __int16 *a2)
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

  v2 = (char *)this + 328;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 328);
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
  v7 = *((_QWORD *)this + 43);
  if ( v7 == -1 )
  {
    if ( *((_QWORD *)this + 42) == -1 )
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
      *((_QWORD *)this + 42) = v4;
    }
    else
    {
      v4 = *((_QWORD *)this + 42);
    }
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)this + 43) = v7;
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
    (void *)0x4B1,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000caf0  push    rbx
0x18000caf2  push    rbp
0x18000caf3  push    rsi
0x18000caf4  push    rdi
0x18000caf5  push    r14
0x18000caf7  push    r15
0x18000caf9  sub     rsp, 28h
0x18000cafd  lea     r14, [rcx+148h]
0x18000cb04  mov     rbx, rdx
0x18000cb07  test    rdx, rdx
0x18000cb0a  jz      loc_18000CC07
0x18000cb10  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000cb17  mov     rbp, rax
0x18000cb1a  nop     word ptr [rax+rax+00h]
0x18000cb20  inc     rbp
0x18000cb23  cmp     word ptr [rdx+rbp*2], 0
0x18000cb28  jnz     short loc_18000CB20
0x18000cb2a  lea     rdi, [rbp+1]
0x18000cb2e  cmp     rdi, rbp
0x18000cb31  jb      loc_18000CBE9
0x18000cb37  mov     r8, [r14+10h]
0x18000cb3b  cmp     r8, rax
0x18000cb3e  jz      loc_18000CCA2
0x18000cb44  test    r8, r8
0x18000cb47  jnz     loc_18000CC1C
0x18000cb4d  mov     eax, 2
0x18000cb52  mov     [rsp+58h+arg_0], r8
0x18000cb57  mul     rdi
0x18000cb5a  test    rdx, rdx
0x18000cb5d  jnz     loc_18000CBE9
0x18000cb63  mov     rcx, rax; cb
0x18000cb66  call    cs:__imp_CoTaskMemAlloc
0x18000cb6c  test    rax, rax
0x18000cb6f  jz      loc_18000CC11
0x18000cb75  xor     r15d, r15d
0x18000cb78  mov     [r14+10h], rdi
0x18000cb7c  xor     ecx, ecx
0x18000cb7e  mov     [r14], rax
0x18000cb81  mov     [rax], cx
0x18000cb84  test    r15d, r15d
0x18000cb87  js      loc_18000CC79
0x18000cb8d  test    rdi, rdi
0x18000cb90  jz      short loc_18000CBE3
0x18000cb92  mov     rdx, [r14]
0x18000cb95  cmp     rdi, 7FFFFFFFh
0x18000cb9c  ja      loc_18000CCE0
0x18000cba2  cmp     rbp, 7FFFFFFEh
0x18000cba9  ja      loc_18000CCEA
0x18000cbaf  mov     rcx, rbp
0x18000cbb2  test    rcx, rcx
0x18000cbb5  jz      short loc_18000CBD3
0x18000cbb7  movzx   eax, word ptr [rbx]
0x18000cbba  test    ax, ax
0x18000cbbd  jz      short loc_18000CBD3
0x18000cbbf  mov     [rdx], ax
0x18000cbc2  add     rbx, 2
0x18000cbc6  add     rdx, 2
0x18000cbca  dec     rcx
0x18000cbcd  sub     rdi, 1
0x18000cbd1  jnz     short loc_18000CBB2
0x18000cbd3  test    rdi, rdi
0x18000cbd6  lea     rcx, [rdx-2]
0x18000cbda  cmovnz  rcx, rdx
0x18000cbde  xor     eax, eax
0x18000cbe0  mov     [rcx], ax
0x18000cbe3  mov     [r14+8], rbp
0x18000cbe7  jmp     short loc_18000CBEF
0x18000cbe9  mov     r15d, 80070216h
0x18000cbef  test    r15d, r15d
0x18000cbf2  js      loc_18000CC79
0x18000cbf8  xor     eax, eax
0x18000cbfa  add     rsp, 28h
0x18000cbfe  pop     r15
0x18000cc00  pop     r14
0x18000cc02  pop     rdi
0x18000cc03  pop     rsi
0x18000cc04  pop     rbp
0x18000cc05  pop     rbx
0x18000cc06  retn
0x18000cc07  mov     rcx, r14
0x18000cc0a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000cc0f  jmp     short loc_18000CBF8
0x18000cc11  mov     r15d, 8007000Eh
0x18000cc17  jmp     loc_18000CB84
0x18000cc1c  xor     r15d, r15d
0x18000cc1f  cmp     rdi, r8
0x18000cc22  jbe     loc_18000CB8D
0x18000cc28  mov     eax, 2
0x18000cc2d  mul     r8
0x18000cc30  mov     rsi, rax
0x18000cc33  test    rdx, rdx
0x18000cc36  jnz     short loc_18000CBE9
0x18000cc38  mov     rcx, rax
0x18000cc3b  sub     rcx, r8
0x18000cc3e  cmp     rcx, 800h
0x18000cc45  jbe     short loc_18000CC4E
0x18000cc47  lea     rsi, [r8+800h]
0x18000cc4e  mov     rcx, [r14]; pv
0x18000cc51  cmp     rdi, rsi
0x18000cc54  cmova   rsi, rdi
0x18000cc58  lea     rdx, [rsi+rsi]; cb
0x18000cc5c  call    cs:__imp_CoTaskMemRealloc
0x18000cc62  test    rax, rax
0x18000cc65  jz      short loc_18000CC73
0x18000cc67  mov     [r14+10h], rsi
0x18000cc6b  mov     [r14], rax
0x18000cc6e  jmp     loc_18000CB8D
0x18000cc73  mov     r15d, 8007000Eh
0x18000cc79  mov     rcx, [rsp+58h]; this
0x18000cc7e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000cc85  mov     r9d, r15d; char *
0x18000cc88  mov     edx, 4B1h; void *
0x18000cc8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc92  mov     eax, r15d
0x18000cc95  add     rsp, 28h
0x18000cc99  pop     r15
0x18000cc9b  pop     r14
0x18000cc9d  pop     rdi
0x18000cc9e  pop     rsi
0x18000cc9f  pop     rbp
0x18000cca0  pop     rbx
0x18000cca1  retn
0x18000cca2  mov     rcx, [r14+8]
0x18000cca6  cmp     rcx, rax
0x18000cca9  jnz     short loc_18000CCC7
0x18000ccab  mov     rcx, [r14]
0x18000ccae  test    rcx, rcx
0x18000ccb1  jnz     short loc_18000CCB7
0x18000ccb3  xor     eax, eax
0x18000ccb5  jmp     short loc_18000CCC1
0x18000ccb7  inc     rax
0x18000ccba  cmp     word ptr [rcx+rax*2], 0
0x18000ccbf  jnz     short loc_18000CCB7
0x18000ccc1  mov     [r14+8], rax
0x18000ccc5  jmp     short loc_18000CCCA
0x18000ccc7  mov     rax, rcx
0x18000ccca  lea     r8, [rax+1]
0x18000ccce  xor     eax, eax
0x18000ccd0  cmp     [r14], rax
0x18000ccd3  cmovz   r8, rax
0x18000ccd7  mov     [r14+10h], r8
0x18000ccdb  jmp     loc_18000CB44
0x18000cce0  xor     eax, eax
0x18000cce2  mov     [rdx], ax
0x18000cce5  jmp     loc_18000CBE3
0x18000ccea  xor     eax, eax
0x18000ccec  mov     [rdx], ax
0x18000ccef  jmp     loc_18000CBE3
```

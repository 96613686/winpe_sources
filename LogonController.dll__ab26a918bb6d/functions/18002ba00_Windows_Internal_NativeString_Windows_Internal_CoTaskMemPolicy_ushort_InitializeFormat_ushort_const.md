# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x18002ba00`
- end: `0x18002bc13`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `531`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b860`
- `0x180061abc`
- `0x180062110`
- `0x180067e38`

## callees

- `0x18002ba00`
- `0x18002bc20`
- `0x1800478e4`
- `0x18006cadc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18002babe`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18002babe`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x18002bb20`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x18002bb20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bb87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bb87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002ba9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002ba9f`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v4; // rcx
  int v5; // ebx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // r14
  LPVOID v9; // rax
  unsigned __int64 v10; // rsi
  wchar_t *v11; // r14
  size_t v12; // rsi
  int v13; // eax
  int v14; // ecx
  unsigned __int64 v15; // rax
  _WORD *v17; // rax
  __int64 v18; // [rsp+20h] [rbp-48h] BYREF
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  v18 = 0;
  v4 = 32;
  v5 = -2147024809;
  while ( 1 )
  {
    v6 = v4 + 1;
    if ( v4 + 1 < v4 )
    {
LABEL_25:
      v5 = -2147024362;
      goto LABEL_26;
    }
    v7 = *(_QWORD *)(a1 + 16);
    if ( v7 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
      if ( *(_QWORD *)a1 )
        v7 = *(_QWORD *)(a1 + 8) + 1LL;
      else
        v7 = 0;
      *(_QWORD *)(a1 + 16) = v7;
    }
    if ( v7 )
    {
      if ( v6 > v7 )
      {
        v18 = 0;
        v8 = 2 * v7;
        if ( !is_mul_ok(v7, 2u) )
          goto LABEL_25;
        if ( v7 > 0x800 )
          v8 = v7 + 2048;
        if ( v6 > v8 )
          v8 = v6;
        v9 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v8);
        if ( !v9 )
          goto LABEL_32;
        *(_QWORD *)(a1 + 16) = v8;
        *(_QWORD *)a1 = v9;
      }
    }
    else
    {
      v18 = 0;
      if ( !is_mul_ok(v6, 2u) )
        goto LABEL_25;
      v17 = CoTaskMemAlloc(2 * v6);
      if ( !v17 )
      {
LABEL_32:
        v5 = -2147024882;
        goto LABEL_26;
      }
      *(_QWORD *)(a1 + 16) = v6;
      *(_QWORD *)a1 = v17;
      *v17 = 0;
    }
    v10 = *(_QWORD *)(a1 + 16);
    v11 = *(wchar_t **)a1;
    _o__set_errno(0);
    if ( v10 )
    {
      if ( v10 > 0x7FFFFFFF )
      {
        *v11 = 0;
        goto LABEL_26;
      }
      v12 = v10 - 1;
      v13 = vsnwprintf(v11, v12, a2, va);
      if ( v13 < 0 || v13 > v12 )
      {
        v11[v12] = 0;
        v14 = -2147024774;
      }
      else
      {
        v14 = 0;
        if ( v13 == v12 )
          v11[v12] = 0;
      }
    }
    else
    {
      v14 = -2147024809;
    }
    if ( v14 != -2147024774 )
      break;
    LODWORD(v18) = 0;
    _o__get_errno(&v18);
    if ( (_DWORD)v18 == 22 )
      goto LABEL_26;
    v15 = *(_QWORD *)(a1 + 16);
    v4 = v15 + 32;
    if ( v15 + 32 < v15 )
    {
      v5 = -2147024362;
LABEL_23:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
      return (unsigned int)v5;
    }
  }
  v5 = v14;
LABEL_26:
  if ( v5 < 0 )
    goto LABEL_23;
  *(_QWORD *)(a1 + 8) = -1;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002ba00  mov     rax, rsp
0x18002ba03  mov     [rax+10h], rdx
0x18002ba07  mov     [rax+18h], r8
0x18002ba0b  mov     [rax+20h], r9
0x18002ba0f  push    rbx
0x18002ba10  push    rbp
0x18002ba11  push    rsi
0x18002ba12  push    rdi
0x18002ba13  push    r12
0x18002ba15  push    r15
0x18002ba17  sub     rsp, 38h
0x18002ba1b  xor     r15d, r15d
0x18002ba1e  mov     [rax-38h], r14
0x18002ba22  mov     rdi, rcx
0x18002ba25  mov     [rax-48h], r15
0x18002ba29  mov     rbp, rdx
0x18002ba2c  lea     r12, [rax+18h]
0x18002ba30  mov     ecx, 20h ; ' '
0x18002ba35  mov     ebx, 80070057h
0x18002ba3a  lea     rsi, [rcx+1]
0x18002ba3e  cmp     rsi, rcx
0x18002ba41  jb      loc_18002BB5F
0x18002ba47  mov     r8, [rdi+10h]
0x18002ba4b  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002ba4f  jz      loc_18002BBC2
0x18002ba55  test    r8, r8
0x18002ba58  jz      loc_18002BB72
0x18002ba5e  cmp     rsi, r8
0x18002ba61  jbe     short loc_18002BAB5
0x18002ba63  mov     eax, 2
0x18002ba68  mov     [rsp+68h+var_48], r15
0x18002ba6d  mul     r8
0x18002ba70  mov     r14, rax
0x18002ba73  test    rdx, rdx
0x18002ba76  jnz     loc_18002BB5F
0x18002ba7c  mov     rcx, rax
0x18002ba7f  sub     rcx, r8
0x18002ba82  cmp     rcx, 800h
0x18002ba89  ja      loc_18002BBE4
0x18002ba8f  cmp     rsi, r14
0x18002ba92  ja      loc_18002BBF0
0x18002ba98  mov     rcx, [rdi]; pv
0x18002ba9b  lea     rdx, [r14+r14]; cb
0x18002ba9f  call    cs:__imp_CoTaskMemRealloc
0x18002baa5  test    rax, rax
0x18002baa8  jz      loc_18002BBBB
0x18002baae  mov     [rdi+10h], r14
0x18002bab2  mov     [rdi], rax
0x18002bab5  mov     rsi, [rdi+10h]
0x18002bab9  xor     ecx, ecx
0x18002babb  mov     r14, [rdi]
0x18002babe  call    cs:__imp__o__set_errno
0x18002bac4  test    rsi, rsi
0x18002bac7  jz      loc_18002BBF8
0x18002bacd  cmp     rsi, 7FFFFFFFh
0x18002bad4  ja      loc_18002BC03
0x18002bada  dec     rsi
0x18002badd  mov     r9, r12; Args
0x18002bae0  mov     rdx, rsi; BufferCount
0x18002bae3  mov     r8, rbp; Format
0x18002bae6  mov     rcx, r14; Buffer
0x18002bae9  call    _vsnwprintf
0x18002baee  test    eax, eax
0x18002baf0  js      loc_18002BBA2
0x18002baf6  cdqe
0x18002baf8  cmp     rax, rsi
0x18002bafb  ja      loc_18002BBA2
0x18002bb01  mov     ecx, r15d
0x18002bb04  jz      loc_18002BBB1
0x18002bb0a  cmp     ecx, 8007007Ah
0x18002bb10  jnz     loc_18002BC0C
0x18002bb16  lea     rcx, [rsp+68h+var_48]
0x18002bb1b  mov     dword ptr [rsp+68h+var_48], r15d
0x18002bb20  call    cs:__imp__o__get_errno
0x18002bb26  cmp     dword ptr [rsp+68h+var_48], 16h
0x18002bb2b  jz      short loc_18002BB64
0x18002bb2d  mov     rax, [rdi+10h]
0x18002bb31  lea     rcx, [rax+20h]
0x18002bb35  cmp     rcx, rax
0x18002bb38  jnb     loc_18002BA3A
0x18002bb3e  mov     ebx, 80070216h
0x18002bb43  mov     rcx, rdi
0x18002bb46  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002bb4b  mov     r14, [rsp+68h+var_38]
0x18002bb50  mov     eax, ebx
0x18002bb52  add     rsp, 38h
0x18002bb56  pop     r15
0x18002bb58  pop     r12
0x18002bb5a  pop     rdi
0x18002bb5b  pop     rsi
0x18002bb5c  pop     rbp
0x18002bb5d  pop     rbx
0x18002bb5e  retn
0x18002bb5f  mov     ebx, 80070216h
0x18002bb64  test    ebx, ebx
0x18002bb66  js      short loc_18002BB43
0x18002bb68  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18002bb70  jmp     short loc_18002BB4B
0x18002bb72  mov     eax, 2
0x18002bb77  mov     [rsp+68h+var_48], r15
0x18002bb7c  mul     rsi
0x18002bb7f  test    rdx, rdx
0x18002bb82  jnz     short loc_18002BB5F
0x18002bb84  mov     rcx, rax; cb
0x18002bb87  call    cs:__imp_CoTaskMemAlloc
0x18002bb8d  test    rax, rax
0x18002bb90  jz      short loc_18002BBBB
0x18002bb92  mov     [rdi+10h], rsi
0x18002bb96  mov     [rdi], rax
0x18002bb99  mov     [rax], r15w
0x18002bb9d  jmp     loc_18002BAB5
0x18002bba2  mov     [r14+rsi*2], r15w
0x18002bba7  mov     ecx, 8007007Ah
0x18002bbac  jmp     loc_18002BB0A
0x18002bbb1  mov     [r14+rsi*2], r15w
0x18002bbb6  jmp     loc_18002BB0A
0x18002bbbb  mov     ebx, 8007000Eh
0x18002bbc0  jmp     short loc_18002BB64
0x18002bbc2  mov     rcx, rdi
0x18002bbc5  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18002bbca  cmp     [rdi], r15
0x18002bbcd  jz      short loc_18002BBD8
0x18002bbcf  mov     r8, [rdi+8]
0x18002bbd3  inc     r8
0x18002bbd6  jmp     short loc_18002BBDB
0x18002bbd8  mov     r8, r15
0x18002bbdb  mov     [rdi+10h], r8
0x18002bbdf  jmp     loc_18002BA55
0x18002bbe4  lea     r14, [r8+800h]
0x18002bbeb  jmp     loc_18002BA8F
0x18002bbf0  mov     r14, rsi
0x18002bbf3  jmp     loc_18002BA98
0x18002bbf8  mov     ecx, ebx
0x18002bbfa  test    rsi, rsi
0x18002bbfd  jz      loc_18002BB0A
0x18002bc03  mov     [r14], r15w
0x18002bc07  jmp     loc_18002BB64
0x18002bc0c  mov     ebx, ecx
0x18002bc0e  jmp     loc_18002BB64
```

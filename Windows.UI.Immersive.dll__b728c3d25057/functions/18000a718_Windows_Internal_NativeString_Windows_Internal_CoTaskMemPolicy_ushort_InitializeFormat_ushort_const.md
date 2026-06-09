# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x18000a718`
- end: `0x18000a908`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `496`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009f0c`
- `0x18001a530`
- `0x18008cb04`
- `0x1800918f4`

## callees

- `0x18000a718`
- `0x18000a910`
- `0x180051530`
- `0x18005e5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18000a83e`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18000a83e`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x18000a8b2`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x18000a8b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a79b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a79b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000a81a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000a81a`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r8
  _WORD *v7; // rax
  int v8; // ebx
  unsigned __int64 v10; // rbx
  LPVOID v11; // rax
  unsigned __int64 v12; // rsi
  wchar_t *v13; // r14
  size_t v14; // rsi
  int v15; // eax
  unsigned __int64 v16; // rax
  _QWORD v17[7]; // [rsp+20h] [rbp-38h] BYREF
  va_list Args; // [rsp+70h] [rbp+18h] BYREF

  va_start(Args, a2);
  v17[0] = 0;
  v3 = 32;
  while ( 1 )
  {
    v5 = v3 + 1;
    if ( v3 + 1 < v3 )
    {
LABEL_39:
      v8 = -2147024362;
      goto LABEL_40;
    }
    v6 = *(_QWORD *)(a1 + 16);
    if ( v6 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
      if ( *(_QWORD *)a1 )
        v6 = *(_QWORD *)(a1 + 8) + 1LL;
      else
        v6 = 0;
      *(_QWORD *)(a1 + 16) = v6;
    }
    if ( v6 )
    {
      if ( v5 > v6 )
      {
        v17[0] = 0;
        v10 = 2 * v6;
        if ( !is_mul_ok(v6, 2u) )
          goto LABEL_39;
        if ( v6 > 0x800 )
          v10 = v6 + 2048;
        if ( v5 > v10 )
          v10 = v5;
        v11 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v10);
        if ( !v11 )
        {
          v8 = -2147024882;
          goto LABEL_40;
        }
        *(_QWORD *)(a1 + 16) = v10;
        *(_QWORD *)a1 = v11;
      }
    }
    else
    {
      v17[0] = 0;
      if ( !is_mul_ok(v5, 2u) )
        goto LABEL_39;
      v7 = CoTaskMemAlloc(2 * v5);
      if ( v7 )
      {
        v8 = 0;
        *(_QWORD *)(a1 + 16) = v5;
        *(_QWORD *)a1 = v7;
        *v7 = 0;
      }
      else
      {
        v8 = -2147024882;
      }
      if ( v8 < 0 )
        goto LABEL_14;
    }
    v12 = *(_QWORD *)(a1 + 16);
    v13 = *(wchar_t **)a1;
    _o__set_errno(0);
    if ( v12 )
      break;
    v8 = -2147024809;
LABEL_32:
    if ( v8 != -2147024774 )
      goto LABEL_40;
    LODWORD(v17[0]) = 0;
    _o__get_errno(v17);
    if ( LODWORD(v17[0]) == 22 )
      goto LABEL_38;
    v16 = *(_QWORD *)(a1 + 16);
    v3 = v16 + 32;
    if ( v16 + 32 < v16 )
    {
      v8 = -2147024362;
LABEL_14:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
      return (unsigned int)v8;
    }
  }
  if ( v12 <= 0x7FFFFFFF )
  {
    v14 = v12 - 1;
    v15 = vsnwprintf(v13, v14, a2, Args);
    if ( v15 < 0 || v15 > v14 )
    {
      v8 = -2147024774;
      v13[v14] = 0;
    }
    else
    {
      v8 = 0;
      if ( v15 == v14 )
        v13[v14] = 0;
    }
    goto LABEL_32;
  }
  *v13 = 0;
LABEL_38:
  v8 = -2147024809;
LABEL_40:
  if ( v8 < 0 )
    goto LABEL_14;
  *(_QWORD *)(a1 + 8) = -1;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a718  mov     rax, rsp
0x18000a71b  mov     [rax+10h], rdx
0x18000a71f  mov     [rax+18h], r8
0x18000a723  mov     [rax+20h], r9
0x18000a727  push    rbx
0x18000a728  push    rbp
0x18000a729  push    rsi
0x18000a72a  push    rdi
0x18000a72b  push    r14
0x18000a72d  sub     rsp, 30h
0x18000a731  mov     rdi, rcx
0x18000a734  mov     qword ptr [rax-38h], 0
0x18000a73c  mov     ecx, 20h ; ' '
0x18000a741  mov     rbp, rdx
0x18000a744  lea     rsi, [rcx+1]
0x18000a748  lea     rbx, [rsp+58h+Args]
0x18000a74d  cmp     rsi, rcx
0x18000a750  jb      loc_18000A8EE
0x18000a756  mov     r8, [rdi+10h]
0x18000a75a  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a75e  jnz     short loc_18000A77E
0x18000a760  mov     rcx, rdi
0x18000a763  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000a768  cmp     qword ptr [rdi], 0
0x18000a76c  jz      short loc_18000A777
0x18000a76e  mov     r8, [rdi+8]
0x18000a772  inc     r8
0x18000a775  jmp     short loc_18000A77A
0x18000a777  xor     r8d, r8d
0x18000a77a  mov     [rdi+10h], r8
0x18000a77e  test    r8, r8
0x18000a781  jnz     short loc_18000A7D4
0x18000a783  lea     eax, [r8+2]
0x18000a787  mov     [rsp+58h+var_38], r8
0x18000a78c  mul     rsi
0x18000a78f  test    rdx, rdx
0x18000a792  jnz     loc_18000A8EE
0x18000a798  mov     rcx, rax; cb
0x18000a79b  call    cs:__imp_CoTaskMemAlloc
0x18000a7a1  test    rax, rax
0x18000a7a4  jz      short loc_18000A7B6
0x18000a7a6  xor     ebx, ebx
0x18000a7a8  mov     [rdi+10h], rsi
0x18000a7ac  xor     ecx, ecx
0x18000a7ae  mov     [rdi], rax
0x18000a7b1  mov     [rax], cx
0x18000a7b4  jmp     short loc_18000A7BB
0x18000a7b6  mov     ebx, 8007000Eh
0x18000a7bb  test    ebx, ebx
0x18000a7bd  jns     short loc_18000A830
0x18000a7bf  mov     rcx, rdi
0x18000a7c2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a7c7  mov     eax, ebx
0x18000a7c9  add     rsp, 30h
0x18000a7cd  pop     r14
0x18000a7cf  pop     rdi
0x18000a7d0  pop     rsi
0x18000a7d1  pop     rbp
0x18000a7d2  pop     rbx
0x18000a7d3  retn
0x18000a7d4  cmp     rsi, r8
0x18000a7d7  jbe     short loc_18000A835
0x18000a7d9  mov     eax, 2
0x18000a7de  mov     [rsp+58h+var_38], 0
0x18000a7e7  mul     r8
0x18000a7ea  mov     rbx, rax
0x18000a7ed  test    rdx, rdx
0x18000a7f0  jnz     loc_18000A8EE
0x18000a7f6  mov     rcx, rax
0x18000a7f9  sub     rcx, r8
0x18000a7fc  cmp     rcx, 800h
0x18000a803  jbe     short loc_18000A80C
0x18000a805  lea     rbx, [r8+800h]
0x18000a80c  mov     rcx, [rdi]; pv
0x18000a80f  cmp     rsi, rbx
0x18000a812  cmova   rbx, rsi
0x18000a816  lea     rdx, [rbx+rbx]; cb
0x18000a81a  call    cs:__imp_CoTaskMemRealloc
0x18000a820  test    rax, rax
0x18000a823  jz      loc_18000A8DA
0x18000a829  mov     [rdi+10h], rbx
0x18000a82d  mov     [rdi], rax
0x18000a830  lea     rbx, [rsp+58h+Args]
0x18000a835  mov     rsi, [rdi+10h]
0x18000a839  xor     ecx, ecx
0x18000a83b  mov     r14, [rdi]
0x18000a83e  call    cs:__imp__o__set_errno
0x18000a844  test    rsi, rsi
0x18000a847  jz      short loc_18000A893
0x18000a849  cmp     rsi, 7FFFFFFFh
0x18000a850  ja      loc_18000A8E1
0x18000a856  dec     rsi
0x18000a859  mov     r9, rbx; Args
0x18000a85c  mov     rdx, rsi; BufferCount
0x18000a85f  mov     r8, rbp; Format
0x18000a862  mov     rcx, r14; Buffer
0x18000a865  call    _vsnwprintf
0x18000a86a  test    eax, eax
0x18000a86c  js      short loc_18000A885
0x18000a86e  cdqe
0x18000a870  cmp     rax, rsi
0x18000a873  ja      short loc_18000A885
0x18000a875  xor     ebx, ebx
0x18000a877  cmp     rax, rsi
0x18000a87a  jnz     short loc_18000A89D
0x18000a87c  xor     eax, eax
0x18000a87e  mov     [r14+rsi*2], ax
0x18000a883  jmp     short loc_18000A89D
0x18000a885  xor     eax, eax
0x18000a887  mov     ebx, 8007007Ah
0x18000a88c  mov     [r14+rsi*2], ax
0x18000a891  jmp     short loc_18000A89D
0x18000a893  mov     ebx, 80070057h
0x18000a898  test    rsi, rsi
0x18000a89b  jnz     short loc_18000A8E1
0x18000a89d  cmp     ebx, 8007007Ah
0x18000a8a3  jnz     short loc_18000A8F3
0x18000a8a5  lea     rcx, [rsp+58h+var_38]
0x18000a8aa  mov     dword ptr [rsp+58h+var_38], 0
0x18000a8b2  call    cs:__imp__o__get_errno
0x18000a8b8  cmp     dword ptr [rsp+58h+var_38], 16h
0x18000a8bd  jz      short loc_18000A8E7
0x18000a8bf  mov     rax, [rdi+10h]
0x18000a8c3  lea     rcx, [rax+20h]
0x18000a8c7  cmp     rcx, rax
0x18000a8ca  jnb     loc_18000A744
0x18000a8d0  mov     ebx, 80070216h
0x18000a8d5  jmp     loc_18000A7BF
0x18000a8da  mov     ebx, 8007000Eh
0x18000a8df  jmp     short loc_18000A8F3
0x18000a8e1  xor     eax, eax
0x18000a8e3  mov     [r14], ax
0x18000a8e7  mov     ebx, 80070057h
0x18000a8ec  jmp     short loc_18000A8F3
0x18000a8ee  mov     ebx, 80070216h
0x18000a8f3  test    ebx, ebx
0x18000a8f5  js      loc_18000A7BF
0x18000a8fb  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18000a903  jmp     loc_18000A7C7
```

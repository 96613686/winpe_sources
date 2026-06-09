# GetCardProperty

- ea: `0x180027d0c`
- end: `0x180027ea2`
- name: `GetCardProperty`
- size: `406`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ef0c`
- `0x180022304`
- `0x180025a40`

## callees

- `0x18000de80`
- `0x180019430`
- `0x180027d0c`
- `0x18002cf6a`
- `0x18002e010`

## string_xrefs

- `0x180027dc2`: `Read Only Mode`
- `0x180027dd9`: `Cache Mode`

## pseudocode

```c
__int64 __fastcall GetCardProperty(__int64 a1, const wchar_t *a2, _QWORD *a3, __int64 a4, int a5)
{
  size_t v9; // rbx
  _DWORD *v10; // rax
  void *v11; // rdi
  unsigned int v12; // ebx
  size_t v13; // rcx
  _DWORD *v14; // rax

  if ( !wcscmp_0(a2, L"Free Space") )
  {
    v9 = 16;
    goto LABEL_3;
  }
  if ( !wcscmp_0(a2, L"Capabilities") )
  {
    v9 = 12;
    goto LABEL_3;
  }
  if ( !wcscmp_0(a2, L"Key Sizes") )
  {
    v9 = 20;
LABEL_3:
    v10 = MIDL_user_allocate(v9);
    v11 = v10;
    if ( v10 )
    {
      *v10 = 1;
      goto LABEL_5;
    }
    return 14;
  }
  if ( !wcscmp_0(a2, L"Read Only Mode")
    || !wcscmp_0(a2, L"Cache Mode")
    || !wcscmp_0(a2, L"PIN List")
    || !wcscmp_0(a2, L"Supports Windows x.509 Enrollment") )
  {
    v13 = 4;
    LODWORD(v9) = 4;
  }
  else
  {
    if ( wcscmp_0(a2, L"Card Identifier") )
    {
      if ( wcscmp_0(a2, L"PIN Information") )
        return 160;
      LODWORD(v9) = 36;
      v14 = MIDL_user_allocate(0x24u);
      v11 = v14;
      if ( !v14 )
        return 14;
      *v14 = 6;
      goto LABEL_5;
    }
    LODWORD(v9) = 16;
    v13 = 16;
  }
  v11 = MIDL_user_allocate(v13);
  if ( !v11 )
    return 14;
LABEL_5:
  v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, void *, _QWORD, __int64, int))(a1 + 400))(
          a1,
          a2,
          v11,
          (unsigned int)v9,
          a4,
          a5);
  if ( v12 )
  {
    if ( v11 )
      CspFreeH(v11);
  }
  else
  {
    *a3 = v11;
  }
  return v12;
}

```

## disassembly

```asm
0x180027d0c  push    rbx
0x180027d0e  push    rbp
0x180027d0f  push    rsi
0x180027d10  push    rdi
0x180027d11  push    r14
0x180027d13  push    r15
0x180027d15  sub     rsp, 48h
0x180027d19  mov     rsi, rdx
0x180027d1c  mov     rbp, rcx
0x180027d1f  mov     rcx, rsi; String1
0x180027d22  lea     rdx, aFreeSpace; "Free Space"
0x180027d29  mov     r15, r9
0x180027d2c  mov     r14, r8
0x180027d2f  call    wcscmp_0
0x180027d34  test    eax, eax
0x180027d36  jnz     short loc_180027D8F
0x180027d38  lea     ebx, [rax+10h]
0x180027d3b  mov     rcx, rbx; size
0x180027d3e  call    MIDL_user_allocate
0x180027d43  mov     rdi, rax
0x180027d46  test    rax, rax
0x180027d49  jz      loc_180027E3F
0x180027d4f  mov     dword ptr [rax], 1
0x180027d55  mov     ecx, [rsp+78h+arg_20]
0x180027d5c  mov     r9d, ebx
0x180027d5f  mov     rax, [rbp+190h]
0x180027d66  mov     r8, rdi
0x180027d69  mov     [rsp+78h+var_50], ecx
0x180027d6d  mov     rdx, rsi
0x180027d70  mov     rcx, rbp
0x180027d73  mov     [rsp+78h+var_58], r15
0x180027d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d7d  mov     ebx, eax
0x180027d7f  test    eax, eax
0x180027d81  jnz     loc_180027E86
0x180027d87  mov     [r14], rdi
0x180027d8a  jmp     loc_180027E93
0x180027d8f  lea     rdx, aCapabilities; "Capabilities"
0x180027d96  mov     rcx, rsi; String1
0x180027d99  call    wcscmp_0
0x180027d9e  test    eax, eax
0x180027da0  jnz     short loc_180027DA7
0x180027da2  lea     ebx, [rax+0Ch]
0x180027da5  jmp     short loc_180027D3B
0x180027da7  lea     rdx, aKeySizes; "Key Sizes"
0x180027dae  mov     rcx, rsi; String1
0x180027db1  call    wcscmp_0
0x180027db6  test    eax, eax
0x180027db8  jnz     short loc_180027DC2
0x180027dba  lea     ebx, [rax+14h]
0x180027dbd  jmp     loc_180027D3B
0x180027dc2  lea     rdx, aReadOnlyMode; "Read Only Mode"
0x180027dc9  mov     rcx, rsi; String1
0x180027dcc  call    wcscmp_0
0x180027dd1  test    eax, eax
0x180027dd3  jz      loc_180027E7D
0x180027dd9  lea     rdx, aCacheMode; "Cache Mode"
0x180027de0  mov     rcx, rsi; String1
0x180027de3  call    wcscmp_0
0x180027de8  test    eax, eax
0x180027dea  jz      loc_180027E7D
0x180027df0  lea     rdx, aPinList; "PIN List"
0x180027df7  mov     rcx, rsi; String1
0x180027dfa  call    wcscmp_0
0x180027dff  test    eax, eax
0x180027e01  jz      short loc_180027E7D
0x180027e03  lea     rdx, aSupportsWindow; "Supports Windows x.509 Enrollment"
0x180027e0a  mov     rcx, rsi; String1
0x180027e0d  call    wcscmp_0
0x180027e12  test    eax, eax
0x180027e14  jz      short loc_180027E7D
0x180027e16  lea     rdx, aCardIdentifier; "Card Identifier"
0x180027e1d  mov     rcx, rsi; String1
0x180027e20  call    wcscmp_0
0x180027e25  test    eax, eax
0x180027e27  jnz     short loc_180027E46
0x180027e29  lea     ebx, [rax+10h]
0x180027e2c  mov     ecx, ebx; size
0x180027e2e  call    MIDL_user_allocate
0x180027e33  mov     rdi, rax
0x180027e36  test    rax, rax
0x180027e39  jnz     loc_180027D55
0x180027e3f  mov     ebx, 0Eh
0x180027e44  jmp     short loc_180027E93
0x180027e46  lea     rdx, aPinInformation; "PIN Information"
0x180027e4d  mov     rcx, rsi; String1
0x180027e50  call    wcscmp_0
0x180027e55  test    eax, eax
0x180027e57  jnz     short loc_180027E76
0x180027e59  lea     ebx, [rax+24h]
0x180027e5c  mov     ecx, ebx; size
0x180027e5e  call    MIDL_user_allocate
0x180027e63  mov     rdi, rax
0x180027e66  test    rax, rax
0x180027e69  jz      short loc_180027E3F
0x180027e6b  mov     dword ptr [rax], 6
0x180027e71  jmp     loc_180027D55
0x180027e76  mov     ebx, 0A0h
0x180027e7b  jmp     short loc_180027E93
0x180027e7d  mov     ecx, 4
0x180027e82  mov     ebx, ecx
0x180027e84  jmp     short loc_180027E2E
0x180027e86  test    rdi, rdi
0x180027e89  jz      short loc_180027E93
0x180027e8b  mov     rcx, rdi
0x180027e8e  call    CspFreeH
0x180027e93  mov     eax, ebx
0x180027e95  add     rsp, 48h
0x180027e99  pop     r15
0x180027e9b  pop     r14
0x180027e9d  pop     rdi
0x180027e9e  pop     rsi
0x180027e9f  pop     rbp
0x180027ea0  pop     rbx
0x180027ea1  retn
```

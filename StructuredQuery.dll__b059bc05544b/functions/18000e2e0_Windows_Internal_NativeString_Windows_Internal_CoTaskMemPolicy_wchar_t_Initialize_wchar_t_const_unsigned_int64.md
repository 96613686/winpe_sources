# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Initialize(wchar_t const *,unsigned __int64)

- ea: `0x18000e2e0`
- end: `0x18000e462`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJPEB_W_K@Z`
- size: `386`
- prototype: `__int64 __fastcall(__int64, _WORD *, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e250`
- `0x180047a98`
- `0x180050e70`

## callees

- `0x18000cda8`
- `0x18000e2e0`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e36f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e36f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180087a5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180087a5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Initialize(
        __int64 a1,
        _WORD *a2,
        unsigned __int64 a3)
{
  _WORD *v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r9
  _WORD *v9; // rax
  int v10; // r15d
  _WORD *v11; // rcx
  unsigned __int64 v12; // rax
  _WORD *v13; // rax
  __int64 v15; // rcx
  __int64 v16; // r9
  unsigned __int64 v17; // r12
  LPVOID v18; // rax
  unsigned __int64 v19; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::~NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>(a1);
    return 0;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( a3 == -1 )
  {
    a3 = v6;
  }
  else if ( a3 < v6 )
  {
    v6 = a3;
  }
  v7 = a3 + 1;
  if ( a3 + 1 < a3 )
    return 2147942934LL;
  v8 = *(_QWORD *)(a1 + 16);
  if ( v8 == -1 )
  {
    v15 = *(_QWORD *)(a1 + 8);
    if ( v15 == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v5;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v5) );
      }
      else
      {
        v5 = 0;
      }
      *(_QWORD *)(a1 + 8) = v5;
    }
    else
    {
      v5 = v15;
    }
    v8 = v5 + 1;
    if ( !*(_QWORD *)a1 )
      v8 = 0;
    *(_QWORD *)(a1 + 16) = v8;
  }
  if ( v8 )
  {
    v10 = 0;
    if ( v7 > v8 )
    {
      v19 = 0;
      v10 = ULongLongMult(v8, 2u, &v19);
      if ( v10 >= 0 )
      {
        v17 = v19;
        if ( v19 - v16 > 0x800 )
          v17 = v16 + 2048;
        if ( v7 > v17 )
          v17 = v7;
        v18 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v17);
        if ( !v18 )
          return 2147942414LL;
        *(_QWORD *)(a1 + 16) = v17;
        *(_QWORD *)a1 = v18;
        goto LABEL_15;
      }
    }
  }
  else
  {
    if ( !is_mul_ok(v7, 2u) )
      return 2147942934LL;
    v9 = CoTaskMemAlloc(2 * v7);
    if ( v9 )
    {
      *(_QWORD *)(a1 + 16) = v7;
      v10 = 0;
      *(_QWORD *)a1 = v9;
      *v9 = 0;
LABEL_15:
      if ( v7 )
      {
        v11 = *(_WORD **)a1;
        if ( v7 > 0x7FFFFFFF || v6 > 0x7FFFFFFE )
        {
          *v11 = 0;
        }
        else
        {
          v12 = v6;
          do
          {
            if ( !v12 )
              break;
            if ( !*v3 )
              break;
            *v11++ = *v3++;
            --v12;
            --v7;
          }
          while ( v7 );
          v13 = v11 - 1;
          if ( v7 )
            v13 = v11;
          *v13 = 0;
        }
      }
      *(_QWORD *)(a1 + 8) = v6;
      return (unsigned int)v10;
    }
    v10 = -2147024882;
  }
  if ( v10 >= 0 )
    goto LABEL_15;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000e2e0  push    rbp
0x18000e2e2  push    rdi
0x18000e2e3  push    r14
0x18000e2e5  sub     rsp, 30h
0x18000e2e9  mov     rdi, rdx
0x18000e2ec  mov     r14, rcx
0x18000e2ef  test    rdx, rdx
0x18000e2f2  jz      loc_18000E457
0x18000e2f8  mov     [rsp+48h+arg_0], rbx
0x18000e2fd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e304  mov     rbx, rax
0x18000e307  mov     [rsp+48h+arg_10], rsi
0x18000e30c  nop     dword ptr [rax+00h]
0x18000e310  inc     rbx
0x18000e313  cmp     word ptr [rdx+rbx*2], 0
0x18000e318  jnz     short loc_18000E310
0x18000e31a  cmp     r8, rax
0x18000e31d  jz      loc_18000E41A
0x18000e323  cmp     r8, rbx
0x18000e326  jb      loc_18000E429
0x18000e32c  lea     rsi, [r8+1]
0x18000e330  cmp     rsi, r8
0x18000e333  jb      loc_18000E413
0x18000e339  mov     r9, [rcx+10h]
0x18000e33d  xor     ebp, ebp
0x18000e33f  cmp     r9, rax
0x18000e342  jz      loc_18000E431
0x18000e348  mov     [rsp+48h+var_20], r12
0x18000e34d  mov     [rsp+48h+var_28], r15
0x18000e352  test    r9, r9
0x18000e355  jnz     loc_180087A08
0x18000e35b  mov     eax, 2
0x18000e360  mul     rsi
0x18000e363  test    rdx, rdx
0x18000e366  jnz     loc_18000E422
0x18000e36c  mov     rcx, rax; cb
0x18000e36f  call    cs:__imp_CoTaskMemAlloc
0x18000e375  test    rax, rax
0x18000e378  jz      short loc_18000E389
0x18000e37a  mov     [r14+10h], rsi
0x18000e37e  mov     r15d, ebp
0x18000e381  mov     [r14], rax
0x18000e384  mov     [rax], bp
0x18000e387  jmp     short loc_18000E394
0x18000e389  mov     r15d, 8007000Eh
0x18000e38f  test    r15d, r15d
0x18000e392  js      short loc_18000E3F3
0x18000e394  test    rsi, rsi
0x18000e397  jz      short loc_18000E3EF
0x18000e399  mov     rcx, [r14]
0x18000e39c  cmp     rsi, 7FFFFFFFh
0x18000e3a3  ja      loc_18000E452
0x18000e3a9  cmp     rbx, 7FFFFFFEh
0x18000e3b0  ja      loc_18000E452
0x18000e3b6  mov     rax, rbx
0x18000e3b9  nop     dword ptr [rax+00000000h]
0x18000e3c0  test    rax, rax
0x18000e3c3  jz      short loc_18000E3E1
0x18000e3c5  movzx   edx, word ptr [rdi]
0x18000e3c8  test    dx, dx
0x18000e3cb  jz      short loc_18000E3E1
0x18000e3cd  mov     [rcx], dx
0x18000e3d0  add     rdi, 2
0x18000e3d4  add     rcx, 2
0x18000e3d8  dec     rax
0x18000e3db  sub     rsi, 1
0x18000e3df  jnz     short loc_18000E3C0
0x18000e3e1  test    rsi, rsi
0x18000e3e4  lea     rax, [rcx-2]
0x18000e3e8  cmovnz  rax, rcx
0x18000e3ec  mov     [rax], bp
0x18000e3ef  mov     [r14+8], rbx
0x18000e3f3  mov     eax, r15d
0x18000e3f6  mov     r12, [rsp+48h+var_20]
0x18000e3fb  mov     r15, [rsp+48h+var_28]
0x18000e400  mov     rbx, [rsp+48h+arg_0]
0x18000e405  mov     rsi, [rsp+48h+arg_10]
0x18000e40a  add     rsp, 30h
0x18000e40e  pop     r14
0x18000e410  pop     rdi
0x18000e411  pop     rbp
0x18000e412  retn
0x18000e413  mov     eax, 80070216h
0x18000e418  jmp     short loc_18000E400
0x18000e41a  mov     r8, rbx
0x18000e41d  jmp     loc_18000E32C
0x18000e422  mov     eax, 80070216h
0x18000e427  jmp     short loc_18000E3F6
0x18000e429  mov     rbx, r8
0x18000e42c  jmp     loc_18000E32C
0x18000e431  mov     rcx, [rcx+8]
0x18000e435  cmp     rcx, rax
0x18000e438  jnz     loc_1800879F1
0x18000e43e  mov     rcx, [r14]
0x18000e441  test    rcx, rcx
0x18000e444  jnz     loc_1800879E2
0x18000e44a  mov     rax, rbp
0x18000e44d  jmp     loc_1800879EB
0x18000e452  mov     [rcx], bp
0x18000e455  jmp     short loc_18000E3EF
0x18000e457  xor     ebp, ebp
0x18000e459  call    ??1?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::~NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>(void)
0x18000e45e  mov     eax, ebp
0x18000e460  jmp     short loc_18000E40A
0x1800879e2  inc     rax
0x1800879e5  cmp     [rcx+rax*2], bp
0x1800879e9  jnz     short loc_1800879E2
0x1800879eb  mov     [r14+8], rax
0x1800879ef  jmp     short loc_1800879F4
0x1800879f1  mov     rax, rcx
0x1800879f4  cmp     [r14], rbp
0x1800879f7  lea     r9, [rax+1]
0x1800879fb  cmovz   r9, rbp
0x1800879ff  mov     [r14+10h], r9
0x180087a03  jmp     loc_18000E348
0x180087a08  mov     r15d, ebp
0x180087a0b  cmp     rsi, r9
0x180087a0e  jbe     loc_18000E38F
0x180087a14  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x180087a19  mov     [rsp+48h+arg_8], rbp
0x180087a1e  mov     edx, 2; unsigned __int64
0x180087a23  mov     rcx, r9; unsigned __int64
0x180087a26  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180087a2b  mov     r15d, eax
0x180087a2e  test    eax, eax
0x180087a30  js      loc_18000E38F
0x180087a36  mov     r12, [rsp+48h+arg_8]
0x180087a3b  mov     rax, r12
0x180087a3e  sub     rax, r9
0x180087a41  cmp     rax, 800h
0x180087a47  jbe     short loc_180087A50
0x180087a49  lea     r12, [r9+800h]
0x180087a50  mov     rcx, [r14]; pv
0x180087a53  cmp     rsi, r12
0x180087a56  cmova   r12, rsi
0x180087a5a  lea     rdx, [r12+r12]; cb
0x180087a5e  call    cs:__imp_CoTaskMemRealloc
0x180087a64  test    rax, rax
0x180087a67  jz      short loc_180087A75
0x180087a69  mov     [r14+10h], r12
0x180087a6d  mov     [r14], rax
0x180087a70  jmp     loc_18000E394
0x180087a75  mov     eax, 8007000Eh
0x180087a7a  jmp     loc_18000E3F6
```

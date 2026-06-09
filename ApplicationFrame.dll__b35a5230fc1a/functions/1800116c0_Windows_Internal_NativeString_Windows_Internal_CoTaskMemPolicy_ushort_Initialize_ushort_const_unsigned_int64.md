# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x1800116c0`
- end: `0x1800118d2`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `530`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800111d0`
- `0x180013430`
- `0x18001feb0`
- `0x1800243a4`
- `0x1800249d8`
- `0x180024ad0`
- `0x180037950`
- `0x18003d6f0`
- `0x180068ef4`
- `0x18006c078`

## callees

- `0x1800116c0`
- `0x18002e020`
- `0x1800532a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800118b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800118b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001174d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001174d`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        __int64 a1,
        _WORD *a2,
        unsigned __int64 a3)
{
  _WORD *v3; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r9
  _WORD *v8; // rax
  int v9; // r12d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rax
  _WORD *v12; // rax
  __int64 result; // rax
  void *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // r9
  unsigned __int64 v17; // r14
  LPVOID v18; // rax
  unsigned __int64 v19; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2;
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    if ( a3 == -1 )
    {
      a3 = v5;
    }
    else if ( a3 < v5 )
    {
      v5 = a3;
    }
    v6 = a3 + 1;
    if ( a3 + 1 < a3 )
      return 2147942934LL;
    v7 = *(_QWORD *)(a1 + 16);
    if ( v7 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
      if ( *v15 )
        v7 = v15[1] + 1LL;
      else
        v7 = 0;
      v15[2] = v7;
    }
    if ( v7 )
    {
      v9 = 0;
      if ( v6 > v7 )
      {
        v19 = 0;
        v9 = ULongLongMult(v7, 2u, &v19);
        if ( v9 >= 0 )
        {
          v17 = v19;
          if ( v19 - v16 > 0x800 )
            v17 = v16 + 2048;
          if ( v6 > v17 )
            v17 = v6;
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
      if ( !is_mul_ok(v6, 2u) )
        return 2147942934LL;
      v8 = CoTaskMemAlloc(2 * v6);
      if ( v8 )
      {
        *(_QWORD *)(a1 + 16) = v6;
        v9 = 0;
        *(_QWORD *)a1 = v8;
        *v8 = 0;
        goto LABEL_15;
      }
      v9 = -2147024882;
    }
    if ( v9 < 0 )
      return (unsigned int)v9;
LABEL_15:
    if ( v6 )
    {
      v10 = *(_WORD **)a1;
      if ( v5 > 0x7FFFFFFE || v6 > 0x7FFFFFFF )
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
    *(_QWORD *)(a1 + 8) = v5;
    return (unsigned int)v9;
  }
  v14 = *(void **)a1;
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  result = 0;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x1800116c0  push    rbx
0x1800116c2  push    rbp
0x1800116c3  push    r15
0x1800116c5  sub     rsp, 30h
0x1800116c9  mov     rbx, rdx
0x1800116cc  mov     r15, rcx
0x1800116cf  test    rdx, rdx
0x1800116d2  jz      loc_18001181D
0x1800116d8  mov     [rsp+48h+arg_0], rsi
0x1800116dd  mov     [rsp+48h+arg_10], rdi
0x1800116e2  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800116e9  nop     dword ptr [rax+00000000h]
0x1800116f0  inc     rdi
0x1800116f3  cmp     word ptr [rdx+rdi*2], 0
0x1800116f8  jnz     short loc_1800116F0
0x1800116fa  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800116fe  jz      loc_180011802
0x180011704  cmp     r8, rdi
0x180011707  jb      loc_180011815
0x18001170d  lea     rsi, [r8+1]
0x180011711  cmp     rsi, r8
0x180011714  jb      loc_1800117F4
0x18001171a  mov     r9, [rcx+10h]
0x18001171e  xor     ebp, ebp
0x180011720  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180011724  jz      loc_180011848
0x18001172a  mov     [rsp+48h+var_20], r12
0x18001172f  mov     [rsp+48h+var_28], r14
0x180011734  test    r9, r9
0x180011737  jnz     short loc_18001176B
0x180011739  mov     eax, 2
0x18001173e  mul     rsi
0x180011741  test    rdx, rdx
0x180011744  jnz     loc_1800117FB
0x18001174a  mov     rcx, rax; cb
0x18001174d  call    cs:__imp_CoTaskMemAlloc
0x180011753  test    rax, rax
0x180011756  jz      loc_18001180A
0x18001175c  mov     [r15+10h], rsi
0x180011760  mov     r12d, ebp
0x180011763  mov     [r15], rax
0x180011766  mov     [rax], bp
0x180011769  jmp     short loc_18001177C
0x18001176b  mov     r12d, ebp
0x18001176e  cmp     rsi, r9
0x180011771  ja      loc_180011867
0x180011777  test    r12d, r12d
0x18001177a  js      short loc_1800117D4
0x18001177c  test    rsi, rsi
0x18001177f  jz      short loc_1800117D0
0x180011781  mov     rdx, [r15]
0x180011784  cmp     rdi, 7FFFFFFEh
0x18001178b  ja      loc_180011843
0x180011791  cmp     rsi, 7FFFFFFFh
0x180011798  ja      loc_180011843
0x18001179e  mov     rax, rdi
0x1800117a1  test    rax, rax
0x1800117a4  jz      short loc_1800117C2
0x1800117a6  movzx   ecx, word ptr [rbx]
0x1800117a9  test    cx, cx
0x1800117ac  jz      short loc_1800117C2
0x1800117ae  mov     [rdx], cx
0x1800117b1  add     rbx, 2
0x1800117b5  add     rdx, 2
0x1800117b9  dec     rax
0x1800117bc  sub     rsi, 1
0x1800117c0  jnz     short loc_1800117A1
0x1800117c2  test    rsi, rsi
0x1800117c5  lea     rax, [rdx-2]
0x1800117c9  cmovnz  rax, rdx
0x1800117cd  mov     [rax], bp
0x1800117d0  mov     [r15+8], rdi
0x1800117d4  mov     eax, r12d
0x1800117d7  mov     r12, [rsp+48h+var_20]
0x1800117dc  mov     r14, [rsp+48h+var_28]
0x1800117e1  mov     rsi, [rsp+48h+arg_0]
0x1800117e6  mov     rdi, [rsp+48h+arg_10]
0x1800117eb  add     rsp, 30h
0x1800117ef  pop     r15
0x1800117f1  pop     rbp
0x1800117f2  pop     rbx
0x1800117f3  retn
0x1800117f4  mov     eax, 80070216h
0x1800117f9  jmp     short loc_1800117E1
0x1800117fb  mov     eax, 80070216h
0x180011800  jmp     short loc_1800117D7
0x180011802  mov     r8, rdi
0x180011805  jmp     loc_18001170D
0x18001180a  mov     r12d, 8007000Eh
0x180011810  jmp     loc_180011777
0x180011815  mov     rdi, r8
0x180011818  jmp     loc_18001170D
0x18001181d  mov     rcx, [rcx]; pv
0x180011820  xor     ebp, ebp
0x180011822  test    rcx, rcx
0x180011825  jz      short loc_180011830
0x180011827  call    cs:__imp_CoTaskMemFree
0x18001182d  mov     [r15], rbp
0x180011830  mov     [r15+8], rbp
0x180011834  mov     eax, ebp
0x180011836  mov     [r15+10h], rbp
0x18001183a  add     rsp, 30h
0x18001183e  pop     r15
0x180011840  pop     rbp
0x180011841  pop     rbx
0x180011842  retn
0x180011843  mov     [rdx], bp
0x180011846  jmp     short loc_1800117D0
0x180011848  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18001184d  cmp     [rcx], rbp
0x180011850  jz      short loc_18001185B
0x180011852  mov     r9, [rcx+8]
0x180011856  inc     r9
0x180011859  jmp     short loc_18001185E
0x18001185b  mov     r9, rbp
0x18001185e  mov     [rcx+10h], r9
0x180011862  jmp     loc_18001172A
0x180011867  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x18001186c  mov     [rsp+48h+arg_8], rbp
0x180011871  mov     edx, 2; unsigned __int64
0x180011876  mov     rcx, r9; unsigned __int64
0x180011879  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001187e  mov     r12d, eax
0x180011881  test    eax, eax
0x180011883  js      loc_180011777
0x180011889  mov     r14, [rsp+48h+arg_8]
0x18001188e  mov     rax, r14
0x180011891  sub     rax, r9
0x180011894  cmp     rax, 800h
0x18001189a  jbe     short loc_1800118A3
0x18001189c  lea     r14, [r9+800h]
0x1800118a3  mov     rcx, [r15]; pv
0x1800118a6  cmp     rsi, r14
0x1800118a9  cmova   r14, rsi
0x1800118ad  lea     rdx, [r14+r14]; cb
0x1800118b1  call    cs:__imp_CoTaskMemRealloc
0x1800118b7  test    rax, rax
0x1800118ba  jz      short loc_1800118C8
0x1800118bc  mov     [r15+10h], r14
0x1800118c0  mov     [r15], rax
0x1800118c3  jmp     loc_18001177C
0x1800118c8  mov     eax, 8007000Eh
0x1800118cd  jmp     loc_1800117D7
```

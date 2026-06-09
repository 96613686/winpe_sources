# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x1800116e0`
- end: `0x1800118b4`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `468`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e538`
- `0x180011450`
- `0x180011620`
- `0x18001a494`
- `0x18001dc70`
- `0x180020ec0`
- `0x1800244b0`
- `0x18004c768`

## callees

- `0x1800116e0`
- `0x180011bb0`
- `0x180011be0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011766`

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
  unsigned __int64 v7; // rcx
  _WORD *v8; // rax
  int v9; // r8d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rax
  _WORD *v12; // rax
  unsigned __int64 v14; // r14
  LPVOID v15; // rax

  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    return 0;
  }
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
    if ( *(_QWORD *)a1 )
      v7 = *(_QWORD *)(a1 + 8) + 1LL;
    else
      v7 = 0;
    *(_QWORD *)(a1 + 16) = v7;
  }
  if ( v7 )
  {
    v9 = 0;
    if ( v6 <= v7 )
      goto LABEL_13;
    v14 = 2 * v7;
    if ( is_mul_ok(v7, 2u) )
    {
      if ( v7 > 0x800 )
        v14 = v7 + 2048;
      if ( v6 > v14 )
        v14 = v6;
      v15 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v14);
      if ( !v15 )
        return 2147942414LL;
      *(_QWORD *)(a1 + 16) = v14;
      v9 = 0;
      *(_QWORD *)a1 = v15;
      goto LABEL_14;
    }
    return 2147942934LL;
  }
  if ( !is_mul_ok(v6, 2u) )
    return 2147942934LL;
  v8 = CoTaskMemAlloc(2 * v6);
  if ( v8 )
  {
    *(_QWORD *)(a1 + 16) = v6;
    v9 = 0;
    *(_QWORD *)a1 = v8;
    *v8 = 0;
LABEL_14:
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
  v9 = -2147024882;
LABEL_13:
  if ( v9 >= 0 )
    goto LABEL_14;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800116e0  push    rbx
0x1800116e2  push    rbp
0x1800116e3  push    r15
0x1800116e5  sub     rsp, 20h
0x1800116e9  mov     rbx, rdx
0x1800116ec  mov     r15, rcx
0x1800116ef  test    rdx, rdx
0x1800116f2  jz      loc_18001188E
0x1800116f8  mov     [rsp+38h+arg_0], rsi
0x1800116fd  mov     [rsp+38h+arg_10], rdi
0x180011702  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180011709  nop     dword ptr [rax+00000000h]
0x180011710  inc     rdi
0x180011713  cmp     word ptr [rdx+rdi*2], 0
0x180011718  jnz     short loc_180011710
0x18001171a  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001171e  jnz     loc_1800118A8
0x180011724  mov     r8, rdi
0x180011727  lea     rsi, [r8+1]
0x18001172b  cmp     rsi, r8
0x18001172e  jb      loc_1800117FE
0x180011734  mov     rcx, [rcx+10h]
0x180011738  xor     ebp, ebp
0x18001173a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001173e  jz      loc_180011862
0x180011744  mov     [rsp+38h+arg_18], r14
0x180011749  test    rcx, rcx
0x18001174c  jnz     loc_18001180C
0x180011752  mov     eax, 2
0x180011757  mul     rsi
0x18001175a  test    rdx, rdx
0x18001175d  jnz     loc_180011805
0x180011763  mov     rcx, rax; cb
0x180011766  call    cs:__imp_CoTaskMemAlloc
0x18001176c  test    rax, rax
0x18001176f  jz      short loc_180011780
0x180011771  mov     [r15+10h], rsi
0x180011775  mov     r8d, ebp
0x180011778  mov     [r15], rax
0x18001177b  mov     [rax], bp
0x18001177e  jmp     short loc_18001178B
0x180011780  mov     r8d, 8007000Eh
0x180011786  test    r8d, r8d
0x180011789  js      short loc_1800117E3
0x18001178b  test    rsi, rsi
0x18001178e  jz      short loc_1800117DF
0x180011790  mov     rdx, [r15]
0x180011793  cmp     rdi, 7FFFFFFEh
0x18001179a  ja      loc_1800118A0
0x1800117a0  cmp     rsi, 7FFFFFFFh
0x1800117a7  ja      loc_1800118A0
0x1800117ad  mov     rax, rdi
0x1800117b0  test    rax, rax
0x1800117b3  jz      short loc_1800117D1
0x1800117b5  movzx   ecx, word ptr [rbx]
0x1800117b8  test    cx, cx
0x1800117bb  jz      short loc_1800117D1
0x1800117bd  mov     [rdx], cx
0x1800117c0  add     rbx, 2
0x1800117c4  add     rdx, 2
0x1800117c8  dec     rax
0x1800117cb  sub     rsi, 1
0x1800117cf  jnz     short loc_1800117B0
0x1800117d1  test    rsi, rsi
0x1800117d4  lea     rax, [rdx-2]
0x1800117d8  cmovnz  rax, rdx
0x1800117dc  mov     [rax], bp
0x1800117df  mov     [r15+8], rdi
0x1800117e3  mov     eax, r8d
0x1800117e6  mov     r14, [rsp+38h+arg_18]
0x1800117eb  mov     rsi, [rsp+38h+arg_0]
0x1800117f0  mov     rdi, [rsp+38h+arg_10]
0x1800117f5  add     rsp, 20h
0x1800117f9  pop     r15
0x1800117fb  pop     rbp
0x1800117fc  pop     rbx
0x1800117fd  retn
0x1800117fe  mov     eax, 80070216h
0x180011803  jmp     short loc_1800117EB
0x180011805  mov     eax, 80070216h
0x18001180a  jmp     short loc_1800117E6
0x18001180c  mov     r8d, ebp
0x18001180f  cmp     rsi, rcx
0x180011812  jbe     loc_180011786
0x180011818  mov     eax, 2
0x18001181d  mul     rcx
0x180011820  mov     r14, rax
0x180011823  test    rdx, rdx
0x180011826  jnz     short loc_180011805
0x180011828  sub     rax, rcx
0x18001182b  cmp     rax, 800h
0x180011831  jbe     short loc_18001183A
0x180011833  lea     r14, [rcx+800h]
0x18001183a  mov     rcx, [r15]; pv
0x18001183d  cmp     rsi, r14
0x180011840  cmova   r14, rsi
0x180011844  lea     rdx, [r14+r14]; cb
0x180011848  call    cs:__imp_CoTaskMemRealloc
0x18001184e  test    rax, rax
0x180011851  jz      short loc_180011884
0x180011853  mov     [r15+10h], r14
0x180011857  mov     r8d, ebp
0x18001185a  mov     [r15], rax
0x18001185d  jmp     loc_18001178B
0x180011862  mov     rcx, r15
0x180011865  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18001186a  cmp     [r15], rbp
0x18001186d  jz      short loc_18001187F
0x18001186f  mov     rcx, [r15+8]
0x180011873  inc     rcx
0x180011876  mov     [r15+10h], rcx
0x18001187a  jmp     loc_180011744
0x18001187f  mov     rcx, rbp
0x180011882  jmp     short loc_180011876
0x180011884  mov     eax, 8007000Eh
0x180011889  jmp     loc_1800117E6
0x18001188e  xor     ebp, ebp
0x180011890  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180011895  mov     eax, ebp
0x180011897  add     rsp, 20h
0x18001189b  pop     r15
0x18001189d  pop     rbp
0x18001189e  pop     rbx
0x18001189f  retn
0x1800118a0  mov     [rdx], bp
0x1800118a3  jmp     loc_1800117DF
0x1800118a8  cmp     r8, rdi
0x1800118ab  cmovb   rdi, r8
0x1800118af  jmp     loc_180011727
```

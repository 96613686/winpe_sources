# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18007954c`
- end: `0x18007967b`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073b00`

## callees

- `0x18002739c`
- `0x18007954c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800795e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800795e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007964d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007964d`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = -1;
  if ( v5 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v6;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v6) );
      }
      else
      {
        v6 = 0;
      }
      *(_QWORD *)(a1 + 8) = v6;
    }
    else
    {
      v6 = *(_QWORD *)(a1 + 8);
    }
    v5 = (v6 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v5;
  }
  if ( !v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v2, 2u, &cb);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v7 = CoTaskMemAlloc(cb);
    if ( v7 )
    {
      *(_QWORD *)(a1 + 16) = v2;
      *(_QWORD *)a1 = v7;
      *v7 = 0;
      return (unsigned int)v4;
    }
    return (unsigned int)-2147024882;
  }
  v4 = 0;
  if ( v2 > v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v5, 2u, &cb);
    if ( v4 >= 0 )
    {
      v9 = cb;
      if ( cb - v8 > 0x800 )
        v9 = v8 + 2048;
      if ( v2 > v9 )
        v9 = v2;
      v10 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v9);
      if ( v10 )
      {
        *(_QWORD *)(a1 + 16) = v9;
        *(_QWORD *)a1 = v10;
        return (unsigned int)v4;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007954c  mov     [rsp+arg_0], rbx
0x180079551  mov     [rsp+arg_10], rbp
0x180079556  push    rsi
0x180079557  push    rdi
0x180079558  push    r14
0x18007955a  sub     rsp, 20h
0x18007955e  lea     rbp, [rdx+1]
0x180079562  mov     rdi, rcx
0x180079565  cmp     rbp, rdx
0x180079568  jnb     short loc_180079574
0x18007956a  mov     ebx, 80070216h
0x18007956f  jmp     loc_180079666
0x180079574  mov     r9, [rcx+10h]
0x180079578  xor     r14d, r14d
0x18007957b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007957f  cmp     r9, rcx
0x180079582  jnz     short loc_1800795BE
0x180079584  cmp     [rdi+8], rcx
0x180079588  jnz     short loc_1800795A7
0x18007958a  mov     rax, [rdi]
0x18007958d  test    rax, rax
0x180079590  jz      short loc_18007959E
0x180079592  inc     rcx
0x180079595  cmp     [rax+rcx*2], r14w
0x18007959a  jnz     short loc_180079592
0x18007959c  jmp     short loc_1800795A1
0x18007959e  mov     rcx, r14
0x1800795a1  mov     [rdi+8], rcx
0x1800795a5  jmp     short loc_1800795AB
0x1800795a7  mov     rcx, [rdi+8]
0x1800795ab  mov     rax, [rdi]
0x1800795ae  inc     rcx
0x1800795b1  neg     rax
0x1800795b4  sbb     r9, r9
0x1800795b7  and     r9, rcx
0x1800795ba  mov     [rdi+10h], r9
0x1800795be  test    r9, r9
0x1800795c1  jnz     short loc_180079600
0x1800795c3  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800795c8  mov     [rsp+38h+cb], r14
0x1800795cd  lea     edx, [r9+2]; unsigned __int64
0x1800795d1  mov     rcx, rbp; unsigned __int64
0x1800795d4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800795d9  mov     ebx, eax
0x1800795db  test    eax, eax
0x1800795dd  js      loc_180079666
0x1800795e3  mov     rcx, [rsp+38h+cb]; cb
0x1800795e8  call    cs:__imp_CoTaskMemAlloc
0x1800795ee  test    rax, rax
0x1800795f1  jz      short loc_180079661
0x1800795f3  mov     [rdi+10h], rbp
0x1800795f7  mov     [rdi], rax
0x1800795fa  mov     [rax], r14w
0x1800795fe  jmp     short loc_180079666
0x180079600  mov     ebx, r14d
0x180079603  cmp     rbp, r9
0x180079606  jbe     short loc_180079666
0x180079608  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18007960d  mov     [rsp+38h+cb], r14
0x180079612  mov     edx, 2; unsigned __int64
0x180079617  mov     rcx, r9; unsigned __int64
0x18007961a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007961f  mov     ebx, eax
0x180079621  test    eax, eax
0x180079623  js      short loc_180079666
0x180079625  mov     rsi, [rsp+38h+cb]
0x18007962a  mov     rax, rsi
0x18007962d  sub     rax, r9
0x180079630  cmp     rax, 800h
0x180079636  jbe     short loc_18007963F
0x180079638  lea     rsi, [r9+800h]
0x18007963f  mov     rcx, [rdi]; pv
0x180079642  cmp     rbp, rsi
0x180079645  cmova   rsi, rbp
0x180079649  lea     rdx, [rsi+rsi]; cb
0x18007964d  call    cs:__imp_CoTaskMemRealloc
0x180079653  test    rax, rax
0x180079656  jz      short loc_180079661
0x180079658  mov     [rdi+10h], rsi
0x18007965c  mov     [rdi], rax
0x18007965f  jmp     short loc_180079666
0x180079661  mov     ebx, 8007000Eh
0x180079666  mov     rbp, [rsp+38h+arg_10]
0x18007966b  mov     eax, ebx
0x18007966d  mov     rbx, [rsp+38h+arg_0]
0x180079672  add     rsp, 20h
0x180079676  pop     r14
0x180079678  pop     rdi
0x180079679  pop     rsi
0x18007967a  retn
```

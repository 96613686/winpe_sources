# GeoDataNative::AllocateArrays(int,int,int,int)

- ea: `0x100427b90`
- end: `0x100427e31`
- name: `?AllocateArrays@GeoDataNative@@QEAAJHHHH@Z`
- size: `673`
- prototype: `__int64 __fastcall(void **this, int, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100427e70`

## callees

- `0x100427b90`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427c31`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427cc6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427d63`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427dfa`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427c31`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427cc6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427d63`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100427dfa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427be5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427c79`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427d10`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427db1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427be5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427c79`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427d10`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100427db1`

## string_xrefs

- `0x100427c12`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`
- `0x100427ca7`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`
- `0x100427d44`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`
- `0x100427ddb`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
__int64 __fastcall GeoDataNative::AllocateArrays(void **this, int a2, int a3, int a4, int a5)
{
  int v9; // esi
  void *v10; // rax
  int v11; // edi
  void *v12; // rax
  int v13; // edi
  void *v14; // rax
  int v15; // esi
  void *v16; // rax

  if ( a2 > *((_DWORD *)this + 20) )
  {
    if ( g_SOSHost )
    {
      if ( *this )
        (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
    }
    else
    {
      free(*this);
    }
    *this = 0;
    v9 = a2 + a2 / 2;
    _mm_lfence();
    if ( g_SOSHost )
      v10 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                      g_SOSMemObj,
                      16LL * v9,
                      "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                      26);
    else
      v10 = malloc(16LL * v9);
    *this = v10;
    if ( !v10 )
      return 2147942414LL;
    *((_DWORD *)this + 20) = v9;
  }
  *((_DWORD *)this + 2) = a2;
  if ( a3 > *((_DWORD *)this + 21) )
  {
    if ( g_SOSHost )
    {
      if ( this[4] )
        (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
    }
    else
    {
      free(this[4]);
    }
    this[4] = 0;
    v11 = a3 / 2 + a3;
    _mm_lfence();
    if ( g_SOSHost )
      v12 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                      g_SOSMemObj,
                      8LL * v11,
                      "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                      26);
    else
      v12 = malloc(8LL * v11);
    this[4] = v12;
    if ( !v12 )
      return 2147942414LL;
    *((_DWORD *)this + 21) = v11;
  }
  *((_DWORD *)this + 10) = a3;
  if ( a4 > *((_DWORD *)this + 22) )
  {
    if ( g_SOSHost )
    {
      if ( this[6] )
        (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
    }
    else
    {
      free(this[6]);
    }
    this[6] = 0;
    v13 = a4 + a4 / 2;
    _mm_lfence();
    if ( g_SOSHost )
      v14 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                      g_SOSMemObj,
                      12LL * v13,
                      "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                      26);
    else
      v14 = malloc(12LL * v13);
    this[6] = v14;
    if ( !v14 )
      return 2147942414LL;
    *((_DWORD *)this + 22) = v13;
  }
  *((_DWORD *)this + 14) = a4;
  if ( a5 > *((_DWORD *)this + 23) )
  {
    if ( g_SOSHost )
    {
      if ( this[8] )
        (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
    }
    else
    {
      free(this[8]);
    }
    this[8] = 0;
    v15 = a5 + a5 / 2;
    _mm_lfence();
    if ( g_SOSHost )
      v16 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, const char *, __int64))(*g_SOSMemObj + 120LL))(
                      g_SOSMemObj,
                      v15,
                      "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                      26);
    else
      v16 = malloc(v15);
    this[8] = v16;
    if ( !v16 )
      return 2147942414LL;
    *((_DWORD *)this + 23) = v15;
  }
  *((_DWORD *)this + 18) = a5;
  return 0;
}

```

## disassembly

```asm
0x100427b90  mov     [rsp+arg_0], rbx
0x100427b95  mov     [rsp+arg_8], rbp
0x100427b9a  mov     [rsp+arg_10], rsi
0x100427b9f  push    rdi
0x100427ba0  push    r14
0x100427ba2  push    r15
0x100427ba4  sub     rsp, 20h
0x100427ba8  xor     r15d, r15d
0x100427bab  mov     r14d, r9d
0x100427bae  mov     ebp, r8d
0x100427bb1  mov     edi, edx
0x100427bb3  mov     rbx, rcx
0x100427bb6  cmp     edx, [rcx+50h]
0x100427bb9  jle     loc_100427C46
0x100427bbf  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427bc6  mov     rdx, [rcx]
0x100427bc9  jz      short loc_100427BE2
0x100427bcb  test    rdx, rdx
0x100427bce  jz      short loc_100427BEB
0x100427bd0  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427bd7  mov     rax, [rcx]
0x100427bda  call    qword ptr [rax+80h]
0x100427be0  jmp     short loc_100427BEB
0x100427be2  mov     rcx, rdx; Block
0x100427be5  call    cs:__imp_free
0x100427beb  mov     eax, edi
0x100427bed  mov     [rbx], r15
0x100427bf0  cdq
0x100427bf1  sub     eax, edx
0x100427bf3  sar     eax, 1
0x100427bf5  lea     esi, [rdi+rax]
0x100427bf8  movsxd  rax, esi
0x100427bfb  shl     rax, 4
0x100427bff  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427c06  jz      short loc_100427C2B
0x100427c08  lfence
0x100427c0b  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427c12  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100427c19  mov     r9d, 1Ah
0x100427c1f  mov     rdx, rax
0x100427c22  mov     r10, [rcx]
0x100427c25  call    qword ptr [r10+78h]
0x100427c29  jmp     short loc_100427C37
0x100427c2b  lfence
0x100427c2e  mov     rcx, rax; Size
0x100427c31  call    cs:__imp_malloc
0x100427c37  mov     [rbx], rax
0x100427c3a  test    rax, rax
0x100427c3d  jz      loc_100427E09
0x100427c43  mov     [rbx+50h], esi
0x100427c46  mov     [rbx+8], edi
0x100427c49  cmp     ebp, [rbx+54h]
0x100427c4c  jle     loc_100427CDC
0x100427c52  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427c59  mov     rdx, [rbx+20h]
0x100427c5d  jz      short loc_100427C76
0x100427c5f  test    rdx, rdx
0x100427c62  jz      short loc_100427C7F
0x100427c64  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427c6b  mov     rax, [rcx]
0x100427c6e  call    qword ptr [rax+80h]
0x100427c74  jmp     short loc_100427C7F
0x100427c76  mov     rcx, rdx; Block
0x100427c79  call    cs:__imp_free
0x100427c7f  mov     eax, ebp
0x100427c81  mov     [rbx+20h], r15
0x100427c85  cdq
0x100427c86  sub     eax, edx
0x100427c88  sar     eax, 1
0x100427c8a  lea     edi, [rax+rbp]
0x100427c8d  movsxd  rax, edi
0x100427c90  shl     rax, 3
0x100427c94  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427c9b  jz      short loc_100427CC0
0x100427c9d  lfence
0x100427ca0  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427ca7  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100427cae  mov     r9d, 1Ah
0x100427cb4  mov     rdx, rax
0x100427cb7  mov     r10, [rcx]
0x100427cba  call    qword ptr [r10+78h]
0x100427cbe  jmp     short loc_100427CCC
0x100427cc0  lfence
0x100427cc3  mov     rcx, rax; Size
0x100427cc6  call    cs:__imp_malloc
0x100427ccc  mov     [rbx+20h], rax
0x100427cd0  test    rax, rax
0x100427cd3  jz      loc_100427E09
0x100427cd9  mov     [rbx+54h], edi
0x100427cdc  mov     [rbx+28h], ebp
0x100427cdf  cmp     r14d, [rbx+58h]
0x100427ce3  jle     loc_100427D79
0x100427ce9  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427cf0  mov     rdx, [rbx+30h]
0x100427cf4  jz      short loc_100427D0D
0x100427cf6  test    rdx, rdx
0x100427cf9  jz      short loc_100427D16
0x100427cfb  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427d02  mov     rax, [rcx]
0x100427d05  call    qword ptr [rax+80h]
0x100427d0b  jmp     short loc_100427D16
0x100427d0d  mov     rcx, rdx; Block
0x100427d10  call    cs:__imp_free
0x100427d16  mov     eax, r14d
0x100427d19  mov     [rbx+30h], r15
0x100427d1d  cdq
0x100427d1e  sub     eax, edx
0x100427d20  sar     eax, 1
0x100427d22  lea     edi, [r14+rax]
0x100427d26  movsxd  rcx, edi
0x100427d29  lea     rax, [rcx+rcx*2]
0x100427d2d  shl     rax, 2
0x100427d31  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427d38  jz      short loc_100427D5D
0x100427d3a  lfence
0x100427d3d  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427d44  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100427d4b  mov     r9d, 1Ah
0x100427d51  mov     rdx, rax
0x100427d54  mov     r10, [rcx]
0x100427d57  call    qword ptr [r10+78h]
0x100427d5b  jmp     short loc_100427D69
0x100427d5d  lfence
0x100427d60  mov     rcx, rax; Size
0x100427d63  call    cs:__imp_malloc
0x100427d69  mov     [rbx+30h], rax
0x100427d6d  test    rax, rax
0x100427d70  jz      loc_100427E09
0x100427d76  mov     [rbx+58h], edi
0x100427d79  mov     edi, [rsp+38h+arg_20]
0x100427d7d  mov     [rbx+38h], r14d
0x100427d81  cmp     edi, [rbx+5Ch]
0x100427d84  jle     loc_100427E13
0x100427d8a  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427d91  mov     rdx, [rbx+40h]
0x100427d95  jz      short loc_100427DAE
0x100427d97  test    rdx, rdx
0x100427d9a  jz      short loc_100427DB7
0x100427d9c  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427da3  mov     rax, [rcx]
0x100427da6  call    qword ptr [rax+80h]
0x100427dac  jmp     short loc_100427DB7
0x100427dae  mov     rcx, rdx; Block
0x100427db1  call    cs:__imp_free
0x100427db7  mov     eax, edi
0x100427db9  mov     [rbx+40h], r15
0x100427dbd  cdq
0x100427dbe  sub     eax, edx
0x100427dc0  sar     eax, 1
0x100427dc2  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x100427dc9  lea     esi, [rdi+rax]
0x100427dcc  movsxd  rax, esi
0x100427dcf  jz      short loc_100427DF4
0x100427dd1  lfence
0x100427dd4  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100427ddb  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100427de2  mov     r9d, 1Ah
0x100427de8  mov     rdx, rax
0x100427deb  mov     r10, [rcx]
0x100427dee  call    qword ptr [r10+78h]
0x100427df2  jmp     short loc_100427E00
0x100427df4  lfence
0x100427df7  mov     rcx, rax; Size
0x100427dfa  call    cs:__imp_malloc
0x100427e00  mov     [rbx+40h], rax
0x100427e04  test    rax, rax
0x100427e07  jnz     short loc_100427E10
0x100427e09  mov     eax, 8007000Eh
0x100427e0e  jmp     short loc_100427E18
0x100427e10  mov     [rbx+5Ch], esi
0x100427e13  mov     [rbx+48h], edi
0x100427e16  xor     eax, eax
0x100427e18  mov     rbx, [rsp+38h+arg_0]
0x100427e1d  mov     rbp, [rsp+38h+arg_8]
0x100427e22  mov     rsi, [rsp+38h+arg_10]
0x100427e27  add     rsp, 20h
0x100427e2b  pop     r15
0x100427e2d  pop     r14
0x100427e2f  pop     rdi
0x100427e30  retn
```

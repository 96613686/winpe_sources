# BackgroundIsStringSupported(HRECOCONTEXT__ *,ulong,ushort const *,long (*)(long,uchar *),void *)

- ea: `0x180083ff4`
- end: `0x1800840f8`
- name: `?BackgroundIsStringSupported@@YAJPEAUHRECOCONTEXT__@@KPEBGP6AJJPEAE@ZPEAX@Z`
- size: `260`
- prototype: `int(HRECOCONTEXT, unsigned int, const unsigned __int16 *, int (*)(int, unsigned __int8 *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a6160`

## callees

- `0x180044ac6`
- `0x180083dc0`
- `0x180083ff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008405f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008405f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800840a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800840d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800840e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800840a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800840d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800840e0`

## pseudocode

```c
__int64 __fastcall BackgroundIsStringSupported(
        _QWORD *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        int (*a4)(int, unsigned __int8 *),
        void *a5)
{
  __int64 v5; // rdi
  _QWORD *v9; // rbx
  SIZE_T v10; // rdi
  void *v11; // rax
  int v12; // edi
  void *v13; // rcx

  v5 = a2;
  if ( a2 > 0x7FFFFFFF )
    return 2147549183LL;
  if ( !a1 || !a3 && a2 || a2 >= 0x3FFFFFFF || 2 * a2 && !a3 )
    return 2147500035LL;
  if ( !a1[2] )
    return 2147746356LL;
  v9 = CoTaskMemAlloc(0x20u);
  if ( !v9 )
    return 2147942414LL;
  *((_DWORD *)v9 + 4) = v5;
  v10 = 2 * v5;
  v9[1] = a5;
  *v9 = InkHResultSynchronousCallback;
  v11 = CoTaskMemAlloc(v10);
  v9[3] = v11;
  if ( !v11 )
  {
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  memcpy_0(v11, a3, v10);
  v12 = AddToQueue(a1, 12, v9);
  if ( v12 < 0 )
  {
    v13 = (void *)v9[3];
    if ( v13 )
      CoTaskMemFree(v13);
    CoTaskMemFree(v9);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180083ff4  push    rbx
0x180083ff6  push    rbp
0x180083ff7  push    rsi
0x180083ff8  push    rdi
0x180083ff9  sub     rsp, 28h
0x180083ffd  mov     edi, edx
0x180083fff  mov     rsi, r8
0x180084002  mov     rbp, rcx
0x180084005  cmp     edx, 7FFFFFFFh
0x18008400b  jbe     short loc_180084017
0x18008400d  mov     eax, 8000FFFFh
0x180084012  jmp     loc_1800840EF
0x180084017  test    rbp, rbp
0x18008401a  jz      loc_1800840EA
0x180084020  test    rsi, rsi
0x180084023  jnz     short loc_18008402D
0x180084025  test    edx, edx
0x180084027  jnz     loc_1800840EA
0x18008402d  cmp     edi, 3FFFFFFFh
0x180084033  jnb     loc_1800840EA
0x180084039  lea     eax, [rdi+rdi]
0x18008403c  test    eax, eax
0x18008403e  jz      short loc_180084049
0x180084040  test    rsi, rsi
0x180084043  jz      loc_1800840EA
0x180084049  cmp     qword ptr [rcx+10h], 0
0x18008404e  jnz     short loc_18008405A
0x180084050  mov     eax, 80040234h
0x180084055  jmp     loc_1800840EF
0x18008405a  mov     ecx, 20h ; ' '; cb
0x18008405f  call    cs:__imp_CoTaskMemAlloc
0x180084065  mov     rbx, rax
0x180084068  test    rax, rax
0x18008406b  jnz     short loc_180084074
0x18008406d  mov     eax, 8007000Eh
0x180084072  jmp     short loc_1800840EF
0x180084074  mov     rax, [rsp+48h+arg_20]
0x180084079  mov     [rbx+10h], edi
0x18008407c  add     rdi, rdi
0x18008407f  mov     [rbx+8], rax
0x180084083  mov     rcx, rdi; cb
0x180084086  lea     rax, ?InkHResultSynchronousCallback@@YAJJPEAE@Z; InkHResultSynchronousCallback(long,uchar *)
0x18008408d  mov     [rbx], rax
0x180084090  call    cs:__imp_CoTaskMemAlloc
0x180084096  mov     [rbx+18h], rax
0x18008409a  test    rax, rax
0x18008409d  jnz     short loc_1800840AA
0x18008409f  mov     rcx, rbx; pv
0x1800840a2  call    cs:__imp_CoTaskMemFree
0x1800840a8  jmp     short loc_18008406D
0x1800840aa  mov     r8, rdi; Size
0x1800840ad  mov     rdx, rsi; Src
0x1800840b0  mov     rcx, rax; void *
0x1800840b3  call    memcpy_0
0x1800840b8  mov     r8, rbx
0x1800840bb  mov     edx, 0Ch
0x1800840c0  mov     rcx, rbp
0x1800840c3  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x1800840c8  mov     edi, eax
0x1800840ca  test    eax, eax
0x1800840cc  jns     short loc_1800840E6
0x1800840ce  mov     rcx, [rbx+18h]; pv
0x1800840d2  test    rcx, rcx
0x1800840d5  jz      short loc_1800840DD
0x1800840d7  call    cs:__imp_CoTaskMemFree
0x1800840dd  mov     rcx, rbx; pv
0x1800840e0  call    cs:__imp_CoTaskMemFree
0x1800840e6  mov     eax, edi
0x1800840e8  jmp     short loc_1800840EF
0x1800840ea  mov     eax, 80004003h
0x1800840ef  add     rsp, 28h
0x1800840f3  pop     rdi
0x1800840f4  pop     rsi
0x1800840f5  pop     rbp
0x1800840f6  pop     rbx
0x1800840f7  retn
```

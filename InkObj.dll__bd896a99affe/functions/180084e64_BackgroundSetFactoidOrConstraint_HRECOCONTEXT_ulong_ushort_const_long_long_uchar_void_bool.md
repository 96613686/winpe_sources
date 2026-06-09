# BackgroundSetFactoidOrConstraint(HRECOCONTEXT__ *,ulong,ushort const *,long (*)(long,uchar *),void *,bool)

- ea: `0x180084e64`
- end: `0x180084fa3`
- name: `?BackgroundSetFactoidOrConstraint@@YAJPEAUHRECOCONTEXT__@@KPEBGP6AJJPEAE@ZPEAX_N@Z`
- size: `319`
- prototype: `int(HRECOCONTEXT, unsigned int, const unsigned __int16 *, int (*)(int, unsigned __int8 *), void *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a7c80`
- `0x1800a8170`

## callees

- `0x180044ac6`
- `0x180083dc0`
- `0x180084e64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084ef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084ef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084f89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084f89`

## pseudocode

```c
__int64 __fastcall BackgroundSetFactoidOrConstraint(
        _QWORD *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        int (*a4)(int, unsigned __int8 *),
        void *a5,
        bool a6)
{
  __int64 v6; // rdi
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  SIZE_T v12; // rdi
  void *v13; // rax
  int v14; // edi
  void *v15; // rcx

  v6 = a2;
  if ( a2 > 0x7FFFFFFF )
    return 2147549183LL;
  if ( !a1 || !a3 && a2 || a2 >= 0x3FFFFFFF || 2 * a2 && !a3 )
    return 2147500035LL;
  if ( !a1[2] )
    return 2147746356LL;
  if ( !a6 && !*(_QWORD *)(*a1 + 152LL) )
    return 2147500033LL;
  v10 = CoTaskMemAlloc(0x20u);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  v10[1] = a5;
  *v10 = InkHResultSynchronousCallback;
  *((_DWORD *)v10 + 4) = v6;
  v10[3] = 0;
  if ( a3 )
  {
    v12 = 2 * v6;
    v13 = CoTaskMemAlloc(v12);
    v11[3] = v13;
    if ( !v13 )
    {
      CoTaskMemFree(v11);
      return 2147942414LL;
    }
    memcpy_0(v13, a3, v12);
  }
  v14 = AddToQueue(a1, a6 ? 13 : 23, v11);
  if ( v14 < 0 )
  {
    v15 = (void *)v11[3];
    if ( v15 )
      CoTaskMemFree(v15);
    CoTaskMemFree(v11);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180084e64  push    rbx
0x180084e66  push    rbp
0x180084e67  push    rsi
0x180084e68  push    rdi
0x180084e69  push    r14
0x180084e6b  sub     rsp, 20h
0x180084e6f  mov     edi, edx
0x180084e71  mov     rbp, r8
0x180084e74  mov     rsi, rcx
0x180084e77  cmp     edx, 7FFFFFFFh
0x180084e7d  jbe     short loc_180084E89
0x180084e7f  mov     eax, 8000FFFFh
0x180084e84  jmp     loc_180084F98
0x180084e89  test    rsi, rsi
0x180084e8c  jz      loc_180084F93
0x180084e92  test    rbp, rbp
0x180084e95  jnz     short loc_180084E9F
0x180084e97  test    edx, edx
0x180084e99  jnz     loc_180084F93
0x180084e9f  cmp     edi, 3FFFFFFFh
0x180084ea5  jnb     loc_180084F93
0x180084eab  lea     eax, [rdi+rdi]
0x180084eae  test    eax, eax
0x180084eb0  jz      short loc_180084EBB
0x180084eb2  test    rbp, rbp
0x180084eb5  jz      loc_180084F93
0x180084ebb  cmp     qword ptr [rcx+10h], 0
0x180084ec0  jnz     short loc_180084ECC
0x180084ec2  mov     eax, 80040234h
0x180084ec7  jmp     loc_180084F98
0x180084ecc  mov     r14b, [rsp+48h+arg_28]
0x180084ed1  test    r14b, r14b
0x180084ed4  jnz     short loc_180084EED
0x180084ed6  mov     rax, [rcx]
0x180084ed9  cmp     qword ptr [rax+98h], 0
0x180084ee1  jnz     short loc_180084EED
0x180084ee3  mov     eax, 80004001h
0x180084ee8  jmp     loc_180084F98
0x180084eed  mov     ecx, 20h ; ' '; cb
0x180084ef2  call    cs:__imp_CoTaskMemAlloc
0x180084ef8  mov     rbx, rax
0x180084efb  test    rax, rax
0x180084efe  jnz     short loc_180084F0A
0x180084f00  mov     eax, 8007000Eh
0x180084f05  jmp     loc_180084F98
0x180084f0a  mov     rax, [rsp+48h+arg_20]
0x180084f0f  mov     [rbx+8], rax
0x180084f13  lea     rax, ?InkHResultSynchronousCallback@@YAJJPEAE@Z; InkHResultSynchronousCallback(long,uchar *)
0x180084f1a  mov     [rbx], rax
0x180084f1d  mov     [rbx+10h], edi
0x180084f20  mov     qword ptr [rbx+18h], 0
0x180084f28  test    rbp, rbp
0x180084f2b  jz      short loc_180084F5B
0x180084f2d  add     rdi, rdi
0x180084f30  mov     rcx, rdi; cb
0x180084f33  call    cs:__imp_CoTaskMemAlloc
0x180084f39  mov     [rbx+18h], rax
0x180084f3d  test    rax, rax
0x180084f40  jnz     short loc_180084F4D
0x180084f42  mov     rcx, rbx; pv
0x180084f45  call    cs:__imp_CoTaskMemFree
0x180084f4b  jmp     short loc_180084F00
0x180084f4d  mov     r8, rdi; Size
0x180084f50  mov     rdx, rbp; Src
0x180084f53  mov     rcx, rax; void *
0x180084f56  call    memcpy_0
0x180084f5b  neg     r14b
0x180084f5e  mov     r8, rbx
0x180084f61  mov     rcx, rsi
0x180084f64  sbb     edx, edx
0x180084f66  and     edx, 0FFFFFFF6h
0x180084f69  add     edx, 17h
0x180084f6c  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x180084f71  mov     edi, eax
0x180084f73  test    eax, eax
0x180084f75  jns     short loc_180084F8F
0x180084f77  mov     rcx, [rbx+18h]; pv
0x180084f7b  test    rcx, rcx
0x180084f7e  jz      short loc_180084F86
0x180084f80  call    cs:__imp_CoTaskMemFree
0x180084f86  mov     rcx, rbx; pv
0x180084f89  call    cs:__imp_CoTaskMemFree
0x180084f8f  mov     eax, edi
0x180084f91  jmp     short loc_180084F98
0x180084f93  mov     eax, 80004003h
0x180084f98  add     rsp, 20h
0x180084f9c  pop     r14
0x180084f9e  pop     rdi
0x180084f9f  pop     rsi
0x180084fa0  pop     rbp
0x180084fa1  pop     rbx
0x180084fa2  retn
```

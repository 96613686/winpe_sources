# BackgroundSetEnabledUnicodeRanges(HRECOCONTEXT__ *,ulong,tagCHARACTER_RANGE const *,long (*)(long,uchar *),void *)

- ea: `0x180084d2c`
- end: `0x180084e5c`
- name: `?BackgroundSetEnabledUnicodeRanges@@YAJPEAUHRECOCONTEXT__@@KPEBUtagCHARACTER_RANGE@@P6AJJPEAE@ZPEAX@Z`
- size: `304`
- prototype: `int(HRECOCONTEXT, unsigned int, const struct tagCHARACTER_RANGE *, int (*)(int, unsigned __int8 *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a7ed0`

## callees

- `0x180044ac6`
- `0x180083dc0`
- `0x180084d2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e44`

## pseudocode

```c
__int64 __fastcall BackgroundSetEnabledUnicodeRanges(
        _QWORD *a1,
        unsigned int a2,
        const struct tagCHARACTER_RANGE *a3,
        int (*a4)(int, unsigned __int8 *),
        void *a5)
{
  __int64 v5; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  SIZE_T v11; // rdi
  void *v12; // rax
  int v13; // edi
  void *v14; // rcx

  v5 = a2;
  if ( a2 > 0x3FFFFFFF )
    return 2147549183LL;
  if ( !a1 || !a3 && a2 || a2 >= 0x1FFFFFFF || 4 * a2 && !a3 )
    return 2147500035LL;
  if ( !*(_QWORD *)(*a1 + 240LL) )
    return 2147500033LL;
  if ( !a1[2] )
    return 2147746356LL;
  v9 = CoTaskMemAlloc(0x20u);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  v9[1] = a5;
  *v9 = InkHResultSynchronousCallback;
  *((_DWORD *)v9 + 4) = v5;
  v9[3] = 0;
  if ( a3 )
  {
    v11 = 4 * v5;
    v12 = CoTaskMemAlloc(v11);
    v10[3] = v12;
    if ( !v12 )
    {
      CoTaskMemFree(v10);
      return 2147942414LL;
    }
    memcpy_0(v12, a3, v11);
  }
  v13 = AddToQueue(a1, 19, v10);
  if ( v13 < 0 )
  {
    v14 = (void *)v10[3];
    if ( v14 )
      CoTaskMemFree(v14);
    CoTaskMemFree(v10);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180084d2c  push    rbx
0x180084d2e  push    rbp
0x180084d2f  push    rsi
0x180084d30  push    rdi
0x180084d31  sub     rsp, 28h
0x180084d35  mov     edi, edx
0x180084d37  mov     rbp, r8
0x180084d3a  mov     rsi, rcx
0x180084d3d  cmp     edx, 3FFFFFFFh
0x180084d43  jbe     short loc_180084D4F
0x180084d45  mov     eax, 8000FFFFh
0x180084d4a  jmp     loc_180084E53
0x180084d4f  test    rsi, rsi
0x180084d52  jz      loc_180084E4E
0x180084d58  test    rbp, rbp
0x180084d5b  jnz     short loc_180084D65
0x180084d5d  test    edx, edx
0x180084d5f  jnz     loc_180084E4E
0x180084d65  cmp     edi, 1FFFFFFFh
0x180084d6b  jnb     loc_180084E4E
0x180084d71  lea     eax, ds:0[rdi*4]
0x180084d78  test    eax, eax
0x180084d7a  jz      short loc_180084D85
0x180084d7c  test    rbp, rbp
0x180084d7f  jz      loc_180084E4E
0x180084d85  mov     rax, [rcx]
0x180084d88  cmp     qword ptr [rax+0F0h], 0
0x180084d90  jnz     short loc_180084D9C
0x180084d92  mov     eax, 80004001h
0x180084d97  jmp     loc_180084E53
0x180084d9c  cmp     qword ptr [rcx+10h], 0
0x180084da1  jnz     short loc_180084DAD
0x180084da3  mov     eax, 80040234h
0x180084da8  jmp     loc_180084E53
0x180084dad  mov     ecx, 20h ; ' '; cb
0x180084db2  call    cs:__imp_CoTaskMemAlloc
0x180084db8  mov     rbx, rax
0x180084dbb  test    rax, rax
0x180084dbe  jnz     short loc_180084DCA
0x180084dc0  mov     eax, 8007000Eh
0x180084dc5  jmp     loc_180084E53
0x180084dca  mov     rax, [rsp+48h+arg_20]
0x180084dcf  mov     [rbx+8], rax
0x180084dd3  lea     rax, ?InkHResultSynchronousCallback@@YAJJPEAE@Z; InkHResultSynchronousCallback(long,uchar *)
0x180084dda  mov     [rbx], rax
0x180084ddd  mov     [rbx+10h], edi
0x180084de0  mov     qword ptr [rbx+18h], 0
0x180084de8  test    rbp, rbp
0x180084deb  jz      short loc_180084E1C
0x180084ded  shl     rdi, 2
0x180084df1  mov     rcx, rdi; cb
0x180084df4  call    cs:__imp_CoTaskMemAlloc
0x180084dfa  mov     [rbx+18h], rax
0x180084dfe  test    rax, rax
0x180084e01  jnz     short loc_180084E0E
0x180084e03  mov     rcx, rbx; pv
0x180084e06  call    cs:__imp_CoTaskMemFree
0x180084e0c  jmp     short loc_180084DC0
0x180084e0e  mov     r8, rdi; Size
0x180084e11  mov     rdx, rbp; Src
0x180084e14  mov     rcx, rax; void *
0x180084e17  call    memcpy_0
0x180084e1c  mov     r8, rbx
0x180084e1f  mov     edx, 13h
0x180084e24  mov     rcx, rsi
0x180084e27  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x180084e2c  mov     edi, eax
0x180084e2e  test    eax, eax
0x180084e30  jns     short loc_180084E4A
0x180084e32  mov     rcx, [rbx+18h]; pv
0x180084e36  test    rcx, rcx
0x180084e39  jz      short loc_180084E41
0x180084e3b  call    cs:__imp_CoTaskMemFree
0x180084e41  mov     rcx, rbx; pv
0x180084e44  call    cs:__imp_CoTaskMemFree
0x180084e4a  mov     eax, edi
0x180084e4c  jmp     short loc_180084E53
0x180084e4e  mov     eax, 80004003h
0x180084e53  add     rsp, 28h
0x180084e57  pop     rdi
0x180084e58  pop     rsi
0x180084e59  pop     rbp
0x180084e5a  pop     rbx
0x180084e5b  retn
```

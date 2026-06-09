# BackgroundSetTextContext(HRECOCONTEXT__ *,ulong,ushort const *,ulong,ushort const *,long (*)(long,uchar *),void *)

- ea: `0x180085060`
- end: `0x1800851ef`
- name: `?BackgroundSetTextContext@@YAJPEAUHRECOCONTEXT__@@KPEBGK1P6AJJPEAE@ZPEAX@Z`
- size: `399`
- prototype: `int(HRECOCONTEXT, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, int (*)(int, unsigned __int8 *), void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8400`
- `0x1800a87c0`

## callees

- `0x180044ac6`
- `0x180083dc0`
- `0x180085060`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008515d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800851c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800851cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008515d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800851c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800851cc`

## pseudocode

```c
__int64 __fastcall BackgroundSetTextContext(
        _QWORD *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int16 *Src,
        int (*a6)(int, unsigned __int8 *),
        void *a7)
{
  __int64 v7; // rsi
  __int64 v8; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rdi
  void *v14; // rax
  size_t v15; // rbx
  int v16; // ebx
  void *v17; // rcx

  v7 = a4;
  v8 = a2;
  if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFF || a2 > a2 + a4 )
    return 2147549183LL;
  if ( !a1 || !a3 && a2 || a2 >= 0x3FFFFFFF || 2 * a2 && !a3 || !Src && a4 || a4 >= 0x3FFFFFFF || 2 * a4 && !Src )
    return 2147500035LL;
  if ( !a1[2] )
    return 2147746356LL;
  v12 = CoTaskMemAlloc(0x20u);
  v13 = v12;
  if ( !v12 )
    return 2147942414LL;
  v12[3] = 0;
  *(_DWORD *)v12 = v8;
  *((_DWORD *)v12 + 1) = v7;
  if ( (_DWORD)v7 || (_DWORD)v8 )
  {
    v14 = CoTaskMemAlloc(2LL * (unsigned int)(v8 + v7));
    v13[3] = v14;
    if ( !v14 )
    {
      CoTaskMemFree(v13);
      return 2147942414LL;
    }
    v15 = 2 * v8;
    memcpy_0(v14, a3, v15);
    memcpy_0((void *)(v15 + v13[3]), Src, 2 * v7);
  }
  v13[1] = InkHResultSynchronousCallback;
  v13[2] = a7;
  v16 = AddToQueue(a1, 15, v13);
  if ( v16 < 0 )
  {
    v17 = (void *)v13[3];
    if ( v17 )
      CoTaskMemFree(v17);
    CoTaskMemFree(v13);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180085060  push    rbx
0x180085062  push    rbp
0x180085063  push    rsi
0x180085064  push    rdi
0x180085065  push    r12
0x180085067  push    r15
0x180085069  sub     rsp, 28h
0x18008506d  mov     eax, 7FFFFFFFh
0x180085072  mov     esi, r9d
0x180085075  mov     ebx, edx
0x180085077  mov     r15, r8
0x18008507a  mov     rbp, rcx
0x18008507d  cmp     edx, eax
0x18008507f  ja      loc_1800851DD
0x180085085  cmp     esi, eax
0x180085087  ja      loc_1800851DD
0x18008508d  lea     r12d, [rbx+rsi]
0x180085091  cmp     ebx, r12d
0x180085094  ja      loc_1800851DD
0x18008509a  test    rcx, rcx
0x18008509d  jz      loc_1800851D6
0x1800850a3  test    r8, r8
0x1800850a6  jnz     short loc_1800850B0
0x1800850a8  test    edx, edx
0x1800850aa  jnz     loc_1800851D6
0x1800850b0  mov     ecx, 3FFFFFFFh
0x1800850b5  cmp     ebx, ecx
0x1800850b7  jnb     loc_1800851D6
0x1800850bd  lea     eax, [rbx+rbx]
0x1800850c0  test    eax, eax
0x1800850c2  jz      short loc_1800850CD
0x1800850c4  test    r15, r15
0x1800850c7  jz      loc_1800851D6
0x1800850cd  cmp     [rsp+58h+Src], 0
0x1800850d6  jnz     short loc_1800850E1
0x1800850d8  test    r9d, r9d
0x1800850db  jnz     loc_1800851D6
0x1800850e1  cmp     esi, ecx
0x1800850e3  jnb     loc_1800851D6
0x1800850e9  lea     eax, [rsi+rsi]
0x1800850ec  test    eax, eax
0x1800850ee  jz      short loc_1800850FF
0x1800850f0  cmp     [rsp+58h+Src], 0
0x1800850f9  jz      loc_1800851D6
0x1800850ff  cmp     qword ptr [rbp+10h], 0
0x180085104  jnz     short loc_180085110
0x180085106  mov     eax, 80040234h
0x18008510b  jmp     loc_1800851E2
0x180085110  mov     ecx, 20h ; ' '; cb
0x180085115  call    cs:__imp_CoTaskMemAlloc
0x18008511b  mov     rdi, rax
0x18008511e  test    rax, rax
0x180085121  jnz     short loc_18008512D
0x180085123  mov     eax, 8007000Eh
0x180085128  jmp     loc_1800851E2
0x18008512d  mov     qword ptr [rax+18h], 0
0x180085135  mov     [rax], ebx
0x180085137  mov     [rax+4], esi
0x18008513a  test    esi, esi
0x18008513c  jnz     short loc_180085142
0x18008513e  test    ebx, ebx
0x180085140  jz      short loc_18008518D
0x180085142  mov     ecx, r12d
0x180085145  add     rcx, rcx; cb
0x180085148  call    cs:__imp_CoTaskMemAlloc
0x18008514e  mov     [rdi+18h], rax
0x180085152  mov     rcx, rax; void *
0x180085155  test    rax, rax
0x180085158  jnz     short loc_180085165
0x18008515a  mov     rcx, rdi; pv
0x18008515d  call    cs:__imp_CoTaskMemFree
0x180085163  jmp     short loc_180085123
0x180085165  add     rbx, rbx
0x180085168  mov     rdx, r15; Src
0x18008516b  mov     r8, rbx; Size
0x18008516e  call    memcpy_0
0x180085173  mov     rcx, [rdi+18h]
0x180085177  mov     r8, rsi
0x18008517a  mov     rdx, [rsp+58h+Src]; Src
0x180085182  add     r8, r8; Size
0x180085185  add     rcx, rbx; void *
0x180085188  call    memcpy_0
0x18008518d  lea     rax, ?InkHResultSynchronousCallback@@YAJJPEAE@Z; InkHResultSynchronousCallback(long,uchar *)
0x180085194  mov     r8, rdi
0x180085197  mov     [rdi+8], rax
0x18008519b  mov     edx, 0Fh
0x1800851a0  mov     rax, [rsp+58h+arg_30]
0x1800851a8  mov     rcx, rbp
0x1800851ab  mov     [rdi+10h], rax
0x1800851af  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x1800851b4  mov     ebx, eax
0x1800851b6  test    eax, eax
0x1800851b8  jns     short loc_1800851D2
0x1800851ba  mov     rcx, [rdi+18h]; pv
0x1800851be  test    rcx, rcx
0x1800851c1  jz      short loc_1800851C9
0x1800851c3  call    cs:__imp_CoTaskMemFree
0x1800851c9  mov     rcx, rdi; pv
0x1800851cc  call    cs:__imp_CoTaskMemFree
0x1800851d2  mov     eax, ebx
0x1800851d4  jmp     short loc_1800851E2
0x1800851d6  mov     eax, 80004003h
0x1800851db  jmp     short loc_1800851E2
0x1800851dd  mov     eax, 8000FFFFh
0x1800851e2  add     rsp, 28h
0x1800851e6  pop     r15
0x1800851e8  pop     r12
0x1800851ea  pop     rdi
0x1800851eb  pop     rsi
0x1800851ec  pop     rbp
0x1800851ed  pop     rbx
0x1800851ee  retn
```

# List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(ulong)

- ea: `0x180004c30`
- end: `0x180004d1d`
- name: `?CloneBackingStore@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@AEAAJK@Z`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001b20`
- `0x180004aac`

## callees

- `0x180001078`
- `0x1800010b8`
- `0x1800010c4`
- `0x180003498`
- `0x1800036a0`
- `0x180004b84`
- `0x180004bdc`
- `0x180004c30`

## pseudocode

```c
__int64 __fastcall List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(__int64 a1, unsigned int a2)
{
  unsigned int v2; // r12d
  __int64 v4; // rax
  bool v5; // cf
  unsigned __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _DWORD *v9; // rax
  _DWORD *v10; // r14
  unsigned int v11; // edi
  int v12; // r15d
  __int64 v13; // rbp
  struct IUnknown **v14; // rcx
  struct IUnknown *v15; // rdx

  v2 = *(_DWORD *)(a1 + 16);
  if ( a2 > v2 )
    v2 = a2;
  v4 = 8LL * v2;
  if ( !is_mul_ok(v2, 8u) )
    v4 = -1;
  v5 = __CFADD__(v4, 8);
  v6 = v4 + 8;
  if ( v5 )
    v6 = -1;
  v7 = operator new[](v6);
  if ( !v7 )
  {
    v8 = 0;
LABEL_16:
    v11 = -2147024882;
    goto LABEL_17;
  }
  v8 = v7 + 1;
  *v7 = v2;
  `vector constructor iterator'(v7 + 1, 8u, v2, InvasivePtr<XPathNodeIteratorBase>::InvasivePtr<XPathNodeIteratorBase>);
  if ( !v8 )
    goto LABEL_16;
  v9 = operator new(4u);
  v10 = v9;
  if ( !v9 )
    goto LABEL_16;
  v11 = 0;
  *v9 = 1;
  v12 = *(_DWORD *)(a1 + 20);
  v13 = 0;
  if ( v12 )
  {
    do
    {
      v14 = (struct IUnknown **)&v8[v13];
      v15 = *(struct IUnknown **)(*(_QWORD *)(a1 + 8) + 8 * v13);
      if ( *v14 != v15 )
        ATL::AtlComPtrAssign(v14, v15);
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < *(_DWORD *)(a1 + 20) );
  }
  List<ATL::CComPtr<XPathExpressionBase>>::Clear(a1);
  *(_QWORD *)(a1 + 8) = v8;
  v8 = 0;
  *(_QWORD *)a1 = v10;
  *(_DWORD *)(a1 + 16) = v2;
  *(_DWORD *)(a1 + 20) = v12;
LABEL_17:
  operator delete(0);
  if ( v8 )
    ATL::CComPtr<XPathExpressionBase>::`vector deleting destructor'(v8);
  return v11;
}

```

## disassembly

```asm
0x180004c30  push    rbx
0x180004c32  push    rbp
0x180004c33  push    rsi
0x180004c34  push    rdi
0x180004c35  push    r12
0x180004c37  push    r14
0x180004c39  push    r15
0x180004c3b  sub     rsp, 20h
0x180004c3f  mov     r12d, [rcx+10h]
0x180004c43  mov     ebp, 8
0x180004c48  cmp     edx, r12d
0x180004c4b  mov     rsi, rcx
0x180004c4e  mov     eax, ebp
0x180004c50  cmova   r12d, edx
0x180004c54  lea     rcx, [rbp-9]
0x180004c58  mov     edi, r12d
0x180004c5b  mul     rdi
0x180004c5e  cmovb   rax, rcx
0x180004c62  add     rax, rbp
0x180004c65  cmovb   rax, rcx
0x180004c69  mov     rcx, rax; unsigned __int64
0x180004c6c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180004c71  test    rax, rax
0x180004c74  jz      short loc_180004CF1
0x180004c76  lea     rbx, [rax+8]
0x180004c7a  mov     [rax], rdi
0x180004c7d  mov     rcx, rbx; void *
0x180004c80  lea     r9, ??0?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAA@XZ; void *(*)(void *)
0x180004c87  mov     r8d, edi; unsigned __int64
0x180004c8a  mov     edx, ebp; unsigned __int64
0x180004c8c  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180004c91  test    rbx, rbx
0x180004c94  jz      short loc_180004CF3
0x180004c96  lea     ecx, [rbp-4]; Size
0x180004c99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c9e  mov     r14, rax
0x180004ca1  test    rax, rax
0x180004ca4  jz      short loc_180004CF3
0x180004ca6  xor     edi, edi
0x180004ca8  mov     dword ptr [rax], 1
0x180004cae  mov     r15d, [rsi+14h]
0x180004cb2  xor     ebp, ebp
0x180004cb4  test    r15d, r15d
0x180004cb7  jz      short loc_180004CD6
0x180004cb9  mov     rax, [rsi+8]
0x180004cbd  lea     rcx, [rbx+rbp*8]; struct IUnknown **
0x180004cc1  mov     rdx, [rax+rbp*8]; struct IUnknown *
0x180004cc5  cmp     [rcx], rdx
0x180004cc8  jz      short loc_180004CCF
0x180004cca  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004ccf  inc     ebp
0x180004cd1  cmp     ebp, [rsi+14h]
0x180004cd4  jb      short loc_180004CB9
0x180004cd6  mov     rcx, rsi
0x180004cd9  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x180004cde  mov     [rsi+8], rbx
0x180004ce2  xor     ebx, ebx
0x180004ce4  mov     [rsi], r14
0x180004ce7  mov     [rsi+10h], r12d
0x180004ceb  mov     [rsi+14h], r15d
0x180004cef  jmp     short loc_180004CF8
0x180004cf1  xor     ebx, ebx
0x180004cf3  mov     edi, 8007000Eh
0x180004cf8  xor     ecx, ecx; Block
0x180004cfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004cff  test    rbx, rbx
0x180004d02  jz      short loc_180004D0C
0x180004d04  mov     rcx, rbx
0x180004d07  call    ??_E?$CComPtr@VXPathExpressionBase@@@ATL@@QEAAPEAXI@Z; ATL::CComPtr<XPathExpressionBase>::`vector deleting destructor'(uint)
0x180004d0c  mov     eax, edi
0x180004d0e  add     rsp, 20h
0x180004d12  pop     r15
0x180004d14  pop     r14
0x180004d16  pop     r12
0x180004d18  pop     rdi
0x180004d19  pop     rsi
0x180004d1a  pop     rbp
0x180004d1b  pop     rbx
0x180004d1c  retn
```

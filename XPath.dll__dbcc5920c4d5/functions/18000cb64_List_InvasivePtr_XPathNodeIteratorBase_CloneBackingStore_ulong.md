# List<InvasivePtr<XPathNodeIteratorBase>>::CloneBackingStore(ulong)

- ea: `0x18000cb64`
- end: `0x18000cc4c`
- name: `?CloneBackingStore@?$List@V?$InvasivePtr@VXPathNodeIteratorBase@@@@@@AEAAJK@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000ca88`

## callees

- `0x180001078`
- `0x1800010b8`
- `0x1800010c4`
- `0x1800036a0`
- `0x1800059d4`
- `0x180006918`
- `0x180008000`
- `0x18000cb64`

## pseudocode

```c
__int64 __fastcall List<InvasivePtr<XPathNodeIteratorBase>>::CloneBackingStore(__int64 a1, unsigned int a2)
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
LABEL_14:
    v11 = -2147024882;
    goto LABEL_15;
  }
  v8 = v7 + 1;
  *v7 = v2;
  `vector constructor iterator'(v7 + 1, 8u, v2, InvasivePtr<XPathNodeIteratorBase>::InvasivePtr<XPathNodeIteratorBase>);
  if ( !v8 )
    goto LABEL_14;
  v9 = operator new(4u);
  v10 = v9;
  if ( !v9 )
    goto LABEL_14;
  v11 = 0;
  *v9 = 1;
  v12 = *(_DWORD *)(a1 + 20);
  v13 = 0;
  if ( v12 )
  {
    do
    {
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        &v8[v13],
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v13));
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < *(_DWORD *)(a1 + 20) );
  }
  List<InvasivePtr<XPathNodeIteratorBase>>::Clear(a1);
  *(_QWORD *)(a1 + 8) = v8;
  v8 = 0;
  *(_QWORD *)a1 = v10;
  *(_DWORD *)(a1 + 16) = v2;
  *(_DWORD *)(a1 + 20) = v12;
LABEL_15:
  operator delete(0);
  if ( v8 )
    InvasivePtr<XPathNodeIteratorBase>::`vector deleting destructor'(v8);
  return v11;
}

```

## disassembly

```asm
0x18000cb64  push    rbx
0x18000cb66  push    rbp
0x18000cb67  push    rsi
0x18000cb68  push    rdi
0x18000cb69  push    r12
0x18000cb6b  push    r14
0x18000cb6d  push    r15
0x18000cb6f  sub     rsp, 20h
0x18000cb73  mov     r12d, [rcx+10h]
0x18000cb77  mov     ebp, 8
0x18000cb7c  cmp     edx, r12d
0x18000cb7f  mov     rsi, rcx
0x18000cb82  mov     eax, ebp
0x18000cb84  cmova   r12d, edx
0x18000cb88  lea     rcx, [rbp-9]
0x18000cb8c  mov     edi, r12d
0x18000cb8f  mul     rdi
0x18000cb92  cmovb   rax, rcx
0x18000cb96  add     rax, rbp
0x18000cb99  cmovb   rax, rcx
0x18000cb9d  mov     rcx, rax; unsigned __int64
0x18000cba0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000cba5  test    rax, rax
0x18000cba8  jz      short loc_18000CC20
0x18000cbaa  lea     rbx, [rax+8]
0x18000cbae  mov     [rax], rdi
0x18000cbb1  mov     rcx, rbx; void *
0x18000cbb4  lea     r9, ??0?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAA@XZ; void *(*)(void *)
0x18000cbbb  mov     r8d, edi; unsigned __int64
0x18000cbbe  mov     edx, ebp; unsigned __int64
0x18000cbc0  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18000cbc5  test    rbx, rbx
0x18000cbc8  jz      short loc_18000CC22
0x18000cbca  lea     ecx, [rbp-4]; Size
0x18000cbcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cbd2  mov     r14, rax
0x18000cbd5  test    rax, rax
0x18000cbd8  jz      short loc_18000CC22
0x18000cbda  xor     edi, edi
0x18000cbdc  mov     dword ptr [rax], 1
0x18000cbe2  mov     r15d, [rsi+14h]
0x18000cbe6  xor     ebp, ebp
0x18000cbe8  test    r15d, r15d
0x18000cbeb  jz      short loc_18000CC05
0x18000cbed  mov     rdx, [rsi+8]
0x18000cbf1  lea     rcx, [rbx+rbp*8]
0x18000cbf5  mov     rdx, [rdx+rbp*8]
0x18000cbf9  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x18000cbfe  inc     ebp
0x18000cc00  cmp     ebp, [rsi+14h]
0x18000cc03  jb      short loc_18000CBED
0x18000cc05  mov     rcx, rsi
0x18000cc08  call    ?Clear@?$List@V?$InvasivePtr@VXPathNodeIteratorBase@@@@@@QEAAXXZ; List<InvasivePtr<XPathNodeIteratorBase>>::Clear(void)
0x18000cc0d  mov     [rsi+8], rbx
0x18000cc11  xor     ebx, ebx
0x18000cc13  mov     [rsi], r14
0x18000cc16  mov     [rsi+10h], r12d
0x18000cc1a  mov     [rsi+14h], r15d
0x18000cc1e  jmp     short loc_18000CC27
0x18000cc20  xor     ebx, ebx
0x18000cc22  mov     edi, 8007000Eh
0x18000cc27  xor     ecx, ecx; Block
0x18000cc29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc2e  test    rbx, rbx
0x18000cc31  jz      short loc_18000CC3B
0x18000cc33  mov     rcx, rbx
0x18000cc36  call    ??_E?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAPEAXI@Z; InvasivePtr<XPathNodeIteratorBase>::`vector deleting destructor'(uint)
0x18000cc3b  mov     eax, edi
0x18000cc3d  add     rsp, 20h
0x18000cc41  pop     r15
0x18000cc43  pop     r14
0x18000cc45  pop     r12
0x18000cc47  pop     rdi
0x18000cc48  pop     rsi
0x18000cc49  pop     rbp
0x18000cc4a  pop     rbx
0x18000cc4b  retn
```

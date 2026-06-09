# CPropertyBag::Add(tagVARIANT *,ushort *)

- ea: `0x18000cab0`
- end: `0x18000cd38`
- name: `?Add@CPropertyBag@@UEAAJPEAUtagVARIANT@@PEAG@Z`
- size: `648`
- prototype: `int(CPropertyBag *__hidden this, struct tagVARIANT *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cab0`
- `0x18000d078`
- `0x18000d15c`
- `0x18000d38c`
- `0x18000d66c`
- `0x18000db24`
- `0x18000db98`
- `0x1800434ba`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000cbce`
- `OLEAUT32!__imp_VariantInit` at `0x18000cbce`
- `OLEAUT32!__imp_VariantCopy` at `0x18000cbda`
- `OLEAUT32!__imp_VariantCopy` at `0x18000cbda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cbb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cbb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cca3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cca3`

## pseudocode

```c
__int64 __fastcall CPropertyBag::Add(CPropertyBag *this, struct tagVARIANT *a2, unsigned __int16 *a3)
{
  unsigned int vt; // r9d
  unsigned int v7; // r9d
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  bool v12; // zf
  unsigned int v13; // r9d
  const OLECHAR *v14; // rdi
  __int64 v15; // rsi
  _DWORD *v16; // rax
  OLECHAR *v17; // rbp
  _DWORD *v18; // rax
  _DWORD *v19; // rsi
  unsigned int v20; // edx
  HRESULT v21; // ebx
  OLECHAR *v22; // rbx
  unsigned int v23; // edi
  OLECHAR *v25; // rcx
  unsigned int v26; // r9d
  unsigned int v27; // r9d
  unsigned int v28; // r9d
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  unsigned int v31; // r9d
  const OLECHAR *v32; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 || !a2 )
    return 2147942487LL;
  vt = a2->vt;
  if ( vt > 0xA )
  {
    v26 = vt - 11;
    if ( !v26 )
      goto LABEL_13;
    v27 = v26 - 3;
    if ( !v27 )
      goto LABEL_13;
    v28 = v27 - 2;
    if ( !v28 )
      goto LABEL_13;
    v29 = v28 - 1;
    if ( !v29 )
      goto LABEL_13;
    v30 = v29 - 1;
    if ( !v30 )
      goto LABEL_13;
    v31 = v30 - 1;
    if ( !v31 )
      goto LABEL_13;
    v13 = v31 - 3;
    v12 = v13 == 0;
  }
  else
  {
    if ( vt == 10 )
      goto LABEL_13;
    if ( !a2->vt )
      goto LABEL_13;
    v7 = vt - 2;
    if ( !v7 )
      goto LABEL_13;
    v8 = v7 - 1;
    if ( !v8 )
      goto LABEL_13;
    v9 = v8 - 1;
    if ( !v9 )
      goto LABEL_13;
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_13;
    v11 = v10 - 1;
    if ( !v11 )
      goto LABEL_13;
    v13 = v11 - 1;
    v12 = v13 == 0;
  }
  if ( !v12 && v13 != 1 )
    return 2147942487LL;
LABEL_13:
  v14 = &dword_180053104;
  v15 = -1;
  v32 = &dword_180053104;
  do
    ++v15;
  while ( a3[v15] );
  if ( (_DWORD)v15 )
  {
    if ( (int)v15 <= 0 )
    {
      v17 = (OLECHAR *)&dword_180053104;
    }
    else
    {
      v16 = CoTaskMemAlloc(2LL * (int)v15 + 14);
      if ( !v16 )
        return 2147942414LL;
      *v16 = 1;
      v14 = (const OLECHAR *)(v16 + 3);
      *((_WORD *)v16 + (int)v15 + 6) = 0;
      v16[1] = v15;
      v16[2] = v15;
      CString::Release((struct CStringData *)&qword_1800530F8);
      v17 = (OLECHAR *)v14;
    }
    memcpy_0(v17, a3, 2LL * (int)v15);
    *((_DWORD *)v17 - 2) = v15;
    v17[(int)v15] = 0;
  }
  else
  {
    CString::Release((CString *)&v32);
    v14 = v32;
  }
  v18 = CoTaskMemAlloc(0x20u);
  v19 = v18;
  if ( v18 )
  {
    v18[6] = 1;
    VariantInit((VARIANTARG *)v18);
    v21 = VariantCopy((VARIANTARG *)v19, a2);
    if ( v21 >= 0 )
    {
      UTSemReadWriteES::LockWrite((CPropertyBag *)((char *)this + 48));
      v22 = (OLECHAR *)(v14 - 6);
      if ( *((int *)v14 - 3) < 0 )
        v14 = &dword_180053104;
      else
        _InterlockedIncrement((volatile signed __int32 *)v14 - 3);
      v32 = v14;
      v23 = CMap<CString,unsigned short const *,RefCountedPointer<RefCountedVariant>,RefCountedVariant *>::SetAtWithActualKeyType(
              (char *)this + 8,
              &v32,
              v19);
      if ( _InterlockedExchangeAdd(v19 + 6, 0xFFFFFFFF) == 1 )
        RefCountedVariant::`scalar deleting destructor'((RefCountedVariant *)v19, 1u);
      UTSemReadWriteES::UnlockWrite((CPropertyBag *)((char *)this + 48));
      if ( v22 != (OLECHAR *)&qword_1800530F8
        && _InterlockedExchangeAdd((volatile signed __int32 *)v22, 0xFFFFFFFF) == 1 )
      {
        CoTaskMemFree(v22);
      }
      return v23;
    }
    RefCountedVariant::`scalar deleting destructor'((RefCountedVariant *)v19, v20);
  }
  else
  {
    v21 = -2147024882;
  }
  v25 = (OLECHAR *)(v14 - 6);
  if ( v14 - 6 != (const OLECHAR *)&qword_1800530F8
    && _InterlockedExchangeAdd((volatile signed __int32 *)v25, 0xFFFFFFFF) == 1 )
  {
    CoTaskMemFree(v25);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18000cab0  push    rbx
0x18000cab2  push    rbp
0x18000cab3  push    rsi
0x18000cab4  push    rdi
0x18000cab5  push    r12
0x18000cab7  push    r13
0x18000cab9  push    r14
0x18000cabb  push    r15
0x18000cabd  sub     rsp, 28h
0x18000cac1  xor     r12d, r12d
0x18000cac4  mov     r15, r8
0x18000cac7  mov     r14, rdx
0x18000caca  mov     r13, rcx
0x18000cacd  test    r8, r8
0x18000cad0  jz      loc_18000CC6C
0x18000cad6  test    rdx, rdx
0x18000cad9  jz      loc_18000CC6C
0x18000cadf  movzx   r9d, word ptr [rdx]
0x18000cae3  cmp     r9d, 0Ah
0x18000cae7  ja      loc_18000CCCC
0x18000caed  jz      short loc_18000CB1C
0x18000caef  test    r9d, r9d
0x18000caf2  jz      short loc_18000CB1C
0x18000caf4  sub     r9d, 2
0x18000caf8  jz      short loc_18000CB1C
0x18000cafa  sub     r9d, 1
0x18000cafe  jz      short loc_18000CB1C
0x18000cb00  sub     r9d, 1
0x18000cb04  jz      short loc_18000CB1C
0x18000cb06  sub     r9d, 1
0x18000cb0a  jz      short loc_18000CB1C
0x18000cb0c  sub     r9d, 1
0x18000cb10  jz      short loc_18000CB1C
0x18000cb12  sub     r9d, 1
0x18000cb16  jnz     loc_18000CCC0
0x18000cb1c  lea     rdi, dword_180053104
0x18000cb23  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000cb27  mov     [rsp+68h+arg_10], rdi
0x18000cb2f  inc     rsi
0x18000cb32  cmp     [r8+rsi*2], r12w
0x18000cb37  jnz     short loc_18000CB2F
0x18000cb39  lea     rbp, qword_1800530F8
0x18000cb40  test    esi, esi
0x18000cb42  jz      loc_18000CD11
0x18000cb48  jle     loc_18000CC7D
0x18000cb4e  movsxd  rbx, esi
0x18000cb51  lea     rcx, ds:0Eh[rbx*2]; cb
0x18000cb59  call    cs:__imp_CoTaskMemAlloc
0x18000cb5f  test    rax, rax
0x18000cb62  jz      loc_18000CCB9
0x18000cb68  mov     dword ptr [rax], 1
0x18000cb6e  lea     rdi, [rax+0Ch]
0x18000cb72  mov     [rax+rbx*2+0Ch], r12w
0x18000cb78  mov     rcx, rbp; struct CStringData *
0x18000cb7b  mov     [rax+4], esi
0x18000cb7e  mov     [rax+8], esi
0x18000cb81  call    ?Release@CString@@KAXPEAUCStringData@@@Z; CString::Release(CStringData *)
0x18000cb86  mov     rbp, rdi
0x18000cb89  movsxd  rax, esi
0x18000cb8c  mov     rdx, r15; Src
0x18000cb8f  mov     rcx, rbp; void *
0x18000cb92  lea     rbx, [rax+rax]
0x18000cb96  mov     r8, rbx; Size
0x18000cb99  call    memcpy_0
0x18000cb9e  mov     [rbp-8], esi
0x18000cba1  mov     [rbx+rbp], r12w
0x18000cba6  lea     rbp, qword_1800530F8
0x18000cbad  mov     ecx, 20h ; ' '; cb
0x18000cbb2  call    cs:__imp_CoTaskMemAlloc
0x18000cbb8  mov     rsi, rax
0x18000cbbb  test    rax, rax
0x18000cbbe  jz      loc_18000CC89
0x18000cbc4  mov     rcx, rax; pvarg
0x18000cbc7  mov     dword ptr [rax+18h], 1
0x18000cbce  call    cs:__imp_VariantInit
0x18000cbd4  mov     rdx, r14; pvargSrc
0x18000cbd7  mov     rcx, rsi; pvargDest
0x18000cbda  call    cs:__imp_VariantCopy
0x18000cbe0  mov     ebx, eax
0x18000cbe2  test    eax, eax
0x18000cbe4  js      loc_18000CD2B
0x18000cbea  lea     rcx, [r13+30h]; this
0x18000cbee  call    ?LockWrite@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::LockWrite(void)
0x18000cbf3  lea     rbx, [rdi-0Ch]
0x18000cbf7  cmp     [rbx], r12d
0x18000cbfa  jl      loc_18000CCAD
0x18000cc00  lock inc dword ptr [rdi-0Ch]
0x18000cc04  lea     rcx, [r13+8]
0x18000cc08  mov     [rsp+68h+arg_10], rdi
0x18000cc10  mov     r8, rsi
0x18000cc13  lea     rdx, [rsp+68h+arg_10]
0x18000cc1b  call    ?SetAtWithActualKeyType@?$CMap@VCString@@PEBGV?$RefCountedPointer@URefCountedVariant@@@@PEAURefCountedVariant@@@@QEAAJVCString@@PEAURefCountedVariant@@@Z; CMap<CString,ushort const *,RefCountedPointer<RefCountedVariant>,RefCountedVariant *>::SetAtWithActualKeyType(CString,RefCountedVariant *)
0x18000cc20  mov     edi, eax
0x18000cc22  or      edx, 0FFFFFFFFh
0x18000cc25  lock xadd [rsi+18h], edx; unsigned int
0x18000cc2a  cmp     edx, 1
0x18000cc2d  jz      short loc_18000CC73
0x18000cc2f  lea     rcx, [r13+30h]; this
0x18000cc33  call    ?UnlockWrite@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::UnlockWrite(void)
0x18000cc38  lea     rax, qword_1800530F8
0x18000cc3f  cmp     rbx, rax
0x18000cc42  jz      short loc_18000CC59
0x18000cc44  or      eax, 0FFFFFFFFh
0x18000cc47  lock xadd [rbx], eax
0x18000cc4b  cmp     eax, 1
0x18000cc4e  jnz     short loc_18000CC59
0x18000cc50  mov     rcx, rbx; pv
0x18000cc53  call    cs:__imp_CoTaskMemFree
0x18000cc59  mov     eax, edi
0x18000cc5b  add     rsp, 28h
0x18000cc5f  pop     r15
0x18000cc61  pop     r14
0x18000cc63  pop     r13
0x18000cc65  pop     r12
0x18000cc67  pop     rdi
0x18000cc68  pop     rsi
0x18000cc69  pop     rbp
0x18000cc6a  pop     rbx
0x18000cc6b  retn
0x18000cc6c  mov     eax, 80070057h
0x18000cc71  jmp     short loc_18000CC5B
0x18000cc73  mov     rcx, rsi; this
0x18000cc76  call    ??_GRefCountedVariant@@AEAAPEAXI@Z; RefCountedVariant::`scalar deleting destructor'(uint)
0x18000cc7b  jmp     short loc_18000CC2F
0x18000cc7d  lea     rbp, dword_180053104
0x18000cc84  jmp     loc_18000CB89
0x18000cc89  mov     ebx, 8007000Eh
0x18000cc8e  lea     rcx, [rdi-0Ch]; pv
0x18000cc92  cmp     rcx, rbp
0x18000cc95  jz      short loc_18000CCA9
0x18000cc97  or      edx, 0FFFFFFFFh
0x18000cc9a  lock xadd [rcx], edx
0x18000cc9e  cmp     edx, 1
0x18000cca1  jnz     short loc_18000CCA9
0x18000cca3  call    cs:__imp_CoTaskMemFree
0x18000cca9  mov     eax, ebx
0x18000ccab  jmp     short loc_18000CC5B
0x18000ccad  lea     rdi, dword_180053104
0x18000ccb4  jmp     loc_18000CC04
0x18000ccb9  mov     eax, 8007000Eh
0x18000ccbe  jmp     short loc_18000CC5B
0x18000ccc0  cmp     r9d, 1
0x18000ccc4  jz      loc_18000CB1C
0x18000ccca  jmp     short loc_18000CC6C
0x18000cccc  sub     r9d, 0Bh
0x18000ccd0  jz      loc_18000CB1C
0x18000ccd6  sub     r9d, 3
0x18000ccda  jz      loc_18000CB1C
0x18000cce0  sub     r9d, 2
0x18000cce4  jz      loc_18000CB1C
0x18000ccea  sub     r9d, 1
0x18000ccee  jz      loc_18000CB1C
0x18000ccf4  sub     r9d, 1
0x18000ccf8  jz      loc_18000CB1C
0x18000ccfe  sub     r9d, 1
0x18000cd02  jz      loc_18000CB1C
0x18000cd08  sub     r9d, 3
0x18000cd0c  jmp     loc_18000CB16
0x18000cd11  lea     rcx, [rsp+68h+arg_10]; this
0x18000cd19  call    ?Release@CString@@IEAAXXZ; CString::Release(void)
0x18000cd1e  mov     rdi, [rsp+68h+arg_10]
0x18000cd26  jmp     loc_18000CBAD
0x18000cd2b  mov     rcx, rsi; this
0x18000cd2e  call    ??_GRefCountedVariant@@AEAAPEAXI@Z; RefCountedVariant::`scalar deleting destructor'(uint)
0x18000cd33  jmp     loc_18000CC8E
```

# VBProperty::put_IndexedValue(tagVARIANT,tagVARIANT,tagVARIANT,tagVARIANT,tagVARIANT)

- ea: `0x1800a158c`
- end: `0x1800a1769`
- name: `?put_IndexedValue@VBProperty@@UEAAJUtagVARIANT@@0000@Z`
- size: `477`
- prototype: `__int64 __fastcall(VBProperty *__hidden this, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180096978`
- `0x1800969b8`
- `0x180096ab0`
- `0x1800a158c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a1662`
- `OLEAUT32!__imp_VariantInit` at `0x1800a1702`
- `OLEAUT32!__imp_VariantInit` at `0x1800a1662`
- `OLEAUT32!__imp_VariantInit` at `0x1800a1702`
- `OLEAUT32!__imp_VariantClear` at `0x1800a173a`
- `OLEAUT32!__imp_VariantClear` at `0x1800a173a`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1679`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1688`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1697`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a16a6`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1710`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1679`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1688`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1697`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a16a6`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1710`

## pseudocode

```c
__int64 __fastcall VBProperty::put_IndexedValue(
        VBProperty *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6)
{
  VBDispatch *v7; // r14
  int v8; // edi
  __int64 v9; // rsi
  __int64 v10; // r12
  VARIANTARG *p_pvarg; // rbx
  __int64 v12; // r11
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rax
  unsigned int v14; // edi
  VARIANTARG *v15; // rbx
  VARIANTARG *v16; // rbx
  VARIANTARG v18; // [rsp+20h] [rbp-E0h] BYREF
  VARIANTARG v19; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v20; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v21; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvargSrc; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvargDest; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v25; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v26; // [rsp+E8h] [rbp-18h] BYREF
  VARIANTARG v27; // [rsp+100h] [rbp+0h] BYREF

  v19 = *a2;
  v7 = (VBProperty *)((char *)this + 8);
  v8 = 0;
  v18 = *a3;
  v20 = *a4;
  pvargSrc = *a5;
  v21 = *a6;
  VBDispatch::EnterOleFunc((VBProperty *)((char *)this + 8));
  v9 = 5;
  v10 = 5;
  p_pvarg = &pvarg;
  do
  {
    VariantInit(p_pvarg++);
    --v10;
  }
  while ( v10 );
  VariantCopy(&pvargDest, &pvargSrc);
  VariantCopy(&v25, &v20);
  VariantCopy(&v26, &v18);
  VariantCopy(&v27, &v19);
  v12 = 1;
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvargDest.llVal;
  do
  {
    if ( *((_WORD *)&p_llVal[-1].scode + 4) == 10 && p_llVal->lVal == -2147352572 )
    {
      if ( v8 )
        goto LABEL_11;
    }
    else
    {
      ++v8;
    }
    ++v12;
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)((char *)p_llVal + 24);
  }
  while ( v12 <= 4 );
  if ( v8 != *((_DWORD *)this + 19) )
  {
LABEL_11:
    v14 = VBDispatch::RaiseException(v7, 5u);
    goto LABEL_13;
  }
  v15 = &pvarg + (unsigned int)(4 - v8);
  VariantInit(v15);
  VariantCopy(v15, &v21);
  v14 = (*(__int64 (__fastcall **)(VBProperty *, _QWORD, VARIANTARG *))(*(_QWORD *)this + 160LL))(
          this,
          (unsigned int)(v8 + 1),
          v15);
  VBDispatch::ExitOleFunc(v7);
LABEL_13:
  v16 = &pvarg;
  do
  {
    VariantClear(v16++);
    --v9;
  }
  while ( v9 );
  return v14;
}

```

## disassembly

```asm
0x1800a158c  push    rbp
0x1800a158e  push    rbx
0x1800a158f  push    rsi
0x1800a1590  push    rdi
0x1800a1591  push    r12
0x1800a1593  push    r14
0x1800a1595  push    r15
0x1800a1597  lea     rbp, [rsp-30h]
0x1800a159c  mov     eax, 130h
0x1800a15a1  call    _alloca_probe
0x1800a15a6  sub     rsp, rax
0x1800a15a9  mov     rax, cs:__security_cookie
0x1800a15b0  xor     rax, rsp
0x1800a15b3  mov     [rbp+60h+var_40], rax
0x1800a15b7  mov     rax, [rdx]
0x1800a15ba  mov     r15, rcx
0x1800a15bd  mov     rcx, [rbp+60h+arg_20]
0x1800a15c4  mov     qword ptr [rsp+160h+var_128], rax
0x1800a15c9  mov     rax, [rdx+8]
0x1800a15cd  lea     r14, [r15+8]
0x1800a15d1  mov     qword ptr [rsp+160h+var_128+8], rax
0x1800a15d6  mov     rax, [rdx+10h]
0x1800a15da  xor     edi, edi
0x1800a15dc  mov     qword ptr [rsp+160h+var_128+10h], rax
0x1800a15e1  mov     rax, [r8]
0x1800a15e4  mov     qword ptr [rsp+160h+var_140], rax
0x1800a15e9  mov     rax, [r8+8]
0x1800a15ed  mov     qword ptr [rsp+160h+var_140+8], rax
0x1800a15f2  mov     rax, [r8+10h]
0x1800a15f6  mov     qword ptr [rsp+160h+var_140+10h], rax
0x1800a15fb  mov     rax, [r9]
0x1800a15fe  mov     qword ptr [rsp+160h+var_110], rax
0x1800a1603  mov     rax, [r9+8]
0x1800a1607  mov     qword ptr [rsp+160h+var_110+8], rax
0x1800a160c  mov     rax, [r9+10h]
0x1800a1610  mov     qword ptr [rsp+160h+var_110+10h], rax
0x1800a1615  mov     rax, [rcx]
0x1800a1618  mov     qword ptr [rbp+60h+pvargSrc], rax
0x1800a161c  mov     rax, [rcx+8]
0x1800a1620  mov     qword ptr [rbp+60h+pvargSrc+8], rax
0x1800a1624  mov     rax, [rcx+10h]
0x1800a1628  mov     rcx, [rbp+60h+arg_28]
0x1800a162f  mov     qword ptr [rbp+60h+pvargSrc+10h], rax
0x1800a1633  mov     rax, [rcx]
0x1800a1636  mov     qword ptr [rsp+160h+var_F8], rax
0x1800a163b  mov     rax, [rcx+8]
0x1800a163f  mov     qword ptr [rsp+160h+var_F8+8], rax
0x1800a1644  mov     rax, [rcx+10h]
0x1800a1648  mov     rcx, r14; this
0x1800a164b  mov     qword ptr [rsp+160h+var_F8+10h], rax
0x1800a1650  call    ?EnterOleFunc@VBDispatch@@QEAAXXZ; VBDispatch::EnterOleFunc(void)
0x1800a1655  lea     esi, [rdi+5]
0x1800a1658  mov     r12d, esi
0x1800a165b  lea     rbx, [rbp+60h+pvarg]
0x1800a165f  mov     rcx, rbx; pvarg
0x1800a1662  call    cs:__imp_VariantInit
0x1800a1668  add     rbx, 18h
0x1800a166c  dec     r12
0x1800a166f  jnz     short loc_1800A165F
0x1800a1671  lea     rdx, [rbp+60h+pvargSrc]; pvargSrc
0x1800a1675  lea     rcx, [rbp+60h+pvargDest]; pvargDest
0x1800a1679  call    cs:__imp_VariantCopy
0x1800a167f  lea     rdx, [rsp+160h+var_110]; pvargSrc
0x1800a1684  lea     rcx, [rbp+60h+var_90]; pvargDest
0x1800a1688  call    cs:__imp_VariantCopy
0x1800a168e  lea     rdx, [rsp+160h+var_140]; pvargSrc
0x1800a1693  lea     rcx, [rbp+60h+var_78]; pvargDest
0x1800a1697  call    cs:__imp_VariantCopy
0x1800a169d  lea     rdx, [rsp+160h+var_128]; pvargSrc
0x1800a16a2  lea     rcx, [rbp+60h+var_60]; pvargDest
0x1800a16a6  call    cs:__imp_VariantCopy
0x1800a16ac  lea     r11d, [r12+1]
0x1800a16b1  lea     rax, [rbp+60h+pvargDest+8]
0x1800a16b5  lea     ecx, [r12+4]
0x1800a16ba  cmp     word ptr [rax-8], 0Ah
0x1800a16bf  jnz     short loc_1800A16CF
0x1800a16c1  cmp     dword ptr [rax], 80020004h
0x1800a16c7  jnz     short loc_1800A16CF
0x1800a16c9  test    edi, edi
0x1800a16cb  jnz     short loc_1800A16E3
0x1800a16cd  jmp     short loc_1800A16D1
0x1800a16cf  inc     edi
0x1800a16d1  inc     r11
0x1800a16d4  add     rax, 18h
0x1800a16d8  cmp     r11, rcx
0x1800a16db  jle     short loc_1800A16BA
0x1800a16dd  cmp     edi, [r15+4Ch]
0x1800a16e1  jz      short loc_1800A16F1
0x1800a16e3  mov     edx, esi; unsigned int
0x1800a16e5  mov     rcx, r14; this
0x1800a16e8  call    ?RaiseException@VBDispatch@@IEAAJI@Z; VBDispatch::RaiseException(uint)
0x1800a16ed  mov     edi, eax
0x1800a16ef  jmp     short loc_1800A1733
0x1800a16f1  sub     ecx, edi
0x1800a16f3  lea     rbx, [rbp+60h+pvarg]
0x1800a16f7  lea     rdx, [rcx+rcx*2]
0x1800a16fb  lea     rbx, [rbx+rdx*8]
0x1800a16ff  mov     rcx, rbx; pvarg
0x1800a1702  call    cs:__imp_VariantInit
0x1800a1708  lea     rdx, [rsp+160h+var_F8]; pvargSrc
0x1800a170d  mov     rcx, rbx; pvargDest
0x1800a1710  call    cs:__imp_VariantCopy
0x1800a1716  mov     r11, [r15]
0x1800a1719  lea     edx, [rdi+1]
0x1800a171c  mov     r8, rbx
0x1800a171f  mov     rcx, r15
0x1800a1722  call    qword ptr [r11+0A0h]
0x1800a1729  mov     rcx, r14; this
0x1800a172c  mov     edi, eax
0x1800a172e  call    ?ExitOleFunc@VBDispatch@@QEAAXXZ; VBDispatch::ExitOleFunc(void)
0x1800a1733  lea     rbx, [rbp+60h+pvarg]
0x1800a1737  mov     rcx, rbx; pvarg
0x1800a173a  call    cs:__imp_VariantClear
0x1800a1740  add     rbx, 18h
0x1800a1744  dec     rsi
0x1800a1747  jnz     short loc_1800A1737
0x1800a1749  mov     eax, edi
0x1800a174b  mov     rcx, [rbp+60h+var_40]
0x1800a174f  xor     rcx, rsp; StackCookie
0x1800a1752  call    __security_check_cookie
0x1800a1757  add     rsp, 130h
0x1800a175e  pop     r15
0x1800a1760  pop     r14
0x1800a1762  pop     r12
0x1800a1764  pop     rdi
0x1800a1765  pop     rsi
0x1800a1766  pop     rbx
0x1800a1767  pop     rbp
0x1800a1768  retn
```

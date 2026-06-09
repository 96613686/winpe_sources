# CCodecOptionsPropertyBag::Write(ulong,tagPROPBAG2 *,tagVARIANT *)

- ea: `0x180031560`
- end: `0x1800316ea`
- name: `?Write@CCodecOptionsPropertyBag@@UEAAJKPEAUtagPROPBAG2@@PEAUtagVARIANT@@@Z`
- size: `394`
- prototype: `int(CCodecOptionsPropertyBag *__hidden this, unsigned int, struct tagPROPBAG2 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180031560`
- `0x1800319d0`
- `0x1800319f0`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180031605`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180031605`
- `OLEAUT32!__imp_VariantClear` at `0x180031634`
- `OLEAUT32!__imp_VariantClear` at `0x180031634`
- `OLEAUT32!__imp_VariantCopy` at `0x18003164d`
- `OLEAUT32!__imp_VariantCopy` at `0x18003164d`

## pseudocode

```c
__int64 __fastcall CCodecOptionsPropertyBag::Write(
        CCodecOptionsPropertyBag *this,
        unsigned int a2,
        struct tagPROPBAG2 *a3,
        struct tagVARIANT *a4)
{
  CMTALock *v4; // rbx
  unsigned int v9; // eax
  HRESULT v10; // edi
  int v11; // r12d
  __int64 v13; // rsi
  unsigned int i; // r15d
  DWORD dwHint; // eax
  const WCHAR *pstrName; // rcx
  const WCHAR *v17; // rdx
  HRESULT v18; // eax
  int v19; // eax
  int v20; // ecx
  bool v21; // zf
  unsigned int v22; // [rsp+60h] [rbp+8h]

  v4 = (CCodecOptionsPropertyBag *)((char *)this - 56);
  CMTALock::Enter((CCodecOptionsPropertyBag *)((char *)this - 56));
  if ( a3 && a4 )
  {
    v9 = *((_DWORD *)this + 8);
    v10 = 0;
    v11 = 0;
    v22 = v9;
    if ( !a2 )
      goto LABEL_4;
LABEL_7:
    v13 = *((_QWORD *)this + 1);
    for ( i = 0; ; ++i )
    {
      if ( i >= v9 )
      {
        v19 = (int)g_doStackCaptures;
LABEL_19:
        if ( i == v22 )
        {
          v10 = -2147467259;
          v21 = v19 == 0;
          goto LABEL_29;
        }
        if ( ++v11 >= a2 )
          goto LABEL_4;
        v9 = v22;
        ++a3;
        ++a4;
        goto LABEL_7;
      }
      dwHint = a3->dwHint;
      if ( dwHint == *(_DWORD *)(v13 + 8) )
      {
        if ( dwHint )
          break;
      }
      if ( !dwHint )
      {
        pstrName = a3->pstrName;
        if ( pstrName )
        {
          v17 = *(const WCHAR **)(v13 + 16);
          if ( v17 )
          {
            if ( !lstrcmpW(pstrName, v17) )
              break;
          }
        }
      }
      v9 = v22;
      v13 += 72;
    }
    if ( *(_WORD *)(v13 + 4) != a4->vt )
    {
      v10 = -2003292274;
      goto LABEL_28;
    }
    v18 = VariantClear((VARIANTARG *)(v13 + 40));
    v10 = v18;
    if ( v18 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_4;
      v20 = v18;
      goto LABEL_24;
    }
    v10 = VariantCopy((VARIANTARG *)(v13 + 40), a4);
    v19 = (int)g_doStackCaptures;
    if ( v10 >= 0 )
      goto LABEL_19;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_4;
LABEL_23:
    v20 = v10;
LABEL_24:
    DoStackCapture(v20);
    goto LABEL_4;
  }
  v10 = -2147024809;
LABEL_28:
  v21 = (_DWORD)g_doStackCaptures == 0;
LABEL_29:
  if ( !v21 )
    goto LABEL_23;
LABEL_4:
  if ( v4 )
    CMTALock::Leave(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180031560  mov     [rsp+arg_10], rbx
0x180031565  mov     [rsp+arg_8], edx
0x180031569  push    rbp
0x18003156a  push    rsi
0x18003156b  push    rdi
0x18003156c  push    r12
0x18003156e  push    r13
0x180031570  push    r14
0x180031572  push    r15
0x180031574  sub     rsp, 20h
0x180031578  lea     rbx, [rcx-38h]
0x18003157c  mov     r13, rcx
0x18003157f  mov     rcx, rbx; this
0x180031582  mov     r14, r9
0x180031585  mov     rbp, r8
0x180031588  mov     esi, edx
0x18003158a  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18003158f  test    rbp, rbp
0x180031592  jz      loc_1800316D2
0x180031598  test    r14, r14
0x18003159b  jz      loc_1800316D2
0x1800315a1  mov     eax, [r13+20h]
0x1800315a5  xor     edi, edi
0x1800315a7  xor     r12d, r12d
0x1800315aa  mov     [rsp+58h+arg_0], eax
0x1800315ae  test    esi, esi
0x1800315b0  jnz     short loc_1800315D7
0x1800315b2  test    rbx, rbx
0x1800315b5  jz      short loc_1800315BF
0x1800315b7  mov     rcx, rbx; this
0x1800315ba  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x1800315bf  mov     rbx, [rsp+58h+arg_10]
0x1800315c4  mov     eax, edi
0x1800315c6  add     rsp, 20h
0x1800315ca  pop     r15
0x1800315cc  pop     r14
0x1800315ce  pop     r13
0x1800315d0  pop     r12
0x1800315d2  pop     rdi
0x1800315d3  pop     rsi
0x1800315d4  pop     rbp
0x1800315d5  retn
0x1800315d7  mov     rsi, [r13+8]
0x1800315db  xor     r15d, r15d
0x1800315de  cmp     r15d, eax
0x1800315e1  jnb     loc_1800316D9
0x1800315e7  mov     eax, [rbp+8]
0x1800315ea  cmp     eax, [rsi+8]
0x1800315ed  jz      short loc_180031622
0x1800315ef  test    eax, eax
0x1800315f1  jnz     short loc_180031615
0x1800315f3  mov     rcx, [rbp+10h]; lpString1
0x1800315f7  test    rcx, rcx
0x1800315fa  jz      short loc_180031615
0x1800315fc  mov     rdx, [rsi+10h]; lpString2
0x180031600  test    rdx, rdx
0x180031603  jz      short loc_180031615
0x180031605  call    cs:__imp_lstrcmpW
0x18003160c  nop     dword ptr [rax+rax+00h]
0x180031611  test    eax, eax
0x180031613  jz      short loc_180031626
0x180031615  mov     eax, [rsp+58h+arg_0]
0x180031619  inc     r15d
0x18003161c  add     rsi, 48h ; 'H'
0x180031620  jmp     short loc_1800315DE
0x180031622  test    eax, eax
0x180031624  jz      short loc_1800315EF
0x180031626  movzx   eax, word ptr [r14]
0x18003162a  cmp     [rsi+4], ax
0x18003162e  jnz     short loc_1800316A8
0x180031630  lea     rcx, [rsi+28h]; pvarg
0x180031634  call    cs:__imp_VariantClear
0x18003163b  nop     dword ptr [rax+rax+00h]
0x180031640  mov     edi, eax
0x180031642  test    eax, eax
0x180031644  js      short loc_18003169B
0x180031646  mov     rdx, r14; pvargSrc
0x180031649  lea     rcx, [rsi+28h]; pvargDest
0x18003164d  call    cs:__imp_VariantCopy
0x180031654  nop     dword ptr [rax+rax+00h]
0x180031659  mov     edi, eax
0x18003165b  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180031661  test    edi, edi
0x180031663  js      short loc_18003168B
0x180031665  cmp     r15d, [rsp+58h+arg_0]
0x18003166a  jz      short loc_1800316E1
0x18003166c  inc     r12d
0x18003166f  cmp     r12d, [rsp+58h+arg_8]
0x180031674  jnb     loc_1800315B2
0x18003167a  mov     eax, [rsp+58h+arg_0]
0x18003167e  add     rbp, 28h ; '('
0x180031682  add     r14, 18h
0x180031686  jmp     loc_1800315D7
0x18003168b  test    eax, eax
0x18003168d  jz      short loc_1800316BB
0x18003168f  mov     ecx, edi; int
0x180031691  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180031696  jmp     loc_1800315B2
0x18003169b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800316a2  jz      short loc_1800316C5
0x1800316a4  mov     ecx, eax
0x1800316a6  jmp     short loc_180031691
0x1800316a8  mov     edi, 88982F8Eh
0x1800316ad  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800316b4  jnz     short loc_18003168F
0x1800316b6  jmp     loc_1800315B2
0x1800316bb  test    edi, edi
0x1800316bd  js      loc_1800315B2
0x1800316c3  jmp     short loc_180031665
0x1800316c5  test    eax, eax
0x1800316c7  jns     loc_180031646
0x1800316cd  jmp     loc_1800315B2
0x1800316d2  mov     edi, 80070057h
0x1800316d7  jmp     short loc_1800316AD
0x1800316d9  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800316df  jmp     short loc_180031665
0x1800316e1  mov     edi, 80004005h
0x1800316e6  test    eax, eax
0x1800316e8  jmp     short loc_1800316B4
```

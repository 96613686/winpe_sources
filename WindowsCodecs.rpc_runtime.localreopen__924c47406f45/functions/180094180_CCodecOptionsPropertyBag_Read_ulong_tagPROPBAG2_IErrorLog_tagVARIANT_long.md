# CCodecOptionsPropertyBag::Read(ulong,tagPROPBAG2 *,IErrorLog *,tagVARIANT *,long *)

- ea: `0x180094180`
- end: `0x1800942cd`
- name: `?Read@CCodecOptionsPropertyBag@@UEAAJKPEAUtagPROPBAG2@@PEAUIErrorLog@@PEAUtagVARIANT@@PEAJ@Z`
- size: `333`
- prototype: `__int64 __fastcall(CCodecOptionsPropertyBag *__hidden this, unsigned int, struct tagPROPBAG2 *, struct IErrorLog *, VARIANTARG *pvarg, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180032d50`
- `0x180032d70`
- `0x180094180`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800942bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800942bd`
- `OLEAUT32!__imp_VariantInit` at `0x1800941fc`
- `OLEAUT32!__imp_VariantInit` at `0x1800941fc`
- `OLEAUT32!__imp_VariantCopy` at `0x180094209`
- `OLEAUT32!__imp_VariantCopy` at `0x180094209`

## pseudocode

```c
__int64 __fastcall CCodecOptionsPropertyBag::Read(
        CCodecOptionsPropertyBag *this,
        unsigned int a2,
        struct tagPROPBAG2 *a3,
        struct IErrorLog *a4,
        VARIANTARG *pvarg,
        int *a6)
{
  CMTALock *v6; // rbx
  CCodecOptionsPropertyBag *v7; // rsi
  VARIANTARG *v10; // rbp
  unsigned int v11; // eax
  int v12; // edi
  int v13; // r13d
  __int64 v14; // r12
  __int64 v15; // rsi
  unsigned int i; // r14d
  DWORD dwHint; // eax
  HRESULT v18; // eax
  const WCHAR *pstrName; // rcx
  const WCHAR *v21; // rdx
  unsigned int v24; // [rsp+70h] [rbp+18h]

  v6 = (CCodecOptionsPropertyBag *)((char *)this - 56);
  v7 = this;
  CMTALock::Enter((CCodecOptionsPropertyBag *)((char *)this - 56));
  if ( a3 && (v10 = pvarg) != 0 )
  {
    v11 = *((_DWORD *)v7 + 8);
    v12 = 0;
    v13 = 0;
    v24 = v11;
    v14 = 0;
    if ( a2 )
    {
      while ( 2 )
      {
        v15 = *((_QWORD *)v7 + 1);
        for ( i = 0; i < v11; ++i )
        {
          dwHint = a3->dwHint;
          if ( dwHint == *(_DWORD *)(v15 + 8) && dwHint
            || !dwHint
            && (pstrName = a3->pstrName) != 0
            && (v21 = *(const WCHAR **)(v15 + 16)) != 0
            && !lstrcmpW(pstrName, v21) )
          {
            VariantInit(v10);
            v18 = VariantCopy(v10, (const VARIANTARG *)(v15 + 40));
            v13 = v18;
            if ( v12 >= 0 && v18 < 0 )
              v12 = v18;
            goto LABEL_12;
          }
          v11 = v24;
          v15 += 72;
        }
        if ( i == v11 )
        {
          v12 = -2147467259;
          goto LABEL_22;
        }
LABEL_12:
        if ( a6 )
          a6[v14] = v13;
        v14 = (unsigned int)(v14 + 1);
        if ( (unsigned int)v14 < a2 )
        {
          v7 = this;
          ++a3;
          v11 = v24;
          ++v10;
          continue;
        }
        break;
      }
    }
  }
  else
  {
    v12 = -2147024809;
LABEL_22:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v12);
  }
  if ( v6 )
    CMTALock::Leave(v6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180094180  mov     [rsp+arg_18], rbx
0x180094185  mov     [rsp+arg_8], edx
0x180094189  mov     [rsp+arg_0], rcx
0x18009418e  push    rbp
0x18009418f  push    rsi
0x180094190  push    rdi
0x180094191  push    r12
0x180094193  push    r13
0x180094195  push    r14
0x180094197  push    r15
0x180094199  sub     rsp, 20h
0x18009419d  lea     rbx, [rcx-38h]
0x1800941a1  mov     rsi, rcx
0x1800941a4  mov     rcx, rbx; this
0x1800941a7  mov     r15, r8
0x1800941aa  mov     r14d, edx
0x1800941ad  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800941b2  test    r15, r15
0x1800941b5  jz      loc_18009428D
0x1800941bb  mov     rbp, [rsp+58h+pvarg]
0x1800941c3  test    rbp, rbp
0x1800941c6  jz      loc_18009428D
0x1800941cc  mov     eax, [rsi+20h]
0x1800941cf  xor     edi, edi
0x1800941d1  xor     r13d, r13d
0x1800941d4  mov     [rsp+58h+arg_10], eax
0x1800941d8  xor     r12d, r12d
0x1800941db  test    r14d, r14d
0x1800941de  jz      short loc_18009423F
0x1800941e0  mov     rsi, [rsi+8]
0x1800941e4  xor     r14d, r14d
0x1800941e7  cmp     r14d, eax
0x1800941ea  jnb     short loc_18009421E
0x1800941ec  mov     eax, [r15+8]
0x1800941f0  cmp     eax, [rsi+8]
0x1800941f3  jnz     short loc_180094263
0x1800941f5  test    eax, eax
0x1800941f7  jz      short loc_180094263
0x1800941f9  mov     rcx, rbp; pvarg
0x1800941fc  call    cs:__imp_VariantInit
0x180094202  lea     rdx, [rsi+28h]; pvargSrc
0x180094206  mov     rcx, rbp; pvargDest
0x180094209  call    cs:__imp_VariantCopy
0x18009420f  mov     r13d, eax
0x180094212  test    edi, edi
0x180094214  js      short loc_180094224
0x180094216  test    eax, eax
0x180094218  jns     short loc_180094224
0x18009421a  mov     edi, eax
0x18009421c  jmp     short loc_180094224
0x18009421e  jz      loc_1800942A4
0x180094224  mov     rcx, [rsp+58h+arg_28]
0x18009422c  test    rcx, rcx
0x18009422f  jz      short loc_180094235
0x180094231  mov     [rcx+r12*4], r13d
0x180094235  inc     r12d
0x180094238  cmp     r12d, [rsp+58h+arg_8]
0x18009423d  jb      short loc_180094277
0x18009423f  test    rbx, rbx
0x180094242  jz      short loc_18009424C
0x180094244  mov     rcx, rbx; this
0x180094247  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18009424c  mov     rbx, [rsp+58h+arg_18]
0x180094251  mov     eax, edi
0x180094253  add     rsp, 20h
0x180094257  pop     r15
0x180094259  pop     r14
0x18009425b  pop     r13
0x18009425d  pop     r12
0x18009425f  pop     rdi
0x180094260  pop     rsi
0x180094261  pop     rbp
0x180094262  retn
0x180094263  test    eax, eax
0x180094265  jz      short loc_1800942AB
0x180094267  mov     eax, [rsp+58h+arg_10]
0x18009426b  inc     r14d
0x18009426e  add     rsi, 48h ; 'H'
0x180094272  jmp     loc_1800941E7
0x180094277  mov     rsi, [rsp+58h+arg_0]
0x18009427c  add     r15, 28h ; '('
0x180094280  mov     eax, [rsp+58h+arg_10]
0x180094284  add     rbp, 18h
0x180094288  jmp     loc_1800941E0
0x18009428d  mov     edi, 80070057h
0x180094292  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180094299  jz      short loc_18009423F
0x18009429b  mov     ecx, edi; int
0x18009429d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800942a2  jmp     short loc_18009423F
0x1800942a4  mov     edi, 80004005h
0x1800942a9  jmp     short loc_180094292
0x1800942ab  mov     rcx, [r15+10h]; lpString1
0x1800942af  test    rcx, rcx
0x1800942b2  jz      short loc_180094267
0x1800942b4  mov     rdx, [rsi+10h]; lpString2
0x1800942b8  test    rdx, rdx
0x1800942bb  jz      short loc_180094267
0x1800942bd  call    cs:__imp_lstrcmpW
0x1800942c3  test    eax, eax
0x1800942c5  jz      loc_1800941F9
0x1800942cb  jmp     short loc_180094267
```

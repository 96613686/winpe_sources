# CCodecOptionsPropertyBag::Read(ulong,tagPROPBAG2 *,IErrorLog *,tagVARIANT *,long *)

- ea: `0x180095670`
- end: `0x1800957d0`
- name: `?Read@CCodecOptionsPropertyBag@@UEAAJKPEAUtagPROPBAG2@@PEAUIErrorLog@@PEAUtagVARIANT@@PEAJ@Z`
- size: `352`
- prototype: `__int64 __fastcall(CCodecOptionsPropertyBag *__hidden this, unsigned int, struct tagPROPBAG2 *, struct IErrorLog *, VARIANTARG *pvarg, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800319d0`
- `0x1800319f0`
- `0x180095670`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800957ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800957ba`
- `OLEAUT32!__imp_VariantInit` at `0x1800956ec`
- `OLEAUT32!__imp_VariantInit` at `0x1800956ec`
- `OLEAUT32!__imp_VariantCopy` at `0x1800956ff`
- `OLEAUT32!__imp_VariantCopy` at `0x1800956ff`

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
0x180095670  mov     [rsp+arg_18], rbx
0x180095675  mov     [rsp+arg_8], edx
0x180095679  mov     [rsp+arg_0], rcx
0x18009567e  push    rbp
0x18009567f  push    rsi
0x180095680  push    rdi
0x180095681  push    r12
0x180095683  push    r13
0x180095685  push    r14
0x180095687  push    r15
0x180095689  sub     rsp, 20h
0x18009568d  lea     rbx, [rcx-38h]
0x180095691  mov     rsi, rcx
0x180095694  mov     rcx, rbx; this
0x180095697  mov     r15, r8
0x18009569a  mov     r14d, edx
0x18009569d  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800956a2  test    r15, r15
0x1800956a5  jz      loc_18009578A
0x1800956ab  mov     rbp, [rsp+58h+pvarg]
0x1800956b3  test    rbp, rbp
0x1800956b6  jz      loc_18009578A
0x1800956bc  mov     eax, [rsi+20h]
0x1800956bf  xor     edi, edi
0x1800956c1  xor     r13d, r13d
0x1800956c4  mov     [rsp+58h+arg_10], eax
0x1800956c8  xor     r12d, r12d
0x1800956cb  test    r14d, r14d
0x1800956ce  jz      short loc_18009573B
0x1800956d0  mov     rsi, [rsi+8]
0x1800956d4  xor     r14d, r14d
0x1800956d7  cmp     r14d, eax
0x1800956da  jnb     short loc_18009571A
0x1800956dc  mov     eax, [r15+8]
0x1800956e0  cmp     eax, [rsi+8]
0x1800956e3  jnz     short loc_180095760
0x1800956e5  test    eax, eax
0x1800956e7  jz      short loc_180095760
0x1800956e9  mov     rcx, rbp; pvarg
0x1800956ec  call    cs:__imp_VariantInit
0x1800956f3  nop     dword ptr [rax+rax+00h]
0x1800956f8  lea     rdx, [rsi+28h]; pvargSrc
0x1800956fc  mov     rcx, rbp; pvargDest
0x1800956ff  call    cs:__imp_VariantCopy
0x180095706  nop     dword ptr [rax+rax+00h]
0x18009570b  mov     r13d, eax
0x18009570e  test    edi, edi
0x180095710  js      short loc_180095720
0x180095712  test    eax, eax
0x180095714  jns     short loc_180095720
0x180095716  mov     edi, eax
0x180095718  jmp     short loc_180095720
0x18009571a  jz      loc_1800957A1
0x180095720  mov     rcx, [rsp+58h+arg_28]
0x180095728  test    rcx, rcx
0x18009572b  jz      short loc_180095731
0x18009572d  mov     [rcx+r12*4], r13d
0x180095731  inc     r12d
0x180095734  cmp     r12d, [rsp+58h+arg_8]
0x180095739  jb      short loc_180095774
0x18009573b  test    rbx, rbx
0x18009573e  jz      short loc_180095748
0x180095740  mov     rcx, rbx; this
0x180095743  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180095748  mov     rbx, [rsp+58h+arg_18]
0x18009574d  mov     eax, edi
0x18009574f  add     rsp, 20h
0x180095753  pop     r15
0x180095755  pop     r14
0x180095757  pop     r13
0x180095759  pop     r12
0x18009575b  pop     rdi
0x18009575c  pop     rsi
0x18009575d  pop     rbp
0x18009575e  retn
0x180095760  test    eax, eax
0x180095762  jz      short loc_1800957A8
0x180095764  mov     eax, [rsp+58h+arg_10]
0x180095768  inc     r14d
0x18009576b  add     rsi, 48h ; 'H'
0x18009576f  jmp     loc_1800956D7
0x180095774  mov     rsi, [rsp+58h+arg_0]
0x180095779  add     r15, 28h ; '('
0x18009577d  mov     eax, [rsp+58h+arg_10]
0x180095781  add     rbp, 18h
0x180095785  jmp     loc_1800956D0
0x18009578a  mov     edi, 80070057h
0x18009578f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180095796  jz      short loc_18009573B
0x180095798  mov     ecx, edi; int
0x18009579a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009579f  jmp     short loc_18009573B
0x1800957a1  mov     edi, 80004005h
0x1800957a6  jmp     short loc_18009578F
0x1800957a8  mov     rcx, [r15+10h]; lpString1
0x1800957ac  test    rcx, rcx
0x1800957af  jz      short loc_180095764
0x1800957b1  mov     rdx, [rsi+10h]; lpString2
0x1800957b5  test    rdx, rdx
0x1800957b8  jz      short loc_180095764
0x1800957ba  call    cs:__imp_lstrcmpW
0x1800957c1  nop     dword ptr [rax+rax+00h]
0x1800957c6  test    eax, eax
0x1800957c8  jz      loc_1800956E9
0x1800957ce  jmp     short loc_180095764
```

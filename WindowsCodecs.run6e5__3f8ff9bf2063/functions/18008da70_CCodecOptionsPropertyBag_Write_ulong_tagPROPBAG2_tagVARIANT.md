# CCodecOptionsPropertyBag::Write(ulong,tagPROPBAG2 *,tagVARIANT *)

- ea: `0x18008da70`
- end: `0x18008dc01`
- name: `?Write@CCodecOptionsPropertyBag@@UEAAJKPEAUtagPROPBAG2@@PEAUtagVARIANT@@@Z`
- size: `401`
- prototype: `int(CCodecOptionsPropertyBag *__hidden this, unsigned int, struct tagPROPBAG2 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18008da70`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008dae4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008dae4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008daa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008daa4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008db2f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008db2f`
- `OLEAUT32!__imp_VariantClear` at `0x18008db58`
- `OLEAUT32!__imp_VariantClear` at `0x18008db58`
- `OLEAUT32!__imp_VariantCopy` at `0x18008db6b`
- `OLEAUT32!__imp_VariantCopy` at `0x18008db6b`

## pseudocode

```c
__int64 __fastcall CCodecOptionsPropertyBag::Write(
        CCodecOptionsPropertyBag *this,
        unsigned int a2,
        struct tagPROPBAG2 *a3,
        struct tagVARIANT *a4)
{
  char *v4; // rbx
  CCodecOptionsPropertyBag *v7; // rax
  unsigned int v8; // ecx
  HRESULT v9; // edi
  int v10; // r12d
  __int64 v12; // rsi
  unsigned int i; // r15d
  DWORD dwHint; // eax
  const WCHAR *pstrName; // rcx
  const WCHAR *v16; // rdx
  HRESULT v17; // eax
  int v18; // eax
  int v19; // ecx
  bool v20; // zf
  unsigned int v22; // [rsp+68h] [rbp+10h]
  unsigned int v23; // [rsp+70h] [rbp+18h]

  v22 = a2;
  v4 = (char *)this - 56;
  v7 = this;
  if ( *((_BYTE *)this - 8) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
    v7 = this;
    a2 = v22;
  }
  if ( a3 && a4 )
  {
    v8 = *((_DWORD *)v7 + 8);
    v9 = 0;
    v10 = 0;
    v23 = v8;
    if ( !a2 )
      goto LABEL_6;
    while ( 2 )
    {
      v12 = *((_QWORD *)v7 + 1);
      for ( i = 0; ; ++i )
      {
        if ( i >= v8 )
        {
          v18 = (int)g_doStackCaptures;
          goto LABEL_24;
        }
        dwHint = a3->dwHint;
        if ( dwHint == *(_DWORD *)(v12 + 8) )
        {
          if ( dwHint )
            break;
        }
        if ( !dwHint )
        {
          pstrName = a3->pstrName;
          if ( pstrName )
          {
            v16 = *(const WCHAR **)(v12 + 16);
            if ( v16 )
            {
              if ( !lstrcmpW(pstrName, v16) )
                break;
            }
          }
          v8 = v23;
        }
        v12 += 72;
      }
      if ( *(_WORD *)(v12 + 4) != a4->vt )
      {
        v9 = -2003292274;
        goto LABEL_33;
      }
      v17 = VariantClear((VARIANTARG *)(v12 + 40));
      v9 = v17;
      if ( v17 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_6;
        v19 = v17;
        goto LABEL_29;
      }
      v9 = VariantCopy((VARIANTARG *)(v12 + 40), a4);
      v18 = (int)g_doStackCaptures;
      if ( v9 >= 0 )
      {
        v8 = v23;
LABEL_24:
        if ( i == v8 )
        {
          v9 = -2147467259;
          v20 = v18 == 0;
          goto LABEL_34;
        }
        if ( ++v10 >= v22 )
          goto LABEL_6;
        v7 = this;
        ++a3;
        ++a4;
        continue;
      }
      break;
    }
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_6;
LABEL_28:
    v19 = v9;
LABEL_29:
    DoStackCapture(v19);
    goto LABEL_6;
  }
  v9 = -2147024809;
LABEL_33:
  v20 = (_DWORD)g_doStackCaptures == 0;
LABEL_34:
  if ( !v20 )
    goto LABEL_28;
LABEL_6:
  if ( v4 && v4[48] )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18008da70  mov     [rsp+arg_18], rbx
0x18008da75  mov     [rsp+arg_8], edx
0x18008da79  mov     [rsp+arg_0], rcx
0x18008da7e  push    rbp
0x18008da7f  push    rsi
0x18008da80  push    rdi
0x18008da81  push    r12
0x18008da83  push    r13
0x18008da85  push    r14
0x18008da87  push    r15
0x18008da89  sub     rsp, 20h
0x18008da8d  lea     rbx, [rcx-38h]
0x18008da91  mov     r14, r9
0x18008da94  cmp     byte ptr [rbx+30h], 0
0x18008da98  mov     rbp, r8
0x18008da9b  mov     rax, rcx
0x18008da9e  jz      short loc_18008DAB3
0x18008daa0  lea     rcx, [rbx+8]; lpCriticalSection
0x18008daa4  call    cs:__imp_EnterCriticalSection
0x18008daaa  mov     rax, [rsp+58h+arg_0]
0x18008daaf  mov     edx, [rsp+58h+arg_8]
0x18008dab3  test    rbp, rbp
0x18008dab6  jz      loc_18008DBE9
0x18008dabc  test    r14, r14
0x18008dabf  jz      loc_18008DBE9
0x18008dac5  mov     ecx, [rax+20h]
0x18008dac8  xor     edi, edi
0x18008daca  xor     r12d, r12d
0x18008dacd  mov     [rsp+58h+arg_10], ecx
0x18008dad1  test    edx, edx
0x18008dad3  jnz     short loc_18008DB01
0x18008dad5  test    rbx, rbx
0x18008dad8  jz      short loc_18008DAEA
0x18008dada  cmp     byte ptr [rbx+30h], 0
0x18008dade  jz      short loc_18008DAEA
0x18008dae0  lea     rcx, [rbx+8]; lpCriticalSection
0x18008dae4  call    cs:__imp_LeaveCriticalSection
0x18008daea  mov     rbx, [rsp+58h+arg_18]
0x18008daef  mov     eax, edi
0x18008daf1  add     rsp, 20h
0x18008daf5  pop     r15
0x18008daf7  pop     r14
0x18008daf9  pop     r13
0x18008dafb  pop     r12
0x18008dafd  pop     rdi
0x18008dafe  pop     rsi
0x18008daff  pop     rbp
0x18008db00  retn
0x18008db01  mov     rsi, [rax+8]
0x18008db05  xor     r15d, r15d
0x18008db08  cmp     r15d, ecx
0x18008db0b  jnb     loc_18008DBF0
0x18008db11  mov     eax, [rbp+8]
0x18008db14  cmp     eax, [rsi+8]
0x18008db17  jz      short loc_18008DB46
0x18008db19  test    eax, eax
0x18008db1b  jnz     short loc_18008DB3D
0x18008db1d  mov     rcx, [rbp+10h]; lpString1
0x18008db21  test    rcx, rcx
0x18008db24  jz      short loc_18008DB39
0x18008db26  mov     rdx, [rsi+10h]; lpString2
0x18008db2a  test    rdx, rdx
0x18008db2d  jz      short loc_18008DB39
0x18008db2f  call    cs:__imp_lstrcmpW
0x18008db35  test    eax, eax
0x18008db37  jz      short loc_18008DB4A
0x18008db39  mov     ecx, [rsp+58h+arg_10]
0x18008db3d  inc     r15d
0x18008db40  add     rsi, 48h ; 'H'
0x18008db44  jmp     short loc_18008DB08
0x18008db46  test    eax, eax
0x18008db48  jz      short loc_18008DB19
0x18008db4a  movzx   eax, word ptr [r14]
0x18008db4e  cmp     [rsi+4], ax
0x18008db52  jnz     short loc_18008DBC3
0x18008db54  lea     rcx, [rsi+28h]; pvarg
0x18008db58  call    cs:__imp_VariantClear
0x18008db5e  mov     edi, eax
0x18008db60  test    eax, eax
0x18008db62  js      short loc_18008DBB6
0x18008db64  mov     rdx, r14; pvargSrc
0x18008db67  lea     rcx, [rsi+28h]; pvargDest
0x18008db6b  call    cs:__imp_VariantCopy
0x18008db71  mov     edi, eax
0x18008db73  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18008db79  test    edi, edi
0x18008db7b  js      short loc_18008DBA6
0x18008db7d  mov     ecx, [rsp+58h+arg_10]
0x18008db81  cmp     r15d, ecx
0x18008db84  jz      short loc_18008DBF8
0x18008db86  inc     r12d
0x18008db89  cmp     r12d, [rsp+58h+arg_8]
0x18008db8e  jnb     loc_18008DAD5
0x18008db94  mov     rax, [rsp+58h+arg_0]
0x18008db99  add     rbp, 28h ; '('
0x18008db9d  add     r14, 18h
0x18008dba1  jmp     loc_18008DB01
0x18008dba6  test    eax, eax
0x18008dba8  jz      short loc_18008DBD6
0x18008dbaa  mov     ecx, edi; int
0x18008dbac  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008dbb1  jmp     loc_18008DAD5
0x18008dbb6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008dbbd  jz      short loc_18008DBE0
0x18008dbbf  mov     ecx, eax
0x18008dbc1  jmp     short loc_18008DBAC
0x18008dbc3  mov     edi, 88982F8Eh
0x18008dbc8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008dbcf  jnz     short loc_18008DBAA
0x18008dbd1  jmp     loc_18008DAD5
0x18008dbd6  test    edi, edi
0x18008dbd8  js      loc_18008DAD5
0x18008dbde  jmp     short loc_18008DB7D
0x18008dbe0  test    eax, eax
0x18008dbe2  jns     short loc_18008DB64
0x18008dbe4  jmp     loc_18008DAD5
0x18008dbe9  mov     edi, 80070057h
0x18008dbee  jmp     short loc_18008DBC8
0x18008dbf0  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18008dbf6  jmp     short loc_18008DB81
0x18008dbf8  mov     edi, 80004005h
0x18008dbfd  test    eax, eax
0x18008dbff  jmp     short loc_18008DBCF
```

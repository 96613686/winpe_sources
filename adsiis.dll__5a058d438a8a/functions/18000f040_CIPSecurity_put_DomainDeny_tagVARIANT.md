# CIPSecurity::put_DomainDeny(tagVARIANT)

- ea: `0x18000f040`
- end: `0x18000f1d8`
- name: `?put_DomainDeny@CIPSecurity@@UEAAJUtagVARIANT@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvargSrc)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000e1f8`
- `0x18000f040`
- `0x180013020`
- `0x18001916c`
- `0x1800192c8`
- `0x18001cd14`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000f07d`
- `OLEAUT32!__imp_VariantInit` at `0x18000f07d`
- `OLEAUT32!__imp_VariantClear` at `0x18000f19c`
- `OLEAUT32!__imp_VariantClear` at `0x18000f1b7`
- `OLEAUT32!__imp_VariantClear` at `0x18000f19c`
- `OLEAUT32!__imp_VariantClear` at `0x18000f1b7`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f08a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f08a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f1ad`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f1ad`

## pseudocode

```c
__int64 __fastcall CIPSecurity::put_DomainDeny(CIPSecurity *this, VARIANTARG *pvargSrc)
{
  VARIANTARG *v3; // rdi
  int v5; // ebx
  int v6; // eax
  unsigned int v7; // esi
  int v8; // r15d
  int v9; // eax
  __int64 i; // r14
  LPVOID pMem; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  struct tagVARIANT v14; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+A0h] [rbp+40h] BYREF
  char *v16; // [rsp+A8h] [rbp+48h] BYREF

  v3 = 0;
  v15 = 0;
  pMem = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v16 = 0;
  VariantInit(&pvarg);
  v5 = VariantCopyInd(&pvarg, pvargSrc);
  if ( v5 < 0 )
    goto LABEL_27;
  if ( ((pvarg.vt & 0xFFF) != 0xC || (pvarg.vt & 0x2000) == 0) && ((pvarg.vt & 0xFFF) != 8 || (pvarg.vt & 0x2000) == 0) )
  {
    v7 = 1;
LABEL_9:
    ADDRESS_CHECK::DeleteAllName((CIPSecurity *)((char *)this + 24), 0);
    v8 = 0;
    if ( v7 )
    {
      while ( 1 )
      {
        if ( pvargSrc->vt != 8 )
        {
          v5 = -2147463156;
          goto LABEL_23;
        }
        v9 = AllocAnsi(pvargSrc->bstrVal, &v16);
        if ( v9 )
          break;
        if ( v16 )
        {
          if ( !CIPSecurity::AddToList(this, 0, 0, v16) )
            v5 = -2147024809;
          FreeAnsi(v16);
          v16 = 0;
          if ( v5 < 0 )
            goto LABEL_23;
        }
        if ( ++v8 >= v7 )
          goto LABEL_23;
        ++pvargSrc;
      }
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      else
        v5 = v9;
    }
    goto LABEL_23;
  }
  v14 = pvarg;
  v6 = ConvertArrayToVariantArray(&v14, (struct tagVARIANT **)&pMem, &v15);
  v3 = (VARIANTARG *)pMem;
  v5 = v6;
  v7 = v15;
  if ( v6 >= 0 )
  {
    pvargSrc = (VARIANTARG *)pMem;
    goto LABEL_9;
  }
LABEL_23:
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      VariantClear(&v3[i]);
    FreeADsMem(v3);
  }
LABEL_27:
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f040  mov     [rsp-28h+arg_0], rbx
0x18000f045  mov     [rsp-28h+arg_8], rsi
0x18000f04a  push    rbp
0x18000f04b  push    rdi
0x18000f04c  push    r13
0x18000f04e  push    r14
0x18000f050  push    r15
0x18000f052  mov     rbp, rsp
0x18000f055  sub     rsp, 60h
0x18000f059  xor     eax, eax
0x18000f05b  mov     r13, rcx
0x18000f05e  xorps   xmm0, xmm0
0x18000f061  mov     qword ptr [rbp+pvarg+10h], rax
0x18000f065  xor     edi, edi
0x18000f067  mov     [rbp+arg_10], eax
0x18000f06a  lea     rcx, [rbp+pvarg]; pvarg
0x18000f06e  mov     [rbp+pMem], rdi
0x18000f072  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000f076  mov     [rbp+arg_18], rax
0x18000f07a  mov     r14, rdx
0x18000f07d  call    cs:__imp_VariantInit
0x18000f083  mov     rdx, r14; pvargSrc
0x18000f086  lea     rcx, [rbp+pvarg]; pvarDest
0x18000f08a  call    cs:__imp_VariantCopyInd
0x18000f090  mov     ebx, eax
0x18000f092  test    eax, eax
0x18000f094  js      loc_18000F1B3
0x18000f09a  movzx   ecx, word ptr [rbp+pvarg]
0x18000f09e  mov     edx, 0FFFh
0x18000f0a3  movzx   eax, cx
0x18000f0a6  and     ax, dx
0x18000f0a9  cmp     ax, 0Ch
0x18000f0ad  jnz     short loc_18000F0B6
0x18000f0af  bt      cx, 0Dh
0x18000f0b4  jb      short loc_18000F0C3
0x18000f0b6  cmp     ax, 8
0x18000f0ba  jnz     short loc_18000F0FC
0x18000f0bc  bt      cx, 0Dh
0x18000f0c1  jnb     short loc_18000F0FC
0x18000f0c3  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000f0c7  lea     r8, [rbp+arg_10]; unsigned int *
0x18000f0cb  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000f0d0  lea     rdx, [rbp+pMem]; struct tagVARIANT **
0x18000f0d4  lea     rcx, [rbp+var_20]; struct tagVARIANT
0x18000f0d8  movaps  xmmword ptr [rbp+var_20], xmm0
0x18000f0dc  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18000f0e1  call    ?ConvertArrayToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertArrayToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x18000f0e6  mov     rdi, [rbp+pMem]
0x18000f0ea  mov     ebx, eax
0x18000f0ec  mov     esi, [rbp+arg_10]
0x18000f0ef  test    eax, eax
0x18000f0f1  js      loc_18000F188
0x18000f0f7  mov     r14, rdi
0x18000f0fa  jmp     short loc_18000F101
0x18000f0fc  mov     esi, 1
0x18000f101  lea     rcx, [r13+18h]; this
0x18000f105  xor     edx, edx; int
0x18000f107  call    ?DeleteAllName@ADDRESS_CHECK@@QEAAHH@Z; ADDRESS_CHECK::DeleteAllName(int)
0x18000f10c  xor     r15d, r15d
0x18000f10f  test    esi, esi
0x18000f111  jz      short loc_18000F188
0x18000f113  cmp     word ptr [r14], 8
0x18000f118  jnz     short loc_18000F183
0x18000f11a  mov     rcx, [r14+8]; lpWideCharStr
0x18000f11e  lea     rdx, [rbp+arg_18]; char **
0x18000f122  call    ?AllocAnsi@@YAIPEBGPEAPEAD@Z; AllocAnsi(ushort const *,char * *)
0x18000f127  test    eax, eax
0x18000f129  jz      short loc_18000F13E
0x18000f12b  jg      short loc_18000F131
0x18000f12d  mov     ebx, eax
0x18000f12f  jmp     short loc_18000F13A
0x18000f131  movzx   ebx, ax
0x18000f134  or      ebx, 80070000h
0x18000f13a  test    ebx, ebx
0x18000f13c  js      short loc_18000F188
0x18000f13e  cmp     [rbp+arg_18], 0
0x18000f143  jz      short loc_18000F175
0x18000f145  mov     r9, [rbp+arg_18]; char *
0x18000f149  xor     r8d, r8d; int
0x18000f14c  xor     edx, edx; int
0x18000f14e  mov     rcx, r13; this
0x18000f151  call    ?AddToList@CIPSecurity@@QEAAHHHPEAD@Z; CIPSecurity::AddToList(int,int,char *)
0x18000f156  test    eax, eax
0x18000f158  mov     ecx, 80070057h
0x18000f15d  cmovz   ebx, ecx
0x18000f160  mov     rcx, [rbp+arg_18]; char *
0x18000f164  call    ?FreeAnsi@@YAXPEAD@Z; FreeAnsi(char *)
0x18000f169  mov     [rbp+arg_18], 0
0x18000f171  test    ebx, ebx
0x18000f173  js      short loc_18000F188
0x18000f175  inc     r15d
0x18000f178  cmp     r15d, esi
0x18000f17b  jnb     short loc_18000F188
0x18000f17d  add     r14, 18h
0x18000f181  jmp     short loc_18000F113
0x18000f183  mov     ebx, 8000500Ch
0x18000f188  test    rdi, rdi
0x18000f18b  jz      short loc_18000F1B3
0x18000f18d  xor     r14d, r14d
0x18000f190  test    esi, esi
0x18000f192  jz      short loc_18000F1AA
0x18000f194  lea     rdx, [r14+r14*2]
0x18000f198  lea     rcx, [rdi+rdx*8]; pvarg
0x18000f19c  call    cs:__imp_VariantClear
0x18000f1a2  inc     r14d
0x18000f1a5  cmp     r14d, esi
0x18000f1a8  jb      short loc_18000F194
0x18000f1aa  mov     rcx, rdi; pMem
0x18000f1ad  call    cs:__imp_FreeADsMem
0x18000f1b3  lea     rcx, [rbp+pvarg]; pvarg
0x18000f1b7  call    cs:__imp_VariantClear
0x18000f1bd  lea     r11, [rsp+60h+var_s0]
0x18000f1c2  mov     eax, ebx
0x18000f1c4  mov     rbx, [r11+30h]
0x18000f1c8  mov     rsi, [r11+38h]
0x18000f1cc  mov     rsp, r11
0x18000f1cf  pop     r15
0x18000f1d1  pop     r14
0x18000f1d3  pop     r13
0x18000f1d5  pop     rdi
0x18000f1d6  pop     rbp
0x18000f1d7  retn
```

# CIPSecurity::put_DomainGrant(tagVARIANT)

- ea: `0x18000f1e0`
- end: `0x18000f37c`
- name: `?put_DomainGrant@CIPSecurity@@UEAAJUtagVARIANT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvargSrc)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000e1f8`
- `0x18000f1e0`
- `0x180013020`
- `0x18001916c`
- `0x1800192c8`
- `0x18001cd14`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000f21d`
- `OLEAUT32!__imp_VariantInit` at `0x18000f21d`
- `OLEAUT32!__imp_VariantClear` at `0x18000f340`
- `OLEAUT32!__imp_VariantClear` at `0x18000f35b`
- `OLEAUT32!__imp_VariantClear` at `0x18000f340`
- `OLEAUT32!__imp_VariantClear` at `0x18000f35b`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f22a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f22a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f351`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f351`

## pseudocode

```c
__int64 __fastcall CIPSecurity::put_DomainGrant(CIPSecurity *this, VARIANTARG *pvargSrc)
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
    ADDRESS_CHECK::DeleteAllName((CIPSecurity *)((char *)this + 24), 1);
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
          if ( !CIPSecurity::AddToList(this, 0, 1, v16) )
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
0x18000f1e0  mov     [rsp-28h+arg_0], rbx
0x18000f1e5  mov     [rsp-28h+arg_8], rsi
0x18000f1ea  push    rbp
0x18000f1eb  push    rdi
0x18000f1ec  push    r13
0x18000f1ee  push    r14
0x18000f1f0  push    r15
0x18000f1f2  mov     rbp, rsp
0x18000f1f5  sub     rsp, 60h
0x18000f1f9  xor     eax, eax
0x18000f1fb  mov     r13, rcx
0x18000f1fe  xorps   xmm0, xmm0
0x18000f201  mov     qword ptr [rbp+pvarg+10h], rax
0x18000f205  xor     edi, edi
0x18000f207  mov     [rbp+arg_10], eax
0x18000f20a  lea     rcx, [rbp+pvarg]; pvarg
0x18000f20e  mov     [rbp+pMem], rdi
0x18000f212  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000f216  mov     [rbp+arg_18], rax
0x18000f21a  mov     r14, rdx
0x18000f21d  call    cs:__imp_VariantInit
0x18000f223  mov     rdx, r14; pvargSrc
0x18000f226  lea     rcx, [rbp+pvarg]; pvarDest
0x18000f22a  call    cs:__imp_VariantCopyInd
0x18000f230  mov     ebx, eax
0x18000f232  test    eax, eax
0x18000f234  js      loc_18000F357
0x18000f23a  movzx   ecx, word ptr [rbp+pvarg]
0x18000f23e  mov     edx, 0FFFh
0x18000f243  movzx   eax, cx
0x18000f246  and     ax, dx
0x18000f249  cmp     ax, 0Ch
0x18000f24d  jnz     short loc_18000F256
0x18000f24f  bt      cx, 0Dh
0x18000f254  jb      short loc_18000F263
0x18000f256  cmp     ax, 8
0x18000f25a  jnz     short loc_18000F29C
0x18000f25c  bt      cx, 0Dh
0x18000f261  jnb     short loc_18000F29C
0x18000f263  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000f267  lea     r8, [rbp+arg_10]; unsigned int *
0x18000f26b  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000f270  lea     rdx, [rbp+pMem]; struct tagVARIANT **
0x18000f274  lea     rcx, [rbp+var_20]; struct tagVARIANT
0x18000f278  movaps  xmmword ptr [rbp+var_20], xmm0
0x18000f27c  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18000f281  call    ?ConvertArrayToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertArrayToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x18000f286  mov     rdi, [rbp+pMem]
0x18000f28a  mov     ebx, eax
0x18000f28c  mov     esi, [rbp+arg_10]
0x18000f28f  test    eax, eax
0x18000f291  js      loc_18000F32C
0x18000f297  mov     r14, rdi
0x18000f29a  jmp     short loc_18000F2A1
0x18000f29c  mov     esi, 1
0x18000f2a1  lea     rcx, [r13+18h]; this
0x18000f2a5  mov     edx, 1; int
0x18000f2aa  call    ?DeleteAllName@ADDRESS_CHECK@@QEAAHH@Z; ADDRESS_CHECK::DeleteAllName(int)
0x18000f2af  xor     r15d, r15d
0x18000f2b2  test    esi, esi
0x18000f2b4  jz      short loc_18000F32C
0x18000f2b6  cmp     word ptr [r14], 8
0x18000f2bb  jnz     short loc_18000F327
0x18000f2bd  mov     rcx, [r14+8]; lpWideCharStr
0x18000f2c1  lea     rdx, [rbp+arg_18]; char **
0x18000f2c5  call    ?AllocAnsi@@YAIPEBGPEAPEAD@Z; AllocAnsi(ushort const *,char * *)
0x18000f2ca  test    eax, eax
0x18000f2cc  jz      short loc_18000F2E1
0x18000f2ce  jg      short loc_18000F2D4
0x18000f2d0  mov     ebx, eax
0x18000f2d2  jmp     short loc_18000F2DD
0x18000f2d4  movzx   ebx, ax
0x18000f2d7  or      ebx, 80070000h
0x18000f2dd  test    ebx, ebx
0x18000f2df  js      short loc_18000F32C
0x18000f2e1  cmp     [rbp+arg_18], 0
0x18000f2e6  jz      short loc_18000F319
0x18000f2e8  mov     r9, [rbp+arg_18]; char *
0x18000f2ec  xor     edx, edx; int
0x18000f2ee  mov     rcx, r13; this
0x18000f2f1  lea     r8d, [rdx+1]; int
0x18000f2f5  call    ?AddToList@CIPSecurity@@QEAAHHHPEAD@Z; CIPSecurity::AddToList(int,int,char *)
0x18000f2fa  test    eax, eax
0x18000f2fc  mov     ecx, 80070057h
0x18000f301  cmovz   ebx, ecx
0x18000f304  mov     rcx, [rbp+arg_18]; char *
0x18000f308  call    ?FreeAnsi@@YAXPEAD@Z; FreeAnsi(char *)
0x18000f30d  mov     [rbp+arg_18], 0
0x18000f315  test    ebx, ebx
0x18000f317  js      short loc_18000F32C
0x18000f319  inc     r15d
0x18000f31c  cmp     r15d, esi
0x18000f31f  jnb     short loc_18000F32C
0x18000f321  add     r14, 18h
0x18000f325  jmp     short loc_18000F2B6
0x18000f327  mov     ebx, 8000500Ch
0x18000f32c  test    rdi, rdi
0x18000f32f  jz      short loc_18000F357
0x18000f331  xor     r14d, r14d
0x18000f334  test    esi, esi
0x18000f336  jz      short loc_18000F34E
0x18000f338  lea     rdx, [r14+r14*2]
0x18000f33c  lea     rcx, [rdi+rdx*8]; pvarg
0x18000f340  call    cs:__imp_VariantClear
0x18000f346  inc     r14d
0x18000f349  cmp     r14d, esi
0x18000f34c  jb      short loc_18000F338
0x18000f34e  mov     rcx, rdi; pMem
0x18000f351  call    cs:__imp_FreeADsMem
0x18000f357  lea     rcx, [rbp+pvarg]; pvarg
0x18000f35b  call    cs:__imp_VariantClear
0x18000f361  lea     r11, [rsp+60h+var_s0]
0x18000f366  mov     eax, ebx
0x18000f368  mov     rbx, [r11+30h]
0x18000f36c  mov     rsi, [r11+38h]
0x18000f370  mov     rsp, r11
0x18000f373  pop     r15
0x18000f375  pop     r14
0x18000f377  pop     r13
0x18000f379  pop     rdi
0x18000f37a  pop     rbp
0x18000f37b  retn
```

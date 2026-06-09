# CIPSecurity::put_IPGrant(tagVARIANT)

- ea: `0x18000f560`
- end: `0x18000f700`
- name: `?put_IPGrant@CIPSecurity@@UEAAJUtagVARIANT@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvargSrc)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000e1f8`
- `0x18000f560`
- `0x180013020`
- `0x18001916c`
- `0x1800192c8`
- `0x18001cce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000f59d`
- `OLEAUT32!__imp_VariantInit` at `0x18000f59d`
- `OLEAUT32!__imp_VariantClear` at `0x18000f6c4`
- `OLEAUT32!__imp_VariantClear` at `0x18000f6df`
- `OLEAUT32!__imp_VariantClear` at `0x18000f6c4`
- `OLEAUT32!__imp_VariantClear` at `0x18000f6df`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f5aa`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f5aa`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f6d5`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f6d5`

## pseudocode

```c
__int64 __fastcall CIPSecurity::put_IPGrant(CIPSecurity *this, VARIANTARG *pvargSrc)
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
    ADDRESS_CHECK::DeleteAllAddr((CIPSecurity *)((char *)this + 24), 1);
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
          if ( !CIPSecurity::AddToList(this, 1, 1, v16) )
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
0x18000f560  mov     [rsp-28h+arg_0], rbx
0x18000f565  mov     [rsp-28h+arg_8], rsi
0x18000f56a  push    rbp
0x18000f56b  push    rdi
0x18000f56c  push    r13
0x18000f56e  push    r14
0x18000f570  push    r15
0x18000f572  mov     rbp, rsp
0x18000f575  sub     rsp, 60h
0x18000f579  xor     eax, eax
0x18000f57b  mov     r13, rcx
0x18000f57e  xorps   xmm0, xmm0
0x18000f581  mov     qword ptr [rbp+pvarg+10h], rax
0x18000f585  xor     edi, edi
0x18000f587  mov     [rbp+arg_10], eax
0x18000f58a  lea     rcx, [rbp+pvarg]; pvarg
0x18000f58e  mov     [rbp+pMem], rdi
0x18000f592  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000f596  mov     [rbp+arg_18], rax
0x18000f59a  mov     r14, rdx
0x18000f59d  call    cs:__imp_VariantInit
0x18000f5a3  mov     rdx, r14; pvargSrc
0x18000f5a6  lea     rcx, [rbp+pvarg]; pvarDest
0x18000f5aa  call    cs:__imp_VariantCopyInd
0x18000f5b0  mov     ebx, eax
0x18000f5b2  test    eax, eax
0x18000f5b4  js      loc_18000F6DB
0x18000f5ba  movzx   ecx, word ptr [rbp+pvarg]
0x18000f5be  mov     edx, 0FFFh
0x18000f5c3  movzx   eax, cx
0x18000f5c6  and     ax, dx
0x18000f5c9  cmp     ax, 0Ch
0x18000f5cd  jnz     short loc_18000F5D6
0x18000f5cf  bt      cx, 0Dh
0x18000f5d4  jb      short loc_18000F5E3
0x18000f5d6  cmp     ax, 8
0x18000f5da  jnz     short loc_18000F61C
0x18000f5dc  bt      cx, 0Dh
0x18000f5e1  jnb     short loc_18000F61C
0x18000f5e3  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000f5e7  lea     r8, [rbp+arg_10]; unsigned int *
0x18000f5eb  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000f5f0  lea     rdx, [rbp+pMem]; struct tagVARIANT **
0x18000f5f4  lea     rcx, [rbp+var_20]; struct tagVARIANT
0x18000f5f8  movaps  xmmword ptr [rbp+var_20], xmm0
0x18000f5fc  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18000f601  call    ?ConvertArrayToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertArrayToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x18000f606  mov     rdi, [rbp+pMem]
0x18000f60a  mov     ebx, eax
0x18000f60c  mov     esi, [rbp+arg_10]
0x18000f60f  test    eax, eax
0x18000f611  js      loc_18000F6B0
0x18000f617  mov     r14, rdi
0x18000f61a  jmp     short loc_18000F621
0x18000f61c  mov     esi, 1
0x18000f621  lea     rcx, [r13+18h]; this
0x18000f625  mov     edx, 1; int
0x18000f62a  call    ?DeleteAllAddr@ADDRESS_CHECK@@QEAAHH@Z; ADDRESS_CHECK::DeleteAllAddr(int)
0x18000f62f  xor     r15d, r15d
0x18000f632  test    esi, esi
0x18000f634  jz      short loc_18000F6B0
0x18000f636  cmp     word ptr [r14], 8
0x18000f63b  jnz     short loc_18000F6AB
0x18000f63d  mov     rcx, [r14+8]; lpWideCharStr
0x18000f641  lea     rdx, [rbp+arg_18]; char **
0x18000f645  call    ?AllocAnsi@@YAIPEBGPEAPEAD@Z; AllocAnsi(ushort const *,char * *)
0x18000f64a  test    eax, eax
0x18000f64c  jz      short loc_18000F661
0x18000f64e  jg      short loc_18000F654
0x18000f650  mov     ebx, eax
0x18000f652  jmp     short loc_18000F65D
0x18000f654  movzx   ebx, ax
0x18000f657  or      ebx, 80070000h
0x18000f65d  test    ebx, ebx
0x18000f65f  js      short loc_18000F6B0
0x18000f661  cmp     [rbp+arg_18], 0
0x18000f666  jz      short loc_18000F69D
0x18000f668  mov     r9, [rbp+arg_18]; char *
0x18000f66c  mov     eax, 1
0x18000f671  mov     r8d, eax; int
0x18000f674  mov     edx, eax; int
0x18000f676  mov     rcx, r13; this
0x18000f679  call    ?AddToList@CIPSecurity@@QEAAHHHPEAD@Z; CIPSecurity::AddToList(int,int,char *)
0x18000f67e  test    eax, eax
0x18000f680  mov     ecx, 80070057h
0x18000f685  cmovz   ebx, ecx
0x18000f688  mov     rcx, [rbp+arg_18]; char *
0x18000f68c  call    ?FreeAnsi@@YAXPEAD@Z; FreeAnsi(char *)
0x18000f691  mov     [rbp+arg_18], 0
0x18000f699  test    ebx, ebx
0x18000f69b  js      short loc_18000F6B0
0x18000f69d  inc     r15d
0x18000f6a0  cmp     r15d, esi
0x18000f6a3  jnb     short loc_18000F6B0
0x18000f6a5  add     r14, 18h
0x18000f6a9  jmp     short loc_18000F636
0x18000f6ab  mov     ebx, 8000500Ch
0x18000f6b0  test    rdi, rdi
0x18000f6b3  jz      short loc_18000F6DB
0x18000f6b5  xor     r14d, r14d
0x18000f6b8  test    esi, esi
0x18000f6ba  jz      short loc_18000F6D2
0x18000f6bc  lea     rdx, [r14+r14*2]
0x18000f6c0  lea     rcx, [rdi+rdx*8]; pvarg
0x18000f6c4  call    cs:__imp_VariantClear
0x18000f6ca  inc     r14d
0x18000f6cd  cmp     r14d, esi
0x18000f6d0  jb      short loc_18000F6BC
0x18000f6d2  mov     rcx, rdi; pMem
0x18000f6d5  call    cs:__imp_FreeADsMem
0x18000f6db  lea     rcx, [rbp+pvarg]; pvarg
0x18000f6df  call    cs:__imp_VariantClear
0x18000f6e5  lea     r11, [rsp+60h+var_s0]
0x18000f6ea  mov     eax, ebx
0x18000f6ec  mov     rbx, [r11+30h]
0x18000f6f0  mov     rsi, [r11+38h]
0x18000f6f4  mov     rsp, r11
0x18000f6f7  pop     r15
0x18000f6f9  pop     r14
0x18000f6fb  pop     r13
0x18000f6fd  pop     rdi
0x18000f6fe  pop     rbp
0x18000f6ff  retn
```

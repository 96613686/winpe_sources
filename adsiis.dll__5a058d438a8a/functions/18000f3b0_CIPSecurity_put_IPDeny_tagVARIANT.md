# CIPSecurity::put_IPDeny(tagVARIANT)

- ea: `0x18000f3b0`
- end: `0x18000f54e`
- name: `?put_IPDeny@CIPSecurity@@UEAAJUtagVARIANT@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvargSrc)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000e1f8`
- `0x18000f3b0`
- `0x180013020`
- `0x18001916c`
- `0x1800192c8`
- `0x18001cce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000f3ed`
- `OLEAUT32!__imp_VariantInit` at `0x18000f3ed`
- `OLEAUT32!__imp_VariantClear` at `0x18000f512`
- `OLEAUT32!__imp_VariantClear` at `0x18000f52d`
- `OLEAUT32!__imp_VariantClear` at `0x18000f512`
- `OLEAUT32!__imp_VariantClear` at `0x18000f52d`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f3fa`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000f3fa`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f523`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000f523`

## pseudocode

```c
__int64 __fastcall CIPSecurity::put_IPDeny(CIPSecurity *this, VARIANTARG *pvargSrc)
{
  VARIANTARG *v3; // rdi
  int v5; // ebx
  int v6; // eax
  unsigned int v7; // esi
  LPCWCH *p_pvarg; // r14
  int v9; // r15d
  int v10; // eax
  __int64 i; // r14
  LPVOID pMem; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  struct tagVARIANT v15; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+A0h] [rbp+40h] BYREF
  char *v17; // [rsp+A8h] [rbp+48h] BYREF

  v3 = 0;
  v16 = 0;
  pMem = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v17 = 0;
  VariantInit(&pvarg);
  v5 = VariantCopyInd(&pvarg, pvargSrc);
  if ( v5 < 0 )
    goto LABEL_27;
  if ( ((pvarg.vt & 0xFFF) != 0xC || (pvarg.vt & 0x2000) == 0) && ((pvarg.vt & 0xFFF) != 8 || (pvarg.vt & 0x2000) == 0) )
  {
    v7 = 1;
    p_pvarg = (LPCWCH *)&pvarg;
LABEL_9:
    ADDRESS_CHECK::DeleteAllAddr((CIPSecurity *)((char *)this + 24), 0);
    v9 = 0;
    if ( v7 )
    {
      while ( 1 )
      {
        if ( *(_WORD *)p_pvarg != 8 )
        {
          v5 = -2147463156;
          goto LABEL_23;
        }
        v10 = AllocAnsi(p_pvarg[1], &v17);
        if ( v10 )
          break;
        if ( v17 )
        {
          if ( !CIPSecurity::AddToList(this, 1, 0, v17) )
            v5 = -2147024809;
          FreeAnsi(v17);
          v17 = 0;
          if ( v5 < 0 )
            goto LABEL_23;
        }
        if ( ++v9 >= v7 )
          goto LABEL_23;
        p_pvarg += 3;
      }
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      else
        v5 = v10;
    }
    goto LABEL_23;
  }
  v15 = pvarg;
  v6 = ConvertArrayToVariantArray(&v15, (struct tagVARIANT **)&pMem, &v16);
  v3 = (VARIANTARG *)pMem;
  v5 = v6;
  v7 = v16;
  if ( v6 >= 0 )
  {
    p_pvarg = (LPCWCH *)pMem;
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
0x18000f3b0  mov     [rsp-28h+arg_0], rbx
0x18000f3b5  mov     [rsp-28h+arg_8], rsi
0x18000f3ba  push    rbp
0x18000f3bb  push    rdi
0x18000f3bc  push    r13
0x18000f3be  push    r14
0x18000f3c0  push    r15
0x18000f3c2  mov     rbp, rsp
0x18000f3c5  sub     rsp, 60h
0x18000f3c9  xor     eax, eax
0x18000f3cb  mov     r13, rcx
0x18000f3ce  xorps   xmm0, xmm0
0x18000f3d1  mov     qword ptr [rbp+pvarg+10h], rax
0x18000f3d5  xor     edi, edi
0x18000f3d7  mov     [rbp+arg_10], eax
0x18000f3da  lea     rcx, [rbp+pvarg]; pvarg
0x18000f3de  mov     [rbp+pMem], rdi
0x18000f3e2  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000f3e6  mov     [rbp+arg_18], rax
0x18000f3ea  mov     rbx, rdx
0x18000f3ed  call    cs:__imp_VariantInit
0x18000f3f3  mov     rdx, rbx; pvargSrc
0x18000f3f6  lea     rcx, [rbp+pvarg]; pvarDest
0x18000f3fa  call    cs:__imp_VariantCopyInd
0x18000f400  mov     ebx, eax
0x18000f402  test    eax, eax
0x18000f404  js      loc_18000F529
0x18000f40a  movzx   ecx, word ptr [rbp+pvarg]
0x18000f40e  mov     edx, 0FFFh
0x18000f413  movzx   eax, cx
0x18000f416  and     ax, dx
0x18000f419  cmp     ax, 0Ch
0x18000f41d  jnz     short loc_18000F426
0x18000f41f  bt      cx, 0Dh
0x18000f424  jb      short loc_18000F433
0x18000f426  cmp     ax, 8
0x18000f42a  jnz     short loc_18000F46C
0x18000f42c  bt      cx, 0Dh
0x18000f431  jnb     short loc_18000F46C
0x18000f433  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000f437  lea     r8, [rbp+arg_10]; unsigned int *
0x18000f43b  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000f440  lea     rdx, [rbp+pMem]; struct tagVARIANT **
0x18000f444  lea     rcx, [rbp+var_20]; struct tagVARIANT
0x18000f448  movaps  xmmword ptr [rbp+var_20], xmm0
0x18000f44c  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18000f451  call    ?ConvertArrayToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertArrayToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x18000f456  mov     rdi, [rbp+pMem]
0x18000f45a  mov     ebx, eax
0x18000f45c  mov     esi, [rbp+arg_10]
0x18000f45f  test    eax, eax
0x18000f461  js      loc_18000F4FE
0x18000f467  mov     r14, rdi
0x18000f46a  jmp     short loc_18000F475
0x18000f46c  mov     esi, 1
0x18000f471  lea     r14, [rbp+pvarg]
0x18000f475  lea     rcx, [r13+18h]; this
0x18000f479  xor     edx, edx; int
0x18000f47b  call    ?DeleteAllAddr@ADDRESS_CHECK@@QEAAHH@Z; ADDRESS_CHECK::DeleteAllAddr(int)
0x18000f480  xor     r15d, r15d
0x18000f483  test    esi, esi
0x18000f485  jz      short loc_18000F4FE
0x18000f487  cmp     word ptr [r14], 8
0x18000f48c  jnz     short loc_18000F4F9
0x18000f48e  mov     rcx, [r14+8]; lpWideCharStr
0x18000f492  lea     rdx, [rbp+arg_18]; char **
0x18000f496  call    ?AllocAnsi@@YAIPEBGPEAPEAD@Z; AllocAnsi(ushort const *,char * *)
0x18000f49b  test    eax, eax
0x18000f49d  jz      short loc_18000F4B2
0x18000f49f  jg      short loc_18000F4A5
0x18000f4a1  mov     ebx, eax
0x18000f4a3  jmp     short loc_18000F4AE
0x18000f4a5  movzx   ebx, ax
0x18000f4a8  or      ebx, 80070000h
0x18000f4ae  test    ebx, ebx
0x18000f4b0  js      short loc_18000F4FE
0x18000f4b2  cmp     [rbp+arg_18], 0
0x18000f4b7  jz      short loc_18000F4EB
0x18000f4b9  mov     r9, [rbp+arg_18]; char *
0x18000f4bd  xor     r8d, r8d; int
0x18000f4c0  mov     rcx, r13; this
0x18000f4c3  lea     edx, [r8+1]; int
0x18000f4c7  call    ?AddToList@CIPSecurity@@QEAAHHHPEAD@Z; CIPSecurity::AddToList(int,int,char *)
0x18000f4cc  test    eax, eax
0x18000f4ce  mov     ecx, 80070057h
0x18000f4d3  cmovz   ebx, ecx
0x18000f4d6  mov     rcx, [rbp+arg_18]; char *
0x18000f4da  call    ?FreeAnsi@@YAXPEAD@Z; FreeAnsi(char *)
0x18000f4df  mov     [rbp+arg_18], 0
0x18000f4e7  test    ebx, ebx
0x18000f4e9  js      short loc_18000F4FE
0x18000f4eb  inc     r15d
0x18000f4ee  cmp     r15d, esi
0x18000f4f1  jnb     short loc_18000F4FE
0x18000f4f3  add     r14, 18h
0x18000f4f7  jmp     short loc_18000F487
0x18000f4f9  mov     ebx, 8000500Ch
0x18000f4fe  test    rdi, rdi
0x18000f501  jz      short loc_18000F529
0x18000f503  xor     r14d, r14d
0x18000f506  test    esi, esi
0x18000f508  jz      short loc_18000F520
0x18000f50a  lea     rdx, [r14+r14*2]
0x18000f50e  lea     rcx, [rdi+rdx*8]; pvarg
0x18000f512  call    cs:__imp_VariantClear
0x18000f518  inc     r14d
0x18000f51b  cmp     r14d, esi
0x18000f51e  jb      short loc_18000F50A
0x18000f520  mov     rcx, rdi; pMem
0x18000f523  call    cs:__imp_FreeADsMem
0x18000f529  lea     rcx, [rbp+pvarg]; pvarg
0x18000f52d  call    cs:__imp_VariantClear
0x18000f533  lea     r11, [rsp+60h+var_s0]
0x18000f538  mov     eax, ebx
0x18000f53a  mov     rbx, [r11+30h]
0x18000f53e  mov     rsi, [r11+38h]
0x18000f542  mov     rsp, r11
0x18000f545  pop     r15
0x18000f547  pop     r14
0x18000f549  pop     r13
0x18000f54b  pop     rdi
0x18000f54c  pop     rbp
0x18000f54d  retn
```

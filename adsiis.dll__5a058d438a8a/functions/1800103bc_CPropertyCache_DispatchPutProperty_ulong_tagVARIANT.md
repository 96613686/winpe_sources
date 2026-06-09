# CPropertyCache::DispatchPutProperty(ulong,tagVARIANT &)

- ea: `0x1800103bc`
- end: `0x18001070b`
- name: `?DispatchPutProperty@CPropertyCache@@IEAAJKAEAUtagVARIANT@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x180011020`

## callees

- `0x1800103bc`
- `0x180010968`
- `0x1800109ec`
- `0x180010bf8`
- `0x180010cd8`
- `0x180010ecc`
- `0x180013020`
- `0x180013190`
- `0x1800184ac`
- `0x180018c08`
- `0x18001b3a8`
- `0x18001b3ec`
- `0x18001b524`
- `0x18001d6c0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001042b`
- `OLEAUT32!__imp_VariantInit` at `0x18001042b`
- `OLEAUT32!__imp_VariantClear` at `0x1800106bd`
- `OLEAUT32!__imp_VariantClear` at `0x1800106d9`
- `OLEAUT32!__imp_VariantClear` at `0x1800106bd`
- `OLEAUT32!__imp_VariantClear` at `0x1800106d9`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180010481`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180010481`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800106ce`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800106ce`

## pseudocode

```c
__int64 __fastcall CPropertyCache::DispatchPutProperty(CPropertyCache *this, unsigned int a2, struct tagVARIANT *a3)
{
  __int64 v3; // rsi
  VARIANTARG *v5; // rdi
  HRESULT Schema; // ebx
  unsigned __int16 *v9; // r15
  int v10; // eax
  unsigned int v11; // esi
  struct tagVARIANT *p_pvarg; // rdx
  int v13; // eax
  unsigned int v14; // r13d
  int v15; // eax
  unsigned int v16; // r9d
  struct _iistype *v17; // r12
  IIsSchema *v18; // rcx
  unsigned int v19; // r9d
  struct _iistype *v20; // r8
  int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // r8d
  unsigned int v24; // r9d
  __int64 i; // r14
  struct _iistype **v26; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID pMem; // [rsp+38h] [rbp-C8h] BYREF
  struct _iistype *v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvargSrc; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v34[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = a2;
  v28 = -1;
  v31 = -1;
  v30 = 0;
  v5 = 0;
  v27 = 0;
  pMem = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  Schema = CPropertyCache::LoadSchema(this);
  if ( Schema >= 0 )
  {
    if ( (unsigned int)v3 >= *((_DWORD *)this + 25) )
      return 2147614723LL;
    v9 = (unsigned __int16 *)(*((_QWORD *)this + 11) + 520 * v3);
    Schema = IIsSchema::LookupSyntaxID(*((IIsSchema **)this + 9), v9, &v28);
    if ( Schema >= 0 )
    {
      Schema = VariantCopyInd(&pvarg, a3);
      if ( Schema >= 0 )
      {
        if ( pvarg.vt == 9 )
        {
          pvargSrc = pvarg;
          v10 = ConvertDispatchToVariantArray(&pvargSrc, (struct tagVARIANT **)&pMem, &v27);
          v5 = (VARIANTARG *)pMem;
          if ( !v10 )
          {
            v11 = v27;
            p_pvarg = (struct tagVARIANT *)pMem;
            goto LABEL_14;
          }
        }
        else if ( (pvarg.vt & 0xFFF) == 0xC && (pvarg.vt & 0x2000) != 0 )
        {
          pvargSrc = pvarg;
          v13 = ConvertArrayToVariantArray(&pvargSrc, (struct tagVARIANT **)&pMem, &v27);
          v5 = (VARIANTARG *)pMem;
          Schema = v13;
          v11 = v27;
          if ( v13 < 0 )
          {
LABEL_33:
            if ( v5 )
            {
              for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
                VariantClear(&v5[i]);
              FreeADsMem(v5);
            }
            goto LABEL_37;
          }
          p_pvarg = (struct tagVARIANT *)pMem;
LABEL_14:
          v14 = v28;
          v15 = VarTypeToIISTypeCopyConstruct(v28, p_pvarg, v11, &v30, 0, *((const unsigned __int16 **)this + 10));
          v17 = v30;
          Schema = v15;
          if ( v15 < 0 )
            goto LABEL_31;
          if ( v14 == 7 )
          {
            v18 = (IIsSchema *)*((_QWORD *)this + 9);
            v27 = 0;
            v30 = 0;
            Schema = IIsSchema::LookupBitMask(v18, v9, &v27);
            if ( Schema < 0 )
              goto LABEL_31;
            Schema = IIsSchema::LookupFlagPropName(*((IIsSchema **)this + 9), v9, v34, v19);
            if ( Schema < 0 )
              goto LABEL_31;
            Schema = CPropertyCache::getproperty(this, v34, &v28, &v28, &v30);
            if ( Schema < 0 )
              goto LABEL_31;
            v20 = v30;
            v21 = *((_DWORD *)v30 + 2);
            if ( *((_DWORD *)v17 + 2) )
              v22 = v27 | v21;
            else
              v22 = ~v27 & v21;
            *((_DWORD *)v17 + 2) = v22;
            v9 = v34;
            *(_DWORD *)v17 = 1;
            IISTypeFreeIISObjects(v20, 1u);
          }
          if ( v14 != 5 )
          {
LABEL_26:
            if ( CPropertyCache::findproperty(this, v9, &v31) >= 0
              || (Schema = CPropertyCache::addproperty(this, v9, v23, v24, (struct _iistype *)v26), Schema >= 0) )
            {
              if ( v14 == 7 )
                v14 = 1;
              Schema = CPropertyCache::putproperty(this, v9, 1u, v14, v11, v17);
            }
            goto LABEL_31;
          }
          Schema = IIsSchema::LookupFlagPropName(*((IIsSchema **)this + 9), v9, v34, v16);
          if ( Schema >= 0 )
          {
            v9 = v34;
            goto LABEL_26;
          }
LABEL_31:
          if ( v17 )
            IISTypeFreeIISObjects(v17, v11);
          goto LABEL_33;
        }
        p_pvarg = &pvarg;
        v11 = 1;
        goto LABEL_14;
      }
    }
  }
LABEL_37:
  VariantClear(&pvarg);
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x1800103bc  mov     [rsp-8+arg_18], rbx
0x1800103c1  push    rbp
0x1800103c2  push    rsi
0x1800103c3  push    rdi
0x1800103c4  push    r12
0x1800103c6  push    r13
0x1800103c8  push    r14
0x1800103ca  push    r15
0x1800103cc  lea     rbp, [rsp-1B0h]
0x1800103d4  sub     rsp, 2B0h
0x1800103db  mov     rax, cs:__security_cookie
0x1800103e2  xor     rax, rsp
0x1800103e5  mov     [rbp+1E0h+var_40], rax
0x1800103ec  or      eax, 0FFFFFFFFh
0x1800103ef  mov     esi, edx
0x1800103f1  mov     [rsp+2E0h+var_2AC], eax
0x1800103f5  mov     r14, rcx
0x1800103f8  mov     [rsp+2E0h+var_298], eax
0x1800103fc  lea     rcx, [rsp+2E0h+pvarg]; pvarg
0x180010401  xor     eax, eax
0x180010403  mov     [rsp+2E0h+var_2A0], 0
0x18001040c  xorps   xmm0, xmm0
0x18001040f  mov     qword ptr [rsp+2E0h+pvarg+10h], rax
0x180010414  xor     edi, edi
0x180010416  mov     [rsp+2E0h+var_2B0], 0
0x18001041e  mov     r12, r8
0x180010421  mov     [rsp+2E0h+pMem], rdi
0x180010426  movups  xmmword ptr [rsp+2E0h+pvarg], xmm0
0x18001042b  call    cs:__imp_VariantInit
0x180010431  mov     rcx, r14; this
0x180010434  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x180010439  mov     ebx, eax
0x18001043b  test    eax, eax
0x18001043d  js      loc_1800106D4
0x180010443  cmp     esi, [r14+64h]
0x180010447  jb      short loc_180010453
0x180010449  mov     eax, 80020003h
0x18001044e  jmp     loc_1800106E1
0x180010453  mov     rcx, [r14+48h]; this
0x180010457  lea     r8, [rsp+2E0h+var_2AC]; unsigned int *
0x18001045c  imul    r15, rsi, 208h
0x180010463  add     r15, [r14+58h]
0x180010467  mov     rdx, r15; unsigned __int16 *
0x18001046a  call    ?LookupSyntaxID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupSyntaxID(ushort const *,ulong *)
0x18001046f  mov     ebx, eax
0x180010471  test    eax, eax
0x180010473  js      loc_1800106D4
0x180010479  mov     rdx, r12; pvargSrc
0x18001047c  lea     rcx, [rsp+2E0h+pvarg]; pvarDest
0x180010481  call    cs:__imp_VariantCopyInd
0x180010487  mov     ebx, eax
0x180010489  test    eax, eax
0x18001048b  js      loc_1800106D4
0x180010491  movzx   ecx, word ptr [rsp+2E0h+pvarg]
0x180010496  mov     r12d, 1
0x18001049c  cmp     cx, 9
0x1800104a0  jnz     short loc_1800104DD
0x1800104a2  movups  xmm0, xmmword ptr [rsp+2E0h+pvarg]
0x1800104a7  lea     r8, [rsp+2E0h+var_2B0]; unsigned int *
0x1800104ac  movsd   xmm1, qword ptr [rsp+2E0h+pvarg+10h]
0x1800104b2  lea     rdx, [rsp+2E0h+pMem]; struct tagVARIANT **
0x1800104b7  lea     rcx, [rsp+2E0h+pvargSrc]; pvargSrc
0x1800104bc  movaps  xmmword ptr [rsp+2E0h+pvargSrc], xmm0
0x1800104c1  movsd   qword ptr [rbp+1E0h+pvargSrc+10h], xmm1
0x1800104c6  call    ?ConvertDispatchToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertDispatchToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x1800104cb  mov     rdi, [rsp+2E0h+pMem]
0x1800104d0  test    eax, eax
0x1800104d2  jnz     short loc_180010536
0x1800104d4  mov     esi, [rsp+2E0h+var_2B0]
0x1800104d8  mov     rdx, rdi
0x1800104db  jmp     short loc_18001053E
0x1800104dd  movzx   eax, cx
0x1800104e0  mov     edx, 0FFFh
0x1800104e5  and     ax, dx
0x1800104e8  cmp     ax, 0Ch
0x1800104ec  jnz     short loc_180010536
0x1800104ee  bt      cx, 0Dh
0x1800104f3  jnb     short loc_180010536
0x1800104f5  movups  xmm0, xmmword ptr [rsp+2E0h+pvarg]
0x1800104fa  lea     r8, [rsp+2E0h+var_2B0]; unsigned int *
0x1800104ff  movsd   xmm1, qword ptr [rsp+2E0h+pvarg+10h]
0x180010505  lea     rdx, [rsp+2E0h+pMem]; struct tagVARIANT **
0x18001050a  lea     rcx, [rsp+2E0h+pvargSrc]; struct tagVARIANT
0x18001050f  movaps  xmmword ptr [rsp+2E0h+pvargSrc], xmm0
0x180010514  movsd   qword ptr [rbp+1E0h+pvargSrc+10h], xmm1
0x180010519  call    ?ConvertArrayToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertArrayToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x18001051e  mov     rdi, [rsp+2E0h+pMem]
0x180010523  mov     ebx, eax
0x180010525  mov     esi, [rsp+2E0h+var_2B0]
0x180010529  test    eax, eax
0x18001052b  js      loc_1800106A9
0x180010531  mov     rdx, rdi
0x180010534  jmp     short loc_18001053E
0x180010536  lea     rdx, [rsp+2E0h+pvarg]; struct tagVARIANT *
0x18001053b  mov     esi, r12d
0x18001053e  mov     rax, [r14+50h]
0x180010542  lea     r9, [rsp+2E0h+var_2A0]; struct _iistype **
0x180010547  mov     r13d, [rsp+2E0h+var_2AC]
0x18001054c  mov     r8d, esi; unsigned int
0x18001054f  mov     [rsp+2E0h+var_2B8], rax; unsigned __int16 *
0x180010554  mov     ecx, r13d; unsigned int
0x180010557  mov     dword ptr [rsp+2E0h+var_2C0], 0; int
0x18001055f  call    ?VarTypeToIISTypeCopyConstruct@@YAJKPEAUtagVARIANT@@KPEAPEAU_iistype@@HPEBG@Z; VarTypeToIISTypeCopyConstruct(ulong,tagVARIANT *,ulong,_iistype * *,int,ushort const *)
0x180010564  mov     r12, [rsp+2E0h+var_2A0]
0x180010569  mov     ebx, eax
0x18001056b  test    eax, eax
0x18001056d  js      loc_180010694
0x180010573  cmp     r13d, 7
0x180010577  jnz     loc_180010626
0x18001057d  mov     rcx, [r14+48h]; this
0x180010581  lea     r8, [rsp+2E0h+var_2B0]; unsigned int *
0x180010586  mov     rdx, r15; unsigned __int16 *
0x180010589  mov     [rsp+2E0h+var_2B0], 0
0x180010591  mov     [rsp+2E0h+var_2A0], 0
0x18001059a  call    ?LookupBitMask@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupBitMask(ushort const *,ulong *)
0x18001059f  mov     ebx, eax
0x1800105a1  test    eax, eax
0x1800105a3  js      loc_180010694
0x1800105a9  mov     rcx, [r14+48h]; this
0x1800105ad  lea     r8, [rbp+1E0h+var_250]; unsigned __int16 *
0x1800105b1  mov     rdx, r15; unsigned __int16 *
0x1800105b4  call    ?LookupFlagPropName@IIsSchema@@QEAAJPEBGPEAGK@Z; IIsSchema::LookupFlagPropName(ushort const *,ushort *,ulong)
0x1800105b9  mov     ebx, eax
0x1800105bb  test    eax, eax
0x1800105bd  js      loc_180010694
0x1800105c3  lea     rax, [rsp+2E0h+var_2A0]
0x1800105c8  mov     rcx, r14; this
0x1800105cb  lea     r9, [rsp+2E0h+var_2AC]; unsigned int *
0x1800105d0  mov     [rsp+2E0h+var_2C0], rax; struct _iistype *
0x1800105d5  lea     r8, [rsp+2E0h+var_2AC]; unsigned int *
0x1800105da  lea     rdx, [rbp+1E0h+var_250]; unsigned __int16 *
0x1800105de  call    ?getproperty@CPropertyCache@@QEAAJPEAGPEAK1PEAPEAU_iistype@@@Z; CPropertyCache::getproperty(ushort *,ulong *,ulong *,_iistype * *)
0x1800105e3  mov     ebx, eax
0x1800105e5  test    eax, eax
0x1800105e7  js      loc_180010694
0x1800105ed  cmp     dword ptr [r12+8], 0
0x1800105f3  mov     r8, [rsp+2E0h+var_2A0]
0x1800105f8  mov     ecx, [r8+8]
0x1800105fc  jz      short loc_180010604
0x1800105fe  or      ecx, [rsp+2E0h+var_2B0]
0x180010602  jmp     short loc_18001060C
0x180010604  mov     eax, [rsp+2E0h+var_2B0]
0x180010608  not     eax
0x18001060a  and     ecx, eax
0x18001060c  mov     [r12+8], ecx
0x180010611  lea     r15, [rbp+1E0h+var_250]
0x180010615  mov     edx, 1; unsigned int
0x18001061a  mov     rcx, r8; struct _iistype *
0x18001061d  mov     [r12], edx
0x180010621  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180010626  cmp     r13d, 5
0x18001062a  jnz     short loc_180010646
0x18001062c  mov     rcx, [r14+48h]; this
0x180010630  lea     r8, [rbp+1E0h+var_250]; unsigned __int16 *
0x180010634  mov     rdx, r15; unsigned __int16 *
0x180010637  call    ?LookupFlagPropName@IIsSchema@@QEAAJPEBGPEAGK@Z; IIsSchema::LookupFlagPropName(ushort const *,ushort *,ulong)
0x18001063c  mov     ebx, eax
0x18001063e  test    eax, eax
0x180010640  js      short loc_180010694
0x180010642  lea     r15, [rbp+1E0h+var_250]
0x180010646  lea     r8, [rsp+2E0h+var_298]; unsigned int *
0x18001064b  mov     rdx, r15; unsigned __int16 *
0x18001064e  mov     rcx, r14; this
0x180010651  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180010656  test    eax, eax
0x180010658  jns     short loc_18001066B
0x18001065a  mov     rdx, r15; unsigned __int16 *
0x18001065d  mov     rcx, r14; this
0x180010660  call    ?addproperty@CPropertyCache@@QEAAJPEAGKKPEAU_iistype@@@Z; CPropertyCache::addproperty(ushort *,ulong,ulong,_iistype *)
0x180010665  mov     ebx, eax
0x180010667  test    eax, eax
0x180010669  js      short loc_180010694
0x18001066b  mov     eax, 1
0x180010670  mov     [rsp+2E0h+var_2B8], r12; struct _iistype *
0x180010675  cmp     r13d, 7
0x180010679  mov     dword ptr [rsp+2E0h+var_2C0], esi; unsigned int
0x18001067d  mov     r8d, eax; unsigned int
0x180010680  mov     rdx, r15; unsigned __int16 *
0x180010683  cmovz   r13d, eax
0x180010687  mov     rcx, r14; this
0x18001068a  mov     r9d, r13d; unsigned int
0x18001068d  call    ?putproperty@CPropertyCache@@QEAAJPEAGKKKPEAU_iistype@@@Z; CPropertyCache::putproperty(ushort *,ulong,ulong,ulong,_iistype *)
0x180010692  mov     ebx, eax
0x180010694  test    r12, r12
0x180010697  jz      short loc_1800106A3
0x180010699  mov     edx, esi; unsigned int
0x18001069b  mov     rcx, r12; struct _iistype *
0x18001069e  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x1800106a3  mov     r12d, 1
0x1800106a9  test    rdi, rdi
0x1800106ac  jz      short loc_1800106D4
0x1800106ae  xor     r14d, r14d
0x1800106b1  test    esi, esi
0x1800106b3  jz      short loc_1800106CB
0x1800106b5  lea     rdx, [r14+r14*2]
0x1800106b9  lea     rcx, [rdi+rdx*8]; pvarg
0x1800106bd  call    cs:__imp_VariantClear
0x1800106c3  add     r14d, r12d
0x1800106c6  cmp     r14d, esi
0x1800106c9  jb      short loc_1800106B5
0x1800106cb  mov     rcx, rdi; pMem
0x1800106ce  call    cs:__imp_FreeADsMem
0x1800106d4  lea     rcx, [rsp+2E0h+pvarg]; pvarg
0x1800106d9  call    cs:__imp_VariantClear
0x1800106df  mov     eax, ebx
0x1800106e1  mov     rcx, [rbp+1E0h+var_40]
0x1800106e8  xor     rcx, rsp; StackCookie
0x1800106eb  call    __security_check_cookie
0x1800106f0  mov     rbx, [rsp+2E0h+arg_18]
0x1800106f8  add     rsp, 2B0h
0x1800106ff  pop     r15
0x180010701  pop     r14
0x180010703  pop     r13
0x180010705  pop     r12
0x180010707  pop     rdi
0x180010708  pop     rsi
0x180010709  pop     rbp
0x18001070a  retn
```

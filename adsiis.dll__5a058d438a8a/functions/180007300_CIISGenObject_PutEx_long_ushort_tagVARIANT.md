# CIISGenObject::PutEx(long,ushort *,tagVARIANT)

- ea: `0x180007300`
- end: `0x1800076e4`
- name: `?PutEx@CIISGenObject@@UEAAJJPEAGUtagVARIANT@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(CIISGenObject *this, int, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180007300`
- `0x18000c690`
- `0x1800109ec`
- `0x180010bf8`
- `0x180010ecc`
- `0x180013020`
- `0x1800184ac`
- `0x180018c08`
- `0x18001b3a8`
- `0x18001b3ec`
- `0x18001b524`
- `0x18001bc84`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007583`
- `OLEAUT32!__imp_SysAllocString` at `0x180007583`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000766d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000766d`
- `OLEAUT32!__imp_VariantInit` at `0x1800073fd`
- `OLEAUT32!__imp_VariantInit` at `0x180007572`
- `OLEAUT32!__imp_VariantInit` at `0x1800073fd`
- `OLEAUT32!__imp_VariantInit` at `0x180007572`
- `OLEAUT32!__imp_VariantClear` at `0x18000748d`
- `OLEAUT32!__imp_VariantClear` at `0x18000769e`
- `OLEAUT32!__imp_VariantClear` at `0x18000748d`
- `OLEAUT32!__imp_VariantClear` at `0x18000769e`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000740c`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000740c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800076b2`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800076b2`

## pseudocode

```c
__int64 __fastcall CIISGenObject::PutEx(CIISGenObject *this, int a2, unsigned __int16 *a3, struct tagVARIANT *a4)
{
  OLECHAR *v5; // rsi
  struct _iistype *v8; // r14
  unsigned int v9; // r12d
  struct tagVARIANT *v10; // r13
  unsigned int v11; // edi
  unsigned int v12; // r9d
  int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  IIsSchema *v16; // rcx
  __int64 (__fastcall *v17)(CIISGenObject *, OLECHAR *, VARIANTARG *); // rdi
  OLECHAR *v18; // rbx
  unsigned int v19; // ecx
  unsigned int v20; // r8d
  unsigned int v21; // r9d
  __int64 v22; // rbx
  struct _iistype *v23; // [rsp+20h] [rbp-E0h]
  HRESULT CoreADsClass; // [rsp+30h] [rbp-D0h]
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v26; // [rsp+38h] [rbp-C8h] BYREF
  struct tagVARIANT *v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-B8h] BYREF
  struct _iistype *v29; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v32; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG *pvargSrc; // [rsp+A0h] [rbp-60h]
  OLECHAR psz[264]; // [rsp+B0h] [rbp-50h] BYREF

  pvargSrc = a4;
  v5 = a3;
  if ( !a3 )
    return 2147500035LL;
  v26 = 0;
  v28 = 0;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  v25 = 0;
  v10 = 0;
  v27 = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  CoreADsClass = CCoreADsObject::get_CoreADsClass((CIISGenObject *)((char *)this - 64), &bstrString);
  v11 = CoreADsClass;
  if ( CoreADsClass < 0 )
    goto LABEL_39;
  CoreADsClass = IIsSchema::ValidateProperty(*((IIsSchema **)this + 18), bstrString, v5);
  v11 = CoreADsClass;
  if ( CoreADsClass < 0 )
    goto LABEL_39;
  CoreADsClass = IIsSchema::LookupSyntaxID(*((IIsSchema **)this + 18), v5, &v26);
  v11 = CoreADsClass;
  if ( CoreADsClass < 0 )
    goto LABEL_39;
  v13 = a2 - 1;
  if ( v13 )
  {
    if ( v13 != 1 )
      return 2147504136LL;
    VariantInit(&pvarg);
    CoreADsClass = VariantCopyInd(&pvarg, pvargSrc);
    v11 = CoreADsClass;
    if ( CoreADsClass < 0 )
      goto LABEL_39;
    if ( ((pvarg.vt & 0xFFF) != 0xC || (pvarg.vt & 0x2000) == 0)
      && ((pvarg.vt & 0xFFF) != 8 || (pvarg.vt & 0x2000) == 0) )
    {
      v11 = -2147467259;
      CoreADsClass = -2147467259;
      goto LABEL_39;
    }
    v32 = pvarg;
    v14 = ConvertArrayToVariantArray(&v32, &v27, &v25);
    v10 = v27;
    v11 = v14;
    CoreADsClass = v14;
    if ( v14 < 0 )
    {
      v9 = v25;
      goto LABEL_39;
    }
    VariantClear(&pvarg);
    v9 = v25;
    v15 = v26;
    CoreADsClass = VarTypeToIISTypeCopyConstruct(v26, v10, v25, &v29, 1, *((const unsigned __int16 **)this + 9));
    v11 = CoreADsClass;
    if ( CoreADsClass < 0 )
    {
      v8 = v29;
      goto LABEL_39;
    }
    LODWORD(v27) = 1;
    v8 = v29;
  }
  else
  {
    v15 = v26;
    LODWORD(v27) = 2;
  }
  if ( v15 == 7 )
  {
    v16 = (IIsSchema *)*((_QWORD *)this + 18);
    memset(&v32, 0, sizeof(v32));
    v25 = 0;
    CoreADsClass = IIsSchema::LookupFlagPropName(v16, v5, psz, v12);
    v11 = CoreADsClass;
    if ( CoreADsClass < 0 )
      goto LABEL_39;
    if ( (_DWORD)v27 != 2 )
    {
      CoreADsClass = IIsSchema::LookupBitMask(*((IIsSchema **)this + 18), v5, &v25);
      v11 = CoreADsClass;
      if ( CoreADsClass < 0 )
        goto LABEL_39;
      VariantInit(&v32);
      v17 = *(__int64 (__fastcall **)(CIISGenObject *, OLECHAR *, VARIANTARG *))(*(_QWORD *)this + 120LL);
      v18 = SysAllocString(psz);
      CoreADsClass = v17(this, v18, &v32);
      v11 = CoreADsClass;
      SysFreeString(v18);
      if ( CoreADsClass < 0 )
        goto LABEL_39;
      if ( *((_DWORD *)v8 + 2) )
        v19 = v25 | v32.lVal;
      else
        v19 = ~v25 & v32.lVal;
      v15 = v26;
      *((_DWORD *)v8 + 2) = v19;
      *(_DWORD *)v8 = 1;
    }
    v5 = psz;
  }
  if ( v15 != 5 )
  {
LABEL_34:
    if ( CPropertyCache::findproperty(*((CPropertyCache **)this + 11), v5, &v28) >= 0
      || (CoreADsClass = CPropertyCache::addproperty(*((CPropertyCache **)this + 11), v5, v20, v21, v23),
          v11 = CoreADsClass,
          CoreADsClass >= 0) )
    {
      if ( v15 == 7 )
        v15 = 1;
      v11 = CPropertyCache::putproperty(*((CPropertyCache **)this + 11), v5, (unsigned int)v27, v15, v9, v8);
      CoreADsClass = v11;
    }
    goto LABEL_39;
  }
  CoreADsClass = IIsSchema::LookupFlagPropName(*((IIsSchema **)this + 18), v5, psz, v12);
  v11 = CoreADsClass;
  if ( CoreADsClass >= 0 )
  {
    v5 = psz;
    goto LABEL_34;
  }
LABEL_39:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v8 )
    IISTypeFreeIISObjects(v8, v9);
  if ( v10 )
  {
    v22 = 0;
    if ( v9 )
    {
      do
      {
        VariantClear(&v10[v22]);
        v22 = (unsigned int)(v22 + 1);
      }
      while ( (unsigned int)v22 < v9 );
      v11 = CoreADsClass;
    }
    FreeADsMem(v10);
  }
  return v11;
}

```

## disassembly

```asm
0x180007300  mov     [rsp-8+arg_8], rbx
0x180007305  push    rbp
0x180007306  push    rsi
0x180007307  push    rdi
0x180007308  push    r12
0x18000730a  push    r13
0x18000730c  push    r14
0x18000730e  push    r15
0x180007310  lea     rbp, [rsp-1D0h]
0x180007318  sub     rsp, 2D0h
0x18000731f  mov     rax, cs:__security_cookie
0x180007326  xor     rax, rsp
0x180007329  mov     [rbp+200h+var_40], rax
0x180007330  mov     r15, rcx
0x180007333  mov     [rbp+200h+pvargSrc], r9
0x180007337  xor     ecx, ecx
0x180007339  mov     rsi, r8
0x18000733c  mov     ebx, edx
0x18000733e  test    r8, r8
0x180007341  jnz     short loc_18000734D
0x180007343  mov     eax, 80004003h
0x180007348  jmp     loc_1800076BA
0x18000734d  mov     [rsp+300h+var_2C8], ecx
0x180007351  lea     rdx, [rsp+300h+bstrString]; unsigned __int16 **
0x180007356  mov     [rsp+300h+var_2B8], ecx
0x18000735a  mov     r14, rcx
0x18000735d  mov     [rsp+300h+var_2B0], rcx
0x180007362  mov     r12d, ecx
0x180007365  mov     [rsp+300h+var_2CC], ecx
0x180007369  mov     r13, rcx
0x18000736c  mov     [rsp+300h+var_2C0], rcx
0x180007371  xorps   xmm0, xmm0
0x180007374  xor     eax, eax
0x180007376  mov     [rsp+300h+bstrString], rcx
0x18000737b  lea     rcx, [r15-40h]; this
0x18000737f  mov     qword ptr [rsp+300h+pvarg+10h], rax
0x180007384  movups  xmmword ptr [rsp+300h+pvarg], xmm0
0x180007389  call    ?get_CoreADsClass@CCoreADsObject@@QEAAJPEAPEAG@Z; CCoreADsObject::get_CoreADsClass(ushort * *)
0x18000738e  mov     [rsp+300h+var_2D0], eax
0x180007392  mov     edi, eax
0x180007394  test    eax, eax
0x180007396  js      loc_180007660
0x18000739c  mov     rdx, [rsp+300h+bstrString]; unsigned __int16 *
0x1800073a1  mov     r8, rsi; unsigned __int16 *
0x1800073a4  mov     rcx, [r15+90h]; this
0x1800073ab  call    ?ValidateProperty@IIsSchema@@QEAAJPEBG0@Z; IIsSchema::ValidateProperty(ushort const *,ushort const *)
0x1800073b0  mov     [rsp+300h+var_2D0], eax
0x1800073b4  mov     edi, eax
0x1800073b6  test    eax, eax
0x1800073b8  js      loc_180007660
0x1800073be  mov     rcx, [r15+90h]; this
0x1800073c5  lea     r8, [rsp+300h+var_2C8]; unsigned int *
0x1800073ca  mov     rdx, rsi; unsigned __int16 *
0x1800073cd  call    ?LookupSyntaxID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupSyntaxID(ushort const *,ulong *)
0x1800073d2  mov     [rsp+300h+var_2D0], eax
0x1800073d6  mov     edi, eax
0x1800073d8  test    eax, eax
0x1800073da  js      loc_180007660
0x1800073e0  sub     ebx, 1
0x1800073e3  jz      loc_1800074FA
0x1800073e9  sub     ebx, 1
0x1800073ec  jz      short loc_1800073F8
0x1800073ee  mov     eax, 80005008h
0x1800073f3  jmp     loc_1800076BA
0x1800073f8  lea     rcx, [rsp+300h+pvarg]; pvarg
0x1800073fd  call    cs:__imp_VariantInit
0x180007403  mov     rdx, [rbp+200h+pvargSrc]; pvargSrc
0x180007407  lea     rcx, [rsp+300h+pvarg]; pvarDest
0x18000740c  call    cs:__imp_VariantCopyInd
0x180007412  mov     [rsp+300h+var_2D0], eax
0x180007416  mov     edi, eax
0x180007418  test    eax, eax
0x18000741a  js      loc_180007660
0x180007420  movzx   ecx, word ptr [rsp+300h+pvarg]
0x180007425  mov     edx, 0FFFh
0x18000742a  movzx   eax, cx
0x18000742d  and     ax, dx
0x180007430  cmp     ax, 0Ch
0x180007434  jnz     short loc_18000743D
0x180007436  bt      cx, 0Dh
0x18000743b  jb      short loc_180007452
0x18000743d  cmp     ax, 8
0x180007441  jnz     loc_1800074EC
0x180007447  bt      cx, 0Dh
0x18000744c  jnb     loc_1800074EC
0x180007452  movups  xmm0, xmmword ptr [rsp+300h+pvarg]
0x180007457  lea     r8, [rsp+300h+var_2CC]; unsigned int *
0x18000745c  movsd   xmm1, qword ptr [rsp+300h+pvarg+10h]
0x180007462  lea     rdx, [rsp+300h+var_2C0]; struct tagVARIANT **
0x180007467  lea     rcx, [rbp+200h+var_280]; struct tagVARIANT
0x18000746b  movaps  xmmword ptr [rbp+200h+var_280], xmm0
0x18000746f  movsd   qword ptr [rbp+200h+var_280+10h], xmm1
0x180007474  call    ?ConvertArrayToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertArrayToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x180007479  mov     r13, [rsp+300h+var_2C0]
0x18000747e  mov     edi, eax
0x180007480  mov     [rsp+300h+var_2D0], eax
0x180007484  test    eax, eax
0x180007486  js      short loc_1800074E2
0x180007488  lea     rcx, [rsp+300h+pvarg]; pvarg
0x18000748d  call    cs:__imp_VariantClear
0x180007493  mov     rax, [r15+48h]
0x180007497  lea     r9, [rsp+300h+var_2B0]; struct _iistype **
0x18000749c  mov     r12d, [rsp+300h+var_2CC]
0x1800074a1  mov     r14d, 1
0x1800074a7  mov     ebx, [rsp+300h+var_2C8]
0x1800074ab  mov     r8d, r12d; unsigned int
0x1800074ae  mov     [rsp+300h+var_2D8], rax; unsigned __int16 *
0x1800074b3  mov     rdx, r13; struct tagVARIANT *
0x1800074b6  mov     ecx, ebx; unsigned int
0x1800074b8  mov     dword ptr [rsp+300h+var_2E0], r14d; int
0x1800074bd  call    ?VarTypeToIISTypeCopyConstruct@@YAJKPEAUtagVARIANT@@KPEAPEAU_iistype@@HPEBG@Z; VarTypeToIISTypeCopyConstruct(ulong,tagVARIANT *,ulong,_iistype * *,int,ushort const *)
0x1800074c2  mov     [rsp+300h+var_2D0], eax
0x1800074c6  mov     edi, eax
0x1800074c8  test    eax, eax
0x1800074ca  js      short loc_1800074D8
0x1800074cc  mov     dword ptr [rsp+300h+var_2C0], r14d
0x1800074d1  mov     r14, [rsp+300h+var_2B0]
0x1800074d6  jmp     short loc_180007506
0x1800074d8  mov     r14, [rsp+300h+var_2B0]
0x1800074dd  jmp     loc_180007660
0x1800074e2  mov     r12d, [rsp+300h+var_2CC]
0x1800074e7  jmp     loc_180007660
0x1800074ec  mov     edi, 80004005h
0x1800074f1  mov     [rsp+300h+var_2D0], edi
0x1800074f5  jmp     loc_180007660
0x1800074fa  mov     ebx, [rsp+300h+var_2C8]
0x1800074fe  mov     dword ptr [rsp+300h+var_2C0], 2
0x180007506  cmp     ebx, 7
0x180007509  jnz     loc_1800075E0
0x18000750f  mov     rcx, [r15+90h]; this
0x180007516  lea     r8, [rbp+200h+psz]; unsigned __int16 *
0x18000751a  xor     eax, eax
0x18000751c  xorps   xmm0, xmm0
0x18000751f  mov     rdx, rsi; unsigned __int16 *
0x180007522  mov     qword ptr [rbp+200h+var_280+10h], rax
0x180007526  movups  xmmword ptr [rbp+200h+var_280], xmm0
0x18000752a  mov     [rsp+300h+var_2CC], eax
0x18000752e  call    ?LookupFlagPropName@IIsSchema@@QEAAJPEBGPEAGK@Z; IIsSchema::LookupFlagPropName(ushort const *,ushort *,ulong)
0x180007533  mov     [rsp+300h+var_2D0], eax
0x180007537  mov     edi, eax
0x180007539  test    eax, eax
0x18000753b  js      loc_180007660
0x180007541  cmp     dword ptr [rsp+300h+var_2C0], 2
0x180007546  jz      loc_1800075DC
0x18000754c  mov     rcx, [r15+90h]; this
0x180007553  lea     r8, [rsp+300h+var_2CC]; unsigned int *
0x180007558  mov     rdx, rsi; unsigned __int16 *
0x18000755b  call    ?LookupBitMask@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupBitMask(ushort const *,ulong *)
0x180007560  mov     [rsp+300h+var_2D0], eax
0x180007564  mov     edi, eax
0x180007566  test    eax, eax
0x180007568  js      loc_180007660
0x18000756e  lea     rcx, [rbp+200h+var_280]; pvarg
0x180007572  call    cs:__imp_VariantInit
0x180007578  mov     rax, [r15]
0x18000757b  lea     rcx, [rbp+200h+psz]; psz
0x18000757f  mov     rdi, [rax+78h]
0x180007583  call    cs:__imp_SysAllocString
0x180007589  lea     r8, [rbp+200h+var_280]
0x18000758d  mov     rcx, r15
0x180007590  mov     rbx, rax
0x180007593  mov     rdx, rax
0x180007596  mov     rax, rdi
0x180007599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000759e  mov     rcx, rbx; bstrString
0x1800075a1  mov     [rsp+300h+var_2D0], eax
0x1800075a5  mov     edi, eax
0x1800075a7  call    cs:__imp_SysFreeString
0x1800075ad  test    edi, edi
0x1800075af  js      loc_180007660
0x1800075b5  cmp     dword ptr [r14+8], 0
0x1800075ba  mov     ecx, dword ptr [rbp+200h+var_280+8]
0x1800075bd  jz      short loc_1800075C5
0x1800075bf  or      ecx, [rsp+300h+var_2CC]
0x1800075c3  jmp     short loc_1800075CD
0x1800075c5  mov     eax, [rsp+300h+var_2CC]
0x1800075c9  not     eax
0x1800075cb  and     ecx, eax
0x1800075cd  mov     ebx, [rsp+300h+var_2C8]
0x1800075d1  mov     [r14+8], ecx
0x1800075d5  mov     dword ptr [r14], 1
0x1800075dc  lea     rsi, [rbp+200h+psz]
0x1800075e0  cmp     ebx, 5
0x1800075e3  jnz     short loc_180007606
0x1800075e5  mov     rcx, [r15+90h]; this
0x1800075ec  lea     r8, [rbp+200h+psz]; unsigned __int16 *
0x1800075f0  mov     rdx, rsi; unsigned __int16 *
0x1800075f3  call    ?LookupFlagPropName@IIsSchema@@QEAAJPEBGPEAGK@Z; IIsSchema::LookupFlagPropName(ushort const *,ushort *,ulong)
0x1800075f8  mov     [rsp+300h+var_2D0], eax
0x1800075fc  mov     edi, eax
0x1800075fe  test    eax, eax
0x180007600  js      short loc_180007660
0x180007602  lea     rsi, [rbp+200h+psz]
0x180007606  mov     rcx, [r15+58h]; this
0x18000760a  lea     r8, [rsp+300h+var_2B8]; unsigned int *
0x18000760f  mov     rdx, rsi; unsigned __int16 *
0x180007612  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180007617  test    eax, eax
0x180007619  jns     short loc_180007631
0x18000761b  mov     rcx, [r15+58h]; this
0x18000761f  mov     rdx, rsi; unsigned __int16 *
0x180007622  call    ?addproperty@CPropertyCache@@QEAAJPEAGKKPEAU_iistype@@@Z; CPropertyCache::addproperty(ushort *,ulong,ulong,_iistype *)
0x180007627  mov     [rsp+300h+var_2D0], eax
0x18000762b  mov     edi, eax
0x18000762d  test    eax, eax
0x18000762f  js      short loc_180007660
0x180007631  mov     r8d, dword ptr [rsp+300h+var_2C0]; unsigned int
0x180007636  cmp     ebx, 7
0x180007639  mov     rcx, [r15+58h]; this
0x18000763d  mov     eax, 1
0x180007642  cmovz   ebx, eax
0x180007645  mov     [rsp+300h+var_2D8], r14; struct _iistype *
0x18000764a  mov     r9d, ebx; unsigned int
0x18000764d  mov     dword ptr [rsp+300h+var_2E0], r12d; unsigned int
0x180007652  mov     rdx, rsi; unsigned __int16 *
0x180007655  call    ?putproperty@CPropertyCache@@QEAAJPEAGKKKPEAU_iistype@@@Z; CPropertyCache::putproperty(ushort *,ulong,ulong,ulong,_iistype *)
0x18000765a  mov     edi, eax
0x18000765c  mov     [rsp+300h+var_2D0], eax
0x180007660  mov     rbx, [rsp+300h+bstrString]
0x180007665  test    rbx, rbx
0x180007668  jz      short loc_180007673
0x18000766a  mov     rcx, rbx; bstrString
0x18000766d  call    cs:__imp_SysFreeString
0x180007673  test    r14, r14
0x180007676  jz      short loc_180007683
0x180007678  mov     edx, r12d; unsigned int
0x18000767b  mov     rcx, r14; struct _iistype *
0x18000767e  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180007683  test    r13, r13
0x180007686  jz      short loc_1800076B8
0x180007688  xor     ebx, ebx
0x18000768a  test    r12d, r12d
0x18000768d  jz      short loc_1800076AF
0x18000768f  lea     rcx, [rbx+rbx*2]
0x180007693  lea     rcx, ds:0[rcx*8]
0x18000769b  add     rcx, r13; pvarg
0x18000769e  call    cs:__imp_VariantClear
0x1800076a4  inc     ebx
0x1800076a6  cmp     ebx, r12d
0x1800076a9  jb      short loc_18000768F
0x1800076ab  mov     edi, [rsp+300h+var_2D0]
0x1800076af  mov     rcx, r13; pMem
0x1800076b2  call    cs:__imp_FreeADsMem
0x1800076b8  mov     eax, edi
0x1800076ba  mov     rcx, [rbp+200h+var_40]
0x1800076c1  xor     rcx, rsp; StackCookie
0x1800076c4  call    __security_check_cookie
0x1800076c9  mov     rbx, [rsp+300h+arg_8]
0x1800076d1  add     rsp, 2D0h
0x1800076d8  pop     r15
0x1800076da  pop     r14
0x1800076dc  pop     r13
0x1800076de  pop     r12
0x1800076e0  pop     rdi
0x1800076e1  pop     rsi
0x1800076e2  pop     rbp
0x1800076e3  retn
```

# CIISGenObject::Put(ushort *,tagVARIANT)

- ea: `0x180006f60`
- end: `0x1800072eb`
- name: `?Put@CIISGenObject@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `907`
- prototype: `__int64 __fastcall(CIISGenObject *this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180006f60`
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

- `OLEAUT32!__imp_SysAllocString` at `0x180007185`
- `OLEAUT32!__imp_SysAllocString` at `0x180007185`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000727f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000727f`
- `OLEAUT32!__imp_VariantInit` at `0x180006fe3`
- `OLEAUT32!__imp_VariantInit` at `0x180007174`
- `OLEAUT32!__imp_VariantInit` at `0x180006fe3`
- `OLEAUT32!__imp_VariantInit` at `0x180007174`
- `OLEAUT32!__imp_VariantClear` at `0x18000729b`
- `OLEAUT32!__imp_VariantClear` at `0x1800072b9`
- `OLEAUT32!__imp_VariantClear` at `0x18000729b`
- `OLEAUT32!__imp_VariantClear` at `0x1800072b9`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180007051`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180007051`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800072ae`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800072ae`

## pseudocode

```c
__int64 __fastcall CIISGenObject::Put(CIISGenObject *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  OLECHAR *v4; // rbx
  unsigned int v7; // esi
  struct tagVARIANT *v8; // r15
  unsigned int v9; // edi
  int v10; // eax
  VARIANTARG *p_pvarg; // rdx
  unsigned int v12; // r13d
  int v13; // eax
  unsigned int v14; // r9d
  struct _iistype *v15; // r12
  IIsSchema *v16; // rcx
  unsigned int v17; // r9d
  __int64 (__fastcall *v18)(CIISGenObject *, OLECHAR *, VARIANTARG *); // rdi
  OLECHAR *v19; // rbx
  unsigned int v20; // ecx
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  unsigned int v23; // ebx
  struct _iistype *v24; // [rsp+20h] [rbp-E0h]
  HRESULT CoreADsClass; // [rsp+30h] [rbp-D0h]
  unsigned int v26; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v27; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h] BYREF
  struct tagVARIANT *v30; // [rsp+50h] [rbp-B0h] BYREF
  struct _iistype *v31; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v33; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR psz[264]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = a2;
  if ( !a2 )
    return 2147500035LL;
  v27 = 0;
  v29 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v31 = 0;
  v7 = 0;
  v26 = 0;
  v8 = 0;
  v30 = 0;
  bstrString = 0;
  VariantInit(&pvarg);
  CoreADsClass = CCoreADsObject::get_CoreADsClass((CIISGenObject *)((char *)this - 64), &bstrString);
  v9 = CoreADsClass;
  if ( CoreADsClass >= 0 )
  {
    CoreADsClass = IIsSchema::ValidateProperty(*((IIsSchema **)this + 18), bstrString, v4);
    v9 = CoreADsClass;
    if ( CoreADsClass >= 0 )
    {
      CoreADsClass = IIsSchema::LookupSyntaxID(*((IIsSchema **)this + 18), v4, &v27);
      v9 = CoreADsClass;
      if ( CoreADsClass >= 0 )
      {
        CoreADsClass = VariantCopyInd(&pvarg, a3);
        v9 = CoreADsClass;
        if ( CoreADsClass >= 0 )
        {
          if ( ((pvarg.vt & 0xFFF) != 0xC || (pvarg.vt & 0x2000) == 0)
            && ((pvarg.vt & 0xFFF) != 8 || (pvarg.vt & 0x2000) == 0) )
          {
            v7 = 1;
            p_pvarg = &pvarg;
LABEL_14:
            v12 = v27;
            v13 = VarTypeToIISTypeCopyConstruct(v27, p_pvarg, v7, &v31, 0, *((const unsigned __int16 **)this + 9));
            v15 = v31;
            v9 = v13;
            CoreADsClass = v13;
            if ( v13 < 0 )
              goto LABEL_31;
            if ( v12 == 7 )
            {
              v16 = (IIsSchema *)*((_QWORD *)this + 18);
              memset(&v33, 0, sizeof(v33));
              v26 = 0;
              CoreADsClass = IIsSchema::LookupBitMask(v16, v4, &v26);
              v9 = CoreADsClass;
              if ( CoreADsClass < 0 )
                goto LABEL_31;
              CoreADsClass = IIsSchema::LookupFlagPropName(*((IIsSchema **)this + 18), v4, psz, v17);
              v9 = CoreADsClass;
              if ( CoreADsClass < 0 )
                goto LABEL_31;
              VariantInit(&v33);
              v18 = *(__int64 (__fastcall **)(CIISGenObject *, OLECHAR *, VARIANTARG *))(*(_QWORD *)this + 120LL);
              v19 = SysAllocString(psz);
              CoreADsClass = v18(this, v19, &v33);
              v9 = CoreADsClass;
              SysFreeString(v19);
              if ( CoreADsClass < 0 )
                goto LABEL_31;
              if ( *((_DWORD *)v15 + 2) )
                v20 = v26 | v33.lVal;
              else
                v20 = ~v26 & v33.lVal;
              *((_DWORD *)v15 + 2) = v20;
              v4 = psz;
              *(_DWORD *)v15 = 1;
            }
            if ( v12 != 5 )
            {
LABEL_26:
              if ( CPropertyCache::findproperty(*((CPropertyCache **)this + 11), v4, &v29) >= 0
                || (CoreADsClass = CPropertyCache::addproperty(*((CPropertyCache **)this + 11), v4, v21, v22, v24),
                    v9 = CoreADsClass,
                    CoreADsClass >= 0) )
              {
                if ( v12 == 7 )
                  v12 = 1;
                v9 = CPropertyCache::putproperty(*((CPropertyCache **)this + 11), v4, 1u, v12, v7, v15);
                CoreADsClass = v9;
              }
              goto LABEL_31;
            }
            CoreADsClass = IIsSchema::LookupFlagPropName(*((IIsSchema **)this + 18), v4, psz, v14);
            v9 = CoreADsClass;
            if ( CoreADsClass >= 0 )
            {
              v4 = psz;
              goto LABEL_26;
            }
LABEL_31:
            if ( v15 )
              IISTypeFreeIISObjects(v15, v7);
            goto LABEL_33;
          }
          v33 = pvarg;
          v10 = ConvertArrayToVariantArray(&v33, &v30, &v26);
          v8 = v30;
          v9 = v10;
          v7 = v26;
          CoreADsClass = v10;
          if ( v10 >= 0 )
          {
            p_pvarg = v30;
            goto LABEL_14;
          }
        }
      }
    }
  }
LABEL_33:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v8 )
  {
    v23 = 0;
    if ( v7 )
    {
      do
        VariantClear(&v8[v23++]);
      while ( v23 < v7 );
      v9 = CoreADsClass;
    }
    FreeADsMem(v8);
  }
  VariantClear(&pvarg);
  return v9;
}

```

## disassembly

```asm
0x180006f60  mov     [rsp-8+arg_18], rbx
0x180006f65  push    rbp
0x180006f66  push    rsi
0x180006f67  push    rdi
0x180006f68  push    r12
0x180006f6a  push    r13
0x180006f6c  push    r14
0x180006f6e  push    r15
0x180006f70  lea     rbp, [rsp-1C0h]
0x180006f78  sub     rsp, 2C0h
0x180006f7f  mov     rax, cs:__security_cookie
0x180006f86  xor     rax, rsp
0x180006f89  mov     [rbp+1F0h+var_40], rax
0x180006f90  xor     r13d, r13d
0x180006f93  mov     r12, r8
0x180006f96  mov     rbx, rdx
0x180006f99  mov     r14, rcx
0x180006f9c  test    rdx, rdx
0x180006f9f  jnz     short loc_180006FAB
0x180006fa1  mov     eax, 80004003h
0x180006fa6  jmp     loc_1800072C1
0x180006fab  xorps   xmm0, xmm0
0x180006fae  mov     [rsp+2F0h+var_2B8], r13d
0x180006fb3  xor     eax, eax
0x180006fb5  mov     [rsp+2F0h+var_2A8], r13d
0x180006fba  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x180006fbf  mov     qword ptr [rsp+2F0h+pvarg+10h], rax
0x180006fc4  movups  xmmword ptr [rsp+2F0h+pvarg], xmm0
0x180006fc9  mov     [rsp+2F0h+var_298], r13
0x180006fce  mov     esi, r13d
0x180006fd1  mov     [rsp+2F0h+var_2BC], r13d
0x180006fd6  mov     r15, r13
0x180006fd9  mov     [rsp+2F0h+var_2A0], r13
0x180006fde  mov     [rsp+2F0h+bstrString], r13
0x180006fe3  call    cs:__imp_VariantInit
0x180006fe9  lea     rcx, [r14-40h]; this
0x180006fed  lea     rdx, [rsp+2F0h+bstrString]; unsigned __int16 **
0x180006ff2  call    ?get_CoreADsClass@CCoreADsObject@@QEAAJPEAPEAG@Z; CCoreADsObject::get_CoreADsClass(ushort * *)
0x180006ff7  mov     [rsp+2F0h+var_2C0], eax
0x180006ffb  mov     edi, eax
0x180006ffd  test    eax, eax
0x180006fff  js      loc_180007273
0x180007005  mov     rdx, [rsp+2F0h+bstrString]; unsigned __int16 *
0x18000700a  mov     r8, rbx; unsigned __int16 *
0x18000700d  mov     rcx, [r14+90h]; this
0x180007014  call    ?ValidateProperty@IIsSchema@@QEAAJPEBG0@Z; IIsSchema::ValidateProperty(ushort const *,ushort const *)
0x180007019  mov     [rsp+2F0h+var_2C0], eax
0x18000701d  mov     edi, eax
0x18000701f  test    eax, eax
0x180007021  js      loc_180007273
0x180007027  mov     rcx, [r14+90h]; this
0x18000702e  lea     r8, [rsp+2F0h+var_2B8]; unsigned int *
0x180007033  mov     rdx, rbx; unsigned __int16 *
0x180007036  call    ?LookupSyntaxID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupSyntaxID(ushort const *,ulong *)
0x18000703b  mov     [rsp+2F0h+var_2C0], eax
0x18000703f  mov     edi, eax
0x180007041  test    eax, eax
0x180007043  js      loc_180007273
0x180007049  mov     rdx, r12; pvargSrc
0x18000704c  lea     rcx, [rsp+2F0h+pvarg]; pvarDest
0x180007051  call    cs:__imp_VariantCopyInd
0x180007057  mov     [rsp+2F0h+var_2C0], eax
0x18000705b  mov     edi, eax
0x18000705d  test    eax, eax
0x18000705f  js      loc_180007273
0x180007065  movzx   ecx, word ptr [rsp+2F0h+pvarg]
0x18000706a  mov     edx, 0FFFh
0x18000706f  movzx   eax, cx
0x180007072  and     ax, dx
0x180007075  cmp     ax, 0Ch
0x180007079  jnz     short loc_180007082
0x18000707b  bt      cx, 0Dh
0x180007080  jb      short loc_18000708F
0x180007082  cmp     ax, 8
0x180007086  jnz     short loc_1800070D2
0x180007088  bt      cx, 0Dh
0x18000708d  jnb     short loc_1800070D2
0x18000708f  movups  xmm0, xmmword ptr [rsp+2F0h+pvarg]
0x180007094  lea     r8, [rsp+2F0h+var_2BC]; unsigned int *
0x180007099  movsd   xmm1, qword ptr [rsp+2F0h+pvarg+10h]
0x18000709f  lea     rdx, [rsp+2F0h+var_2A0]; struct tagVARIANT **
0x1800070a4  lea     rcx, [rbp+1F0h+var_270]; struct tagVARIANT
0x1800070a8  movaps  xmmword ptr [rbp+1F0h+var_270], xmm0
0x1800070ac  movsd   qword ptr [rbp+1F0h+var_270+10h], xmm1
0x1800070b1  call    ?ConvertArrayToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z; ConvertArrayToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)
0x1800070b6  mov     r15, [rsp+2F0h+var_2A0]
0x1800070bb  mov     edi, eax
0x1800070bd  mov     esi, [rsp+2F0h+var_2BC]
0x1800070c1  mov     [rsp+2F0h+var_2C0], eax
0x1800070c5  test    eax, eax
0x1800070c7  js      loc_180007273
0x1800070cd  mov     rdx, r15
0x1800070d0  jmp     short loc_1800070DC
0x1800070d2  mov     esi, 1
0x1800070d7  lea     rdx, [rsp+2F0h+pvarg]; struct tagVARIANT *
0x1800070dc  mov     rax, [r14+48h]
0x1800070e0  lea     r9, [rsp+2F0h+var_298]; struct _iistype **
0x1800070e5  mov     [rsp+2F0h+var_2C8], rax; unsigned __int16 *
0x1800070ea  mov     r8d, esi; unsigned int
0x1800070ed  mov     dword ptr [rsp+2F0h+var_2D0], r13d; struct _iistype *
0x1800070f2  mov     r13d, [rsp+2F0h+var_2B8]
0x1800070f7  mov     ecx, r13d; unsigned int
0x1800070fa  call    ?VarTypeToIISTypeCopyConstruct@@YAJKPEAUtagVARIANT@@KPEAPEAU_iistype@@HPEBG@Z; VarTypeToIISTypeCopyConstruct(ulong,tagVARIANT *,ulong,_iistype * *,int,ushort const *)
0x1800070ff  mov     r12, [rsp+2F0h+var_298]
0x180007104  mov     edi, eax
0x180007106  mov     [rsp+2F0h+var_2C0], eax
0x18000710a  test    eax, eax
0x18000710c  js      loc_180007261
0x180007112  cmp     r13d, 7
0x180007116  jnz     loc_1800071E1
0x18000711c  mov     rcx, [r14+90h]; this
0x180007123  lea     r8, [rsp+2F0h+var_2BC]; unsigned int *
0x180007128  xor     eax, eax
0x18000712a  xorps   xmm0, xmm0
0x18000712d  mov     rdx, rbx; unsigned __int16 *
0x180007130  mov     qword ptr [rbp+1F0h+var_270+10h], rax
0x180007134  movups  xmmword ptr [rbp+1F0h+var_270], xmm0
0x180007138  mov     [rsp+2F0h+var_2BC], eax
0x18000713c  call    ?LookupBitMask@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupBitMask(ushort const *,ulong *)
0x180007141  mov     [rsp+2F0h+var_2C0], eax
0x180007145  mov     edi, eax
0x180007147  test    eax, eax
0x180007149  js      loc_180007261
0x18000714f  mov     rcx, [r14+90h]; this
0x180007156  lea     r8, [rbp+1F0h+psz]; unsigned __int16 *
0x18000715a  mov     rdx, rbx; unsigned __int16 *
0x18000715d  call    ?LookupFlagPropName@IIsSchema@@QEAAJPEBGPEAGK@Z; IIsSchema::LookupFlagPropName(ushort const *,ushort *,ulong)
0x180007162  mov     [rsp+2F0h+var_2C0], eax
0x180007166  mov     edi, eax
0x180007168  test    eax, eax
0x18000716a  js      loc_180007261
0x180007170  lea     rcx, [rbp+1F0h+var_270]; pvarg
0x180007174  call    cs:__imp_VariantInit
0x18000717a  mov     rax, [r14]
0x18000717d  lea     rcx, [rbp+1F0h+psz]; psz
0x180007181  mov     rdi, [rax+78h]
0x180007185  call    cs:__imp_SysAllocString
0x18000718b  lea     r8, [rbp+1F0h+var_270]
0x18000718f  mov     rcx, r14
0x180007192  mov     rbx, rax
0x180007195  mov     rdx, rax
0x180007198  mov     rax, rdi
0x18000719b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a0  mov     rcx, rbx; bstrString
0x1800071a3  mov     [rsp+2F0h+var_2C0], eax
0x1800071a7  mov     edi, eax
0x1800071a9  call    cs:__imp_SysFreeString
0x1800071af  test    edi, edi
0x1800071b1  js      loc_180007261
0x1800071b7  cmp     dword ptr [r12+8], 0
0x1800071bd  mov     ecx, dword ptr [rbp+1F0h+var_270+8]
0x1800071c0  jz      short loc_1800071C8
0x1800071c2  or      ecx, [rsp+2F0h+var_2BC]
0x1800071c6  jmp     short loc_1800071D0
0x1800071c8  mov     eax, [rsp+2F0h+var_2BC]
0x1800071cc  not     eax
0x1800071ce  and     ecx, eax
0x1800071d0  mov     [r12+8], ecx
0x1800071d5  lea     rbx, [rbp+1F0h+psz]
0x1800071d9  mov     dword ptr [r12], 1
0x1800071e1  cmp     r13d, 5
0x1800071e5  jnz     short loc_180007208
0x1800071e7  mov     rcx, [r14+90h]; this
0x1800071ee  lea     r8, [rbp+1F0h+psz]; unsigned __int16 *
0x1800071f2  mov     rdx, rbx; unsigned __int16 *
0x1800071f5  call    ?LookupFlagPropName@IIsSchema@@QEAAJPEBGPEAGK@Z; IIsSchema::LookupFlagPropName(ushort const *,ushort *,ulong)
0x1800071fa  mov     [rsp+2F0h+var_2C0], eax
0x1800071fe  mov     edi, eax
0x180007200  test    eax, eax
0x180007202  js      short loc_180007261
0x180007204  lea     rbx, [rbp+1F0h+psz]
0x180007208  mov     rcx, [r14+58h]; this
0x18000720c  lea     r8, [rsp+2F0h+var_2A8]; unsigned int *
0x180007211  mov     rdx, rbx; unsigned __int16 *
0x180007214  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180007219  test    eax, eax
0x18000721b  jns     short loc_180007233
0x18000721d  mov     rcx, [r14+58h]; this
0x180007221  mov     rdx, rbx; unsigned __int16 *
0x180007224  call    ?addproperty@CPropertyCache@@QEAAJPEAGKKPEAU_iistype@@@Z; CPropertyCache::addproperty(ushort *,ulong,ulong,_iistype *)
0x180007229  mov     [rsp+2F0h+var_2C0], eax
0x18000722d  mov     edi, eax
0x18000722f  test    eax, eax
0x180007231  js      short loc_180007261
0x180007233  mov     rcx, [r14+58h]; this
0x180007237  mov     eax, 1
0x18000723c  cmp     r13d, 7
0x180007240  mov     [rsp+2F0h+var_2C8], r12; struct _iistype *
0x180007245  mov     r8d, eax; unsigned int
0x180007248  mov     dword ptr [rsp+2F0h+var_2D0], esi; unsigned int
0x18000724c  cmovz   r13d, eax
0x180007250  mov     rdx, rbx; unsigned __int16 *
0x180007253  mov     r9d, r13d; unsigned int
0x180007256  call    ?putproperty@CPropertyCache@@QEAAJPEAGKKKPEAU_iistype@@@Z; CPropertyCache::putproperty(ushort *,ulong,ulong,ulong,_iistype *)
0x18000725b  mov     edi, eax
0x18000725d  mov     [rsp+2F0h+var_2C0], eax
0x180007261  xor     r13d, r13d
0x180007264  test    r12, r12
0x180007267  jz      short loc_180007273
0x180007269  mov     edx, esi; unsigned int
0x18000726b  mov     rcx, r12; struct _iistype *
0x18000726e  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180007273  cmp     [rsp+2F0h+bstrString], r13
0x180007278  jz      short loc_180007285
0x18000727a  mov     rcx, [rsp+2F0h+bstrString]; bstrString
0x18000727f  call    cs:__imp_SysFreeString
0x180007285  test    r15, r15
0x180007288  jz      short loc_1800072B4
0x18000728a  mov     ebx, r13d
0x18000728d  test    esi, esi
0x18000728f  jz      short loc_1800072AB
0x180007291  mov     eax, ebx
0x180007293  lea     rdx, [rax+rax*2]
0x180007297  lea     rcx, [r15+rdx*8]; pvarg
0x18000729b  call    cs:__imp_VariantClear
0x1800072a1  inc     ebx
0x1800072a3  cmp     ebx, esi
0x1800072a5  jb      short loc_180007291
0x1800072a7  mov     edi, [rsp+2F0h+var_2C0]
0x1800072ab  mov     rcx, r15; pMem
0x1800072ae  call    cs:__imp_FreeADsMem
0x1800072b4  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x1800072b9  call    cs:__imp_VariantClear
0x1800072bf  mov     eax, edi
0x1800072c1  mov     rcx, [rbp+1F0h+var_40]
0x1800072c8  xor     rcx, rsp; StackCookie
0x1800072cb  call    __security_check_cookie
0x1800072d0  mov     rbx, [rsp+2F0h+arg_18]
0x1800072d8  add     rsp, 2C0h
0x1800072df  pop     r15
0x1800072e1  pop     r14
0x1800072e3  pop     r13
0x1800072e5  pop     r12
0x1800072e7  pop     rdi
0x1800072e8  pop     rsi
0x1800072e9  pop     rbp
0x1800072ea  retn
```

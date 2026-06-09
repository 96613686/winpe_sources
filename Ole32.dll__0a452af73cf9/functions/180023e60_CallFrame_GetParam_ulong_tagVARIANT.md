# CallFrame::GetParam(ulong,tagVARIANT *)

- ea: `0x180023e60`
- end: `0x18002414d`
- name: `?GetParam@CallFrame@@UEAAJKPEAUtagVARIANT@@@Z`
- size: `749`
- prototype: `HRESULT __fastcall(CallFrame *this, unsigned int iParam, tagVARIANT *pvar)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023e60`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180023e88`
- `OLEAUT32!__imp_VariantInit` at `0x180023ec7`
- `OLEAUT32!__imp_VariantInit` at `0x1800240c0`
- `OLEAUT32!__imp_VariantInit` at `0x180023e88`
- `OLEAUT32!__imp_VariantInit` at `0x180023ec7`
- `OLEAUT32!__imp_VariantInit` at `0x1800240c0`
- `OLEAUT32!__imp_VariantCopy` at `0x180023f6e`
- `OLEAUT32!__imp_VariantCopy` at `0x180023f6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800240a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800240a5`

## pseudocode

```c
HRESULT __fastcall CallFrame::GetParam(CallFrame *this, unsigned int iParam, tagVARIANT *pvar)
{
  __int64 v3; // rbx
  PARAM_DESCRIPTION *m_params; // r12
  __int64 v7; // rax
  __int64 StackOffset; // r12
  __int64 v9; // r15
  MD_METHOD *m_pmd; // r8
  METHOD_DESCRIPTOR *m_rgMethodDescs; // rcx
  __int64 v12; // rdi
  unsigned __int16 vt; // ax
  unsigned int m_cbPushedByCaller; // ecx
  size_t v15; // r8
  bool v17; // zf
  int v18; // ecx
  int v19; // ecx
  bool v20; // zf
  int v21; // ecx
  bool v22; // zf
  int v23; // ecx
  VARIANTARG *v24; // rax
  __int64 v25; // rbx
  tagVARIANT varTemp; // [rsp+20h] [rbp-28h] BYREF
  PARAM_DESCRIPTION *v27; // [rsp+A0h] [rbp+58h]

  v3 = iParam;
  if ( !pvar )
    return -2147467261;
  VariantInit(pvar);
  m_params = this->m_pmd->m_params;
  v27 = m_params;
  v7 = ((__int64 (__fastcall *)(CallFrame *))this->ICallFrame::IUnknown::lpVtbl[2].QueryInterface)(this);
  StackOffset = m_params[v3].StackOffset;
  v9 = v7;
  memset(&varTemp, 0, sizeof(varTemp));
  VariantInit(&varTemp);
  m_pmd = this->m_pmd;
  m_rgMethodDescs = this->m_pInterceptor->m_ndrTypeInfo.m_ptr->m_rgMethodDescs;
  if ( (unsigned int)v3 >= m_rgMethodDescs[m_pmd->m_info.iMethod].m_cParams )
    return -2147352562;
  v12 = v9 + StackOffset;
  varTemp.vt = m_rgMethodDescs[m_pmd->m_info.iMethod].m_paramVTs[v3];
  vt = varTemp.vt & 0xF000;
  if ( (varTemp.vt & 0x2000) == 0 )
    vt = varTemp.vt;
  if ( vt > 0x24u )
  {
    if ( vt <= 0x400Bu )
    {
      if ( vt == 16395 )
        goto LABEL_7;
      if ( vt <= 0x4005u )
      {
        if ( vt == 16389 || vt == 0x2000 || vt == 0x4000 )
          goto LABEL_7;
        v21 = vt - 16386;
        v20 = vt == 16386;
        goto LABEL_22;
      }
      v18 = vt - 16390;
      v17 = vt == 16390;
LABEL_19:
      if ( v17 )
        goto LABEL_7;
      v19 = v18 - 1;
      if ( !v19 )
        goto LABEL_7;
      v21 = v19 - 1;
      v20 = v21 == 0;
LABEL_22:
      if ( !v20 )
      {
        v23 = v21 - 1;
        v22 = v23 == 0;
        goto LABEL_24;
      }
LABEL_7:
      if ( (_DWORD)v3 == m_pmd->m_numberOfParams )
        m_cbPushedByCaller = m_pmd->m_cbPushedByCaller;
      else
        m_cbPushedByCaller = m_pmd->m_params[(unsigned int)(v3 + 1)].StackOffset;
      v15 = m_cbPushedByCaller - v27[v3].StackOffset;
      if ( v15 <= 0x10 )
      {
        memcpy_0(&varTemp.boolVal, (const void *)(v9 + StackOffset), v15);
        return VariantCopy(pvar, &varTemp);
      }
      return -2147352568;
    }
    if ( vt > 0x4012u )
    {
      if ( vt == 16403 || vt == 16406 || vt == 16407 || vt == 16420 || vt == 24576 )
        goto LABEL_7;
      return -2147352568;
    }
    if ( vt == 16402 || vt == 16396 || vt == 16397 || vt == 16398 )
      goto LABEL_7;
    v23 = vt - 16400;
    v22 = vt == 16400;
LABEL_24:
    if ( v22 || v23 == 1 )
      goto LABEL_7;
    return -2147352568;
  }
  if ( vt == 36 )
    goto LABEL_7;
  if ( vt <= 0xBu )
  {
    if ( vt == 11 || vt == 2 || vt == 3 || vt == 4 || vt == 5 )
      goto LABEL_7;
    v18 = vt - 6;
    v17 = vt == 6;
    goto LABEL_19;
  }
  if ( vt != 12 )
  {
    switch ( vt )
    {
      case 0xDu:
        goto LABEL_7;
      case 0xEu:
        varTemp.vt = *(_WORD *)v12;
        *(_DWORD *)&varTemp.decVal.scale = *(_DWORD *)(v12 + 2);
        varTemp.wReserved3 = *(_WORD *)(v12 + 6);
        varTemp.llVal = *(_QWORD *)(v12 + 8);
        return VariantCopy(pvar, &varTemp);
      case 0x10u:
      case 0x11u:
      case 0x12u:
      case 0x13u:
        goto LABEL_7;
    }
    v23 = vt - 22;
    v22 = vt == 22;
    goto LABEL_24;
  }
  v24 = (VARIANTARG *)CoTaskMemAlloc(0x18u);
  v25 = (__int64)v24;
  if ( v24 )
  {
    VariantInit(v24);
    *(_WORD *)v25 = *(_WORD *)v12;
    *(_OWORD *)(v25 + 8) = *(_OWORD *)(v12 + 8);
    varTemp.vt |= 0x4000u;
    varTemp.llVal = v25;
    return VariantCopy(pvar, &varTemp);
  }
  return -2147024882;
}

```

## disassembly

```asm
0x180023e60  push    rbp
0x180023e62  push    rbx
0x180023e63  push    rsi
0x180023e64  push    rdi
0x180023e65  push    r12
0x180023e67  push    r13
0x180023e69  push    r14
0x180023e6b  push    r15
0x180023e6d  mov     rbp, rsp
0x180023e70  sub     rsp, 48h
0x180023e74  mov     ebx, iParam
0x180023e76  mov     rsi, pvar
0x180023e79  mov     rdi, this
0x180023e7c  test    pvar, pvar
0x180023e7f  jz      loc_18002402B
0x180023e85  mov     this, pvar; pvarg
0x180023e88  call    cs:__imp_VariantInit
0x180023e8e  mov     rax, [rdi+10h]
0x180023e92  lea     r13, [rbx+rbx*2]
0x180023e96  mov     this, rdi
0x180023e99  mov     r12, [rax+8]
0x180023e9d  mov     rax, [rdi]
0x180023ea0  mov     [rbp+arg_10], r12
0x180023ea4  mov     rax, [rax+30h]
0x180023ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ead  movzx   r12d, word ptr [r12+r13*2+2]
0x180023eb3  lea     this, [rbp+varTemp]; pvarg
0x180023eb7  mov     r15, rax
0x180023eba  xorps   xmm0, xmm0
0x180023ebd  xor     eax, eax
0x180023ebf  mov     [rbp+varTemp.pRecInfo], rax
0x180023ec3  movups  xmmword ptr [rbp+varTemp.___u0], xmm0
0x180023ec7  call    cs:__imp_VariantInit
0x180023ecd  mov     pvar, [rdi+10h]
0x180023ed1  movsxd  this, dword ptr [pvar+2Ch]
0x180023ed5  lea     r9, [this+this*2]
0x180023ed9  mov     this, [rdi+40h]
0x180023edd  mov     rdx, [this+68h]
0x180023ee1  mov     this, [rdx+38h]
0x180023ee5  movsx   eax, word ptr [this+r9*8+8]
0x180023eeb  cmp     ebx, eax
0x180023eed  jnb     loc_180024035
0x180023ef3  mov     rax, [this+r9*8+10h]
0x180023ef8  lea     rdi, [r15+r12]
0x180023efc  mov     r9d, 0F000h
0x180023f02  mov     r10d, 2000h
0x180023f08  movzx   iParam, word ptr [rax+rbx*2]
0x180023f0c  movzx   eax, dx
0x180023f0f  mov     word ptr [rbp+varTemp.___u0], dx
0x180023f13  and     ax, r9w
0x180023f17  test    r10w, dx
0x180023f1b  cmovz   ax, dx
0x180023f1f  movzx   ecx, ax
0x180023f22  cmp     ecx, 24h ; '$'
0x180023f25  ja      loc_180023FD4
0x180023f2b  jnz     short loc_180023F85
0x180023f2d  cmp     ebx, [pvar]
0x180023f30  jz      loc_180024022
0x180023f36  lea     eax, [rbx+1]
0x180023f39  lea     rdx, [rax+rax*2]
0x180023f3d  mov     rax, [pvar+8]
0x180023f41  movzx   ecx, word ptr [rax+rdx*2+2]
0x180023f46  mov     rax, [rbp+arg_10]
0x180023f4a  movzx   eax, word ptr [rax+r13*2+2]
0x180023f50  sub     ecx, eax
0x180023f52  mov     r8d, ecx; Size
0x180023f55  cmp     pvar, 10h
0x180023f59  ja      short loc_180023FCD
0x180023f5b  mov     rdx, rdi; Src
0x180023f5e  lea     this, [rbp+varTemp.___u0+8]; void *
0x180023f62  call    memcpy_0
0x180023f67  lea     rdx, [rbp+varTemp]; pvargSrc
0x180023f6b  mov     this, rsi; pvargDest
0x180023f6e  call    cs:__imp_VariantCopy
0x180023f74  add     rsp, 48h
0x180023f78  pop     r15
0x180023f7a  pop     r14
0x180023f7c  pop     r13
0x180023f7e  pop     r12
0x180023f80  pop     rdi
0x180023f81  pop     rsi
0x180023f82  pop     rbx
0x180023f83  pop     rbp
0x180023f84  retn
0x180023f85  cmp     ecx, 0Bh
0x180023f88  ja      loc_18002403F
0x180023f8e  jz      short loc_180023F2D
0x180023f90  sub     ecx, 2
0x180023f93  jz      short loc_180023F2D
0x180023f95  sub     ecx, 1
0x180023f98  jz      short loc_180023F2D
0x180023f9a  sub     ecx, 1
0x180023f9d  jz      short loc_180023F2D
0x180023f9f  sub     ecx, 1
0x180023fa2  jz      short loc_180023F2D
0x180023fa4  sub     ecx, 1
0x180023fa7  jz      short loc_180023F2D
0x180023fa9  sub     ecx, 1
0x180023fac  jz      loc_180023F2D
0x180023fb2  sub     ecx, 1
0x180023fb5  jz      loc_180023F2D
0x180023fbb  sub     ecx, 1
0x180023fbe  jz      loc_180023F2D
0x180023fc4  cmp     ecx, 1
0x180023fc7  jz      loc_180023F2D
0x180023fcd  mov     eax, 80020008h
0x180023fd2  jmp     short loc_180023F74
0x180023fd4  mov     eax, 400Bh
0x180023fd9  cmp     ecx, eax
0x180023fdb  jbe     loc_1800240E7
0x180023fe1  mov     eax, 4012h
0x180023fe6  cmp     ecx, eax
0x180023fe8  jbe     loc_180024121
0x180023fee  sub     ecx, 4013h
0x180023ff4  jz      loc_180023F2D
0x180023ffa  sub     ecx, 3
0x180023ffd  jz      loc_180023F2D
0x180024003  sub     ecx, 1
0x180024006  jz      loc_180023F2D
0x18002400c  sub     ecx, 0Dh
0x18002400f  jz      loc_180023F2D
0x180024015  cmp     ecx, 1FDCh
0x18002401b  jnz     short loc_180023FCD
0x18002401d  jmp     loc_180023F2D
0x180024022  mov     ecx, [pvar+20h]
0x180024026  jmp     loc_180023F46
0x18002402b  mov     eax, 80004003h
0x180024030  jmp     loc_180023F74
0x180024035  mov     eax, 8002000Eh
0x18002403a  jmp     loc_180023F74
0x18002403f  sub     ecx, 0Ch
0x180024042  jz      short loc_1800240A0
0x180024044  sub     ecx, 1
0x180024047  jz      loc_180023F2D
0x18002404d  sub     ecx, 1
0x180024050  jz      short loc_18002407E
0x180024052  sub     ecx, 2
0x180024055  jz      loc_180023F2D
0x18002405b  sub     ecx, 1
0x18002405e  jz      loc_180023F2D
0x180024064  sub     ecx, 1
0x180024067  jz      loc_180023F2D
0x18002406d  sub     ecx, 1
0x180024070  jz      loc_180023F2D
0x180024076  sub     ecx, 3
0x180024079  jmp     loc_180023FBE
0x18002407e  movzx   eax, word ptr [rdi]
0x180024081  mov     word ptr [rbp+varTemp.___u0], ax
0x180024085  mov     eax, [rdi+2]
0x180024088  mov     dword ptr [rbp+varTemp.___u0+2], eax
0x18002408b  movzx   eax, word ptr [rdi+6]
0x18002408f  mov     word ptr [rbp+varTemp.___u0+6], ax
0x180024093  mov     rax, [rdi+8]
0x180024097  mov     qword ptr [rbp+varTemp.___u0+8], rax
0x18002409b  jmp     loc_180023F67
0x1800240a0  mov     ecx, 18h; cb
0x1800240a5  call    cs:__imp_CoTaskMemAlloc
0x1800240ab  mov     rbx, rax
0x1800240ae  test    rax, rax
0x1800240b1  jnz     short loc_1800240BD
0x1800240b3  mov     eax, 8007000Eh
0x1800240b8  jmp     loc_180023F74
0x1800240bd  mov     this, rbx; pvarg
0x1800240c0  call    cs:__imp_VariantInit
0x1800240c6  movzx   eax, word ptr [rdi]
0x1800240c9  mov     [rbx], ax
0x1800240cc  mov     eax, 4000h
0x1800240d1  movups  xmm0, xmmword ptr [rdi+8]
0x1800240d5  movdqu  xmmword ptr [rbx+8], xmm0
0x1800240da  or      word ptr [rbp+varTemp.___u0], ax
0x1800240de  mov     qword ptr [rbp+varTemp.___u0+8], rbx
0x1800240e2  jmp     loc_180023F67
0x1800240e7  jz      loc_180023F2D
0x1800240ed  mov     eax, 4005h
0x1800240f2  cmp     ecx, eax
0x1800240f4  ja      short loc_180024116
0x1800240f6  jz      loc_180023F2D
0x1800240fc  sub     ecx, r10d
0x1800240ff  jz      loc_180023F2D
0x180024105  sub     ecx, r10d
0x180024108  jz      loc_180023F2D
0x18002410e  sub     ecx, 2
0x180024111  jmp     loc_180023FB5
0x180024116  sub     ecx, 4006h
0x18002411c  jmp     loc_180023FA7
0x180024121  jz      loc_180023F2D
0x180024127  sub     ecx, 400Ch
0x18002412d  jz      loc_180023F2D
0x180024133  sub     ecx, 1
0x180024136  jz      loc_180023F2D
0x18002413c  sub     ecx, 1
0x18002413f  jz      loc_180023F2D
0x180024145  sub     ecx, 2
0x180024148  jmp     loc_180023FBE
```

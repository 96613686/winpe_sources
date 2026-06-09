# HyperVStorage::SetVariantValue(ushort const *,tagVARIANT const &)

- ea: `0x1401ca234`
- end: `0x1401ca59c`
- name: `?SetVariantValue@HyperVStorage@@QEAAJPEBGAEBUtagVARIANT@@@Z`
- size: `872`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401eaa10`

## callees

- `0x140036cac`
- `0x1400b9ba4`
- `0x140132940`
- `0x1401ca234`
- `0x1402c2010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1401ca278`
- `OLEAUT32!__imp_VariantInit` at `0x1401ca278`
- `OLEAUT32!__imp_VariantClear` at `0x1401ca571`
- `OLEAUT32!__imp_VariantClear` at `0x1401ca571`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca2ee`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca402`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca4d0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca505`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca2ee`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca402`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca4d0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca505`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ca37d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ca37d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ca348`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ca348`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ca313`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ca313`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ca560`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ca560`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1401ca443`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1401ca443`

## pseudocode

```c
__int64 __fastcall HyperVStorage::SetVariantValue(
        HyperVStorage *this,
        const unsigned __int16 *a2,
        const struct tagVARIANT *p_pvarg)
{
  SAFEARRAY *parray; // rsi
  unsigned int vt; // eax
  HRESULT v8; // eax
  HRESULT v9; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  __int64 v12; // r9
  __int64 v13; // r8
  HRESULT v14; // eax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v15; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdi
  HRESULT v17; // eax
  HRESULT v18; // eax
  void *ppvData; // [rsp+40h] [rbp-68h] BYREF
  LONG plLbound; // [rsp+48h] [rbp-60h] BYREF
  LONG plUbound; // [rsp+4Ch] [rbp-5Ch] BYREF
  BOOL v23; // [rsp+50h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-50h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  parray = 0;
  VariantInit(&pvarg);
  try
  {
    if ( !(*(unsigned int (**)(void))(*(_QWORD *)this + 288LL))() )
      HvsThrowHResultError(-2147467259);
    if ( !a2 )
      HvsThrowHResultError(-2147024809);
    ppvData = 0;
    v23 = 0;
    vt = p_pvarg->vt;
    if ( (vt & 0x2000) != 0 )
    {
      if ( (vt & 0xFFF) != 0x11 )
      {
        v8 = VariantChangeType(&pvarg, p_pvarg, 0, 0x2011u);
        if ( v8 < 0 )
          HvsThrowHResultError(v8);
        p_pvarg = &pvarg;
      }
      v9 = SafeArrayAccessData(p_pvarg->parray, &ppvData);
      if ( v9 < 0 )
        HvsThrowHResultError(v9);
      parray = p_pvarg->parray;
      plUbound = 0;
      plLbound = 0;
      LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
      if ( LBound < 0 )
        HvsThrowHResultError(LBound);
      if ( plLbound )
        HvsThrowHResultError(-2147024809);
      UBound = SafeArrayGetUBound(p_pvarg->parray, 1u, &plUbound);
      if ( UBound < 0 )
        HvsThrowHResultError(UBound);
      v12 = (unsigned int)(plUbound + 1);
      v13 = 7;
      goto LABEL_55;
    }
    if ( vt <= 0x10 )
    {
      if ( vt != 16 && vt != 2 && vt != 3 )
      {
        switch ( vt )
        {
          case 4u:
LABEL_29:
            v14 = VariantChangeType(&pvarg, p_pvarg, 0, 5u);
            if ( v14 < 0 )
              HvsThrowHResultError(v14);
            p_pvarg = &pvarg;
            goto LABEL_34;
          case 5u:
LABEL_34:
            p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&p_pvarg->llVal;
            if ( p_llVal->dblVal > 1.797693134862314e308 )
              HvsThrowHResultError(-2147352566);
            ppvData = p_llVal;
            v12 = 8;
            v13 = 5;
            goto LABEL_55;
          case 8u:
            ppvData = p_pvarg->bstrVal;
            v12 = SysStringByteLen((BSTR)ppvData);
            v13 = 6;
LABEL_55:
            HyperVStorage::SetValueInternal(this, a2, v13, v12, ppvData);
            goto LABEL_62;
        }
        if ( vt != 11 )
        {
          if ( vt == 14 )
            goto LABEL_29;
LABEL_44:
          HvsThrowHResultError(-2147352571);
        }
        v23 = p_pvarg->iVal != 0;
        v15 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v23;
        v12 = 4;
        v13 = 8;
LABEL_54:
        ppvData = v15;
        goto LABEL_55;
      }
      goto LABEL_45;
    }
    if ( vt != 17 && vt != 18 && vt != 19 )
    {
      switch ( vt )
      {
        case 0x14u:
LABEL_48:
          v13 = 3;
LABEL_53:
          v12 = 8;
          v15 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&p_pvarg->llVal;
          goto LABEL_54;
        case 0x15u:
LABEL_52:
          v13 = 4;
          goto LABEL_53;
        case 0x16u:
LABEL_45:
          v17 = VariantChangeType(&pvarg, p_pvarg, 0, 0x14u);
          if ( v17 < 0 )
            HvsThrowHResultError(v17);
          p_pvarg = &pvarg;
          goto LABEL_48;
      }
      if ( vt != 23 )
        goto LABEL_44;
    }
    v18 = VariantChangeType(&pvarg, p_pvarg, 0, 0x15u);
    if ( v18 < 0 )
      HvsThrowHResultError(v18);
    p_pvarg = &pvarg;
    goto LABEL_52;
  }
  catch ( ... )
  {
    HvsGetHResultForThrownException();
  }
LABEL_62:
  if ( parray )
    SafeArrayUnaccessData(parray);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1401ca234  push    rbx
0x1401ca236  push    rsi
0x1401ca237  push    rdi
0x1401ca238  push    r14
0x1401ca23a  push    r15
0x1401ca23c  sub     rsp, 80h
0x1401ca243  mov     rax, cs:__security_cookie
0x1401ca24a  xor     rax, rsp
0x1401ca24d  mov     [rsp+0A8h+var_38], rax
0x1401ca252  mov     rdi, r8
0x1401ca255  mov     r14, rdx
0x1401ca258  mov     r15, rcx
0x1401ca25b  xorps   xmm0, xmm0
0x1401ca25e  xor     eax, eax
0x1401ca260  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1401ca265  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1401ca26a  xor     ebx, ebx
0x1401ca26c  mov     esi, ebx
0x1401ca26e  mov     [rsp+0A8h+var_70], rbx
0x1401ca273  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1401ca278  call    cs:__imp_VariantInit
0x1401ca27f  nop     dword ptr [rax+rax+00h]
0x1401ca284  nop
0x1401ca285  mov     rax, [r15]
0x1401ca288  mov     rcx, r15
0x1401ca28b  mov     rax, [rax+120h]
0x1401ca292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca297  test    eax, eax
0x1401ca299  jnz     short loc_1401CA2A5
0x1401ca29b  mov     ecx, 80004005h; int
0x1401ca2a0  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca2a5  test    r14, r14
0x1401ca2a8  jnz     short loc_1401CA2B4
0x1401ca2aa  mov     ecx, 80070057h; int
0x1401ca2af  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca2b4  mov     [rsp+0A8h+ppvData], rbx
0x1401ca2b9  mov     [rsp+0A8h+var_58], ebx
0x1401ca2bd  movzx   eax, word ptr [rdi]
0x1401ca2c0  bt      ax, 0Dh
0x1401ca2c5  jnb     loc_1401CA3A7
0x1401ca2cb  mov     ecx, 0FFFh
0x1401ca2d0  and     ax, cx
0x1401ca2d3  mov     edx, 11h
0x1401ca2d8  cmp     ax, dx
0x1401ca2db  jz      short loc_1401CA30A
0x1401ca2dd  mov     r9d, 2011h; vt
0x1401ca2e3  xor     r8d, r8d; wFlags
0x1401ca2e6  mov     rdx, rdi; pvarSrc
0x1401ca2e9  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca2ee  call    cs:__imp_VariantChangeType
0x1401ca2f5  nop     dword ptr [rax+rax+00h]
0x1401ca2fa  test    eax, eax
0x1401ca2fc  jns     short loc_1401CA305
0x1401ca2fe  mov     ecx, eax; int
0x1401ca300  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca305  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca30a  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x1401ca30f  mov     rcx, [rdi+8]; psa
0x1401ca313  call    cs:__imp_SafeArrayAccessData
0x1401ca31a  nop     dword ptr [rax+rax+00h]
0x1401ca31f  test    eax, eax
0x1401ca321  jns     short loc_1401CA32A
0x1401ca323  mov     ecx, eax; int
0x1401ca325  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca32a  mov     rsi, [rdi+8]
0x1401ca32e  mov     [rsp+0A8h+var_70], rsi
0x1401ca333  mov     [rsp+0A8h+plUbound], ebx
0x1401ca337  mov     [rsp+0A8h+plLbound], ebx
0x1401ca33b  lea     r8, [rsp+0A8h+plLbound]; plLbound
0x1401ca340  mov     edx, 1; nDim
0x1401ca345  mov     rcx, rsi; psa
0x1401ca348  call    cs:__imp_SafeArrayGetLBound
0x1401ca34f  nop     dword ptr [rax+rax+00h]
0x1401ca354  test    eax, eax
0x1401ca356  jns     short loc_1401CA35F
0x1401ca358  mov     ecx, eax; int
0x1401ca35a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca35f  cmp     [rsp+0A8h+plLbound], ebx
0x1401ca363  jz      short loc_1401CA36F
0x1401ca365  mov     ecx, 80070057h; int
0x1401ca36a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca36f  lea     r8, [rsp+0A8h+plUbound]; plUbound
0x1401ca374  mov     edx, 1; nDim
0x1401ca379  mov     rcx, [rdi+8]; psa
0x1401ca37d  call    cs:__imp_SafeArrayGetUBound
0x1401ca384  nop     dword ptr [rax+rax+00h]
0x1401ca389  test    eax, eax
0x1401ca38b  jns     short loc_1401CA394
0x1401ca38d  mov     ecx, eax; int
0x1401ca38f  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca394  mov     r9d, [rsp+0A8h+plUbound]
0x1401ca399  inc     r9d
0x1401ca39c  mov     r8d, 7
0x1401ca3a2  jmp     loc_1401CA536
0x1401ca3a7  mov     ecx, eax
0x1401ca3a9  cmp     eax, 10h
0x1401ca3ac  ja      loc_1401CA492
0x1401ca3b2  jz      loc_1401CA4BF
0x1401ca3b8  sub     ecx, 2
0x1401ca3bb  jz      loc_1401CA4BF
0x1401ca3c1  sub     ecx, 1
0x1401ca3c4  jz      loc_1401CA4BF
0x1401ca3ca  sub     ecx, 1
0x1401ca3cd  jz      short loc_1401CA3F1
0x1401ca3cf  sub     ecx, 1
0x1401ca3d2  jz      loc_1401CA462
0x1401ca3d8  mov     r8d, 3
0x1401ca3de  sub     ecx, r8d
0x1401ca3e1  jz      short loc_1401CA43A
0x1401ca3e3  sub     ecx, r8d
0x1401ca3e6  jz      short loc_1401CA419
0x1401ca3e8  cmp     ecx, r8d
0x1401ca3eb  jnz     loc_1401CA4B5
0x1401ca3f1  mov     r9d, 5; vt
0x1401ca3f7  xor     r8d, r8d; wFlags
0x1401ca3fa  mov     rdx, rdi; pvarSrc
0x1401ca3fd  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca402  call    cs:__imp_VariantChangeType
0x1401ca409  nop     dword ptr [rax+rax+00h]
0x1401ca40e  test    eax, eax
0x1401ca410  jns     short loc_1401CA45D
0x1401ca412  mov     ecx, eax; int
0x1401ca414  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca419  mov     eax, ebx
0x1401ca41b  cmp     [rdi+8], bx
0x1401ca41f  setnz   al
0x1401ca422  mov     [rsp+0A8h+var_58], eax
0x1401ca426  lea     rax, [rsp+0A8h+var_58]
0x1401ca42b  mov     r9d, 4
0x1401ca431  lea     r8d, [r9+4]
0x1401ca435  jmp     loc_1401CA531
0x1401ca43a  mov     rcx, [rdi+8]; bstr
0x1401ca43e  mov     [rsp+0A8h+ppvData], rcx
0x1401ca443  call    cs:__imp_SysStringByteLen
0x1401ca44a  nop     dword ptr [rax+rax+00h]
0x1401ca44f  mov     r9d, eax
0x1401ca452  mov     r8d, 6
0x1401ca458  jmp     loc_1401CA536
0x1401ca45d  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca462  add     rdi, 8
0x1401ca466  movsd   xmm0, qword ptr [rdi]
0x1401ca46a  comisd  xmm0, cs:__real@7feffffffffffff6
0x1401ca472  jbe     short loc_1401CA47E
0x1401ca474  mov     ecx, 8002000Ah; int
0x1401ca479  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca47e  mov     [rsp+0A8h+ppvData], rdi
0x1401ca483  mov     r9d, 8
0x1401ca489  lea     r8d, [r9-3]
0x1401ca48d  jmp     loc_1401CA536
0x1401ca492  sub     ecx, 11h
0x1401ca495  jz      short loc_1401CA4F4
0x1401ca497  sub     ecx, 1
0x1401ca49a  jz      short loc_1401CA4F4
0x1401ca49c  sub     ecx, 1
0x1401ca49f  jz      short loc_1401CA4F4
0x1401ca4a1  sub     ecx, 1
0x1401ca4a4  jz      short loc_1401CA4EC
0x1401ca4a6  sub     ecx, 1
0x1401ca4a9  jz      short loc_1401CA521
0x1401ca4ab  sub     ecx, 1
0x1401ca4ae  jz      short loc_1401CA4BF
0x1401ca4b0  cmp     ecx, 1
0x1401ca4b3  jz      short loc_1401CA4F4
0x1401ca4b5  mov     ecx, 80020005h; int
0x1401ca4ba  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca4bf  mov     r9d, 14h; vt
0x1401ca4c5  xor     r8d, r8d; wFlags
0x1401ca4c8  mov     rdx, rdi; pvarSrc
0x1401ca4cb  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca4d0  call    cs:__imp_VariantChangeType
0x1401ca4d7  nop     dword ptr [rax+rax+00h]
0x1401ca4dc  test    eax, eax
0x1401ca4de  jns     short loc_1401CA4E7
0x1401ca4e0  mov     ecx, eax; int
0x1401ca4e2  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca4e7  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca4ec  mov     r8d, 3
0x1401ca4f2  jmp     short loc_1401CA527
0x1401ca4f4  mov     r9d, 15h; vt
0x1401ca4fa  xor     r8d, r8d; wFlags
0x1401ca4fd  mov     rdx, rdi; pvarSrc
0x1401ca500  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca505  call    cs:__imp_VariantChangeType
0x1401ca50c  nop     dword ptr [rax+rax+00h]
0x1401ca511  test    eax, eax
0x1401ca513  jns     short loc_1401CA51C
0x1401ca515  mov     ecx, eax; int
0x1401ca517  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca51c  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca521  mov     r8d, 4
0x1401ca527  mov     r9d, 8
0x1401ca52d  lea     rax, [rdi+8]
0x1401ca531  mov     [rsp+0A8h+ppvData], rax
0x1401ca536  mov     rax, [rsp+0A8h+ppvData]
0x1401ca53b  mov     [rsp+0A8h+var_88], rax
0x1401ca540  mov     rdx, r14
0x1401ca543  mov     rcx, r15
0x1401ca546  call    ?SetValueInternal@HyperVStorage@@IEAAXPEBGW4HyperVStorageKeyType@@IPEBE@Z; HyperVStorage::SetValueInternal(ushort const *,HyperVStorageKeyType,uint,uchar const *)
0x1401ca54b  mov     edi, ebx
0x1401ca54d  jmp     short loc_1401CA558
0x1401ca54f  mov     edi, [rsp+0A8h+var_78]
0x1401ca553  mov     rsi, [rsp+0A8h+var_70]
0x1401ca558  test    rsi, rsi
0x1401ca55b  jz      short loc_1401CA56C
0x1401ca55d  mov     rcx, rsi; psa
0x1401ca560  call    cs:__imp_SafeArrayUnaccessData
0x1401ca567  nop     dword ptr [rax+rax+00h]
0x1401ca56c  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1401ca571  call    cs:__imp_VariantClear
0x1401ca578  nop     dword ptr [rax+rax+00h]
0x1401ca57d  mov     eax, edi
0x1401ca57f  mov     rcx, [rsp+0A8h+var_38]
0x1401ca584  xor     rcx, rsp; StackCookie
0x1401ca587  call    __security_check_cookie
0x1401ca58c  add     rsp, 80h
0x1401ca593  pop     r15
0x1401ca595  pop     r14
0x1401ca597  pop     rdi
0x1401ca598  pop     rsi
0x1401ca599  pop     rbx
0x1401ca59a  retn
```

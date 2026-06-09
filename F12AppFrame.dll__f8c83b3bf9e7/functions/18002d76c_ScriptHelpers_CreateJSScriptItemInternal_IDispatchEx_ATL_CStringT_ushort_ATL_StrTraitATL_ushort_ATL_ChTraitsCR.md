# ScriptHelpers::CreateJSScriptItemInternal(IDispatchEx *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>> const &,ATL::CComVariant &)

- ea: `0x18002d76c`
- end: `0x18002dba7`
- name: `?CreateJSScriptItemInternal@ScriptHelpers@@YAJPEAUIDispatchEx@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@AEAVCComVariant@4@@Z`
- size: `1083`
- prototype: `__int64 __fastcall(__int64, const OLECHAR **, __int64 **, VARIANTARG *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002e270`

## callees

- `0x180003858`
- `0x18002d76c`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002d833`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d932`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d833`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d932`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d7f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d8d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d9e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da46`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da67`
- `OLEAUT32!__imp_SysFreeString` at `0x18002daaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002db31`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d7f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d8d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d9e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da46`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da67`
- `OLEAUT32!__imp_SysFreeString` at `0x18002daaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002db31`
- `OLEAUT32!__imp_VariantInit` at `0x18002d7af`
- `OLEAUT32!__imp_VariantInit` at `0x18002d7af`
- `OLEAUT32!__imp_VariantClear` at `0x18002d802`
- `OLEAUT32!__imp_VariantClear` at `0x18002d8de`
- `OLEAUT32!__imp_VariantClear` at `0x18002da72`
- `OLEAUT32!__imp_VariantClear` at `0x18002db10`
- `OLEAUT32!__imp_VariantClear` at `0x18002db3c`
- `OLEAUT32!__imp_VariantClear` at `0x18002d802`
- `OLEAUT32!__imp_VariantClear` at `0x18002d8de`
- `OLEAUT32!__imp_VariantClear` at `0x18002da72`
- `OLEAUT32!__imp_VariantClear` at `0x18002db10`
- `OLEAUT32!__imp_VariantClear` at `0x18002db3c`
- `OLEAUT32!__imp_VariantCopy` at `0x18002db02`
- `OLEAUT32!__imp_VariantCopy` at `0x18002db02`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ScriptHelpers::CreateJSScriptItemInternal(
        __int64 a1,
        const OLECHAR **a2,
        __int64 **a3,
        VARIANTARG *a4)
{
  OLECHAR *v8; // rdi
  int v9; // ebx
  volatile signed __int32 *v10; // rdx
  int v12; // r14d
  OLECHAR *v13; // rsi
  volatile signed __int32 *v14; // rdx
  __int64 *v15; // rbx
  const OLECHAR *v16; // rcx
  __int64 **v17; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  volatile signed __int32 *v20; // rdx
  void (*v21)(void); // rax
  HRESULT v22; // eax
  volatile signed __int32 *v23; // rdx
  unsigned int v24; // [rsp+50h] [rbp-89h] BYREF
  __int64 v25; // [rsp+58h] [rbp-81h] BYREF
  int v26; // [rsp+60h] [rbp-79h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-71h] BYREF
  OLECHAR *v28; // [rsp+80h] [rbp-59h]
  OLECHAR *v29; // [rsp+88h] [rbp-51h]
  _QWORD v30[2]; // [rsp+90h] [rbp-49h] BYREF
  int v31; // [rsp+A0h] [rbp-39h]
  int v32; // [rsp+A4h] [rbp-35h]
  VARIANTARG pvargSrc; // [rsp+A8h] [rbp-31h] BYREF
  __int128 v34; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-9h]
  __int128 v36; // [rsp+D8h] [rbp-1h] BYREF
  __int64 v37; // [rsp+E8h] [rbp+Fh]

  v34 = 0;
  v35 = 0;
  v26 = -3;
  VariantInit(&pvarg);
  v24 = 0;
  if ( *a2 )
  {
    v8 = SysAllocString(*a2);
    v28 = v8;
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v8 = 0;
    v28 = 0;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, unsigned int *))(*(_QWORD *)a1 + 56LL))(a1, v8, 0, &v24);
  if ( v9 )
  {
    if ( v9 >= 0 )
      v9 = -2147467259;
    SysFreeString(v8);
    VariantClear(&pvarg);
    v10 = (volatile signed __int32 *)(*a2 - 12);
    if ( _InterlockedExchangeAdd(v10 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
    return (unsigned int)v9;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a1 + 64LL))(
          a1,
          v24,
          1024,
          0x4000,
          &v34,
          &pvarg,
          0,
          0);
  v13 = 0;
  if ( v12 )
  {
    if ( v12 >= 0 )
      v12 = -2147467259;
LABEL_54:
    SysFreeString(v8);
    VariantClear(&pvarg);
    v23 = (volatile signed __int32 *)(*a2 - 12);
    if ( _InterlockedExchangeAdd(v23 + 4, 0xFFFFFFFF) > 1 )
      return (unsigned int)v12;
    v21 = *(void (**)(void))(**(_QWORD **)v23 + 8LL);
LABEL_56:
    v21();
    return (unsigned int)v12;
  }
  v25 = 0;
  if ( pvarg.llVal )
    (**(void (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
      pvarg.llVal,
      &GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9,
      &v25);
  if ( v25 )
  {
    v15 = (__int64 *)**a3;
    while ( 1 )
    {
      if ( v15 == *a3 )
      {
        pvargSrc.vt = 9;
        pvargSrc.llVal = pvarg.llVal;
        if ( pvarg.llVal )
          (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 8))(pvarg.llVal);
        if ( a4 != &pvargSrc )
        {
          v22 = VariantCopy(a4, &pvargSrc);
          if ( v22 < 0 )
          {
            a4->vt = 10;
            a4->lVal = v22;
            ATL::AtlThrowImpl(v22);
          }
        }
        VariantClear(&pvargSrc);
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        goto LABEL_54;
      }
      v16 = (const OLECHAR *)v15[4];
      if ( v16 )
      {
        v13 = SysAllocString(v16);
        v29 = v13;
        if ( !v13 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v29 = 0;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(
              v25,
              v13,
              2,
              &v24);
      if ( v12 )
        break;
      v36 = *(_OWORD *)(v15 + 5);
      v37 = v15[7];
      v30[0] = &v36;
      v30[1] = &v26;
      v31 = 1;
      v32 = 1;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
              v25,
              v24,
              1024,
              8,
              v30,
              0,
              0,
              0);
      if ( v12 )
      {
        if ( v12 >= 0 )
          v12 = -2147467259;
        SysFreeString(v13);
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        goto LABEL_41;
      }
      SysFreeString(v13);
      v17 = (__int64 **)v15[2];
      v13 = 0;
      if ( *((_BYTE *)v17 + 25) )
      {
        for ( i = (__int64 *)v15[1]; !*((_BYTE *)i + 25) && v15 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v15 = i;
        v15 = i;
      }
      else
      {
        v15 = (__int64 *)v15[2];
        for ( j = *v17; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v15 = j;
      }
    }
    if ( v12 >= 0 )
      v12 = -2147467259;
    SysFreeString(v13);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_41:
    SysFreeString(v8);
    VariantClear(&pvarg);
    v20 = (volatile signed __int32 *)(*a2 - 12);
    if ( _InterlockedExchangeAdd(v20 + 4, 0xFFFFFFFF) > 1 )
      return (unsigned int)v12;
    v21 = *(void (**)(void))(**(_QWORD **)v20 + 8LL);
    goto LABEL_56;
  }
  SysFreeString(v8);
  VariantClear(&pvarg);
  v14 = (volatile signed __int32 *)(*a2 - 12);
  if ( _InterlockedExchangeAdd(v14 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18002d76c  mov     [rsp-8+arg_8], rdx
0x18002d771  push    rbp
0x18002d772  push    rbx
0x18002d773  push    rsi
0x18002d774  push    rdi
0x18002d775  push    r12
0x18002d777  push    r13
0x18002d779  push    r14
0x18002d77b  push    r15
0x18002d77d  lea     rbp, [rsp-1Fh]
0x18002d782  sub     rsp, 0F8h
0x18002d789  mov     r12, r9
0x18002d78c  mov     r13, r8
0x18002d78f  mov     r15, rdx
0x18002d792  mov     rsi, rcx
0x18002d795  xorps   xmm0, xmm0
0x18002d798  movdqu  [rbp+57h+var_70], xmm0
0x18002d79d  xor     r14d, r14d
0x18002d7a0  mov     [rbp+57h+var_60], r14
0x18002d7a4  mov     [rbp+57h+var_D0], 0FFFFFFFDh
0x18002d7ab  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002d7af  call    cs:__imp_VariantInit
0x18002d7b5  nop
0x18002d7b6  mov     [rsp+130h+var_E0], r14d
0x18002d7bb  mov     rcx, [r15]; psz
0x18002d7be  test    rcx, rcx
0x18002d7c1  jnz     short loc_18002D833
0x18002d7c3  mov     edi, r14d
0x18002d7c6  mov     [rbp+57h+var_B0], r14
0x18002d7ca  mov     rax, [rsi]
0x18002d7cd  lea     r9, [rsp+130h+var_E0]
0x18002d7d2  xor     r8d, r8d
0x18002d7d5  mov     rdx, rdi
0x18002d7d8  mov     rcx, rsi
0x18002d7db  mov     rax, [rax+38h]
0x18002d7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7e4  mov     ebx, eax
0x18002d7e6  test    eax, eax
0x18002d7e8  jz      short loc_18002D84E
0x18002d7ea  mov     eax, 80004005h
0x18002d7ef  test    ebx, ebx
0x18002d7f1  cmovns  ebx, eax
0x18002d7f4  mov     rcx, rdi; bstrString
0x18002d7f7  call    cs:__imp_SysFreeString
0x18002d7fd  nop
0x18002d7fe  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002d802  call    cs:__imp_VariantClear
0x18002d808  nop
0x18002d809  mov     rdx, [r15]
0x18002d80c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002d810  or      ecx, 0FFFFFFFFh
0x18002d813  lock xadd [rdx+10h], ecx
0x18002d818  sub     ecx, 1
0x18002d81b  jg      short loc_18002D82C
0x18002d81d  mov     rcx, [rdx]
0x18002d820  mov     r8, [rcx]
0x18002d823  mov     rax, [r8+8]
0x18002d827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d82c  mov     eax, ebx
0x18002d82e  jmp     loc_18002DB69
0x18002d833  call    cs:__imp_SysAllocString
0x18002d839  mov     rdi, rax
0x18002d83c  mov     [rbp+57h+var_B0], rax
0x18002d840  test    rax, rax
0x18002d843  jz      loc_18002DB91
0x18002d849  jmp     loc_18002D7CA
0x18002d84e  mov     rax, [rsi]
0x18002d851  mov     r9d, 4000h
0x18002d857  mov     [rsp+130h+var_F8], r14
0x18002d85c  mov     [rsp+130h+var_100], r14
0x18002d861  lea     rcx, [rbp+57h+pvarg]
0x18002d865  mov     [rsp+130h+var_108], rcx
0x18002d86a  lea     rcx, [rbp+57h+var_70]
0x18002d86e  mov     [rsp+130h+var_110], rcx
0x18002d873  mov     r8d, 400h
0x18002d879  mov     edx, [rsp+130h+var_E0]
0x18002d87d  mov     rcx, rsi
0x18002d880  mov     rax, [rax+40h]
0x18002d884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d889  mov     r14d, eax
0x18002d88c  xor     esi, esi
0x18002d88e  test    eax, eax
0x18002d890  jz      short loc_18002D8A3
0x18002d892  mov     eax, 80004005h
0x18002d897  test    r14d, r14d
0x18002d89a  cmovns  r14d, eax
0x18002d89e  jmp     loc_18002DB2E
0x18002d8a3  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18002d8a7  mov     [rsp+130h+var_D8], rsi
0x18002d8ac  test    rcx, rcx
0x18002d8af  jz      short loc_18002D8C9
0x18002d8b1  mov     rax, [rcx]
0x18002d8b4  lea     r8, [rsp+130h+var_D8]
0x18002d8b9  lea     rdx, _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9
0x18002d8c0  mov     rax, [rax]
0x18002d8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8c8  nop
0x18002d8c9  cmp     [rsp+130h+var_D8], rsi
0x18002d8ce  jnz     short loc_18002D912
0x18002d8d0  mov     rcx, rdi; bstrString
0x18002d8d3  call    cs:__imp_SysFreeString
0x18002d8d9  nop
0x18002d8da  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002d8de  call    cs:__imp_VariantClear
0x18002d8e4  nop
0x18002d8e5  mov     rdx, [r15]
0x18002d8e8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002d8ec  or      eax, 0FFFFFFFFh
0x18002d8ef  lock xadd [rdx+10h], eax
0x18002d8f4  sub     eax, 1
0x18002d8f7  jg      short loc_18002D908
0x18002d8f9  mov     rcx, [rdx]
0x18002d8fc  mov     rax, [rcx]
0x18002d8ff  mov     rax, [rax+8]
0x18002d903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d908  mov     eax, 8000FFFFh
0x18002d90d  jmp     loc_18002DB69
0x18002d912  mov     rbx, [r13+0]
0x18002d916  mov     rbx, [rbx]
0x18002d919  cmp     rbx, [r13+0]
0x18002d91d  jz      loc_18002DACF
0x18002d923  mov     rcx, [rbx+20h]; psz
0x18002d927  test    rcx, rcx
0x18002d92a  jnz     short loc_18002D932
0x18002d92c  mov     [rbp+57h+var_A8], rsi
0x18002d930  jmp     short loc_18002D948
0x18002d932  call    cs:__imp_SysAllocString
0x18002d938  mov     rsi, rax
0x18002d93b  mov     [rbp+57h+var_A8], rax
0x18002d93f  test    rax, rax
0x18002d942  jz      loc_18002DB9C
0x18002d948  mov     rcx, [rsp+130h+var_D8]
0x18002d94d  mov     rax, [rcx]
0x18002d950  lea     r9, [rsp+130h+var_E0]
0x18002d955  mov     r8d, 2
0x18002d95b  mov     rdx, rsi
0x18002d95e  mov     rax, [rax+38h]
0x18002d962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d967  mov     r14d, eax
0x18002d96a  xor     edx, edx
0x18002d96c  test    eax, eax
0x18002d96e  jnz     loc_18002DAA0
0x18002d974  movups  xmm0, xmmword ptr [rbx+28h]
0x18002d978  movups  [rbp+57h+var_58], xmm0
0x18002d97c  movsd   xmm1, qword ptr [rbx+38h]
0x18002d981  movsd   [rbp+57h+var_48], xmm1
0x18002d986  lea     rax, [rbp+57h+var_58]
0x18002d98a  mov     [rbp+57h+var_A0], rax
0x18002d98e  lea     rax, [rbp+57h+var_D0]
0x18002d992  mov     [rbp+57h+var_98], rax
0x18002d996  lea     eax, [rdx+1]
0x18002d999  mov     [rbp+57h+var_90], eax
0x18002d99c  mov     [rbp+57h+var_8C], eax
0x18002d99f  mov     rcx, [rsp+130h+var_D8]
0x18002d9a4  mov     rax, [rcx]
0x18002d9a7  lea     r9d, [r14+8]
0x18002d9ab  mov     [rsp+130h+var_F8], rdx
0x18002d9b0  mov     [rsp+130h+var_100], rdx
0x18002d9b5  mov     [rsp+130h+var_108], rdx
0x18002d9ba  lea     rdx, [rbp+57h+var_A0]
0x18002d9be  mov     [rsp+130h+var_110], rdx
0x18002d9c3  mov     r8d, 400h
0x18002d9c9  mov     edx, [rsp+130h+var_E0]
0x18002d9cd  mov     rax, [rax+40h]
0x18002d9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9d6  mov     r14d, eax
0x18002d9d9  test    eax, eax
0x18002d9db  jnz     short loc_18002DA37
0x18002d9dd  mov     rcx, rsi; bstrString
0x18002d9e0  call    cs:__imp_SysFreeString
0x18002d9e6  mov     rcx, [rbx+10h]
0x18002d9ea  xor     esi, esi
0x18002d9ec  cmp     [rcx+19h], sil
0x18002d9f0  jz      short loc_18002DA13
0x18002d9f2  mov     rax, [rbx+8]
0x18002d9f6  jmp     short loc_18002DA05
0x18002d9f8  cmp     rbx, [rax+10h]
0x18002d9fc  jnz     short loc_18002DA0B
0x18002d9fe  mov     rbx, rax
0x18002da01  mov     rax, [rax+8]
0x18002da05  cmp     [rax+19h], sil
0x18002da09  jz      short loc_18002D9F8
0x18002da0b  mov     rbx, rax
0x18002da0e  jmp     loc_18002D919
0x18002da13  mov     rbx, rcx
0x18002da16  mov     rcx, [rcx]
0x18002da19  cmp     [rcx+19h], sil
0x18002da1d  jnz     loc_18002D919
0x18002da23  mov     rbx, rcx
0x18002da26  mov     rax, [rcx]
0x18002da29  mov     rcx, rax
0x18002da2c  cmp     [rax+19h], sil
0x18002da30  jz      short loc_18002DA23
0x18002da32  jmp     loc_18002D919
0x18002da37  mov     eax, 80004005h
0x18002da3c  test    r14d, r14d
0x18002da3f  cmovns  r14d, eax
0x18002da43  mov     rcx, rsi; bstrString
0x18002da46  call    cs:__imp_SysFreeString
0x18002da4c  nop
0x18002da4d  mov     rcx, [rsp+130h+var_D8]
0x18002da52  test    rcx, rcx
0x18002da55  jz      short loc_18002DA64
0x18002da57  mov     rax, [rcx]
0x18002da5a  mov     rax, [rax+10h]
0x18002da5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da63  nop
0x18002da64  mov     rcx, rdi; bstrString
0x18002da67  call    cs:__imp_SysFreeString
0x18002da6d  nop
0x18002da6e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002da72  call    cs:__imp_VariantClear
0x18002da78  nop
0x18002da79  mov     rdx, [r15]
0x18002da7c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002da80  or      ecx, 0FFFFFFFFh
0x18002da83  lock xadd [rdx+10h], ecx
0x18002da88  sub     ecx, 1
0x18002da8b  jg      loc_18002DB66
0x18002da91  mov     rcx, [rdx]
0x18002da94  mov     r8, [rcx]
0x18002da97  mov     rax, [r8+8]
0x18002da9b  jmp     loc_18002DB61
0x18002daa0  mov     eax, 80004005h
0x18002daa5  test    r14d, r14d
0x18002daa8  cmovns  r14d, eax
0x18002daac  mov     rcx, rsi; bstrString
0x18002daaf  call    cs:__imp_SysFreeString
0x18002dab5  nop
0x18002dab6  mov     rcx, [rsp+130h+var_D8]
0x18002dabb  test    rcx, rcx
0x18002dabe  jz      short loc_18002DACD
0x18002dac0  mov     rax, [rcx]
0x18002dac3  mov     rax, [rax+10h]
0x18002dac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dacc  nop
0x18002dacd  jmp     short loc_18002DA64
0x18002dacf  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18002dad3  mov     eax, 9
0x18002dad8  mov     word ptr [rbp+57h+pvargSrc], ax
0x18002dadc  mov     qword ptr [rbp+57h+pvargSrc+8], rcx
0x18002dae0  test    rcx, rcx
0x18002dae3  jz      short loc_18002DAF2
0x18002dae5  mov     rax, [rcx]
0x18002dae8  mov     rax, [rax+8]
0x18002daec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002daf1  nop
0x18002daf2  lea     rax, [rbp+57h+pvargSrc]
0x18002daf6  cmp     r12, rax
0x18002daf9  jz      short loc_18002DB0C
0x18002dafb  lea     rdx, [rbp+57h+pvargSrc]; pvargSrc
0x18002daff  mov     rcx, r12; pvargDest
0x18002db02  call    cs:__imp_VariantCopy
0x18002db08  test    eax, eax
0x18002db0a  js      short loc_18002DB7D
0x18002db0c  lea     rcx, [rbp+57h+pvargSrc]; pvarg
0x18002db10  call    cs:__imp_VariantClear
0x18002db16  nop
0x18002db17  mov     rcx, [rsp+130h+var_D8]
0x18002db1c  test    rcx, rcx
0x18002db1f  jz      short loc_18002DB2E
0x18002db21  mov     rax, [rcx]
0x18002db24  mov     rax, [rax+10h]
0x18002db28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db2d  nop
0x18002db2e  mov     rcx, rdi; bstrString
0x18002db31  call    cs:__imp_SysFreeString
0x18002db37  nop
0x18002db38  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002db3c  call    cs:__imp_VariantClear
0x18002db42  nop
0x18002db43  mov     rdx, [r15]
0x18002db46  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002db4a  or      eax, 0FFFFFFFFh
0x18002db4d  lock xadd [rdx+10h], eax
0x18002db52  sub     eax, 1
0x18002db55  jg      short loc_18002DB66
0x18002db57  mov     rcx, [rdx]
0x18002db5a  mov     rax, [rcx]
0x18002db5d  mov     rax, [rax+8]
0x18002db61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db66  mov     eax, r14d
0x18002db69  add     rsp, 0F8h
0x18002db70  pop     r15
0x18002db72  pop     r14
0x18002db74  pop     r13
0x18002db76  pop     r12
0x18002db78  pop     rdi
0x18002db79  pop     rsi
0x18002db7a  pop     rbx
0x18002db7b  pop     rbp
0x18002db7c  retn
0x18002db7d  mov     word ptr [r12], 0Ah
0x18002db84  mov     [r12+8], eax
0x18002db89  mov     ecx, eax; int
0x18002db8b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002db91  mov     ecx, 8007000Eh; int
0x18002db96  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002db9c  mov     ecx, 8007000Eh; int
0x18002dba1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```

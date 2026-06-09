# ScriptHelpers::CreateJSScriptItemInternal(IWebPlatform *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>> const &,ATL::CComVariant &)

- ea: `0x18002dbb0`
- end: `0x18002deb8`
- name: `?CreateJSScriptItemInternal@ScriptHelpers@@YAJPEAUIWebPlatform@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@AEAVCComVariant@4@@Z`
- size: `776`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, GUID *, __int64 *), const OLECHAR **, __int64 **, VARIANTARG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002e270`

## callees

- `0x180001c84`
- `0x180003858`
- `0x18002dbb0`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002dc6c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dcc5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dc6c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dcc5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dc26`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dd6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ddee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002de4d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dc26`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dd6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ddee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002de4d`
- `OLEAUT32!__imp_VariantInit` at `0x18002dbdd`
- `OLEAUT32!__imp_VariantInit` at `0x18002dbdd`
- `OLEAUT32!__imp_VariantClear` at `0x18002dc31`
- `OLEAUT32!__imp_VariantClear` at `0x18002ddce`
- `OLEAUT32!__imp_VariantClear` at `0x18002ddf9`
- `OLEAUT32!__imp_VariantClear` at `0x18002de58`
- `OLEAUT32!__imp_VariantClear` at `0x18002dc31`
- `OLEAUT32!__imp_VariantClear` at `0x18002ddce`
- `OLEAUT32!__imp_VariantClear` at `0x18002ddf9`
- `OLEAUT32!__imp_VariantClear` at `0x18002de58`
- `OLEAUT32!__imp_VariantCopy` at `0x18002ddbc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002ddbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ScriptHelpers::CreateJSScriptItemInternal(
        void (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        const OLECHAR **a2,
        __int64 **a3,
        VARIANTARG *a4)
{
  unsigned int v8; // esi
  OLECHAR *v9; // rdi
  __int64 v10; // rax
  volatile signed __int32 *v11; // rdx
  char *v13; // rdx
  unsigned int v14; // r12d
  __int64 *v15; // rbx
  __int64 v16; // rsi
  BSTR v17; // rax
  __int64 **v18; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v21; // ebx
  const OLECHAR **v22; // r12
  char *v23; // r12
  HRESULT v24; // eax
  volatile signed __int32 *v25; // rdx
  volatile signed __int32 *v26; // rdx
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
  char *v28; // [rsp+38h] [rbp-31h]
  OLECHAR *v29; // [rsp+40h] [rbp-29h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-21h] BYREF
  VARIANTARG pvargSrc; // [rsp+60h] [rbp-9h] BYREF

  VariantInit(&pvarg);
  v8 = 0;
  if ( *a2 )
  {
    v9 = SysAllocString(*a2);
    v29 = v9;
    if ( !v9 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v9 = 0;
    v29 = 0;
  }
  v10 = 0;
  v27 = 0;
  if ( a1 )
  {
    (**a1)(a1, &GUID_4c3a0a63_2098_4819_9be4_976f4a335d31, &v27);
    v10 = v27;
  }
  if ( v10 )
  {
    v13 = (char *)operator new[](saturated_mul((unsigned __int64)a3[1], 0x20u));
    v28 = v13;
    v14 = 0;
    v15 = (__int64 *)**a3;
    while ( v15 != *a3 )
    {
      v16 = 32LL * v14;
      v17 = SysAllocString((const OLECHAR *)v15[4]);
      v13 = v28;
      *(_QWORD *)&v28[v16] = v17;
      *(_OWORD *)&v13[v16 + 8] = *(_OWORD *)(v15 + 5);
      *(_QWORD *)&v13[v16 + 24] = v15[7];
      v18 = (__int64 **)v15[2];
      v8 = 0;
      if ( *((_BYTE *)v18 + 25) )
      {
        for ( i = (__int64 *)v15[1]; !*((_BYTE *)i + 25) && v15 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v15 = i;
        v15 = i;
      }
      else
      {
        v15 = (__int64 *)v15[2];
        for ( j = *v18; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v15 = j;
      }
      ++v14;
    }
    v21 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, char *, VARIANTARG *))(*(_QWORD *)v27 + 40LL))(
            v27,
            v9,
            *((unsigned int *)a3 + 2),
            v13,
            &pvarg);
    v22 = a2;
    if ( a3[1] )
    {
      v23 = v28;
      do
        SysFreeString(*(BSTR *)&v23[32 * v8++]);
      while ( v8 < (unsigned __int64)a3[1] );
      v22 = a2;
    }
    if ( v21 )
    {
      if ( v21 >= 0 )
        v21 = -2147467259;
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      SysFreeString(v9);
      VariantClear(&pvarg);
      v26 = (volatile signed __int32 *)(*v22 - 12);
      if ( _InterlockedDecrement(v26 + 4) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26);
      return (unsigned int)v21;
    }
    else
    {
      pvargSrc.vt = 9;
      pvargSrc.llVal = pvarg.llVal;
      if ( pvarg.llVal )
        (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 8))(pvarg.llVal);
      if ( a4 != &pvargSrc )
      {
        v24 = VariantCopy(a4, &pvargSrc);
        if ( v24 < 0 )
        {
          a4->vt = 10;
          a4->lVal = v24;
          ATL::AtlThrowImpl(v24);
        }
      }
      VariantClear(&pvargSrc);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      SysFreeString(v9);
      VariantClear(&pvarg);
      v25 = (volatile signed __int32 *)(*v22 - 12);
      if ( _InterlockedDecrement(v25 + 4) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25);
      return 0;
    }
  }
  else
  {
    SysFreeString(v9);
    VariantClear(&pvarg);
    v11 = (volatile signed __int32 *)(*a2 - 12);
    if ( _InterlockedDecrement(v11 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18002dbb0  mov     [rsp-8+arg_8], rdx
0x18002dbb5  push    rbp
0x18002dbb6  push    rbx
0x18002dbb7  push    rsi
0x18002dbb8  push    rdi
0x18002dbb9  push    r12
0x18002dbbb  push    r13
0x18002dbbd  push    r14
0x18002dbbf  push    r15
0x18002dbc1  lea     rbp, [rsp-1Fh]
0x18002dbc6  sub     rsp, 88h
0x18002dbcd  mov     r15, r9
0x18002dbd0  mov     r13, r8
0x18002dbd3  mov     r12, rdx
0x18002dbd6  mov     rbx, rcx
0x18002dbd9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002dbdd  call    cs:__imp_VariantInit
0x18002dbe3  nop
0x18002dbe4  mov     rcx, [r12]; psz
0x18002dbe8  xor     esi, esi
0x18002dbea  test    rcx, rcx
0x18002dbed  jnz     short loc_18002DC6C
0x18002dbef  mov     edi, esi
0x18002dbf1  mov     [rbp+57h+var_80], rsi
0x18002dbf5  mov     rax, rsi
0x18002dbf8  mov     [rbp+57h+var_90], rax
0x18002dbfc  test    rbx, rbx
0x18002dbff  jz      short loc_18002DC1E
0x18002dc01  mov     rax, [rbx]
0x18002dc04  lea     r8, [rbp+57h+var_90]
0x18002dc08  lea     rdx, _GUID_4c3a0a63_2098_4819_9be4_976f4a335d31
0x18002dc0f  mov     rcx, rbx
0x18002dc12  mov     rax, [rax]
0x18002dc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc1a  mov     rax, [rbp+57h+var_90]
0x18002dc1e  test    rax, rax
0x18002dc21  jnz     short loc_18002DC87
0x18002dc23  mov     rcx, rdi; bstrString
0x18002dc26  call    cs:__imp_SysFreeString
0x18002dc2c  nop
0x18002dc2d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002dc31  call    cs:__imp_VariantClear
0x18002dc37  nop
0x18002dc38  mov     rdx, [r12]
0x18002dc3c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002dc40  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002dc44  mov     eax, r14d
0x18002dc47  lock xadd [rdx+10h], eax
0x18002dc4c  add     eax, r14d
0x18002dc4f  test    eax, eax
0x18002dc51  jg      short loc_18002DC62
0x18002dc53  mov     rcx, [rdx]
0x18002dc56  mov     rax, [rcx]
0x18002dc59  mov     rax, [rax+8]
0x18002dc5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc62  mov     eax, 8000FFFFh
0x18002dc67  jmp     loc_18002DE87
0x18002dc6c  call    cs:__imp_SysAllocString
0x18002dc72  mov     rdi, rax
0x18002dc75  mov     [rbp+57h+var_80], rax
0x18002dc79  test    rax, rax
0x18002dc7c  jz      loc_18002DEAD
0x18002dc82  jmp     loc_18002DBF5
0x18002dc87  mov     eax, 20h ; ' '
0x18002dc8c  mul     qword ptr [r13+8]
0x18002dc90  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002dc97  cmovb   rax, r14
0x18002dc9b  mov     rcx, rax; unsigned __int64
0x18002dc9e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002dca3  mov     rdx, rax
0x18002dca6  mov     [rbp+57h+var_88], rax
0x18002dcaa  mov     r12d, esi
0x18002dcad  mov     rbx, [r13+0]
0x18002dcb1  mov     rbx, [rbx]
0x18002dcb4  cmp     rbx, [r13+0]
0x18002dcb8  jz      short loc_18002DD31
0x18002dcba  mov     esi, r12d
0x18002dcbd  shl     rsi, 5
0x18002dcc1  mov     rcx, [rbx+20h]; psz
0x18002dcc5  call    cs:__imp_SysAllocString
0x18002dccb  mov     rdx, [rbp+57h+var_88]
0x18002dccf  mov     [rsi+rdx], rax
0x18002dcd3  movups  xmm0, xmmword ptr [rbx+28h]
0x18002dcd7  movups  xmmword ptr [rsi+rdx+8], xmm0
0x18002dcdc  movsd   xmm1, qword ptr [rbx+38h]
0x18002dce1  movsd   qword ptr [rsi+rdx+18h], xmm1
0x18002dce7  mov     rcx, [rbx+10h]
0x18002dceb  xor     esi, esi
0x18002dced  cmp     [rcx+19h], sil
0x18002dcf1  jz      short loc_18002DD11
0x18002dcf3  mov     rax, [rbx+8]
0x18002dcf7  jmp     short loc_18002DD06
0x18002dcf9  cmp     rbx, [rax+10h]
0x18002dcfd  jnz     short loc_18002DD0C
0x18002dcff  mov     rbx, rax
0x18002dd02  mov     rax, [rax+8]
0x18002dd06  cmp     [rax+19h], sil
0x18002dd0a  jz      short loc_18002DCF9
0x18002dd0c  mov     rbx, rax
0x18002dd0f  jmp     short loc_18002DD2C
0x18002dd11  mov     rbx, rcx
0x18002dd14  mov     rcx, [rcx]
0x18002dd17  cmp     [rcx+19h], sil
0x18002dd1b  jnz     short loc_18002DD2C
0x18002dd1d  mov     rbx, rcx
0x18002dd20  mov     rax, [rcx]
0x18002dd23  mov     rcx, rax
0x18002dd26  cmp     [rax+19h], sil
0x18002dd2a  jz      short loc_18002DD1D
0x18002dd2c  inc     r12d
0x18002dd2f  jmp     short loc_18002DCB4
0x18002dd31  mov     rcx, [rbp+57h+var_90]
0x18002dd35  mov     rax, [rcx]
0x18002dd38  lea     r8, [rbp+57h+pvarg]
0x18002dd3c  mov     [rsp+0C0h+var_A0], r8
0x18002dd41  mov     r9, rdx
0x18002dd44  mov     r8d, [r13+8]
0x18002dd48  mov     rdx, rdi
0x18002dd4b  mov     rax, [rax+28h]
0x18002dd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd54  mov     ebx, eax
0x18002dd56  cmp     qword ptr [r13+8], 0
0x18002dd5b  mov     r12, [rbp+57h+arg_8]
0x18002dd5f  jbe     short loc_18002DD83
0x18002dd61  mov     r12, [rbp+57h+var_88]
0x18002dd65  mov     ecx, esi
0x18002dd67  shl     rcx, 5
0x18002dd6b  mov     rcx, [rcx+r12]; bstrString
0x18002dd6f  call    cs:__imp_SysFreeString
0x18002dd75  inc     esi
0x18002dd77  mov     eax, esi
0x18002dd79  cmp     rax, [r13+8]
0x18002dd7d  jb      short loc_18002DD65
0x18002dd7f  mov     r12, [rbp+57h+arg_8]
0x18002dd83  test    ebx, ebx
0x18002dd85  jnz     loc_18002DE2A
0x18002dd8b  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18002dd8f  lea     eax, [rbx+9]
0x18002dd92  mov     word ptr [rbp+57h+pvargSrc], ax
0x18002dd96  mov     qword ptr [rbp+57h+pvargSrc+8], rcx
0x18002dd9a  test    rcx, rcx
0x18002dd9d  jz      short loc_18002DDAC
0x18002dd9f  mov     rax, [rcx]
0x18002dda2  mov     rax, [rax+8]
0x18002dda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddab  nop
0x18002ddac  lea     rax, [rbp+57h+pvargSrc]
0x18002ddb0  cmp     r15, rax
0x18002ddb3  jz      short loc_18002DDCA
0x18002ddb5  lea     rdx, [rbp+57h+pvargSrc]; pvargSrc
0x18002ddb9  mov     rcx, r15; pvargDest
0x18002ddbc  call    cs:__imp_VariantCopy
0x18002ddc2  test    eax, eax
0x18002ddc4  js      loc_18002DE9B
0x18002ddca  lea     rcx, [rbp+57h+pvargSrc]; pvarg
0x18002ddce  call    cs:__imp_VariantClear
0x18002ddd4  nop
0x18002ddd5  mov     rcx, [rbp+57h+var_90]
0x18002ddd9  test    rcx, rcx
0x18002dddc  jz      short loc_18002DDEB
0x18002ddde  mov     rax, [rcx]
0x18002dde1  mov     rax, [rax+10h]
0x18002dde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddea  nop
0x18002ddeb  mov     rcx, rdi; bstrString
0x18002ddee  call    cs:__imp_SysFreeString
0x18002ddf4  nop
0x18002ddf5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002ddf9  call    cs:__imp_VariantClear
0x18002ddff  nop
0x18002de00  mov     rdx, [r12]
0x18002de04  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002de08  mov     eax, r14d
0x18002de0b  lock xadd [rdx+10h], eax
0x18002de10  add     eax, r14d
0x18002de13  test    eax, eax
0x18002de15  jg      short loc_18002DE26
0x18002de17  mov     rcx, [rdx]
0x18002de1a  mov     rax, [rcx]
0x18002de1d  mov     rax, [rax+8]
0x18002de21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de26  xor     eax, eax
0x18002de28  jmp     short loc_18002DE87
0x18002de2a  mov     eax, 80004005h
0x18002de2f  test    ebx, ebx
0x18002de31  cmovns  ebx, eax
0x18002de34  mov     rcx, [rbp+57h+var_90]
0x18002de38  test    rcx, rcx
0x18002de3b  jz      short loc_18002DE4A
0x18002de3d  mov     rax, [rcx]
0x18002de40  mov     rax, [rax+10h]
0x18002de44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de49  nop
0x18002de4a  mov     rcx, rdi; bstrString
0x18002de4d  call    cs:__imp_SysFreeString
0x18002de53  nop
0x18002de54  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002de58  call    cs:__imp_VariantClear
0x18002de5e  nop
0x18002de5f  mov     rdx, [r12]
0x18002de63  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002de67  mov     ecx, r14d
0x18002de6a  lock xadd [rdx+10h], ecx
0x18002de6f  add     ecx, r14d
0x18002de72  test    ecx, ecx
0x18002de74  jg      short loc_18002DE85
0x18002de76  mov     rcx, [rdx]
0x18002de79  mov     r8, [rcx]
0x18002de7c  mov     rax, [r8+8]
0x18002de80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de85  mov     eax, ebx
0x18002de87  add     rsp, 88h
0x18002de8e  pop     r15
0x18002de90  pop     r14
0x18002de92  pop     r13
0x18002de94  pop     r12
0x18002de96  pop     rdi
0x18002de97  pop     rsi
0x18002de98  pop     rbx
0x18002de99  pop     rbp
0x18002de9a  retn
0x18002de9b  mov     word ptr [r15], 0Ah
0x18002dea1  mov     [r15+8], eax
0x18002dea5  mov     ecx, eax; int
0x18002dea7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002dead  mov     ecx, 8007000Eh; int
0x18002deb2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

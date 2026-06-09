# UICollection::_GetUIItemResId(IItem *,ushort * *)

- ea: `0x1800807ec`
- end: `0x180080b10`
- name: `?_GetUIItemResId@UICollection@@IEAAJPEAUIItem@@PEAPEAG@Z`
- size: `804`
- prototype: `int(UICollection *__hidden this, struct IItem *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005bda8`
- `0x180080360`

## callees

- `0x180055e64`
- `0x1800807ec`
- `0x180080b18`
- `0x1800a611c`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x1800808c4`
- `SHLWAPI!StrChrW` at `0x1800808c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080900`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180080a9f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180080a9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080abe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080abe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080ad1`
- `PROPSYS!PropVariantToStringAlloc` at `0x180080a74`
- `PROPSYS!PropVariantToStringAlloc` at `0x180080a74`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x180080a15`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x180080a15`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180080865`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180080865`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008085c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008088a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008085c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008088a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18008084b`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18008084b`
- `DUI70!?GetStringNull@Value@DirectUI@@SAPEAV12@XZ` at `0x180080820`
- `DUI70!?GetStringNull@Value@DirectUI@@SAPEAV12@XZ` at `0x180080820`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008083f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008083f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UICollection::_GetUIItemResId(UICollection *this, WCHAR *a2, unsigned __int16 **a3)
{
  __int64 StringNull; // rdi
  DirectUI::Value *Value; // r12
  const WCHAR *String; // rax
  const WCHAR *v8; // r14
  struct DirectUI::Element *Parent; // rax
  HRESULT ValueFromMap; // ebx
  PWSTR v12; // rax
  PWSTR v13; // r13
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rsi
  unsigned __int16 *v16; // rdx
  unsigned __int64 v17; // r8
  unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  WCHAR v20; // r9
  __int64 v21; // r9
  unsigned __int16 *v22; // rcx
  __int64 v23; // rsi
  bool v24; // cf
  WCHAR *v25; // rsi
  WCHAR *v26; // r14
  int v27; // eax
  PWSTR ppszOut; // [rsp+30h] [rbp-59h] BYREF
  int v29; // [rsp+38h] [rbp-51h] BYREF
  WCHAR *v30; // [rsp+40h] [rbp-49h] BYREF
  __int64 v31; // [rsp+48h] [rbp-41h]
  __int64 v32; // [rsp+50h] [rbp-39h]
  PCWSTR pszName[3]; // [rsp+58h] [rbp-31h] BYREF
  PROPVARIANT propvar[2]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v35; // [rsp+80h] [rbp-9h]
  PROPERTYKEY ppropkey; // [rsp+88h] [rbp-1h] BYREF

  ppszOut = a2;
  StringNull = DirectUI::Value::GetStringNull();
  while ( 1 )
  {
    if ( !this )
    {
      Value = (DirectUI::Value *)StringNull;
      ValueFromMap = -2147467259;
      goto LABEL_7;
    }
    Value = DirectUI::Element::GetValue(this, UICollection::UIItemCreationPropMapProp, 2, 0);
    String = DirectUI::Value::GetString(Value);
    v8 = String;
    if ( String )
      break;
    DirectUI::Value::Release(Value);
    Parent = DirectUI::Element::GetParent(this);
    this = (UICollection *)FindAncestorElement<UICollection>(Parent);
  }
  *a3 = 0;
  v12 = StrChrW(String, 0x3Au);
  v13 = v12;
  if ( !v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v8[v14] );
    *a3 = 0;
    v15 = v14 + 1;
    if ( v14 + 1 < v14 || !is_mul_ok(v15, 2u) )
    {
      ValueFromMap = -2147024362;
      goto LABEL_7;
    }
    v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15);
    *a3 = v16;
    ValueFromMap = v16 == 0 ? 0x8007000E : 0;
    if ( !v16 )
      goto LABEL_7;
    if ( v15 <= 0x7FFFFFFF )
    {
      if ( v14 < 0x7FFFFFFF )
      {
        v17 = v14 + 1;
        v18 = v16;
        v19 = 0;
        do
        {
          if ( !v14 )
            break;
          v20 = *v8;
          if ( !*v8 )
            break;
          ++v8;
          *v18++ = v20;
          --v14;
          ++v19;
          --v17;
        }
        while ( v17 );
        v21 = v19 - 1;
        if ( v17 )
          v21 = v19;
        v22 = v18 - 1;
        if ( v17 )
          v22 = v18;
        *v22 = 0;
        if ( v17 )
        {
          v24 = v15 == v21;
          v23 = v15 - v21;
          if ( !v24 && v23 != 1 && (unsigned __int64)(2 * v23) > 2 )
            memset_0(&v16[v21 + 1], 0, 2 * v23 - 2);
        }
        goto LABEL_7;
      }
      if ( v14 == -1 )
        goto LABEL_7;
    }
    *v16 = 0;
    goto LABEL_7;
  }
  v25 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  memset(pszName, 0, sizeof(pszName));
  ValueFromMap = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                   pszName,
                   v8,
                   v12 - v8);
  v26 = (WCHAR *)pszName[0];
  if ( ValueFromMap >= 0 )
  {
    memset(&ppropkey, 0, sizeof(ppropkey));
    ValueFromMap = PSGetPropertyKeyFromName(pszName[0], &ppropkey);
    if ( ValueFromMap >= 0 )
    {
      *(_OWORD *)propvar = 0;
      v35 = 0;
      v29 = 0;
      v27 = (*(__int64 (__fastcall **)(PWSTR, _QWORD, PROPERTYKEY *, PROPVARIANT *, int *))(*(_QWORD *)ppszOut + 24LL))(
              ppszOut,
              0,
              &ppropkey,
              propvar,
              &v29);
      if ( v27 < 0 )
      {
        if ( v27 == -2147483638 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &v30,
            L"~",
            -1);
          v25 = v30;
        }
      }
      else
      {
        ppszOut = 0;
        CoTaskMemFree(0);
        PropVariantToStringAlloc(propvar, &ppszOut);
        v25 = ppszOut;
        ppszOut = 0;
        v30 = v25;
        v32 = -1;
        v31 = -1;
        CoTaskMemFree(0);
      }
      PropVariantClear(propvar);
      ValueFromMap = GetValueFromMap(v13 + 1, v25, a3);
    }
  }
  if ( v26 )
    CoTaskMemFree(v26);
  if ( v25 )
    CoTaskMemFree(v25);
LABEL_7:
  DirectUI::Value::Release(Value);
  return (unsigned int)ValueFromMap;
}

```

## disassembly

```asm
0x1800807ec  mov     [rsp-8+arg_18], rbx
0x1800807f1  push    rbp
0x1800807f2  push    rsi
0x1800807f3  push    rdi
0x1800807f4  push    r12
0x1800807f6  push    r13
0x1800807f8  push    r14
0x1800807fa  push    r15
0x1800807fc  lea     rbp, [rsp-27h]
0x180080801  sub     rsp, 0B0h
0x180080808  mov     rax, cs:__security_cookie
0x18008080f  xor     rax, rsp
0x180080812  mov     [rbp+57h+var_40], rax
0x180080816  mov     r15, r8
0x180080819  mov     [rbp+57h+ppszOut], rdx
0x18008081d  mov     rbx, rcx
0x180080820  call    cs:__imp_?GetStringNull@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetStringNull(void)
0x180080826  mov     rdi, rax
0x180080829  test    rbx, rbx
0x18008082c  jz      short loc_180080878
0x18008082e  xor     r9d, r9d
0x180080831  lea     r8d, [r9+2]
0x180080835  lea     rdx, ?UIItemCreationPropMapProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::UIItemCreationPropMapProp(void)
0x18008083c  mov     rcx, rbx
0x18008083f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180080845  mov     r12, rax
0x180080848  mov     rcx, rax
0x18008084b  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180080851  mov     r14, rax
0x180080854  test    rax, rax
0x180080857  jnz     short loc_1800808B9
0x180080859  mov     rcx, r12
0x18008085c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180080862  mov     rcx, rbx
0x180080865  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18008086b  mov     rcx, rax
0x18008086e  call    ??$FindAncestorElement@VUICollection@@@@YAPEAVUICollection@@PEAVElement@DirectUI@@@Z; FindAncestorElement<UICollection>(DirectUI::Element *)
0x180080873  mov     rbx, rax
0x180080876  jmp     short loc_180080829
0x180080878  mov     r12, rdi
0x18008087b  mov     ebx, 80004005h
0x180080880  jmp     short loc_180080887
0x180080882  mov     ebx, 80070216h
0x180080887  mov     rcx, r12
0x18008088a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180080890  mov     eax, ebx
0x180080892  mov     rcx, [rbp+57h+var_40]
0x180080896  xor     rcx, rsp; StackCookie
0x180080899  call    __security_check_cookie
0x18008089e  mov     rbx, [rsp+0E0h+arg_18]
0x1800808a6  add     rsp, 0B0h
0x1800808ad  pop     r15
0x1800808af  pop     r14
0x1800808b1  pop     r13
0x1800808b3  pop     r12
0x1800808b5  pop     rdi
0x1800808b6  pop     rsi
0x1800808b7  pop     rbp
0x1800808b8  retn
0x1800808b9  xor     edi, edi
0x1800808bb  mov     [r15], rdi
0x1800808be  lea     edx, [rdi+3Ah]; wMatch
0x1800808c1  mov     rcx, r14; pszStart
0x1800808c4  call    cs:__imp_StrChrW
0x1800808ca  mov     r13, rax
0x1800808cd  test    rax, rax
0x1800808d0  jnz     loc_1800809C4
0x1800808d6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800808da  inc     rdi
0x1800808dd  cmp     [r14+rdi*2], r13w
0x1800808e2  jnz     short loc_1800808DA
0x1800808e4  mov     [r15], r13
0x1800808e7  lea     rsi, [rdi+1]
0x1800808eb  cmp     rsi, rdi
0x1800808ee  jb      short loc_180080882
0x1800808f0  mov     eax, 2
0x1800808f5  mul     rsi
0x1800808f8  test    rdx, rdx
0x1800808fb  jnz     short loc_180080882
0x1800808fd  mov     rcx, rax; cb
0x180080900  call    cs:__imp_CoTaskMemAlloc
0x180080906  mov     rdx, rax
0x180080909  mov     [r15], rax
0x18008090c  mov     rcx, rax
0x18008090f  neg     rcx
0x180080912  sbb     ebx, ebx
0x180080914  not     ebx
0x180080916  and     ebx, 8007000Eh
0x18008091c  test    rax, rax
0x18008091f  jz      loc_180080887
0x180080925  mov     eax, 7FFFFFFFh
0x18008092a  cmp     rsi, rax
0x18008092d  ja      loc_180080AE5
0x180080933  cmp     rdi, rax
0x180080936  jnb     loc_180080ADC
0x18008093c  test    rsi, rsi
0x18008093f  jz      loc_180080887
0x180080945  mov     r8, rsi
0x180080948  mov     rax, rdx
0x18008094b  mov     rcx, r13
0x18008094e  test    rdi, rdi
0x180080951  jz      short loc_180080975
0x180080953  movzx   r9d, word ptr [r14]
0x180080957  test    r9w, r9w
0x18008095b  jz      short loc_180080975
0x18008095d  add     r14, 2
0x180080961  mov     [rax], r9w
0x180080965  add     rax, 2
0x180080969  dec     rdi
0x18008096c  inc     rcx
0x18008096f  sub     r8, 1
0x180080973  jnz     short loc_18008094E
0x180080975  lea     r9, [rcx-1]
0x180080979  test    r8, r8
0x18008097c  cmovnz  r9, rcx
0x180080980  lea     rcx, [rax-2]
0x180080984  cmovnz  rcx, rax
0x180080988  mov     [rcx], r13w
0x18008098c  jz      loc_180080887
0x180080992  sub     rsi, r9
0x180080995  cmp     rsi, 1
0x180080999  jbe     loc_180080887
0x18008099f  lea     r8, [rsi+rsi]
0x1800809a3  cmp     r8, 2
0x1800809a7  jbe     loc_180080887
0x1800809ad  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800809b1  inc     r9
0x1800809b4  lea     rcx, [rdx+r9*2]; void *
0x1800809b8  xor     edx, edx; Val
0x1800809ba  call    memset_0
0x1800809bf  jmp     loc_180080887
0x1800809c4  mov     rsi, rdi
0x1800809c7  mov     [rbp+57h+var_A0], rdi
0x1800809cb  mov     [rbp+57h+var_98], rdi
0x1800809cf  mov     [rbp+57h+var_90], rdi
0x1800809d3  mov     [rbp+57h+pszName], rdi
0x1800809d7  mov     [rbp+57h+var_80], rdi
0x1800809db  mov     [rbp+57h+var_78], rdi
0x1800809df  mov     r8, r13
0x1800809e2  sub     r8, r14
0x1800809e5  sar     r8, 1
0x1800809e8  mov     rdx, r14
0x1800809eb  lea     rcx, [rbp+57h+pszName]
0x1800809ef  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800809f4  mov     ebx, eax
0x1800809f6  mov     r14, [rbp+57h+pszName]
0x1800809fa  test    eax, eax
0x1800809fc  js      loc_180080AB6
0x180080a02  xorps   xmm0, xmm0
0x180080a05  xor     eax, eax
0x180080a07  movups  xmmword ptr [rbp+57h+ppropkey.fmtid.Data1], xmm0
0x180080a0b  mov     [rbp+57h+ppropkey.pid], eax
0x180080a0e  lea     rdx, [rbp+57h+ppropkey]; ppropkey
0x180080a12  mov     rcx, r14; pszName
0x180080a15  call    cs:__imp_PSGetPropertyKeyFromName
0x180080a1b  mov     ebx, eax
0x180080a1d  test    eax, eax
0x180080a1f  js      loc_180080AB6
0x180080a25  xorps   xmm0, xmm0
0x180080a28  xor     eax, eax
0x180080a2a  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x180080a2e  mov     [rbp+57h+var_60], rax
0x180080a32  mov     [rbp+57h+var_A8], edi
0x180080a35  mov     rcx, [rbp+57h+ppszOut]
0x180080a39  mov     rax, [rcx]
0x180080a3c  lea     rdx, [rbp+57h+var_A8]
0x180080a40  mov     [rsp+0E0h+var_C0], rdx
0x180080a45  lea     r9, [rbp+57h+propvar]
0x180080a49  lea     r8, [rbp+57h+ppropkey]
0x180080a4d  xor     edx, edx
0x180080a4f  mov     rax, [rax+18h]
0x180080a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080a58  test    eax, eax
0x180080a5a  js      loc_180080AEE
0x180080a60  mov     [rbp+57h+ppszOut], rdi
0x180080a64  xor     ecx, ecx; pv
0x180080a66  call    cs:__imp_CoTaskMemFree
0x180080a6c  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x180080a70  lea     rcx, [rbp+57h+propvar]; propvar
0x180080a74  call    cs:__imp_PropVariantToStringAlloc
0x180080a7a  mov     rsi, [rbp+57h+ppszOut]
0x180080a7e  mov     [rbp+57h+ppszOut], rdi
0x180080a82  mov     [rbp+57h+var_A0], rsi
0x180080a86  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180080a8a  mov     [rbp+57h+var_90], rdi
0x180080a8e  mov     [rbp+57h+var_98], rdi
0x180080a92  xor     ecx, ecx; pv
0x180080a94  call    cs:__imp_CoTaskMemFree
0x180080a9a  nop
0x180080a9b  lea     rcx, [rbp+57h+propvar]; pvar
0x180080a9f  call    cs:__imp_PropVariantClear
0x180080aa5  lea     rcx, [r13+2]; pszStart
0x180080aa9  mov     r8, r15; unsigned __int16 **
0x180080aac  mov     rdx, rsi; pszStr1
0x180080aaf  call    ?GetValueFromMap@@YAJPEBG0PEAPEAG@Z; GetValueFromMap(ushort const *,ushort const *,ushort * *)
0x180080ab4  mov     ebx, eax
0x180080ab6  test    r14, r14
0x180080ab9  jz      short loc_180080AC5
0x180080abb  mov     rcx, r14; pv
0x180080abe  call    cs:__imp_CoTaskMemFree
0x180080ac4  nop
0x180080ac5  test    rsi, rsi
0x180080ac8  jz      loc_180080887
0x180080ace  mov     rcx, rsi; pv
0x180080ad1  call    cs:__imp_CoTaskMemFree
0x180080ad7  jmp     loc_180080887
0x180080adc  test    rsi, rsi
0x180080adf  jz      loc_180080887
0x180080ae5  mov     [rdx], r13w
0x180080ae9  jmp     loc_180080887
0x180080aee  cmp     eax, 8000000Ah
0x180080af3  jnz     short loc_180080A9B
0x180080af5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180080af9  lea     rdx, asc_18024DF70; "~"
0x180080b00  lea     rcx, [rbp+57h+var_A0]
0x180080b04  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180080b09  mov     rsi, [rbp+57h+var_A0]
0x180080b0d  jmp     short loc_180080A9B
```

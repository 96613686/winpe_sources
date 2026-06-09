# imp_ApxPinCreate

- ea: `0x1800246d0`
- end: `0x1800249ba`
- name: `imp_ApxPinCreate`
- size: `746`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, struct _APX_PIN_CONFIG *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a1b4`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ab68`
- `0x18000ae48`
- `0x18000d210`
- `0x180023274`
- `0x180023fdc`
- `0x1800246d0`

## string_xrefs

- `0x18002477e`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxPinCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        struct _APX_PIN_CONFIG *a3,
        Apx::ApfVerify *a4)
{
  Apx::ApfVerify *v8; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  wil::details *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  unsigned int v18; // r8d
  int v20; // [rsp+40h] [rbp-58h] BYREF
  __int16 v21; // [rsp+44h] [rbp-54h]
  struct Apx::ApfPin *v22; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v23[9]; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f42e13db022534e71d1da1205b6f7053_Traceguids);
  }
  v22 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_39;
  IsNull = Apx::ApfVerify::IsApxInitialized(v8);
  if ( IsNull < 0 )
    goto LABEL_39;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v10);
  if ( IsNull < 0 )
    goto LABEL_39;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v11);
  if ( IsNull < 0 )
    goto LABEL_39;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v12);
  if ( IsNull < 0 )
    goto LABEL_39;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Pin", v13);
  if ( IsNull < 0 )
    goto LABEL_39;
  *(_QWORD *)a4 = 0;
  if ( *(_DWORD *)a3 == 48 )
  {
    v16 = *((unsigned int *)a3 + 1);
    if ( (_DWORD)v16 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_40;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_f42e13db022534e71d1da1205b6f7053_Traceguids, v16, 0);
      goto LABEL_39;
    }
    if ( *((_DWORD *)a3 + 2) == -1 )
    {
      if ( *((_DWORD *)a3 + 3) != 1 || *((_DWORD *)a3 + 4) != 1 )
      {
        v18 = *(_DWORD *)Feature_Audio_Drivers_Apx_Streaming__descriptor;
        if ( (*(_DWORD *)Feature_Audio_Drivers_Apx_Streaming__descriptor & 4) == 0 )
        {
          v23[0] = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Audio_Drivers_Apx_Streaming>::GetCachedFeatureEnabledState(
                      v14,
                      v23);
          v18 = v23[0];
        }
        v20 = 0;
        v21 = 3;
        wil::details::ReportUsageToService(
          (__int64)&qword_1800338B8,
          0x2B35621u,
          (v18 >> 10) & 1,
          (v18 >> 11) & 1,
          (__int64)&v20,
          1u,
          3);
        IsNull = Apx::ApfPin::_CreateAndInitialize(a3, &v22);
        if ( IsNull < 0 )
        {
          if ( v22 )
            imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v22);
        }
        else
        {
          IsNull = 0;
          *(_QWORD *)a4 = ~(unsigned __int64)v22;
        }
        goto LABEL_39;
      }
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_40;
      v17 = 14;
    }
    else
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_40;
      v17 = 13;
    }
    WPP_SF_d(v15[2], v17, &WPP_f42e13db022534e71d1da1205b6f7053_Traceguids);
LABEL_39:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_40;
  }
  IsNull = -2147024809;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_f42e13db022534e71d1da1205b6f7053_Traceguids,
      48,
      *(_DWORD *)a3);
    goto LABEL_39;
  }
LABEL_40:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_(v15[2], 16, &WPP_f42e13db022534e71d1da1205b6f7053_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x1800246d0  push    rbx
0x1800246d2  push    rbp
0x1800246d3  push    rsi
0x1800246d4  push    rdi
0x1800246d5  push    r12
0x1800246d7  push    r13
0x1800246d9  push    r14
0x1800246db  sub     rsp, 60h
0x1800246df  mov     rsi, r9
0x1800246e2  mov     rdi, r8
0x1800246e5  mov     r14, rdx
0x1800246e8  mov     rbp, rcx
0x1800246eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246f2  lea     r12, WPP_GLOBAL_Control
0x1800246f9  lea     r13, WPP_f42e13db022534e71d1da1205b6f7053_Traceguids
0x180024700  cmp     rcx, r12
0x180024703  jz      short loc_180024722
0x180024705  test    byte ptr [rcx+1Ch], 1
0x180024709  jz      short loc_180024722
0x18002470b  cmp     byte ptr [rcx+19h], 5
0x18002470f  jb      short loc_180024722
0x180024711  mov     rcx, [rcx+10h]
0x180024715  mov     edx, 0Ah
0x18002471a  mov     r8, r13
0x18002471d  call    WPP_SF_
0x180024722  lea     rdx, aGlobals; "Globals"
0x180024729  mov     [rsp+98h+var_50], 0
0x180024732  mov     rcx, rbp; this
0x180024735  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18002473a  mov     ebx, eax
0x18002473c  test    eax, eax
0x18002473e  js      loc_180024980
0x180024744  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x180024749  mov     ebx, eax
0x18002474b  test    eax, eax
0x18002474d  js      loc_180024980
0x180024753  mov     rcx, rbp; this
0x180024756  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x18002475b  mov     ebx, eax
0x18002475d  test    eax, eax
0x18002475f  js      loc_180024980
0x180024765  lea     rdx, aAttributes; "Attributes"
0x18002476c  mov     rcx, r14; this
0x18002476f  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x180024774  mov     ebx, eax
0x180024776  test    eax, eax
0x180024778  js      loc_180024980
0x18002477e  lea     rdx, aConfig_0; "Config"
0x180024785  mov     rcx, rdi; this
0x180024788  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18002478d  mov     ebx, eax
0x18002478f  test    eax, eax
0x180024791  js      loc_180024980
0x180024797  lea     rdx, aPin; "Pin"
0x18002479e  mov     rcx, rsi; this
0x1800247a1  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800247a6  mov     ebx, eax
0x1800247a8  test    eax, eax
0x1800247aa  js      loc_180024980
0x1800247b0  mov     qword ptr [rsi], 0
0x1800247b7  mov     r9d, 30h ; '0'
0x1800247bd  mov     eax, [rdi]
0x1800247bf  cmp     eax, r9d
0x1800247c2  jz      short loc_180024806
0x1800247c4  mov     ebx, 80070057h
0x1800247c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247d0  cmp     rcx, r12
0x1800247d3  jz      loc_1800249A9
0x1800247d9  test    byte ptr [rcx+1Ch], 40h
0x1800247dd  jz      loc_180024987
0x1800247e3  cmp     byte ptr [rcx+19h], 2
0x1800247e7  jb      loc_180024987
0x1800247ed  mov     rcx, [rcx+10h]
0x1800247f1  lea     edx, [r9-25h]
0x1800247f5  mov     r8, r13
0x1800247f8  mov     dword ptr [rsp+98h+var_78], eax
0x1800247fc  call    WPP_SF_DDd
0x180024801  jmp     loc_180024980
0x180024806  mov     r9d, [rdi+4]
0x18002480a  test    r9d, r9d
0x18002480d  jz      short loc_180024856
0x18002480f  mov     ebx, 80070057h
0x180024814  mov     rcx, cs:WPP_GLOBAL_Control
0x18002481b  cmp     rcx, r12
0x18002481e  jz      loc_1800249A9
0x180024824  test    byte ptr [rcx+1Ch], 40h
0x180024828  jz      loc_180024987
0x18002482e  cmp     byte ptr [rcx+19h], 2
0x180024832  jb      loc_180024987
0x180024838  mov     rcx, [rcx+10h]
0x18002483c  mov     edx, 0Ch
0x180024841  mov     r8, r13
0x180024844  mov     dword ptr [rsp+98h+var_78], 0
0x18002484c  call    WPP_SF_DDd
0x180024851  jmp     loc_180024980
0x180024856  cmp     dword ptr [rdi+8], 0FFFFFFFFh
0x18002485a  jz      short loc_18002489E
0x18002485c  mov     ebx, 80070057h
0x180024861  mov     rcx, cs:WPP_GLOBAL_Control
0x180024868  cmp     rcx, r12
0x18002486b  jz      loc_1800249A9
0x180024871  test    byte ptr [rcx+1Ch], 40h
0x180024875  jz      loc_180024987
0x18002487b  cmp     byte ptr [rcx+19h], 2
0x18002487f  jb      loc_180024987
0x180024885  mov     edx, 0Dh
0x18002488a  mov     rcx, [rcx+10h]
0x18002488e  mov     r9d, ebx
0x180024891  mov     r8, r13
0x180024894  call    WPP_SF_d
0x180024899  jmp     loc_180024980
0x18002489e  cmp     dword ptr [rdi+0Ch], 1
0x1800248a2  jnz     short loc_1800248DA
0x1800248a4  cmp     dword ptr [rdi+10h], 1
0x1800248a8  jnz     short loc_1800248DA
0x1800248aa  mov     ebx, 80070057h
0x1800248af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248b6  cmp     rcx, r12
0x1800248b9  jz      loc_1800249A9
0x1800248bf  test    byte ptr [rcx+1Ch], 40h
0x1800248c3  jz      loc_180024987
0x1800248c9  cmp     byte ptr [rcx+19h], 2
0x1800248cd  jb      loc_180024987
0x1800248d3  mov     edx, 0Eh
0x1800248d8  jmp     short loc_18002488A
0x1800248da  mov     rax, cs:Feature_Audio_Drivers_Apx_Streaming__descriptor
0x1800248e1  mov     r8d, [rax]
0x1800248e4  test    r8b, 4
0x1800248e8  jnz     short loc_1800248FF
0x1800248ea  lea     rdx, [rsp+98h+var_48]
0x1800248ef  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Audio_Drivers_Apx_Streaming@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Audio_Drivers_Apx_Streaming>::GetCachedFeatureEnabledState(void)
0x1800248f4  mov     rcx, [rax]
0x1800248f7  mov     [rsp+98h+var_48], rcx
0x1800248fc  mov     r8d, ecx
0x1800248ff  mov     r9d, r8d
0x180024902  mov     [rsp+98h+var_68], 3
0x18002490a  xor     eax, eax
0x18002490c  shr     r9d, 0Bh
0x180024910  mov     [rsp+98h+var_58], eax
0x180024914  lea     rcx, qword_1800338B8
0x18002491b  shr     r8d, 0Ah
0x18002491f  lea     rax, [rsp+98h+var_58]
0x180024924  and     r9d, 1
0x180024928  mov     [rsp+98h+var_70], 1
0x180024930  and     r8d, 1
0x180024934  mov     [rsp+98h+var_78], rax
0x180024939  mov     edx, 2B35621h
0x18002493e  mov     [rsp+98h+var_54], 3
0x180024945  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18002494a  lea     rdx, [rsp+98h+var_50]; struct Apx::ApfPin **
0x18002494f  mov     rcx, rdi; struct _APX_PIN_CONFIG *
0x180024952  call    ?_CreateAndInitialize@ApfPin@Apx@@SAJPEAU_APX_PIN_CONFIG@@PEAPEAV12@@Z; Apx::ApfPin::_CreateAndInitialize(_APX_PIN_CONFIG *,Apx::ApfPin * *)
0x180024957  mov     ebx, eax
0x180024959  test    eax, eax
0x18002495b  js      short loc_18002496C
0x18002495d  mov     rax, [rsp+98h+var_50]
0x180024962  xor     ebx, ebx
0x180024964  not     rax
0x180024967  mov     [rsi], rax
0x18002496a  jmp     short loc_180024980
0x18002496c  mov     rdx, [rsp+98h+var_50]
0x180024971  test    rdx, rdx
0x180024974  jz      short loc_180024980
0x180024976  not     rdx; Apx::ApfVerify *
0x180024979  xor     ecx, ecx; this
0x18002497b  call    imp_ApxObjectDelete
0x180024980  mov     rcx, cs:WPP_GLOBAL_Control
0x180024987  cmp     rcx, r12
0x18002498a  jz      short loc_1800249A9
0x18002498c  test    byte ptr [rcx+1Ch], 1
0x180024990  jz      short loc_1800249A9
0x180024992  cmp     byte ptr [rcx+19h], 5
0x180024996  jb      short loc_1800249A9
0x180024998  mov     rcx, [rcx+10h]
0x18002499c  mov     edx, 10h
0x1800249a1  mov     r8, r13
0x1800249a4  call    WPP_SF_
0x1800249a9  mov     eax, ebx
0x1800249ab  add     rsp, 60h
0x1800249af  pop     r14
0x1800249b1  pop     r13
0x1800249b3  pop     r12
0x1800249b5  pop     rdi
0x1800249b6  pop     rsi
0x1800249b7  pop     rbp
0x1800249b8  pop     rbx
0x1800249b9  retn
```

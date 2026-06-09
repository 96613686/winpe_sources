# EffectPolicy::GetDelayedAECInsertionPolicy(EffectPack *,IPropertyStore *,SystemEffectDescriptor *,_GUID,INBOX_AEC_INSERTION_POLICY *,_AEC_POLICY_RESULTS &)

- ea: `0x180029870`
- end: `0x180029e24`
- name: `?GetDelayedAECInsertionPolicy@EffectPolicy@@SAJPEAVEffectPack@@PEAUIPropertyStore@@PEAVSystemEffectDescriptor@@U_GUID@@PEAW4INBOX_AEC_INSERTION_POLICY@@AEAU_AEC_POLICY_RESULTS@@@Z`
- size: `1460`
- prototype: `static int(struct EffectPack *, struct IPropertyStore *, struct SystemEffectDescriptor *, struct _GUID *__struct_ptr, enum INBOX_AEC_INSERTION_POLICY *, struct _AEC_POLICY_RESULTS *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013eaf0`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x180029660`
- `0x180029754`
- `0x180029870`
- `0x180029e2c`
- `0x180029eec`
- `0x180029f20`
- `0x180029f60`
- `0x180038d4c`
- `0x1800993e0`
- `0x1800a4ed8`
- `0x1800cddac`
- `0x1800ce75c`
- `0x1801528c0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800299eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180029dcf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800299eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180029dcf`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180029e1d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180029e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800299c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800299c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e10`

## string_xrefs

- `0x180029945`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`
- `0x1800299af`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`
- `0x1800299d0`: `avcore\audiocore\server\lib\audioserviceutil\effectpolicy.cpp`
- `0x180029b38`: `avcore\audiocore\server\lib\audioserviceutil\effectpolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall EffectPolicy::GetDelayedAECInsertionPolicy(
        struct CEndpointCharacteristics **a1,
        struct IPropertyStore *a2,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 *a3,
        struct _GUID *a4,
        enum INBOX_AEC_INSERTION_POLICY *a5,
        struct _AEC_POLICY_RESULTS *a6)
{
  void *v8; // rbx
  void *v9; // r14
  __int64 v10; // rdi
  __int64 v11; // r14
  int v12; // eax
  int v13; // edi
  __int64 v14; // rdi
  unsigned __int64 v15; // rcx
  void *v16; // rax
  void *v17; // rcx
  unsigned __int64 v18; // rcx
  BOOL v19; // r15d
  CCompositeSystemEffect *v20; // rax
  CCompositeSystemEffect *v21; // r14
  _QWORD *v23; // rax
  __int64 v24; // r9
  __int64 v25; // r10
  __int64 v26; // r11
  __int64 v27; // r8
  __int64 v28; // r14
  unsigned int i; // edi
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // [rsp+20h] [rbp-89h]
  int v34; // [rsp+20h] [rbp-89h]
  unsigned int v35; // [rsp+40h] [rbp-69h] BYREF
  __int64 v36; // [rsp+48h] [rbp-61h] BYREF
  void *Block; // [rsp+50h] [rbp-59h] BYREF
  __int64 v38; // [rsp+58h] [rbp-51h]
  __int64 v39; // [rsp+60h] [rbp-49h] BYREF
  struct _GUID *v40; // [rsp+68h] [rbp-41h]
  __int64 v41; // [rsp+70h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-31h] BYREF
  struct IPropertyStore *v43; // [rsp+80h] [rbp-29h]
  void *v44; // [rsp+88h] [rbp-21h]
  __int64 v45; // [rsp+90h] [rbp-19h] BYREF
  struct _GUID v46; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]

  v40 = a4;
  v43 = a2;
  *(_QWORD *)&v46.Data1 = a1;
  pv = 0;
  v35 = 0;
  v8 = 0;
  v44 = 0;
  v36 = 0;
  v39 = 0;
  v9 = 0;
  Block = 0;
  v38 = 0;
  v10 = 0;
  v41 = 0;
  if ( EffectPolicy::IsMicArray(a2, a6) && !EffectPolicy::IsValidMicArrayForAEC(a1[198], a3[12], v43, a6) )
  {
    *(_DWORD *)a5 = 2;
    *((_DWORD *)a6 + 16) = 5;
    goto LABEL_60;
  }
  v38 = 0;
  if ( *((_QWORD *)a3 + 2) )
  {
    ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator=(&Block);
    v11 = *((_QWORD *)a3 + 2);
    v12 = *(_DWORD *)(v11 + 8);
    if ( (_DWORD)v38 != v12 )
    {
      v13 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\systemeffect.cpp",
        (const char *)0x8007000ELL,
        v33);
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpolicy.cpp",
        (const char *)0x8007000ELL,
        v34);
      if ( Block )
        free(Block);
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v17 = 0;
      goto LABEL_30;
    }
    v14 = 40;
    if ( v12 <= 0 )
      v14 = 56;
    v15 = *(int *)(v14 + v11 + 8);
    if ( *(_DWORD *)(v14 + v11 + 8) )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 0x10 || (v15 *= 16LL, v15 > 0x7FFFFFFF) )
      {
        v8 = 0;
LABEL_14:
        v13 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\systemeffect.cpp",
          (const char *)0x8007000ELL,
          v33);
        CoTaskMemFree(v8);
        goto LABEL_15;
      }
    }
    v16 = CoTaskMemAlloc((unsigned int)v15);
    v8 = v16;
    if ( !v16 )
      goto LABEL_14;
    memcpy_0(v16, *(const void **)(v14 + v11), 16LL * *(int *)(v14 + v11 + 8));
    v44 = v8;
    CoTaskMemFree(0);
  }
  v18 = *((int *)a3 + 12);
  if ( v18 >= (unsigned __int64)a1[214] )
  {
    _o_terminate();
    JUMPOUT(0x180029E23LL);
  }
  v19 = ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find((char *)a1[215] + 16 * v18, v40) != -1;
  v36 = 0;
  v20 = (CCompositeSystemEffect *)operator new[](0x90u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v20 )
  {
    v13 = -2147024882;
    goto LABEL_29;
  }
  v21 = CCompositeSystemEffect::CCompositeSystemEffect(v20);
  v45 = 0;
  v33 = 1;
  v13 = CCompositeSystemEffect::RuntimeClassInitialize(v21, 0, 2, v19);
  if ( v13 < 0 )
  {
    if ( v21 )
      (*(void (__fastcall **)(CCompositeSystemEffect *))(*(_QWORD *)v21 + 16LL))(v21);
    Microsoft::WRL::Details::MakeAllocator<CAudioRenderEndpointChangeDelegator>::~MakeAllocator<CAudioRenderEndpointChangeDelegator>(&v45);
    goto LABEL_29;
  }
  v13 = (**(__int64 (__fastcall ***)(CCompositeSystemEffect *, GUID *, __int64 *))v21)(
          v21,
          &GUID_60091a17_6288_4f0a_a649_7b8e9028d2ee,
          &v36);
  (*(void (__fastcall **)(CCompositeSystemEffect *))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v13 < 0 )
  {
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpolicy.cpp",
      (const char *)(unsigned int)v13,
      v33);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
    ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&Block);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v39);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v36);
    v17 = v8;
LABEL_30:
    CoTaskMemFree(v17);
    CoTaskMemFree(pv);
    return (unsigned int)v13;
  }
  wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(
    *(_QWORD *)(*(_QWORD *)&v46.Data1 + 1584LL) + 40LL,
    &v41);
  v46 = *v40;
  v10 = v41;
  if ( (*(int (__fastcall **)(__int64, __int64, struct _GUID *, __int64, _DWORD, _QWORD, __int64 *))(*(_QWORD *)v36 + 24LL))(
         v36,
         v41,
         &v46,
         1,
         *((_DWORD *)a3 + 12),
         0,
         &v39) >= 0
    && (*(int (__fastcall **)(__int64, LPVOID *, unsigned int *, _QWORD))(*(_QWORD *)v39 + 24LL))(v39, &pv, &v35, 0) >= 0 )
  {
    *((_DWORD *)a6 + 9) = 0;
    LODWORD(v40) = 0;
    if ( v35 )
    {
      v23 = pv;
      v24 = *(_QWORD *)GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4;
      v25 = *(_QWORD *)GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4;
      v26 = *(_QWORD *)&GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1;
      v27 = *(_QWORD *)GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4;
      v28 = *(_QWORD *)&GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1;
      for ( i = (unsigned int)v40; i < v35; ++i )
      {
        v30 = v23[2 * i] - *(_QWORD *)&GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data1;
        if ( !v30 )
          v30 = v23[2 * i + 1] - v24;
        if ( !v30 )
        {
          *((_DWORD *)a6 + 9) |= 2u;
          v24 = *(_QWORD *)GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4;
          v25 = *(_QWORD *)GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4;
          v26 = *(_QWORD *)&GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1;
          v27 = *(_QWORD *)GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4;
          v28 = *(_QWORD *)&GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1;
        }
        v31 = v23[2 * i] - v26;
        if ( !v31 )
          v31 = v23[2 * i + 1] - v25;
        if ( !v31 )
        {
          *((_DWORD *)a6 + 9) |= 4u;
          v24 = *(_QWORD *)GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4;
          v25 = *(_QWORD *)GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4;
          v26 = *(_QWORD *)&GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1;
          v27 = *(_QWORD *)GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4;
          v28 = *(_QWORD *)&GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1;
        }
        v32 = v23[2 * i] - v28;
        if ( !v32 )
          v32 = v23[2 * i + 1] - v27;
        if ( !v32 )
        {
          *((_DWORD *)a6 + 9) |= 8u;
          v24 = *(_QWORD *)GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4;
          v25 = *(_QWORD *)GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4;
          v26 = *(_QWORD *)&GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1;
          v27 = *(_QWORD *)GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4;
          v28 = *(_QWORD *)&GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1;
        }
      }
      v10 = v41;
    }
  }
  if ( (*((_BYTE *)a6 + 36) & 4) != 0 && (*((_DWORD *)a3 + 12) == 3 || (*((_BYTE *)a6 + 36) & 2) != 0) )
  {
    EffectPolicy::IsIntegratedAudioDevice(v43, (int *)a6 + 10);
    if ( *((_DWORD *)a6 + 1) != 2 || !*((_DWORD *)a6 + 10) )
    {
      v9 = Block;
      if ( (*((_BYTE *)a6 + 36) & 8) != 0 )
      {
        *(_DWORD *)a5 = 0;
        *((_DWORD *)a6 + 16) = 9;
      }
      else
      {
        *(_DWORD *)a5 = 3;
        *((_DWORD *)a6 + 16) = 7;
      }
      goto LABEL_60;
    }
    *(_DWORD *)a5 = 2;
    *((_DWORD *)a6 + 16) = 0;
  }
  else
  {
    *(_DWORD *)a5 = 2;
    *((_DWORD *)a6 + 16) = 8;
  }
  v9 = Block;
LABEL_60:
  *((_DWORD *)a6 + 15) = *(_DWORD *)a5;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v9 )
    free(v9);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  CoTaskMemFree(v8);
  CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180029870  push    rbp
0x180029872  push    rbx
0x180029873  push    rsi
0x180029874  push    rdi
0x180029875  push    r12
0x180029877  push    r13
0x180029879  push    r14
0x18002987b  push    r15
0x18002987d  lea     rbp, [rsp-0Fh]
0x180029882  sub     rsp, 0B8h
0x180029889  mov     [rbp+47h+var_88], r9
0x18002988d  mov     r13, r8
0x180029890  mov     rax, rdx
0x180029893  mov     [rbp+47h+var_70], rdx
0x180029897  mov     r15, rcx
0x18002989a  mov     qword ptr [rbp+47h+var_50], rcx
0x18002989e  mov     r12, [rbp+47h+arg_20]
0x1800298a2  mov     rsi, [rbp+47h+arg_28]
0x1800298a6  xor     ecx, ecx
0x1800298a8  mov     [rbp+47h+pv], rcx
0x1800298ac  mov     [rbp+47h+var_B0], ecx
0x1800298af  mov     ebx, ecx
0x1800298b1  mov     [rbp+47h+var_68], rcx
0x1800298b5  mov     [rbp+47h+var_A8], rcx
0x1800298b9  mov     [rbp+47h+var_90], rcx
0x1800298bd  mov     r14d, ecx
0x1800298c0  mov     [rbp+47h+Block], rcx
0x1800298c4  mov     [rbp+47h+var_98], rcx
0x1800298c8  mov     edi, ecx
0x1800298ca  mov     [rbp+47h+var_80], rcx
0x1800298ce  mov     rdx, rsi; struct _AEC_POLICY_RESULTS *
0x1800298d1  mov     rcx, rax; struct IPropertyStore *
0x1800298d4  call    ?IsMicArray@EffectPolicy@@CA_NPEAUIPropertyStore@@AEAU_AEC_POLICY_RESULTS@@@Z; EffectPolicy::IsMicArray(IPropertyStore *,_AEC_POLICY_RESULTS &)
0x1800298d9  test    al, al
0x1800298db  jz      short loc_18002990C
0x1800298dd  mov     r9, rsi; struct _AEC_POLICY_RESULTS *
0x1800298e0  mov     r8, [rbp+47h+var_70]; struct IPropertyStore *
0x1800298e4  mov     edx, [r13+30h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800298e8  mov     rcx, [r15+630h]; struct CEndpointCharacteristics *
0x1800298ef  call    ?IsValidMicArrayForAEC@EffectPolicy@@CA_NPEAVCEndpointCharacteristics@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIPropertyStore@@AEAU_AEC_POLICY_RESULTS@@@Z; EffectPolicy::IsValidMicArrayForAEC(CEndpointCharacteristics *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IPropertyStore *,_AEC_POLICY_RESULTS &)
0x1800298f4  test    al, al
0x1800298f6  jnz     short loc_18002990C
0x1800298f8  mov     dword ptr [r12], 2
0x180029900  mov     dword ptr [rsi+40h], 5
0x180029907  jmp     loc_180029DAB
0x18002990c  mov     [rbp+47h+var_98], 0
0x180029914  xor     edi, edi
0x180029916  mov     rdx, [r13+10h]
0x18002991a  test    rdx, rdx
0x18002991d  jz      loc_180029A4B
0x180029923  lea     rcx, [rbp+47h+Block]
0x180029927  call    ??4?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator=(ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>> const &)
0x18002992c  mov     r14, [r13+10h]
0x180029930  mov     eax, [r14+8]
0x180029934  cmp     dword ptr [rbp+47h+var_98], eax
0x180029937  jz      short loc_180029958
0x180029939  mov     rcx, [rbp+4Fh]; this
0x18002993d  mov     edi, 8007000Eh
0x180029942  mov     r9d, edi; char *
0x180029945  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002994c  mov     edx, 0BAh; void *
0x180029951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029956  jmp     short loc_1800299C9
0x180029958  mov     edi, 28h ; '('
0x18002995d  lea     ecx, [rdi+10h]
0x180029960  test    eax, eax
0x180029962  cmovle  edi, ecx
0x180029965  movsxd  rcx, dword ptr [rdi+r14+8]
0x18002996a  test    rcx, rcx
0x18002996d  jz      short loc_18002998F
0x18002996f  xor     edx, edx
0x180029971  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029975  div     rcx
0x180029978  cmp     rax, 10h
0x18002997c  jnb     short loc_180029982
0x18002997e  xor     ebx, ebx
0x180029980  jmp     short loc_1800299A3
0x180029982  shl     rcx, 4
0x180029986  cmp     rcx, 7FFFFFFFh
0x18002998d  ja      short loc_18002997E
0x18002998f  mov     ecx, ecx; cb
0x180029991  call    cs:__imp_CoTaskMemAlloc
0x180029997  mov     rbx, rax
0x18002999a  test    rax, rax
0x18002999d  jnz     loc_180029A25
0x1800299a3  mov     rcx, [rbp+4Fh]; this
0x1800299a7  mov     edi, 8007000Eh
0x1800299ac  mov     r9d, edi; char *
0x1800299af  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800299b6  mov     edx, 0C0h; void *
0x1800299bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299c0  mov     rcx, rbx; pv
0x1800299c3  call    cs:__imp_CoTaskMemFree
0x1800299c9  mov     rcx, [rbp+4Fh]; this
0x1800299cd  mov     r9d, edi; char *
0x1800299d0  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800299d7  mov     edx, 136h; void *
0x1800299dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299e1  nop
0x1800299e2  mov     rcx, [rbp+47h+Block]; Block
0x1800299e6  test    rcx, rcx
0x1800299e9  jz      short loc_1800299F2
0x1800299eb  call    cs:__imp_free
0x1800299f1  nop
0x1800299f2  mov     rcx, [rbp+47h+var_90]
0x1800299f6  test    rcx, rcx
0x1800299f9  jz      short loc_180029A08
0x1800299fb  mov     rax, [rcx]
0x1800299fe  mov     rax, [rax+10h]
0x180029a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a07  nop
0x180029a08  mov     rcx, [rbp+47h+var_A8]
0x180029a0c  test    rcx, rcx
0x180029a0f  jz      short loc_180029A1E
0x180029a11  mov     rax, [rcx]
0x180029a14  mov     rax, [rax+10h]
0x180029a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a1d  nop
0x180029a1e  xor     ecx, ecx
0x180029a20  jmp     loc_180029B75
0x180029a25  movsxd  r8, dword ptr [rdi+r14+8]
0x180029a2a  shl     r8, 4; Size
0x180029a2e  mov     rdx, [rdi+r14]; Src
0x180029a32  mov     rcx, rbx; void *
0x180029a35  call    memcpy_0
0x180029a3a  mov     [rbp+47h+var_68], rbx
0x180029a3e  xor     ecx, ecx; pv
0x180029a40  call    cs:__imp_CoTaskMemFree
0x180029a46  mov     edi, [rdi+r14+8]
0x180029a4b  movsxd  rcx, dword ptr [r13+30h]
0x180029a4f  cmp     rcx, [r15+6B0h]
0x180029a56  jnb     loc_180029E1D
0x180029a5c  shl     rcx, 4
0x180029a60  add     rcx, [r15+6B8h]
0x180029a67  mov     rdx, [rbp+47h+var_88]
0x180029a6b  call    ?Find@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEBAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(_GUID const &)
0x180029a70  xor     r15d, r15d
0x180029a73  cmp     eax, 0FFFFFFFFh
0x180029a76  setnz   r15b
0x180029a7a  mov     [rbp+47h+var_A8], 0
0x180029a82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029a89  mov     ecx, 90h; unsigned __int64
0x180029a8e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029a93  test    rax, rax
0x180029a96  jnz     short loc_180029AA2
0x180029a98  mov     edi, 8007000Eh
0x180029a9d  jmp     loc_180029B31
0x180029aa2  mov     rcx, rax; this
0x180029aa5  call    ??0CCompositeSystemEffect@@QEAA@XZ; CCompositeSystemEffect::CCompositeSystemEffect(void)
0x180029aaa  mov     r14, rax
0x180029aad  mov     [rbp+47h+var_60], 0
0x180029ab5  mov     [rsp+0F0h+var_C0], rbx
0x180029aba  mov     dword ptr [rsp+0F0h+var_C8], edi
0x180029abe  mov     [rsp+0F0h+var_D0], 1; int
0x180029ac6  mov     r9d, r15d
0x180029ac9  mov     r15d, 2
0x180029acf  mov     r8d, r15d
0x180029ad2  xor     edx, edx
0x180029ad4  mov     rcx, rax
0x180029ad7  call    ?RuntimeClassInitialize@CCompositeSystemEffect@@QEAAJPEBU_tlgProvider_t@@W4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@W4FormatChangePosition@@W4AUDIO_DIRECTION@@IPEBU_GUID@@@Z; CCompositeSystemEffect::RuntimeClassInitialize(_tlgProvider_t const *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,FormatChangePosition,AUDIO_DIRECTION,uint,_GUID const *)
0x180029adc  mov     edi, eax
0x180029ade  test    eax, eax
0x180029ae0  jns     short loc_180029B02
0x180029ae2  test    r14, r14
0x180029ae5  jz      short loc_180029AF7
0x180029ae7  mov     rax, [r14]
0x180029aea  mov     rcx, r14
0x180029aed  mov     rax, [rax+10h]
0x180029af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af6  nop
0x180029af7  lea     rcx, [rbp+47h+var_60]
0x180029afb  call    ??1?$MakeAllocator@VCAudioRenderEndpointChangeDelegator@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioRenderEndpointChangeDelegator>::~MakeAllocator<CAudioRenderEndpointChangeDelegator>(void)
0x180029b00  jmp     short loc_180029B31
0x180029b02  mov     rax, [r14]
0x180029b05  lea     r8, [rbp+47h+var_A8]
0x180029b09  lea     rdx, _GUID_60091a17_6288_4f0a_a649_7b8e9028d2ee
0x180029b10  mov     rcx, r14
0x180029b13  mov     rax, [rax]
0x180029b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b1b  mov     edi, eax
0x180029b1d  mov     rax, [r14]
0x180029b20  mov     rcx, r14
0x180029b23  mov     rax, [rax+10h]
0x180029b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b2c  nop
0x180029b2d  test    edi, edi
0x180029b2f  jns     short loc_180029B9C
0x180029b31  mov     rcx, [rbp+4Fh]; this
0x180029b35  mov     r9d, edi; char *
0x180029b38  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audiose"...
0x180029b3f  mov     edx, 13Fh; void *
0x180029b44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029b49  nop
0x180029b4a  lea     rcx, [rbp+47h+var_80]
0x180029b4e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180029b53  nop
0x180029b54  lea     rcx, [rbp+47h+Block]; void *
0x180029b58  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x180029b5d  nop
0x180029b5e  lea     rcx, [rbp+47h+var_90]
0x180029b62  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180029b67  nop
0x180029b68  lea     rcx, [rbp+47h+var_A8]
0x180029b6c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180029b71  nop
0x180029b72  mov     rcx, rbx; pv
0x180029b75  call    cs:__imp_CoTaskMemFree
0x180029b7b  nop
0x180029b7c  mov     rcx, [rbp+47h+pv]; pv
0x180029b80  call    cs:__imp_CoTaskMemFree
0x180029b86  mov     eax, edi
0x180029b88  add     rsp, 0B8h
0x180029b8f  pop     r15
0x180029b91  pop     r14
0x180029b93  pop     r13
0x180029b95  pop     r12
0x180029b97  pop     rdi
0x180029b98  pop     rsi
0x180029b99  pop     rbx
0x180029b9a  pop     rbp
0x180029b9b  retn
0x180029b9c  mov     rcx, qword ptr [rbp+47h+var_50]
0x180029ba0  mov     rcx, [rcx+630h]
0x180029ba7  add     rcx, 28h ; '('
0x180029bab  lea     rdx, [rbp+47h+var_80]
0x180029baf  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x180029bb4  mov     rcx, [rbp+47h+var_A8]
0x180029bb8  mov     rax, [rbp+47h+var_88]
0x180029bbc  movaps  xmm0, xmmword ptr [rax]
0x180029bbf  movdqa  [rbp+47h+var_50], xmm0
0x180029bc4  mov     rax, [rcx]
0x180029bc7  lea     rdx, [rbp+47h+var_90]
0x180029bcb  mov     [rsp+0F0h+var_C0], rdx
0x180029bd0  mov     [rsp+0F0h+var_C8], 0
0x180029bd9  mov     edx, [r13+30h]
0x180029bdd  mov     [rsp+0F0h+var_D0], edx
0x180029be1  mov     r9d, 1
0x180029be7  lea     r8, [rbp+47h+var_50]
0x180029beb  mov     rdi, [rbp+47h+var_80]
0x180029bef  mov     rdx, rdi
0x180029bf2  mov     rax, [rax+18h]
0x180029bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bfb  test    eax, eax
0x180029bfd  js      loc_180029D37
0x180029c03  mov     rcx, [rbp+47h+var_90]
0x180029c07  mov     rax, [rcx]
0x180029c0a  xor     r9d, r9d
0x180029c0d  lea     r8, [rbp+47h+var_B0]
0x180029c11  lea     rdx, [rbp+47h+pv]
0x180029c15  mov     rax, [rax+18h]
0x180029c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c1e  test    eax, eax
0x180029c20  js      loc_180029D37
0x180029c26  mov     dword ptr [rsi+24h], 0
0x180029c2d  mov     dword ptr [rbp+47h+var_88], 0
0x180029c34  cmp     [rbp+47h+var_B0], 0
0x180029c38  jbe     loc_180029D37
0x180029c3e  mov     rax, [rbp+47h+pv]
0x180029c42  mov     r9, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029c49  mov     r10, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029c50  mov     r11, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029c57  mov     r8, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029c5e  mov     r14, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029c65  mov     edi, dword ptr [rbp+47h+var_88]
0x180029c68  mov     edx, edi
0x180029c6a  add     rdx, rdx
0x180029c6d  mov     rcx, [rax+rdx*8]
0x180029c71  sub     rcx, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029c78  jnz     short loc_180029C82
0x180029c7a  mov     rcx, [rax+rdx*8+8]
0x180029c7f  sub     rcx, r9
0x180029c82  test    rcx, rcx
0x180029c85  jnz     short loc_180029CAE
0x180029c87  or      [rsi+24h], r15d
0x180029c8b  mov     r9, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029c92  mov     r10, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029c99  mov     r11, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029ca0  mov     r8, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029ca7  mov     r14, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029cae  mov     rcx, [rax+rdx*8]
0x180029cb2  sub     rcx, r11
0x180029cb5  jnz     short loc_180029CBF
0x180029cb7  mov     rcx, [rax+rdx*8+8]
0x180029cbc  sub     rcx, r10
0x180029cbf  test    rcx, rcx
0x180029cc2  jnz     short loc_180029CEB
0x180029cc4  or      dword ptr [rsi+24h], 4
0x180029cc8  mov     r9, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029ccf  mov     r10, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029cd6  mov     r11, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029cdd  mov     r8, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029ce4  mov     r14, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029ceb  mov     rcx, [rax+rdx*8]
0x180029cef  sub     rcx, r14
0x180029cf2  jnz     short loc_180029CFC
0x180029cf4  mov     rcx, [rax+rdx*8+8]
0x180029cf9  sub     rcx, r8
0x180029cfc  test    rcx, rcx
0x180029cff  jnz     short loc_180029D28
0x180029d01  or      dword ptr [rsi+24h], 8
  ... truncated ...
```

# EffectPolicy::GetDelayedAECInsertionPolicy(EffectPack *,IPropertyStore *,SystemEffectDescriptor *,_GUID,INBOX_AEC_INSERTION_POLICY *,_AEC_POLICY_RESULTS &)

- ea: `0x180029710`
- end: `0x180029cc4`
- name: `?GetDelayedAECInsertionPolicy@EffectPolicy@@SAJPEAVEffectPack@@PEAUIPropertyStore@@PEAVSystemEffectDescriptor@@U_GUID@@PEAW4INBOX_AEC_INSERTION_POLICY@@AEAU_AEC_POLICY_RESULTS@@@Z`
- size: `1460`
- prototype: `static int(struct EffectPack *, struct IPropertyStore *, struct SystemEffectDescriptor *, struct _GUID *__struct_ptr, enum INBOX_AEC_INSERTION_POLICY *, struct _AEC_POLICY_RESULTS *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180098bdc`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x180029500`
- `0x1800295f4`
- `0x180029710`
- `0x180029ccc`
- `0x180029d8c`
- `0x180029dc0`
- `0x180029e00`
- `0x180038bec`
- `0x180099c3c`
- `0x1800a5738`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x180151bb0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002988b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180029c6f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002988b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180029c6f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180029cbd`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180029cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029cb0`

## string_xrefs

- `0x1800297e5`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`
- `0x18002984f`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`
- `0x180029870`: `avcore\audiocore\server\lib\audioserviceutil\effectpolicy.cpp`
- `0x1800299d8`: `avcore\audiocore\server\lib\audioserviceutil\effectpolicy.cpp`

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
    JUMPOUT(0x180029CC3LL);
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
0x180029710  push    rbp
0x180029712  push    rbx
0x180029713  push    rsi
0x180029714  push    rdi
0x180029715  push    r12
0x180029717  push    r13
0x180029719  push    r14
0x18002971b  push    r15
0x18002971d  lea     rbp, [rsp-0Fh]
0x180029722  sub     rsp, 0B8h
0x180029729  mov     [rbp+47h+var_88], r9
0x18002972d  mov     r13, r8
0x180029730  mov     rax, rdx
0x180029733  mov     [rbp+47h+var_70], rdx
0x180029737  mov     r15, rcx
0x18002973a  mov     qword ptr [rbp+47h+var_50], rcx
0x18002973e  mov     r12, [rbp+47h+arg_20]
0x180029742  mov     rsi, [rbp+47h+arg_28]
0x180029746  xor     ecx, ecx
0x180029748  mov     [rbp+47h+pv], rcx
0x18002974c  mov     [rbp+47h+var_B0], ecx
0x18002974f  mov     ebx, ecx
0x180029751  mov     [rbp+47h+var_68], rcx
0x180029755  mov     [rbp+47h+var_A8], rcx
0x180029759  mov     [rbp+47h+var_90], rcx
0x18002975d  mov     r14d, ecx
0x180029760  mov     [rbp+47h+Block], rcx
0x180029764  mov     [rbp+47h+var_98], rcx
0x180029768  mov     edi, ecx
0x18002976a  mov     [rbp+47h+var_80], rcx
0x18002976e  mov     rdx, rsi; struct _AEC_POLICY_RESULTS *
0x180029771  mov     rcx, rax; struct IPropertyStore *
0x180029774  call    ?IsMicArray@EffectPolicy@@CA_NPEAUIPropertyStore@@AEAU_AEC_POLICY_RESULTS@@@Z; EffectPolicy::IsMicArray(IPropertyStore *,_AEC_POLICY_RESULTS &)
0x180029779  test    al, al
0x18002977b  jz      short loc_1800297AC
0x18002977d  mov     r9, rsi; struct _AEC_POLICY_RESULTS *
0x180029780  mov     r8, [rbp+47h+var_70]; struct IPropertyStore *
0x180029784  mov     edx, [r13+30h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180029788  mov     rcx, [r15+630h]; struct CEndpointCharacteristics *
0x18002978f  call    ?IsValidMicArrayForAEC@EffectPolicy@@CA_NPEAVCEndpointCharacteristics@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIPropertyStore@@AEAU_AEC_POLICY_RESULTS@@@Z; EffectPolicy::IsValidMicArrayForAEC(CEndpointCharacteristics *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IPropertyStore *,_AEC_POLICY_RESULTS &)
0x180029794  test    al, al
0x180029796  jnz     short loc_1800297AC
0x180029798  mov     dword ptr [r12], 2
0x1800297a0  mov     dword ptr [rsi+40h], 5
0x1800297a7  jmp     loc_180029C4B
0x1800297ac  mov     [rbp+47h+var_98], 0
0x1800297b4  xor     edi, edi
0x1800297b6  mov     rdx, [r13+10h]
0x1800297ba  test    rdx, rdx
0x1800297bd  jz      loc_1800298EB
0x1800297c3  lea     rcx, [rbp+47h+Block]
0x1800297c7  call    ??4?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator=(ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>> const &)
0x1800297cc  mov     r14, [r13+10h]
0x1800297d0  mov     eax, [r14+8]
0x1800297d4  cmp     dword ptr [rbp+47h+var_98], eax
0x1800297d7  jz      short loc_1800297F8
0x1800297d9  mov     rcx, [rbp+4Fh]; this
0x1800297dd  mov     edi, 8007000Eh
0x1800297e2  mov     r9d, edi; char *
0x1800297e5  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800297ec  mov     edx, 0BAh; void *
0x1800297f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800297f6  jmp     short loc_180029869
0x1800297f8  mov     edi, 28h ; '('
0x1800297fd  lea     ecx, [rdi+10h]
0x180029800  test    eax, eax
0x180029802  cmovle  edi, ecx
0x180029805  movsxd  rcx, dword ptr [rdi+r14+8]
0x18002980a  test    rcx, rcx
0x18002980d  jz      short loc_18002982F
0x18002980f  xor     edx, edx
0x180029811  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029815  div     rcx
0x180029818  cmp     rax, 10h
0x18002981c  jnb     short loc_180029822
0x18002981e  xor     ebx, ebx
0x180029820  jmp     short loc_180029843
0x180029822  shl     rcx, 4
0x180029826  cmp     rcx, 7FFFFFFFh
0x18002982d  ja      short loc_18002981E
0x18002982f  mov     ecx, ecx; cb
0x180029831  call    cs:__imp_CoTaskMemAlloc
0x180029837  mov     rbx, rax
0x18002983a  test    rax, rax
0x18002983d  jnz     loc_1800298C5
0x180029843  mov     rcx, [rbp+4Fh]; this
0x180029847  mov     edi, 8007000Eh
0x18002984c  mov     r9d, edi; char *
0x18002984f  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x180029856  mov     edx, 0C0h; void *
0x18002985b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029860  mov     rcx, rbx; pv
0x180029863  call    cs:__imp_CoTaskMemFree
0x180029869  mov     rcx, [rbp+4Fh]; this
0x18002986d  mov     r9d, edi; char *
0x180029870  lea     r8, aAvcoreAudiocor_76; "avcore\\audiocore\\server\\lib\\audiose"...
0x180029877  mov     edx, 136h; void *
0x18002987c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029881  nop
0x180029882  mov     rcx, [rbp+47h+Block]; Block
0x180029886  test    rcx, rcx
0x180029889  jz      short loc_180029892
0x18002988b  call    cs:__imp_free
0x180029891  nop
0x180029892  mov     rcx, [rbp+47h+var_90]
0x180029896  test    rcx, rcx
0x180029899  jz      short loc_1800298A8
0x18002989b  mov     rax, [rcx]
0x18002989e  mov     rax, [rax+10h]
0x1800298a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298a7  nop
0x1800298a8  mov     rcx, [rbp+47h+var_A8]
0x1800298ac  test    rcx, rcx
0x1800298af  jz      short loc_1800298BE
0x1800298b1  mov     rax, [rcx]
0x1800298b4  mov     rax, [rax+10h]
0x1800298b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298bd  nop
0x1800298be  xor     ecx, ecx
0x1800298c0  jmp     loc_180029A15
0x1800298c5  movsxd  r8, dword ptr [rdi+r14+8]
0x1800298ca  shl     r8, 4; Size
0x1800298ce  mov     rdx, [rdi+r14]; Src
0x1800298d2  mov     rcx, rbx; void *
0x1800298d5  call    memcpy_0
0x1800298da  mov     [rbp+47h+var_68], rbx
0x1800298de  xor     ecx, ecx; pv
0x1800298e0  call    cs:__imp_CoTaskMemFree
0x1800298e6  mov     edi, [rdi+r14+8]
0x1800298eb  movsxd  rcx, dword ptr [r13+30h]
0x1800298ef  cmp     rcx, [r15+6B0h]
0x1800298f6  jnb     loc_180029CBD
0x1800298fc  shl     rcx, 4
0x180029900  add     rcx, [r15+6B8h]
0x180029907  mov     rdx, [rbp+47h+var_88]
0x18002990b  call    ?Find@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEBAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(_GUID const &)
0x180029910  xor     r15d, r15d
0x180029913  cmp     eax, 0FFFFFFFFh
0x180029916  setnz   r15b
0x18002991a  mov     [rbp+47h+var_A8], 0
0x180029922  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029929  mov     ecx, 90h; unsigned __int64
0x18002992e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029933  test    rax, rax
0x180029936  jnz     short loc_180029942
0x180029938  mov     edi, 8007000Eh
0x18002993d  jmp     loc_1800299D1
0x180029942  mov     rcx, rax; this
0x180029945  call    ??0CCompositeSystemEffect@@QEAA@XZ; CCompositeSystemEffect::CCompositeSystemEffect(void)
0x18002994a  mov     r14, rax
0x18002994d  mov     [rbp+47h+var_60], 0
0x180029955  mov     [rsp+0F0h+var_C0], rbx
0x18002995a  mov     dword ptr [rsp+0F0h+var_C8], edi
0x18002995e  mov     [rsp+0F0h+var_D0], 1; int
0x180029966  mov     r9d, r15d
0x180029969  mov     r15d, 2
0x18002996f  mov     r8d, r15d
0x180029972  xor     edx, edx
0x180029974  mov     rcx, rax
0x180029977  call    ?RuntimeClassInitialize@CCompositeSystemEffect@@QEAAJPEBU_tlgProvider_t@@W4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@W4FormatChangePosition@@W4AUDIO_DIRECTION@@IPEBU_GUID@@@Z; CCompositeSystemEffect::RuntimeClassInitialize(_tlgProvider_t const *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,FormatChangePosition,AUDIO_DIRECTION,uint,_GUID const *)
0x18002997c  mov     edi, eax
0x18002997e  test    eax, eax
0x180029980  jns     short loc_1800299A2
0x180029982  test    r14, r14
0x180029985  jz      short loc_180029997
0x180029987  mov     rax, [r14]
0x18002998a  mov     rcx, r14
0x18002998d  mov     rax, [rax+10h]
0x180029991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029996  nop
0x180029997  lea     rcx, [rbp+47h+var_60]
0x18002999b  call    ??1?$MakeAllocator@VCAudioRenderEndpointChangeDelegator@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioRenderEndpointChangeDelegator>::~MakeAllocator<CAudioRenderEndpointChangeDelegator>(void)
0x1800299a0  jmp     short loc_1800299D1
0x1800299a2  mov     rax, [r14]
0x1800299a5  lea     r8, [rbp+47h+var_A8]
0x1800299a9  lea     rdx, _GUID_60091a17_6288_4f0a_a649_7b8e9028d2ee
0x1800299b0  mov     rcx, r14
0x1800299b3  mov     rax, [rax]
0x1800299b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299bb  mov     edi, eax
0x1800299bd  mov     rax, [r14]
0x1800299c0  mov     rcx, r14
0x1800299c3  mov     rax, [rax+10h]
0x1800299c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299cc  nop
0x1800299cd  test    edi, edi
0x1800299cf  jns     short loc_180029A3C
0x1800299d1  mov     rcx, [rbp+4Fh]; this
0x1800299d5  mov     r9d, edi; char *
0x1800299d8  lea     r8, aAvcoreAudiocor_76; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800299df  mov     edx, 13Fh; void *
0x1800299e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299e9  nop
0x1800299ea  lea     rcx, [rbp+47h+var_80]
0x1800299ee  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800299f3  nop
0x1800299f4  lea     rcx, [rbp+47h+Block]; void *
0x1800299f8  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x1800299fd  nop
0x1800299fe  lea     rcx, [rbp+47h+var_90]
0x180029a02  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180029a07  nop
0x180029a08  lea     rcx, [rbp+47h+var_A8]
0x180029a0c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180029a11  nop
0x180029a12  mov     rcx, rbx; pv
0x180029a15  call    cs:__imp_CoTaskMemFree
0x180029a1b  nop
0x180029a1c  mov     rcx, [rbp+47h+pv]; pv
0x180029a20  call    cs:__imp_CoTaskMemFree
0x180029a26  mov     eax, edi
0x180029a28  add     rsp, 0B8h
0x180029a2f  pop     r15
0x180029a31  pop     r14
0x180029a33  pop     r13
0x180029a35  pop     r12
0x180029a37  pop     rdi
0x180029a38  pop     rsi
0x180029a39  pop     rbx
0x180029a3a  pop     rbp
0x180029a3b  retn
0x180029a3c  mov     rcx, qword ptr [rbp+47h+var_50]
0x180029a40  mov     rcx, [rcx+630h]
0x180029a47  add     rcx, 28h ; '('
0x180029a4b  lea     rdx, [rbp+47h+var_80]
0x180029a4f  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x180029a54  mov     rcx, [rbp+47h+var_A8]
0x180029a58  mov     rax, [rbp+47h+var_88]
0x180029a5c  movaps  xmm0, xmmword ptr [rax]
0x180029a5f  movdqa  [rbp+47h+var_50], xmm0
0x180029a64  mov     rax, [rcx]
0x180029a67  lea     rdx, [rbp+47h+var_90]
0x180029a6b  mov     [rsp+0F0h+var_C0], rdx
0x180029a70  mov     [rsp+0F0h+var_C8], 0
0x180029a79  mov     edx, [r13+30h]
0x180029a7d  mov     [rsp+0F0h+var_D0], edx
0x180029a81  mov     r9d, 1
0x180029a87  lea     r8, [rbp+47h+var_50]
0x180029a8b  mov     rdi, [rbp+47h+var_80]
0x180029a8f  mov     rdx, rdi
0x180029a92  mov     rax, [rax+18h]
0x180029a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a9b  test    eax, eax
0x180029a9d  js      loc_180029BD7
0x180029aa3  mov     rcx, [rbp+47h+var_90]
0x180029aa7  mov     rax, [rcx]
0x180029aaa  xor     r9d, r9d
0x180029aad  lea     r8, [rbp+47h+var_B0]
0x180029ab1  lea     rdx, [rbp+47h+pv]
0x180029ab5  mov     rax, [rax+18h]
0x180029ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029abe  test    eax, eax
0x180029ac0  js      loc_180029BD7
0x180029ac6  mov     dword ptr [rsi+24h], 0
0x180029acd  mov     dword ptr [rbp+47h+var_88], 0
0x180029ad4  cmp     [rbp+47h+var_B0], 0
0x180029ad8  jbe     loc_180029BD7
0x180029ade  mov     rax, [rbp+47h+pv]
0x180029ae2  mov     r9, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029ae9  mov     r10, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029af0  mov     r11, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029af7  mov     r8, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029afe  mov     r14, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029b05  mov     edi, dword ptr [rbp+47h+var_88]
0x180029b08  mov     edx, edi
0x180029b0a  add     rdx, rdx
0x180029b0d  mov     rcx, [rax+rdx*8]
0x180029b11  sub     rcx, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029b18  jnz     short loc_180029B22
0x180029b1a  mov     rcx, [rax+rdx*8+8]
0x180029b1f  sub     rcx, r9
0x180029b22  test    rcx, rcx
0x180029b25  jnz     short loc_180029B4E
0x180029b27  or      [rsi+24h], r15d
0x180029b2b  mov     r9, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029b32  mov     r10, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029b39  mov     r11, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029b40  mov     r8, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029b47  mov     r14, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029b4e  mov     rcx, [rax+rdx*8]
0x180029b52  sub     rcx, r11
0x180029b55  jnz     short loc_180029B5F
0x180029b57  mov     rcx, [rax+rdx*8+8]
0x180029b5c  sub     rcx, r10
0x180029b5f  test    rcx, rcx
0x180029b62  jnz     short loc_180029B8B
0x180029b64  or      dword ptr [rsi+24h], 4
0x180029b68  mov     r9, qword ptr cs:_GUID_6f64adbe_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029b6f  mov     r10, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029b76  mov     r11, qword ptr cs:_GUID_6f64adbf_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029b7d  mov     r8, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data4
0x180029b84  mov     r14, qword ptr cs:_GUID_6f64adc0_8211_11e2_8c70_2c27d7f001fa.Data1
0x180029b8b  mov     rcx, [rax+rdx*8]
0x180029b8f  sub     rcx, r14
0x180029b92  jnz     short loc_180029B9C
0x180029b94  mov     rcx, [rax+rdx*8+8]
0x180029b99  sub     rcx, r8
0x180029b9c  test    rcx, rcx
0x180029b9f  jnz     short loc_180029BC8
0x180029ba1  or      dword ptr [rsi+24h], 8
  ... truncated ...
```

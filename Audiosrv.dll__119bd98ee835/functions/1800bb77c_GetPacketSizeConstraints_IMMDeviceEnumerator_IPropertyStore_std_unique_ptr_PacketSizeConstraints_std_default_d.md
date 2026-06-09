# GetPacketSizeConstraints(IMMDeviceEnumerator *,IPropertyStore *,std::unique_ptr<PacketSizeConstraints,std::default_delete<PacketSizeConstraints>> &)

- ea: `0x1800bb77c`
- end: `0x1800bbc12`
- name: `?GetPacketSizeConstraints@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@AEAV?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@@Z`
- size: `1174`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18014283c`
- `0x180145ad0`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x18002cbc4`
- `0x1800424ec`
- `0x180051b30`
- `0x1800bb77c`
- `0x1800bbc18`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800cdf70`
- `0x1800cdfd8`
- `0x1800ce750`
- `0x1800ce75c`
- `0x1801409fc`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb971`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb9fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bba5e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bba8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bbae0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bbbdb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb971`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb9fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bba5e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bba8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bbae0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bbbdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bb9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbb48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbbb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bb9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbb48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbbb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetPacketSizeConstraints(__int64 a1, __int64 a2, __int64 *a3)
{
  __int128 *v6; // rdi
  char v7; // si
  int v8; // eax
  void *v9; // rcx
  unsigned int v10; // ebx
  __int16 v11; // ax
  int v12; // eax
  __int64 (__fastcall *v13)(__int64, PROPVARIANT, __int64 **); // rbx
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  void *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rcx
  void *v20; // rdi
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rdx
  void *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-69h] BYREF
  void *pv; // [rsp+28h] [rbp-61h] BYREF
  __int64 *v29; // [rsp+30h] [rbp-59h] BYREF
  LPVOID v30; // [rsp+38h] [rbp-51h] BYREF
  size_t Size[2]; // [rsp+40h] [rbp-49h] BYREF
  void *Src; // [rsp+50h] [rbp-39h]
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v34; // [rsp+68h] [rbp-21h]
  void **p_pv; // [rsp+70h] [rbp-19h] BYREF
  void *v36; // [rsp+78h] [rbp-11h] BYREF
  char v37; // [rsp+80h] [rbp-9h]
  _DWORD v38[6]; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( dword_1801D6AB8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801D6AB8);
    if ( dword_1801D6AB8 == -1 )
    {
      xmmword_1801D6690 = DEVPKEY_KsAudio_PacketSize_Constraints2;
      dword_1801D66A0 = 2;
      xmmword_1801D66A4 = DEVPKEY_KsAudio_PacketSize_Constraints;
      dword_1801D66B4 = 2;
      Init_thread_footer(&dword_1801D6AB8);
    }
  }
  v30 = 0;
  v6 = &xmmword_1801D6690;
  v7 = 1;
  while ( 1 )
  {
    if ( v6 == (__int128 *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl'::`2'::impl )
      return 2147943568LL;
    *(_OWORD *)Size = 0;
    Src = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int128 *, size_t *))(*(_QWORD *)a2 + 40LL))(a2, v6, Size);
    v10 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36E,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)(unsigned int)v8,
        v27);
      goto LABEL_46;
    }
    v11 = Size[0];
    if ( !LOWORD(Size[0]) )
    {
      *(_OWORD *)pvar = 0;
      v34 = 0;
      v38[0] = 590439624;
      v38[1] = 1283267372;
      v38[2] = 1907779772;
      v38[3] = 1730509416;
      v38[4] = 1;
      v12 = (*(__int64 (__fastcall **)(__int64, _DWORD *, PROPVARIANT *))(*(_QWORD *)a2 + 40LL))(a2, v38, pvar);
      v10 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x376,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)(unsigned int)v12,
          v27);
      }
      else
      {
        if ( LOWORD(pvar[0]) != 31 )
        {
          PropVariantClear(pvar);
          v10 = -2147023728;
LABEL_46:
          PropVariantClear((PROPVARIANT *)Size);
          return v10;
        }
        v29 = 0;
        v13 = *(__int64 (__fastcall **)(__int64, PROPVARIANT, __int64 **))(*(_QWORD *)a1 + 40LL);
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v29);
        v14 = v13(a1, pvar[1], &v29);
        v10 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37C,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v14,
            v27);
        }
        else
        {
          v27 = 0;
          v15 = *v29;
          v27 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 32))(v29, 0, &v27);
          v10 = v16;
          if ( v16 < 0 )
          {
            v18 = 895;
          }
          else
          {
            v16 = (*(__int64 (__fastcall **)(__int64, __int128 *, size_t *))(*(_QWORD *)v27 + 40LL))(v27, v6, Size);
            v10 = v16;
            if ( v16 >= 0 )
            {
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v27);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
              PropVariantClear(pvar);
              v11 = Size[0];
              goto LABEL_14;
            }
            v18 = 897;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v16,
            v27);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v27);
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
      }
      PropVariantClear(pvar);
      goto LABEL_46;
    }
LABEL_14:
    if ( v11 == 65 && LODWORD(Size[1]) >= 0x28 )
      break;
LABEL_20:
    PropVariantClear((PROPVARIANT *)Size);
    v6 = (__int128 *)((char *)v6 + 20);
  }
  pv = 0;
  p_pv = &pv;
  v36 = 0;
  v37 = 1;
  v10 = CTCoAllocPolicy::Alloc(v9, 1u, LODWORD(Size[1]), &v36);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38C,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)v10,
      v27);
    v26 = pv;
    pv = 0;
    if ( v26 )
      CoTaskMemFree(v26);
    goto LABEL_46;
  }
  memcpy_0(pv, Src, LODWORD(Size[1]));
  v17 = pv;
  if ( LODWORD(Size[1]) < 24 * *((_DWORD *)pv + 3) + 16 )
  {
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    goto LABEL_20;
  }
  if ( *((_DWORD *)v6 + 4) != 2 || memcmp_0(v6, &DEVPKEY_KsAudio_PacketSize_Constraints2, 0x10u) )
    v7 = 0;
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    &v30,
    &pv);
  v19 = pv;
  pv = 0;
  if ( v19 )
    CoTaskMemFree(v19);
  PropVariantClear((PROPVARIANT *)Size);
  v20 = v30;
  if ( !v30 )
    return 2147943568LL;
  v21 = operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v21;
  if ( !v21 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A0,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8007000ELL,
      0);
    std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v27);
    if ( v20 )
      CoTaskMemFree(v20);
    return v10;
  }
  *v21 = 0;
  v21[1] = 0;
  *(_BYTE *)v21 = v7;
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    v21 + 1,
    &v30);
  v27 = 0;
  v24 = *a3;
  *a3 = (__int64)v22;
  if ( v24 )
    std::default_delete<PacketSizeConstraints>::operator()(v23, v24);
  std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v27);
  if ( v30 )
    CoTaskMemFree(v30);
  return 0;
}

```

## disassembly

```asm
0x1800bb77c  mov     [rsp-8+arg_18], rbx
0x1800bb781  push    rbp
0x1800bb782  push    rsi
0x1800bb783  push    rdi
0x1800bb784  push    r12
0x1800bb786  push    r13
0x1800bb788  push    r14
0x1800bb78a  push    r15
0x1800bb78c  lea     rbp, [rsp-27h]
0x1800bb791  sub     rsp, 0B0h
0x1800bb798  mov     rax, cs:__security_cookie
0x1800bb79f  xor     rax, rsp
0x1800bb7a2  mov     [rbp+57h+var_40], rax
0x1800bb7a6  mov     r14, r8
0x1800bb7a9  mov     r15, rdx
0x1800bb7ac  mov     r12, rcx
0x1800bb7af  mov     r9d, cs:_tls_index
0x1800bb7b6  mov     rax, gs:58h
0x1800bb7bf  mov     ecx, 4
0x1800bb7c4  mov     rax, [rax+r9*8]
0x1800bb7c8  mov     r9d, [rcx+rax]
0x1800bb7cc  cmp     cs:dword_1801D6AB8, r9d
0x1800bb7d3  jle     short loc_1800BB82A
0x1800bb7d5  lea     rcx, dword_1801D6AB8
0x1800bb7dc  call    _Init_thread_header
0x1800bb7e1  cmp     cs:dword_1801D6AB8, 0FFFFFFFFh
0x1800bb7e8  jnz     short loc_1800BB82A
0x1800bb7ea  movups  xmm0, cs:DEVPKEY_KsAudio_PacketSize_Constraints2
0x1800bb7f1  movups  cs:xmmword_1801D6690, xmm0
0x1800bb7f8  mov     eax, cs:dword_18018BD18
0x1800bb7fe  mov     cs:dword_1801D66A0, eax
0x1800bb804  movups  xmm0, cs:DEVPKEY_KsAudio_PacketSize_Constraints
0x1800bb80b  movups  cs:xmmword_1801D66A4, xmm0
0x1800bb812  mov     eax, cs:dword_180197C80
0x1800bb818  mov     cs:dword_1801D66B4, eax
0x1800bb81e  lea     rcx, dword_1801D6AB8
0x1800bb825  call    _Init_thread_footer
0x1800bb82a  xor     r13d, r13d
0x1800bb82d  mov     [rbp+57h+var_A8], r13
0x1800bb831  lea     rdi, xmmword_1801D6690
0x1800bb838  lea     esi, [r13+1]
0x1800bb83c  lea     rax, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl(void)'::`2'::impl
0x1800bb843  cmp     rdi, rax
0x1800bb846  jz      loc_1800BBBE6
0x1800bb84c  xorps   xmm0, xmm0
0x1800bb84f  xor     eax, eax
0x1800bb851  movups  xmmword ptr [rbp+57h+Size], xmm0
0x1800bb855  mov     [rbp+57h+Src], rax
0x1800bb859  mov     rax, [r15]
0x1800bb85c  lea     r8, [rbp+57h+Size]
0x1800bb860  mov     rdx, rdi
0x1800bb863  mov     rcx, r15
0x1800bb866  mov     rax, [rax+28h]
0x1800bb86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb86f  mov     ebx, eax
0x1800bb871  test    eax, eax
0x1800bb873  js      loc_1800BBBBE
0x1800bb879  movzx   eax, word ptr [rbp+57h+Size]
0x1800bb87d  test    ax, ax
0x1800bb880  jnz     loc_1800BB97B
0x1800bb886  xorps   xmm0, xmm0
0x1800bb889  xor     eax, eax
0x1800bb88b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800bb88f  mov     [rbp+57h+var_78], rax
0x1800bb893  mov     [rbp+57h+var_58], 233164C8h
0x1800bb89a  mov     [rbp+57h+var_54], 4C7D1B2Ch
0x1800bb8a1  mov     [rbp+57h+var_50], 71B668BCh
0x1800bb8a8  mov     [rbp+57h+var_4C], 67257A68h
0x1800bb8af  mov     [rbp+57h+var_48], esi
0x1800bb8b2  mov     rax, [r15]
0x1800bb8b5  lea     r8, [rbp+57h+pvar]
0x1800bb8b9  lea     rdx, [rbp+57h+var_58]
0x1800bb8bd  mov     rcx, r15
0x1800bb8c0  mov     rax, [rax+28h]
0x1800bb8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8c9  mov     ebx, eax
0x1800bb8cb  test    eax, eax
0x1800bb8cd  js      loc_1800BBA6E
0x1800bb8d3  cmp     word ptr [rbp+57h+pvar], 1Fh
0x1800bb8d8  jnz     loc_1800BBA5A
0x1800bb8de  mov     [rbp+57h+var_B0], r13
0x1800bb8e2  mov     rax, [r12]
0x1800bb8e6  mov     rbx, [rax+28h]
0x1800bb8ea  lea     rcx, [rbp+57h+var_B0]
0x1800bb8ee  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800bb8f3  lea     r8, [rbp+57h+var_B0]
0x1800bb8f7  mov     rdx, [rbp+57h+pvar+8]
0x1800bb8fb  mov     rcx, r12
0x1800bb8fe  mov     rax, rbx
0x1800bb901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb906  mov     ebx, eax
0x1800bb908  test    eax, eax
0x1800bb90a  js      loc_1800BBA36
0x1800bb910  mov     [rbp+57h+var_C0], r13
0x1800bb914  mov     rcx, [rbp+57h+var_B0]
0x1800bb918  mov     rax, [rcx]
0x1800bb91b  mov     [rbp+57h+var_C0], r13
0x1800bb91f  lea     r8, [rbp+57h+var_C0]
0x1800bb923  xor     edx, edx
0x1800bb925  mov     rax, [rax+20h]
0x1800bb929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb92e  mov     ebx, eax
0x1800bb930  test    eax, eax
0x1800bb932  js      loc_1800BBA12
0x1800bb938  mov     rcx, [rbp+57h+var_C0]
0x1800bb93c  mov     rax, [rcx]
0x1800bb93f  lea     r8, [rbp+57h+Size]
0x1800bb943  mov     rdx, rdi
0x1800bb946  mov     rax, [rax+28h]
0x1800bb94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb94f  mov     ebx, eax
0x1800bb951  test    eax, eax
0x1800bb953  js      loc_1800BBA0B
0x1800bb959  lea     rcx, [rbp+57h+var_C0]
0x1800bb95d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bb962  nop
0x1800bb963  lea     rcx, [rbp+57h+var_B0]
0x1800bb967  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bb96c  nop
0x1800bb96d  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bb971  call    cs:__imp_PropVariantClear
0x1800bb977  movzx   eax, word ptr [rbp+57h+Size]
0x1800bb97b  cmp     ax, 41h ; 'A'
0x1800bb97f  jnz     short loc_1800BB9F8
0x1800bb981  cmp     dword ptr [rbp+57h+Size+8], 28h ; '('
0x1800bb985  jb      short loc_1800BB9F8
0x1800bb987  mov     [rbp+57h+pv], r13
0x1800bb98b  lea     rax, [rbp+57h+pv]
0x1800bb98f  mov     [rbp+57h+var_70], rax
0x1800bb993  mov     [rbp+57h+var_68], r13
0x1800bb997  mov     [rbp+57h+var_60], sil
0x1800bb99b  mov     r8d, dword ptr [rbp+57h+Size+8]; unsigned __int64
0x1800bb99f  lea     r9, [rbp+57h+var_68]; void **
0x1800bb9a3  mov     edx, esi; unsigned int
0x1800bb9a5  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800bb9aa  mov     ebx, eax
0x1800bb9ac  lea     rcx, [rbp+57h+var_70]
0x1800bb9b0  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800bb9b5  test    ebx, ebx
0x1800bb9b7  js      loc_1800BBB90
0x1800bb9bd  mov     r8d, dword ptr [rbp+57h+Size+8]; Size
0x1800bb9c1  mov     rdx, [rbp+57h+Src]; Src
0x1800bb9c5  mov     rcx, [rbp+57h+pv]; void *
0x1800bb9c9  call    memcpy_0
0x1800bb9ce  mov     rcx, [rbp+57h+pv]; pv
0x1800bb9d2  mov     eax, [rcx+0Ch]
0x1800bb9d5  lea     edx, [rax+rax*2]
0x1800bb9d8  lea     edx, ds:10h[rdx*8]
0x1800bb9df  cmp     dword ptr [rbp+57h+Size+8], edx
0x1800bb9e2  jnb     loc_1800BBA96
0x1800bb9e8  mov     [rbp+57h+pv], r13
0x1800bb9ec  test    rcx, rcx
0x1800bb9ef  jz      short loc_1800BB9F8
0x1800bb9f1  call    cs:__imp_CoTaskMemFree
0x1800bb9f7  nop
0x1800bb9f8  lea     rcx, [rbp+57h+Size]; pvar
0x1800bb9fc  call    cs:__imp_PropVariantClear
0x1800bba02  add     rdi, 14h
0x1800bba06  jmp     loc_1800BB83C
0x1800bba0b  mov     edx, 381h
0x1800bba10  jmp     short loc_1800BBA17
0x1800bba12  mov     edx, 37Fh; void *
0x1800bba17  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bba1e  mov     r9d, eax; char *
0x1800bba21  mov     rcx, [rbp+5Fh]; this
0x1800bba25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bba2a  nop
0x1800bba2b  lea     rcx, [rbp+57h+var_C0]
0x1800bba2f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bba34  jmp     short loc_1800BBA4F
0x1800bba36  mov     rcx, [rbp+5Fh]; this
0x1800bba3a  mov     r9d, eax; char *
0x1800bba3d  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bba44  mov     edx, 37Ch; void *
0x1800bba49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bba4e  nop
0x1800bba4f  lea     rcx, [rbp+57h+var_B0]
0x1800bba53  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bba58  jmp     short loc_1800BBA87
0x1800bba5a  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bba5e  call    cs:__imp_PropVariantClear
0x1800bba64  mov     ebx, 80070490h
0x1800bba69  jmp     loc_1800BBBD7
0x1800bba6e  mov     rcx, [rbp+5Fh]; this
0x1800bba72  mov     r9d, eax; char *
0x1800bba75  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bba7c  mov     edx, 376h; void *
0x1800bba81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bba86  nop
0x1800bba87  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bba8b  call    cs:__imp_PropVariantClear
0x1800bba91  jmp     loc_1800BBBD7
0x1800bba96  mov     ebx, 10h
0x1800bba9b  cmp     dword ptr [rdi+10h], 2
0x1800bba9f  jnz     short loc_1800BBAB7
0x1800bbaa1  mov     r8d, ebx; Size
0x1800bbaa4  lea     rdx, DEVPKEY_KsAudio_PacketSize_Constraints2; Buf2
0x1800bbaab  mov     rcx, rdi; Buf1
0x1800bbaae  call    memcmp_0
0x1800bbab3  test    eax, eax
0x1800bbab5  jz      short loc_1800BBABA
0x1800bbab7  mov     sil, r13b
0x1800bbaba  lea     rdx, [rbp+57h+pv]
0x1800bbabe  lea     rcx, [rbp+57h+var_A8]
0x1800bbac2  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800bbac7  nop
0x1800bbac8  mov     rcx, [rbp+57h+pv]; pv
0x1800bbacc  mov     [rbp+57h+pv], r13
0x1800bbad0  test    rcx, rcx
0x1800bbad3  jz      short loc_1800BBADC
0x1800bbad5  call    cs:__imp_CoTaskMemFree
0x1800bbadb  nop
0x1800bbadc  lea     rcx, [rbp+57h+Size]; pvar
0x1800bbae0  call    cs:__imp_PropVariantClear
0x1800bbae6  mov     rdi, [rbp+57h+var_A8]
0x1800bbaea  test    rdi, rdi
0x1800bbaed  jz      loc_1800BBBE6
0x1800bbaf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bbafa  mov     rcx, rbx; unsigned __int64
0x1800bbafd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bbb02  mov     rbx, rax
0x1800bbb05  test    rax, rax
0x1800bbb08  jz      short loc_1800BBB55
0x1800bbb0a  mov     [rax], r13
0x1800bbb0d  mov     [rax+8], r13
0x1800bbb11  mov     [rax], sil
0x1800bbb14  lea     rcx, [rax+8]
0x1800bbb18  lea     rdx, [rbp+57h+var_A8]
0x1800bbb1c  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800bbb21  mov     [rbp+57h+var_C0], r13
0x1800bbb25  mov     rdx, [r14]
0x1800bbb28  mov     [r14], rbx
0x1800bbb2b  test    rdx, rdx
0x1800bbb2e  jz      short loc_1800BBB35
0x1800bbb30  call    ??R?$default_delete@UPacketSizeConstraints@@@std@@QEBAXPEAUPacketSizeConstraints@@@Z; std::default_delete<PacketSizeConstraints>::operator()(PacketSizeConstraints *)
0x1800bbb35  lea     rcx, [rbp+57h+var_C0]
0x1800bbb39  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x1800bbb3e  nop
0x1800bbb3f  mov     rcx, [rbp+57h+var_A8]; pv
0x1800bbb43  test    rcx, rcx
0x1800bbb46  jz      short loc_1800BBB4E
0x1800bbb48  call    cs:__imp_CoTaskMemFree
0x1800bbb4e  xor     eax, eax
0x1800bbb50  jmp     loc_1800BBBEB
0x1800bbb55  mov     [rbp+57h+var_C0], r13
0x1800bbb59  mov     rcx, [rbp+5Fh]; this
0x1800bbb5d  mov     ebx, 8007000Eh
0x1800bbb62  mov     r9d, ebx; char *
0x1800bbb65  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bbb6c  mov     edx, 3A0h; void *
0x1800bbb71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbb76  lea     rcx, [rbp+57h+var_C0]
0x1800bbb7a  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x1800bbb7f  nop
0x1800bbb80  test    rdi, rdi
0x1800bbb83  jz      short loc_1800BBBE2
0x1800bbb85  mov     rcx, rdi; pv
0x1800bbb88  call    cs:__imp_CoTaskMemFree
0x1800bbb8e  jmp     short loc_1800BBBE2
0x1800bbb90  mov     rcx, [rbp+5Fh]; this
0x1800bbb94  mov     r9d, ebx; char *
0x1800bbb97  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bbb9e  mov     edx, 38Ch; void *
0x1800bbba3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbba8  nop
0x1800bbba9  mov     rcx, [rbp+57h+pv]; pv
0x1800bbbad  mov     [rbp+57h+pv], r13
0x1800bbbb1  test    rcx, rcx
0x1800bbbb4  jz      short loc_1800BBBD7
0x1800bbbb6  call    cs:__imp_CoTaskMemFree
0x1800bbbbc  jmp     short loc_1800BBBD7
0x1800bbbbe  mov     rcx, [rbp+5Fh]; this
0x1800bbbc2  mov     r9d, eax; char *
0x1800bbbc5  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bbbcc  mov     edx, 36Eh; void *
0x1800bbbd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbbd6  nop
0x1800bbbd7  lea     rcx, [rbp+57h+Size]; pvar
0x1800bbbdb  call    cs:__imp_PropVariantClear
0x1800bbbe1  nop
0x1800bbbe2  mov     eax, ebx
0x1800bbbe4  jmp     short loc_1800BBBEB
0x1800bbbe6  mov     eax, 80070490h
0x1800bbbeb  mov     rcx, [rbp+57h+var_40]
0x1800bbbef  xor     rcx, rsp; StackCookie
0x1800bbbf2  call    __security_check_cookie
0x1800bbbf7  mov     rbx, [rsp+0E0h+arg_18]
0x1800bbbff  add     rsp, 0B0h
0x1800bbc06  pop     r15
0x1800bbc08  pop     r14
0x1800bbc0a  pop     r13
0x1800bbc0c  pop     r12
0x1800bbc0e  pop     rdi
0x1800bbc0f  pop     rsi
0x1800bbc10  pop     rbp
0x1800bbc11  retn
```

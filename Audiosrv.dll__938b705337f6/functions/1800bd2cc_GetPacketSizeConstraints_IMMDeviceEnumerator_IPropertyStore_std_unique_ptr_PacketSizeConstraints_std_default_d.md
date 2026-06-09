# GetPacketSizeConstraints(IMMDeviceEnumerator *,IPropertyStore *,std::unique_ptr<PacketSizeConstraints,std::default_delete<PacketSizeConstraints>> &)

- ea: `0x1800bd2cc`
- end: `0x1800bd762`
- name: `?GetPacketSizeConstraints@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@AEAV?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@@Z`
- size: `1174`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180141f28`
- `0x180144e50`

## callees

- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x18002ca64`
- `0x1800423cc`
- `0x180051fc0`
- `0x1800bd2cc`
- `0x1800bd768`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800cff60`
- `0x1800cffc8`
- `0x1800d0740`
- `0x1800d074c`
- `0x180140084`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd4c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd54c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd5ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd5db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd630`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd72b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd4c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd54c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd5ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd5db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd630`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd72b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd6d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd6d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd706`

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

  if ( dword_1801D5AA8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801D5AA8);
    if ( dword_1801D5AA8 == -1 )
    {
      xmmword_1801D5688 = DEVPKEY_KsAudio_PacketSize_Constraints2;
      dword_1801D5698 = 2;
      xmmword_1801D569C = DEVPKEY_KsAudio_PacketSize_Constraints;
      dword_1801D56AC = 2;
      Init_thread_footer(&dword_1801D5AA8);
    }
  }
  v30 = 0;
  v6 = &xmmword_1801D5688;
  v7 = 1;
  while ( 1 )
  {
    if ( v6 == (__int128 *)&`wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl'::`2'::impl )
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
0x1800bd2cc  mov     [rsp-8+arg_18], rbx
0x1800bd2d1  push    rbp
0x1800bd2d2  push    rsi
0x1800bd2d3  push    rdi
0x1800bd2d4  push    r12
0x1800bd2d6  push    r13
0x1800bd2d8  push    r14
0x1800bd2da  push    r15
0x1800bd2dc  lea     rbp, [rsp-27h]
0x1800bd2e1  sub     rsp, 0B0h
0x1800bd2e8  mov     rax, cs:__security_cookie
0x1800bd2ef  xor     rax, rsp
0x1800bd2f2  mov     [rbp+57h+var_40], rax
0x1800bd2f6  mov     r14, r8
0x1800bd2f9  mov     r15, rdx
0x1800bd2fc  mov     r12, rcx
0x1800bd2ff  mov     r9d, cs:_tls_index
0x1800bd306  mov     rax, gs:58h
0x1800bd30f  mov     ecx, 4
0x1800bd314  mov     rax, [rax+r9*8]
0x1800bd318  mov     r9d, [rcx+rax]
0x1800bd31c  cmp     cs:dword_1801D5AA8, r9d
0x1800bd323  jle     short loc_1800BD37A
0x1800bd325  lea     rcx, dword_1801D5AA8
0x1800bd32c  call    _Init_thread_header
0x1800bd331  cmp     cs:dword_1801D5AA8, 0FFFFFFFFh
0x1800bd338  jnz     short loc_1800BD37A
0x1800bd33a  movups  xmm0, cs:DEVPKEY_KsAudio_PacketSize_Constraints2
0x1800bd341  movups  cs:xmmword_1801D5688, xmm0
0x1800bd348  mov     eax, cs:dword_18018AD08
0x1800bd34e  mov     cs:dword_1801D5698, eax
0x1800bd354  movups  xmm0, cs:DEVPKEY_KsAudio_PacketSize_Constraints
0x1800bd35b  movups  cs:xmmword_1801D569C, xmm0
0x1800bd362  mov     eax, cs:dword_180196BC0
0x1800bd368  mov     cs:dword_1801D56AC, eax
0x1800bd36e  lea     rcx, dword_1801D5AA8
0x1800bd375  call    _Init_thread_footer
0x1800bd37a  xor     r13d, r13d
0x1800bd37d  mov     [rbp+57h+var_A8], r13
0x1800bd381  lea     rdi, xmmword_1801D5688
0x1800bd388  lea     esi, [r13+1]
0x1800bd38c  lea     rax, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl(void)'::`2'::impl
0x1800bd393  cmp     rdi, rax
0x1800bd396  jz      loc_1800BD736
0x1800bd39c  xorps   xmm0, xmm0
0x1800bd39f  xor     eax, eax
0x1800bd3a1  movups  xmmword ptr [rbp+57h+Size], xmm0
0x1800bd3a5  mov     [rbp+57h+Src], rax
0x1800bd3a9  mov     rax, [r15]
0x1800bd3ac  lea     r8, [rbp+57h+Size]
0x1800bd3b0  mov     rdx, rdi
0x1800bd3b3  mov     rcx, r15
0x1800bd3b6  mov     rax, [rax+28h]
0x1800bd3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd3bf  mov     ebx, eax
0x1800bd3c1  test    eax, eax
0x1800bd3c3  js      loc_1800BD70E
0x1800bd3c9  movzx   eax, word ptr [rbp+57h+Size]
0x1800bd3cd  test    ax, ax
0x1800bd3d0  jnz     loc_1800BD4CB
0x1800bd3d6  xorps   xmm0, xmm0
0x1800bd3d9  xor     eax, eax
0x1800bd3db  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800bd3df  mov     [rbp+57h+var_78], rax
0x1800bd3e3  mov     [rbp+57h+var_58], 233164C8h
0x1800bd3ea  mov     [rbp+57h+var_54], 4C7D1B2Ch
0x1800bd3f1  mov     [rbp+57h+var_50], 71B668BCh
0x1800bd3f8  mov     [rbp+57h+var_4C], 67257A68h
0x1800bd3ff  mov     [rbp+57h+var_48], esi
0x1800bd402  mov     rax, [r15]
0x1800bd405  lea     r8, [rbp+57h+pvar]
0x1800bd409  lea     rdx, [rbp+57h+var_58]
0x1800bd40d  mov     rcx, r15
0x1800bd410  mov     rax, [rax+28h]
0x1800bd414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd419  mov     ebx, eax
0x1800bd41b  test    eax, eax
0x1800bd41d  js      loc_1800BD5BE
0x1800bd423  cmp     word ptr [rbp+57h+pvar], 1Fh
0x1800bd428  jnz     loc_1800BD5AA
0x1800bd42e  mov     [rbp+57h+var_B0], r13
0x1800bd432  mov     rax, [r12]
0x1800bd436  mov     rbx, [rax+28h]
0x1800bd43a  lea     rcx, [rbp+57h+var_B0]
0x1800bd43e  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800bd443  lea     r8, [rbp+57h+var_B0]
0x1800bd447  mov     rdx, [rbp+57h+pvar+8]
0x1800bd44b  mov     rcx, r12
0x1800bd44e  mov     rax, rbx
0x1800bd451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd456  mov     ebx, eax
0x1800bd458  test    eax, eax
0x1800bd45a  js      loc_1800BD586
0x1800bd460  mov     [rbp+57h+var_C0], r13
0x1800bd464  mov     rcx, [rbp+57h+var_B0]
0x1800bd468  mov     rax, [rcx]
0x1800bd46b  mov     [rbp+57h+var_C0], r13
0x1800bd46f  lea     r8, [rbp+57h+var_C0]
0x1800bd473  xor     edx, edx
0x1800bd475  mov     rax, [rax+20h]
0x1800bd479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd47e  mov     ebx, eax
0x1800bd480  test    eax, eax
0x1800bd482  js      loc_1800BD562
0x1800bd488  mov     rcx, [rbp+57h+var_C0]
0x1800bd48c  mov     rax, [rcx]
0x1800bd48f  lea     r8, [rbp+57h+Size]
0x1800bd493  mov     rdx, rdi
0x1800bd496  mov     rax, [rax+28h]
0x1800bd49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd49f  mov     ebx, eax
0x1800bd4a1  test    eax, eax
0x1800bd4a3  js      loc_1800BD55B
0x1800bd4a9  lea     rcx, [rbp+57h+var_C0]
0x1800bd4ad  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bd4b2  nop
0x1800bd4b3  lea     rcx, [rbp+57h+var_B0]
0x1800bd4b7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bd4bc  nop
0x1800bd4bd  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bd4c1  call    cs:__imp_PropVariantClear
0x1800bd4c7  movzx   eax, word ptr [rbp+57h+Size]
0x1800bd4cb  cmp     ax, 41h ; 'A'
0x1800bd4cf  jnz     short loc_1800BD548
0x1800bd4d1  cmp     dword ptr [rbp+57h+Size+8], 28h ; '('
0x1800bd4d5  jb      short loc_1800BD548
0x1800bd4d7  mov     [rbp+57h+pv], r13
0x1800bd4db  lea     rax, [rbp+57h+pv]
0x1800bd4df  mov     [rbp+57h+var_70], rax
0x1800bd4e3  mov     [rbp+57h+var_68], r13
0x1800bd4e7  mov     [rbp+57h+var_60], sil
0x1800bd4eb  mov     r8d, dword ptr [rbp+57h+Size+8]; unsigned __int64
0x1800bd4ef  lea     r9, [rbp+57h+var_68]; void **
0x1800bd4f3  mov     edx, esi; unsigned int
0x1800bd4f5  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800bd4fa  mov     ebx, eax
0x1800bd4fc  lea     rcx, [rbp+57h+var_70]
0x1800bd500  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800bd505  test    ebx, ebx
0x1800bd507  js      loc_1800BD6E0
0x1800bd50d  mov     r8d, dword ptr [rbp+57h+Size+8]; Size
0x1800bd511  mov     rdx, [rbp+57h+Src]; Src
0x1800bd515  mov     rcx, [rbp+57h+pv]; void *
0x1800bd519  call    memcpy_0
0x1800bd51e  mov     rcx, [rbp+57h+pv]; pv
0x1800bd522  mov     eax, [rcx+0Ch]
0x1800bd525  lea     edx, [rax+rax*2]
0x1800bd528  lea     edx, ds:10h[rdx*8]
0x1800bd52f  cmp     dword ptr [rbp+57h+Size+8], edx
0x1800bd532  jnb     loc_1800BD5E6
0x1800bd538  mov     [rbp+57h+pv], r13
0x1800bd53c  test    rcx, rcx
0x1800bd53f  jz      short loc_1800BD548
0x1800bd541  call    cs:__imp_CoTaskMemFree
0x1800bd547  nop
0x1800bd548  lea     rcx, [rbp+57h+Size]; pvar
0x1800bd54c  call    cs:__imp_PropVariantClear
0x1800bd552  add     rdi, 14h
0x1800bd556  jmp     loc_1800BD38C
0x1800bd55b  mov     edx, 381h
0x1800bd560  jmp     short loc_1800BD567
0x1800bd562  mov     edx, 37Fh; void *
0x1800bd567  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bd56e  mov     r9d, eax; char *
0x1800bd571  mov     rcx, [rbp+5Fh]; this
0x1800bd575  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd57a  nop
0x1800bd57b  lea     rcx, [rbp+57h+var_C0]
0x1800bd57f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bd584  jmp     short loc_1800BD59F
0x1800bd586  mov     rcx, [rbp+5Fh]; this
0x1800bd58a  mov     r9d, eax; char *
0x1800bd58d  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bd594  mov     edx, 37Ch; void *
0x1800bd599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd59e  nop
0x1800bd59f  lea     rcx, [rbp+57h+var_B0]
0x1800bd5a3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bd5a8  jmp     short loc_1800BD5D7
0x1800bd5aa  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bd5ae  call    cs:__imp_PropVariantClear
0x1800bd5b4  mov     ebx, 80070490h
0x1800bd5b9  jmp     loc_1800BD727
0x1800bd5be  mov     rcx, [rbp+5Fh]; this
0x1800bd5c2  mov     r9d, eax; char *
0x1800bd5c5  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bd5cc  mov     edx, 376h; void *
0x1800bd5d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd5d6  nop
0x1800bd5d7  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bd5db  call    cs:__imp_PropVariantClear
0x1800bd5e1  jmp     loc_1800BD727
0x1800bd5e6  mov     ebx, 10h
0x1800bd5eb  cmp     dword ptr [rdi+10h], 2
0x1800bd5ef  jnz     short loc_1800BD607
0x1800bd5f1  mov     r8d, ebx; Size
0x1800bd5f4  lea     rdx, DEVPKEY_KsAudio_PacketSize_Constraints2; Buf2
0x1800bd5fb  mov     rcx, rdi; Buf1
0x1800bd5fe  call    memcmp_0
0x1800bd603  test    eax, eax
0x1800bd605  jz      short loc_1800BD60A
0x1800bd607  mov     sil, r13b
0x1800bd60a  lea     rdx, [rbp+57h+pv]
0x1800bd60e  lea     rcx, [rbp+57h+var_A8]
0x1800bd612  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800bd617  nop
0x1800bd618  mov     rcx, [rbp+57h+pv]; pv
0x1800bd61c  mov     [rbp+57h+pv], r13
0x1800bd620  test    rcx, rcx
0x1800bd623  jz      short loc_1800BD62C
0x1800bd625  call    cs:__imp_CoTaskMemFree
0x1800bd62b  nop
0x1800bd62c  lea     rcx, [rbp+57h+Size]; pvar
0x1800bd630  call    cs:__imp_PropVariantClear
0x1800bd636  mov     rdi, [rbp+57h+var_A8]
0x1800bd63a  test    rdi, rdi
0x1800bd63d  jz      loc_1800BD736
0x1800bd643  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bd64a  mov     rcx, rbx; unsigned __int64
0x1800bd64d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bd652  mov     rbx, rax
0x1800bd655  test    rax, rax
0x1800bd658  jz      short loc_1800BD6A5
0x1800bd65a  mov     [rax], r13
0x1800bd65d  mov     [rax+8], r13
0x1800bd661  mov     [rax], sil
0x1800bd664  lea     rcx, [rax+8]
0x1800bd668  lea     rdx, [rbp+57h+var_A8]
0x1800bd66c  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800bd671  mov     [rbp+57h+var_C0], r13
0x1800bd675  mov     rdx, [r14]
0x1800bd678  mov     [r14], rbx
0x1800bd67b  test    rdx, rdx
0x1800bd67e  jz      short loc_1800BD685
0x1800bd680  call    ??R?$default_delete@UPacketSizeConstraints@@@std@@QEBAXPEAUPacketSizeConstraints@@@Z; std::default_delete<PacketSizeConstraints>::operator()(PacketSizeConstraints *)
0x1800bd685  lea     rcx, [rbp+57h+var_C0]
0x1800bd689  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x1800bd68e  nop
0x1800bd68f  mov     rcx, [rbp+57h+var_A8]; pv
0x1800bd693  test    rcx, rcx
0x1800bd696  jz      short loc_1800BD69E
0x1800bd698  call    cs:__imp_CoTaskMemFree
0x1800bd69e  xor     eax, eax
0x1800bd6a0  jmp     loc_1800BD73B
0x1800bd6a5  mov     [rbp+57h+var_C0], r13
0x1800bd6a9  mov     rcx, [rbp+5Fh]; this
0x1800bd6ad  mov     ebx, 8007000Eh
0x1800bd6b2  mov     r9d, ebx; char *
0x1800bd6b5  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bd6bc  mov     edx, 3A0h; void *
0x1800bd6c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd6c6  lea     rcx, [rbp+57h+var_C0]
0x1800bd6ca  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x1800bd6cf  nop
0x1800bd6d0  test    rdi, rdi
0x1800bd6d3  jz      short loc_1800BD732
0x1800bd6d5  mov     rcx, rdi; pv
0x1800bd6d8  call    cs:__imp_CoTaskMemFree
0x1800bd6de  jmp     short loc_1800BD732
0x1800bd6e0  mov     rcx, [rbp+5Fh]; this
0x1800bd6e4  mov     r9d, ebx; char *
0x1800bd6e7  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bd6ee  mov     edx, 38Ch; void *
0x1800bd6f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd6f8  nop
0x1800bd6f9  mov     rcx, [rbp+57h+pv]; pv
0x1800bd6fd  mov     [rbp+57h+pv], r13
0x1800bd701  test    rcx, rcx
0x1800bd704  jz      short loc_1800BD727
0x1800bd706  call    cs:__imp_CoTaskMemFree
0x1800bd70c  jmp     short loc_1800BD727
0x1800bd70e  mov     rcx, [rbp+5Fh]; this
0x1800bd712  mov     r9d, eax; char *
0x1800bd715  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800bd71c  mov     edx, 36Eh; void *
0x1800bd721  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd726  nop
0x1800bd727  lea     rcx, [rbp+57h+Size]; pvar
0x1800bd72b  call    cs:__imp_PropVariantClear
0x1800bd731  nop
0x1800bd732  mov     eax, ebx
0x1800bd734  jmp     short loc_1800BD73B
0x1800bd736  mov     eax, 80070490h
0x1800bd73b  mov     rcx, [rbp+57h+var_40]
0x1800bd73f  xor     rcx, rsp; StackCookie
0x1800bd742  call    __security_check_cookie
0x1800bd747  mov     rbx, [rsp+0E0h+arg_18]
0x1800bd74f  add     rsp, 0B0h
0x1800bd756  pop     r15
0x1800bd758  pop     r14
0x1800bd75a  pop     r13
0x1800bd75c  pop     r12
0x1800bd75e  pop     rdi
0x1800bd75f  pop     rsi
0x1800bd760  pop     rbp
0x1800bd761  retn
```

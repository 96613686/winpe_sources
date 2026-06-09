# SensorGroup::CreateSensorGroupFromMediaSource(IMFMediaSource *,ushort const *,IUnknown *,IMFSensorGroup * *)

- ea: `0x18004b1ec`
- end: `0x18004b6a1`
- name: `?CreateSensorGroupFromMediaSource@SensorGroup@@SAJPEAUIMFMediaSource@@PEBGPEAUIUnknown@@PEAPEAUIMFSensorGroup@@@Z`
- size: `1205`
- prototype: `__int64 __fastcall(struct IMFMediaSource *, const char *, struct IUnknown *, struct IMFSensorGroup **)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18004c758`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000c348`
- `0x18000c94c`
- `0x18000fde4`
- `0x1800116a4`
- `0x180011960`
- `0x180019a4c`
- `0x180028d34`
- `0x18002c008`
- `0x18003369c`
- `0x180044adc`
- `0x18004b1ec`
- `0x18004bc70`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b3ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b480`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b3ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b480`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b53f`

## pseudocode

```c
__int64 __fastcall SensorGroup::CreateSensorGroupFromMediaSource(
        struct IMFMediaSource *a1,
        const char *a2,
        struct IUnknown *a3,
        struct IMFSensorGroup **a4)
{
  int v8; // edi
  __int64 v9; // rdx
  const char *v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  struct IMFSensorGroupId *v13; // rdi
  __int64 (__fastcall *v14)(struct IMFSensorGroupId *, GUID *, __int64 *); // rbx
  struct IMFMediaSourceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IMFMediaSource *, const IID *const, void **); // rax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 **); // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  SensorGroup *v24; // rax
  SensorGroup *v25; // rax
  SensorGroup *v26; // rbx
  __int64 *v27; // [rsp+30h] [rbp-50h] BYREF
  __int64 v28; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  __int64 v30; // [rsp+48h] [rbp-38h] BYREF
  struct IMFSensorGroupId *v31; // [rsp+50h] [rbp-30h] BYREF
  SensorGroup *v32; // [rsp+58h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+60h] [rbp-20h] BYREF
  __int64 v34; // [rsp+68h] [rbp-18h] BYREF
  char v35; // [rsp+70h] [rbp-10h]
  int v36; // [rsp+B0h] [rbp+30h] BYREF

  v32 = 0;
  v31 = 0;
  v30 = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
    {
LABEL_65:
      if ( !byte_18008D62D )
        goto LABEL_37;
      v22 = 139;
      goto LABEL_36;
    }
    v9 = 124;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, 0, v8);
    goto LABEL_65;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_65;
    v9 = 125;
    goto LABEL_4;
  }
  *a4 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v10 = L"<nullptr>";
    if ( a2 )
      v10 = a2;
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      126,
      (unsigned int)&WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
      (_DWORD)a1,
      (__int64)v10);
  }
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v31);
  v11 = SensorGroupId::CreateSensorGroupId(&v31);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_65;
    v12 = 127;
LABEL_64:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, 0, v11);
    goto LABEL_65;
  }
  v13 = v31;
  v14 = **(__int64 (__fastcall ***)(struct IMFSensorGroupId *, GUID *, __int64 *))v31;
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v30);
  v11 = v14(v13, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v30);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_65;
    v12 = 128;
    goto LABEL_64;
  }
  if ( a2 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v30 + 64LL))(v30, a2);
    v8 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_65;
      v12 = 133;
      goto LABEL_64;
    }
  }
  else
  {
    lpVtbl = a1->lpVtbl;
    pv = 0;
    v36 = 0;
    v27 = 0;
    QueryInterface = lpVtbl->QueryInterface;
    v28 = 0;
    v17 = ((__int64 (__fastcall *)(struct IMFMediaSource *, GUID *, __int64 *))QueryInterface)(
            a1,
            &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8,
            &v28);
    v8 = v17;
    if ( v17 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_23;
      v18 = 129;
      goto LABEL_22;
    }
    v19 = v28;
    v20 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v28 + 104LL);
    wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&v27);
    v17 = v20(v19, &v27);
    v8 = v17;
    if ( v17 < 0 )
    {
      if ( g_wppLevels )
      {
        v18 = 130;
LABEL_22:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, 0, v17);
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    v21 = *v27;
    p_pv = &pv;
    v34 = 0;
    v35 = 1;
    v8 = (*(__int64 (__fastcall **)(__int64 *, const IID *, __int64 *, int *))(v21 + 104))(
           v27,
           &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
           &v34,
           &v36);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&p_pv);
    if ( v8 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, 0, v8);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v28);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v27);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_65;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v30 + 64LL))(v30, pv);
    v8 = v17;
    if ( v17 < 0 )
    {
      if ( g_wppLevels )
      {
        v18 = 132;
        goto LABEL_22;
      }
LABEL_23:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v28);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v27);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_65;
    }
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v28);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v27);
    if ( pv )
      CoTaskMemFree(pv);
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 72LL))(v30, 0);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_65;
    v12 = 134;
    goto LABEL_64;
  }
  v24 = (SensorGroup *)operator new(0x198u);
  if ( v24 )
    v25 = SensorGroup::SensorGroup(v24, 0);
  else
    v25 = 0;
  wil::com_ptr_t<FSConfiguration,wil::err_returncode_policy>::attach((__int64 *)&v32, (__int64)v25);
  v26 = v32;
  if ( !v32 )
  {
    v8 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_65;
    v9 = 135;
    goto LABEL_4;
  }
  v11 = SensorGroup::InternalInitialize(v32);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_65;
    v12 = 136;
    goto LABEL_64;
  }
  v11 = SensorGroup::InitializeForPublishWithMediaSource(v26, v31, a1, a3);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_65;
    v12 = 137;
    goto LABEL_64;
  }
  v11 = (**(__int64 (__fastcall ***)(SensorGroup *, GUID *, struct IMFSensorGroup **))v26)(
          v26,
          &GUID_4110243a_9757_461f_89f1_f22345bcab4e,
          a4);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_65;
    v12 = 138;
    goto LABEL_64;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v22 = 140;
LABEL_36:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v22,
      &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
      (unsigned int)v8);
  }
LABEL_37:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v30);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v31);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004b1ec  mov     [rsp-28h+arg_8], rbx
0x18004b1f1  mov     [rsp-28h+arg_10], rdi
0x18004b1f6  push    rbp
0x18004b1f7  push    r12
0x18004b1f9  push    r13
0x18004b1fb  push    r14
0x18004b1fd  push    r15
0x18004b1ff  mov     rbp, rsp
0x18004b202  sub     rsp, 80h
0x18004b209  mov     [rbp+var_28], 0
0x18004b211  mov     r12, r9
0x18004b214  mov     [rbp+var_30], 0
0x18004b21c  mov     r13, r8
0x18004b21f  mov     [rbp+var_38], 0
0x18004b227  mov     r14, rdx
0x18004b22a  mov     r15, rcx
0x18004b22d  test    rcx, rcx
0x18004b230  jnz     short loc_18004B250
0x18004b232  mov     edi, 80070057h
0x18004b237  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b23e  jb      loc_18004B68A
0x18004b244  lea     edx, [rcx+7Ch]
0x18004b247  mov     dword ptr [rsp+80h+var_60], edi
0x18004b24b  jmp     loc_18004B670
0x18004b250  test    r12, r12
0x18004b253  jnz     short loc_18004B26E
0x18004b255  mov     edi, 80004003h
0x18004b25a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b261  jb      loc_18004B68A
0x18004b267  lea     edx, [r12+7Dh]
0x18004b26c  jmp     short loc_18004B247
0x18004b26e  mov     qword ptr [r9], 0
0x18004b275  cmp     cs:byte_18008D62D, 8
0x18004b27c  jb      short loc_18004B2B3
0x18004b27e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b285  lea     rax, aNullptr; "<nullptr>"
0x18004b28c  test    r14, r14
0x18004b28f  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004b296  mov     edx, 7Eh ; '~'
0x18004b29b  mov     r9, r15
0x18004b29e  cmovnz  rax, r14
0x18004b2a2  mov     rcx, [rcx+0D8h]
0x18004b2a9  mov     [rsp+80h+var_60], rax
0x18004b2ae  call    WPP_SF_qS
0x18004b2b3  lea     rcx, [rbp+var_30]
0x18004b2b7  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18004b2bc  lea     rcx, [rbp+var_30]; struct IMFSensorGroupId **
0x18004b2c0  call    ?CreateSensorGroupId@SensorGroupId@@SAJPEAPEAUIMFSensorGroupId@@@Z; SensorGroupId::CreateSensorGroupId(IMFSensorGroupId * *)
0x18004b2c5  mov     edi, eax
0x18004b2c7  test    eax, eax
0x18004b2c9  jns     short loc_18004B2E2
0x18004b2cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b2d2  jb      loc_18004B68A
0x18004b2d8  mov     edx, 7Fh
0x18004b2dd  jmp     loc_18004B66C
0x18004b2e2  mov     rdi, [rbp+var_30]
0x18004b2e6  lea     rcx, [rbp+var_38]
0x18004b2ea  mov     rax, [rdi]
0x18004b2ed  mov     rbx, [rax]
0x18004b2f0  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18004b2f5  lea     r8, [rbp+var_38]
0x18004b2f9  mov     rcx, rdi
0x18004b2fc  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x18004b303  mov     rax, rbx
0x18004b306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b30b  mov     edi, eax
0x18004b30d  test    eax, eax
0x18004b30f  jns     short loc_18004B328
0x18004b311  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b318  jb      loc_18004B68A
0x18004b31e  mov     edx, 80h
0x18004b323  jmp     loc_18004B66C
0x18004b328  test    r14, r14
0x18004b32b  jnz     loc_18004B574
0x18004b331  mov     rax, [r15]
0x18004b334  lea     r8, [rbp+var_48]
0x18004b338  lea     rdx, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8
0x18004b33f  mov     [rbp+pv], r14
0x18004b343  mov     rcx, r15
0x18004b346  mov     [rbp+arg_0], r14d
0x18004b34a  mov     [rbp+var_50], r14
0x18004b34e  mov     rax, [rax]
0x18004b351  mov     [rbp+var_48], r14
0x18004b355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b35a  mov     edi, eax
0x18004b35c  test    eax, eax
0x18004b35e  jns     short loc_18004B3B6
0x18004b360  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b367  jb      short loc_18004B38C
0x18004b369  mov     edx, 81h
0x18004b36e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b375  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004b37c  xor     r9d, r9d
0x18004b37f  mov     dword ptr [rsp+80h+var_60], eax
0x18004b383  mov     rcx, [rcx+10h]
0x18004b387  call    WPP_SF_qD
0x18004b38c  lea     rcx, [rbp+var_48]
0x18004b390  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b395  lea     rcx, [rbp+var_50]
0x18004b399  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b39e  mov     rcx, [rbp+pv]; pv
0x18004b3a2  test    rcx, rcx
0x18004b3a5  jz      loc_18004B68A
0x18004b3ab  call    cs:__imp_CoTaskMemFree
0x18004b3b1  jmp     loc_18004B68A
0x18004b3b6  mov     rdi, [rbp+var_48]
0x18004b3ba  lea     rcx, [rbp+var_50]
0x18004b3be  mov     rax, [rdi]
0x18004b3c1  mov     rbx, [rax+68h]
0x18004b3c5  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x18004b3ca  lea     rdx, [rbp+var_50]
0x18004b3ce  mov     rcx, rdi
0x18004b3d1  mov     rax, rbx
0x18004b3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b3d9  mov     edi, eax
0x18004b3db  test    eax, eax
0x18004b3dd  jns     short loc_18004B3F2
0x18004b3df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b3e6  jb      short loc_18004B38C
0x18004b3e8  mov     edx, 82h
0x18004b3ed  jmp     loc_18004B36E
0x18004b3f2  mov     rcx, [rbp+var_50]
0x18004b3f6  lea     rdx, [rbp+pv]
0x18004b3fa  lea     r9, [rbp+arg_0]
0x18004b3fe  lea     r8, [rbp+var_18]
0x18004b402  mov     rax, [rcx]
0x18004b405  mov     [rbp+var_20], rdx
0x18004b409  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x18004b410  mov     [rbp+var_18], r14
0x18004b414  mov     [rbp+var_10], 1
0x18004b418  mov     rax, [rax+68h]
0x18004b41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b421  lea     rcx, [rbp+var_20]
0x18004b425  mov     edi, eax
0x18004b427  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18004b42c  mov     eax, edi
0x18004b42e  shr     eax, 1Fh
0x18004b431  test    al, al
0x18004b433  jz      loc_18004B4F3
0x18004b439  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b440  jb      short loc_18004B465
0x18004b442  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b449  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004b450  mov     edx, 83h
0x18004b455  mov     dword ptr [rsp+80h+var_60], edi
0x18004b459  xor     r9d, r9d
0x18004b45c  mov     rcx, [rcx+10h]
0x18004b460  call    WPP_SF_qD
0x18004b465  lea     rcx, [rbp+var_48]
0x18004b469  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b46e  lea     rcx, [rbp+var_50]
0x18004b472  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b477  mov     rcx, [rbp+pv]; pv
0x18004b47b  test    rcx, rcx
0x18004b47e  jz      short loc_18004B486
0x18004b480  call    cs:__imp_CoTaskMemFree
0x18004b486  test    edi, edi
0x18004b488  js      loc_18004B68A
0x18004b48e  cmp     cs:byte_18008D62D, 8
0x18004b495  jb      short loc_18004B4B9
0x18004b497  mov     edx, 8Ch
0x18004b49c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b4a3  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004b4aa  mov     r9d, edi
0x18004b4ad  mov     rcx, [rcx+0D8h]
0x18004b4b4  call    WPP_SF_d
0x18004b4b9  lea     rcx, [rbp+var_38]
0x18004b4bd  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b4c2  lea     rcx, [rbp+var_30]
0x18004b4c6  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b4cb  lea     rcx, [rbp+var_28]
0x18004b4cf  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b4d4  lea     r11, [rsp+80h+var_s0]
0x18004b4dc  mov     eax, edi
0x18004b4de  mov     rbx, [r11+38h]
0x18004b4e2  mov     rdi, [r11+40h]
0x18004b4e6  mov     rsp, r11
0x18004b4e9  pop     r15
0x18004b4eb  pop     r14
0x18004b4ed  pop     r13
0x18004b4ef  pop     r12
0x18004b4f1  pop     rbp
0x18004b4f2  retn
0x18004b4f3  mov     rcx, [rbp+var_38]
0x18004b4f7  mov     rdx, [rbp+pv]
0x18004b4fb  mov     rax, [rcx]
0x18004b4fe  mov     rax, [rax+40h]
0x18004b502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b507  mov     edi, eax
0x18004b509  test    eax, eax
0x18004b50b  jns     short loc_18004B524
0x18004b50d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b514  jb      loc_18004B38C
0x18004b51a  mov     edx, 84h
0x18004b51f  jmp     loc_18004B36E
0x18004b524  lea     rcx, [rbp+var_48]
0x18004b528  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b52d  lea     rcx, [rbp+var_50]
0x18004b531  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004b536  mov     rcx, [rbp+pv]; pv
0x18004b53a  test    rcx, rcx
0x18004b53d  jz      short loc_18004B545
0x18004b53f  call    cs:__imp_CoTaskMemFree
0x18004b545  mov     rcx, [rbp+var_38]
0x18004b549  xor     edx, edx
0x18004b54b  mov     rax, [rcx]
0x18004b54e  mov     rax, [rax+48h]
0x18004b552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b557  mov     edi, eax
0x18004b559  test    eax, eax
0x18004b55b  jns     short loc_18004B5A7
0x18004b55d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b564  jb      loc_18004B68A
0x18004b56a  mov     edx, 86h
0x18004b56f  jmp     loc_18004B66C
0x18004b574  mov     rcx, [rbp+var_38]
0x18004b578  mov     rdx, r14
0x18004b57b  mov     rax, [rcx]
0x18004b57e  mov     rax, [rax+40h]
0x18004b582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b587  xor     r14d, r14d
0x18004b58a  mov     edi, eax
0x18004b58c  test    eax, eax
0x18004b58e  jns     short loc_18004B545
0x18004b590  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b597  jb      loc_18004B68A
0x18004b59d  mov     edx, 85h
0x18004b5a2  jmp     loc_18004B66C
0x18004b5a7  mov     ecx, 198h; Size
0x18004b5ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b5b1  test    rax, rax
0x18004b5b4  jz      short loc_18004B5C2
0x18004b5b6  xor     edx, edx; struct IMFSensorGroupPlugin *
0x18004b5b8  mov     rcx, rax; this
0x18004b5bb  call    ??0SensorGroup@@IEAA@PEAUIMFSensorGroupPlugin@@@Z; SensorGroup::SensorGroup(IMFSensorGroupPlugin *)
0x18004b5c0  jmp     short loc_18004B5C5
0x18004b5c2  mov     rax, r14
0x18004b5c5  mov     rdx, rax
0x18004b5c8  lea     rcx, [rbp+var_28]
0x18004b5cc  call    ?attach@?$com_ptr_t@VFSConfiguration@@Uerr_returncode_policy@wil@@@wil@@QEAAXPEAVFSConfiguration@@@Z; wil::com_ptr_t<FSConfiguration,wil::err_returncode_policy>::attach(FSConfiguration *)
0x18004b5d1  mov     rbx, [rbp+var_28]
0x18004b5d5  test    rbx, rbx
0x18004b5d8  jnz     short loc_18004B5F6
0x18004b5da  mov     edi, 8007000Eh
0x18004b5df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b5e6  jb      loc_18004B68A
0x18004b5ec  mov     edx, 87h
0x18004b5f1  jmp     loc_18004B247
0x18004b5f6  mov     rcx, rbx; this
0x18004b5f9  call    ?InternalInitialize@SensorGroup@@IEAAJXZ; SensorGroup::InternalInitialize(void)
0x18004b5fe  mov     edi, eax
0x18004b600  test    eax, eax
0x18004b602  jns     short loc_18004B614
0x18004b604  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b60b  jb      short loc_18004B68A
0x18004b60d  mov     edx, 88h
0x18004b612  jmp     short loc_18004B66C
0x18004b614  mov     rdx, [rbp+var_30]; struct IMFSensorGroupId *
0x18004b618  mov     r9, r13; struct IUnknown *
0x18004b61b  mov     r8, r15; struct IMFMediaSource *
0x18004b61e  mov     rcx, rbx; this
0x18004b621  call    ?InitializeForPublishWithMediaSource@SensorGroup@@IEAAJPEAUIMFSensorGroupId@@PEAUIMFMediaSource@@PEAUIUnknown@@@Z; SensorGroup::InitializeForPublishWithMediaSource(IMFSensorGroupId *,IMFMediaSource *,IUnknown *)
0x18004b626  mov     edi, eax
0x18004b628  test    eax, eax
0x18004b62a  jns     short loc_18004B63C
0x18004b62c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b633  jb      short loc_18004B68A
0x18004b635  mov     edx, 89h
0x18004b63a  jmp     short loc_18004B66C
0x18004b63c  mov     rax, [rbx]
0x18004b63f  lea     rdx, _GUID_4110243a_9757_461f_89f1_f22345bcab4e
0x18004b646  mov     r8, r12
0x18004b649  mov     rcx, rbx
0x18004b64c  mov     rax, [rax]
0x18004b64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b654  mov     edi, eax
0x18004b656  test    eax, eax
0x18004b658  jns     loc_18004B48E
0x18004b65e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b665  jb      short loc_18004B68A
0x18004b667  mov     edx, 8Ah
0x18004b66c  mov     dword ptr [rsp+80h+var_60], eax
0x18004b670  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b677  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004b67e  xor     r9d, r9d
0x18004b681  mov     rcx, [rcx+10h]
0x18004b685  call    WPP_SF_qD
0x18004b68a  cmp     cs:byte_18008D62D, 1
0x18004b691  jb      loc_18004B4B9
0x18004b697  mov     edx, 8Bh
0x18004b69c  jmp     loc_18004B49C
```

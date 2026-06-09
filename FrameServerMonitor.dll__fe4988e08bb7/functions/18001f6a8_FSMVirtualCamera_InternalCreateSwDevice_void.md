# FSMVirtualCamera::InternalCreateSwDevice(void * *)

- ea: `0x18001f6a8`
- end: `0x18001fb25`
- name: `?InternalCreateSwDevice@FSMVirtualCamera@@IEAAJPEAPEAX@Z`
- size: `1149`
- prototype: `int(FSMVirtualCamera *__hidden this, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024850`
- `0x180024b00`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180006a14`
- `0x180006a98`
- `0x18001ea4c`
- `0x18001ebb8`
- `0x18001f6a8`
- `0x1800255a0`
- `0x18002da24`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f9f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fa05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f9f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fa05`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001fa29`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001fa29`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18001f9c3`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18001f9c3`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::InternalCreateSwDevice(FSMVirtualCamera *this, void **a2)
{
  signed int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // rdx
  int v7; // eax
  int v8; // eax
  struct FSMVirtualCameraInfo *v9; // r15
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  HANDLE CurrentProcess; // rax
  void *v16; // rdi
  void *v17; // rbx
  HANDLE v18; // rax
  signed int LastError; // eax
  __int64 v20; // rdx
  struct FSMVirtualCameraInfo *v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  char *v25; // [rsp+58h] [rbp-A8h]
  const wchar_t *v26; // [rsp+60h] [rbp-A0h]
  const wchar_t *v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+78h] [rbp-88h]
  const wchar_t *v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+B0h] [rbp-50h]
  int v35; // [rsp+B4h] [rbp-4Ch]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  int v37; // [rsp+C0h] [rbp-40h]
  int v38; // [rsp+C4h] [rbp-3Ch]
  char *v39; // [rsp+C8h] [rbp-38h]
  __int128 v40; // [rsp+D0h] [rbp-30h]
  int v41; // [rsp+E0h] [rbp-20h]
  int v42; // [rsp+E4h] [rbp-1Ch]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  int v44; // [rsp+F0h] [rbp-10h]
  int v45; // [rsp+F4h] [rbp-Ch]
  __int64 v46; // [rsp+F8h] [rbp-8h]

  v23 = 0;
  memset_0(&v24, 0, 0x48u);
  v22 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      243,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      this,
      *((_DWORD *)this + 39));
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_46;
    v5 = 244;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v4);
    goto LABEL_46;
  }
  *a2 = 0;
  if ( !*((_WORD *)this + 96) )
  {
    v4 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_46;
    v6 = 245;
    goto LABEL_11;
  }
  v7 = *((_DWORD *)this + 114);
  if ( *((_QWORD *)this + 56) )
  {
    if ( v7 )
      goto LABEL_14;
LABEL_18:
    v4 = -1072875845;
    if ( !g_wppLevels )
      goto LABEL_46;
    v5 = 246;
    goto LABEL_6;
  }
  if ( v7 )
    goto LABEL_18;
LABEL_14:
  if ( !*((_QWORD *)this + 66) )
  {
    v4 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_46;
    v6 = 247;
LABEL_11:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      this,
      -1072875850);
    goto LABEL_46;
  }
  v8 = FSMVirtualCameraInfo::CreateInstance(&v22);
  v4 = v8;
  if ( v8 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v8);
    v9 = v22;
    goto LABEL_43;
  }
  v9 = v22;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)v22 + 16);
  v4 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v11 = 249;
LABEL_27:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      this,
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
    goto LABEL_43;
  }
  v12 = *((_QWORD *)v9 + 1);
  *((_QWORD *)v9 + 1) = this;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 5) + 8LL))((char *)this + 40);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 + 40) + 16LL))(v12 + 40);
  v24 = 72;
  v39 = (char *)this + 136;
  v13 = *((_QWORD *)this + 56);
  v25 = (char *)this + 192;
  v26 = L"VCAMDEVAPI\\VCAMERA";
  v27 = L"VCAMERA";
  v30 = L"Windows Virtual Camera Device";
  v32 = *((_QWORD *)this + 76);
  v34 = 3;
  v28 = 0;
  v29 = 6;
  v31 = 0;
  v33 = DEVPKEY_Device_FSM_VirtualCamera_Data;
  v35 = 0;
  v36 = 0;
  v37 = 4099;
  v38 = 200;
  if ( v13 )
  {
    v41 = 100;
    v14 = *((_DWORD *)this + 114);
    v40 = DEVPKEY_Device_RestrictedSD;
    v42 = 0;
    v43 = 0;
    v44 = 19;
    v45 = v14;
    v46 = v13;
  }
  wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::reset(
    &v23,
    0);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = SwDeviceCreate(L"VCAMDEVAPI", L"HTREE\\ROOT\\0", &v24, (unsigned int)(*((_QWORD *)this + 56) != 0) + 1, &v33, FSMVirtualCamera::SWDeviceCreateCallback, v9, &v23);
  v4 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    *((_DWORD *)this + 39) = 2;
    *((_DWORD *)this + 35) = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( !g_wppLevels )
      goto LABEL_43;
    v11 = 250;
    goto LABEL_27;
  }
  CurrentProcess = GetCurrentProcess();
  v16 = (void *)*((_QWORD *)v9 + 2);
  v17 = CurrentProcess;
  v18 = GetCurrentProcess();
  if ( DuplicateHandle(v18, v16, v17, a2, 0, 0, 2u) )
    goto LABEL_42;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_42:
    v22 = (struct FSMVirtualCameraInfo *)*((_QWORD *)this + 73);
    *((_QWORD *)this + 73) = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>::operator=(
      (char *)this + 584,
      &v23);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>::operator=(
      &v23,
      &v22);
    wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>(&v22);
    v9 = 0;
  }
  else if ( g_wppLevels )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v4);
  }
LABEL_43:
  if ( v9 )
    (*(void (__fastcall **)(struct FSMVirtualCameraInfo *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v4 < 0 )
  {
LABEL_46:
    if ( byte_18005E5A5 )
    {
      v20 = 252;
LABEL_50:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v20, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v4);
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v20 = 253;
    goto LABEL_50;
  }
LABEL_51:
  wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>(&v23);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f6a8  mov     [rsp-8+arg_10], rbx
0x18001f6ad  push    rbp
0x18001f6ae  push    rsi
0x18001f6af  push    rdi
0x18001f6b0  push    r12
0x18001f6b2  push    r13
0x18001f6b4  push    r14
0x18001f6b6  push    r15
0x18001f6b8  lea     rbp, [rsp-10h]
0x18001f6bd  sub     rsp, 110h
0x18001f6c4  mov     rax, cs:__security_cookie
0x18001f6cb  xor     rax, rsp
0x18001f6ce  mov     [rbp+40h+var_40], rax
0x18001f6d2  xor     r13d, r13d
0x18001f6d5  mov     r12, rdx
0x18001f6d8  mov     r14, rcx
0x18001f6db  mov     [rsp+140h+var_F8], r13
0x18001f6e0  xor     edx, edx; Val
0x18001f6e2  lea     rcx, [rsp+140h+var_F0]; void *
0x18001f6e7  lea     r8d, [r13+48h]; Size
0x18001f6eb  call    memset_0
0x18001f6f0  mov     [rsp+140h+var_100], r13
0x18001f6f5  cmp     cs:byte_18005E5A5, 8
0x18001f6fc  jb      short loc_18001F72B
0x18001f6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f705  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001f70c  mov     eax, [r14+9Ch]
0x18001f713  mov     edx, 0F3h
0x18001f718  mov     r9, r14
0x18001f71b  mov     [rsp+140h+dwDesiredAccess], eax
0x18001f71f  mov     rcx, [rcx+0D8h]
0x18001f726  call    WPP_SF_qD
0x18001f72b  test    r12, r12
0x18001f72e  jnz     short loc_18001F76A
0x18001f730  mov     esi, 80004003h
0x18001f735  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f73c  jb      loc_18001FAB3
0x18001f742  mov     edx, 0F4h
0x18001f747  mov     [rsp+140h+dwDesiredAccess], esi
0x18001f74b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f752  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001f759  mov     r9, r14
0x18001f75c  mov     rcx, [rcx+10h]
0x18001f760  call    WPP_SF_qD
0x18001f765  jmp     loc_18001FAB3
0x18001f76a  mov     [r12], r13
0x18001f76e  cmp     [r14+0C0h], r13w
0x18001f776  jnz     short loc_18001F797
0x18001f778  mov     eax, 0C00D36B6h
0x18001f77d  mov     esi, eax
0x18001f77f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f786  jb      loc_18001FAB3
0x18001f78c  mov     edx, 0F5h
0x18001f791  mov     [rsp+140h+dwDesiredAccess], eax
0x18001f795  jmp     short loc_18001F74B
0x18001f797  mov     eax, [r14+1C8h]
0x18001f79e  cmp     [r14+1C0h], r13
0x18001f7a5  jz      short loc_18001F7CF
0x18001f7a7  test    eax, eax
0x18001f7a9  jz      short loc_18001F7D3
0x18001f7ab  cmp     [r14+210h], r13
0x18001f7b2  jnz     short loc_18001F7EF
0x18001f7b4  mov     eax, 0C00D36B6h
0x18001f7b9  mov     esi, eax
0x18001f7bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f7c2  jb      loc_18001FAB3
0x18001f7c8  mov     edx, 0F7h
0x18001f7cd  jmp     short loc_18001F791
0x18001f7cf  test    eax, eax
0x18001f7d1  jz      short loc_18001F7AB
0x18001f7d3  mov     esi, 0C00D36BBh
0x18001f7d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f7df  jb      loc_18001FAB3
0x18001f7e5  mov     edx, 0F6h
0x18001f7ea  jmp     loc_18001F747
0x18001f7ef  lea     rcx, [rsp+140h+var_100]; struct FSMVirtualCameraInfo **
0x18001f7f4  call    ?CreateInstance@FSMVirtualCameraInfo@@SAJPEAPEAV1@@Z; FSMVirtualCameraInfo::CreateInstance(FSMVirtualCameraInfo * *)
0x18001f7f9  mov     esi, eax
0x18001f7fb  test    eax, eax
0x18001f7fd  jns     short loc_18001F835
0x18001f7ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f806  jb      short loc_18001F82B
0x18001f808  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f80f  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001f816  mov     edx, 0F8h
0x18001f81b  mov     [rsp+140h+dwDesiredAccess], eax
0x18001f81f  mov     r9, r14
0x18001f822  mov     rcx, [rcx+10h]
0x18001f826  call    WPP_SF_qD
0x18001f82b  mov     r15, [rsp+140h+var_100]
0x18001f830  jmp     loc_18001FA9B
0x18001f835  mov     r15, [rsp+140h+var_100]
0x18001f83a  lea     rcx, [r15+10h]
0x18001f83e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001f843  mov     esi, eax
0x18001f845  test    eax, eax
0x18001f847  jns     short loc_18001F87E
0x18001f849  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f850  jb      loc_18001FA9B
0x18001f856  mov     edx, 0F9h
0x18001f85b  mov     [rsp+140h+dwDesiredAccess], eax
0x18001f85f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f866  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001f86d  mov     r9, r14
0x18001f870  mov     rcx, [rcx+10h]
0x18001f874  call    WPP_SF_qD
0x18001f879  jmp     loc_18001FA9B
0x18001f87e  mov     rbx, [r15+8]
0x18001f882  lea     rcx, [r14+28h]
0x18001f886  mov     [r15+8], r14
0x18001f88a  mov     rax, [rcx]
0x18001f88d  mov     rax, [rax+8]
0x18001f891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f896  test    rbx, rbx
0x18001f899  jz      short loc_18001F8AB
0x18001f89b  lea     rcx, [rbx+28h]
0x18001f89f  mov     rax, [rcx]
0x18001f8a2  mov     rax, [rax+10h]
0x18001f8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8ab  movups  xmm0, cs:DEVPKEY_Device_FSM_VirtualCamera_Data
0x18001f8b2  lea     rcx, [r14+88h]
0x18001f8b9  mov     [rsp+140h+var_F0], 48h ; 'H'
0x18001f8c1  lea     rax, [rcx+38h]
0x18001f8c5  mov     [rbp+40h+var_78], rcx
0x18001f8c9  mov     rcx, [r14+1C0h]
0x18001f8d0  mov     [rsp+140h+var_E8], rax
0x18001f8d5  lea     rax, aVcamdevapiVcam; "VCAMDEVAPI\\VCAMERA"
0x18001f8dc  mov     [rsp+140h+var_E0], rax
0x18001f8e1  lea     rax, aVcamera; "VCAMERA"
0x18001f8e8  mov     [rsp+140h+var_D8], rax
0x18001f8ed  lea     rax, aWindowsVirtual; "Windows Virtual Camera Device"
0x18001f8f4  mov     [rbp+40h+var_C0], rax
0x18001f8f8  mov     rax, [r14+260h]
0x18001f8ff  mov     [rbp+40h+var_B0], rax
0x18001f903  mov     eax, cs:dword_180052228
0x18001f909  mov     [rbp+40h+var_90], eax
0x18001f90c  mov     [rsp+140h+var_D0], r13
0x18001f911  mov     [rsp+140h+var_C8], 6
0x18001f919  mov     [rbp+40h+var_B8], r13
0x18001f91d  movaps  [rbp+40h+var_A0], xmm0
0x18001f921  mov     [rbp+40h+var_8C], r13d
0x18001f925  mov     [rbp+40h+var_88], r13
0x18001f929  mov     [rbp+40h+var_80], 1003h
0x18001f930  mov     [rbp+40h+var_7C], 0C8h
0x18001f937  test    rcx, rcx
0x18001f93a  jz      short loc_18001F96D
0x18001f93c  mov     eax, cs:dword_180052168
0x18001f942  movups  xmm0, cs:DEVPKEY_Device_RestrictedSD
0x18001f949  mov     [rbp+40h+var_60], eax
0x18001f94c  mov     eax, [r14+1C8h]
0x18001f953  movaps  [rbp+40h+var_70], xmm0
0x18001f957  mov     [rbp+40h+var_5C], r13d
0x18001f95b  mov     [rbp+40h+var_58], r13
0x18001f95f  mov     [rbp+40h+var_50], 13h
0x18001f966  mov     [rbp+40h+var_4C], eax
0x18001f969  mov     [rbp+40h+var_48], rcx
0x18001f96d  xor     edx, edx
0x18001f96f  lea     rcx, [rsp+140h+var_F8]
0x18001f974  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSWDEVICE__@@P6AXPEAU1@@Z$1?SwDeviceClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSWDEVICE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::reset(HSWDEVICE__ *)
0x18001f979  mov     rax, [r14+1C0h]
0x18001f980  lea     r8, [rsp+140h+var_F0]
0x18001f985  neg     rax
0x18001f988  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18001f98f  lea     rax, [rsp+140h+var_F8]
0x18001f994  mov     [rsp+140h+var_108], rax
0x18001f999  lea     rcx, aVcamdevapi; "VCAMDEVAPI"
0x18001f9a0  sbb     r9d, r9d
0x18001f9a3  mov     qword ptr [rsp+140h+dwOptions], r15
0x18001f9a8  lea     rax, ?SWDeviceCreateCallback@FSMVirtualCamera@@KAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; FSMVirtualCamera::SWDeviceCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18001f9af  neg     r9d
0x18001f9b2  mov     qword ptr [rsp+140h+bInheritHandle], rax
0x18001f9b7  inc     r9d
0x18001f9ba  lea     rax, [rbp+40h+var_A0]
0x18001f9be  mov     qword ptr [rsp+140h+dwDesiredAccess], rax
0x18001f9c3  call    cs:__imp_SwDeviceCreate
0x18001f9c9  mov     esi, eax
0x18001f9cb  test    eax, eax
0x18001f9cd  jns     short loc_18001F9F8
0x18001f9cf  mov     dword ptr [r14+9Ch], 2
0x18001f9da  mov     [r14+8Ch], eax
0x18001f9e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f9e8  jb      loc_18001FA9B
0x18001f9ee  mov     edx, 0FAh
0x18001f9f3  jmp     loc_18001F85B
0x18001f9f8  call    cs:__imp_GetCurrentProcess
0x18001f9fe  mov     rdi, [r15+10h]
0x18001fa02  mov     rbx, rax
0x18001fa05  call    cs:__imp_GetCurrentProcess
0x18001fa0b  mov     [rsp+140h+dwOptions], 2; dwOptions
0x18001fa13  mov     r9, r12; lpTargetHandle
0x18001fa16  mov     rcx, rax; hSourceProcessHandle
0x18001fa19  mov     [rsp+140h+bInheritHandle], r13d; bInheritHandle
0x18001fa1e  mov     r8, rbx; hTargetProcessHandle
0x18001fa21  mov     [rsp+140h+dwDesiredAccess], r13d; dwDesiredAccess
0x18001fa26  mov     rdx, rdi; hSourceHandle
0x18001fa29  call    cs:__imp_DuplicateHandle
0x18001fa2f  test    eax, eax
0x18001fa31  jnz     short loc_18001FA63
0x18001fa33  call    cs:__imp_GetLastError
0x18001fa39  mov     esi, eax
0x18001fa3b  test    eax, eax
0x18001fa3d  jle     short loc_18001FA48
0x18001fa3f  movzx   esi, ax
0x18001fa42  or      esi, 80070000h
0x18001fa48  test    esi, esi
0x18001fa4a  jns     short loc_18001FA63
0x18001fa4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fa53  jb      short loc_18001FA9B
0x18001fa55  mov     edx, 0FBh
0x18001fa5a  mov     [rsp+140h+dwDesiredAccess], esi
0x18001fa5e  jmp     loc_18001F85F
0x18001fa63  lea     rcx, [r14+248h]
0x18001fa6a  mov     rax, [rcx]
0x18001fa6d  lea     rdx, [rsp+140h+var_F8]
0x18001fa72  mov     [rsp+140h+var_100], rax
0x18001fa77  mov     [rcx], r13
0x18001fa7a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSWDEVICE__@@P6AXPEAU1@@Z$1?SwDeviceClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>> &&)
0x18001fa7f  lea     rdx, [rsp+140h+var_100]
0x18001fa84  lea     rcx, [rsp+140h+var_F8]
0x18001fa89  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSWDEVICE__@@P6AXPEAU1@@Z$1?SwDeviceClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>> &&)
0x18001fa8e  lea     rcx, [rsp+140h+var_100]
0x18001fa93  call    ??1?$unique_storage@U?$resource_policy@PEAUHSWDEVICE__@@P6AXPEAU1@@Z$1?SwDeviceClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>(void)
0x18001fa98  mov     r15, r13
0x18001fa9b  test    r15, r15
0x18001fa9e  jz      short loc_18001FAAF
0x18001faa0  mov     rax, [r15]
0x18001faa3  mov     rcx, r15
0x18001faa6  mov     rax, [rax+10h]
0x18001faaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faaf  test    esi, esi
0x18001fab1  jns     short loc_18001FAC3
0x18001fab3  cmp     cs:byte_18005E5A5, 1
0x18001faba  jb      short loc_18001FAF2
0x18001fabc  mov     edx, 0FCh
0x18001fac1  jmp     short loc_18001FAD1
0x18001fac3  cmp     cs:byte_18005E5A5, 8
0x18001faca  jb      short loc_18001FAF2
0x18001facc  mov     edx, 0FDh
0x18001fad1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fad8  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001fadf  mov     r9, r14
0x18001fae2  mov     [rsp+140h+dwDesiredAccess], esi
0x18001fae6  mov     rcx, [rcx+0D8h]
0x18001faed  call    WPP_SF_qD
0x18001faf2  lea     rcx, [rsp+140h+var_F8]
0x18001faf7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSWDEVICE__@@P6AXPEAU1@@Z$1?SwDeviceClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>(void)
0x18001fafc  mov     eax, esi
0x18001fafe  mov     rcx, [rbp+40h+var_40]
0x18001fb02  xor     rcx, rsp; StackCookie
0x18001fb05  call    __security_check_cookie
0x18001fb0a  mov     rbx, [rsp+140h+arg_10]
0x18001fb12  add     rsp, 110h
0x18001fb19  pop     r15
0x18001fb1b  pop     r14
0x18001fb1d  pop     r13
0x18001fb1f  pop     r12
0x18001fb21  pop     rdi
0x18001fb22  pop     rsi
0x18001fb23  pop     rbp
0x18001fb24  retn
```

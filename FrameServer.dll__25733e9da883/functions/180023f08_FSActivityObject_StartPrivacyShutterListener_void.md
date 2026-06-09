# FSActivityObject::StartPrivacyShutterListener(void)

- ea: `0x180023f08`
- end: `0x1800241f8`
- name: `?StartPrivacyShutterListener@FSActivityObject@@IEAAJXZ`
- size: `752`
- prototype: `__int64 __fastcall(FSActivityObject *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023704`

## callees

- `0x180008cf0`
- `0x18000943c`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x180017d34`
- `0x180023f08`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x18002404f`
- `MFPlat!MFCreateAsyncResult` at `0x18002404f`
- `MFPlat!MFPutWaitingWorkItem` at `0x180024082`
- `MFPlat!MFPutWaitingWorkItem` at `0x180024082`

## pseudocode

```c
__int64 __fastcall FSActivityObject::StartPrivacyShutterListener(FSActivityObject *this)
{
  __int64 v2; // rcx
  __int64 *v3; // rbx
  __int64 v4; // rax
  __int64 (__fastcall *v5)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rsi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  HANDLE *v9; // rsi
  IMFAsyncResult *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  GUID v14; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+98h] [rbp+38h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+A0h] [rbp+40h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  v18 = 0;
  v15 = 0;
  ppAsyncResult = 0;
  v16 = 0;
  v14 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, &WPP_7bc5bb764cec377de403c44151704250_Traceguids, this);
    v2 = (__int64)v18;
  }
  v3 = (__int64 *)*((_QWORD *)this + 10);
  v4 = *v3;
  v18 = 0;
  v5 = *(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v4 + 56);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v5(v3, &v18);
  v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v16);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (**v18)(v18, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, &v16);
    v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      v9 = (HANDLE *)((char *)this + 184);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 184, 0);
      v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      {
        v10 = ppAsyncResult;
        ppAsyncResult = 0;
        if ( v10 )
          ((void (__fastcall *)(IMFAsyncResult *))v10->lpVtbl->Release)(v10);
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 1, 0, &ppAsyncResult);
        v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
        if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
        {
          event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = MFPutWaitingWorkItem(*v9, 0, ppAsyncResult, (MFWORKITEM_KEY *)this + 24);
          v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
          if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
          {
            v11 = v16;
            *((_QWORD *)this + 14) = *v9;
            v14 = GUID_c6e13370_30ac_11d0_a18c_00a0c9118956;
            v15 = 0x100000008LL;
            *((_DWORD *)this + 26) = 1;
            event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v11 + 40LL))(v11, &v14, 24);
            v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
            if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
            {
              v12 = v16;
              v16 = *((_QWORD *)this + 12);
              *((_QWORD *)this + 12) = v12;
              wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v16);
              *((_BYTE *)this + 200) = 1;
              goto LABEL_34;
            }
            if ( g_wppLevels >= 8u )
            {
              v8 = 36;
              goto LABEL_25;
            }
          }
          else if ( g_wppLevels )
          {
            v8 = 35;
            goto LABEL_25;
          }
        }
        else if ( g_wppLevels )
        {
          v8 = 34;
          goto LABEL_25;
        }
      }
      else if ( g_wppLevels )
      {
        v8 = 33;
        goto LABEL_25;
      }
    }
    else if ( g_wppLevels )
    {
      v8 = 32;
      goto LABEL_25;
    }
  }
  else if ( g_wppLevels )
  {
    v8 = 31;
LABEL_25:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      &WPP_7bc5bb764cec377de403c44151704250_Traceguids,
      this,
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
  }
  if ( v7 != -2147024846 && v7 != -2147023726 && v7 != -2147023728 && v7 != -2147024809 && v7 != -2147467263 )
  {
    if ( byte_18010EC4D )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 38, &WPP_7bc5bb764cec377de403c44151704250_Traceguids, this, v7);
    goto LABEL_36;
  }
LABEL_34:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qdq(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      37,
      &WPP_7bc5bb764cec377de403c44151704250_Traceguids,
      this,
      v7,
      *((_QWORD *)this + 12));
LABEL_36:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppAsyncResult);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v16);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v18);
  return v7;
}

```

## disassembly

```asm
0x180023f08  push    rbp
0x180023f0a  push    rbx
0x180023f0b  push    rsi
0x180023f0c  push    rdi
0x180023f0d  push    r15
0x180023f0f  mov     rbp, rsp
0x180023f12  sub     rsp, 60h
0x180023f16  mov     rdi, rcx
0x180023f19  xorps   xmm0, xmm0
0x180023f1c  xor     ecx, ecx
0x180023f1e  xor     eax, eax
0x180023f20  mov     [rbp+arg_18], rcx
0x180023f24  mov     [rbp+var_10], rax
0x180023f28  mov     [rbp+arg_0], eax
0x180023f2b  mov     [rbp+ppAsyncResult], rax
0x180023f2f  mov     [rbp+arg_8], rcx
0x180023f33  movups  [rbp+var_20], xmm0
0x180023f37  cmp     cs:byte_18010EC4D, 8
0x180023f3e  lea     r15, WPP_7bc5bb764cec377de403c44151704250_Traceguids
0x180023f45  jb      short loc_180023F67
0x180023f47  lea     edx, [rcx+1Eh]
0x180023f4a  mov     r9, rdi
0x180023f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f54  mov     r8, r15
0x180023f57  mov     rcx, [rcx+0D8h]
0x180023f5e  call    WPP_SF_q
0x180023f63  mov     rcx, [rbp+arg_18]
0x180023f67  mov     rbx, [rdi+50h]
0x180023f6b  mov     rax, [rbx]
0x180023f6e  mov     [rbp+arg_18], 0
0x180023f76  mov     rsi, [rax+38h]
0x180023f7a  test    rcx, rcx
0x180023f7d  jz      short loc_180023F8B
0x180023f7f  mov     rax, [rcx]
0x180023f82  mov     rax, [rax+10h]
0x180023f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f8b  lea     rdx, [rbp+arg_18]
0x180023f8f  mov     rcx, rbx
0x180023f92  mov     rax, rsi
0x180023f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f9a  mov     ebx, eax
0x180023f9c  test    eax, eax
0x180023f9e  jns     short loc_180023FB7
0x180023fa0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023fa7  jb      loc_180024127
0x180023fad  mov     edx, 1Fh
0x180023fb2  jmp     loc_18002410D
0x180023fb7  lea     rcx, [rbp+arg_8]
0x180023fbb  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180023fc0  mov     rcx, [rbp+arg_18]
0x180023fc4  lea     r8, [rbp+arg_8]
0x180023fc8  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x180023fcf  mov     rax, [rcx]
0x180023fd2  mov     rax, [rax]
0x180023fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fda  mov     ebx, eax
0x180023fdc  test    eax, eax
0x180023fde  jns     short loc_180023FF7
0x180023fe0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023fe7  jb      loc_180024127
0x180023fed  mov     edx, 20h ; ' '
0x180023ff2  jmp     loc_18002410D
0x180023ff7  lea     rsi, [rdi+0B8h]
0x180023ffe  xor     edx, edx
0x180024000  mov     rcx, rsi
0x180024003  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180024008  mov     ebx, eax
0x18002400a  test    eax, eax
0x18002400c  jns     short loc_180024025
0x18002400e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024015  jb      loc_180024127
0x18002401b  mov     edx, 21h ; '!'
0x180024020  jmp     loc_18002410D
0x180024025  mov     rcx, [rbp+ppAsyncResult]
0x180024029  mov     [rbp+ppAsyncResult], 0
0x180024031  test    rcx, rcx
0x180024034  jz      short loc_180024042
0x180024036  mov     rax, [rcx]
0x180024039  mov     rax, [rax+10h]
0x18002403d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024042  lea     rdx, [rdi+8]; pCallback
0x180024046  xor     r8d, r8d; punkState
0x180024049  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x18002404d  xor     ecx, ecx; punkObject
0x18002404f  call    cs:__imp_MFCreateAsyncResult
0x180024055  mov     ebx, eax
0x180024057  test    eax, eax
0x180024059  jns     short loc_180024072
0x18002405b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024062  jb      loc_180024127
0x180024068  mov     edx, 22h ; '"'
0x18002406d  jmp     loc_18002410D
0x180024072  mov     r8, [rbp+ppAsyncResult]; pResult
0x180024076  lea     r9, [rdi+0C0h]; pKey
0x18002407d  mov     rcx, [rsi]; hEvent
0x180024080  xor     edx, edx; Priority
0x180024082  call    cs:__imp_MFPutWaitingWorkItem
0x180024088  mov     ebx, eax
0x18002408a  test    eax, eax
0x18002408c  jns     short loc_1800240A2
0x18002408e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024095  jb      loc_180024127
0x18002409b  mov     edx, 23h ; '#'
0x1800240a0  jmp     short loc_18002410D
0x1800240a2  movaps  xmm0, xmmword ptr cs:_GUID_c6e13370_30ac_11d0_a18c_00a0c9118956.Data1
0x1800240a9  lea     r9, [rdi+68h]
0x1800240ad  mov     rax, [rsi]
0x1800240b0  lea     rdx, [rbp+arg_0]
0x1800240b4  mov     rcx, [rbp+arg_8]
0x1800240b8  mov     r8d, 18h
0x1800240be  mov     [rdi+70h], rax
0x1800240c2  mov     [rsp+60h+var_38], rdx
0x1800240c7  lea     rdx, [rbp+var_20]
0x1800240cb  movdqu  [rbp+var_20], xmm0
0x1800240d0  mov     dword ptr [rbp+var_10], 8
0x1800240d7  mov     dword ptr [rbp+var_10+4], 1
0x1800240de  mov     dword ptr [r9], 1
0x1800240e5  mov     rax, [rcx]
0x1800240e8  mov     [rsp+60h+var_40], 20h ; ' '
0x1800240f0  mov     rax, [rax+28h]
0x1800240f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240f9  mov     ebx, eax
0x1800240fb  test    eax, eax
0x1800240fd  jns     short loc_18002417C
0x1800240ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180024106  jb      short loc_180024127
0x180024108  mov     edx, 24h ; '$'
0x18002410d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024114  mov     r9, rdi
0x180024117  mov     r8, r15
0x18002411a  mov     [rsp+60h+var_40], eax
0x18002411e  mov     rcx, [rcx+10h]
0x180024122  call    WPP_SF_qD
0x180024127  cmp     ebx, 80070032h
0x18002412d  jz      short loc_18002419C
0x18002412f  cmp     ebx, 80070492h
0x180024135  jz      short loc_18002419C
0x180024137  cmp     ebx, 80070490h
0x18002413d  jz      short loc_18002419C
0x18002413f  cmp     ebx, 80070057h
0x180024145  jz      short loc_18002419C
0x180024147  cmp     ebx, 80004001h
0x18002414d  jz      short loc_18002419C
0x18002414f  cmp     cs:byte_18010EC4D, 1
0x180024156  jb      short loc_1800241D0
0x180024158  mov     rcx, cs:WPP_GLOBAL_Control
0x18002415f  mov     edx, 26h ; '&'
0x180024164  mov     r9, rdi
0x180024167  mov     [rsp+60h+var_40], ebx
0x18002416b  mov     r8, r15
0x18002416e  mov     rcx, [rcx+0D8h]
0x180024175  call    WPP_SF_qD
0x18002417a  jmp     short loc_1800241D0
0x18002417c  mov     rcx, [rdi+60h]
0x180024180  mov     rax, [rbp+arg_8]
0x180024184  mov     [rbp+arg_8], rcx
0x180024188  lea     rcx, [rbp+arg_8]
0x18002418c  mov     [rdi+60h], rax
0x180024190  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180024195  mov     byte ptr [rdi+0C8h], 1
0x18002419c  cmp     cs:byte_18010EC4D, 8
0x1800241a3  jb      short loc_1800241D0
0x1800241a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241ac  mov     edx, 25h ; '%'
0x1800241b1  mov     rax, [rdi+60h]
0x1800241b5  mov     r9, rdi
0x1800241b8  mov     [rsp+60h+var_38], rax
0x1800241bd  mov     r8, r15
0x1800241c0  mov     [rsp+60h+var_40], ebx
0x1800241c4  mov     rcx, [rcx+0D8h]
0x1800241cb  call    WPP_SF_qdq
0x1800241d0  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800241d4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800241d9  lea     rcx, [rbp+arg_8]; void *
0x1800241dd  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800241e2  lea     rcx, [rbp+arg_18]; void *
0x1800241e6  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800241eb  mov     eax, ebx
0x1800241ed  add     rsp, 60h
0x1800241f1  pop     r15
0x1800241f3  pop     rdi
0x1800241f4  pop     rsi
0x1800241f5  pop     rbx
0x1800241f6  pop     rbp
0x1800241f7  retn
```

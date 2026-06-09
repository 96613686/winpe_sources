# CAudioClient::FinishConstruction(AudioClientConstructionParams const *)

- ea: `0x18000f72c`
- end: `0x18000fb08`
- name: `?FinishConstruction@CAudioClient@@QEAAJPEBUAudioClientConstructionParams@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(CAudioClient *__hidden this, const struct AudioClientConstructionParams *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004ab20`
- `0x180071250`
- `0x18007a6ac`
- `0x18007bb60`
- `0x1800a5548`

## callees

- `0x18000f72c`
- `0x180010a90`
- `0x18001550c`
- `0x18002d6ac`
- `0x18004fa8c`
- `0x18005b5c8`
- `0x18007221c`
- `0x180087e80`
- `0x1800952c4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f78c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f885`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f78c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f885`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x18000f986`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x18000f986`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fac1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fac1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioClient::FinishConstruction(CAudioClient *this, const struct AudioClientConstructionParams *a2)
{
  GUID *v4; // rsi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  GUID v8; // xmm0
  void *v9; // rbx
  const wchar_t *v10; // r12
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rsi
  __int64 v13; // r9
  __int64 v14; // rdx
  wchar_t *v16; // r8
  unsigned __int64 v17; // rdx
  wchar_t *v18; // rax
  __int64 v19; // rcx
  wchar_t v20; // r9
  __int64 v21; // r9
  wchar_t *v22; // rcx
  void *v23; // rsi
  __int64 v24; // rsi
  bool v25; // cf
  void *v26; // rdx
  int v27; // [rsp+28h] [rbp-49h]
  struct _GUID v28; // [rsp+38h] [rbp-39h] BYREF
  struct _GUID Buf1; // [rsp+48h] [rbp-29h] BYREF
  __int128 v30; // [rsp+58h] [rbp-19h]
  GUID ActivityId; // [rsp+68h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v30 = *((_OWORD *)this + 33);
  ActivityId = (GUID)*((_OWORD *)this + 33);
  EventActivityIdControl(4u, &ActivityId);
  v28 = GUID_00000000_0000_0000_0000_000000000000;
  if ( *((_DWORD *)a2 + 8) == 2 )
  {
    v6 = -2147024809;
    v13 = 2147942487LL;
    v14 = 132;
    goto LABEL_17;
  }
  Buf1 = *(struct _GUID *)a2;
  v4 = (GUID *)((char *)this + 192);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = ParseAudioClientActivationParams(&Buf1, *((const struct tagPROPVARIANT **)a2 + 2), (struct _GUID *)this + 12, &v28);
  v6 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v14 = 137;
LABEL_45:
    v13 = (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    goto LABEL_17;
  }
  *((struct _GUID *)this + 32) = v28;
  v7 = *(_QWORD *)&v4->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&v4->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v7 = *((_QWORD *)this + 25) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( !v7 )
  {
    if ( !*((_DWORD *)a2 + 8) )
    {
      v8 = DEVINTERFACE_AUDIO_RENDER;
LABEL_8:
      *v4 = v8;
      goto LABEL_9;
    }
    if ( *((_DWORD *)a2 + 8) == 1 )
    {
      v8 = DEVINTERFACE_AUDIO_CAPTURE;
      goto LABEL_8;
    }
  }
LABEL_9:
  *((_DWORD *)this + 52) = *((_DWORD *)a2 + 8);
  if ( !*((_QWORD *)a2 + 3) )
  {
LABEL_38:
    *((_DWORD *)this + 53) = *((_DWORD *)a2 + 9);
    *((_DWORD *)this + 54) = *((_DWORD *)a2 + 10);
    *((_DWORD *)this + 55) = *((_DWORD *)a2 + 11);
    *((_DWORD *)this + 56) = *((_DWORD *)a2 + 12);
    *(_QWORD *)((char *)this + 340) = 0;
    *((_DWORD *)this + 87) = 0;
    *((_DWORD *)this + 90) = 0;
    *((_DWORD *)this + 84) = 0;
    *((_DWORD *)this + 105) = *((_DWORD *)a2 + 13);
    *((_DWORD *)this + 92) = 0;
    *((_QWORD *)this + 22) = *((_QWORD *)a2 + 7);
    *((_DWORD *)this + 209) = *((_DWORD *)a2 + 16);
    *((GUID *)this + 24) = GUID_00000000_0000_0000_0000_000000000000;
    *((GUID *)this + 25) = GUID_00000000_0000_0000_0000_000000000000;
    if ( *((_DWORD *)a2 + 16) != 2 )
    {
LABEL_39:
      v6 = 0;
      goto LABEL_18;
    }
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 872, 1);
    v6 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      wil::details::SetEvent(*((wil::details **)this + 109), v26);
      goto LABEL_39;
    }
    v14 = 180;
    goto LABEL_45;
  }
  v9 = (void *)*((_QWORD *)this + 21);
  if ( v9 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v28);
    CoTaskMemFree(v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v28);
  }
  *((_QWORD *)this + 21) = 0;
  v10 = (const wchar_t *)*((_QWORD *)a2 + 3);
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  v12 = v11 + 1;
  if ( v11 + 1 >= v11 && (*(_QWORD *)&v28.Data1 = 0, is_mul_ok(v12, 2u)) )
  {
    v16 = (wchar_t *)CoTaskMemAlloc(2 * v12);
    *((_QWORD *)this + 21) = v16;
    v6 = v16 == 0 ? 0x8007000E : 0;
    if ( v16 )
    {
      if ( v12 > 0x7FFFFFFF )
        goto LABEL_48;
      if ( v11 < 0x7FFFFFFF )
      {
        if ( !v10 )
        {
          v10 = &pszFormat;
          v11 = 0;
        }
        if ( v12 )
        {
          v17 = v12;
          v18 = v16;
          v19 = 0;
          do
          {
            if ( !v11 )
              break;
            v20 = *v10;
            if ( !*v10 )
              break;
            ++v10;
            *v18++ = v20;
            --v11;
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
            v25 = v12 == v21;
            v24 = v12 - v21;
            if ( !v25 && v24 != 1 )
              StringExHandleFillBehindNullW(&v16[v21], 2 * v24, 0x300u);
          }
        }
        goto LABEL_35;
      }
      if ( v11 != -1 )
LABEL_48:
        *v16 = 0;
LABEL_35:
      v23 = (void *)*((_QWORD *)this + 23);
      if ( v23 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v28);
        CoTaskMemFree(v23);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v28);
      }
      *((_QWORD *)this + 23) = 0;
      mmdDevGetInstanceIdFromMMDeviceId(*((_QWORD *)a2 + 3), (char *)this + 184, v16);
      goto LABEL_38;
    }
  }
  else
  {
    v6 = -2147024362;
  }
  v13 = v6;
  v14 = 157;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
    (const char *)v13,
    v27);
LABEL_18:
  EventActivityIdControl(4u, &ActivityId);
  return v6;
}

```

## disassembly

```asm
0x18000f72c  mov     rax, rsp
0x18000f72f  mov     [rax+18h], rbx
0x18000f733  push    rbp
0x18000f734  push    rsi
0x18000f735  push    rdi
0x18000f736  push    r12
0x18000f738  push    r13
0x18000f73a  push    r14
0x18000f73c  push    r15
0x18000f73e  lea     rbp, [rax-5Fh]
0x18000f742  sub     rsp, 90h
0x18000f749  movaps  xmmword ptr [rax-48h], xmm6
0x18000f74d  mov     rax, cs:__security_cookie
0x18000f754  xor     rax, rsp
0x18000f757  mov     [rbp+57h+var_50], rax
0x18000f75b  mov     r14, rdx
0x18000f75e  mov     rdi, rcx
0x18000f761  movups  xmm0, xmmword ptr [rcx+210h]
0x18000f768  movdqu  [rbp+57h+var_70], xmm0
0x18000f76d  mov     rax, [rcx+210h]
0x18000f774  mov     qword ptr [rbp+57h+ActivityId.Data1], rax
0x18000f778  mov     rax, [rcx+218h]
0x18000f77f  mov     qword ptr [rbp+57h+ActivityId.Data4], rax
0x18000f783  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18000f787  mov     ecx, 4; ControlCode
0x18000f78c  call    cs:__imp_EventActivityIdControl
0x18000f792  nop
0x18000f793  movups  xmm6, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000f79a  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm6
0x18000f79f  cmp     dword ptr [r14+20h], 2
0x18000f7a4  jz      loc_18000FA62
0x18000f7aa  movups  xmm0, xmmword ptr [r14]
0x18000f7ae  movdqu  xmmword ptr [rbp+57h+Buf1.Data1], xmm0
0x18000f7b3  lea     rsi, [rdi+0C0h]
0x18000f7ba  lea     r9, [rbp+57h+var_90]; struct _GUID *
0x18000f7be  mov     r8, rsi; struct _GUID *
0x18000f7c1  mov     rdx, [r14+10h]; struct tagPROPVARIANT *
0x18000f7c5  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000f7c9  call    ?ParseAudioClientActivationParams@@YAJU_GUID@@PEBUtagPROPVARIANT@@PEAU1@2@Z; ParseAudioClientActivationParams(_GUID,tagPROPVARIANT const *,_GUID *,_GUID *)
0x18000f7ce  mov     ebx, eax
0x18000f7d0  xor     r13d, r13d
0x18000f7d3  test    eax, eax
0x18000f7d5  js      loc_18000FA55
0x18000f7db  movaps  xmm0, xmmword ptr [rbp+57h+var_90.Data1]
0x18000f7df  movdqu  xmmword ptr [rdi+200h], xmm0
0x18000f7e7  mov     rax, [rsi]
0x18000f7ea  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000f7f1  jnz     short loc_18000F7FE
0x18000f7f3  mov     rax, [rsi+8]
0x18000f7f7  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18000f7fe  test    rax, rax
0x18000f801  jnz     short loc_18000F818
0x18000f803  cmp     [r14+20h], r13d
0x18000f807  jnz     loc_18000FA19
0x18000f80d  movups  xmm0, xmmword ptr cs:DEVINTERFACE_AUDIO_RENDER.Data1
0x18000f814  movdqu  xmmword ptr [rsi], xmm0
0x18000f818  mov     eax, [r14+20h]
0x18000f81c  mov     [rdi+0D0h], eax
0x18000f822  cmp     [r14+18h], r13
0x18000f826  jz      loc_18000F98C
0x18000f82c  mov     rbx, [rdi+0A8h]
0x18000f833  test    rbx, rbx
0x18000f836  jnz     loc_18000FA74
0x18000f83c  mov     [rdi+0A8h], r13
0x18000f843  mov     r12, [r14+18h]
0x18000f847  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000f84b  inc     r15
0x18000f84e  cmp     [r12+r15*2], r13w
0x18000f853  jnz     short loc_18000F84B
0x18000f855  lea     rsi, [r15+1]
0x18000f859  cmp     rsi, r15
0x18000f85c  jnb     short loc_18000F8B9
0x18000f85e  mov     ebx, 80070216h
0x18000f863  mov     r9d, ebx; char *
0x18000f866  mov     edx, 9Dh; void *
0x18000f86b  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x18000f872  mov     rcx, [rbp+5Fh]; this
0x18000f876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f87b  nop
0x18000f87c  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18000f880  mov     ecx, 4; ControlCode
0x18000f885  call    cs:__imp_EventActivityIdControl
0x18000f88b  mov     eax, ebx
0x18000f88d  mov     rcx, [rbp+57h+var_50]
0x18000f891  xor     rcx, rsp; StackCookie
0x18000f894  call    __security_check_cookie
0x18000f899  lea     r11, [rsp+0C0h+var_30]
0x18000f8a1  mov     rbx, [r11+50h]
0x18000f8a5  movaps  xmm6, xmmword ptr [r11-10h]
0x18000f8aa  mov     rsp, r11
0x18000f8ad  pop     r15
0x18000f8af  pop     r14
0x18000f8b1  pop     r13
0x18000f8b3  pop     r12
0x18000f8b5  pop     rdi
0x18000f8b6  pop     rsi
0x18000f8b7  pop     rbp
0x18000f8b8  retn
0x18000f8b9  mov     qword ptr [rbp+57h+var_90.Data1], r13
0x18000f8bd  mov     eax, 2
0x18000f8c2  mul     rsi
0x18000f8c5  test    rdx, rdx
0x18000f8c8  jnz     short loc_18000F85E
0x18000f8ca  mov     rcx, rax; cb
0x18000f8cd  call    cs:__imp_CoTaskMemAlloc
0x18000f8d3  mov     r8, rax
0x18000f8d6  mov     [rdi+0A8h], rax
0x18000f8dd  mov     rcx, rax
0x18000f8e0  neg     rcx
0x18000f8e3  sbb     ebx, ebx
0x18000f8e5  not     ebx
0x18000f8e7  and     ebx, 8007000Eh
0x18000f8ed  test    rax, rax
0x18000f8f0  jz      loc_18000F863
0x18000f8f6  mov     eax, 7FFFFFFFh
0x18000f8fb  cmp     rsi, rax
0x18000f8fe  ja      loc_18000FA9D
0x18000f904  cmp     r15, rax
0x18000f907  jnb     loc_18000FA94
0x18000f90d  test    r12, r12
0x18000f910  jz      loc_18000FAA6
0x18000f916  test    rsi, rsi
0x18000f919  jz      short loc_18000F969
0x18000f91b  mov     rdx, rsi
0x18000f91e  mov     rax, r8
0x18000f921  mov     rcx, r13
0x18000f924  test    r15, r15
0x18000f927  jz      short loc_18000F94C
0x18000f929  movzx   r9d, word ptr [r12]
0x18000f92e  test    r9w, r9w
0x18000f932  jz      short loc_18000F94C
0x18000f934  add     r12, 2
0x18000f938  mov     [rax], r9w
0x18000f93c  add     rax, 2
0x18000f940  dec     r15
0x18000f943  inc     rcx
0x18000f946  sub     rdx, 1
0x18000f94a  jnz     short loc_18000F924
0x18000f94c  lea     r9, [rcx-1]
0x18000f950  test    rdx, rdx
0x18000f953  cmovnz  r9, rcx
0x18000f957  lea     rcx, [rax-2]
0x18000f95b  cmovnz  rcx, rax
0x18000f95f  mov     [rcx], r13w
0x18000f963  jnz     loc_18000FA30
0x18000f969  lea     rbx, [rdi+0B8h]
0x18000f970  mov     rsi, [rbx]
0x18000f973  test    rsi, rsi
0x18000f976  jnz     loc_18000FAB5
0x18000f97c  mov     [rbx], r13
0x18000f97f  mov     rdx, rbx
0x18000f982  mov     rcx, [r14+18h]
0x18000f986  call    cs:__imp_mmdDevGetInstanceIdFromMMDeviceId
0x18000f98c  mov     eax, [r14+24h]
0x18000f990  mov     [rdi+0D4h], eax
0x18000f996  mov     eax, [r14+28h]
0x18000f99a  mov     [rdi+0D8h], eax
0x18000f9a0  mov     eax, [r14+2Ch]
0x18000f9a4  mov     [rdi+0DCh], eax
0x18000f9aa  mov     eax, [r14+30h]
0x18000f9ae  mov     [rdi+0E0h], eax
0x18000f9b4  mov     [rdi+154h], r13
0x18000f9bb  mov     [rdi+15Ch], r13d
0x18000f9c2  mov     [rdi+168h], r13d
0x18000f9c9  mov     [rdi+150h], r13d
0x18000f9d0  mov     eax, [r14+34h]
0x18000f9d4  mov     [rdi+1A4h], eax
0x18000f9da  mov     [rdi+170h], r13d
0x18000f9e1  mov     rax, [r14+38h]
0x18000f9e5  mov     [rdi+0B0h], rax
0x18000f9ec  mov     eax, [r14+40h]
0x18000f9f0  mov     [rdi+344h], eax
0x18000f9f6  movdqu  xmmword ptr [rdi+180h], xmm6
0x18000f9fe  movdqu  xmmword ptr [rdi+190h], xmm6
0x18000fa06  cmp     dword ptr [r14+40h], 2
0x18000fa0b  jz      loc_18000FAD5
0x18000fa11  mov     ebx, r13d
0x18000fa14  jmp     loc_18000F87C
0x18000fa19  cmp     dword ptr [r14+20h], 1
0x18000fa1e  jnz     loc_18000F818
0x18000fa24  movups  xmm0, xmmword ptr cs:DEVINTERFACE_AUDIO_CAPTURE.Data1
0x18000fa2b  jmp     loc_18000F814
0x18000fa30  sub     rsi, r9
0x18000fa33  cmp     rsi, 1
0x18000fa37  jbe     loc_18000F969
0x18000fa3d  lea     rdx, [rsi+rsi]; cbRemaining
0x18000fa41  lea     rcx, [r8+r9*2]; pszDestEnd
0x18000fa45  mov     r8d, 300h; dwFlags
0x18000fa4b  call    StringExHandleFillBehindNullW
0x18000fa50  jmp     loc_18000F969
0x18000fa55  mov     edx, 89h
0x18000fa5a  mov     r9d, eax
0x18000fa5d  jmp     loc_18000F86B
0x18000fa62  mov     ebx, 80070057h
0x18000fa67  mov     r9d, ebx
0x18000fa6a  mov     edx, 84h
0x18000fa6f  jmp     loc_18000F86B
0x18000fa74  lea     rcx, [rbp+57h+var_90]; this
0x18000fa78  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000fa7d  mov     rcx, rbx; pv
0x18000fa80  call    cs:__imp_CoTaskMemFree
0x18000fa86  lea     rcx, [rbp+57h+var_90]; this
0x18000fa8a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000fa8f  jmp     loc_18000F83C
0x18000fa94  test    rsi, rsi
0x18000fa97  jz      loc_18000F969
0x18000fa9d  mov     [r8], r13w
0x18000faa1  jmp     loc_18000F969
0x18000faa6  lea     r12, pszFormat
0x18000faad  mov     r15, r13
0x18000fab0  jmp     loc_18000F916
0x18000fab5  lea     rcx, [rbp+57h+var_90]; this
0x18000fab9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000fabe  mov     rcx, rsi; pv
0x18000fac1  call    cs:__imp_CoTaskMemFree
0x18000fac7  lea     rcx, [rbp+57h+var_90]; this
0x18000facb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000fad0  jmp     loc_18000F97C
0x18000fad5  mov     edx, 1
0x18000fada  lea     rcx, [rdi+368h]
0x18000fae1  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000fae6  mov     ebx, eax
0x18000fae8  test    eax, eax
0x18000faea  jns     short loc_18000FAF6
0x18000faec  mov     edx, 0B4h
0x18000faf1  jmp     loc_18000FA5A
0x18000faf6  mov     rcx, [rdi+368h]; this
0x18000fafd  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000fb02  jmp     loc_18000FA11
```

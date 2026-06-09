# ShieldProvider::AppAndBrowserShield::GetPhishingSensorsMode(AppAndBrowserControlLevel *,int *,int *,int *,int *,int *,int *,int *)

- ea: `0x18006fcd0`
- end: `0x18006ff78`
- name: `?GetPhishingSensorsMode@AppAndBrowserShield@ShieldProvider@@UEAAJPEAW4AppAndBrowserControlLevel@@PEAH111111@Z`
- size: `680`
- prototype: `int(ShieldProvider::AppAndBrowserShield *__hidden this, enum AppAndBrowserControlLevel *, int *, int *, int *, int *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006ff80`
- `0x18006ff90`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x18006fa90`
- `0x18006fcd0`
- `0x180070b6c`
- `0x180075730`
- `0x1800e1a1c`
- `0x1800e1a88`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe33`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe8d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe9b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe33`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe8d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006fe9b`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AppAndBrowserShield::GetPhishingSensorsMode(
        ShieldProvider::AppAndBrowserShield *this,
        enum AppAndBrowserControlLevel *a2,
        int *a3,
        int *a4,
        struct SC_HANDLE__ **a5,
        int *a6,
        int *a7,
        int *a8,
        int *a9)
{
  int *v9; // rax
  int *v10; // r13
  int *v12; // rdi
  int *v14; // rsi
  struct SC_HANDLE__ **v16; // rdx
  unsigned int v17; // r8d
  const unsigned __int16 *v18; // r9
  int v19; // esi
  PVOID *v20; // rax
  SC_HANDLE v21; // rcx
  SC_HANDLE v22; // rbx
  int v23; // edi
  int PhishingMode; // eax
  ShieldProvider::AppAndBrowserShield *v26; // rcx
  unsigned int v27; // ebx
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  int *v30; // [rsp+20h] [rbp-38h]
  unsigned int v31; // [rsp+20h] [rbp-38h]
  SC_HANDLE hSCObject; // [rsp+A8h] [rbp+50h] BYREF

  v9 = a8;
  v10 = (int *)a5;
  v12 = a6;
  v14 = a7;
  *(_DWORD *)a2 = 2;
  *a3 = 0;
  *a4 = 0;
  *v10 = 0;
  *v12 = 0;
  *v14 = 0;
  *v9 = 0;
  *a9 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl'::`2'::impl) )
    goto LABEL_34;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl'::`2'::impl)
    && !IsActiveSessionCountLimited() )
  {
    return 2147942450LL;
  }
  a5 = 0;
  v19 = CommonUtil::HrOpenSCManager((CommonUtil *)&a5, v16, v17, v18, (const unsigned __int16 *)v30);
  if ( v19 < 0 )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v19);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    v21 = (SC_HANDLE)a5;
    if ( !a5 )
      goto LABEL_22;
    goto LABEL_21;
  }
  hSCObject = 0;
  v22 = (SC_HANDLE)a5;
  v19 = CommonUtil::HrOpenService(
          (CommonUtil *)&hSCObject,
          a5,
          (struct SC_HANDLE__ *)&stru_1800FD090,
          (const unsigned __int16 *)4,
          v31);
  if ( v19 == -2147023836 )
  {
    v23 = 0;
    goto LABEL_27;
  }
  if ( !v19 )
  {
    v23 = 1;
    goto LABEL_27;
  }
  v23 = 0;
  if ( v19 >= 0 )
  {
LABEL_27:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    if ( v22 )
      CloseServiceHandle(v22);
    if ( !v23 )
      return 2147942450LL;
    v12 = a6;
    v14 = a7;
LABEL_34:
    a6 = 0;
    PhishingMode = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&a6);
    v27 = PhishingMode;
    if ( PhishingMode >= 0 )
    {
      PhishingMode = ShieldProvider::AppAndBrowserShield::GetPhishingMode(v26, a2, a3, a4, v10, v12, v14, a8, a9);
      v27 = PhishingMode;
      if ( PhishingMode >= 0 )
      {
        v27 = 0;
        goto LABEL_44;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v29 = 29;
    }
    else
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v29 = 28;
    }
    WPP_SF_d(v28[2], v29, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, (unsigned int)PhishingMode);
LABEL_44:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&a6);
    return v27;
  }
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      134,
      WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
      (unsigned int)v19);
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hSCObject )
  {
    CloseServiceHandle(hSCObject);
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v22 )
    goto LABEL_22;
  v21 = v22;
LABEL_21:
  CloseServiceHandle(v21);
  v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_22:
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
    WPP_SF_d(v20[2], 27, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, (unsigned int)v19);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18006fcd0  push    rbp
0x18006fcd2  push    rbx
0x18006fcd3  push    rsi
0x18006fcd4  push    rdi
0x18006fcd5  push    r12
0x18006fcd7  push    r13
0x18006fcd9  push    r14
0x18006fcdb  push    r15
0x18006fcdd  mov     rbp, rsp
0x18006fce0  sub     rsp, 58h
0x18006fce4  mov     rax, [rbp+arg_38]
0x18006fceb  xor     ebx, ebx
0x18006fced  mov     r13, [rbp+arg_20]
0x18006fcf1  mov     r14, r9
0x18006fcf4  mov     rdi, [rbp+arg_28]
0x18006fcf8  mov     r15, r8
0x18006fcfb  mov     rsi, [rbp+arg_30]
0x18006fcff  mov     r12, rdx
0x18006fd02  mov     dword ptr [rdx], 2
0x18006fd08  mov     [r8], ebx
0x18006fd0b  mov     [r9], ebx
0x18006fd0e  mov     [r13+0], ebx
0x18006fd12  mov     [rdi], ebx
0x18006fd14  mov     [rsi], ebx
0x18006fd16  mov     [rax], ebx
0x18006fd18  mov     rax, [rbp+arg_40]
0x18006fd1f  mov     [rax], ebx
0x18006fd21  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix> `wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl(void)'::`2'::impl
0x18006fd28  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(void)
0x18006fd2d  test    al, al
0x18006fd2f  jz      loc_18006FEB9
0x18006fd35  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix> `wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl(void)'::`2'::impl
0x18006fd3c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(void)
0x18006fd41  test    al, al
0x18006fd43  jz      short loc_18006FD52
0x18006fd45  call    ?IsActiveSessionCountLimited@@YA_NXZ; IsActiveSessionCountLimited(void)
0x18006fd4a  test    al, al
0x18006fd4c  jz      loc_18006FEA7
0x18006fd52  lea     rcx, [rbp+arg_20]; this
0x18006fd56  mov     [rbp+arg_20], rbx
0x18006fd5a  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x18006fd5f  mov     esi, eax
0x18006fd61  test    eax, eax
0x18006fd63  jns     short loc_18006FDAF
0x18006fd65  mov     rax, cs:WPP_GLOBAL_Control
0x18006fd6c  lea     rdi, WPP_GLOBAL_Control
0x18006fd73  cmp     rax, rdi
0x18006fd76  jz      short loc_18006FD9D
0x18006fd78  test    byte ptr [rax+1Ch], 1
0x18006fd7c  jz      short loc_18006FD9D
0x18006fd7e  mov     rcx, [rax+10h]
0x18006fd82  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006fd89  mov     edx, 85h
0x18006fd8e  mov     r9d, esi
0x18006fd91  call    WPP_SF_d
0x18006fd96  mov     rax, cs:WPP_GLOBAL_Control
0x18006fd9d  mov     rcx, [rbp+arg_20]
0x18006fda1  test    rcx, rcx
0x18006fda4  jz      loc_18006FE55
0x18006fdaa  jmp     loc_18006FE48
0x18006fdaf  mov     [rbp+hSCObject], rbx
0x18006fdb3  lea     r8, stru_1800FD090; struct SC_HANDLE__ *
0x18006fdba  mov     rbx, [rbp+arg_20]
0x18006fdbe  lea     rcx, [rbp+hSCObject]; this
0x18006fdc2  mov     rdx, rbx; struct SC_HANDLE__ **
0x18006fdc5  mov     r9d, 4; unsigned __int16 *
0x18006fdcb  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x18006fdd0  mov     esi, eax
0x18006fdd2  cmp     eax, 80070424h
0x18006fdd7  jnz     short loc_18006FDE0
0x18006fdd9  xor     edi, edi
0x18006fddb  jmp     loc_18006FE84
0x18006fde0  test    esi, esi
0x18006fde2  jz      loc_18006FE7F
0x18006fde8  xor     edi, edi
0x18006fdea  test    esi, esi
0x18006fdec  jns     loc_18006FE84
0x18006fdf2  mov     rax, cs:WPP_GLOBAL_Control
0x18006fdf9  lea     rdi, WPP_GLOBAL_Control
0x18006fe00  cmp     rax, rdi
0x18006fe03  jz      short loc_18006FE2A
0x18006fe05  test    byte ptr [rax+1Ch], 1
0x18006fe09  jz      short loc_18006FE2A
0x18006fe0b  mov     rcx, [rax+10h]
0x18006fe0f  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006fe16  mov     edx, 86h
0x18006fe1b  mov     r9d, esi
0x18006fe1e  call    WPP_SF_d
0x18006fe23  mov     rax, cs:WPP_GLOBAL_Control
0x18006fe2a  mov     rcx, [rbp+hSCObject]; hSCObject
0x18006fe2e  test    rcx, rcx
0x18006fe31  jz      short loc_18006FE40
0x18006fe33  call    cs:__imp_CloseServiceHandle
0x18006fe39  mov     rax, cs:WPP_GLOBAL_Control
0x18006fe40  test    rbx, rbx
0x18006fe43  jz      short loc_18006FE55
0x18006fe45  mov     rcx, rbx; hSCObject
0x18006fe48  call    cs:__imp_CloseServiceHandle
0x18006fe4e  mov     rax, cs:WPP_GLOBAL_Control
0x18006fe55  cmp     rax, rdi
0x18006fe58  jz      short loc_18006FE78
0x18006fe5a  test    byte ptr [rax+1Ch], 1
0x18006fe5e  jz      short loc_18006FE78
0x18006fe60  mov     rcx, [rax+10h]
0x18006fe64  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006fe6b  mov     edx, 1Bh
0x18006fe70  mov     r9d, esi
0x18006fe73  call    WPP_SF_d
0x18006fe78  mov     eax, esi
0x18006fe7a  jmp     loc_18006FF67
0x18006fe7f  mov     edi, 1
0x18006fe84  mov     rcx, [rbp+hSCObject]; hSCObject
0x18006fe88  test    rcx, rcx
0x18006fe8b  jz      short loc_18006FE93
0x18006fe8d  call    cs:__imp_CloseServiceHandle
0x18006fe93  test    rbx, rbx
0x18006fe96  jz      short loc_18006FEA1
0x18006fe98  mov     rcx, rbx; hSCObject
0x18006fe9b  call    cs:__imp_CloseServiceHandle
0x18006fea1  xor     ebx, ebx
0x18006fea3  test    edi, edi
0x18006fea5  jnz     short loc_18006FEB1
0x18006fea7  mov     eax, 80070032h
0x18006feac  jmp     loc_18006FF67
0x18006feb1  mov     rdi, [rbp+arg_28]
0x18006feb5  mov     rsi, [rbp+arg_30]
0x18006feb9  lea     rcx, [rbp+arg_28]
0x18006febd  mov     [rbp+arg_28], rbx
0x18006fec1  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x18006fec6  mov     ebx, eax
0x18006fec8  test    eax, eax
0x18006feca  jns     short loc_18006FEEC
0x18006fecc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fed3  lea     rdi, WPP_GLOBAL_Control
0x18006feda  cmp     rcx, rdi
0x18006fedd  jz      short loc_18006FF5C
0x18006fedf  test    byte ptr [rcx+1Ch], 1
0x18006fee3  jz      short loc_18006FF5C
0x18006fee5  mov     edx, 1Ch
0x18006feea  jmp     short loc_18006FF45
0x18006feec  mov     rax, [rbp+arg_40]
0x18006fef3  mov     r9, r14; int *
0x18006fef6  mov     [rsp+58h+var_18], rax; int *
0x18006fefb  mov     r8, r15; int *
0x18006fefe  mov     rax, [rbp+arg_38]
0x18006ff05  mov     rdx, r12; enum AppAndBrowserControlLevel *
0x18006ff08  mov     [rsp+58h+var_20], rax; int *
0x18006ff0d  mov     [rsp+58h+var_28], rsi; int *
0x18006ff12  mov     [rsp+58h+var_30], rdi; int *
0x18006ff17  mov     [rsp+58h+var_38], r13; int *
0x18006ff1c  call    ?GetPhishingMode@AppAndBrowserShield@ShieldProvider@@AEAAJPEAW4AppAndBrowserControlLevel@@PEAH111111@Z; ShieldProvider::AppAndBrowserShield::GetPhishingMode(AppAndBrowserControlLevel *,int *,int *,int *,int *,int *,int *,int *)
0x18006ff21  mov     ebx, eax
0x18006ff23  test    eax, eax
0x18006ff25  jns     short loc_18006FF5A
0x18006ff27  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ff2e  lea     rdi, WPP_GLOBAL_Control
0x18006ff35  cmp     rcx, rdi
0x18006ff38  jz      short loc_18006FF5C
0x18006ff3a  test    byte ptr [rcx+1Ch], 1
0x18006ff3e  jz      short loc_18006FF5C
0x18006ff40  mov     edx, 1Dh
0x18006ff45  mov     rcx, [rcx+10h]
0x18006ff49  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18006ff50  mov     r9d, eax
0x18006ff53  call    WPP_SF_d
0x18006ff58  jmp     short loc_18006FF5C
0x18006ff5a  xor     ebx, ebx
0x18006ff5c  lea     rcx, [rbp+arg_28]
0x18006ff60  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18006ff65  mov     eax, ebx
0x18006ff67  add     rsp, 58h
0x18006ff6b  pop     r15
0x18006ff6d  pop     r14
0x18006ff6f  pop     r13
0x18006ff71  pop     r12
0x18006ff73  pop     rdi
0x18006ff74  pop     rsi
0x18006ff75  pop     rbx
0x18006ff76  pop     rbp
0x18006ff77  retn
```

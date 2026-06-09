# CAudioResourceManager::ReevaluateSaDeviceSettings(CEndpointStore *,bool)

- ea: `0x18001d7b4`
- end: `0x18001df5a`
- name: `?ReevaluateSaDeviceSettings@CAudioResourceManager@@IEAAXPEAVCEndpointStore@@_N@Z`
- size: `1958`
- prototype: `void __fastcall(CAudioResourceManager *__hidden this, struct CEndpointStore *, bool)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e56c0`

## callees

- `0x18000af70`
- `0x180018198`
- `0x18001d69c`
- `0x18001d7b4`
- `0x18001e7dc`
- `0x18001eb4c`
- `0x18003880c`
- `0x18003a080`
- `0x180045068`
- `0x180053400`
- `0x1800b8c20`
- `0x1800beb70`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1800e5960`
- `0x1800e5a18`
- `0x1800ea6ac`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df14`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001da27`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001dc67`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001da27`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001dc67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de4e`
- `ext-ms-win-audiocore-policymanager-l1-1-1!AudioPolicyManagerExtension_OnPostMatchFormatStateChange` at `0x18001dec7`
- `ext-ms-win-audiocore-policymanager-l1-1-1!AudioPolicyManagerExtension_OnPostMatchFormatStateChange` at `0x18001dec7`

## string_xrefs

- `0x18001de17`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18001def9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall CAudioResourceManager::ReevaluateSaDeviceSettings(
        CAudioResourceManager *this,
        struct CEndpointStore *a2,
        char a3)
{
  struct tWAVEFORMATEX *v4; // rsi
  char *v5; // r12
  char *v6; // rdx
  int v7; // ebx
  char *v8; // r9
  char v9; // r14
  char v10; // r15
  int v11; // ebx
  __int64 v12; // r8
  struct tWAVEFORMATEX *v13; // rdi
  _QWORD *i; // rbx
  ULONGLONG v15; // rdx
  __int64 v16; // r15
  __int64 v17; // r14
  __int64 v18; // r14
  ULONGLONG TickCount64; // rax
  struct _GUID v20; // xmm8
  struct _GUID v21; // xmm7
  struct _GUID v22; // xmm6
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v23; // eax
  int v24; // eax
  struct tWAVEFORMATEX *v25; // r14
  __int64 v26; // r15
  struct _GUID v27; // xmm6
  unsigned int v28; // eax
  __int64 v29; // rax
  const struct tWAVEFORMATEX *v30; // rax
  __int64 v31; // r15
  unsigned int v32; // edx
  __int64 v33; // rcx
  int v34; // eax
  char v35; // al
  int v36; // eax
  int *v37; // [rsp+28h] [rbp-E0h]
  char v38; // [rsp+78h] [rbp-90h]
  char v39; // [rsp+79h] [rbp-8Fh]
  SaDeviceParams *v41; // [rsp+80h] [rbp-88h] BYREF
  int v42; // [rsp+88h] [rbp-80h]
  __int64 v43; // [rsp+90h] [rbp-78h] BYREF
  struct _GUID v44; // [rsp+98h] [rbp-70h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-60h]
  struct tWAVEFORMATEX *v46; // [rsp+B8h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-48h] BYREF
  struct tWAVEFORMATEX *v48; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD *v49; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD *v50; // [rsp+D8h] [rbp-30h]
  __int64 v51; // [rsp+E0h] [rbp-28h]
  struct tWAVEFORMATEX *v52; // [rsp+E8h] [rbp-20h] BYREF
  struct tWAVEFORMATEX *v53; // [rsp+F0h] [rbp-18h]
  struct tWAVEFORMATEX *v54; // [rsp+F8h] [rbp-10h]
  int v55[4]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v56; // [rsp+110h] [rbp+8h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+118h] [rbp+10h] BYREF
  struct _GUID v58; // [rsp+128h] [rbp+20h] BYREF
  struct _GUID v59; // [rsp+138h] [rbp+30h] BYREF
  char v60[16]; // [rsp+148h] [rbp+40h] BYREF
  char v61[16]; // [rsp+158h] [rbp+50h] BYREF
  char v62[16]; // [rsp+168h] [rbp+60h] BYREF
  char v63[16]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+210h] [rbp+108h]

  *(_OWORD *)v55 = 0;
  v4 = 0;
  v56 = 0;
  v5 = (char *)a2 + 16;
  if ( *((_QWORD *)a2 + 5) <= 7u )
    v6 = (char *)a2 + 16;
  else
    v6 = *(char **)v5;
  v37 = v55;
  v7 = (*(__int64 (__fastcall **)(PVOID, char *, _QWORD, _QWORD))(*(_QWORD *)g_pEndpointCharacteristicsCache + 40LL))(
         g_pEndpointCharacteristicsCache,
         v6,
         0,
         0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v8 = v5;
    else
      v8 = *(char **)v5;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_eacb2d5fa25a3e5f73f3ddb8cb456386_Traceguids, v8);
  }
  if ( v7 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)a2 + 13) + 128LL))(
      *((_QWORD *)a2 + 13),
      lpCriticalSection);
    v9 = 0;
    v38 = 0;
    v39 = 0;
    while ( 1 )
    {
      v10 = 1;
      std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(&v49);
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(**((_QWORD **)a2 + 13) + 96LL))(*((_QWORD *)a2 + 13), &v49);
      v42 = v11;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v12, v50 - v49);
      }
      if ( v11 < 0 )
        goto LABEL_54;
      v43 = 0;
      v13 = 0;
      v53 = 0;
      v54 = 0;
      for ( i = v49; ; ++i )
      {
        if ( i == v50 )
        {
          v10 = 1;
LABEL_50:
          v11 = v42;
          goto LABEL_51;
        }
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 168LL))(*i)
          || (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 136LL))(*i) )
        {
          v39 = 1;
          continue;
        }
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 152LL))(*i) )
          break;
        LODWORD(v41) = 0;
        v52 = 0;
        v46 = 0;
        v48 = 0;
        pv = 0;
        v20 = *(struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*i + 40LL))(*i, v60);
        v21 = *(struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*i + 40LL))(*i, v61);
        v22 = *(struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*i + 40LL))(*i, v62);
        v23 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*i + 96LL))(*i);
        v58 = v20;
        v59 = v21;
        v44 = v22;
        v24 = DeriveDeviceGraphFormatsForStream(
                (struct EndpointCharacteristicsDescriptor *)v55,
                0,
                v23,
                AUDCLNT_SHAREMODE_SHARED,
                0,
                &v44,
                &v59,
                &v58,
                0,
                &v48,
                (struct tWAVEFORMATEX **)&pv,
                &v46,
                &v52);
        v25 = v52;
        if ( v24 >= 0 )
        {
          v26 = *(_QWORD *)&v55[2];
          v27 = *(struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*i + 40LL))(*i, v63);
          v28 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 96LL))(*i);
          v44 = v27;
          LODWORD(v37) = 0;
          if ( (int)EffectPack::GetSharedModeEnginePeriodicity(v26, v28, v25, &v44) >= 0 )
          {
            v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 32LL))(*i);
            if ( v29 != (int)((double)(int)v41 * 10000000.0 / (double)(int)v25->nSamplesPerSec + 0.5)
              || (v30 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 48LL))(*i),
                  !(unsigned int)CompareWaveFormat(v25, v30)) )
            {
              v31 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 192LL))(*i);
              if ( GetTickCount64() - v31 >= (unsigned int)(g_TimeoutRevertAudioPumpFormatAndPeriodInMs - 16) )
              {
                v10 = 0;
                Microsoft::WRL::ComPtr<ISaDeviceProxy>::operator=(&v43, i);
                v13 = v25;
                CoTaskMemFree(0);
                v53 = v25;
                v4 = v46;
                CoTaskMemFree(0);
                v54 = v4;
                CoTaskMemFree(pv);
                CoTaskMemFree(v48);
                CoTaskMemFree(0);
                CoTaskMemFree(0);
                goto LABEL_45;
              }
            }
          }
        }
        CoTaskMemFree(pv);
        CoTaskMemFree(v48);
        CoTaskMemFree(v46);
        CoTaskMemFree(v25);
LABEL_39:
        ;
      }
      std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(&v44);
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct _GUID *))(**((_QWORD **)a2 + 13) + 120LL))(
             *((_QWORD *)a2 + 13),
             *i,
             &v44) < 0
        || *(_QWORD *)v44.Data4 - *(_QWORD *)&v44.Data1 != 8 )
      {
        goto LABEL_30;
      }
      v41 = 0;
      if ( (*(int (__fastcall **)(_QWORD, SaDeviceParams **))(*(_QWORD *)*i + 120LL))(*i, &v41) < 0 )
        break;
      v16 = **(_QWORD **)&v44.Data1;
      v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 32LL))(*i);
      if ( v17 == (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 128LL))(v16) )
        break;
      v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 192LL))(*i);
      TickCount64 = GetTickCount64();
      v15 = (unsigned int)(g_TimeoutRevertAudioPumpFormatAndPeriodInMs - 16);
      if ( TickCount64 - v18 < v15 )
        break;
      v10 = 0;
      Microsoft::WRL::ComPtr<ISaDeviceProxy>::operator=(&v43, i);
      v13 = (struct tWAVEFORMATEX *)*((_QWORD *)v41 + 2);
      *((_QWORD *)v41 + 2) = 0;
      CoTaskMemFree(0);
      v53 = v13;
      v4 = (struct tWAVEFORMATEX *)*((_QWORD *)v41 + 3);
      *((_QWORD *)v41 + 3) = 0;
      CoTaskMemFree(0);
      v54 = v4;
      (*(void (__fastcall **)(_QWORD))(***(_QWORD ***)&v44.Data1 + 128LL))(**(_QWORD **)&v44.Data1);
      if ( v41 )
        SaDeviceParams::`scalar deleting destructor'(v41, v32);
      v41 = 0;
      if ( *(_QWORD *)&v44.Data1 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(
          *(_QWORD *)&v44.Data1,
          *(_QWORD *)v44.Data4);
        std::_Deallocate<16>(*(_QWORD *)&v44.Data1, (v45 - *(_QWORD *)&v44.Data1) & 0xFFFFFFFFFFFFFFF8uLL);
      }
LABEL_45:
      if ( !v43 )
        goto LABEL_50;
      std::vector<Microsoft::WRL::ComPtr<ISaDeviceProxy>>::clear(&v49);
      LODWORD(v37) = (_DWORD)v4;
      v34 = CAudioResourceManager::SwitchStreamGroupsToNewSaDevice(v33, v55, *((_QWORD *)a2 + 13), v13);
      v11 = v34;
      if ( v34 >= 0 )
      {
        v9 = 1;
        v38 = 1;
        goto LABEL_52;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA9D,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v34,
        (int)v4);
LABEL_51:
      v9 = v38;
LABEL_52:
      CoTaskMemFree(v4);
      CoTaskMemFree(v13);
      v4 = 0;
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
LABEL_54:
      if ( v49 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(v49, v50);
        std::_Deallocate<16>(v49, (v51 - (_QWORD)v49) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      if ( v11 < 0 || v10 )
      {
        v35 = a3;
        if ( a3 && !v39 )
        {
          if ( *((_QWORD *)v5 + 3) > 7u )
            v5 = *(char **)v5;
          AudioPolicyManagerExtension_OnPostMatchFormatStateChange(v5, 0);
          v35 = a3;
        }
        if ( g_UseSoftwareLoopbackOnMatchFormat )
        {
          if ( v35 )
          {
            if ( v9 )
            {
              v36 = CAudioSessionManager::DisconnectAllStreamsOfType(*((_QWORD *)a2 + 12));
              if ( v36 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xAB3,
                  (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
                  (const char *)(unsigned int)v36,
                  (int)v37);
            }
          }
        }
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
        goto LABEL_70;
      }
    }
    if ( v41 )
      SaDeviceParams::`scalar deleting destructor'(v41, v15);
LABEL_30:
    if ( *(_QWORD *)&v44.Data1 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(
        *(_QWORD *)&v44.Data1,
        *(_QWORD *)v44.Data4);
      std::_Deallocate<16>(*(_QWORD *)&v44.Data1, (v45 - *(_QWORD *)&v44.Data1) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    goto LABEL_39;
  }
LABEL_70:
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v55);
}

```

## disassembly

```asm
0x18001d7b4  mov     rax, rsp
0x18001d7b7  push    rbp
0x18001d7b8  push    rbx
0x18001d7b9  push    rsi
0x18001d7ba  push    rdi
0x18001d7bb  push    r12
0x18001d7bd  push    r13
0x18001d7bf  push    r14
0x18001d7c1  push    r15
0x18001d7c3  lea     rbp, [rax-108h]
0x18001d7ca  sub     rsp, 1C8h
0x18001d7d1  movaps  xmmword ptr [rax-58h], xmm6
0x18001d7d5  movaps  xmmword ptr [rax-68h], xmm7
0x18001d7d9  movaps  xmmword ptr [rax-78h], xmm8
0x18001d7de  mov     rax, cs:__security_cookie
0x18001d7e5  xor     rax, rsp
0x18001d7e8  mov     [rbp+100h+var_80], rax
0x18001d7ef  mov     byte ptr [rsp+200h+var_190+2], r8b
0x18001d7f4  mov     r13, rdx
0x18001d7f7  xorps   xmm0, xmm0
0x18001d7fa  movdqu  xmmword ptr [rbp+100h+var_108], xmm0
0x18001d7ff  xor     esi, esi
0x18001d801  mov     [rbp+100h+var_F8], rsi
0x18001d805  lea     r12, [rdx+10h]
0x18001d809  cmp     qword ptr [r12+18h], 7
0x18001d80f  jbe     short loc_18001D817
0x18001d811  mov     rdx, [r12]
0x18001d815  jmp     short loc_18001D81A
0x18001d817  mov     rdx, r12
0x18001d81a  mov     rcx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x18001d821  mov     rax, [rcx]
0x18001d824  lea     r8, [rbp+100h+var_108]
0x18001d828  mov     qword ptr [rsp+200h+var_1E0], r8; int
0x18001d82d  xor     r9d, r9d
0x18001d830  xor     r8d, r8d
0x18001d833  mov     rax, [rax+28h]
0x18001d837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d83c  mov     ebx, eax
0x18001d83e  lea     rdi, WPP_GLOBAL_Control
0x18001d845  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d84c  cmp     rcx, rdi
0x18001d84f  jz      short loc_18001D886
0x18001d851  test    dword ptr [rcx+1Ch], 100h
0x18001d858  jz      short loc_18001D886
0x18001d85a  cmp     byte ptr [rcx+19h], 4
0x18001d85e  jb      short loc_18001D886
0x18001d860  cmp     qword ptr [r12+18h], 7
0x18001d866  jbe     short loc_18001D86E
0x18001d868  mov     r9, [r12]
0x18001d86c  jmp     short loc_18001D871
0x18001d86e  mov     r9, r12
0x18001d871  mov     edx, 16h
0x18001d876  lea     r8, WPP_eacb2d5fa25a3e5f73f3ddb8cb456386_Traceguids
0x18001d87d  mov     rcx, [rcx+10h]
0x18001d881  call    WPP_SF_S
0x18001d886  test    ebx, ebx
0x18001d888  js      loc_18001DF1B
0x18001d88e  mov     rcx, [r13+68h]
0x18001d892  mov     rax, [rcx]
0x18001d895  lea     rdx, [rbp+100h+lpCriticalSection]
0x18001d899  mov     rax, [rax+80h]
0x18001d8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8a5  nop
0x18001d8a6  mov     r14b, sil
0x18001d8a9  mov     byte ptr [rsp+200h+var_190], sil
0x18001d8ae  mov     byte ptr [rsp+200h+var_190+1], sil
0x18001d8b3  mov     r15b, 1
0x18001d8b6  mov     byte ptr [rsp+200h+var_190+3], r15b
0x18001d8bb  lea     rcx, [rbp+100h+var_138]; void *
0x18001d8bf  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x18001d8c4  nop
0x18001d8c5  mov     rcx, [r13+68h]
0x18001d8c9  mov     rax, [rcx]
0x18001d8cc  lea     rdx, [rbp+100h+var_138]
0x18001d8d0  mov     rax, [rax+60h]
0x18001d8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d9  mov     ebx, eax
0x18001d8db  mov     [rbp+100h+var_180], eax
0x18001d8de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8e5  cmp     rcx, rdi
0x18001d8e8  jz      short loc_18001D913
0x18001d8ea  test    dword ptr [rcx+1Ch], 100h
0x18001d8f1  jz      short loc_18001D913
0x18001d8f3  cmp     byte ptr [rcx+19h], 4
0x18001d8f7  jb      short loc_18001D913
0x18001d8f9  mov     r9, [rbp+100h+var_130]
0x18001d8fd  sub     r9, [rbp+100h+var_138]
0x18001d901  sar     r9, 3
0x18001d905  mov     edx, 17h
0x18001d90a  mov     rcx, [rcx+10h]
0x18001d90e  call    WPP_SF_P
0x18001d913  test    ebx, ebx
0x18001d915  js      loc_18001DE74
0x18001d91b  mov     [rbp+100h+var_178], rsi
0x18001d91f  mov     rdi, rsi
0x18001d922  mov     [rbp+100h+var_118], rsi
0x18001d926  mov     [rbp+100h+var_110], rsi
0x18001d92a  mov     rbx, [rbp+100h+var_138]
0x18001d92e  cmp     rbx, [rbp+100h+var_130]
0x18001d932  jz      loc_18001DE34
0x18001d938  mov     rcx, [rbx]
0x18001d93b  mov     rax, [rcx]
0x18001d93e  mov     rax, [rax+0A8h]
0x18001d945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d94a  test    al, al
0x18001d94c  jnz     loc_18001DCAE
0x18001d952  mov     rcx, [rbx]
0x18001d955  mov     rax, [rcx]
0x18001d958  mov     rax, [rax+88h]
0x18001d95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d964  test    al, al
0x18001d966  jnz     loc_18001DCAE
0x18001d96c  mov     rcx, [rbx]
0x18001d96f  mov     rax, [rcx]
0x18001d972  mov     rax, [rax+98h]
0x18001d979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d97e  test    al, al
0x18001d980  jz      loc_18001DA81
0x18001d986  lea     rcx, [rbp+100h+var_170]; void *
0x18001d98a  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x18001d98f  nop
0x18001d990  mov     rcx, [r13+68h]
0x18001d994  mov     rax, [rcx]
0x18001d997  lea     r8, [rbp+100h+var_170]
0x18001d99b  mov     rdx, [rbx]
0x18001d99e  mov     rax, [rax+78h]
0x18001d9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9a7  test    eax, eax
0x18001d9a9  js      loc_18001DA52
0x18001d9af  mov     rax, qword ptr [rbp+100h+var_170.Data4]
0x18001d9b3  sub     rax, qword ptr [rbp+100h+var_170.Data1]
0x18001d9b7  cmp     rax, 8
0x18001d9bb  jnz     loc_18001DA52
0x18001d9c1  mov     [rsp+200h+var_188], 0
0x18001d9ca  mov     rcx, [rbx]
0x18001d9cd  mov     rax, [rcx]
0x18001d9d0  lea     rdx, [rsp+200h+var_188]
0x18001d9d5  mov     rax, [rax+78h]
0x18001d9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9de  test    eax, eax
0x18001d9e0  js      short loc_18001DA42
0x18001d9e2  mov     rcx, [rbx]
0x18001d9e5  mov     rax, qword ptr [rbp+100h+var_170.Data1]
0x18001d9e9  mov     r15, [rax]
0x18001d9ec  mov     rax, [rcx]
0x18001d9ef  mov     rax, [rax+20h]
0x18001d9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f8  mov     r14, rax
0x18001d9fb  mov     rcx, [r15]
0x18001d9fe  mov     rax, [rcx+80h]
0x18001da05  mov     rcx, r15
0x18001da08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da0d  cmp     r14, rax
0x18001da10  jz      short loc_18001DA42
0x18001da12  mov     rcx, [rbx]
0x18001da15  mov     rax, [rcx]
0x18001da18  mov     rax, [rax+0C0h]
0x18001da1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da24  mov     r14, rax
0x18001da27  call    cs:__imp_GetTickCount64
0x18001da2d  sub     rax, r14
0x18001da30  mov     edx, cs:?g_TimeoutRevertAudioPumpFormatAndPeriodInMs@@3HA; int g_TimeoutRevertAudioPumpFormatAndPeriodInMs
0x18001da36  add     edx, 0FFFFFFF0h; unsigned int
0x18001da39  cmp     rax, rdx
0x18001da3c  jnb     loc_18001DCBC
0x18001da42  mov     rcx, [rsp+200h+var_188]; this
0x18001da47  test    rcx, rcx
0x18001da4a  jz      short loc_18001DA52
0x18001da4c  call    ??_GSaDeviceParams@@QEAAPEAXI@Z; SaDeviceParams::`scalar deleting destructor'(uint)
0x18001da51  nop
0x18001da52  mov     rcx, qword ptr [rbp+100h+var_170.Data1]
0x18001da56  test    rcx, rcx
0x18001da59  jz      loc_18001DCB3
0x18001da5f  mov     rdx, qword ptr [rbp+100h+var_170.Data4]
0x18001da63  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIStreamGroupProxy@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIStreamGroupProxy@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIStreamGroupProxy@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(Microsoft::WRL::ComPtr<IStreamGroupProxy> *,Microsoft::WRL::ComPtr<IStreamGroupProxy> * const,std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>> &)
0x18001da68  mov     rcx, qword ptr [rbp+100h+var_170.Data1]
0x18001da6c  mov     rdx, [rbp+100h+var_160]
0x18001da70  sub     rdx, rcx
0x18001da73  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001da77  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001da7c  jmp     loc_18001DCB3
0x18001da81  mov     dword ptr [rsp+200h+var_188], 0
0x18001da89  mov     [rbp+100h+var_120], 0
0x18001da91  mov     [rbp+100h+var_150], 0
0x18001da99  mov     [rbp+100h+var_140], 0
0x18001daa1  mov     [rbp+100h+pv], 0
0x18001daa9  mov     rcx, [rbx]
0x18001daac  mov     rax, [rcx]
0x18001daaf  lea     rdx, [rbp+100h+var_C0]
0x18001dab3  mov     rax, [rax+28h]
0x18001dab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dabc  movups  xmm8, xmmword ptr [rax]
0x18001dac0  mov     rcx, [rbx]
0x18001dac3  mov     rax, [rcx]
0x18001dac6  lea     rdx, [rbp+100h+var_B0]
0x18001daca  mov     rax, [rax+28h]
0x18001dace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dad3  movups  xmm7, xmmword ptr [rax]
0x18001dad6  mov     rcx, [rbx]
0x18001dad9  mov     rax, [rcx]
0x18001dadc  lea     rdx, [rbp+100h+var_A0]
0x18001dae0  mov     rax, [rax+28h]
0x18001dae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae9  movups  xmm6, xmmword ptr [rax]
0x18001daec  mov     rcx, [rbx]
0x18001daef  mov     rax, [rcx]
0x18001daf2  mov     rax, [rax+60h]
0x18001daf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dafb  movdqu  xmmword ptr [rbp+100h+var_E0.Data1], xmm8
0x18001db01  movdqu  xmmword ptr [rbp+100h+var_D0.Data1], xmm7
0x18001db06  movdqu  xmmword ptr [rbp+100h+var_170.Data1], xmm6
0x18001db0b  lea     rcx, [rbp+100h+var_120]
0x18001db0f  mov     [rsp+200h+var_1A0], rcx; struct tWAVEFORMATEX **
0x18001db14  lea     rcx, [rbp+100h+var_150]
0x18001db18  mov     [rsp+200h+var_1A8], rcx; struct tWAVEFORMATEX **
0x18001db1d  lea     rcx, [rbp+100h+pv]
0x18001db21  mov     [rsp+200h+var_1B0], rcx; struct tWAVEFORMATEX **
0x18001db26  lea     rcx, [rbp+100h+var_140]
0x18001db2a  mov     [rsp+200h+var_1B8], rcx; struct tWAVEFORMATEX **
0x18001db2f  mov     [rsp+200h+var_1C0], 0; struct tWAVEFORMATEX *
0x18001db38  lea     rcx, [rbp+100h+var_E0]
0x18001db3c  mov     [rsp+200h+var_1C8], rcx; struct _GUID *
0x18001db41  lea     rcx, [rbp+100h+var_D0]
0x18001db45  mov     [rsp+200h+var_1D0], rcx; struct _GUID *
0x18001db4a  lea     rcx, [rbp+100h+var_170]
0x18001db4e  mov     [rsp+200h+var_1D8], rcx; struct _GUID *
0x18001db53  mov     [rsp+200h+var_1E0], 0; unsigned int
0x18001db5b  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x18001db5e  mov     r8d, eax; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001db61  xor     edx, edx; bool
0x18001db63  lea     rcx, [rbp+100h+var_108]; struct EndpointCharacteristicsDescriptor *
0x18001db67  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x18001db6c  mov     r14, [rbp+100h+var_120]
0x18001db70  test    eax, eax
0x18001db72  js      loc_18001DC82
0x18001db78  mov     r15, qword ptr [rbp+100h+var_108+8]
0x18001db7c  mov     rcx, [rbx]
0x18001db7f  mov     rax, [rcx]
0x18001db82  lea     rdx, [rbp+100h+var_90]
0x18001db86  mov     rax, [rax+28h]
0x18001db8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db8f  movups  xmm6, xmmword ptr [rax]
0x18001db92  mov     rcx, [rbx]
0x18001db95  mov     rax, [rcx]
0x18001db98  mov     rax, [rax+60h]
0x18001db9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dba1  movdqu  xmmword ptr [rbp+100h+var_170.Data1], xmm6
0x18001dba6  mov     [rsp+200h+var_1C0], 0
0x18001dbaf  mov     [rsp+200h+var_1C8], 0
0x18001dbb8  mov     [rsp+200h+var_1D0], 0
0x18001dbc1  lea     rcx, [rsp+200h+var_188]
0x18001dbc6  mov     [rsp+200h+var_1D8], rcx
0x18001dbcb  mov     [rsp+200h+var_1E0], 0
0x18001dbd3  lea     r9, [rbp+100h+var_170]
0x18001dbd7  mov     r8, r14
0x18001dbda  mov     edx, eax
0x18001dbdc  mov     rcx, r15
0x18001dbdf  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x18001dbe4  test    eax, eax
0x18001dbe6  js      loc_18001DC82
0x18001dbec  mov     rcx, [rbx]
0x18001dbef  mov     rax, [rcx]
0x18001dbf2  mov     rax, [rax+20h]
0x18001dbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbfb  mov     ecx, dword ptr [rsp+200h+var_188]
0x18001dbff  xorps   xmm6, xmm6
0x18001dc02  cvtsi2sd xmm6, rcx
0x18001dc07  mulsd   xmm6, cs:__real@416312d000000000
0x18001dc0f  mov     ecx, [r14+4]
0x18001dc13  xorps   xmm0, xmm0
0x18001dc16  cvtsi2sd xmm0, rcx
0x18001dc1b  movaps  xmm1, xmm6
0x18001dc1e  divsd   xmm1, xmm0
0x18001dc22  addsd   xmm1, cs:__real@3fe0000000000000
0x18001dc2a  cvttsd2si rcx, xmm1
0x18001dc2f  cmp     rax, rcx
0x18001dc32  jnz     short loc_18001DC52
0x18001dc34  mov     rcx, [rbx]
0x18001dc37  mov     rax, [rcx]
0x18001dc3a  mov     rax, [rax+30h]
0x18001dc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc43  mov     rdx, rax; struct tWAVEFORMATEX *
0x18001dc46  mov     rcx, r14; struct tWAVEFORMATEX *
0x18001dc49  call    ?CompareWaveFormat@@YAHPEBUtWAVEFORMATEX@@0@Z; CompareWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x18001dc4e  test    eax, eax
0x18001dc50  jnz     short loc_18001DC82
0x18001dc52  mov     rcx, [rbx]
0x18001dc55  mov     rax, [rcx]
0x18001dc58  mov     rax, [rax+0C0h]
0x18001dc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc64  mov     r15, rax
0x18001dc67  call    cs:__imp_GetTickCount64
0x18001dc6d  sub     rax, r15
0x18001dc70  mov     edx, cs:?g_TimeoutRevertAudioPumpFormatAndPeriodInMs@@3HA; int g_TimeoutRevertAudioPumpFormatAndPeriodInMs
0x18001dc76  add     edx, 0FFFFFFF0h
0x18001dc79  cmp     rax, rdx
0x18001dc7c  jnb     loc_18001DD62
0x18001dc82  mov     rcx, [rbp+100h+pv]; pv
0x18001dc86  call    cs:__imp_CoTaskMemFree
0x18001dc8c  nop
  ... truncated ...
```

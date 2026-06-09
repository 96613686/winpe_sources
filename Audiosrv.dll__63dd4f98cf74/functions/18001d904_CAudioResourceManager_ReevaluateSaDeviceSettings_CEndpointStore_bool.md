# CAudioResourceManager::ReevaluateSaDeviceSettings(CEndpointStore *,bool)

- ea: `0x18001d904`
- end: `0x18001e0aa`
- name: `?ReevaluateSaDeviceSettings@CAudioResourceManager@@IEAAXPEAVCEndpointStore@@_N@Z`
- size: `1958`
- prototype: `void __fastcall(CAudioResourceManager *__hidden this, struct CEndpointStore *, bool)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e4f40`

## callees

- `0x18000b0c0`
- `0x1800182e8`
- `0x18001d7ec`
- `0x18001d904`
- `0x18001e92c`
- `0x18001ec9c`
- `0x18003896c`
- `0x18003a1e0`
- `0x180044bd8`
- `0x180052f70`
- `0x1800b70d0`
- `0x1800bd020`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1800e51e0`
- `0x1800e5298`
- `0x1800e9f2c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e064`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e064`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001db77`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ddb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001db77`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ddb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dde1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ded6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dde1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ded6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df9e`
- `ext-ms-win-audiocore-policymanager-l1-1-1!AudioPolicyManagerExtension_OnPostMatchFormatStateChange` at `0x18001e017`
- `ext-ms-win-audiocore-policymanager-l1-1-1!AudioPolicyManagerExtension_OnPostMatchFormatStateChange` at `0x18001e017`

## string_xrefs

- `0x18001df67`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18001e049`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

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
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_eacb2d5fa25a3e5f73f3ddb8cb456386_Traceguids, v8);
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
                (CEndpointCharacteristics **)v55,
                0,
                v23,
                AUDCLNT_SHAREMODE_SHARED,
                0,
                (IAudioMediaType *)&v44,
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
0x18001d904  mov     rax, rsp
0x18001d907  push    rbp
0x18001d908  push    rbx
0x18001d909  push    rsi
0x18001d90a  push    rdi
0x18001d90b  push    r12
0x18001d90d  push    r13
0x18001d90f  push    r14
0x18001d911  push    r15
0x18001d913  lea     rbp, [rax-108h]
0x18001d91a  sub     rsp, 1C8h
0x18001d921  movaps  xmmword ptr [rax-58h], xmm6
0x18001d925  movaps  xmmword ptr [rax-68h], xmm7
0x18001d929  movaps  xmmword ptr [rax-78h], xmm8
0x18001d92e  mov     rax, cs:__security_cookie
0x18001d935  xor     rax, rsp
0x18001d938  mov     [rbp+100h+var_80], rax
0x18001d93f  mov     byte ptr [rsp+200h+var_190+2], r8b
0x18001d944  mov     r13, rdx
0x18001d947  xorps   xmm0, xmm0
0x18001d94a  movdqu  xmmword ptr [rbp+100h+var_108], xmm0
0x18001d94f  xor     esi, esi
0x18001d951  mov     [rbp+100h+var_F8], rsi
0x18001d955  lea     r12, [rdx+10h]
0x18001d959  cmp     qword ptr [r12+18h], 7
0x18001d95f  jbe     short loc_18001D967
0x18001d961  mov     rdx, [r12]
0x18001d965  jmp     short loc_18001D96A
0x18001d967  mov     rdx, r12
0x18001d96a  mov     rcx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x18001d971  mov     rax, [rcx]
0x18001d974  lea     r8, [rbp+100h+var_108]
0x18001d978  mov     qword ptr [rsp+200h+var_1E0], r8; int
0x18001d97d  xor     r9d, r9d
0x18001d980  xor     r8d, r8d
0x18001d983  mov     rax, [rax+28h]
0x18001d987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d98c  mov     ebx, eax
0x18001d98e  lea     rdi, WPP_GLOBAL_Control
0x18001d995  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d99c  cmp     rcx, rdi
0x18001d99f  jz      short loc_18001D9D6
0x18001d9a1  test    dword ptr [rcx+1Ch], 100h
0x18001d9a8  jz      short loc_18001D9D6
0x18001d9aa  cmp     byte ptr [rcx+19h], 4
0x18001d9ae  jb      short loc_18001D9D6
0x18001d9b0  cmp     qword ptr [r12+18h], 7
0x18001d9b6  jbe     short loc_18001D9BE
0x18001d9b8  mov     r9, [r12]
0x18001d9bc  jmp     short loc_18001D9C1
0x18001d9be  mov     r9, r12
0x18001d9c1  mov     edx, 16h
0x18001d9c6  lea     r8, WPP_eacb2d5fa25a3e5f73f3ddb8cb456386_Traceguids
0x18001d9cd  mov     rcx, [rcx+10h]
0x18001d9d1  call    WPP_SF_S
0x18001d9d6  test    ebx, ebx
0x18001d9d8  js      loc_18001E06B
0x18001d9de  mov     rcx, [r13+68h]
0x18001d9e2  mov     rax, [rcx]
0x18001d9e5  lea     rdx, [rbp+100h+lpCriticalSection]
0x18001d9e9  mov     rax, [rax+80h]
0x18001d9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f5  nop
0x18001d9f6  mov     r14b, sil
0x18001d9f9  mov     byte ptr [rsp+200h+var_190], sil
0x18001d9fe  mov     byte ptr [rsp+200h+var_190+1], sil
0x18001da03  mov     r15b, 1
0x18001da06  mov     byte ptr [rsp+200h+var_190+3], r15b
0x18001da0b  lea     rcx, [rbp+100h+var_138]; void *
0x18001da0f  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x18001da14  nop
0x18001da15  mov     rcx, [r13+68h]
0x18001da19  mov     rax, [rcx]
0x18001da1c  lea     rdx, [rbp+100h+var_138]
0x18001da20  mov     rax, [rax+60h]
0x18001da24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da29  mov     ebx, eax
0x18001da2b  mov     [rbp+100h+var_180], eax
0x18001da2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da35  cmp     rcx, rdi
0x18001da38  jz      short loc_18001DA63
0x18001da3a  test    dword ptr [rcx+1Ch], 100h
0x18001da41  jz      short loc_18001DA63
0x18001da43  cmp     byte ptr [rcx+19h], 4
0x18001da47  jb      short loc_18001DA63
0x18001da49  mov     r9, [rbp+100h+var_130]
0x18001da4d  sub     r9, [rbp+100h+var_138]
0x18001da51  sar     r9, 3
0x18001da55  mov     edx, 17h
0x18001da5a  mov     rcx, [rcx+10h]
0x18001da5e  call    WPP_SF_P
0x18001da63  test    ebx, ebx
0x18001da65  js      loc_18001DFC4
0x18001da6b  mov     [rbp+100h+var_178], rsi
0x18001da6f  mov     rdi, rsi
0x18001da72  mov     [rbp+100h+var_118], rsi
0x18001da76  mov     [rbp+100h+var_110], rsi
0x18001da7a  mov     rbx, [rbp+100h+var_138]
0x18001da7e  cmp     rbx, [rbp+100h+var_130]
0x18001da82  jz      loc_18001DF84
0x18001da88  mov     rcx, [rbx]
0x18001da8b  mov     rax, [rcx]
0x18001da8e  mov     rax, [rax+0A8h]
0x18001da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da9a  test    al, al
0x18001da9c  jnz     loc_18001DDFE
0x18001daa2  mov     rcx, [rbx]
0x18001daa5  mov     rax, [rcx]
0x18001daa8  mov     rax, [rax+88h]
0x18001daaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dab4  test    al, al
0x18001dab6  jnz     loc_18001DDFE
0x18001dabc  mov     rcx, [rbx]
0x18001dabf  mov     rax, [rcx]
0x18001dac2  mov     rax, [rax+98h]
0x18001dac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dace  test    al, al
0x18001dad0  jz      loc_18001DBD1
0x18001dad6  lea     rcx, [rbp+100h+var_170]; void *
0x18001dada  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x18001dadf  nop
0x18001dae0  mov     rcx, [r13+68h]
0x18001dae4  mov     rax, [rcx]
0x18001dae7  lea     r8, [rbp+100h+var_170]
0x18001daeb  mov     rdx, [rbx]
0x18001daee  mov     rax, [rax+78h]
0x18001daf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daf7  test    eax, eax
0x18001daf9  js      loc_18001DBA2
0x18001daff  mov     rax, qword ptr [rbp+100h+var_170.Data4]
0x18001db03  sub     rax, qword ptr [rbp+100h+var_170.Data1]
0x18001db07  cmp     rax, 8
0x18001db0b  jnz     loc_18001DBA2
0x18001db11  mov     [rsp+200h+var_188], 0
0x18001db1a  mov     rcx, [rbx]
0x18001db1d  mov     rax, [rcx]
0x18001db20  lea     rdx, [rsp+200h+var_188]
0x18001db25  mov     rax, [rax+78h]
0x18001db29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db2e  test    eax, eax
0x18001db30  js      short loc_18001DB92
0x18001db32  mov     rcx, [rbx]
0x18001db35  mov     rax, qword ptr [rbp+100h+var_170.Data1]
0x18001db39  mov     r15, [rax]
0x18001db3c  mov     rax, [rcx]
0x18001db3f  mov     rax, [rax+20h]
0x18001db43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db48  mov     r14, rax
0x18001db4b  mov     rcx, [r15]
0x18001db4e  mov     rax, [rcx+80h]
0x18001db55  mov     rcx, r15
0x18001db58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db5d  cmp     r14, rax
0x18001db60  jz      short loc_18001DB92
0x18001db62  mov     rcx, [rbx]
0x18001db65  mov     rax, [rcx]
0x18001db68  mov     rax, [rax+0C0h]
0x18001db6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db74  mov     r14, rax
0x18001db77  call    cs:__imp_GetTickCount64
0x18001db7d  sub     rax, r14
0x18001db80  mov     edx, cs:?g_TimeoutRevertAudioPumpFormatAndPeriodInMs@@3HA; int g_TimeoutRevertAudioPumpFormatAndPeriodInMs
0x18001db86  add     edx, 0FFFFFFF0h; unsigned int
0x18001db89  cmp     rax, rdx
0x18001db8c  jnb     loc_18001DE0C
0x18001db92  mov     rcx, [rsp+200h+var_188]; this
0x18001db97  test    rcx, rcx
0x18001db9a  jz      short loc_18001DBA2
0x18001db9c  call    ??_GSaDeviceParams@@QEAAPEAXI@Z; SaDeviceParams::`scalar deleting destructor'(uint)
0x18001dba1  nop
0x18001dba2  mov     rcx, qword ptr [rbp+100h+var_170.Data1]
0x18001dba6  test    rcx, rcx
0x18001dba9  jz      loc_18001DE03
0x18001dbaf  mov     rdx, qword ptr [rbp+100h+var_170.Data4]
0x18001dbb3  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIStreamGroupProxy@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIStreamGroupProxy@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIStreamGroupProxy@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(Microsoft::WRL::ComPtr<IStreamGroupProxy> *,Microsoft::WRL::ComPtr<IStreamGroupProxy> * const,std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>> &)
0x18001dbb8  mov     rcx, qword ptr [rbp+100h+var_170.Data1]
0x18001dbbc  mov     rdx, [rbp+100h+var_160]
0x18001dbc0  sub     rdx, rcx
0x18001dbc3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001dbc7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001dbcc  jmp     loc_18001DE03
0x18001dbd1  mov     dword ptr [rsp+200h+var_188], 0
0x18001dbd9  mov     [rbp+100h+var_120], 0
0x18001dbe1  mov     [rbp+100h+var_150], 0
0x18001dbe9  mov     [rbp+100h+var_140], 0
0x18001dbf1  mov     [rbp+100h+pv], 0
0x18001dbf9  mov     rcx, [rbx]
0x18001dbfc  mov     rax, [rcx]
0x18001dbff  lea     rdx, [rbp+100h+var_C0]
0x18001dc03  mov     rax, [rax+28h]
0x18001dc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc0c  movups  xmm8, xmmword ptr [rax]
0x18001dc10  mov     rcx, [rbx]
0x18001dc13  mov     rax, [rcx]
0x18001dc16  lea     rdx, [rbp+100h+var_B0]
0x18001dc1a  mov     rax, [rax+28h]
0x18001dc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc23  movups  xmm7, xmmword ptr [rax]
0x18001dc26  mov     rcx, [rbx]
0x18001dc29  mov     rax, [rcx]
0x18001dc2c  lea     rdx, [rbp+100h+var_A0]
0x18001dc30  mov     rax, [rax+28h]
0x18001dc34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc39  movups  xmm6, xmmword ptr [rax]
0x18001dc3c  mov     rcx, [rbx]
0x18001dc3f  mov     rax, [rcx]
0x18001dc42  mov     rax, [rax+60h]
0x18001dc46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc4b  movdqu  xmmword ptr [rbp+100h+var_E0.Data1], xmm8
0x18001dc51  movdqu  xmmword ptr [rbp+100h+var_D0.Data1], xmm7
0x18001dc56  movdqu  xmmword ptr [rbp+100h+var_170.Data1], xmm6
0x18001dc5b  lea     rcx, [rbp+100h+var_120]
0x18001dc5f  mov     [rsp+200h+var_1A0], rcx; struct tWAVEFORMATEX **
0x18001dc64  lea     rcx, [rbp+100h+var_150]
0x18001dc68  mov     [rsp+200h+var_1A8], rcx; struct tWAVEFORMATEX **
0x18001dc6d  lea     rcx, [rbp+100h+pv]
0x18001dc71  mov     [rsp+200h+var_1B0], rcx; struct tWAVEFORMATEX **
0x18001dc76  lea     rcx, [rbp+100h+var_140]
0x18001dc7a  mov     [rsp+200h+var_1B8], rcx; struct tWAVEFORMATEX **
0x18001dc7f  mov     [rsp+200h+var_1C0], 0; struct tWAVEFORMATEX *
0x18001dc88  lea     rcx, [rbp+100h+var_E0]
0x18001dc8c  mov     [rsp+200h+var_1C8], rcx; struct _GUID *
0x18001dc91  lea     rcx, [rbp+100h+var_D0]
0x18001dc95  mov     [rsp+200h+var_1D0], rcx; struct _GUID *
0x18001dc9a  lea     rcx, [rbp+100h+var_170]
0x18001dc9e  mov     [rsp+200h+var_1D8], rcx; struct _GUID *
0x18001dca3  mov     [rsp+200h+var_1E0], 0; unsigned int
0x18001dcab  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x18001dcae  mov     r8d, eax; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001dcb1  xor     edx, edx; bool
0x18001dcb3  lea     rcx, [rbp+100h+var_108]; struct EndpointCharacteristicsDescriptor *
0x18001dcb7  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x18001dcbc  mov     r14, [rbp+100h+var_120]
0x18001dcc0  test    eax, eax
0x18001dcc2  js      loc_18001DDD2
0x18001dcc8  mov     r15, qword ptr [rbp+100h+var_108+8]
0x18001dccc  mov     rcx, [rbx]
0x18001dccf  mov     rax, [rcx]
0x18001dcd2  lea     rdx, [rbp+100h+var_90]
0x18001dcd6  mov     rax, [rax+28h]
0x18001dcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcdf  movups  xmm6, xmmword ptr [rax]
0x18001dce2  mov     rcx, [rbx]
0x18001dce5  mov     rax, [rcx]
0x18001dce8  mov     rax, [rax+60h]
0x18001dcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcf1  movdqu  xmmword ptr [rbp+100h+var_170.Data1], xmm6
0x18001dcf6  mov     [rsp+200h+var_1C0], 0
0x18001dcff  mov     [rsp+200h+var_1C8], 0
0x18001dd08  mov     [rsp+200h+var_1D0], 0
0x18001dd11  lea     rcx, [rsp+200h+var_188]
0x18001dd16  mov     [rsp+200h+var_1D8], rcx
0x18001dd1b  mov     [rsp+200h+var_1E0], 0
0x18001dd23  lea     r9, [rbp+100h+var_170]
0x18001dd27  mov     r8, r14
0x18001dd2a  mov     edx, eax
0x18001dd2c  mov     rcx, r15
0x18001dd2f  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x18001dd34  test    eax, eax
0x18001dd36  js      loc_18001DDD2
0x18001dd3c  mov     rcx, [rbx]
0x18001dd3f  mov     rax, [rcx]
0x18001dd42  mov     rax, [rax+20h]
0x18001dd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd4b  mov     ecx, dword ptr [rsp+200h+var_188]
0x18001dd4f  xorps   xmm6, xmm6
0x18001dd52  cvtsi2sd xmm6, rcx
0x18001dd57  mulsd   xmm6, cs:__real@416312d000000000
0x18001dd5f  mov     ecx, [r14+4]
0x18001dd63  xorps   xmm0, xmm0
0x18001dd66  cvtsi2sd xmm0, rcx
0x18001dd6b  movaps  xmm1, xmm6
0x18001dd6e  divsd   xmm1, xmm0
0x18001dd72  addsd   xmm1, cs:__real@3fe0000000000000
0x18001dd7a  cvttsd2si rcx, xmm1
0x18001dd7f  cmp     rax, rcx
0x18001dd82  jnz     short loc_18001DDA2
0x18001dd84  mov     rcx, [rbx]
0x18001dd87  mov     rax, [rcx]
0x18001dd8a  mov     rax, [rax+30h]
0x18001dd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd93  mov     rdx, rax; struct tWAVEFORMATEX *
0x18001dd96  mov     rcx, r14; struct tWAVEFORMATEX *
0x18001dd99  call    ?CompareWaveFormat@@YAHPEBUtWAVEFORMATEX@@0@Z; CompareWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x18001dd9e  test    eax, eax
0x18001dda0  jnz     short loc_18001DDD2
0x18001dda2  mov     rcx, [rbx]
0x18001dda5  mov     rax, [rcx]
0x18001dda8  mov     rax, [rax+0C0h]
0x18001ddaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddb4  mov     r15, rax
0x18001ddb7  call    cs:__imp_GetTickCount64
0x18001ddbd  sub     rax, r15
0x18001ddc0  mov     edx, cs:?g_TimeoutRevertAudioPumpFormatAndPeriodInMs@@3HA; int g_TimeoutRevertAudioPumpFormatAndPeriodInMs
0x18001ddc6  add     edx, 0FFFFFFF0h
0x18001ddc9  cmp     rax, rdx
0x18001ddcc  jnb     loc_18001DEB2
0x18001ddd2  mov     rcx, [rbp+100h+pv]; pv
0x18001ddd6  call    cs:__imp_CoTaskMemFree
0x18001dddc  nop
  ... truncated ...
```

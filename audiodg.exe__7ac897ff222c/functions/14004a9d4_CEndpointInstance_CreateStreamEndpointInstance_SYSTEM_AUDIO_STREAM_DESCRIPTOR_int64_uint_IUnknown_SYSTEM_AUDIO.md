# CEndpointInstance::CreateStreamEndpointInstance(SYSTEM_AUDIO_STREAM_DESCRIPTOR *,__int64,uint,IUnknown *,SYSTEM_AUDIO_STREAM *,ICrossProcessMemory * *,ICrossProcessEvent * *,CEndpointInstance * *)

- ea: `0x14004a9d4`
- end: `0x14004b2bc`
- name: `?CreateStreamEndpointInstance@CEndpointInstance@@SAJPEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@_JIPEAUIUnknown@@PEAUSYSTEM_AUDIO_STREAM@@PEAPEAUICrossProcessMemory@@PEAPEAUICrossProcessEvent@@PEAPEAV1@@Z`
- size: `2280`
- prototype: `__int64 __fastcall(struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *, int, unsigned int, struct IUnknown *, struct SYSTEM_AUDIO_STREAM *, struct ICrossProcessMemory **, struct ICrossProcessEvent **, struct CEndpointInstance **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004a090`

## callees

- `0x140008124`
- `0x14000a39c`
- `0x14000c33c`
- `0x140019830`
- `0x1400310a0`
- `0x140035664`
- `0x140039b40`
- `0x14004a9d4`
- `0x14004e808`
- `0x1400516e8`
- `0x140053040`
- `0x14005d148`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004b0d3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004b0d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004ab32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004aea1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004ab32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004aea1`

## pseudocode

```c
__int64 __fastcall CEndpointInstance::CreateStreamEndpointInstance(
        struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *a1,
        int a2,
        unsigned int a3,
        struct IUnknown *a4,
        struct SYSTEM_AUDIO_STREAM *a5,
        struct ICrossProcessMemory **a6,
        struct ICrossProcessEvent **a7,
        struct CEndpointInstance **a8)
{
  __int64 v11; // r13
  int v12; // esi
  BOOL v13; // r14d
  unsigned int v14; // r11d
  double v15; // xmm1_8
  __int64 v16; // rdx
  int v17; // ebx
  unsigned int v18; // r10d
  __int64 v19; // r11
  __int64 v20; // rax
  __int64 v21; // rax
  HRESULT v22; // eax
  __int64 v23; // rdx
  GUID v24; // xmm6
  int v25; // eax
  int FactoryFromAudioPumpDspResource; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  HRESULT v35; // eax
  __int64 v36; // r9
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  GUID *p_pvData; // rcx
  int v43; // ebx
  int v44; // edi
  struct SYSTEM_AUDIO_STREAM *v45; // rax
  GUID *p_Buf1; // rcx
  int v47; // eax
  __int64 v48; // rdx
  int v49; // edi
  struct SYSTEM_AUDIO_STREAM *v50; // rax
  int v51; // eax
  __int64 v52; // rdx
  CEndpointInstance *v53; // rax
  struct CEndpointInstance *v54; // rax
  int ppv; // [rsp+28h] [rbp-C9h]
  int ppva; // [rsp+28h] [rbp-C9h]
  int ppvb; // [rsp+28h] [rbp-C9h]
  LPVOID v59; // [rsp+88h] [rbp-69h] BYREF
  struct IAudioEndpointRT *v60; // [rsp+90h] [rbp-61h] BYREF
  __int64 v61; // [rsp+98h] [rbp-59h] BYREF
  __int64 *v62; // [rsp+A0h] [rbp-51h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-49h] BYREF
  LPVOID v64; // [rsp+B0h] [rbp-41h] BYREF
  GUID Buf1; // [rsp+B8h] [rbp-39h] BYREF
  __int128 v66; // [rsp+C8h] [rbp-29h] BYREF
  DWORD pcbData[8]; // [rsp+D8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+3Fh]
  __int64 v69; // [rsp+138h] [rbp+47h] BYREF
  __int64 pvData; // [rsp+140h] [rbp+4Fh] BYREF

  v11 = *((_QWORD *)a1 + 16);
  v12 = *(_DWORD *)a1;
  v13 = *(_DWORD *)a1 != 0;
  v14 = *(unsigned __int16 *)(v11 + 12);
  v15 = (double)(int)(*(_DWORD *)(v11 + 8) / v14) * (double)a2 / 10000000.0 + 0.5;
  if ( v15 >= 4294967295.0 )
  {
    v16 = 305;
    goto LABEL_104;
  }
  if ( (int)v15 + a3 < (int)v15 )
  {
    v16 = 306;
LABEL_104:
    v17 = -2147024362;
    goto LABEL_105;
  }
  LODWORD(v69) = 0;
  v17 = HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE(*((_QWORD *)a1 + 3), *(_DWORD *)(v11 + 8), v14, (unsigned int *)&v69);
  if ( v17 < 0 )
  {
    v16 = 310;
LABEL_105:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
      (const char *)(unsigned int)v17,
      ppv);
    return (unsigned int)v17;
  }
  if ( *((_DWORD *)a1 + 2) == 1 )
  {
    v20 = (unsigned int)v69;
  }
  else
  {
    v20 = (unsigned int)v69;
    if ( v18 > (unsigned int)v69 )
      v20 = v18;
  }
  LODWORD(v69) = 0;
  v17 = LongLongToUInt(v20 * v19, (unsigned int *)&v69);
  if ( v17 < 0 )
  {
    v16 = 319;
    goto LABEL_105;
  }
  pvData = *((_QWORD *)a1 + 2);
  v64 = 0;
  if ( (*((_DWORD *)a1 + 34) & 0x40000) == 0 )
    goto LABEL_21;
  v21 = *((_QWORD *)a1 + 10) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v21 )
    v21 = *((_QWORD *)a1 + 11) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( !v21 )
    goto LABEL_21;
  v64 = 0;
  v22 = CoCreateInstance((const IID *const)a1 + 5, 0, 0x17u, &GUID_c4e70434_407d_416b_94be_9717b79065fb, &v64);
  v17 = v22;
  if ( v22 >= 0 )
  {
    v22 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v64 + 24LL))(v64, (char *)a1 + 96);
    v17 = v22;
    if ( v22 < 0 )
    {
      v23 = 329;
      goto LABEL_20;
    }
LABEL_21:
    v60 = 0;
    if ( a4 )
    {
      if ( v12 )
        v24 = GUID_1a5582a4_990a_409a_b299_4413d56ff865;
      else
        v24 = GUID_3fd3bade_0ea7_4684_80f8_ff3609fa59ac;
    }
    else if ( v12 )
    {
      v24 = GUID_5bfd515e_4aba_4483_a1c5_6651b7110ab6;
    }
    else
    {
      v24 = GUID_9dba709c_b3e1_4013_95b7_5ed33a2e8561;
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(&v60);
    v66 = *((_OWORD *)a1 + 3);
    Buf1 = v24;
    v25 = CreateCrossProcessServerEndpoint(&Buf1, (__int64)&v60);
    v17 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)(unsigned int)v25,
        ppvb);
LABEL_101:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
      goto LABEL_102;
    }
    v59 = 0;
    if ( a4 )
    {
      v62 = 0;
      FactoryFromAudioPumpDspResource = GetFactoryFromAudioPumpDspResourceToken<IDspCrossProcessAudioEndpointFactory>(
                                          a4,
                                          &v62);
      v17 = FactoryFromAudioPumpDspResource;
      if ( FactoryFromAudioPumpDspResource < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)FactoryFromAudioPumpDspResource,
          ppvb);
LABEL_33:
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v62);
LABEL_100:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
        goto LABEL_101;
      }
      v61 = 0;
      v27 = *v62;
      if ( v12 )
      {
        v61 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v27 + 32))(v62, &v61);
        v17 = v28;
        if ( v28 < 0 )
        {
          v29 = 362;
          goto LABEL_37;
        }
      }
      else
      {
        v61 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v27 + 24))(v62, &v61);
        v17 = v28;
        if ( v28 < 0 )
        {
          v29 = 358;
LABEL_37:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
            (const char *)(unsigned int)v28,
            ppvb);
LABEL_38:
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v61);
          goto LABEL_33;
        }
      }
      v63 = 0;
      v30 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int64 *))v60->lpVtbl->QueryInterface)(
              v60,
              &GUID_cb9fb9a6_9421_4b4b_b277_583d4d482547,
              &v63);
      v17 = v30;
      if ( v30 < 0 )
      {
        v31 = 366;
LABEL_43:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)v30,
          ppvb);
LABEL_44:
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v63);
        goto LABEL_38;
      }
      v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 24LL))(v63, v61);
      v17 = v30;
      if ( v30 < 0 )
      {
        v31 = 367;
        goto LABEL_43;
      }
      v59 = 0;
      v30 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, LPVOID *))v60->lpVtbl->QueryInterface)(
              v60,
              &GUID_6b7f3699_f0ab_4184_bfd4_383e1520e0c9,
              &v59);
      v17 = v30;
      if ( v30 < 0 )
      {
        v31 = 369;
        goto LABEL_43;
      }
      v32 = *((_QWORD *)a1 + 8) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
      if ( !v32 )
        v32 = *((_QWORD *)a1 + 9) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
      if ( v32 )
      {
        v30 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v59 + 24LL))(v59, (char *)a1 + 96);
        v17 = v30;
        if ( v30 < 0 )
        {
          v31 = 373;
          goto LABEL_43;
        }
      }
      *(_QWORD *)&v66 = 0;
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int128 *))v59)(
             v59,
             &GUID_fc48820a_f18b_41c6_83aa_e9fcee39e429,
             &v66) >= 0 )
      {
        v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v66 + 40LL))(v66, *((unsigned int *)a1 + 3));
        v17 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17E,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
            (const char *)(unsigned int)v33,
            ppvb);
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v66);
          goto LABEL_44;
        }
      }
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v66);
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v63);
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v61);
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v62);
    }
    else
    {
      v34 = *((_QWORD *)a1 + 8) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
      if ( !v34 )
        v34 = *((_QWORD *)a1 + 9) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
      if ( v34 )
      {
        v59 = 0;
        v35 = CoCreateInstance((const IID *const)a1 + 4, 0, 0x17u, &GUID_6b7f3699_f0ab_4184_bfd4_383e1520e0c9, &v59);
        v17 = v35;
        if ( v35 < 0 )
        {
          v36 = (unsigned int)v35;
          v37 = 391;
          goto LABEL_99;
        }
        v38 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v59 + 24LL))(v59, (char *)a1 + 96);
        v17 = v38;
        if ( v38 < 0 )
        {
          v36 = (unsigned int)v38;
          v37 = 392;
          goto LABEL_99;
        }
      }
      else
      {
        v59 = 0;
        v39 = Microsoft::WRL::Details::MakeAndInitialize<CSectionBasedCrossProcessMemoryManager,ICrossProcessMemoryManager,unsigned short const * &>(
                &v59,
                &pvData);
        v17 = v39;
        if ( v39 < 0 )
        {
          v36 = (unsigned int)v39;
          v37 = 397;
          goto LABEL_99;
        }
      }
    }
    if ( v13 )
    {
      pvData = 0;
      v40 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int64 *))v60->lpVtbl->QueryInterface)(
              v60,
              &GUID_497dee26_e484_456d_9349_60b89142d65e,
              &pvData);
      v17 = v40;
      if ( v40 < 0 )
      {
        v41 = 452;
LABEL_71:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)v40,
          ppvb);
        p_pvData = (GUID *)&pvData;
LABEL_72:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(p_pvData);
        goto LABEL_100;
      }
      if ( *((_QWORD *)a1 + 31) || *((_QWORD *)a1 + 33) )
        v43 = (int)((double)*(int *)(v11 + 4) * (double)(int)*((_QWORD *)a1 + 32) / 10000000.0 + 0.5);
      else
        v43 = 0;
      ppvb = v43;
      v44 = v69;
      v40 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)pvData + 24LL))(
              pvData,
              v11,
              (unsigned int)v69,
              a3);
      v17 = v40;
      if ( v40 < 0 )
      {
        v41 = 474;
        goto LABEL_71;
      }
      v45 = a5;
      *(GUID *)a5 = GUID_f64a6da6_e8af_4b7b_bca8_847ae765d538;
      *((_DWORD *)v45 + 234) = 0;
      *((_DWORD *)v45 + 4) = v44;
      p_Buf1 = (GUID *)&pvData;
      goto LABEL_88;
    }
    *(_QWORD *)&Buf1.Data1 = 0;
    v47 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, GUID *))v60->lpVtbl->QueryInterface)(
            v60,
            &GUID_497dee26_e484_456d_9349_60b89142d65e,
            &Buf1);
    v17 = v47;
    if ( v47 >= 0 )
    {
      if ( *((_DWORD *)a1 + 74) == 2 )
      {
        LODWORD(pvData) = 0;
        pcbData[0] = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"SuppressBridgeTargetGlitchLogging",
          0x18u,
          0,
          &pvData,
          pcbData);
      }
      ppvb = 0;
      v49 = v69;
      v47 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)&Buf1.Data1 + 24LL))(
              *(_QWORD *)&Buf1.Data1,
              v11,
              (unsigned int)v69,
              a3);
      v17 = v47;
      if ( v47 >= 0 )
      {
        v50 = a5;
        *(GUID *)a5 = GUID_cd773740_b187_4974_a1d5_e0ff91372277;
        *((_DWORD *)v50 + 234) = 0;
        *((_DWORD *)v50 + 4) = v49;
        p_Buf1 = &Buf1;
LABEL_88:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(p_Buf1);
        if ( a4 )
        {
          v69 = 0;
          v51 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int64 *))v60->lpVtbl->QueryInterface)(
                  v60,
                  &GUID_cb9fb9a6_9421_4b4b_b277_583d4d482547,
                  &v69);
          v17 = v51;
          if ( v51 < 0 )
          {
            v52 = 492;
LABEL_91:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v52,
              (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
              (const char *)(unsigned int)v51,
              ppvb);
            wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v69);
            goto LABEL_100;
          }
          v51 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v69 + 32LL))(v69, a3);
          v17 = v51;
          if ( v51 < 0 )
          {
            v52 = 493;
            goto LABEL_91;
          }
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v69);
        }
        v53 = (CEndpointInstance *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)pcbData = v53;
        if ( v53 )
        {
          v54 = CEndpointInstance::CEndpointInstance(v53, v60, 0);
          if ( v54 )
          {
            *a8 = v54;
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
            v17 = 0;
            goto LABEL_102;
          }
        }
        v17 = -2147024882;
        v37 = 500;
        v36 = 2147942414LL;
LABEL_99:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)v36,
          ppvb);
        goto LABEL_100;
      }
      v48 = 439;
    }
    else
    {
      v48 = 407;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v48,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
      (const char *)(unsigned int)v47,
      ppvb);
    p_pvData = &Buf1;
    goto LABEL_72;
  }
  v23 = 328;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
    (const char *)(unsigned int)v22,
    ppva);
LABEL_102:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v64);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14004a9d4  mov     rax, rsp
0x14004a9d7  mov     [rax+18h], rbx
0x14004a9db  push    rbp
0x14004a9dc  push    rsi
0x14004a9dd  push    rdi
0x14004a9de  push    r12
0x14004a9e0  push    r13
0x14004a9e2  push    r14
0x14004a9e4  push    r15
0x14004a9e6  lea     rbp, [rax-3Fh]
0x14004a9ea  sub     rsp, 0F0h
0x14004a9f1  movaps  xmmword ptr [rax-48h], xmm6
0x14004a9f5  mov     r15, r9
0x14004a9f8  mov     r12d, r8d
0x14004a9fb  mov     r10, rdx
0x14004a9fe  mov     rdi, rcx
0x14004aa01  mov     r13, [rcx+80h]
0x14004aa08  mov     esi, [rcx]
0x14004aa0a  xor     r14d, r14d
0x14004aa0d  test    esi, esi
0x14004aa0f  setnz   r14b
0x14004aa13  movzx   r11d, word ptr [r13+0Ch]
0x14004aa18  xor     edx, edx
0x14004aa1a  mov     eax, [r13+8]
0x14004aa1e  div     r11d
0x14004aa21  mov     ecx, eax
0x14004aa23  xorps   xmm1, xmm1
0x14004aa26  cvtsi2sd xmm1, rcx
0x14004aa2b  xorps   xmm0, xmm0
0x14004aa2e  cvtsi2sd xmm0, r10
0x14004aa33  mulsd   xmm1, xmm0
0x14004aa37  divsd   xmm1, cs:__real@416312d000000000
0x14004aa3f  addsd   xmm1, cs:__real@3fe0000000000000
0x14004aa47  comisd  xmm1, cs:__real@41efffffffe00000
0x14004aa4f  jnb     loc_14004B27D
0x14004aa55  cvttsd2si rax, xmm1
0x14004aa5a  lea     r10d, [rax+r8]
0x14004aa5e  cmp     r10d, eax
0x14004aa61  jnb     short loc_14004AA6D
0x14004aa63  mov     edx, 132h
0x14004aa68  jmp     loc_14004B282
0x14004aa6d  mov     dword ptr [rbp+37h+arg_0], 0
0x14004aa74  lea     r9, [rbp+37h+arg_0]; unsigned int *
0x14004aa78  mov     r8d, r11d; unsigned int
0x14004aa7b  mov     edx, [r13+8]; unsigned int
0x14004aa7f  mov     rcx, [rdi+18h]; __int64
0x14004aa83  call    ?HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE@@YAJ_JIIPEAI@Z; HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE(__int64,uint,uint,uint *)
0x14004aa88  mov     ebx, eax
0x14004aa8a  test    eax, eax
0x14004aa8c  jns     short loc_14004AA98
0x14004aa8e  mov     edx, 136h
0x14004aa93  jmp     loc_14004B287
0x14004aa98  cmp     dword ptr [rdi+8], 1
0x14004aa9c  jnz     short loc_14004AAA3
0x14004aa9e  mov     eax, dword ptr [rbp+37h+arg_0]
0x14004aaa1  jmp     short loc_14004AAAD
0x14004aaa3  mov     eax, dword ptr [rbp+37h+arg_0]
0x14004aaa6  cmp     r10d, eax
0x14004aaa9  cmova   eax, r10d
0x14004aaad  mov     dword ptr [rbp+37h+arg_0], 0
0x14004aab4  mov     rcx, r11
0x14004aab7  imul    rcx, rax; __int64
0x14004aabb  lea     rdx, [rbp+37h+arg_0]; unsigned int *
0x14004aabf  call    ?LongLongToUInt@@YAJ_JPEAI@Z; LongLongToUInt(__int64,uint *)
0x14004aac4  mov     ebx, eax
0x14004aac6  test    eax, eax
0x14004aac8  jns     short loc_14004AAD4
0x14004aaca  mov     edx, 13Fh
0x14004aacf  jmp     loc_14004B287
0x14004aad4  mov     rax, [rdi+10h]
0x14004aad8  mov     [rbp+37h+arg_8], rax
0x14004aadc  mov     [rbp+37h+var_78], 0
0x14004aae4  test    dword ptr [rdi+88h], 40000h
0x14004aaee  jz      loc_14004AB7C
0x14004aaf4  lea     rcx, [rdi+50h]; rclsid
0x14004aaf8  mov     rax, [rcx]
0x14004aafb  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x14004ab02  jnz     short loc_14004AB0F
0x14004ab04  mov     rax, [rcx+8]
0x14004ab08  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x14004ab0f  test    rax, rax
0x14004ab12  jz      short loc_14004AB7C
0x14004ab14  mov     [rbp+37h+var_78], 0
0x14004ab1c  lea     rax, [rbp+37h+var_78]
0x14004ab20  mov     [rsp+120h+ppv], rax; int
0x14004ab25  lea     r9, _GUID_c4e70434_407d_416b_94be_9717b79065fb; riid
0x14004ab2c  xor     edx, edx; pUnkOuter
0x14004ab2e  lea     r8d, [rdx+17h]; dwClsContext
0x14004ab32  call    cs:__imp_CoCreateInstance
0x14004ab38  mov     ebx, eax
0x14004ab3a  test    eax, eax
0x14004ab3c  jns     short loc_14004AB45
0x14004ab3e  mov     edx, 148h
0x14004ab43  jmp     short loc_14004AB64
0x14004ab45  mov     rcx, [rbp+37h+var_78]
0x14004ab49  mov     rax, [rcx]
0x14004ab4c  lea     rdx, [rdi+60h]
0x14004ab50  mov     rax, [rax+18h]
0x14004ab54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ab59  mov     ebx, eax
0x14004ab5b  test    eax, eax
0x14004ab5d  jns     short loc_14004AB7C
0x14004ab5f  mov     edx, 149h; void *
0x14004ab64  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004ab6b  mov     r9d, eax; char *
0x14004ab6e  mov     rcx, [rbp+3Fh]; this
0x14004ab72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ab77  jmp     loc_14004B272
0x14004ab7c  mov     [rbp+37h+var_98], 0
0x14004ab84  test    r15, r15
0x14004ab87  jz      short loc_14004AB9F
0x14004ab89  test    esi, esi
0x14004ab8b  jnz     short loc_14004AB96
0x14004ab8d  movups  xmm6, xmmword ptr cs:_GUID_3fd3bade_0ea7_4684_80f8_ff3609fa59ac.Data1
0x14004ab94  jmp     short loc_14004ABB3
0x14004ab96  movups  xmm6, xmmword ptr cs:_GUID_1a5582a4_990a_409a_b299_4413d56ff865.Data1
0x14004ab9d  jmp     short loc_14004ABB3
0x14004ab9f  test    esi, esi
0x14004aba1  jnz     short loc_14004ABAC
0x14004aba3  movups  xmm6, xmmword ptr cs:_GUID_9dba709c_b3e1_4013_95b7_5ed33a2e8561.Data1
0x14004abaa  jmp     short loc_14004ABB3
0x14004abac  movups  xmm6, xmmword ptr cs:_GUID_5bfd515e_4aba_4483_a1c5_6651b7110ab6.Data1
0x14004abb3  lea     rcx, [rbp+37h+var_98]
0x14004abb7  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x14004abbc  movups  xmm0, xmmword ptr [rdi+30h]
0x14004abc0  movdqu  [rbp+37h+var_60], xmm0
0x14004abc5  movdqa  [rbp+37h+Buf1], xmm6
0x14004abca  lea     rax, [rbp+37h+var_98]
0x14004abce  mov     [rsp+120h+ppv], rax; int
0x14004abd3  mov     r8d, [rdi+138h]
0x14004abda  lea     rdx, [rbp+37h+var_60]
0x14004abde  lea     rcx, [rbp+37h+Buf1]; Buf1
0x14004abe2  call    CreateCrossProcessServerEndpoint
0x14004abe7  mov     ebx, eax
0x14004abe9  test    eax, eax
0x14004abeb  jns     short loc_14004AC0A
0x14004abed  mov     rcx, [rbp+3Fh]; this
0x14004abf1  mov     r9d, eax; char *
0x14004abf4  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004abfb  mov     edx, 159h; void *
0x14004ac00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ac05  jmp     loc_14004B268
0x14004ac0a  mov     [rbp+37h+var_A0], 0
0x14004ac12  test    r15, r15
0x14004ac15  jz      loc_14004AE65
0x14004ac1b  mov     [rbp+37h+var_88], 0
0x14004ac23  lea     rdx, [rbp+37h+var_88]
0x14004ac27  mov     rcx, r15
0x14004ac2a  call    ??$GetFactoryFromAudioPumpDspResourceToken@UIDspCrossProcessAudioEndpointFactory@@@@YAJPEAUIUnknown@@PEAPEAUIDspCrossProcessAudioEndpointFactory@@@Z; GetFactoryFromAudioPumpDspResourceToken<IDspCrossProcessAudioEndpointFactory>(IUnknown *,IDspCrossProcessAudioEndpointFactory * *)
0x14004ac2f  mov     ebx, eax
0x14004ac31  test    eax, eax
0x14004ac33  jns     short loc_14004AC5C
0x14004ac35  mov     rcx, [rbp+3Fh]; this
0x14004ac39  mov     r9d, eax; char *
0x14004ac3c  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004ac43  mov     edx, 161h; void *
0x14004ac48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ac4d  nop
0x14004ac4e  lea     rcx, [rbp+37h+var_88]
0x14004ac52  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004ac57  jmp     loc_14004B25E
0x14004ac5c  mov     [rbp+37h+var_90], 0
0x14004ac64  mov     rcx, [rbp+37h+var_88]
0x14004ac68  mov     rax, [rcx]
0x14004ac6b  test    esi, esi
0x14004ac6d  jnz     short loc_14004ACAC
0x14004ac6f  xor     esi, esi
0x14004ac71  mov     [rbp+37h+var_90], rsi
0x14004ac75  lea     rdx, [rbp+37h+var_90]
0x14004ac79  mov     rax, [rax+18h]
0x14004ac7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ac82  mov     ebx, eax
0x14004ac84  test    eax, eax
0x14004ac86  jns     short loc_14004ACCC
0x14004ac88  mov     edx, 166h; void *
0x14004ac8d  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004ac94  mov     r9d, eax; char *
0x14004ac97  mov     rcx, [rbp+3Fh]; this
0x14004ac9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004aca0  nop
0x14004aca1  lea     rcx, [rbp+37h+var_90]
0x14004aca5  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004acaa  jmp     short loc_14004AC4E
0x14004acac  xor     esi, esi
0x14004acae  mov     [rbp+37h+var_90], rsi
0x14004acb2  lea     rdx, [rbp+37h+var_90]
0x14004acb6  mov     rax, [rax+20h]
0x14004acba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004acbf  mov     ebx, eax
0x14004acc1  test    eax, eax
0x14004acc3  jns     short loc_14004ACCC
0x14004acc5  mov     edx, 16Ah
0x14004acca  jmp     short loc_14004AC8D
0x14004accc  mov     [rbp+37h+var_80], rsi
0x14004acd0  mov     rcx, [rbp+37h+var_98]
0x14004acd4  mov     rax, [rcx]
0x14004acd7  lea     r8, [rbp+37h+var_80]
0x14004acdb  lea     rdx, _GUID_cb9fb9a6_9421_4b4b_b277_583d4d482547
0x14004ace2  mov     rax, [rax]
0x14004ace5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004acea  mov     ebx, eax
0x14004acec  test    eax, eax
0x14004acee  jns     short loc_14004AD14
0x14004acf0  mov     edx, 16Eh; void *
0x14004acf5  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004acfc  mov     r9d, eax; char *
0x14004acff  mov     rcx, [rbp+3Fh]; this
0x14004ad03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ad08  nop
0x14004ad09  lea     rcx, [rbp+37h+var_80]
0x14004ad0d  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004ad12  jmp     short loc_14004ACA1
0x14004ad14  mov     rcx, [rbp+37h+var_80]
0x14004ad18  mov     rax, [rcx]
0x14004ad1b  mov     rdx, [rbp+37h+var_90]
0x14004ad1f  mov     rax, [rax+18h]
0x14004ad23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ad28  mov     ebx, eax
0x14004ad2a  test    eax, eax
0x14004ad2c  jns     short loc_14004AD35
0x14004ad2e  mov     edx, 16Fh
0x14004ad33  jmp     short loc_14004ACF5
0x14004ad35  mov     rcx, [rbp+37h+var_A0]
0x14004ad39  mov     [rbp+37h+var_A0], rsi
0x14004ad3d  test    rcx, rcx
0x14004ad40  jz      short loc_14004AD4F
0x14004ad42  mov     rax, [rcx]
0x14004ad45  mov     rax, [rax+10h]
0x14004ad49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ad4e  nop
0x14004ad4f  mov     rcx, [rbp+37h+var_98]
0x14004ad53  mov     rax, [rcx]
0x14004ad56  lea     r8, [rbp+37h+var_A0]
0x14004ad5a  lea     rdx, _GUID_6b7f3699_f0ab_4184_bfd4_383e1520e0c9
0x14004ad61  mov     rax, [rax]
0x14004ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ad69  mov     ebx, eax
0x14004ad6b  test    eax, eax
0x14004ad6d  jns     short loc_14004AD79
0x14004ad6f  mov     edx, 171h
0x14004ad74  jmp     loc_14004ACF5
0x14004ad79  mov     rax, [rdi+40h]
0x14004ad7d  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x14004ad84  jnz     short loc_14004AD91
0x14004ad86  mov     rax, [rdi+48h]
0x14004ad8a  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x14004ad91  test    rax, rax
0x14004ad94  jz      short loc_14004ADBA
0x14004ad96  mov     rcx, [rbp+37h+var_A0]
0x14004ad9a  mov     rax, [rcx]
0x14004ad9d  lea     rdx, [rdi+60h]
0x14004ada1  mov     rax, [rax+18h]
0x14004ada5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004adaa  mov     ebx, eax
0x14004adac  test    eax, eax
0x14004adae  jns     short loc_14004ADBA
0x14004adb0  mov     edx, 175h
0x14004adb5  jmp     loc_14004ACF5
0x14004adba  mov     qword ptr [rbp+37h+var_60], rsi
0x14004adbe  mov     rcx, [rbp+37h+var_A0]
0x14004adc2  mov     rax, [rcx]
0x14004adc5  lea     r8, [rbp+37h+var_60]
0x14004adc9  lea     rdx, _GUID_fc48820a_f18b_41c6_83aa_e9fcee39e429
0x14004add0  mov     rax, [rax]
0x14004add3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004add8  test    eax, eax
0x14004adda  js      short loc_14004AE1C
0x14004addc  mov     rcx, qword ptr [rbp+37h+var_60]
0x14004ade0  mov     rax, [rcx]
0x14004ade3  mov     edx, [rdi+0Ch]
0x14004ade6  mov     rax, [rax+28h]
0x14004adea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004adef  mov     ebx, eax
0x14004adf1  test    eax, eax
0x14004adf3  jns     short loc_14004AE1C
0x14004adf5  mov     rcx, [rbp+3Fh]; this
0x14004adf9  mov     r9d, eax; char *
0x14004adfc  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004ae03  mov     edx, 17Eh; void *
0x14004ae08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ae0d  nop
0x14004ae0e  lea     rcx, [rbp+37h+var_60]
0x14004ae12  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004ae17  jmp     loc_14004AD09
0x14004ae1c  lea     rcx, [rbp+37h+var_60]
0x14004ae20  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004ae25  nop
0x14004ae26  lea     rcx, [rbp+37h+var_80]
0x14004ae2a  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004ae2f  nop
0x14004ae30  lea     rcx, [rbp+37h+var_90]
0x14004ae34  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004ae39  nop
0x14004ae3a  lea     rcx, [rbp+37h+var_88]
0x14004ae3e  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004ae43  test    r14d, r14d
0x14004ae46  jz      loc_14004B046
0x14004ae4c  cmp     r14d, 1
0x14004ae50  jz      loc_14004AF0D
0x14004ae56  mov     ebx, 8000FFFFh
  ... truncated ...
```

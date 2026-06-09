# CEndpointInstance::CreateSpatialStreamEndpointInstance(SYSTEM_AUDIO_STREAM_DESCRIPTOR *,__int64,uint,IUnknown *,SYSTEM_AUDIO_STREAM *,ICrossProcessMemory * *,ICrossProcessEvent * *,CEndpointInstance * *)

- ea: `0x14004a178`
- end: `0x14004a9cb`
- name: `?CreateSpatialStreamEndpointInstance@CEndpointInstance@@SAJPEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@_JIPEAUIUnknown@@PEAUSYSTEM_AUDIO_STREAM@@PEAPEAUICrossProcessMemory@@PEAPEAUICrossProcessEvent@@PEAPEAV1@@Z`
- size: `2131`
- prototype: `__int64 __fastcall(struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *, __int64, unsigned int, struct IUnknown *, struct SYSTEM_AUDIO_STREAM *, struct ICrossProcessMemory **, struct ICrossProcessEvent **, struct CEndpointInstance **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004a090`

## callees

- `0x140008124`
- `0x14000a39c`
- `0x14000c33c`
- `0x140019830`
- `0x1400310a0`
- `0x140032d5c`
- `0x140035664`
- `0x14004a178`
- `0x14004e808`
- `0x1400516e8`
- `0x140053040`
- `0x14005d0e0`
- `0x14005d148`
- `0x14005e168`
- `0x1400a9ee0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004a2df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004a71b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004a2df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004a71b`

## pseudocode

```c
__int64 __fastcall CEndpointInstance::CreateSpatialStreamEndpointInstance(
        struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *a1,
        __int64 a2,
        unsigned int a3,
        struct IUnknown *a4,
        struct SYSTEM_AUDIO_STREAM *a5,
        struct ICrossProcessMemory **a6,
        struct ICrossProcessEvent **a7,
        struct CEndpointInstance **a8)
{
  unsigned int v9; // edi
  __int64 v11; // r14
  int v12; // ebx
  unsigned int v13; // r11d
  __int64 v14; // rdx
  unsigned int v15; // r10d
  int v16; // r15d
  unsigned int v17; // r14d
  HRESULT v18; // eax
  __int64 v19; // rdx
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, _QWORD *); // rbx
  GUID v22; // xmm6
  int v23; // eax
  int FactoryFromAudioPumpDspResource; // eax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  LPVOID v29; // rcx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  HRESULT v33; // eax
  __int64 v34; // rdx
  unsigned __int16 *v35; // r15
  int v36; // eax
  __int64 v37; // rdx
  CEndpointInstance *v38; // rax
  CEndpointInstance *v39; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID v43; // [rsp+30h] [rbp-D0h] BYREF
  struct IAudioEndpointRT *v44; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v50; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v51[2]; // [rsp+70h] [rbp-90h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-80h] BYREF
  __int128 v53; // [rsp+90h] [rbp-70h] BYREF
  struct ICrossProcessMemory **v54; // [rsp+A0h] [rbp-60h]
  struct CEndpointInstance **v55; // [rsp+A8h] [rbp-58h]
  struct ICrossProcessEvent **v56; // [rsp+B0h] [rbp-50h]
  int v57; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v58; // [rsp+C8h] [rbp-38h]
  __int128 v59; // [rsp+D8h] [rbp-28h]
  __int128 v60; // [rsp+E8h] [rbp-18h]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  int v62; // [rsp+100h] [rbp+0h]
  __int64 v63; // [rsp+108h] [rbp+8h]
  unsigned int v64[4]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v65; // [rsp+120h] [rbp+20h]
  LPVOID v66; // [rsp+128h] [rbp+28h]
  __int64 v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  __int64 v69; // [rsp+140h] [rbp+40h]
  __int128 v70; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v9 = a3;
  LODWORD(v45) = a3;
  v54 = a6;
  v56 = a7;
  v55 = a8;
  v11 = *((_QWORD *)a1 + 16);
  v48 = (unsigned __int16 *)v11;
  LODWORD(v43) = 0;
  v12 = HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE(
          a2,
          *(_DWORD *)(v11 + 8),
          *(unsigned __int16 *)(v11 + 12),
          (unsigned int *)&v43);
  if ( v12 >= 0 )
  {
    if ( v9 + (unsigned int)v43 < (unsigned int)v43 )
    {
      v12 = -2147024362;
      v14 = 566;
      goto LABEL_3;
    }
    LODWORD(v43) = 0;
    v12 = HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE(*((_QWORD *)a1 + 3), *(_DWORD *)(v11 + 8), v13, (unsigned int *)&v43);
    if ( v12 < 0 )
    {
      v14 = 570;
      goto LABEL_3;
    }
    v16 = *(_DWORD *)a1;
    v17 = (unsigned int)v43;
    if ( *((_DWORD *)a1 + 2) != 1 && v15 > (unsigned int)v43 )
      v17 = v15;
    v49 = *((_QWORD *)a1 + 2);
    v51[0] = 0;
    if ( *((_QWORD *)a1 + 10) != *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
      || *((_QWORD *)a1 + 11) != *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    {
      v50 = 0;
      v18 = CoCreateInstance((const IID *const)a1 + 5, 0, 0x17u, &GUID_c4e70434_407d_416b_94be_9717b79065fb, &v50);
      v12 = v18;
      if ( v18 < 0 )
      {
        v19 = 583;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)v18,
          ppv);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
LABEL_85:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v51);
        return (unsigned int)v12;
      }
      v18 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v50 + 24LL))(v50, (char *)a1 + 96);
      v12 = v18;
      if ( v18 < 0 )
      {
        v19 = 584;
        goto LABEL_19;
      }
      v20 = v50;
      v21 = *(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)v50 + 32LL);
      wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(v51);
      v18 = v21(v20, v51);
      v12 = v18;
      if ( v18 < 0 )
      {
        v19 = 585;
        goto LABEL_19;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
      v9 = v45;
    }
    if ( v16 )
    {
      v12 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
      goto LABEL_85;
    }
    v44 = 0;
    if ( a4 )
      v22 = GUID_89965474_473f_4fe5_a282_80ba8b851b45;
    else
      v22 = GUID_6b78656b_c0e1_4190_83ee_ef91c2908926;
    wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(&v44);
    v53 = *((_OWORD *)a1 + 3);
    Buf1 = v22;
    v23 = CreateSpatialCrossProcessServerEndpoint(&Buf1, (__int64)&v44);
    v12 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)(unsigned int)v23,
        ppva);
LABEL_28:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
      goto LABEL_85;
    }
    v43 = 0;
    if ( a4 )
    {
      v46 = 0;
      FactoryFromAudioPumpDspResource = GetFactoryFromAudioPumpDspResourceToken<IDspCrossProcessAudioEndpointFactory>(
                                          a4,
                                          &v46);
      v12 = FactoryFromAudioPumpDspResource;
      if ( FactoryFromAudioPumpDspResource < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x257,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)FactoryFromAudioPumpDspResource,
          ppva);
LABEL_32:
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v46);
LABEL_33:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        goto LABEL_28;
      }
      v45 = 0;
      v25 = *v46;
      v45 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v25 + 40))(v46, &v45);
      v12 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x25A,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)v26,
          ppva);
LABEL_36:
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v45);
        goto LABEL_32;
      }
      v47 = 0;
      v27 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int64 *))v44->lpVtbl->QueryInterface)(
              v44,
              &GUID_cb9fb9a6_9421_4b4b_b277_583d4d482547,
              &v47);
      v12 = v27;
      if ( v27 < 0 )
      {
        v28 = 605;
LABEL_39:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v28,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)v27,
          ppva);
LABEL_40:
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v47);
        goto LABEL_36;
      }
      v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 24LL))(v47, v45);
      v12 = v27;
      if ( v27 < 0 )
      {
        v28 = 606;
        goto LABEL_39;
      }
      v29 = v43;
      v43 = 0;
      if ( v29 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
      v27 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, LPVOID *))v44->lpVtbl->QueryInterface)(
              v44,
              &GUID_6b7f3699_f0ab_4184_bfd4_383e1520e0c9,
              &v43);
      v12 = v27;
      if ( v27 < 0 )
      {
        v28 = 608;
        goto LABEL_39;
      }
      if ( *((_QWORD *)a1 + 8) != *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
        || *((_QWORD *)a1 + 9) != *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
      {
        v27 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v43 + 24LL))(v43, (char *)a1 + 96);
        v12 = v27;
        if ( v27 < 0 )
        {
          v28 = 612;
          goto LABEL_39;
        }
      }
      v49 = 0;
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v43)(
             v43,
             &GUID_fc48820a_f18b_41c6_83aa_e9fcee39e429,
             &v49) >= 0 )
      {
        v30 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 40LL))(v49, *((unsigned int *)a1 + 3));
        v12 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26D,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
            (const char *)(unsigned int)v30,
            ppva);
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v49);
          goto LABEL_40;
        }
      }
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v49);
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v47);
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v45);
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v46);
LABEL_55:
      *(_QWORD *)&Buf1.Data1 = 0;
      *(_QWORD *)&v53 = 0;
      v31 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int128 *))v44->lpVtbl->QueryInterface)(
              v44,
              &GUID_51a95308_7091_4c68_9bff_af559a414bea,
              &v53);
      v12 = v31;
      if ( v31 < 0 )
      {
        v32 = 646;
LABEL_57:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)v31,
          ppva);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
LABEL_58:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Buf1);
        goto LABEL_33;
      }
      memset_0(&v57, 0, 0x98u);
      v57 = 152;
      v58 = *((_OWORD *)a1 + 12);
      v59 = *((_OWORD *)a1 + 13);
      v60 = *((_OWORD *)a1 + 14);
      v61 = *((_QWORD *)a1 + 30);
      v62 = 0;
      v63 = *((_QWORD *)a1 + 4);
      v35 = v48;
      v31 = LongLongToUInt(v17 * (unsigned __int64)v48[6], v64);
      v12 = v31;
      if ( v31 < 0 )
      {
        v32 = 653;
        goto LABEL_57;
      }
      v64[1] = v9;
      v64[2] = *((_DWORD *)a1 + 3);
      v65 = v51[0];
      v67 = 0;
      v68 = *((_QWORD *)a1 + 16);
      v69 = *((_QWORD *)a1 + 14);
      v70 = *(_OWORD *)((char *)a1 + 172);
      v66 = v43;
      v31 = (*(__int64 (__fastcall **)(_QWORD, int *, struct ICrossProcessMemory **))(*(_QWORD *)v53 + 24LL))(
              v53,
              &v57,
              v54);
      v12 = v31;
      if ( v31 < 0 )
      {
        v32 = 663;
        goto LABEL_57;
      }
      *(GUID *)a5 = GUID_9371e7ff_df2d_4962_9585_40424d054550;
      *((_DWORD *)a5 + 234) = 0;
      *((_DWORD *)a5 + 4) = v17 * v35[6];
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
      if ( a4 )
      {
        v48 = 0;
        v36 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, unsigned __int16 **))v44->lpVtbl->QueryInterface)(
                v44,
                &GUID_cb9fb9a6_9421_4b4b_b277_583d4d482547,
                &v48);
        v12 = v36;
        if ( v36 < 0 )
        {
          v37 = 682;
LABEL_75:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v37,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
            (const char *)(unsigned int)v36,
            ppva);
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v48);
          goto LABEL_58;
        }
        v36 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v48 + 32LL))(v48, v9);
        v12 = v36;
        if ( v36 < 0 )
        {
          v37 = 683;
          goto LABEL_75;
        }
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v48);
      }
      v38 = (CEndpointInstance *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      v54 = (struct ICrossProcessMemory **)v38;
      if ( v38 )
        v39 = CEndpointInstance::CEndpointInstance(v38, v44, 0);
      else
        v39 = 0;
      if ( v39 )
      {
        v54 = 0;
        *v55 = v39;
        wil::com_ptr_t<ICrossProcessEvent,wil::err_returncode_policy>::copy_to<ICrossProcessEvent>(v51, v56);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Buf1);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
        v12 = 0;
        goto LABEL_85;
      }
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B2,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)0x8007000ELL,
        ppva);
      goto LABEL_58;
    }
    if ( *((_QWORD *)a1 + 8) == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
      && *((_QWORD *)a1 + 9) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    {
      v43 = 0;
      v33 = Microsoft::WRL::Details::MakeAndInitialize<CSectionBasedCrossProcessMemoryManager,ICrossProcessMemoryManager,unsigned short const * &>(
              &v43,
              &v49);
      v12 = v33;
      if ( v33 >= 0 )
        goto LABEL_55;
      v34 = 635;
    }
    else
    {
      v43 = 0;
      v33 = CoCreateInstance((const IID *const)a1 + 4, 0, 0x17u, &GUID_6b7f3699_f0ab_4184_bfd4_383e1520e0c9, &v43);
      v12 = v33;
      if ( v33 >= 0 )
      {
        v33 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v43 + 24LL))(v43, (char *)a1 + 96);
        v12 = v33;
        if ( v33 >= 0 )
          goto LABEL_55;
        v34 = 630;
      }
      else
      {
        v34 = 629;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
      (const char *)(unsigned int)v33,
      ppva);
    goto LABEL_33;
  }
  v14 = 565;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
    (const char *)(unsigned int)v12,
    ppv);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14004a178  mov     rax, rsp
0x14004a17b  mov     [rax+10h], rbx
0x14004a17f  push    rbp
0x14004a180  push    rsi
0x14004a181  push    rdi
0x14004a182  push    r12
0x14004a184  push    r13
0x14004a186  push    r14
0x14004a188  push    r15
0x14004a18a  lea     rbp, [rsp-80h]
0x14004a18f  sub     rsp, 180h
0x14004a196  movaps  xmmword ptr [rax-48h], xmm6
0x14004a19a  mov     rax, cs:__security_cookie
0x14004a1a1  xor     rax, rsp
0x14004a1a4  mov     [rbp+0B0h+var_50], rax
0x14004a1a8  mov     r12, r9
0x14004a1ab  mov     edi, r8d
0x14004a1ae  mov     dword ptr [rsp+1B0h+var_170], r8d
0x14004a1b3  mov     rax, rdx
0x14004a1b6  mov     rsi, rcx
0x14004a1b9  mov     r13, [rbp+0B0h+arg_20]
0x14004a1c0  mov     rcx, [rbp+0B0h+arg_28]
0x14004a1c7  mov     [rbp+0B0h+var_110], rcx
0x14004a1cb  mov     rcx, [rbp+0B0h+arg_30]
0x14004a1d2  mov     [rbp+0B0h+var_100], rcx
0x14004a1d6  mov     rcx, [rbp+0B0h+arg_38]
0x14004a1dd  mov     [rbp+0B0h+var_108], rcx
0x14004a1e1  mov     r14, [rsi+80h]
0x14004a1e8  mov     [rsp+1B0h+var_158], r14
0x14004a1ed  mov     dword ptr [rsp+1B0h+var_180], 0
0x14004a1f5  movzx   r11d, word ptr [r14+0Ch]
0x14004a1fa  lea     r9, [rsp+1B0h+var_180]; unsigned int *
0x14004a1ff  mov     r8d, r11d; unsigned int
0x14004a202  mov     edx, [r14+8]; unsigned int
0x14004a206  mov     rcx, rax; __int64
0x14004a209  call    ?HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE@@YAJ_JIIPEAI@Z; HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE(__int64,uint,uint,uint *)
0x14004a20e  mov     ebx, eax
0x14004a210  test    eax, eax
0x14004a212  jns     short loc_14004A234
0x14004a214  mov     edx, 235h; void *
0x14004a219  mov     rcx, [rbp+0B8h]; this
0x14004a220  mov     r9d, ebx; char *
0x14004a223  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a22a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a22f  jmp     loc_14004A99D
0x14004a234  mov     eax, dword ptr [rsp+1B0h+var_180]
0x14004a238  lea     r10d, [rdi+rax]
0x14004a23c  cmp     r10d, eax
0x14004a23f  jnb     short loc_14004A24D
0x14004a241  mov     ebx, 80070216h
0x14004a246  mov     edx, 236h
0x14004a24b  jmp     short loc_14004A219
0x14004a24d  mov     dword ptr [rsp+1B0h+var_180], 0
0x14004a255  lea     r9, [rsp+1B0h+var_180]; unsigned int *
0x14004a25a  mov     r8d, r11d; unsigned int
0x14004a25d  mov     edx, [r14+8]; unsigned int
0x14004a261  mov     rcx, [rsi+18h]; __int64
0x14004a265  call    ?HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE@@YAJ_JIIPEAI@Z; HNSTIME_BYTERATE_TO_FRAMES_DOUBLE_SAFE(__int64,uint,uint,uint *)
0x14004a26a  mov     ebx, eax
0x14004a26c  test    eax, eax
0x14004a26e  jns     short loc_14004A277
0x14004a270  mov     edx, 23Ah
0x14004a275  jmp     short loc_14004A219
0x14004a277  mov     r15d, [rsi]
0x14004a27a  mov     r14d, dword ptr [rsp+1B0h+var_180]
0x14004a27f  cmp     dword ptr [rsi+8], 1
0x14004a283  jz      short loc_14004A28C
0x14004a285  cmp     r10d, r14d
0x14004a288  cmova   r14d, r10d
0x14004a28c  mov     rax, [rsi+10h]
0x14004a290  mov     [rsp+1B0h+var_150], rax
0x14004a295  mov     [rsp+1B0h+var_140], 0
0x14004a29e  lea     rcx, [rsi+50h]; rclsid
0x14004a2a2  mov     rax, [rcx]
0x14004a2a5  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x14004a2ac  jnz     short loc_14004A2BF
0x14004a2ae  mov     rax, [rcx+8]
0x14004a2b2  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x14004a2b9  jz      loc_14004A379
0x14004a2bf  mov     [rsp+1B0h+var_148], 0
0x14004a2c8  lea     rax, [rsp+1B0h+var_148]
0x14004a2cd  mov     qword ptr [rsp+1B0h+ppv], rax; int
0x14004a2d2  lea     r9, _GUID_c4e70434_407d_416b_94be_9717b79065fb; riid
0x14004a2d9  xor     edx, edx; pUnkOuter
0x14004a2db  lea     r8d, [rdx+17h]; dwClsContext
0x14004a2df  call    cs:__imp_CoCreateInstance
0x14004a2e5  mov     ebx, eax
0x14004a2e7  test    eax, eax
0x14004a2e9  jns     short loc_14004A2F2
0x14004a2eb  mov     edx, 247h
0x14004a2f0  jmp     short loc_14004A345
0x14004a2f2  mov     rcx, [rsp+1B0h+var_148]
0x14004a2f7  mov     rax, [rcx]
0x14004a2fa  lea     rdx, [rsi+60h]
0x14004a2fe  mov     rax, [rax+18h]
0x14004a302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a307  mov     ebx, eax
0x14004a309  test    eax, eax
0x14004a30b  jns     short loc_14004A314
0x14004a30d  mov     edx, 248h
0x14004a312  jmp     short loc_14004A345
0x14004a314  mov     rdi, [rsp+1B0h+var_148]
0x14004a319  mov     rax, [rdi]
0x14004a31c  mov     rbx, [rax+20h]
0x14004a320  lea     rcx, [rsp+1B0h+var_140]
0x14004a325  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x14004a32a  lea     rdx, [rsp+1B0h+var_140]
0x14004a32f  mov     rcx, rdi
0x14004a332  mov     rax, rbx
0x14004a335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a33a  mov     ebx, eax
0x14004a33c  test    eax, eax
0x14004a33e  jns     short loc_14004A36B
0x14004a340  mov     edx, 249h; void *
0x14004a345  mov     r9d, eax; char *
0x14004a348  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a34f  mov     rcx, [rbp+0B8h]; this
0x14004a356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a35b  nop
0x14004a35c  lea     rcx, [rsp+1B0h+var_148]
0x14004a361  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a366  jmp     loc_14004A993
0x14004a36b  lea     rcx, [rsp+1B0h+var_148]
0x14004a370  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a375  mov     edi, dword ptr [rsp+1B0h+var_170]
0x14004a379  test    r15d, r15d
0x14004a37c  jz      short loc_14004A3A3
0x14004a37e  mov     rcx, [rbp+0B8h]; this
0x14004a385  mov     ebx, 8000FFFFh
0x14004a38a  mov     r9d, ebx; char *
0x14004a38d  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a394  mov     edx, 24Ch; void *
0x14004a399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a39e  jmp     loc_14004A993
0x14004a3a3  xor     r15d, r15d
0x14004a3a6  mov     [rsp+1B0h+var_178], r15
0x14004a3ab  test    r12, r12
0x14004a3ae  jz      short loc_14004A3B9
0x14004a3b0  movups  xmm6, xmmword ptr cs:_GUID_89965474_473f_4fe5_a282_80ba8b851b45.Data1
0x14004a3b7  jmp     short loc_14004A3C0
0x14004a3b9  movups  xmm6, xmmword ptr cs:_GUID_6b78656b_c0e1_4190_83ee_ef91c2908926.Data1
0x14004a3c0  lea     rcx, [rsp+1B0h+var_178]
0x14004a3c5  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x14004a3ca  movups  xmm0, xmmword ptr [rsi+30h]
0x14004a3ce  movdqu  [rbp+0B0h+var_120], xmm0
0x14004a3d3  movdqa  [rbp+0B0h+Buf1], xmm6
0x14004a3d8  lea     rax, [rsp+1B0h+var_178]
0x14004a3dd  mov     qword ptr [rsp+1B0h+ppv], rax; int
0x14004a3e2  mov     r8d, [rsi+138h]
0x14004a3e9  lea     rdx, [rbp+0B0h+var_120]
0x14004a3ed  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x14004a3f1  call    CreateSpatialCrossProcessServerEndpoint
0x14004a3f6  mov     ebx, eax
0x14004a3f8  test    eax, eax
0x14004a3fa  jns     short loc_14004A427
0x14004a3fc  mov     rcx, [rbp+0B8h]; this
0x14004a403  mov     r9d, eax; char *
0x14004a406  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a40d  mov     edx, 250h; void *
0x14004a412  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a417  nop
0x14004a418  lea     rcx, [rsp+1B0h+var_178]
0x14004a41d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a422  jmp     loc_14004A993
0x14004a427  mov     [rsp+1B0h+var_180], r15
0x14004a42c  test    r12, r12
0x14004a42f  jz      loc_14004A6BD
0x14004a435  mov     [rsp+1B0h+var_168], r15
0x14004a43a  lea     rdx, [rsp+1B0h+var_168]
0x14004a43f  mov     rcx, r12
0x14004a442  call    ??$GetFactoryFromAudioPumpDspResourceToken@UIDspCrossProcessAudioEndpointFactory@@@@YAJPEAUIUnknown@@PEAPEAUIDspCrossProcessAudioEndpointFactory@@@Z; GetFactoryFromAudioPumpDspResourceToken<IDspCrossProcessAudioEndpointFactory>(IUnknown *,IDspCrossProcessAudioEndpointFactory * *)
0x14004a447  mov     ebx, eax
0x14004a449  test    eax, eax
0x14004a44b  jns     short loc_14004A480
0x14004a44d  mov     rcx, [rbp+0B8h]; this
0x14004a454  mov     r9d, eax; char *
0x14004a457  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a45e  mov     edx, 257h; void *
0x14004a463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a468  nop
0x14004a469  lea     rcx, [rsp+1B0h+var_168]
0x14004a46e  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004a473  nop
0x14004a474  lea     rcx, [rsp+1B0h+var_180]
0x14004a479  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a47e  jmp     short loc_14004A418
0x14004a480  mov     [rsp+1B0h+var_170], r15
0x14004a485  mov     rcx, [rsp+1B0h+var_168]
0x14004a48a  mov     rax, [rcx]
0x14004a48d  mov     [rsp+1B0h+var_170], r15
0x14004a492  lea     rdx, [rsp+1B0h+var_170]
0x14004a497  mov     rax, [rax+28h]
0x14004a49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a4a0  mov     ebx, eax
0x14004a4a2  test    eax, eax
0x14004a4a4  jns     short loc_14004A4CE
0x14004a4a6  mov     rcx, [rbp+0B8h]; this
0x14004a4ad  mov     r9d, eax; char *
0x14004a4b0  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a4b7  mov     edx, 25Ah; void *
0x14004a4bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a4c1  nop
0x14004a4c2  lea     rcx, [rsp+1B0h+var_170]
0x14004a4c7  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004a4cc  jmp     short loc_14004A469
0x14004a4ce  mov     [rsp+1B0h+var_160], r15
0x14004a4d3  mov     rcx, [rsp+1B0h+var_178]
0x14004a4d8  mov     rax, [rcx]
0x14004a4db  lea     r8, [rsp+1B0h+var_160]
0x14004a4e0  lea     rdx, _GUID_cb9fb9a6_9421_4b4b_b277_583d4d482547
0x14004a4e7  mov     rax, [rax]
0x14004a4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a4ef  mov     ebx, eax
0x14004a4f1  test    eax, eax
0x14004a4f3  jns     short loc_14004A51D
0x14004a4f5  mov     edx, 25Dh; void *
0x14004a4fa  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a501  mov     r9d, eax; char *
0x14004a504  mov     rcx, [rbp+0B8h]; this
0x14004a50b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a510  nop
0x14004a511  lea     rcx, [rsp+1B0h+var_160]
0x14004a516  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004a51b  jmp     short loc_14004A4C2
0x14004a51d  mov     rcx, [rsp+1B0h+var_160]
0x14004a522  mov     rax, [rcx]
0x14004a525  mov     rdx, [rsp+1B0h+var_170]
0x14004a52a  mov     rax, [rax+18h]
0x14004a52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a533  mov     ebx, eax
0x14004a535  test    eax, eax
0x14004a537  jns     short loc_14004A540
0x14004a539  mov     edx, 25Eh
0x14004a53e  jmp     short loc_14004A4FA
0x14004a540  mov     rcx, [rsp+1B0h+var_180]
0x14004a545  mov     [rsp+1B0h+var_180], r15
0x14004a54a  test    rcx, rcx
0x14004a54d  jz      short loc_14004A55C
0x14004a54f  mov     rax, [rcx]
0x14004a552  mov     rax, [rax+10h]
0x14004a556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a55b  nop
0x14004a55c  mov     rcx, [rsp+1B0h+var_178]
0x14004a561  mov     rax, [rcx]
0x14004a564  lea     r8, [rsp+1B0h+var_180]
0x14004a569  lea     rdx, _GUID_6b7f3699_f0ab_4184_bfd4_383e1520e0c9
0x14004a570  mov     rax, [rax]
0x14004a573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a578  mov     ebx, eax
0x14004a57a  test    eax, eax
0x14004a57c  jns     short loc_14004A588
0x14004a57e  mov     edx, 260h
0x14004a583  jmp     loc_14004A4FA
0x14004a588  mov     rax, [rsi+40h]
0x14004a58c  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x14004a593  jnz     short loc_14004A5A2
0x14004a595  mov     rax, [rsi+48h]
0x14004a599  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x14004a5a0  jz      short loc_14004A5C7
0x14004a5a2  mov     rcx, [rsp+1B0h+var_180]
0x14004a5a7  mov     rax, [rcx]
0x14004a5aa  lea     rdx, [rsi+60h]
0x14004a5ae  mov     rax, [rax+18h]
0x14004a5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a5b7  mov     ebx, eax
0x14004a5b9  test    eax, eax
0x14004a5bb  jns     short loc_14004A5C7
0x14004a5bd  mov     edx, 264h
0x14004a5c2  jmp     loc_14004A4FA
0x14004a5c7  mov     [rsp+1B0h+var_150], r15
0x14004a5cc  mov     rcx, [rsp+1B0h+var_180]
0x14004a5d1  mov     rax, [rcx]
0x14004a5d4  lea     r8, [rsp+1B0h+var_150]
0x14004a5d9  lea     rdx, _GUID_fc48820a_f18b_41c6_83aa_e9fcee39e429
0x14004a5e0  mov     rax, [rax]
0x14004a5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a5e8  test    eax, eax
0x14004a5ea  js      short loc_14004A631
0x14004a5ec  mov     rcx, [rsp+1B0h+var_150]
0x14004a5f1  mov     rax, [rcx]
0x14004a5f4  mov     edx, [rsi+0Ch]
0x14004a5f7  mov     rax, [rax+28h]
0x14004a5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a600  mov     ebx, eax
0x14004a602  test    eax, eax
0x14004a604  jns     short loc_14004A631
0x14004a606  mov     rcx, [rbp+0B8h]; this
0x14004a60d  mov     r9d, eax; char *
0x14004a610  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004a617  mov     edx, 26Dh; void *
0x14004a61c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a621  nop
0x14004a622  lea     rcx, [rsp+1B0h+var_150]
0x14004a627  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004a62c  jmp     loc_14004A511
0x14004a631  lea     rcx, [rsp+1B0h+var_150]
0x14004a636  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14004a63b  nop
0x14004a63c  lea     rcx, [rsp+1B0h+var_160]
0x14004a641  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
  ... truncated ...
```

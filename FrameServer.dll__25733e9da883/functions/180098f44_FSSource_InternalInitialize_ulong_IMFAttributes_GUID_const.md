# FSSource::InternalInitialize(ulong,IMFAttributes *,_GUID const &)

- ea: `0x180098f44`
- end: `0x180099469`
- name: `?InternalInitialize@FSSource@@IEAAJKPEAUIMFAttributes@@AEBU_GUID@@@Z`
- size: `1317`
- prototype: `int(FSSource *__hidden this, unsigned int, struct IMFAttributes *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009467c`

## callees

- `0x1800041f0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x180009b5c`
- `0x180009fac`
- `0x18000a880`
- `0x18000a91c`
- `0x180017858`
- `0x18002836c`
- `0x18004d714`
- `0x18004da70`
- `0x1800525a4`
- `0x180073610`
- `0x18009167c`
- `0x180098f44`
- `0x1800a5f20`
- `0x1800b8590`
- `0x1800b93b8`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFGetSensorOrientation` at `0x18009928a`
- `MFSENSORGROUP!MFGetSensorOrientation` at `0x18009928a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099407`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099414`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009938c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009938c`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18009930c`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18009930c`

## pseudocode

```c
__int64 __fastcall FSSource::InternalInitialize(
        FSSource *this,
        const struct std::nothrow_t *a2,
        struct IMFAttributes *a3,
        const struct _GUID *a4)
{
  char v4; // al
  int v7; // r12d
  __int64 **v9; // r14
  GuidTrace *v10; // rax
  const char *String; // rdi
  char v12; // bl
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  __int64 (*v17)(void); // rax
  __int64 v18; // rax
  HRESULT ProcessActivities; // eax
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int64 **v22; // r15
  const WCHAR *v23; // rax
  __int64 *v24; // rdi
  unsigned int v25; // r12d
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v27; // rdx
  void *v28; // rcx
  unsigned __int8 *v29; // rbx
  const WCHAR *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  const void *v33; // rbx
  unsigned __int64 v34; // rax
  unsigned int v35; // r8d
  FSSourceUtils *v36; // rcx
  void **v37; // r8
  int Instance; // eax
  __int64 v39; // rdx
  void *v41; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v42[96]; // [rsp+48h] [rbp-60h] BYREF
  unsigned int v43; // [rsp+B0h] [rbp+8h] BYREF
  int v44; // [rsp+B8h] [rbp+10h]

  v44 = (int)a2;
  v4 = 0;
  v43 = 0;
  v7 = (int)a2;
  v9 = (__int64 **)((char *)this + 256);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v10 = GuidTrace::GuidTrace((GuidTrace *)v42, a4);
    String = GuidTrace::GetString(v10);
    v12 = (*(__int64 (__fastcall **)(__int64 *))(**v9 + 24))(*v9);
    v13 = (*(__int64 (__fastcall **)(__int64 *))(**v9 + 32))(*v9);
    WPP_SF_qSds(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, v12, (__int64)String);
    v4 = 1;
  }
  if ( (v4 & 1) != 0 )
    FSString::~FSString((FSString *)v42, a2);
  if ( (*(unsigned int (__fastcall **)(__int64 *))(**v9 + 24))(*v9) == 2
    && *(_DWORD *)(*(__int64 (__fastcall **)(__int64 *))(**v9 + 96))(*v9) == 1 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *))(**v9 + 96))(*v9);
    if ( !memcmp_0((const void *)(v14 + 32), &MF_SENSORTRANSFORM_BUILTINST_MULTIPLEXOR, 0x10u) )
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 500, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this);
      *((_BYTE *)this + 169) = 1;
      v22 = (__int64 **)((char *)this + 256);
      goto LABEL_34;
    }
    v9 = (__int64 **)((char *)this + 256);
  }
  v15 = (*(__int64 (__fastcall **)(__int64 *))(**v9 + 24))(*v9);
  v16 = **v9;
  if ( v15 == 3 )
  {
    v17 = *(__int64 (**)(void))(v16 + 144);
    v43 = 0;
    if ( v17() )
    {
      v18 = (*(__int64 (__fastcall **)(__int64 *))(**v9 + 144))(*v9);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 856,
                               v18) )
      {
        ProcessActivities = -2147024882;
        v20 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_48;
        v21 = 501;
        goto LABEL_14;
      }
      v22 = (__int64 **)((char *)this + 256);
    }
    else
    {
      v22 = v9;
    }
    v23 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(**v9 + 40))(*v9);
    if ( (int)FSGetDeviceInterfaceProperty2(
                v23,
                (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceInfo,
                0x12u,
                0,
                0,
                &v43) >= 0 )
    {
      v24 = (__int64 *)((char *)this + 520);
      v25 = (v43 >> 1) + 1;
      unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v41, v25);
      wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(
        (void **)this + 65,
        unique);
      v28 = v41;
      v41 = 0;
      if ( v28 )
        operator delete(v28, v27);
      else
        v22 = v9;
      v29 = (unsigned __int8 *)*v24;
      if ( !*v24 )
      {
        ProcessActivities = -2147024882;
        v20 = -2147024882;
        if ( g_wppLevels )
        {
          v21 = 502;
LABEL_14:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
            this,
            ProcessActivities);
          goto LABEL_48;
        }
        goto LABEL_48;
      }
      v30 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(**v22 + 40))(*v22);
      ProcessActivities = FSGetDeviceInterfaceProperty2(
                            v30,
                            (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceInfo,
                            0x12u,
                            v29,
                            2 * v25,
                            &v43);
      v20 = ProcessActivities;
      if ( ProcessActivities < 0 )
      {
        if ( g_wppLevels )
        {
          v21 = 503;
          goto LABEL_14;
        }
LABEL_48:
        if ( byte_18010EC4D )
        {
          v39 = 509;
LABEL_52:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v39,
            &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
            this,
            v20);
          return v20;
        }
        return v20;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v31 = (*(__int64 (__fastcall **)(__int64 *))(**v22 + 40))(*v22);
        WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 27), *v24, v31);
      }
      v7 = v44;
    }
  }
  else
  {
    v32 = (*(__int64 (**)(void))(v16 + 40))();
    MFGetSensorOrientation(v32, (char *)this + 616);
    v22 = v9;
  }
LABEL_34:
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 576);
  (*(void (__fastcall **)(__int64 *))(**v22 + 112))(*v22);
  v33 = (const void *)(*(__int64 (__fastcall **)(__int64 *))(**v22 + 104))(*v22);
  v34 = (*(__int64 (__fastcall **)(FSSource *))(*(_QWORD *)this + 536LL))(this);
  ProcessActivities = FSProcessActivities::CreateProcessActivities(
                        v34,
                        v33,
                        v35,
                        (struct IFSProcessActivities **)this + 72);
  v20 = ProcessActivities;
  if ( ProcessActivities < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 505;
      goto LABEL_14;
    }
    goto LABEL_48;
  }
  ProcessActivities = MFAllocateSerialWorkQueue(5u, (DWORD *)this + 71);
  v20 = ProcessActivities;
  if ( ProcessActivities < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 506;
      goto LABEL_14;
    }
    goto LABEL_48;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 1000);
  ProcessActivities = FSSourceUtils::CoCreateCameraDeviceStateStats(
                        v36,
                        (const struct _GUID *)((char *)this + 1000),
                        v37);
  v20 = ProcessActivities;
  if ( ProcessActivities < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 507;
      goto LABEL_14;
    }
    goto LABEL_48;
  }
  *((_DWORD *)this + 70) = v7;
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)this + 73, (__int64)a3);
  *((struct _GUID *)this + 15) = *a4;
  CoCreateGuid((GUID *)((char *)this + 600));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::GetImpl'::`2'::impl) )
    _InterlockedExchange((volatile __int32 *)this + 257, 0);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 1056);
  Instance = FSSourceSupportedProperties::CreateInstance((struct IFSSourceSupportedProperties **)this + 132);
  v20 = Instance;
  if ( Instance < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        508,
        &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
        this,
        Instance);
    goto LABEL_48;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *((_BYTE *)this + 168) = 1;
  *((_DWORD *)this + 83) = GetCurrentThreadId();
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v39 = 510;
    goto LABEL_52;
  }
  return v20;
}

```

## disassembly

```asm
0x180098f44  mov     [rsp+arg_10], rbx
0x180098f49  mov     [rsp+arg_8], edx
0x180098f4d  push    rbp
0x180098f4e  push    rsi
0x180098f4f  push    rdi
0x180098f50  push    r12
0x180098f52  push    r13
0x180098f54  push    r14
0x180098f56  push    r15
0x180098f58  sub     rsp, 70h
0x180098f5c  xor     eax, eax
0x180098f5e  mov     rbp, r9
0x180098f61  mov     [rsp+0A8h+arg_0], eax
0x180098f68  mov     r13, r8
0x180098f6b  mov     r12d, edx
0x180098f6e  mov     rsi, rcx
0x180098f71  cmp     cs:byte_18010EC4D, 8
0x180098f78  lea     r14, [rcx+100h]
0x180098f7f  jb      short loc_180098FE2
0x180098f81  mov     rdx, r9; struct _GUID *
0x180098f84  lea     rcx, [rsp+0A8h+var_60]; this
0x180098f89  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180098f8e  mov     rcx, rax; this
0x180098f91  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180098f96  mov     rcx, [r14]
0x180098f99  mov     rdi, rax
0x180098f9c  mov     rdx, [rcx]
0x180098f9f  mov     rax, [rdx+18h]
0x180098fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098fa8  mov     rcx, [r14]
0x180098fab  mov     ebx, eax
0x180098fad  mov     rdx, [rcx]
0x180098fb0  mov     rax, [rdx+20h]
0x180098fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180098fc0  mov     r9, rsi
0x180098fc3  mov     [rsp+0A8h+var_78], rdi; __int64
0x180098fc8  mov     dword ptr [rsp+0A8h+var_80], ebx; char
0x180098fcc  mov     qword ptr [rsp+0A8h+var_88], rax; __int64
0x180098fd1  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180098fd8  call    WPP_SF_qSds
0x180098fdd  mov     eax, 1
0x180098fe2  test    al, 1
0x180098fe4  jz      short loc_180098FF0
0x180098fe6  lea     rcx, [rsp+0A8h+var_60]; this
0x180098feb  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180098ff0  mov     rcx, [r14]
0x180098ff3  mov     rax, [rcx]
0x180098ff6  mov     rax, [rax+18h]
0x180098ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098fff  cmp     eax, 2
0x180099002  jnz     short loc_18009904C
0x180099004  mov     rcx, [r14]
0x180099007  mov     rax, [rcx]
0x18009900a  mov     rax, [rax+60h]
0x18009900e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099013  cmp     dword ptr [rax], 1
0x180099016  jnz     short loc_18009904C
0x180099018  mov     rcx, [r14]
0x18009901b  mov     rax, [rcx]
0x18009901e  mov     rax, [rax+60h]
0x180099022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099027  mov     r8d, 10h; Size
0x18009902d  lea     rdx, MF_SENSORTRANSFORM_BUILTINST_MULTIPLEXOR; Buf2
0x180099034  lea     rcx, [rax+20h]; Buf1
0x180099038  call    memcmp_0
0x18009903d  test    eax, eax
0x18009903f  jz      loc_1800990D1
0x180099045  lea     r14, [rsi+100h]
0x18009904c  mov     rcx, [r14]
0x18009904f  mov     rax, [rcx]
0x180099052  mov     rax, [rax+18h]
0x180099056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009905b  mov     rcx, [r14]
0x18009905e  mov     rdx, [rcx]
0x180099061  cmp     eax, 3
0x180099064  jnz     loc_180099277
0x18009906a  mov     rax, [rdx+90h]
0x180099071  mov     [rsp+0A8h+arg_0], 0
0x18009907c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099081  test    rax, rax
0x180099084  jz      loc_180099118
0x18009908a  mov     rcx, [r14]
0x18009908d  mov     rax, [rcx]
0x180099090  mov     rax, [rax+90h]
0x180099097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009909c  mov     rdx, rax
0x18009909f  lea     rcx, [rsi+358h]
0x1800990a6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800990ab  test    al, al
0x1800990ad  jnz     short loc_18009910F
0x1800990af  mov     eax, 8007000Eh
0x1800990b4  mov     ebx, eax
0x1800990b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800990bd  jb      loc_1800993F3
0x1800990c3  mov     edx, 1F5h
0x1800990c8  mov     [rsp+0A8h+var_88], eax
0x1800990cc  jmp     loc_1800993D9
0x1800990d1  cmp     cs:byte_18010EC4D, 8
0x1800990d8  jb      short loc_1800990FC
0x1800990da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800990e1  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x1800990e8  mov     edx, 1F4h
0x1800990ed  mov     r9, rsi
0x1800990f0  mov     rcx, [rcx+0D8h]
0x1800990f7  call    WPP_SF_q
0x1800990fc  mov     byte ptr [rsi+0A9h], 1
0x180099103  lea     r15, [rsi+100h]
0x18009910a  jmp     loc_180099293
0x18009910f  lea     r15, [rsi+100h]
0x180099116  jmp     short loc_18009911B
0x180099118  mov     r15, r14
0x18009911b  mov     rcx, [r14]
0x18009911e  mov     rax, [rcx]
0x180099121  mov     rax, [rax+28h]
0x180099125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009912a  xor     r9d, r9d; unsigned __int8 *
0x18009912d  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceInfo; PropertyKey
0x180099134  mov     rcx, rax; pszDeviceInterface
0x180099137  lea     rax, [rsp+0A8h+arg_0]
0x18009913f  mov     [rsp+0A8h+var_80], rax; unsigned int *
0x180099144  mov     [rsp+0A8h+var_88], 0; unsigned int
0x18009914c  lea     r8d, [r9+12h]; unsigned int
0x180099150  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x180099155  test    eax, eax
0x180099157  js      loc_180099293
0x18009915d  mov     r12d, [rsp+0A8h+arg_0]
0x180099165  lea     rcx, [rsp+0A8h+var_68]
0x18009916a  shr     r12d, 1
0x18009916d  lea     rdi, [rsi+208h]
0x180099174  inc     r12d
0x180099177  mov     edx, r12d
0x18009917a  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18009917f  mov     rdx, rax
0x180099182  mov     rcx, rdi
0x180099185  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18009918a  mov     rcx, [rsp+0A8h+var_68]; void *
0x18009918f  mov     [rsp+0A8h+var_68], 0
0x180099198  test    rcx, rcx
0x18009919b  jz      short loc_1800991A4
0x18009919d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800991a2  jmp     short loc_1800991A7
0x1800991a4  mov     r15, r14
0x1800991a7  mov     rbx, [rdi]
0x1800991aa  test    rbx, rbx
0x1800991ad  jnz     short loc_1800991CD
0x1800991af  mov     eax, 8007000Eh
0x1800991b4  mov     ebx, eax
0x1800991b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800991bd  jb      loc_1800993F3
0x1800991c3  mov     edx, 1F6h
0x1800991c8  jmp     loc_1800990C8
0x1800991cd  mov     rcx, [r15]
0x1800991d0  mov     rax, [rcx]
0x1800991d3  mov     rax, [rax+28h]
0x1800991d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800991dc  lea     r9, [rsp+0A8h+arg_0]
0x1800991e4  mov     r8d, 12h; unsigned int
0x1800991ea  mov     [rsp+0A8h+var_80], r9; unsigned int *
0x1800991ef  lea     ecx, [r12+r12]
0x1800991f3  mov     [rsp+0A8h+var_88], ecx; unsigned int
0x1800991f7  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceInfo; PropertyKey
0x1800991fe  mov     rcx, rax; pszDeviceInterface
0x180099201  mov     r9, rbx; unsigned __int8 *
0x180099204  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x180099209  mov     ebx, eax
0x18009920b  test    eax, eax
0x18009920d  jns     short loc_180099226
0x18009920f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180099216  jb      loc_1800993F3
0x18009921c  mov     edx, 1F7h
0x180099221  jmp     loc_1800990C8
0x180099226  cmp     cs:byte_18010EC4D, 8
0x18009922d  jb      short loc_18009926D
0x18009922f  mov     rcx, [r15]
0x180099232  mov     rax, [rcx]
0x180099235  mov     rax, [rax+28h]
0x180099239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009923e  mov     rcx, cs:WPP_GLOBAL_Control
0x180099245  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x18009924c  mov     [rsp+0A8h+var_80], rax; __int64
0x180099251  mov     edx, 1F8h
0x180099256  mov     rax, [rdi]
0x180099259  mov     r9, rsi
0x18009925c  mov     qword ptr [rsp+0A8h+var_88], rax; __int64
0x180099261  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180099268  call    WPP_SF_qSS
0x18009926d  mov     r12d, [rsp+0A8h+arg_8]
0x180099275  jmp     short loc_180099293
0x180099277  mov     rax, [rdx+28h]
0x18009927b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099280  mov     rcx, rax
0x180099283  lea     rdx, [rsi+268h]
0x18009928a  call    cs:__imp_MFGetSensorOrientation
0x180099290  mov     r15, r14
0x180099293  lea     rdi, [rsi+240h]
0x18009929a  mov     rcx, rdi
0x18009929d  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800992a2  mov     rcx, [r15]
0x1800992a5  mov     rax, [rcx]
0x1800992a8  mov     rax, [rax+70h]
0x1800992ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800992b1  mov     rcx, [r15]
0x1800992b4  mov     rax, [rcx]
0x1800992b7  mov     rax, [rax+68h]
0x1800992bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800992c0  mov     rcx, [rsi]
0x1800992c3  mov     rbx, rax
0x1800992c6  mov     rax, [rcx+218h]
0x1800992cd  mov     rcx, rsi
0x1800992d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800992d5  mov     r9, rdi; struct IFSProcessActivities **
0x1800992d8  mov     rdx, rbx; void *
0x1800992db  mov     rcx, rax; unsigned __int64
0x1800992de  call    ?CreateProcessActivities@FSProcessActivities@@SAJ_KPEBXKPEAPEAUIFSProcessActivities@@@Z; FSProcessActivities::CreateProcessActivities(unsigned __int64,void const *,ulong,IFSProcessActivities * *)
0x1800992e3  mov     ebx, eax
0x1800992e5  test    eax, eax
0x1800992e7  jns     short loc_180099300
0x1800992e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800992f0  jb      loc_1800993F3
0x1800992f6  mov     edx, 1F9h
0x1800992fb  jmp     loc_1800990C8
0x180099300  lea     rdx, [rsi+11Ch]; pdwWorkQueue
0x180099307  mov     ecx, 5; dwWorkQueue
0x18009930c  call    cs:__imp_MFAllocateSerialWorkQueue
0x180099312  mov     ebx, eax
0x180099314  test    eax, eax
0x180099316  jns     short loc_18009932F
0x180099318  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009931f  jb      loc_1800993F3
0x180099325  mov     edx, 1FAh
0x18009932a  jmp     loc_1800990C8
0x18009932f  lea     rbx, [rsi+3E8h]
0x180099336  mov     rcx, rbx
0x180099339  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18009933e  mov     rdx, rbx; struct _GUID *
0x180099341  call    ?CoCreateCameraDeviceStateStats@FSSourceUtils@@YAJAEBU_GUID@@PEAPEAX@Z; FSSourceUtils::CoCreateCameraDeviceStateStats(_GUID const &,void * *)
0x180099346  mov     ebx, eax
0x180099348  test    eax, eax
0x18009934a  jns     short loc_180099363
0x18009934c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180099353  jb      loc_1800993F3
0x180099359  mov     edx, 1FBh
0x18009935e  jmp     loc_1800990C8
0x180099363  lea     rcx, [rsi+248h]
0x18009936a  mov     [rsi+118h], r12d
0x180099371  mov     rdx, r13
0x180099374  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x180099379  movups  xmm0, xmmword ptr [rbp+0]
0x18009937d  lea     rcx, [rsi+258h]; pguid
0x180099384  movdqu  xmmword ptr [rsi+0F0h], xmm0
0x18009938c  call    cs:__imp_CoCreateGuid
0x180099392  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FrameServerErrorTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerErrorTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry> `wil::Feature<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::GetImpl(void)'::`2'::impl
0x180099399  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerErrorTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::__private_IsEnabled(void)
0x18009939e  test    al, al
0x1800993a0  jz      short loc_1800993AA
0x1800993a2  xor     eax, eax
0x1800993a4  xchg    eax, [rsi+404h]
0x1800993aa  lea     rbx, [rsi+420h]
0x1800993b1  mov     rcx, rbx
0x1800993b4  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800993b9  mov     rcx, rbx; struct IFSSourceSupportedProperties **
0x1800993bc  call    ?CreateInstance@FSSourceSupportedProperties@@SAJPEAPEAUIFSSourceSupportedProperties@@@Z; FSSourceSupportedProperties::CreateInstance(IFSSourceSupportedProperties * *)
0x1800993c1  mov     ebx, eax
0x1800993c3  test    eax, eax
0x1800993c5  jns     short loc_180099403
0x1800993c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800993ce  jb      short loc_1800993F3
0x1800993d0  mov     edx, 1FCh
0x1800993d5  mov     [rsp+0A8h+var_88], eax
0x1800993d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800993e0  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x1800993e7  mov     r9, rsi
0x1800993ea  mov     rcx, [rcx+10h]
0x1800993ee  call    WPP_SF_qD
0x1800993f3  cmp     cs:byte_18010EC4D, 1
0x1800993fa  jb      short loc_18009944F
0x1800993fc  mov     edx, 1FDh
0x180099401  jmp     short loc_18009942E
0x180099403  lea     rcx, [rsi+38h]; lpCriticalSection
0x180099407  call    cs:__imp_EnterCriticalSection
0x18009940d  mov     byte ptr [rsi+0A8h], 1
0x180099414  call    cs:__imp_GetCurrentThreadId
0x18009941a  mov     [rsi+14Ch], eax
0x180099420  cmp     cs:byte_18010EC4D, 8
0x180099427  jb      short loc_18009944F
0x180099429  mov     edx, 1FEh
0x18009942e  mov     rcx, cs:WPP_GLOBAL_Control
0x180099435  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x18009943c  mov     r9, rsi
0x18009943f  mov     [rsp+0A8h+var_88], ebx
0x180099443  mov     rcx, [rcx+0D8h]
0x18009944a  call    WPP_SF_qD
0x18009944f  mov     eax, ebx
0x180099451  mov     rbx, [rsp+0A8h+arg_10]
0x180099459  add     rsp, 70h
0x18009945d  pop     r15
0x18009945f  pop     r14
0x180099461  pop     r13
0x180099463  pop     r12
  ... truncated ...
```

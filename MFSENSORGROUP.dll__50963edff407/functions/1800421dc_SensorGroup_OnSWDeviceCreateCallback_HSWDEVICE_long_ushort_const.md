# SensorGroup::OnSWDeviceCreateCallback(HSWDEVICE__ *,long,ushort const *)

- ea: `0x1800421dc`
- end: `0x180042ae2`
- name: `?OnSWDeviceCreateCallback@SensorGroup@@IEAAXPEAUHSWDEVICE__@@JPEBG@Z`
- size: `2310`
- prototype: `void __fastcall(SensorGroup *__hidden this, struct HSWDEVICE__ *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004d9d0`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000d1f0`
- `0x180015e80`
- `0x180019a70`
- `0x180019b7c`
- `0x18001bd24`
- `0x18001c854`
- `0x18001c96c`
- `0x180037d70`
- `0x1800421dc`
- `0x180042ae8`
- `0x180044b28`
- `0x180045300`
- `0x180045900`
- `0x18004e380`
- `0x18004e564`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042a90`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042a90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042ac8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042ac8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042213`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042213`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x180042806`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x180042806`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x180042a2a`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x180042a2a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18004254c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18004254c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x18004289a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x18004289a`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x1800424de`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x1800424de`

## pseudocode

```c
void __fastcall SensorGroup::OnSWDeviceCreateCallback(
        SensorGroup *this,
        struct HSWDEVICE__ *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  struct HSWDEVICE__ *v5; // r12
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v7; // rbx
  __int64 (__fastcall **v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // eax
  int v10; // esi
  __int64 v11; // rdx
  unsigned __int16 *v12; // r12
  const char *v13; // rcx
  size_t v14; // rsi
  _QWORD *v15; // rax
  unsigned __int16 *v16; // r12
  __int64 i; // r13
  __int64 v18; // r15
  GuidTrace *v19; // rcx
  const char *String; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 **); // rcx
  int v25; // eax
  __int64 v26; // rdx
  void *v27; // r13
  __int64 k; // r15
  int v29; // eax
  __int64 j; // r15
  int v31; // eax
  const char *v32; // rcx
  unsigned __int16 *v33; // r12
  const char *v34; // r8
  __int64 m; // r15
  __int64 v36; // rdx
  void *v37; // rcx
  void *Block; // [rsp+88h] [rbp-80h] BYREF
  __int64 v39; // [rsp+90h] [rbp-78h] BYREF
  char v40[8]; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v41; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v42; // [rsp+A4h] [rbp-64h] BYREF
  unsigned __int16 *v43; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v44; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-40h] BYREF
  char v47[8]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 *v48; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v49[96]; // [rsp+E8h] [rbp-20h] BYREF
  int v50; // [rsp+158h] [rbp+50h] BYREF
  struct HSWDEVICE__ *v51; // [rsp+160h] [rbp+58h]
  unsigned int v52; // [rsp+168h] [rbp+60h] BYREF
  __int64 *v53; // [rsp+170h] [rbp+68h] BYREF

  HIDWORD(v53) = HIDWORD(a4);
  v52 = a3;
  v51 = a2;
  LODWORD(v53) = 0;
  v5 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 22);
  v46 = 0;
  v44 = 0;
  v7 = 0;
  v39 = 0;
  *(_QWORD *)v40 = 0;
  v52 = 0;
  *(_QWORD *)v47 = 0;
  v50 = 0;
  v8 = *v6;
  Block = 0;
  v42 = 0;
  v9 = (*v8)(v6, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v39);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_wppLevels )
    {
      v11 = 316;
      goto LABEL_4;
    }
    goto LABEL_111;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *, unsigned int *))(*(_QWORD *)v39 + 192LL))(
         v39,
         8,
         0,
         v40,
         &v52);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_wppLevels )
    {
      v11 = 317;
      goto LABEL_4;
    }
    goto LABEL_111;
  }
  if ( !*(_QWORD *)v40 || !v52 || (v52 & 0xF) != 0 )
  {
    v10 = -1072875829;
    if ( !g_wppLevels )
      goto LABEL_111;
    v23 = 318;
    goto LABEL_110;
  }
  v52 >>= 4;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v39 + 192LL))(
         v39,
         13,
         0,
         &v46,
         0);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_wppLevels )
    {
      v11 = 319;
      goto LABEL_4;
    }
    goto LABEL_111;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)v39 + 192LL))(
         v39,
         7,
         0,
         &v44,
         0);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_wppLevels )
    {
      v11 = 320;
      goto LABEL_4;
    }
    goto LABEL_111;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *, int *))(*(_QWORD *)v39 + 192LL))(
         v39,
         3,
         0,
         v47,
         &v50);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_wppLevels )
    {
      v11 = 321;
      goto LABEL_4;
    }
    goto LABEL_111;
  }
  if ( !*(_QWORD *)v47 || v50 != 96 || !*(_QWORD *)v40 || !v52 )
  {
    if ( byte_18008D62D )
    {
      v33 = L"<null>";
      v34 = "enable";
      if ( v44 )
        v33 = v44;
      if ( *((_DWORD *)this + 46) != 1 )
        v34 = "disable";
      WPP_SF_qsSqDqD(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v34, (__int64)v33, v40[0], v52, v47[0], v50);
    }
    v10 = -1072875829;
    goto LABEL_111;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v12 = L"<null>";
    v13 = "enable";
    if ( v44 )
      v12 = v44;
    if ( *((_DWORD *)this + 46) != 1 )
      v13 = "disable";
    WPP_SF_qsSqDddSidddd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (__int64)v13,
      (__int64)v12,
      v40[0],
      v52,
      **(_DWORD **)v47,
      *(_DWORD *)(*(_QWORD *)v47 + 4LL),
      v46,
      *(_QWORD *)(*(_QWORD *)v47 + 72LL),
      *(_DWORD *)(*(_QWORD *)v47 + 80LL),
      *(_DWORD *)(*(_QWORD *)v47 + 84LL),
      *(_DWORD *)(*(_QWORD *)v47 + 88LL),
      *(_DWORD *)(*(_QWORD *)v47 + 92LL));
    v5 = v51;
  }
  v14 = 8LL * v52;
  if ( !is_mul_ok(v52, 8u) )
    v14 = -1;
  v15 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v15;
  if ( !v15 )
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        324,
        &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
        this,
        -2147024882);
    v7 = 0;
    goto LABEL_111;
  }
  memset_0(v15, 0, v14);
  memset_0(v7, 0, 8LL * v52);
  v9 = SwDeviceSetLifetime(v5, 1);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_wppLevels )
    {
      v11 = 325;
      goto LABEL_4;
    }
    goto LABEL_111;
  }
  v16 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v52 )
    {
      if ( !v16 )
      {
        v16 = (unsigned __int16 *)*v7;
        if ( !*v7 )
        {
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_111;
          v23 = 331;
LABEL_110:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v23,
            &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
            this,
            v10);
          goto LABEL_111;
        }
      }
      if ( *((_DWORD *)this + 46) != 1 )
      {
LABEL_87:
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          v31 = *((_DWORD *)this + 46);
          if ( (unsigned int)j >= v52 )
          {
            SensorGroup::GenerateTelemetryReportForSensorGroups(this, v31 == 1, v16, v44, *((_DWORD *)this + 26));
            goto LABEL_111;
          }
          v9 = SwDeviceInterfaceSetState(v51, v7[j], v31 == 1);
          v10 = v9;
          if ( v9 < 0 )
            break;
          if ( (unsigned __int8)byte_18008D62D >= 8u )
          {
            v32 = "enable";
            if ( *((_DWORD *)this + 46) != 1 )
              v32 = "disable";
            WPP_SF_qsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v32, v7[j]);
          }
        }
        if ( !g_wppLevels )
          goto LABEL_111;
        v11 = 336;
        goto LABEL_4;
      }
      v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))*((_QWORD *)this + 22);
      v53 = 0;
      v25 = (**v24)(v24, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v53);
      v10 = v25;
      if ( v25 >= 0 )
      {
        v25 = SensorGroup::CheckAllDevicesForSphericalAttributes(this);
        v10 = v25;
        if ( v25 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_72;
          v26 = 333;
          goto LABEL_71;
        }
        v25 = SensorGroupId::CreateDevPropertyArray(v53, &Block, &v42);
        v10 = v25;
        if ( v25 >= 0 )
        {
          v27 = Block;
          for ( k = 0; ; k = (unsigned int)(k + 1) )
          {
            if ( (unsigned int)k >= v52 )
            {
              (*(void (__fastcall **)(__int64 *, __int64))(*v53 + 216))(v53, 1);
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v53);
              goto LABEL_87;
            }
            v29 = SwDeviceInterfacePropertySet(v51, v7[k], v42, v27);
            v10 = v29;
            if ( v29 < 0 )
              break;
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              335,
              &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
              this,
              v29);
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v53);
          goto LABEL_112;
        }
        if ( g_wppLevels )
        {
          v26 = 334;
          goto LABEL_71;
        }
      }
      else if ( g_wppLevels )
      {
        v26 = 332;
LABEL_71:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v25);
      }
LABEL_72:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v53);
      goto LABEL_111;
    }
    v18 = 16LL * (unsigned int)i;
    v43 = 0;
    v9 = SwDeviceInterfaceRegister(v51, v18 + *(_QWORD *)v40, v46, 0, 0, 0, &v43);
    v10 = v9;
    if ( v9 < 0 )
      break;
    v7[i] = v43;
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      LODWORD(v53) = (unsigned int)v53 | 1;
      v45 = (unsigned __int64)v43;
      v19 = GuidTrace::GuidTrace((GuidTrace *)v49, (const struct _GUID *)(v18 + *(_QWORD *)v40));
      String = (const char *)*((_QWORD *)v19 + 3);
      if ( !String )
        String = FSString::GetString(v19);
      WPP_SF_qsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)String, v45);
    }
    if ( ((unsigned __int8)v53 & 1) != 0 )
    {
      LODWORD(v53) = (unsigned int)v53 & 0xFFFFFFFE;
      FSString::~FSString((FSString *)v49);
    }
    v21 = *(_QWORD *)(v18 + *(_QWORD *)v40) - *(_QWORD *)&KSCATEGORY_SENSOR_GROUP_INTERNAL.Data1;
    if ( !v21 )
      v21 = *(_QWORD *)(v18 + *(_QWORD *)v40 + 8) - *(_QWORD *)KSCATEGORY_SENSOR_GROUP_INTERNAL.Data4;
    if ( !v21 )
      goto LABEL_51;
    v22 = *(_QWORD *)(v18 + *(_QWORD *)v40) - KSCATEGORY_FRAMEPROVIDER;
    if ( !v22 )
      v22 = *(_QWORD *)(v18 + *(_QWORD *)v40 + 8) - 0xCAAFAB1C068F381LL;
    if ( !v22 )
    {
LABEL_51:
      v16 = v43;
      v45 = 0;
      v41 = 0;
      v48 = 0;
      v9 = StringCchLengthW(v43, 0x7FFFFFFFu, &v45);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_111;
        v11 = 328;
        goto LABEL_4;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 **, unsigned int *))(*(_QWORD *)v39 + 192LL))(
             v39,
             4,
             (unsigned int)(2 * (v45 + 1)),
             &v48,
             &v41);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_111;
        v11 = 329;
        goto LABEL_4;
      }
      v9 = StringCchCopyW(v48, v41, v43);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_111;
        v11 = 330;
        goto LABEL_4;
      }
    }
  }
  if ( !g_wppLevels )
    goto LABEL_111;
  v11 = 326;
LABEL_4:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v9);
LABEL_111:
  v27 = Block;
LABEL_112:
  for ( m = 0; (unsigned int)m < v52; m = (unsigned int)(m + 1) )
  {
    if ( v7[m] )
    {
      SwMemFree();
      v7[m] = 0;
    }
  }
  if ( v10 >= 0 )
  {
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v36 = 339;
LABEL_121:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v36, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v10);
    }
  }
  else if ( byte_18008D62D )
  {
    v36 = 338;
    goto LABEL_121;
  }
  v37 = (void *)*((_QWORD *)this + 20);
  if ( v37 )
  {
    SetEvent(v37);
    *((_QWORD *)this + 20) = 0;
  }
  if ( v7 )
    operator delete(v7);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v39);
  if ( v27 )
    operator delete(v27);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
}

```

## disassembly

```asm
0x1800421dc  mov     rax, rsp
0x1800421df  mov     [rax+20h], r9
0x1800421e3  mov     [rax+18h], r8d
0x1800421e7  mov     [rax+10h], rdx
0x1800421eb  push    rbp
0x1800421ec  push    rbx
0x1800421ed  push    rsi
0x1800421ee  push    rdi
0x1800421ef  push    r12
0x1800421f1  push    r13
0x1800421f3  push    r14
0x1800421f5  push    r15
0x1800421f7  lea     rbp, [rax-48h]
0x1800421fb  sub     rsp, 108h
0x180042202  mov     r14, rcx
0x180042205  xor     r13d, r13d
0x180042208  add     rcx, 20h ; ' '; lpCriticalSection
0x18004220c  mov     dword ptr [rbp+40h+arg_18], r13d
0x180042210  mov     r12, rdx
0x180042213  call    cs:__imp_EnterCriticalSection
0x180042219  mov     rcx, [r14+0B0h]
0x180042220  lea     r8, [rbp+40h+var_B8]
0x180042224  mov     [rbp+40h+var_80], r13
0x180042228  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x18004222f  mov     [rbp+40h+var_90], r13
0x180042233  mov     ebx, r13d
0x180042236  mov     [rbp+40h+var_B8], r13
0x18004223a  mov     qword ptr [rbp+40h+var_B0], r13
0x18004223e  mov     [rbp+40h+arg_10], r13d
0x180042242  mov     qword ptr [rbp+40h+var_78], r13
0x180042246  mov     [rbp+40h+arg_0], r13d
0x18004224a  mov     rax, [rcx]
0x18004224d  mov     [rbp+40h+Block], r13
0x180042251  mov     dword ptr [rbp+40h+var_A8+4], r13d
0x180042255  mov     rax, [rax]
0x180042258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004225d  mov     esi, eax
0x18004225f  test    eax, eax
0x180042261  jns     short loc_18004227E
0x180042263  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004226a  jb      loc_180042A14
0x180042270  mov     edx, 13Ch
0x180042275  mov     [rsp+140h+var_120], eax
0x180042279  jmp     loc_1800429FA
0x18004227e  mov     rcx, [rbp+40h+var_B8]
0x180042282  lea     rdx, [rbp+40h+arg_10]
0x180042286  xor     r8d, r8d
0x180042289  mov     qword ptr [rsp+140h+var_120], rdx
0x18004228e  lea     r9, [rbp+40h+var_B0]
0x180042292  mov     rax, [rcx]
0x180042295  lea     edx, [r8+8]
0x180042299  mov     rax, [rax+0C0h]
0x1800422a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422a5  mov     esi, eax
0x1800422a7  test    eax, eax
0x1800422a9  jns     short loc_1800422BF
0x1800422ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800422b2  jb      loc_180042A14
0x1800422b8  mov     edx, 13Dh
0x1800422bd  jmp     short loc_180042275
0x1800422bf  cmp     qword ptr [rbp+40h+var_B0], r13
0x1800422c3  jz      loc_1800429E3
0x1800422c9  mov     r15d, [rbp+40h+arg_10]
0x1800422cd  test    r15d, r15d
0x1800422d0  jz      loc_1800429E3
0x1800422d6  test    r15b, 0Fh
0x1800422da  jnz     loc_1800429E3
0x1800422e0  mov     rcx, [rbp+40h+var_B8]
0x1800422e4  lea     r9, [rbp+40h+var_80]
0x1800422e8  shr     [rbp+40h+arg_10], 4
0x1800422ec  xor     r8d, r8d
0x1800422ef  mov     qword ptr [rsp+140h+var_120], r13
0x1800422f4  mov     rax, [rcx]
0x1800422f7  lea     edx, [r8+0Dh]
0x1800422fb  mov     rax, [rax+0C0h]
0x180042302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042307  mov     esi, eax
0x180042309  test    eax, eax
0x18004230b  jns     short loc_180042324
0x18004230d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042314  jb      loc_180042A14
0x18004231a  mov     edx, 13Fh
0x18004231f  jmp     loc_180042275
0x180042324  mov     rcx, [rbp+40h+var_B8]
0x180042328  lea     r9, [rbp+40h+var_90]
0x18004232c  xor     r8d, r8d
0x18004232f  mov     qword ptr [rsp+140h+var_120], r13
0x180042334  mov     rax, [rcx]
0x180042337  lea     edx, [r8+7]
0x18004233b  mov     rax, [rax+0C0h]
0x180042342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042347  mov     esi, eax
0x180042349  test    eax, eax
0x18004234b  jns     short loc_180042364
0x18004234d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042354  jb      loc_180042A14
0x18004235a  mov     edx, 140h
0x18004235f  jmp     loc_180042275
0x180042364  mov     rcx, [rbp+40h+var_B8]
0x180042368  lea     rdx, [rbp+40h+arg_0]
0x18004236c  xor     r8d, r8d
0x18004236f  mov     qword ptr [rsp+140h+var_120], rdx
0x180042374  lea     r9, [rbp+40h+var_78]
0x180042378  mov     rax, [rcx]
0x18004237b  lea     edx, [r8+3]
0x18004237f  mov     rax, [rax+0C0h]
0x180042386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004238b  mov     esi, eax
0x18004238d  test    eax, eax
0x18004238f  jns     short loc_1800423A8
0x180042391  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042398  jb      loc_180042A14
0x18004239e  mov     edx, 141h
0x1800423a3  jmp     loc_180042275
0x1800423a8  mov     rcx, qword ptr [rbp+40h+var_78]
0x1800423ac  mov     r13, qword ptr [rbp+40h+var_B0]
0x1800423b0  mov     edx, [rbp+40h+arg_0]
0x1800423b3  test    rcx, rcx
0x1800423b6  jz      loc_180042972
0x1800423bc  cmp     edx, 60h ; '`'
0x1800423bf  jnz     loc_180042972
0x1800423c5  test    r13, r13
0x1800423c8  jz      loc_180042972
0x1800423ce  mov     r15d, [rbp+40h+arg_10]
0x1800423d2  test    r15d, r15d
0x1800423d5  jz      loc_180042972
0x1800423db  cmp     cs:byte_18008D62D, 8
0x1800423e2  jb      loc_180042483
0x1800423e8  mov     r9d, [rcx+54h]
0x1800423ec  lea     r12, aNull_0; "<null>"
0x1800423f3  mov     edx, [rcx+5Ch]
0x1800423f6  mov     r8d, [rcx+58h]
0x1800423fa  mov     r10d, [rcx+50h]
0x1800423fe  mov     r11, [rcx+48h]
0x180042402  mov     ebx, [rcx+4]
0x180042405  mov     esi, [rcx]
0x180042407  lea     rcx, aEnable; "enable"
0x18004240e  mov     rax, [rbp+40h+var_90]
0x180042412  mov     [rsp+78h], edx; char
0x180042416  test    rax, rax
0x180042419  mov     dword ptr [rsp+140h+var_D0], r8d; char
0x18004241e  mov     dword ptr [rsp+140h+var_D8], r9d; char
0x180042423  cmovnz  r12, rax
0x180042427  cmp     dword ptr [r14+0B8h], 1
0x18004242f  lea     rax, aDisable; "disable"
0x180042436  mov     dword ptr [rsp+140h+var_E0], r10d; char
0x18004243b  mov     r9, r14
0x18004243e  mov     qword ptr [rsp+140h+var_E8], r11; char
0x180042443  cmovnz  rcx, rax
0x180042447  mov     rax, [rbp+40h+var_80]
0x18004244b  mov     [rsp+140h+var_F0], rax; __int64
0x180042450  mov     dword ptr [rsp+140h+var_F8], ebx; char
0x180042454  mov     dword ptr [rsp+140h+var_100], esi; char
0x180042458  mov     dword ptr [rsp+140h+var_108], r15d; char
0x18004245d  mov     qword ptr [rsp+140h+var_110], r13; char
0x180042462  mov     [rsp+140h+var_118], r12; __int64
0x180042467  mov     qword ptr [rsp+140h+var_120], rcx; __int64
0x18004246c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042473  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18004247a  call    WPP_SF_qsSqDddSidddd
0x18004247f  mov     r12, [rbp+40h+arg_8]
0x180042483  mov     ecx, [rbp+40h+arg_10]
0x180042486  mov     eax, 8
0x18004248b  mul     rcx
0x18004248e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042495  mov     rsi, rax
0x180042498  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004249f  cmovb   rsi, rax
0x1800424a3  mov     rcx, rsi; unsigned __int64
0x1800424a6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800424ab  mov     rbx, rax
0x1800424ae  test    rax, rax
0x1800424b1  jz      loc_18004293A
0x1800424b7  mov     r8, rsi; Size
0x1800424ba  xor     edx, edx; Val
0x1800424bc  mov     rcx, rax; void *
0x1800424bf  call    memset_0
0x1800424c4  mov     r8d, [rbp+40h+arg_10]
0x1800424c8  xor     edx, edx; Val
0x1800424ca  shl     r8, 3; Size
0x1800424ce  mov     rcx, rbx; void *
0x1800424d1  call    memset_0
0x1800424d6  mov     edx, 1
0x1800424db  mov     rcx, r12
0x1800424de  call    cs:__imp_SwDeviceSetLifetime
0x1800424e4  mov     esi, eax
0x1800424e6  test    eax, eax
0x1800424e8  jns     short loc_180042501
0x1800424ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800424f1  jb      loc_180042A14
0x1800424f7  mov     edx, 145h
0x1800424fc  jmp     loc_180042275
0x180042501  xor     r12d, r12d
0x180042504  xor     r13d, r13d
0x180042507  cmp     r13d, [rbp+40h+arg_10]
0x18004250b  jnb     loc_180042709
0x180042511  mov     rdx, qword ptr [rbp+40h+var_B0]
0x180042515  lea     rax, [rbp+40h+var_A0]
0x180042519  mov     r8, [rbp+40h+var_80]
0x18004251d  xor     r9d, r9d
0x180042520  mov     rcx, [rbp+40h+arg_8]
0x180042524  mov     qword ptr [rsp+140h+var_110], rax
0x180042529  mov     r15d, r13d
0x18004252c  shl     r15, 4
0x180042530  add     rdx, r15
0x180042533  mov     dword ptr [rsp+140h+var_118], 0
0x18004253b  mov     [rbp+40h+var_A0], 0
0x180042543  mov     qword ptr [rsp+140h+var_120], 0
0x18004254c  call    cs:__imp_SwDeviceInterfaceRegister
0x180042552  mov     esi, eax
0x180042554  test    eax, eax
0x180042556  js      loc_1800426F2
0x18004255c  mov     rax, [rbp+40h+var_A0]
0x180042560  mov     [rbx+r13*8], rax
0x180042564  cmp     cs:byte_18008D62D, 8
0x18004256b  jb      short loc_1800425CA
0x18004256d  mov     rax, [rbp+40h+var_A0]
0x180042571  lea     rcx, [rbp+40h+var_60]; this
0x180042575  or      dword ptr [rbp+40h+arg_18], 1
0x180042579  mov     rdx, qword ptr [rbp+40h+var_B0]
0x18004257d  add     rdx, r15; struct _GUID *
0x180042580  mov     [rbp+40h+var_88], rax
0x180042584  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180042589  mov     rcx, rax; this
0x18004258c  mov     rax, [rax+18h]
0x180042590  test    rax, rax
0x180042593  jnz     short loc_18004259A
0x180042595  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18004259a  mov     rcx, [rbp+40h+var_88]
0x18004259e  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x1800425a5  mov     [rsp+140h+var_118], rcx; __int64
0x1800425aa  mov     edx, 147h
0x1800425af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800425b6  mov     r9, r14
0x1800425b9  mov     qword ptr [rsp+140h+var_120], rax; __int64
0x1800425be  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800425c5  call    WPP_SF_qsS
0x1800425ca  mov     eax, dword ptr [rbp+40h+arg_18]
0x1800425cd  test    al, 1
0x1800425cf  jz      short loc_1800425E0
0x1800425d1  and     eax, 0FFFFFFFEh
0x1800425d4  lea     rcx, [rbp+40h+var_60]; this
0x1800425d8  mov     dword ptr [rbp+40h+arg_18], eax
0x1800425db  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800425e0  mov     rcx, qword ptr [rbp+40h+var_B0]
0x1800425e4  mov     rax, [r15+rcx]
0x1800425e8  sub     rax, qword ptr cs:KSCATEGORY_SENSOR_GROUP_INTERNAL.Data1
0x1800425ef  jnz     short loc_1800425FD
0x1800425f1  mov     rax, [r15+rcx+8]
0x1800425f6  sub     rax, qword ptr cs:KSCATEGORY_SENSOR_GROUP_INTERNAL.Data4
0x1800425fd  test    rax, rax
0x180042600  jz      short loc_180042624
0x180042602  mov     rax, [r15+rcx]
0x180042606  sub     rax, cs:KSCATEGORY_FRAMEPROVIDER
0x18004260d  jnz     short loc_18004261B
0x18004260f  mov     rax, [r15+rcx+8]
0x180042614  sub     rax, cs:qword_18007C2B8
0x18004261b  test    rax, rax
0x18004261e  jnz     loc_1800426A5
0x180042624  mov     r12, [rbp+40h+var_A0]
0x180042628  lea     r8, [rbp+40h+var_88]; unsigned __int64 *
0x18004262c  mov     rcx, r12; unsigned __int16 *
0x18004262f  mov     [rbp+40h+var_88], 0
0x180042637  mov     edx, 7FFFFFFFh; unsigned __int64
0x18004263c  mov     dword ptr [rbp+40h+var_A8], 0
0x180042643  mov     [rbp+40h+var_70], 0
0x18004264b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180042650  mov     esi, eax
0x180042652  test    eax, eax
0x180042654  js      loc_1800426DB
0x18004265a  mov     rcx, [rbp+40h+var_B8]
0x18004265e  lea     rdx, [rbp+40h+var_A8]
0x180042662  mov     r8, [rbp+40h+var_88]
0x180042666  lea     r9, [rbp+40h+var_70]
0x18004266a  inc     r8
0x18004266d  mov     qword ptr [rsp+140h+var_120], rdx
0x180042672  add     r8d, r8d
0x180042675  mov     edx, 4
0x18004267a  mov     rax, [rcx]
0x18004267d  mov     rax, [rax+0C0h]
0x180042684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042689  mov     esi, eax
0x18004268b  test    eax, eax
0x18004268d  js      short loc_1800426C4
0x18004268f  mov     edx, dword ptr [rbp+40h+var_A8]; unsigned __int64
0x180042692  mov     r8, [rbp+40h+var_A0]; unsigned __int16 *
0x180042696  mov     rcx, [rbp+40h+var_70]; unsigned __int16 *
0x18004269a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004269f  mov     esi, eax
0x1800426a1  test    eax, eax
0x1800426a3  js      short loc_1800426AD
0x1800426a5  inc     r13d
0x1800426a8  jmp     loc_180042507
0x1800426ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800426b4  jb      loc_180042A14
0x1800426ba  mov     edx, 14Ah
0x1800426bf  jmp     loc_180042275
0x1800426c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800426cb  jb      loc_180042A14
0x1800426d1  mov     edx, 149h
  ... truncated ...
```

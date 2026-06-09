# FSMonitorService::KsProxySetControl(ushort const *,KSIDENTIFIER *)

- ea: `0x180009f90`
- end: `0x18000a432`
- name: `?KsProxySetControl@FSMonitorService@@UEAAJPEBGPEAUKSIDENTIFIER@@@Z`
- size: `1186`
- prototype: `int(FSMonitorService *__hidden this, const unsigned __int16 *, struct KSIDENTIFIER *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180006a98`
- `0x180006eb8`
- `0x180007348`
- `0x180009f90`
- `0x18000d594`
- `0x18000d6ac`
- `0x18002fa3c`
- `0x18002fa70`
- `0x1800437cc`
- `0x18004bf44`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFGetSensorGroupIdFromDeviceName` at `0x18000a0db`
- `MFSENSORGROUP!MFGetSensorGroupIdFromDeviceName` at `0x18000a0db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a403`
- `MFPlat!MFScheduleWorkItem` at `0x18000a2f6`
- `MFPlat!MFScheduleWorkItem` at `0x18000a2f6`

## pseudocode

```c
__int64 __fastcall FSMonitorService::KsProxySetControl(
        FSMonitorService *this,
        const unsigned __int16 *a2,
        struct KSIDENTIFIER *a3)
{
  char v4; // r15
  const struct std::nothrow_t *v7; // rdx
  __int64 v8; // r8
  const unsigned __int8 *v9; // r9
  int v10; // edi
  KSPropertyTrace *v11; // rax
  const char *String; // rax
  __int64 v13; // rdx
  HRESULT v14; // eax
  __int64 v15; // rdx
  unsigned __int16 v16; // r12
  __int64 v17; // r13
  __int64 v18; // rax
  __int64 v19; // rcx
  KSPropertyTrace *v20; // rax
  const char *v21; // rax
  bool v22; // zf
  KSPropertyTrace *v23; // rax
  const char *v24; // rax
  struct IFSCameraControlStates *v26; // [rsp+30h] [rbp-69h] BYREF
  ULONG Id; // [rsp+38h] [rbp-61h]
  int v28; // [rsp+3Ch] [rbp-5Dh] BYREF
  unsigned int v29; // [rsp+40h] [rbp-59h]
  void **v30; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v31[24]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v32; // [rsp+68h] [rbp-31h]
  _OWORD Buf2[2]; // [rsp+70h] [rbp-29h] BYREF
  _OWORD Buf1[2]; // [rsp+90h] [rbp-9h] BYREF

  v4 = 0;
  Id = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v10 = 0;
  v26 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  v28 = 0;
  memset(Buf1, 0, sizeof(Buf1));
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v11 = KSPropertyTrace::KSPropertyTrace((KSPropertyTrace *)&v30, a3, v8, v9);
    String = FSString::GetString((KSPropertyTrace *)((char *)v11 + 8));
    WPP_SF_qSs(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)a2, (__int64)String);
    v4 = 1;
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    v30 = &SensorGroupBlobHeaderTrace::`vftable';
    FSString::~FSString((FSString *)v31, v7);
  }
  if ( *((_DWORD *)this + 23) == 3 )
    goto LABEL_51;
  if ( !a2 )
  {
    v10 = -2147024809;
    if ( !g_wppLevels )
    {
LABEL_48:
      if ( byte_18005E5A5 )
      {
        v4 |= 2u;
        v20 = KSPropertyTrace::KSPropertyTrace((KSPropertyTrace *)&v30, a3, v8, v9);
        v21 = FSString::GetString((KSPropertyTrace *)((char *)v20 + 8));
        WPP_SF_qDs(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          131,
          (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
          (_DWORD)this,
          v10,
          (__int64)v21);
      }
      v22 = (v4 & 2) == 0;
      goto LABEL_54;
    }
    v13 = 124;
LABEL_9:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      this,
      -2147024809);
    goto LABEL_48;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_48;
    v13 = 125;
    goto LABEL_9;
  }
  Id = a3->Id;
  v14 = MFGetSensorGroupIdFromDeviceName(a2, 32, Buf2, &v28);
  v10 = v14;
  if ( v14 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_47;
    v15 = 126;
    goto LABEL_16;
  }
  if ( a3->Alignment == *(_QWORD *)&GUID_c6e13360_30ac_11d0_a18c_00a0c9118956.Data1
    && *(&a3->Alignment + 1) == *(_QWORD *)GUID_c6e13360_30ac_11d0_a18c_00a0c9118956.Data4 )
  {
    v16 = 1;
  }
  else if ( a3->Alignment == *(_QWORD *)&GUID_c6e13370_30ac_11d0_a18c_00a0c9118956.Data1
         && *(&a3->Alignment + 1) == *(_QWORD *)GUID_c6e13370_30ac_11d0_a18c_00a0c9118956.Data4 )
  {
    v16 = 2;
  }
  else if ( a3->Alignment == *(_QWORD *)&GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
         && *(&a3->Alignment + 1) == *(_QWORD *)GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4 )
  {
    v16 = 3;
  }
  else if ( a3->Alignment == *(_QWORD *)&GUID_1666d655_21a6_4982_9728_52c39e869f90.Data1
         && *(&a3->Alignment + 1) == *(_QWORD *)GUID_1666d655_21a6_4982_9728_52c39e869f90.Data4 )
  {
    v16 = 4;
  }
  else
  {
    v16 = 0;
  }
  v17 = 0;
  v29 = *((_DWORD *)this + 52);
  if ( v29 )
  {
    while ( 1 )
    {
      v18 = *((_QWORD *)this + 25);
      v32 = (unsigned int)v17;
      v14 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64))(**(_QWORD **)(v18 + 8 * v17) + 24LL))(
              *(_QWORD *)(v18 + 8 * v17),
              Buf1,
              32);
      v10 = v14;
      if ( v14 < 0 )
        break;
      if ( !memcmp_0(Buf1, Buf2, 0x20u) )
      {
        v19 = *(_QWORD *)(*((_QWORD *)this + 25) + 8 * v32);
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 64LL))(v19, v16, Id);
        v10 = v14;
        if ( v14 >= 0 )
          goto LABEL_42;
        if ( g_wppLevels )
        {
          v15 = 128;
          goto LABEL_16;
        }
        goto LABEL_47;
      }
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= v29 )
        goto LABEL_34;
    }
    if ( !g_wppLevels )
      goto LABEL_47;
    v15 = 127;
    goto LABEL_16;
  }
LABEL_34:
  v26 = 0;
  FSCameraControlStates::CreateCameraControlStates((unsigned __int8 *)Buf2, (__int64)v7, &v26);
  (*(void (__fastcall **)(struct IFSCameraControlStates *, _QWORD, _QWORD))(*(_QWORD *)v26 + 64LL))(v26, v16, a3->Id);
  if ( !(unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)this + 25, (__int64)v26) )
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
        this,
        -2147024882);
    goto LABEL_48;
  }
LABEL_42:
  if ( !*((_BYTE *)this + 224) )
  {
    v14 = MFScheduleWorkItem((IMFAsyncCallback *)this + 4, 0, -500, 0);
    v10 = v14;
    if ( v14 >= 0 )
    {
      *((_BYTE *)this + 224) = 1;
    }
    else if ( g_wppLevels )
    {
      v15 = 130;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v14);
    }
  }
LABEL_47:
  if ( v10 < 0 )
    goto LABEL_48;
LABEL_51:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v4 |= 4u;
    v23 = KSPropertyTrace::KSPropertyTrace((KSPropertyTrace *)&v30, a3, v8, v9);
    v24 = FSString::GetString((KSPropertyTrace *)((char *)v23 + 8));
    WPP_SF_qDs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      132,
      (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      (_DWORD)this,
      v10,
      (__int64)v24);
  }
  v22 = (v4 & 4) == 0;
LABEL_54:
  if ( !v22 )
  {
    v30 = &SensorGroupBlobHeaderTrace::`vftable';
    FSString::~FSString((FSString *)v31, v7);
  }
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v26);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009f90  mov     [rsp-8+arg_18], rbx
0x180009f95  push    rbp
0x180009f96  push    rsi
0x180009f97  push    rdi
0x180009f98  push    r12
0x180009f9a  push    r13
0x180009f9c  push    r14
0x180009f9e  push    r15
0x180009fa0  lea     rbp, [rsp-27h]
0x180009fa5  sub     rsp, 0C0h
0x180009fac  mov     rax, cs:__security_cookie
0x180009fb3  xor     rax, rsp
0x180009fb6  mov     [rbp+57h+var_40], rax
0x180009fba  mov     rsi, rcx
0x180009fbd  xor     r15d, r15d
0x180009fc0  add     rcx, 30h ; '0'; lpCriticalSection
0x180009fc4  mov     [rbp+57h+var_B8], r15d
0x180009fc8  mov     r14, r8
0x180009fcb  mov     r12, rdx
0x180009fce  call    cs:__imp_EnterCriticalSection
0x180009fd4  xor     edi, edi
0x180009fd6  xorps   xmm0, xmm0
0x180009fd9  xorps   xmm1, xmm1
0x180009fdc  mov     [rbp+57h+var_C0], rdi
0x180009fe0  movups  [rbp+57h+Buf2], xmm0
0x180009fe4  mov     [rbp+57h+var_B4], edi
0x180009fe7  movups  [rbp+57h+var_70], xmm0
0x180009feb  movups  [rbp+57h+Buf1], xmm1
0x180009fef  movups  [rbp+57h+var_50], xmm1
0x180009ff3  cmp     cs:byte_18005E5A5, 8
0x180009ffa  lea     r13d, [r15+1]
0x180009ffe  jb      short loc_18000A038
0x18000a000  mov     rdx, r14; struct KSIDENTIFIER *
0x18000a003  lea     rcx, [rbp+57h+var_A8]; this
0x18000a007  call    ??0KSPropertyTrace@@QEAA@QEAUKSIDENTIFIER@@@Z; KSPropertyTrace::KSPropertyTrace(KSIDENTIFIER * const)
0x18000a00c  lea     rcx, [rax+8]; this
0x18000a010  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18000a015  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a01c  mov     r9, rsi
0x18000a01f  mov     [rsp+0F0h+var_C8], rax; __int64
0x18000a024  mov     [rsp+0F0h+var_D0], r12; __int64
0x18000a029  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18000a030  call    WPP_SF_qSs
0x18000a035  mov     r15d, r13d
0x18000a038  lea     rax, ??_7SensorGroupBlobHeaderTrace@@6B@; const SensorGroupBlobHeaderTrace::`vftable'
0x18000a03f  test    r13b, r15b
0x18000a042  jz      short loc_18000A055
0x18000a044  and     r15d, 0FFFFFFFEh
0x18000a048  mov     [rbp+57h+var_A8], rax
0x18000a04c  lea     rcx, [rbp+57h+var_A0]; this
0x18000a050  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18000a055  cmp     dword ptr [rsi+5Ch], 3
0x18000a059  mov     eax, 4
0x18000a05e  jz      loc_18000A38C
0x18000a064  test    r12, r12
0x18000a067  jnz     short loc_18000A0A5
0x18000a069  mov     eax, 80070057h
0x18000a06e  mov     edi, eax
0x18000a070  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18000a077  jb      loc_18000A334
0x18000a07d  lea     edx, [r12+7Ch]
0x18000a082  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18000a086  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a08d  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000a094  mov     r9, rsi
0x18000a097  mov     rcx, [rcx+10h]
0x18000a09b  call    WPP_SF_qD
0x18000a0a0  jmp     loc_18000A334
0x18000a0a5  test    r14, r14
0x18000a0a8  jnz     short loc_18000A0C4
0x18000a0aa  mov     eax, 80070057h
0x18000a0af  mov     edi, eax
0x18000a0b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18000a0b8  jb      loc_18000A334
0x18000a0be  lea     edx, [r14+7Dh]
0x18000a0c2  jmp     short loc_18000A082
0x18000a0c4  mov     eax, [r14+10h]
0x18000a0c8  lea     r9, [rbp+57h+var_B4]
0x18000a0cc  lea     r8, [rbp+57h+Buf2]
0x18000a0d0  mov     [rbp+57h+var_B8], eax
0x18000a0d3  mov     edx, 20h ; ' '
0x18000a0d8  mov     rcx, r12
0x18000a0db  call    cs:__imp_MFGetSensorGroupIdFromDeviceName
0x18000a0e1  mov     edi, eax
0x18000a0e3  test    eax, eax
0x18000a0e5  jns     short loc_18000A11C
0x18000a0e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18000a0ee  jb      loc_18000A330
0x18000a0f4  mov     edx, 7Eh ; '~'
0x18000a0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a100  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000a107  mov     r9, rsi
0x18000a10a  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18000a10e  mov     rcx, [rcx+10h]
0x18000a112  call    WPP_SF_qD
0x18000a117  jmp     loc_18000A330
0x18000a11c  mov     rax, [r14]
0x18000a11f  cmp     rax, qword ptr cs:_GUID_c6e13360_30ac_11d0_a18c_00a0c9118956.Data1
0x18000a126  jnz     short loc_18000A13B
0x18000a128  mov     rax, [r14+8]
0x18000a12c  cmp     rax, qword ptr cs:_GUID_c6e13360_30ac_11d0_a18c_00a0c9118956.Data4
0x18000a133  jnz     short loc_18000A13B
0x18000a135  movzx   r12d, r13w
0x18000a139  jmp     short loc_18000A1A4
0x18000a13b  mov     rax, [r14]
0x18000a13e  cmp     rax, qword ptr cs:_GUID_c6e13370_30ac_11d0_a18c_00a0c9118956.Data1
0x18000a145  jnz     short loc_18000A15C
0x18000a147  mov     rax, [r14+8]
0x18000a14b  cmp     rax, qword ptr cs:_GUID_c6e13370_30ac_11d0_a18c_00a0c9118956.Data4
0x18000a152  jnz     short loc_18000A15C
0x18000a154  mov     r12d, 2
0x18000a15a  jmp     short loc_18000A1A4
0x18000a15c  mov     rax, [r14]
0x18000a15f  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
0x18000a166  jnz     short loc_18000A17D
0x18000a168  mov     rax, [r14+8]
0x18000a16c  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4
0x18000a173  jnz     short loc_18000A17D
0x18000a175  mov     r12d, 3
0x18000a17b  jmp     short loc_18000A1A4
0x18000a17d  mov     rax, [r14]
0x18000a180  cmp     rax, qword ptr cs:_GUID_1666d655_21a6_4982_9728_52c39e869f90.Data1
0x18000a187  jnz     short loc_18000A19E
0x18000a189  mov     rax, [r14+8]
0x18000a18d  cmp     rax, qword ptr cs:_GUID_1666d655_21a6_4982_9728_52c39e869f90.Data4
0x18000a194  jnz     short loc_18000A19E
0x18000a196  mov     r12d, 4
0x18000a19c  jmp     short loc_18000A1A4
0x18000a19e  xor     eax, eax
0x18000a1a0  movzx   r12d, ax
0x18000a1a4  mov     eax, [rsi+0D0h]
0x18000a1aa  xor     r13d, r13d
0x18000a1ad  mov     [rbp+57h+var_B0], eax
0x18000a1b0  test    eax, eax
0x18000a1b2  jz      short loc_18000A20A
0x18000a1b4  mov     rax, [rsi+0C8h]
0x18000a1bb  lea     rdx, [rbp+57h+Buf1]
0x18000a1bf  mov     ecx, r13d
0x18000a1c2  mov     r8d, 20h ; ' '
0x18000a1c8  mov     [rbp+57h+var_88], rcx
0x18000a1cc  mov     rcx, [rax+r13*8]
0x18000a1d0  mov     rax, [rcx]
0x18000a1d3  mov     rax, [rax+18h]
0x18000a1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1dc  mov     edi, eax
0x18000a1de  test    eax, eax
0x18000a1e0  js      loc_18000A2C5
0x18000a1e6  mov     r8d, 20h ; ' '; Size
0x18000a1ec  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000a1f0  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000a1f4  call    memcmp_0
0x18000a1f9  test    eax, eax
0x18000a1fb  jz      loc_18000A284
0x18000a201  inc     r13d
0x18000a204  cmp     r13d, [rbp+57h+var_B0]
0x18000a208  jb      short loc_18000A1B4
0x18000a20a  mov     rcx, [rbp+57h+var_C0]
0x18000a20e  mov     [rbp+57h+var_C0], 0
0x18000a216  test    rcx, rcx
0x18000a219  jz      short loc_18000A227
0x18000a21b  mov     rax, [rcx]
0x18000a21e  mov     rax, [rax+10h]
0x18000a222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a227  lea     r8, [rbp+57h+var_C0]; struct IFSCameraControlStates **
0x18000a22b  lea     rcx, [rbp+57h+Buf2]; unsigned __int8 *
0x18000a22f  call    ?CreateCameraControlStates@FSCameraControlStates@@SAJPEAEKPEAPEAUIFSCameraControlStates@@@Z; FSCameraControlStates::CreateCameraControlStates(uchar *,ulong,IFSCameraControlStates * *)
0x18000a234  mov     rcx, [rbp+57h+var_C0]
0x18000a238  movzx   edx, r12w
0x18000a23c  mov     r8d, [r14+10h]
0x18000a240  mov     rax, [rcx]
0x18000a243  mov     rax, [rax+40h]
0x18000a247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24c  mov     rdx, [rbp+57h+var_C0]
0x18000a250  lea     rcx, [rsi+0C8h]
0x18000a257  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x18000a25c  test    eax, eax
0x18000a25e  jnz     short loc_18000A2DD
0x18000a260  mov     edi, 8007000Eh
0x18000a265  lea     r13d, [rax+1]
0x18000a269  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18000a270  jb      loc_18000A334
0x18000a276  mov     edx, 81h
0x18000a27b  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18000a27f  jmp     loc_18000A086
0x18000a284  mov     rax, [rsi+0C8h]
0x18000a28b  movzx   edx, r12w
0x18000a28f  mov     rcx, [rbp+57h+var_88]
0x18000a293  mov     r8d, [rbp+57h+var_B8]
0x18000a297  mov     rcx, [rax+rcx*8]
0x18000a29b  mov     rax, [rcx]
0x18000a29e  mov     rax, [rax+40h]
0x18000a2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a7  mov     edi, eax
0x18000a2a9  test    eax, eax
0x18000a2ab  jns     short loc_18000A2DD
0x18000a2ad  mov     r13d, 1
0x18000a2b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18000a2ba  jb      short loc_18000A330
0x18000a2bc  lea     edx, [r13+7Fh]
0x18000a2c0  jmp     loc_18000A0F9
0x18000a2c5  mov     r13d, 1
0x18000a2cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18000a2d2  jb      short loc_18000A330
0x18000a2d4  lea     edx, [r13+7Eh]
0x18000a2d8  jmp     loc_18000A0F9
0x18000a2dd  cmp     byte ptr [rsi+0E0h], 0
0x18000a2e4  jnz     short loc_18000A32A
0x18000a2e6  lea     rcx, [rsi+20h]; pCallback
0x18000a2ea  xor     r9d, r9d; pKey
0x18000a2ed  xor     edx, edx; pState
0x18000a2ef  mov     r8, 0FFFFFFFFFFFFFE0Ch; Timeout
0x18000a2f6  call    cs:__imp_MFScheduleWorkItem
0x18000a2fc  mov     edi, eax
0x18000a2fe  test    eax, eax
0x18000a300  jns     short loc_18000A31B
0x18000a302  mov     r13d, 1
0x18000a308  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18000a30f  jb      short loc_18000A330
0x18000a311  mov     edx, 82h
0x18000a316  jmp     loc_18000A0F9
0x18000a31b  mov     r13d, 1
0x18000a321  mov     [rsi+0E0h], r13b
0x18000a328  jmp     short loc_18000A330
0x18000a32a  mov     r13d, 1
0x18000a330  test    edi, edi
0x18000a332  jns     short loc_18000A387
0x18000a334  cmp     cs:byte_18005E5A5, r13b
0x18000a33b  jb      short loc_18000A381
0x18000a33d  mov     rdx, r14; struct KSIDENTIFIER *
0x18000a340  lea     rcx, [rbp+57h+var_A8]; this
0x18000a344  or      r15d, 2
0x18000a348  call    ??0KSPropertyTrace@@QEAA@QEAUKSIDENTIFIER@@@Z; KSPropertyTrace::KSPropertyTrace(KSIDENTIFIER * const)
0x18000a34d  lea     rcx, [rax+8]; this
0x18000a351  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18000a356  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a35d  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000a364  mov     [rsp+0F0h+var_C8], rax
0x18000a369  mov     edx, 83h
0x18000a36e  mov     r9, rsi
0x18000a371  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18000a375  mov     rcx, [rcx+0D8h]
0x18000a37c  call    WPP_SF_qDs
0x18000a381  test    r15b, 2
0x18000a385  jmp     short loc_18000A3E0
0x18000a387  mov     eax, 4
0x18000a38c  cmp     cs:byte_18005E5A5, 8
0x18000a393  jb      short loc_18000A3D8
0x18000a395  mov     rdx, r14; struct KSIDENTIFIER *
0x18000a398  lea     rcx, [rbp+57h+var_A8]; this
0x18000a39c  or      r15d, eax
0x18000a39f  call    ??0KSPropertyTrace@@QEAA@QEAUKSIDENTIFIER@@@Z; KSPropertyTrace::KSPropertyTrace(KSIDENTIFIER * const)
0x18000a3a4  lea     rcx, [rax+8]; this
0x18000a3a8  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18000a3ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3b4  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000a3bb  mov     [rsp+0F0h+var_C8], rax
0x18000a3c0  mov     edx, 84h
0x18000a3c5  mov     r9, rsi
0x18000a3c8  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18000a3cc  mov     rcx, [rcx+0D8h]
0x18000a3d3  call    WPP_SF_qDs
0x18000a3d8  mov     eax, 4
0x18000a3dd  test    al, r15b
0x18000a3e0  jz      short loc_18000A3F6
0x18000a3e2  lea     rax, ??_7SensorGroupBlobHeaderTrace@@6B@; const SensorGroupBlobHeaderTrace::`vftable'
0x18000a3e9  lea     rcx, [rbp+57h+var_A0]; this
0x18000a3ed  mov     [rbp+57h+var_A8], rax
0x18000a3f1  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18000a3f6  lea     rcx, [rbp+57h+var_C0]
0x18000a3fa  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000a3ff  lea     rcx, [rsi+30h]; lpCriticalSection
0x18000a403  call    cs:__imp_LeaveCriticalSection
0x18000a409  mov     eax, edi
0x18000a40b  mov     rcx, [rbp+57h+var_40]
0x18000a40f  xor     rcx, rsp; StackCookie
0x18000a412  call    __security_check_cookie
0x18000a417  mov     rbx, [rsp+0F0h+arg_18]
0x18000a41f  add     rsp, 0C0h
0x18000a426  pop     r15
0x18000a428  pop     r14
0x18000a42a  pop     r13
0x18000a42c  pop     r12
0x18000a42e  pop     rdi
0x18000a42f  pop     rsi
0x18000a430  pop     rbp
0x18000a431  retn
```

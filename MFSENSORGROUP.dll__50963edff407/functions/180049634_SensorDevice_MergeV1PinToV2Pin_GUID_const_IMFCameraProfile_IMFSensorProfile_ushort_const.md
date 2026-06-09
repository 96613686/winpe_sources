# SensorDevice::MergeV1PinToV2Pin(_GUID const &,IMFCameraProfile *,IMFSensorProfile *,ushort const *)

- ea: `0x180049634`
- end: `0x180049ad1`
- name: `?MergeV1PinToV2Pin@SensorDevice@@IEAAJAEBU_GUID@@PEAUIMFCameraProfile@@PEAUIMFSensorProfile@@PEBG@Z`
- size: `1181`
- prototype: `__int64 __fastcall(SensorDevice *__hidden this, const struct _GUID *, struct IMFCameraProfile *, struct IMFSensorProfile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047880`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180044f30`
- `0x180048108`
- `0x180049634`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18004987e`
- `MFPlat!MFCreateMediaType` at `0x18004987e`

## pseudocode

```c
__int64 __fastcall SensorDevice::MergeV1PinToV2Pin(
        SensorDevice *this,
        const struct _GUID *a2,
        struct IMFCameraProfile *a3,
        __int64 (__fastcall ***a4)(struct IMFSensorProfile *, GUID *, __int64 *))
{
  __int64 (__fastcall **v4)(struct IMFSensorProfile *, GUID *, __int64 *); // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int i; // r15d
  __int64 v12; // rax
  int v13; // eax
  unsigned int j; // r14d
  HRESULT v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v20; // [rsp+30h] [rbp-51h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v22; // [rsp+40h] [rbp-41h] BYREF
  __int64 v23; // [rsp+48h] [rbp-39h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-31h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v26; // [rsp+5Ch] [rbp-25h] BYREF
  unsigned int v27; // [rsp+60h] [rbp-21h] BYREF
  __int64 v28; // [rsp+68h] [rbp-19h] BYREF
  _OWORD v29[2]; // [rsp+70h] [rbp-11h] BYREF
  __int64 v30; // [rsp+90h] [rbp+Fh]

  v4 = *a4;
  v25 = 0;
  v28 = 0;
  v8 = (*v4)((struct IMFSensorProfile *)a4, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, &v28);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( (*(int (__fastcall **)(struct IMFCameraProfile *, const struct _GUID *, unsigned int *))(*(_QWORD *)a3 + 40LL))(
           a3,
           a2,
           &v25) >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v25 )
          goto LABEL_57;
        v12 = *(_QWORD *)a3;
        v27 = -1;
        v20 = 0;
        v22 = -1;
        v13 = (*(__int64 (__fastcall **)(struct IMFCameraProfile *, const struct _GUID *, _QWORD, __int64 *))(v12 + 48))(
                a3,
                a2,
                i,
                &v20);
        v9 = v13;
        if ( v13 < 0 )
          break;
        v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 56LL))(v20, &v22);
        v9 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_56;
          v18 = 340;
LABEL_55:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v18,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v13);
          goto LABEL_56;
        }
        if ( SensorDevice::GetStreamIdFromCameraProfile(this, a2, v22, &v27) )
        {
          v26 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 32LL))(v20, &v26);
          v9 = v13;
          if ( v13 >= 0 )
          {
            for ( j = 0; ; ++j )
            {
              if ( j >= v26 )
                goto LABEL_30;
              v24 = 0;
              v30 = 0;
              v23 = 0;
              ppMFType = 0;
              memset(v29, 0, sizeof(v29));
              v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v20 + 40LL))(v20, j, &v24);
              v9 = v15;
              if ( v15 < 0 )
                break;
              v15 = (**v24)(v24, &GUID_41571254_67a7_464b_84f8_2cd7f8556281, &v23);
              v9 = v15;
              if ( v15 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_34;
                v17 = 343;
                goto LABEL_33;
              }
              v15 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v23 + 32LL))(v23, v29);
              v9 = v15;
              if ( v15 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_34;
                v17 = 344;
                goto LABEL_33;
              }
              v15 = MFCreateMediaType(&ppMFType);
              v9 = v15;
              if ( v15 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_34;
                v17 = 345;
                goto LABEL_33;
              }
              v15 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                      ppMFType,
                      &MF_MT_MAJOR_TYPE,
                      &MFMediaType_Video);
              v9 = v15;
              if ( v15 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_34;
                v17 = 346;
                goto LABEL_33;
              }
              v15 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))ppMFType->lpVtbl->SetUINT64)(
                      ppMFType,
                      &MF_MT_FRAME_SIZE,
                      DWORD1(v29[0]) | ((unsigned __int64)LODWORD(v29[0]) << 32));
              v9 = v15;
              if ( v15 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_34;
                v17 = 347;
                goto LABEL_33;
              }
              v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data1;
              if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data1 )
                v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data4;
              if ( v16 )
              {
                v15 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))ppMFType->lpVtbl->SetUINT64)(
                        ppMFType,
                        &MF_MT_FRAME_RATE,
                        HIDWORD(v29[0]) | ((unsigned __int64)DWORD2(v29[0]) << 32));
                v9 = v15;
                if ( v15 < 0 )
                {
                  if ( g_wppLevels )
                  {
                    v17 = 348;
                    goto LABEL_33;
                  }
LABEL_34:
                  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFType);
                  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v23);
                  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v24);
                  goto LABEL_56;
                }
              }
              v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFMediaType *))(*(_QWORD *)v28 + 120LL))(
                      v28,
                      v27,
                      ppMFType);
              v9 = v15;
              if ( v15 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_34;
                v17 = 349;
                goto LABEL_33;
              }
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFType);
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v23);
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v24);
            }
            if ( !g_wppLevels )
              goto LABEL_34;
            v17 = 342;
LABEL_33:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v17,
              &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
              this,
              v15);
            goto LABEL_34;
          }
          if ( g_wppLevels )
          {
            v18 = 341;
            goto LABEL_55;
          }
LABEL_56:
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v20);
          goto LABEL_57;
        }
LABEL_30:
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v20);
      }
      if ( !g_wppLevels )
        goto LABEL_56;
      v18 = 339;
      goto LABEL_55;
    }
    v22 = -1;
    if ( SensorDevice::GetStreamIdFromCameraProfile(this, a2, 0, &v22) )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v28 + 32LL))(
             v28,
             v22,
             L"((RES==;FRT==;SUT==))");
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 338;
          goto LABEL_4;
        }
      }
    }
  }
  else if ( g_wppLevels )
  {
    v10 = 337;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v8);
  }
LABEL_57:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v28);
  return v9;
}

```

## disassembly

```asm
0x180049634  push    rbp
0x180049636  push    rbx
0x180049637  push    rsi
0x180049638  push    rdi
0x180049639  push    r12
0x18004963b  push    r14
0x18004963d  push    r15
0x18004963f  lea     rbp, [rsp-1Fh]
0x180049644  sub     rsp, 0A0h
0x18004964b  mov     rax, cs:__security_cookie
0x180049652  xor     rax, rsp
0x180049655  mov     [rbp+4Fh+var_38], rax
0x180049659  mov     rax, [r9]
0x18004965c  mov     r12, r8
0x18004965f  mov     rsi, rdx
0x180049662  mov     [rbp+4Fh+var_78], 0
0x180049669  mov     rdi, rcx
0x18004966c  mov     [rbp+4Fh+var_68], 0
0x180049674  lea     r8, [rbp+4Fh+var_68]
0x180049678  mov     rcx, r9
0x18004967b  mov     rax, [rax]
0x18004967e  lea     rdx, _GUID_b35b06ef_9123_4604_a586_9750cdd2c67d
0x180049685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004968a  mov     ebx, eax
0x18004968c  test    eax, eax
0x18004968e  jns     short loc_1800496C5
0x180049690  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049697  jb      loc_180049AA8
0x18004969d  mov     edx, 151h
0x1800496a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800496a9  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x1800496b0  mov     r9, rdi
0x1800496b3  mov     [rsp+0D0h+var_B0], eax
0x1800496b7  mov     rcx, [rcx+10h]
0x1800496bb  call    WPP_SF_qD
0x1800496c0  jmp     loc_180049AA8
0x1800496c5  mov     rax, [r12]
0x1800496c9  lea     r8, [rbp+4Fh+var_78]
0x1800496cd  mov     rdx, rsi
0x1800496d0  mov     rcx, r12
0x1800496d3  mov     rax, [rax+28h]
0x1800496d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496dc  test    eax, eax
0x1800496de  jns     short loc_18004973C
0x1800496e0  lea     r9, [rbp+4Fh+var_90]; unsigned int *
0x1800496e4  mov     [rbp+4Fh+var_90], 0FFFFFFFFh
0x1800496eb  xor     r8d, r8d; unsigned int
0x1800496ee  mov     rdx, rsi; struct _GUID *
0x1800496f1  mov     rcx, rdi; this
0x1800496f4  call    ?GetStreamIdFromCameraProfile@SensorDevice@@IEAA_NAEBU_GUID@@IPEAI@Z; SensorDevice::GetStreamIdFromCameraProfile(_GUID const &,uint,uint *)
0x1800496f9  test    al, al
0x1800496fb  jz      loc_180049AA8
0x180049701  mov     rcx, [rbp+4Fh+var_68]
0x180049705  lea     r8, aResFrtSut; "((RES==;FRT==;SUT==))"
0x18004970c  mov     edx, [rbp+4Fh+var_90]
0x18004970f  mov     rax, [rcx]
0x180049712  mov     rax, [rax+20h]
0x180049716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004971b  mov     ebx, eax
0x18004971d  test    eax, eax
0x18004971f  jns     loc_180049AA8
0x180049725  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004972c  jb      loc_180049AA8
0x180049732  mov     edx, 152h
0x180049737  jmp     loc_1800496A2
0x18004973c  xor     r15d, r15d
0x18004973f  cmp     r15d, [rbp+4Fh+var_78]
0x180049743  jnb     loc_180049AA8
0x180049749  mov     rax, [r12]
0x18004974d  lea     r9, [rbp+4Fh+var_A0]
0x180049751  mov     r8d, r15d
0x180049754  mov     [rbp+4Fh+var_70], 0FFFFFFFFh
0x18004975b  mov     rdx, rsi
0x18004975e  mov     [rbp+4Fh+var_A0], 0
0x180049766  mov     rcx, r12
0x180049769  mov     [rbp+4Fh+var_90], 0FFFFFFFFh
0x180049770  mov     rax, [rax+30h]
0x180049774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049779  mov     ebx, eax
0x18004977b  test    eax, eax
0x18004977d  js      loc_180049A73
0x180049783  mov     rcx, [rbp+4Fh+var_A0]
0x180049787  lea     rdx, [rbp+4Fh+var_90]
0x18004978b  mov     rax, [rcx]
0x18004978e  mov     rax, [rax+38h]
0x180049792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049797  mov     ebx, eax
0x180049799  test    eax, eax
0x18004979b  js      loc_180049A63
0x1800497a1  mov     r8d, [rbp+4Fh+var_90]; unsigned int
0x1800497a5  lea     r9, [rbp+4Fh+var_70]; unsigned int *
0x1800497a9  mov     rdx, rsi; struct _GUID *
0x1800497ac  mov     rcx, rdi; this
0x1800497af  call    ?GetStreamIdFromCameraProfile@SensorDevice@@IEAA_NAEBU_GUID@@IPEAI@Z; SensorDevice::GetStreamIdFromCameraProfile(_GUID const &,uint,uint *)
0x1800497b4  test    al, al
0x1800497b6  jz      loc_180049979
0x1800497bc  mov     rcx, [rbp+4Fh+var_A0]
0x1800497c0  lea     rdx, [rbp+4Fh+var_74]
0x1800497c4  mov     [rbp+4Fh+var_74], 0
0x1800497cb  mov     rax, [rcx]
0x1800497ce  mov     rax, [rax+20h]
0x1800497d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497d7  mov     ebx, eax
0x1800497d9  test    eax, eax
0x1800497db  js      loc_180049A53
0x1800497e1  xor     r14d, r14d
0x1800497e4  cmp     r14d, [rbp+4Fh+var_74]
0x1800497e8  jnb     loc_180049979
0x1800497ee  mov     rcx, [rbp+4Fh+var_A0]
0x1800497f2  lea     r8, [rbp+4Fh+var_80]
0x1800497f6  xor     eax, eax
0x1800497f8  mov     [rbp+4Fh+var_80], 0
0x180049800  xorps   xmm0, xmm0
0x180049803  mov     [rbp+4Fh+var_40], rax
0x180049807  mov     [rbp+4Fh+var_88], 0
0x18004980f  mov     edx, r14d
0x180049812  mov     [rbp+4Fh+ppMFType], 0
0x18004981a  movups  [rbp+4Fh+var_60], xmm0
0x18004981e  movups  [rbp+4Fh+var_50], xmm0
0x180049822  mov     rax, [rcx]
0x180049825  mov     rax, [rax+28h]
0x180049829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004982e  mov     ebx, eax
0x180049830  test    eax, eax
0x180049832  js      loc_180049A3C
0x180049838  mov     rcx, [rbp+4Fh+var_80]
0x18004983c  lea     r8, [rbp+4Fh+var_88]
0x180049840  lea     rdx, _GUID_41571254_67a7_464b_84f8_2cd7f8556281
0x180049847  mov     rax, [rcx]
0x18004984a  mov     rax, [rax]
0x18004984d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049852  mov     ebx, eax
0x180049854  test    eax, eax
0x180049856  js      loc_180049A29
0x18004985c  mov     rcx, [rbp+4Fh+var_88]
0x180049860  lea     rdx, [rbp+4Fh+var_60]
0x180049864  mov     rax, [rcx]
0x180049867  mov     rax, [rax+20h]
0x18004986b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049870  mov     ebx, eax
0x180049872  test    eax, eax
0x180049874  js      loc_180049A16
0x18004987a  lea     rcx, [rbp+4Fh+ppMFType]; ppMFType
0x18004987e  call    cs:__imp_MFCreateMediaType
0x180049884  mov     ebx, eax
0x180049886  test    eax, eax
0x180049888  js      loc_180049A06
0x18004988e  mov     rcx, [rbp+4Fh+ppMFType]
0x180049892  lea     r8, MFMediaType_Video
0x180049899  lea     rdx, MF_MT_MAJOR_TYPE
0x1800498a0  mov     rax, [rcx]
0x1800498a3  mov     rax, [rax+0C0h]
0x1800498aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498af  mov     ebx, eax
0x1800498b1  test    eax, eax
0x1800498b3  js      loc_1800499F6
0x1800498b9  mov     eax, dword ptr [rbp+4Fh+var_60+4]
0x1800498bc  lea     rdx, MF_MT_FRAME_SIZE
0x1800498c3  mov     rcx, [rbp+4Fh+ppMFType]
0x1800498c7  mov     r8d, dword ptr [rbp+4Fh+var_60]
0x1800498cb  shl     r8, 20h
0x1800498cf  or      r8, rax
0x1800498d2  mov     r9, [rcx]
0x1800498d5  mov     rax, [r9+0B0h]
0x1800498dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498e1  mov     ebx, eax
0x1800498e3  test    eax, eax
0x1800498e5  js      loc_1800499E6
0x1800498eb  mov     rax, [rsi]
0x1800498ee  sub     rax, qword ptr cs:_GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data1
0x1800498f5  jnz     short loc_180049902
0x1800498f7  mov     rax, [rsi+8]
0x1800498fb  sub     rax, qword ptr cs:_GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data4
0x180049902  test    rax, rax
0x180049905  jz      short loc_180049935
0x180049907  mov     eax, dword ptr [rbp+4Fh+var_60+0Ch]
0x18004990a  lea     rdx, MF_MT_FRAME_RATE
0x180049911  mov     rcx, [rbp+4Fh+ppMFType]
0x180049915  mov     r8d, dword ptr [rbp+4Fh+var_60+8]
0x180049919  shl     r8, 20h
0x18004991d  or      r8, rax
0x180049920  mov     r9, [rcx]
0x180049923  mov     rax, [r9+0B0h]
0x18004992a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004992f  mov     ebx, eax
0x180049931  test    eax, eax
0x180049933  js      short loc_18004998A
0x180049935  mov     rcx, [rbp+4Fh+var_68]
0x180049939  mov     r8, [rbp+4Fh+ppMFType]
0x18004993d  mov     edx, [rbp+4Fh+var_70]
0x180049940  mov     rax, [rcx]
0x180049943  mov     rax, [rax+78h]
0x180049947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004994c  mov     ebx, eax
0x18004994e  test    eax, eax
0x180049950  js      loc_1800499D6
0x180049956  lea     rcx, [rbp+4Fh+ppMFType]
0x18004995a  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004995f  lea     rcx, [rbp+4Fh+var_88]
0x180049963  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180049968  lea     rcx, [rbp+4Fh+var_80]
0x18004996c  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180049971  inc     r14d
0x180049974  jmp     loc_1800497E4
0x180049979  lea     rcx, [rbp+4Fh+var_A0]
0x18004997d  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180049982  inc     r15d
0x180049985  jmp     loc_18004973F
0x18004998a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049991  jb      short loc_1800499B6
0x180049993  mov     edx, 15Ch
0x180049998  mov     rcx, cs:WPP_GLOBAL_Control
0x18004999f  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x1800499a6  mov     r9, rdi
0x1800499a9  mov     [rsp+0D0h+var_B0], eax
0x1800499ad  mov     rcx, [rcx+10h]
0x1800499b1  call    WPP_SF_qD
0x1800499b6  lea     rcx, [rbp+4Fh+ppMFType]
0x1800499ba  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800499bf  lea     rcx, [rbp+4Fh+var_88]
0x1800499c3  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800499c8  lea     rcx, [rbp+4Fh+var_80]
0x1800499cc  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800499d1  jmp     loc_180049A9F
0x1800499d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800499dd  jb      short loc_1800499B6
0x1800499df  mov     edx, 15Dh
0x1800499e4  jmp     short loc_180049998
0x1800499e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800499ed  jb      short loc_1800499B6
0x1800499ef  mov     edx, 15Bh
0x1800499f4  jmp     short loc_180049998
0x1800499f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800499fd  jb      short loc_1800499B6
0x1800499ff  mov     edx, 15Ah
0x180049a04  jmp     short loc_180049998
0x180049a06  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049a0d  jb      short loc_1800499B6
0x180049a0f  mov     edx, 159h
0x180049a14  jmp     short loc_180049998
0x180049a16  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049a1d  jb      short loc_1800499B6
0x180049a1f  mov     edx, 158h
0x180049a24  jmp     loc_180049998
0x180049a29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049a30  jb      short loc_1800499B6
0x180049a32  mov     edx, 157h
0x180049a37  jmp     loc_180049998
0x180049a3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049a43  jb      loc_1800499B6
0x180049a49  mov     edx, 156h
0x180049a4e  jmp     loc_180049998
0x180049a53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049a5a  jb      short loc_180049A9F
0x180049a5c  mov     edx, 155h
0x180049a61  jmp     short loc_180049A81
0x180049a63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049a6a  jb      short loc_180049A9F
0x180049a6c  mov     edx, 154h
0x180049a71  jmp     short loc_180049A81
0x180049a73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049a7a  jb      short loc_180049A9F
0x180049a7c  mov     edx, 153h
0x180049a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a88  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x180049a8f  mov     r9, rdi
0x180049a92  mov     [rsp+0D0h+var_B0], eax
0x180049a96  mov     rcx, [rcx+10h]
0x180049a9a  call    WPP_SF_qD
0x180049a9f  lea     rcx, [rbp+4Fh+var_A0]
0x180049aa3  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180049aa8  lea     rcx, [rbp+4Fh+var_68]
0x180049aac  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180049ab1  mov     eax, ebx
0x180049ab3  mov     rcx, [rbp+4Fh+var_38]
0x180049ab7  xor     rcx, rsp; StackCookie
0x180049aba  call    __security_check_cookie
0x180049abf  add     rsp, 0A0h
0x180049ac6  pop     r15
0x180049ac8  pop     r14
0x180049aca  pop     r12
0x180049acc  pop     rdi
0x180049acd  pop     rsi
0x180049ace  pop     rbx
0x180049acf  pop     rbp
0x180049ad0  retn
```

# SensorActivities::AddActivities(IMFSensorActivitiesReportInternal *)

- ea: `0x180014cc0`
- end: `0x18001513b`
- name: `?AddActivities@SensorActivities@@UEAAJPEAUIMFSensorActivitiesReportInternal@@@Z`
- size: `1147`
- prototype: `__int64 __fastcall(SensorActivities *__hidden this, struct IMFSensorActivitiesReportInternal *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180009a20`
- `0x180014cc0`
- `0x180015144`
- `0x180044f30`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014cfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014cfa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014e4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014e4e`

## pseudocode

```c
__int64 __fastcall SensorActivities::AddActivities(
        SensorActivities *this,
        struct IMFSensorActivitiesReportInternal *a2)
{
  int v4; // edi
  unsigned int v5; // r13d
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  __int64 i; // r14
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  struct IMFSensorActivityReportInternal *v15; // rcx
  int v16; // eax
  struct IMFSensorActivityReportInternal *v17; // r14
  __int64 *v18; // rcx
  __int64 v19; // rdx
  struct IMFSensorActivityReportInternal *v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  struct IMFSensorActivityReportInternal *v22; // [rsp+40h] [rbp-C0h] BYREF
  struct IMFSensorActivityReportInternal *v23; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v25[3]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR String2[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String1[264]; // [rsp+270h] [rbp+170h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = 0;
  v24 = 0;
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(struct IMFSensorActivitiesReportInternal *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           &v24);
    if ( v4 >= 0 )
    {
      v5 = 0;
LABEL_4:
      if ( v5 >= v24 )
        goto LABEL_22;
      v21 = 0;
      v20 = 0;
      memset_0(String2, 0, 0x208u);
      v6 = *(_QWORD *)a2;
      v25[0] = 0;
      v4 = (*(__int64 (__fastcall **)(struct IMFSensorActivitiesReportInternal *, _QWORD, __int64 *))(v6 + 32))(
             a2,
             v5,
             &v21);
      if ( v4 < 0 )
        goto LABEL_44;
      v7 = (*(__int64 (__fastcall **)(__int64, WCHAR *, __int64, _DWORD *))(*(_QWORD *)v21 + 32LL))(
             v21,
             String2,
             260,
             v25);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IMFSensorActivityReportInternal **))v21)(
               v21,
               &GUID_edc45026_2f8c_47b1_b22e_b0d00d8089b5,
               &v20);
        v4 = v8;
        if ( v8 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_44;
          v19 = 18;
        }
        else
        {
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= *((_DWORD *)this + 16) )
            {
              v23 = 0;
              v16 = SensorActivity::CreateClonedActivity(v20, &v23);
              v4 = v16;
              if ( v16 < 0 )
              {
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    22,
                    WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids,
                    this,
                    v16);
              }
              else
              {
                v17 = v23;
                LODWORD(v22) = *((_DWORD *)this + 16);
                if ( (unsigned int)CTEntryArray<SensorDeviceId *>::SetSize(
                                     (char *)this + 56,
                                     (unsigned int)((_DWORD)v22 + 1)) )
                {
                  *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * (unsigned int)v22) = v17;
                  if ( v17 )
                    (*(void (__fastcall **)(struct IMFSensorActivityReportInternal *))(*(_QWORD *)v17 + 8LL))(v17);
                  v15 = v23;
                  goto LABEL_25;
                }
                v4 = -2147024882;
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    23,
                    WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids,
                    this,
                    -2147024882);
              }
              v18 = (__int64 *)&v23;
LABEL_43:
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(v18);
              goto LABEL_44;
            }
            memset_0(String1, 0, 0x208u);
            v10 = *((_QWORD *)this + 7);
            v23 = (struct IMFSensorActivityReportInternal *)(unsigned int)i;
            v8 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64, _DWORD *))(**(_QWORD **)(v10 + 8 * i) + 32LL))(
                   *(_QWORD *)(v10 + 8 * i),
                   String1,
                   260,
                   v25);
            v4 = v8;
            if ( v8 < 0 )
              break;
            if ( CompareStringOrdinal(String1, -1, String2, -1, 1) == 2 )
            {
              v11 = *((_QWORD *)this + 7);
              v22 = 0;
              v12 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IMFSensorActivityReportInternal **))(v11 + 8LL * (_QWORD)v23))(
                      *(_QWORD *)(v11 + 8LL * (_QWORD)v23),
                      &GUID_edc45026_2f8c_47b1_b22e_b0d00d8089b5,
                      &v22);
              v4 = v12;
              if ( v12 < 0 )
              {
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    20,
                    WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids,
                    this,
                    v12);
                v18 = (__int64 *)&v22;
                goto LABEL_43;
              }
              v13 = (*(__int64 (__fastcall **)(struct IMFSensorActivityReportInternal *, struct IMFSensorActivityReportInternal *))(*(_QWORD *)v22 + 64LL))(
                      v22,
                      v20);
              v4 = v13;
              if ( v13 < 0 )
              {
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    21,
                    WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids,
                    this,
                    v13);
                if ( v22 )
                  (*(void (__fastcall **)(struct IMFSensorActivityReportInternal *))(*(_QWORD *)v22 + 16LL))(v22);
                goto LABEL_18;
              }
              v15 = v22;
LABEL_25:
              if ( v15 )
                (*(void (__fastcall **)(struct IMFSensorActivityReportInternal *))(*(_QWORD *)v15 + 16LL))(v15);
              if ( v20 )
                (*(void (__fastcall **)(struct IMFSensorActivityReportInternal *))(*(_QWORD *)v20 + 16LL))(v20);
              if ( v21 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              ++v5;
              goto LABEL_4;
            }
          }
          if ( !g_wppLevels )
            goto LABEL_44;
          v19 = 19;
        }
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids, this, v8);
LABEL_44:
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v20);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v21);
        goto LABEL_22;
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids, this, v7);
LABEL_18:
      if ( v20 )
        (*(void (__fastcall **)(struct IMFSensorActivityReportInternal *))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014cc0  mov     [rsp-8+arg_10], rbx
0x180014cc5  push    rbp
0x180014cc6  push    rsi
0x180014cc7  push    rdi
0x180014cc8  push    r12
0x180014cca  push    r13
0x180014ccc  push    r14
0x180014cce  push    r15
0x180014cd0  lea     rbp, [rsp-390h]
0x180014cd8  sub     rsp, 490h
0x180014cdf  mov     rax, cs:__security_cookie
0x180014ce6  xor     rax, rsp
0x180014ce9  mov     [rbp+3C0h+var_40], rax
0x180014cf0  mov     rsi, rcx
0x180014cf3  mov     r15, rdx
0x180014cf6  add     rcx, 10h; lpCriticalSection
0x180014cfa  call    cs:__imp_EnterCriticalSection
0x180014d00  xor     edi, edi
0x180014d02  mov     [rsp+4C0h+var_470], edi
0x180014d06  test    r15, r15
0x180014d09  jz      loc_180014F03
0x180014d0f  mov     rax, [r15]
0x180014d12  lea     rdx, [rsp+4C0h+var_470]
0x180014d17  mov     rcx, r15
0x180014d1a  mov     rax, [rax+18h]
0x180014d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d23  mov     edi, eax
0x180014d25  test    eax, eax
0x180014d27  js      loc_180014F03
0x180014d2d  xor     r13d, r13d
0x180014d30  cmp     r13d, [rsp+4C0h+var_470]
0x180014d35  jnb     loc_180014F03
0x180014d3b  xor     edx, edx; Val
0x180014d3d  mov     [rsp+4C0h+var_488], 0
0x180014d46  mov     r8d, 208h; Size
0x180014d4c  mov     [rsp+4C0h+var_490], 0
0x180014d55  lea     rcx, [rsp+4C0h+String2]; void *
0x180014d5a  call    memset_0
0x180014d5f  mov     rax, [r15]
0x180014d62  lea     r8, [rsp+4C0h+var_488]
0x180014d67  mov     edx, r13d
0x180014d6a  mov     [rsp+4C0h+var_46C], 0
0x180014d72  mov     rcx, r15
0x180014d75  mov     rax, [rax+20h]
0x180014d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d7e  mov     edi, eax
0x180014d80  test    eax, eax
0x180014d82  js      loc_1800150B4
0x180014d88  mov     rcx, [rsp+4C0h+var_488]
0x180014d8d  lea     r9, [rsp+4C0h+var_46C]
0x180014d92  mov     r8d, 104h
0x180014d98  lea     rdx, [rsp+4C0h+String2]
0x180014d9d  mov     rax, [rcx]
0x180014da0  mov     rax, [rax+20h]
0x180014da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014da9  mov     edi, eax
0x180014dab  test    eax, eax
0x180014dad  js      loc_180014F8B
0x180014db3  mov     rcx, [rsp+4C0h+var_488]
0x180014db8  lea     r8, [rsp+4C0h+var_490]
0x180014dbd  lea     rdx, _GUID_edc45026_2f8c_47b1_b22e_b0d00d8089b5
0x180014dc4  mov     rax, [rcx]
0x180014dc7  mov     rax, [rax]
0x180014dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dcf  mov     edi, eax
0x180014dd1  test    eax, eax
0x180014dd3  js      loc_18001512C
0x180014dd9  xor     r14d, r14d
0x180014ddc  cmp     r14d, [rsi+40h]
0x180014de0  jnb     loc_180014FC0
0x180014de6  xor     edx, edx; Val
0x180014de8  lea     rcx, [rbp+3C0h+String1]; void *
0x180014def  mov     r8d, 208h; Size
0x180014df5  call    memset_0
0x180014dfa  mov     rax, [rsi+38h]
0x180014dfe  lea     r9, [rsp+4C0h+var_46C]
0x180014e03  mov     ecx, r14d
0x180014e06  lea     rdx, [rbp+3C0h+String1]
0x180014e0d  mov     [rsp+4C0h+var_478], rcx
0x180014e12  mov     r8d, 104h
0x180014e18  mov     rcx, [rax+r14*8]
0x180014e1c  mov     rax, [rcx]
0x180014e1f  mov     rax, [rax+20h]
0x180014e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e28  mov     edi, eax
0x180014e2a  test    eax, eax
0x180014e2c  js      loc_1800150CD
0x180014e32  or      eax, 0FFFFFFFFh
0x180014e35  mov     [rsp+4C0h+bIgnoreCase], 1; bIgnoreCase
0x180014e3d  mov     r9d, eax; cchCount2
0x180014e40  lea     r8, [rsp+4C0h+String2]; lpString2
0x180014e45  mov     edx, eax; cchCount1
0x180014e47  lea     rcx, [rbp+3C0h+String1]; lpString1
0x180014e4e  call    cs:__imp_CompareStringOrdinal
0x180014e54  cmp     eax, 2
0x180014e57  jnz     loc_180014F39
0x180014e5d  mov     rax, [rsi+38h]
0x180014e61  lea     r8, [rsp+4C0h+var_480]
0x180014e66  mov     rcx, [rsp+4C0h+var_478]
0x180014e6b  lea     rdx, _GUID_edc45026_2f8c_47b1_b22e_b0d00d8089b5
0x180014e72  mov     [rsp+4C0h+var_480], 0
0x180014e7b  mov     rcx, [rax+rcx*8]
0x180014e7f  mov     rax, [rcx]
0x180014e82  mov     rax, [rax]
0x180014e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e8a  mov     edi, eax
0x180014e8c  test    eax, eax
0x180014e8e  js      loc_180015054
0x180014e94  mov     rcx, [rsp+4C0h+var_480]
0x180014e99  mov     rdx, [rsp+4C0h+var_490]
0x180014e9e  mov     rax, [rcx]
0x180014ea1  mov     rax, [rax+40h]
0x180014ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eaa  mov     edi, eax
0x180014eac  test    eax, eax
0x180014eae  jns     loc_180014F41
0x180014eb4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014ebb  jnb     loc_18001502C
0x180014ec1  mov     rcx, [rsp+4C0h+var_480]
0x180014ec6  test    rcx, rcx
0x180014ec9  jz      short loc_180014ED7
0x180014ecb  mov     rax, [rcx]
0x180014ece  mov     rax, [rax+10h]
0x180014ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ed7  mov     rcx, [rsp+4C0h+var_490]
0x180014edc  test    rcx, rcx
0x180014edf  jz      short loc_180014EED
0x180014ee1  mov     rax, [rcx]
0x180014ee4  mov     rax, [rax+10h]
0x180014ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eed  mov     rcx, [rsp+4C0h+var_488]
0x180014ef2  test    rcx, rcx
0x180014ef5  jz      short loc_180014F03
0x180014ef7  mov     rax, [rcx]
0x180014efa  mov     rax, [rax+10h]
0x180014efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f03  lea     rcx, [rsi+10h]; lpCriticalSection
0x180014f07  call    cs:__imp_LeaveCriticalSection
0x180014f0d  mov     eax, edi
0x180014f0f  mov     rcx, [rbp+3C0h+var_40]
0x180014f16  xor     rcx, rsp; StackCookie
0x180014f19  call    __security_check_cookie
0x180014f1e  mov     rbx, [rsp+4C0h+arg_10]
0x180014f26  add     rsp, 490h
0x180014f2d  pop     r15
0x180014f2f  pop     r14
0x180014f31  pop     r13
0x180014f33  pop     r12
0x180014f35  pop     rdi
0x180014f36  pop     rsi
0x180014f37  pop     rbp
0x180014f38  retn
0x180014f39  inc     r14d
0x180014f3c  jmp     loc_180014DDC
0x180014f41  mov     rcx, [rsp+4C0h+var_480]
0x180014f46  test    rcx, rcx
0x180014f49  jz      short loc_180014F57
0x180014f4b  mov     rax, [rcx]
0x180014f4e  mov     rax, [rax+10h]
0x180014f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f57  mov     rcx, [rsp+4C0h+var_490]
0x180014f5c  test    rcx, rcx
0x180014f5f  jz      short loc_180014F6D
0x180014f61  mov     rax, [rcx]
0x180014f64  mov     rax, [rax+10h]
0x180014f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f6d  mov     rcx, [rsp+4C0h+var_488]
0x180014f72  test    rcx, rcx
0x180014f75  jz      short loc_180014F83
0x180014f77  mov     rax, [rcx]
0x180014f7a  mov     rax, [rax+10h]
0x180014f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f83  inc     r13d
0x180014f86  jmp     loc_180014D30
0x180014f8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014f92  jb      loc_180014ED7
0x180014f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f9f  lea     r8, WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids
0x180014fa6  mov     edx, 11h
0x180014fab  mov     [rsp+4C0h+bIgnoreCase], eax
0x180014faf  mov     r9, rsi
0x180014fb2  mov     rcx, [rcx+10h]
0x180014fb6  call    WPP_SF_qD
0x180014fbb  jmp     loc_180014ED7
0x180014fc0  mov     rcx, [rsp+4C0h+var_490]; struct IMFSensorActivityReportInternal *
0x180014fc5  lea     rdx, [rsp+4C0h+var_478]; struct IMFSensorActivityReportInternal **
0x180014fca  mov     [rsp+4C0h+var_478], 0
0x180014fd3  call    ?CreateClonedActivity@SensorActivity@@SAJPEAUIMFSensorActivityReportInternal@@PEAPEAU2@@Z; SensorActivity::CreateClonedActivity(IMFSensorActivityReportInternal *,IMFSensorActivityReportInternal * *)
0x180014fd8  mov     edi, eax
0x180014fda  test    eax, eax
0x180014fdc  js      loc_180015115
0x180014fe2  mov     eax, [rsi+40h]
0x180014fe5  lea     rcx, [rsi+38h]
0x180014fe9  mov     r14, [rsp+4C0h+var_478]
0x180014fee  mov     dword ptr [rsp+4C0h+var_480], eax
0x180014ff2  lea     edx, [rax+1]
0x180014ff5  call    ?SetSize@?$CTEntryArray@PEAVSensorDeviceId@@@@QEAAHKK@Z; CTEntryArray<SensorDeviceId *>::SetSize(ulong,ulong)
0x180014ffa  test    eax, eax
0x180014ffc  jz      loc_180015102
0x180015002  mov     ecx, dword ptr [rsp+4C0h+var_480]
0x180015006  mov     rax, [rsi+38h]
0x18001500a  mov     [rax+rcx*8], r14
0x18001500e  test    r14, r14
0x180015011  jz      short loc_180015022
0x180015013  mov     rax, [r14]
0x180015016  mov     rcx, r14
0x180015019  mov     rax, [rax+8]
0x18001501d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015022  mov     rcx, [rsp+4C0h+var_478]
0x180015027  jmp     loc_180014F46
0x18001502c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015033  lea     r8, WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids
0x18001503a  mov     edx, 15h
0x18001503f  mov     [rsp+4C0h+bIgnoreCase], eax
0x180015043  mov     r9, rsi
0x180015046  mov     rcx, [rcx+10h]
0x18001504a  call    WPP_SF_qD
0x18001504f  jmp     loc_180014EC1
0x180015054  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001505b  jb      short loc_180015080
0x18001505d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015064  lea     r8, WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids
0x18001506b  mov     edx, 14h
0x180015070  mov     [rsp+4C0h+bIgnoreCase], eax
0x180015074  mov     r9, rsi
0x180015077  mov     rcx, [rcx+10h]
0x18001507b  call    WPP_SF_qD
0x180015080  lea     rcx, [rsp+4C0h+var_480]
0x180015085  jmp     short loc_1800150AF
0x180015087  mov     edx, 17h
0x18001508c  mov     [rsp+4C0h+bIgnoreCase], edi
0x180015090  mov     rcx, cs:WPP_GLOBAL_Control
0x180015097  lea     r8, WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids
0x18001509e  mov     r9, rsi
0x1800150a1  mov     rcx, [rcx+10h]
0x1800150a5  call    WPP_SF_qD
0x1800150aa  lea     rcx, [rsp+4C0h+var_478]
0x1800150af  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800150b4  lea     rcx, [rsp+4C0h+var_490]
0x1800150b9  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800150be  lea     rcx, [rsp+4C0h+var_488]
0x1800150c3  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800150c8  jmp     loc_180014F03
0x1800150cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800150d4  jb      short loc_1800150B4
0x1800150d6  mov     edx, 13h
0x1800150db  jmp     short loc_1800150E2
0x1800150dd  mov     edx, 12h
0x1800150e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150e9  lea     r8, WPP_2efda9130c02331b798ed57ee7e01b68_Traceguids
0x1800150f0  mov     r9, rsi
0x1800150f3  mov     [rsp+4C0h+bIgnoreCase], eax
0x1800150f7  mov     rcx, [rcx+10h]
0x1800150fb  call    WPP_SF_qD
0x180015100  jmp     short loc_1800150B4
0x180015102  mov     edi, 8007000Eh
0x180015107  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001510e  jb      short loc_1800150AA
0x180015110  jmp     loc_180015087
0x180015115  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001511c  jb      short loc_1800150AA
0x18001511e  mov     edx, 16h
0x180015123  mov     [rsp+4C0h+bIgnoreCase], eax
0x180015127  jmp     loc_180015090
0x18001512c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015133  jb      loc_1800150B4
0x180015139  jmp     short loc_1800150DD
```

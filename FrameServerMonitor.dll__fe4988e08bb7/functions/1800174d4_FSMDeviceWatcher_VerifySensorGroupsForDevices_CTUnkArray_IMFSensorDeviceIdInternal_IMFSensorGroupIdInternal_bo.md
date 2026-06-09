# FSMDeviceWatcher::VerifySensorGroupsForDevices(CTUnkArray<IMFSensorDeviceIdInternal> &,IMFSensorGroupIdInternal *,bool *)

- ea: `0x1800174d4`
- end: `0x180017985`
- name: `?VerifySensorGroupsForDevices@FSMDeviceWatcher@@IEAAJAEAV?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@PEAUIMFSensorGroupIdInternal@@PEA_N@Z`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016d0c`

## callees

- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006b84`
- `0x180006f3c`
- `0x180007348`
- `0x18000d4f8`
- `0x18000d594`
- `0x18000d62c`
- `0x18001440c`
- `0x1800174d4`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroup` at `0x1800176af`
- `MFSENSORGROUP!MFCreateSensorGroup` at `0x1800176af`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::VerifySensorGroupsForDevices(__int64 a1, __int64 a2, __int64 *a3, _BYTE *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // r13d
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int i; // r15d
  __int64 v13; // rax
  int (__fastcall *v14)(__int64 *, _QWORD, __int64 *); // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  int (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // r12
  int (__fastcall **v19)(_QWORD, _QWORD); // rax
  int (__fastcall *v20)(_QWORD, _QWORD); // rax
  __int64 v21; // rcx
  _QWORD *v22; // r12
  __int64 v23; // rax
  int (__fastcall *v24)(_QWORD, _QWORD); // rax
  unsigned __int8 Level; // al
  int v26; // ecx
  __int64 j; // rsi
  unsigned __int8 v28; // al
  char v29; // cl
  __int64 v30; // rax
  __int64 v31; // rax
  const char *v32; // rax
  __int64 v34; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-38h] BYREF
  int (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // [rsp+40h] [rbp-30h] BYREF
  __int64 v37; // [rsp+48h] [rbp-28h] BYREF
  int (__fastcall *v38)(_QWORD, _QWORD); // [rsp+50h] [rbp-20h]
  __int64 v39; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-10h]
  __int64 v41; // [rsp+64h] [rbp-Ch]
  unsigned int v43; // [rsp+C0h] [rbp+50h] BYREF

  v43 = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v8 = 151;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v7 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 152;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, a1, v7);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  v9 = *(_DWORD *)(a2 + 8);
  *a4 = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 153, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, a1);
  if ( !v9 )
  {
    v7 = 0;
    *a4 = 1;
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 8u )
      goto LABEL_53;
    v10 = 154;
    goto LABEL_13;
  }
  v7 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a3 + 80))(a3, &v43);
  if ( v7 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 155;
      goto LABEL_4;
    }
LABEL_37:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 162, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, a1, v7);
    goto LABEL_57;
  }
  v11 = v43;
  if ( v43 )
  {
    for ( i = 0; i < v11; ++i )
    {
      v13 = *a3;
      v36 = 0;
      v35 = 0;
      v34 = 0;
      v14 = *(int (__fastcall **)(__int64 *, _QWORD, __int64 *))(v13 + 88);
      v37 = 0;
      if ( v14(a3, i, &v37) >= 0 )
      {
        v15 = (__int64)v36;
        v36 = 0;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 24LL))(v37);
        if ( (int)MFCreateSensorGroup(v16, &v36) >= 0 )
        {
          v17 = (__int64)v35;
          v18 = v36;
          v19 = (int (__fastcall **)(_QWORD, _QWORD))*v36;
          v35 = 0;
          v20 = *v19;
          v38 = v20;
          if ( v17 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v20 = v38;
          }
          if ( ((int (__fastcall *)(_QWORD, GUID *, _QWORD **))v20)(
                 v18,
                 &GUID_8e3196f0_ce22_4599_a16a_886bb13a7966,
                 &v35) >= 0 )
          {
            v21 = v34;
            v22 = v35;
            v23 = *v35;
            v34 = 0;
            v24 = *(int (__fastcall **)(_QWORD, _QWORD))(v23 + 56);
            v38 = v24;
            if ( v21 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              v24 = v38;
            }
            if ( v24(v22, &v34) >= 0 && !(unsigned int)CTUnkArray<IFSCameraControlState>::Add(&v39, v34) )
            {
              v7 = -2147024882;
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  157,
                  &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                  a1,
                  -2147024882);
              wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v34);
              wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v37);
              wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v35);
              wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v36);
              goto LABEL_37;
            }
          }
        }
      }
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v34);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v37);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v35);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v36);
      v11 = v43;
    }
    v43 = v40;
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
    if ( v26 )
    {
      if ( Level >= 8u )
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          159,
          &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          a1,
          v9,
          v26);
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= v9 )
        {
          *a4 = 1;
          goto LABEL_53;
        }
        FSMDeviceWatcher::IsSensorDeviceInCollection(*(_QWORD *)(*(_QWORD *)a2 + 8 * j), &v39);
        v28 = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
        if ( !v29 )
          break;
        if ( v28 >= 8u )
        {
          v30 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 8 * j) + 24LL))(*(_QWORD *)(*(_QWORD *)a2 + 8 * j));
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            161,
            (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            a1,
            v30);
        }
      }
      if ( v28 >= 8u )
      {
        _mm_lfence();
        v31 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 8 * j) + 24LL))(*(_QWORD *)(*(_QWORD *)a2 + 8 * j));
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          160,
          (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          a1,
          v31);
      }
      goto LABEL_53;
    }
    if ( Level < 8u )
      goto LABEL_53;
    v10 = 158;
    goto LABEL_13;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v10 = 156;
LABEL_13:
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, a1);
  }
LABEL_53:
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v32 = "true";
    if ( !*a4 )
      v32 = "false";
    WPP_SF_qDs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      163,
      (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
      a1,
      v7,
      (__int64)v32);
  }
LABEL_57:
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(&v39);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800174d4  mov     [rsp-38h+arg_0], rbx
0x1800174d9  mov     [rsp-38h+arg_8], rdx
0x1800174de  push    rbp
0x1800174df  push    rsi
0x1800174e0  push    rdi
0x1800174e1  push    r12
0x1800174e3  push    r13
0x1800174e5  push    r14
0x1800174e7  push    r15
0x1800174e9  mov     rbp, rsp
0x1800174ec  sub     rsp, 70h
0x1800174f0  mov     [rbp+arg_10], 0
0x1800174f7  mov     r14, r9
0x1800174fa  mov     [rbp+var_18], 0
0x180017502  mov     rsi, r8
0x180017505  mov     [rbp+var_C], 0
0x18001750d  mov     rdi, rcx
0x180017510  mov     [rbp+var_10], 0
0x180017517  test    r8, r8
0x18001751a  jnz     short loc_180017556
0x18001751c  mov     ebx, 80070057h
0x180017521  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180017526  cmp     al, 1
0x180017528  jb      loc_1800177DA
0x18001752e  mov     edx, 97h
0x180017533  mov     rcx, cs:WPP_GLOBAL_Control
0x18001753a  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180017541  mov     r9, rdi
0x180017544  mov     dword ptr [rsp+70h+var_50], ebx
0x180017548  mov     rcx, [rcx+10h]
0x18001754c  call    WPP_SF_qD
0x180017551  jmp     loc_1800177DA
0x180017556  test    r14, r14
0x180017559  jnz     short loc_180017574
0x18001755b  mov     ebx, 80004003h
0x180017560  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180017565  cmp     al, 1
0x180017567  jb      loc_1800177DA
0x18001756d  mov     edx, 98h
0x180017572  jmp     short loc_180017533
0x180017574  mov     r13d, [rdx+8]
0x180017578  mov     byte ptr [r9], 0
0x18001757c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180017581  cmp     al, 8
0x180017583  jb      short loc_1800175A7
0x180017585  mov     rcx, cs:WPP_GLOBAL_Control
0x18001758c  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180017593  mov     edx, 99h
0x180017598  mov     r9, rdi
0x18001759b  mov     rcx, [rcx+0D8h]
0x1800175a2  call    WPP_SF_q
0x1800175a7  test    r13d, r13d
0x1800175aa  jnz     short loc_1800175E6
0x1800175ac  xor     ebx, ebx
0x1800175ae  mov     byte ptr [r14], 1
0x1800175b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800175b7  cmp     al, 8
0x1800175b9  jb      loc_180017918
0x1800175bf  mov     edx, 9Ah
0x1800175c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175cb  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800175d2  mov     r9, rdi
0x1800175d5  mov     rcx, [rcx+0D8h]
0x1800175dc  call    WPP_SF_q
0x1800175e1  jmp     loc_180017918
0x1800175e6  mov     rax, [rsi]
0x1800175e9  lea     rdx, [rbp+arg_10]
0x1800175ed  mov     rcx, rsi
0x1800175f0  mov     rax, [rax+50h]
0x1800175f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175f9  mov     ebx, eax
0x1800175fb  test    eax, eax
0x1800175fd  jns     short loc_180017616
0x1800175ff  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180017604  cmp     al, 1
0x180017606  jb      loc_1800177DA
0x18001760c  mov     edx, 9Bh
0x180017611  jmp     loc_180017533
0x180017616  mov     eax, [rbp+arg_10]
0x180017619  test    eax, eax
0x18001761b  jnz     short loc_180017631
0x18001761d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180017622  cmp     al, 8
0x180017624  jb      loc_180017918
0x18001762a  mov     edx, 9Ch
0x18001762f  jmp     short loc_1800175C4
0x180017631  xor     r15d, r15d
0x180017634  cmp     r15d, eax
0x180017637  jnb     loc_180017812
0x18001763d  mov     rax, [rsi]
0x180017640  lea     r8, [rbp+var_28]
0x180017644  mov     edx, r15d
0x180017647  mov     [rbp+var_30], 0
0x18001764f  mov     rcx, rsi
0x180017652  mov     [rbp+var_38], 0
0x18001765a  mov     [rbp+var_40], 0
0x180017662  mov     rax, [rax+58h]
0x180017666  mov     [rbp+var_28], 0
0x18001766e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017673  test    eax, eax
0x180017675  js      loc_180017756
0x18001767b  mov     rcx, [rbp+var_30]
0x18001767f  mov     [rbp+var_30], 0
0x180017687  test    rcx, rcx
0x18001768a  jz      short loc_180017698
0x18001768c  mov     rax, [rcx]
0x18001768f  mov     rax, [rax+10h]
0x180017693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017698  mov     rcx, [rbp+var_28]
0x18001769c  mov     rax, [rcx]
0x18001769f  mov     rax, [rax+18h]
0x1800176a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176a8  lea     rdx, [rbp+var_30]
0x1800176ac  mov     rcx, rax
0x1800176af  call    cs:__imp_MFCreateSensorGroup
0x1800176b5  test    eax, eax
0x1800176b7  js      loc_180017756
0x1800176bd  mov     rcx, [rbp+var_38]
0x1800176c1  mov     r12, [rbp+var_30]
0x1800176c5  mov     rax, [r12]
0x1800176c9  mov     [rbp+var_38], 0
0x1800176d1  mov     rax, [rax]
0x1800176d4  mov     [rbp+var_20], rax
0x1800176d8  test    rcx, rcx
0x1800176db  jz      short loc_1800176ED
0x1800176dd  mov     rdx, [rcx]
0x1800176e0  mov     rax, [rdx+10h]
0x1800176e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176e9  mov     rax, [rbp+var_20]
0x1800176ed  lea     r8, [rbp+var_38]
0x1800176f1  mov     rcx, r12
0x1800176f4  lea     rdx, _GUID_8e3196f0_ce22_4599_a16a_886bb13a7966
0x1800176fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017700  test    eax, eax
0x180017702  js      short loc_180017756
0x180017704  mov     rcx, [rbp+var_40]
0x180017708  mov     r12, [rbp+var_38]
0x18001770c  mov     rax, [r12]
0x180017710  mov     [rbp+var_40], 0
0x180017718  mov     rax, [rax+38h]
0x18001771c  mov     [rbp+var_20], rax
0x180017720  test    rcx, rcx
0x180017723  jz      short loc_180017735
0x180017725  mov     rdx, [rcx]
0x180017728  mov     rax, [rdx+10h]
0x18001772c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017731  mov     rax, [rbp+var_20]
0x180017735  lea     rdx, [rbp+var_40]
0x180017739  mov     rcx, r12
0x18001773c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017741  test    eax, eax
0x180017743  js      short loc_180017756
0x180017745  mov     rdx, [rbp+var_40]
0x180017749  lea     rcx, [rbp+var_18]
0x18001774d  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x180017752  test    eax, eax
0x180017754  jz      short loc_180017785
0x180017756  lea     rcx, [rbp+var_40]
0x18001775a  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001775f  lea     rcx, [rbp+var_28]
0x180017763  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180017768  lea     rcx, [rbp+var_38]
0x18001776c  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180017771  lea     rcx, [rbp+var_30]
0x180017775  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001777a  mov     eax, [rbp+arg_10]
0x18001777d  inc     r15d
0x180017780  jmp     loc_180017634
0x180017785  mov     ebx, 8007000Eh
0x18001778a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001778f  cmp     al, 1
0x180017791  jb      short loc_1800177B6
0x180017793  mov     rcx, cs:WPP_GLOBAL_Control
0x18001779a  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800177a1  mov     edx, 9Dh
0x1800177a6  mov     dword ptr [rsp+70h+var_50], ebx
0x1800177aa  mov     r9, rdi
0x1800177ad  mov     rcx, [rcx+10h]
0x1800177b1  call    WPP_SF_qD
0x1800177b6  lea     rcx, [rbp+var_40]
0x1800177ba  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800177bf  lea     rcx, [rbp+var_28]
0x1800177c3  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800177c8  lea     rcx, [rbp+var_38]
0x1800177cc  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800177d1  lea     rcx, [rbp+var_30]
0x1800177d5  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800177da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800177df  cmp     al, 1
0x1800177e1  jb      loc_180017962
0x1800177e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177ee  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800177f5  mov     edx, 0A2h
0x1800177fa  mov     dword ptr [rsp+70h+var_50], ebx
0x1800177fe  mov     r9, rdi
0x180017801  mov     rcx, [rcx+0D8h]
0x180017808  call    WPP_SF_qD
0x18001780d  jmp     loc_180017962
0x180017812  mov     ecx, [rbp+var_10]
0x180017815  mov     [rbp+arg_10], ecx
0x180017818  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001781d  test    ecx, ecx
0x18001781f  jnz     short loc_180017833
0x180017821  cmp     al, 8
0x180017823  jb      loc_180017918
0x180017829  mov     edx, 9Eh
0x18001782e  jmp     loc_1800175C4
0x180017833  cmp     al, 8
0x180017835  jb      short loc_180017862
0x180017837  mov     dword ptr [rsp+70h+var_48], ecx
0x18001783b  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180017842  mov     rcx, cs:WPP_GLOBAL_Control
0x180017849  mov     edx, 9Fh
0x18001784e  mov     r9, rdi
0x180017851  mov     dword ptr [rsp+70h+var_50], r13d
0x180017856  mov     rcx, [rcx+0D8h]
0x18001785d  call    WPP_SF_qDD
0x180017862  mov     r12, [rbp+arg_8]
0x180017866  xor     esi, esi
0x180017868  cmp     esi, r13d
0x18001786b  jnb     loc_180017914
0x180017871  mov     rcx, [r12]
0x180017875  lea     rdx, [rbp+var_18]
0x180017879  mov     rcx, [rcx+rsi*8]
0x18001787d  call    ?IsSensorDeviceInCollection@FSMDeviceWatcher@@SA_NPEAUIMFSensorDeviceIdInternal@@AEAV?$CTUnkArray@UIMFSensorGroupId@@@@@Z; FSMDeviceWatcher::IsSensorDeviceInCollection(IMFSensorDeviceIdInternal *,CTUnkArray<IMFSensorGroupId> &)
0x180017882  mov     cl, al
0x180017884  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180017889  test    cl, cl
0x18001788b  jz      short loc_1800178D0
0x18001788d  cmp     al, 8
0x18001788f  jb      short loc_1800178CC
0x180017891  mov     rax, [r12]
0x180017895  mov     rcx, [rax+rsi*8]
0x180017899  mov     rax, [rcx]
0x18001789c  mov     rax, [rax+18h]
0x1800178a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178ac  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800178b3  mov     edx, 0A1h
0x1800178b8  mov     [rsp+70h+var_50], rax
0x1800178bd  mov     r9, rdi
0x1800178c0  mov     rcx, [rcx+0D8h]
0x1800178c7  call    WPP_SF_qS
0x1800178cc  inc     esi
0x1800178ce  jmp     short loc_180017868
0x1800178d0  cmp     al, 8
0x1800178d2  jb      short loc_180017918
0x1800178d4  lfence
0x1800178d7  mov     rax, [r12]
0x1800178db  mov     rcx, [rax+rsi*8]
0x1800178df  mov     rax, [rcx]
0x1800178e2  mov     rax, [rax+18h]
0x1800178e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178f2  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800178f9  mov     edx, 0A0h
0x1800178fe  mov     [rsp+70h+var_50], rax
0x180017903  mov     r9, rdi
0x180017906  mov     rcx, [rcx+0D8h]
0x18001790d  call    WPP_SF_qS
0x180017912  jmp     short loc_180017918
0x180017914  mov     byte ptr [r14], 1
0x180017918  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001791d  cmp     al, 8
0x18001791f  jb      short loc_180017962
0x180017921  cmp     byte ptr [r14], 0
0x180017925  lea     rcx, aFalse; "false"
0x18001792c  lea     rax, aTrue_0; "true"
0x180017933  mov     edx, 0A3h
0x180017938  cmovz   rax, rcx
0x18001793c  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180017943  mov     rcx, cs:WPP_GLOBAL_Control
0x18001794a  mov     r9, rdi
0x18001794d  mov     [rsp+70h+var_48], rax
0x180017952  mov     dword ptr [rsp+70h+var_50], ebx
0x180017956  mov     rcx, [rcx+0D8h]
0x18001795d  call    WPP_SF_qDs
0x180017962  lea     rcx, [rbp+var_18]
0x180017966  call    ??1?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAA@XZ; CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(void)
0x18001796b  mov     eax, ebx
0x18001796d  mov     rbx, [rsp+70h+arg_0]
0x180017975  add     rsp, 70h
0x180017979  pop     r15
0x18001797b  pop     r14
0x18001797d  pop     r13
0x18001797f  pop     r12
0x180017981  pop     rdi
0x180017982  pop     rsi
0x180017983  pop     rbp
0x180017984  retn
```

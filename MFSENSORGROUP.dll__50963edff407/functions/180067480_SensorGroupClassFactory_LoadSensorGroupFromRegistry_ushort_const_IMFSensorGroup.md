# SensorGroupClassFactory::LoadSensorGroupFromRegistry(ushort const *,IMFSensorGroup * *)

- ea: `0x180067480`
- end: `0x180067731`
- name: `?LoadSensorGroupFromRegistry@SensorGroupClassFactory@@UEAAJPEBGPEAPEAUIMFSensorGroup@@@Z`
- size: `689`
- prototype: `int(SensorGroupClassFactory *__hidden this, const unsigned __int16 *, struct IMFSensorGroup **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000c348`
- `0x18000d1f0`
- `0x18000fde4`
- `0x1800114c0`
- `0x18002c008`
- `0x18002d02c`
- `0x180067480`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800675a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800675c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800675a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800675c1`

## pseudocode

```c
__int64 __fastcall SensorGroupClassFactory::LoadSensorGroupFromRegistry(
        SensorGroupClassFactory *this,
        const unsigned __int16 *a2,
        struct IMFSensorGroup **a3)
{
  const char *v6; // r9
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rbx
  const unsigned __int16 *v12; // r15
  struct IMFSensorGroupId *v13; // rdi
  __int64 (__fastcall *v14)(struct IMFSensorGroupId *, GUID *, __int64 *); // rbx
  __int64 v15; // rdx
  unsigned __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  struct IMFSensorGroup *v18; // [rsp+88h] [rbp+48h] BYREF
  struct IMFSensorGroupId *v19; // [rsp+90h] [rbp+50h] BYREF
  __int64 v20; // [rsp+98h] [rbp+58h] BYREF

  v19 = 0;
  v20 = 0;
  v18 = 0;
  v17 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v6 = (const char *)a2;
    if ( !a2 )
      v6 = L"<nullptr>";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 138, &WPP_09150840c5f230171d137cf28cc6c946_Traceguids, v6);
  }
  if ( !a3 )
  {
    v7 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_35;
    v8 = 139;
    goto LABEL_34;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    v7 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_35;
    v10 = 140;
    goto LABEL_11;
  }
  v9 = StringCchLengthW(a2, 0x7FFFFFFFu, &v17);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_35;
    v10 = 141;
    goto LABEL_11;
  }
  if ( v17 <= 0x13 )
  {
    v9 = -2147024809;
    v7 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_35;
    v10 = 142;
    goto LABEL_11;
  }
  v11 = a2 + 19;
  if ( (unsigned int)_o__wcsnicmp(a2, L"HKEY_LOCAL_MACHINE\\", 19) )
    v11 = a2;
  v12 = v11 + 5;
  if ( (unsigned int)_o__wcsnicmp(a2, L"HKLM\\", 5) )
    v12 = v11;
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset((__int64 *)&v19);
  v9 = SensorGroupId::CreateSensorGroupId(&v19);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_35;
    v10 = 143;
    goto LABEL_11;
  }
  v13 = v19;
  v14 = **(__int64 (__fastcall ***)(struct IMFSensorGroupId *, GUID *, __int64 *))v19;
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v20);
  v9 = v14(v13, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v20);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_35;
    v10 = 144;
    goto LABEL_11;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v20 + 208LL))(v20, 1, v12);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_35;
    v10 = 145;
LABEL_11:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
      (char *)this - 8,
      v9);
    goto LABEL_35;
  }
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset((__int64 *)&v18);
  v7 = SensorGroup::LoadSensorGroup(v19, &v18);
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_35;
    v8 = 146;
LABEL_34:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
      (char *)this - 8,
      v7);
LABEL_35:
    if ( byte_18008D62D )
    {
      v15 = 147;
LABEL_39:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v15,
        &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
        (unsigned int)v7);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  *a3 = v18;
  v18 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v15 = 148;
    goto LABEL_39;
  }
LABEL_40:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v18);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v20);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180067480  push    rbp
0x180067482  push    rbx
0x180067483  push    rsi
0x180067484  push    rdi
0x180067485  push    r13
0x180067487  push    r14
0x180067489  push    r15
0x18006748b  mov     rbp, rsp
0x18006748e  sub     rsp, 40h
0x180067492  mov     r14, r8
0x180067495  mov     [rbp+arg_10], 0
0x18006749d  mov     rdi, rdx
0x1800674a0  mov     [rbp+arg_18], 0
0x1800674a8  mov     rsi, rcx
0x1800674ab  mov     [rbp+arg_8], 0
0x1800674b3  mov     [rbp+var_10], 0
0x1800674bb  cmp     cs:byte_18008D62D, 8
0x1800674c2  lea     r13, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x1800674c9  jb      short loc_1800674F7
0x1800674cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800674d2  lea     rax, aNullptr; "<nullptr>"
0x1800674d9  test    rdx, rdx
0x1800674dc  mov     r9, rdx
0x1800674df  mov     edx, 8Ah
0x1800674e4  mov     r8, r13
0x1800674e7  cmovz   r9, rax
0x1800674eb  mov     rcx, [rcx+0D8h]
0x1800674f2  call    WPP_SF_S
0x1800674f7  test    r14, r14
0x1800674fa  jnz     short loc_180067518
0x1800674fc  mov     ebx, 80004003h
0x180067501  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067508  jb      loc_1800676BF
0x18006750e  mov     edx, 8Bh
0x180067513  jmp     loc_1800676A4
0x180067518  mov     qword ptr [r14], 0
0x18006751f  test    rdi, rdi
0x180067522  jnz     short loc_180067546
0x180067524  mov     eax, 80070057h
0x180067529  mov     ebx, eax
0x18006752b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067532  jb      loc_1800676BF
0x180067538  mov     edx, 8Ch
0x18006753d  mov     [rsp+40h+var_20], eax
0x180067541  jmp     loc_1800676A8
0x180067546  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18006754a  mov     edx, 7FFFFFFFh; unsigned __int64
0x18006754f  mov     rcx, rdi; unsigned __int16 *
0x180067552  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180067557  mov     ebx, eax
0x180067559  test    eax, eax
0x18006755b  jns     short loc_180067571
0x18006755d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067564  jb      loc_1800676BF
0x18006756a  mov     edx, 8Dh
0x18006756f  jmp     short loc_18006753D
0x180067571  mov     r8d, 13h
0x180067577  cmp     [rbp+var_10], r8
0x18006757b  ja      short loc_180067597
0x18006757d  mov     eax, 80070057h
0x180067582  mov     ebx, eax
0x180067584  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006758b  jb      loc_1800676BF
0x180067591  lea     edx, [r8+7Bh]
0x180067595  jmp     short loc_18006753D
0x180067597  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x18006759e  mov     rcx, rdi
0x1800675a1  call    cs:__imp__o__wcsnicmp
0x1800675a7  lea     rbx, [rdi+26h]
0x1800675ab  mov     r8d, 5
0x1800675b1  test    eax, eax
0x1800675b3  lea     rdx, aHklm; "HKLM\\"
0x1800675ba  mov     rcx, rdi
0x1800675bd  cmovnz  rbx, rdi
0x1800675c1  call    cs:__imp__o__wcsnicmp
0x1800675c7  test    eax, eax
0x1800675c9  lea     r15, [rbx+0Ah]
0x1800675cd  lea     rcx, [rbp+arg_10]
0x1800675d1  cmovnz  r15, rbx
0x1800675d5  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x1800675da  lea     rcx, [rbp+arg_10]; struct IMFSensorGroupId **
0x1800675de  call    ?CreateSensorGroupId@SensorGroupId@@SAJPEAPEAUIMFSensorGroupId@@@Z; SensorGroupId::CreateSensorGroupId(IMFSensorGroupId * *)
0x1800675e3  mov     ebx, eax
0x1800675e5  test    eax, eax
0x1800675e7  jns     short loc_180067600
0x1800675e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800675f0  jb      loc_1800676BF
0x1800675f6  mov     edx, 8Fh
0x1800675fb  jmp     loc_18006753D
0x180067600  mov     rdi, [rbp+arg_10]
0x180067604  lea     rcx, [rbp+arg_18]
0x180067608  mov     rax, [rdi]
0x18006760b  mov     rbx, [rax]
0x18006760e  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180067613  lea     r8, [rbp+arg_18]
0x180067617  mov     rcx, rdi
0x18006761a  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180067621  mov     rax, rbx
0x180067624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067629  mov     ebx, eax
0x18006762b  test    eax, eax
0x18006762d  jns     short loc_180067646
0x18006762f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067636  jb      loc_1800676BF
0x18006763c  mov     edx, 90h
0x180067641  jmp     loc_18006753D
0x180067646  mov     rcx, [rbp+arg_18]
0x18006764a  mov     r8, r15
0x18006764d  mov     edx, 1
0x180067652  mov     rax, [rcx]
0x180067655  mov     rax, [rax+0D0h]
0x18006765c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067661  mov     ebx, eax
0x180067663  test    eax, eax
0x180067665  jns     short loc_18006767A
0x180067667  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006766e  jb      short loc_1800676BF
0x180067670  mov     edx, 91h
0x180067675  jmp     loc_18006753D
0x18006767a  lea     rcx, [rbp+arg_8]
0x18006767e  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180067683  mov     rcx, [rbp+arg_10]; struct IMFSensorGroupId *
0x180067687  lea     rdx, [rbp+arg_8]; struct IMFSensorGroup **
0x18006768b  call    ?LoadSensorGroup@SensorGroup@@SAJPEAUIMFSensorGroupId@@PEAPEAUIMFSensorGroup@@@Z; SensorGroup::LoadSensorGroup(IMFSensorGroupId *,IMFSensorGroup * *)
0x180067690  mov     ebx, eax
0x180067692  test    eax, eax
0x180067694  jns     short loc_1800676CF
0x180067696  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006769d  jb      short loc_1800676BF
0x18006769f  mov     edx, 92h
0x1800676a4  mov     [rsp+40h+var_20], ebx
0x1800676a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800676af  lea     r9, [rsi-8]
0x1800676b3  mov     r8, r13
0x1800676b6  mov     rcx, [rcx+10h]
0x1800676ba  call    WPP_SF_qD
0x1800676bf  cmp     cs:byte_18008D62D, 1
0x1800676c6  jb      short loc_180067705
0x1800676c8  mov     edx, 93h
0x1800676cd  jmp     short loc_1800676EC
0x1800676cf  mov     rax, [rbp+arg_8]
0x1800676d3  mov     [r14], rax
0x1800676d6  mov     [rbp+arg_8], 0
0x1800676de  cmp     cs:byte_18008D62D, 8
0x1800676e5  jb      short loc_180067705
0x1800676e7  mov     edx, 94h
0x1800676ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800676f3  mov     r9d, ebx
0x1800676f6  mov     r8, r13
0x1800676f9  mov     rcx, [rcx+0D8h]
0x180067700  call    WPP_SF_d
0x180067705  lea     rcx, [rbp+arg_8]
0x180067709  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18006770e  lea     rcx, [rbp+arg_18]
0x180067712  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180067717  lea     rcx, [rbp+arg_10]
0x18006771b  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180067720  mov     eax, ebx
0x180067722  add     rsp, 40h
0x180067726  pop     r15
0x180067728  pop     r14
0x18006772a  pop     r13
0x18006772c  pop     rdi
0x18006772d  pop     rsi
0x18006772e  pop     rbx
0x18006772f  pop     rbp
0x180067730  retn
```

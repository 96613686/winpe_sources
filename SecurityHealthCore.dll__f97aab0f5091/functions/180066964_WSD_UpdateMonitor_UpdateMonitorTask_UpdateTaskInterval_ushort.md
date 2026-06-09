# WSD::UpdateMonitor::UpdateMonitorTask::UpdateTaskInterval(ushort *)

- ea: `0x180066964`
- end: `0x180066faf`
- name: `?UpdateTaskInterval@UpdateMonitorTask@UpdateMonitor@WSD@@QEAAJPEAG@Z`
- size: `1611`
- prototype: `__int64 __fastcall(WSD::UpdateMonitor::UpdateMonitorTask *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180062f6c`

## callees

- `0x18000ccb0`
- `0x18000d7fc`
- `0x180058070`
- `0x180063188`
- `0x180065574`
- `0x180066964`
- `0x1800e7010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180066c00`
- `ole32!CoCreateInstance` at `0x180066c00`
- `OLEAUT32!__imp_VariantInit` at `0x180066c5d`
- `OLEAUT32!__imp_VariantInit` at `0x180066c74`
- `OLEAUT32!__imp_VariantInit` at `0x180066c8b`
- `OLEAUT32!__imp_VariantInit` at `0x180066c9f`
- `OLEAUT32!__imp_VariantInit` at `0x180066e28`
- `OLEAUT32!__imp_VariantInit` at `0x180066e3f`
- `OLEAUT32!__imp_VariantInit` at `0x180066c5d`
- `OLEAUT32!__imp_VariantInit` at `0x180066c74`
- `OLEAUT32!__imp_VariantInit` at `0x180066c8b`
- `OLEAUT32!__imp_VariantInit` at `0x180066c9f`
- `OLEAUT32!__imp_VariantInit` at `0x180066e28`
- `OLEAUT32!__imp_VariantInit` at `0x180066e3f`
- `OLEAUT32!__imp_VariantClear` at `0x180066cfd`
- `OLEAUT32!__imp_VariantClear` at `0x180066d08`
- `OLEAUT32!__imp_VariantClear` at `0x180066d14`
- `OLEAUT32!__imp_VariantClear` at `0x180066d1f`
- `OLEAUT32!__imp_VariantClear` at `0x180066edf`
- `OLEAUT32!__imp_VariantClear` at `0x180066eeb`
- `OLEAUT32!__imp_VariantClear` at `0x180066ef6`
- `OLEAUT32!__imp_VariantClear` at `0x180066cfd`
- `OLEAUT32!__imp_VariantClear` at `0x180066d08`
- `OLEAUT32!__imp_VariantClear` at `0x180066d14`
- `OLEAUT32!__imp_VariantClear` at `0x180066d1f`
- `OLEAUT32!__imp_VariantClear` at `0x180066edf`
- `OLEAUT32!__imp_VariantClear` at `0x180066eeb`
- `OLEAUT32!__imp_VariantClear` at `0x180066ef6`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall WSD::UpdateMonitor::UpdateMonitorTask::UpdateTaskInterval(
        WSD::UpdateMonitor::UpdateMonitorTask *this,
        unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  _QWORD *v5; // rsi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, VARIANTARG *, __int128 *, __int128 *, VARIANTARG *); // rbx
  __int128 v12; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v14; // xmm8
  IRecordInfo *v15; // xmm9_8
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  LPVOID v18; // rbx
  __int64 (__fastcall *v19)(LPVOID, _QWORD *, __int64 *); // rdi
  _QWORD *v20; // rdx
  const unsigned __int16 *v21; // rdx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, _QWORD *); // rdi
  _variant_t *v26; // rax
  __int128 v27; // xmm6
  IRecordInfo *v28; // xmm7_8
  __int128 v29; // xmm8
  IRecordInfo *v30; // xmm9_8
  __int128 v31; // xmm10
  IRecordInfo *v32; // xmm11_8
  __int64 v33; // r15
  _QWORD *v34; // rdx
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG v39; // [rsp+70h] [rbp-98h] BYREF
  IRecordInfo *v40; // [rsp+88h] [rbp-80h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-78h] BYREF
  __int128 v42; // [rsp+A8h] [rbp-60h] BYREF
  IRecordInfo *v43; // [rsp+B8h] [rbp-50h]
  __int128 v44; // [rsp+C8h] [rbp-40h] BYREF
  IRecordInfo *v45; // [rsp+D8h] [rbp-30h]
  VARIANTARG v46; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG v47; // [rsp+108h] [rbp+0h] BYREF
  VARIANTARG v48; // [rsp+128h] [rbp+20h] BYREF
  VARIANTARG v49; // [rsp+140h] [rbp+38h] BYREF
  __int64 v50; // [rsp+1F0h] [rbp+E8h] BYREF
  __int64 v51; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v52; // [rsp+200h] [rbp+F8h] BYREF

  if ( a2 )
  {
    v38 = 0;
    v5 = (_QWORD *)((char *)this + 16);
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 2) + 152LL))(*((_QWORD *)this + 2), &v38);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids,
          (unsigned int)v4);
      goto LABEL_56;
    }
    v50 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 72LL))(v38, &v50);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids,
          (unsigned int)v4);
      goto LABEL_13;
    }
    v51 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v50 + 64LL))(v50, 1, &v51);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids,
          (unsigned int)v4);
      goto LABEL_18;
    }
    v52 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 80LL))(v51, &v52);
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v7 = 54;
      goto LABEL_23;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v52 + 64LL))(v52, a2);
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v7 = 55;
LABEL_23:
      WPP_SF_d(v6[2], v7, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids, (unsigned int)v4);
LABEL_24:
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v52);
LABEL_18:
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v51);
LABEL_13:
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v50);
LABEL_56:
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v38);
      return (unsigned int)v4;
    }
    ppv = 0;
    v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    if ( v4 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_34;
      v9 = 56;
      goto LABEL_33;
    }
    v10 = ppv;
    v11 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, VARIANTARG *))(*(_QWORD *)ppv + 80LL);
    VariantInit(&pvarg);
    v12 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit((VARIANTARG *)&v39.decVal.8);
    v14 = *(_OWORD *)&v39.decVal.Lo32;
    v15 = v40;
    VariantInit(&v49);
    v16 = *(_OWORD *)&v49.vt;
    v17 = v49.pRecInfo;
    VariantInit(&v48);
    *(_OWORD *)&v47.vt = v12;
    v47.pRecInfo = pRecInfo;
    v42 = v14;
    v43 = v15;
    v44 = v16;
    v45 = v17;
    v46 = v48;
    v4 = v11(v10, &v46, &v44, &v42, &v47);
    VariantClear(&v48);
    VariantClear(&v49);
    VariantClear((VARIANTARG *)&v39.decVal.8);
    VariantClear(&pvarg);
    if ( v4 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_34;
      v9 = 57;
LABEL_33:
      WPP_SF_d(v8[2], v9, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids, (unsigned int)v4);
LABEL_34:
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
      goto LABEL_24;
    }
    v37 = 0;
    v18 = ppv;
    v19 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)ppv + 56LL);
    v20 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v39, L"\\microsoft\\windows\\waasmedic");
    if ( v20 )
      v20 = (_QWORD *)*v20;
    v4 = v19(v18, v20, &v37);
    _bstr_t::_Free((_bstr_t *)&v39);
    if ( v4 >= 0 )
    {
      v24 = v37;
      v25 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, _QWORD *))(*(_QWORD *)v37 + 136LL);
      if ( *v5 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
        *v5 = 0;
      }
      v26 = _variant_t::_variant_t((_variant_t *)&v47, v21);
      v27 = *(_OWORD *)v26;
      v28 = (IRecordInfo *)*((_QWORD *)v26 + 2);
      VariantInit((VARIANTARG *)&v39.decVal.8);
      v29 = *(_OWORD *)&v39.decVal.Lo32;
      v30 = v40;
      VariantInit(&pvarg);
      v31 = *(_OWORD *)&pvarg.vt;
      v32 = pvarg.pRecInfo;
      v33 = v38;
      v34 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v39, L"performremediation");
      if ( v34 )
        v34 = (_QWORD *)*v34;
      *(_OWORD *)&v46.vt = v27;
      v46.pRecInfo = v28;
      v44 = v29;
      v45 = v30;
      v42 = v31;
      v43 = v32;
      v4 = v25(v24, v34, v33, 6, &v42, &v44, 5, &v46, v5);
      _bstr_t::_Free((_bstr_t *)&v39);
      VariantClear(&pvarg);
      VariantClear((VARIANTARG *)&v39.decVal.8);
      VariantClear(&v47);
      if ( v4 >= 0 )
      {
        *((_DWORD *)this + 6) |= 8u;
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v37);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v52);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v51);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v50);
        v4 = 0;
        goto LABEL_56;
      }
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      v23 = 59;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      v23 = 58;
    }
    WPP_SF_d(v22[2], v23, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids, (unsigned int)v4);
LABEL_46:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v37);
    goto LABEL_34;
  }
  v4 = -2147024809;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids, 2147942487LL);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180066964  mov     rax, rsp
0x180066967  mov     [rax+8], rbx
0x18006696b  push    rbp
0x18006696c  push    rsi
0x18006696d  push    rdi
0x18006696e  push    r14
0x180066970  push    r15
0x180066972  lea     rbp, [rax-0D8h]
0x180066979  sub     rsp, 1B0h
0x180066980  movaps  xmmword ptr [rax-38h], xmm6
0x180066984  movaps  xmmword ptr [rax-48h], xmm7
0x180066988  movaps  xmmword ptr [rax-58h], xmm8
0x18006698d  movaps  xmmword ptr [rax-68h], xmm9
0x180066992  movaps  xmmword ptr [rax-78h], xmm10
0x180066997  movaps  xmmword ptr [rax-88h], xmm11
0x18006699f  mov     rdi, rdx
0x1800669a2  mov     r14, rcx
0x1800669a5  test    rdx, rdx
0x1800669a8  jnz     short loc_1800669EB
0x1800669aa  lea     rax, WPP_GLOBAL_Control
0x1800669b1  mov     ebx, 80070057h
0x1800669b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800669bd  cmp     rcx, rax
0x1800669c0  jz      loc_180066F78
0x1800669c6  test    byte ptr [rcx+1Ch], 1
0x1800669ca  jz      loc_180066F78
0x1800669d0  lea     edx, [rdi+32h]
0x1800669d3  mov     r9d, ebx
0x1800669d6  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x1800669dd  mov     rcx, [rcx+10h]
0x1800669e1  call    WPP_SF_d
0x1800669e6  jmp     loc_180066F78
0x1800669eb  mov     [rsp+1D0h+var_170], 0
0x1800669f4  lea     rsi, [rcx+10h]
0x1800669f8  mov     rcx, [rsi]
0x1800669fb  mov     rax, [rcx]
0x1800669fe  lea     rdx, [rsp+1D0h+var_170]
0x180066a03  mov     rax, [rax+98h]
0x180066a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a0f  mov     ebx, eax
0x180066a11  test    eax, eax
0x180066a13  jns     short loc_180066A53
0x180066a15  lea     rax, WPP_GLOBAL_Control
0x180066a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a23  cmp     rcx, rax
0x180066a26  jz      loc_180066F6E
0x180066a2c  test    byte ptr [rcx+1Ch], 1
0x180066a30  jz      loc_180066F6E
0x180066a36  mov     edx, 33h ; '3'
0x180066a3b  mov     r9d, ebx
0x180066a3e  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180066a45  mov     rcx, [rcx+10h]
0x180066a49  call    WPP_SF_d
0x180066a4e  jmp     loc_180066F6E
0x180066a53  mov     [rbp+0D0h+arg_8], 0
0x180066a5e  mov     rcx, [rsp+1D0h+var_170]
0x180066a63  mov     rax, [rcx]
0x180066a66  lea     rdx, [rbp+0D0h+arg_8]
0x180066a6d  mov     rax, [rax+48h]
0x180066a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a76  mov     ebx, eax
0x180066a78  test    eax, eax
0x180066a7a  jns     short loc_180066ABF
0x180066a7c  lea     rax, WPP_GLOBAL_Control
0x180066a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a8a  cmp     rcx, rax
0x180066a8d  jz      short loc_180066AAE
0x180066a8f  test    byte ptr [rcx+1Ch], 1
0x180066a93  jz      short loc_180066AAE
0x180066a95  mov     edx, 34h ; '4'
0x180066a9a  mov     r9d, ebx
0x180066a9d  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180066aa4  mov     rcx, [rcx+10h]
0x180066aa8  call    WPP_SF_d
0x180066aad  nop
0x180066aae  lea     rcx, [rbp+0D0h+arg_8]
0x180066ab5  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180066aba  jmp     loc_180066F6E
0x180066abf  mov     [rbp+0D0h+arg_10], 0
0x180066aca  mov     rcx, [rbp+0D0h+arg_8]
0x180066ad1  mov     rax, [rcx]
0x180066ad4  lea     r8, [rbp+0D0h+arg_10]
0x180066adb  mov     edx, 1
0x180066ae0  mov     rax, [rax+40h]
0x180066ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ae9  mov     ebx, eax
0x180066aeb  test    eax, eax
0x180066aed  jns     short loc_180066B32
0x180066aef  lea     rax, WPP_GLOBAL_Control
0x180066af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180066afd  cmp     rcx, rax
0x180066b00  jz      short loc_180066B21
0x180066b02  test    byte ptr [rcx+1Ch], 1
0x180066b06  jz      short loc_180066B21
0x180066b08  mov     edx, 35h ; '5'
0x180066b0d  mov     r9d, ebx
0x180066b10  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180066b17  mov     rcx, [rcx+10h]
0x180066b1b  call    WPP_SF_d
0x180066b20  nop
0x180066b21  lea     rcx, [rbp+0D0h+arg_10]
0x180066b28  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180066b2d  jmp     loc_180066AAE
0x180066b32  mov     [rbp+0D0h+arg_18], 0
0x180066b3d  mov     rcx, [rbp+0D0h+arg_10]
0x180066b44  mov     rax, [rcx]
0x180066b47  lea     rdx, [rbp+0D0h+arg_18]
0x180066b4e  mov     rax, [rax+50h]
0x180066b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b57  mov     ebx, eax
0x180066b59  test    eax, eax
0x180066b5b  jns     short loc_180066B9D
0x180066b5d  lea     rax, WPP_GLOBAL_Control
0x180066b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180066b6b  cmp     rcx, rax
0x180066b6e  jz      short loc_180066B8F
0x180066b70  test    byte ptr [rcx+1Ch], 1
0x180066b74  jz      short loc_180066B8F
0x180066b76  mov     edx, 36h ; '6'
0x180066b7b  mov     r9d, ebx
0x180066b7e  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180066b85  mov     rcx, [rcx+10h]
0x180066b89  call    WPP_SF_d
0x180066b8e  nop
0x180066b8f  lea     rcx, [rbp+0D0h+arg_18]
0x180066b96  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180066b9b  jmp     short loc_180066B21
0x180066b9d  mov     rcx, [rbp+0D0h+arg_18]
0x180066ba4  mov     rax, [rcx]
0x180066ba7  mov     rdx, rdi
0x180066baa  mov     rax, [rax+40h]
0x180066bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bb3  mov     ebx, eax
0x180066bb5  test    eax, eax
0x180066bb7  jns     short loc_180066BD9
0x180066bb9  lea     rax, WPP_GLOBAL_Control
0x180066bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180066bc7  cmp     rcx, rax
0x180066bca  jz      short loc_180066B8F
0x180066bcc  test    byte ptr [rcx+1Ch], 1
0x180066bd0  jz      short loc_180066B8F
0x180066bd2  mov     edx, 37h ; '7'
0x180066bd7  jmp     short loc_180066B7B
0x180066bd9  mov     [rsp+1D0h+var_180], 0
0x180066be2  lea     rax, [rsp+1D0h+var_180]
0x180066be7  mov     [rsp+1D0h+ppv], rax; ppv
0x180066bec  lea     r9, IID_ITaskService; riid
0x180066bf3  xor     edx, edx; pUnkOuter
0x180066bf5  lea     r8d, [rdx+1]; dwClsContext
0x180066bf9  lea     rcx, CLSID_TaskScheduler; rclsid
0x180066c00  call    cs:__imp_CoCreateInstance
0x180066c06  mov     ebx, eax
0x180066c08  test    eax, eax
0x180066c0a  jns     short loc_180066C4D
0x180066c0c  lea     rax, WPP_GLOBAL_Control
0x180066c13  mov     rcx, cs:WPP_GLOBAL_Control
0x180066c1a  cmp     rcx, rax
0x180066c1d  jz      short loc_180066C3E
0x180066c1f  test    byte ptr [rcx+1Ch], 1
0x180066c23  jz      short loc_180066C3E
0x180066c25  mov     edx, 38h ; '8'
0x180066c2a  mov     r9d, ebx
0x180066c2d  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180066c34  mov     rcx, [rcx+10h]
0x180066c38  call    WPP_SF_d
0x180066c3d  nop
0x180066c3e  lea     rcx, [rsp+1D0h+var_180]
0x180066c43  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180066c48  jmp     loc_180066B8F
0x180066c4d  mov     rdi, [rsp+1D0h+var_180]
0x180066c52  mov     rax, [rdi]
0x180066c55  mov     rbx, [rax+50h]
0x180066c59  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x180066c5d  call    cs:__imp_VariantInit
0x180066c63  nop
0x180066c64  movups  xmm10, xmmword ptr [rbp+0D0h+pvarg]
0x180066c69  movsd   xmm11, qword ptr [rbp+0D0h+pvarg+10h]
0x180066c6f  lea     rcx, [rsp+1D0h+var_168+8]; pvarg
0x180066c74  call    cs:__imp_VariantInit
0x180066c7a  nop
0x180066c7b  movups  xmm8, xmmword ptr [rsp+1D0h+var_168+8]
0x180066c81  movsd   xmm9, [rbp+0D0h+var_150]
0x180066c87  lea     rcx, [rbp+0D0h+var_98]; pvarg
0x180066c8b  call    cs:__imp_VariantInit
0x180066c91  nop
0x180066c92  movups  xmm6, xmmword ptr [rbp+0D0h+var_98]
0x180066c96  movsd   xmm7, qword ptr [rbp+0D0h+var_98+10h]
0x180066c9b  lea     rcx, [rbp+0D0h+var_B0]; pvarg
0x180066c9f  call    cs:__imp_VariantInit
0x180066ca5  nop
0x180066ca6  movups  xmm0, xmmword ptr [rbp+0D0h+var_B0]
0x180066caa  movsd   xmm1, qword ptr [rbp+0D0h+var_B0+10h]
0x180066caf  movaps  xmmword ptr [rbp+0D0h+var_D0], xmm10
0x180066cb4  movsd   qword ptr [rbp+0D0h+var_D0+10h], xmm11
0x180066cba  movaps  [rbp+0D0h+var_130], xmm8
0x180066cbf  movsd   [rbp+0D0h+var_120], xmm9
0x180066cc5  movaps  [rbp+0D0h+var_110], xmm6
0x180066cc9  movsd   [rbp+0D0h+var_100], xmm7
0x180066cce  movaps  [rbp+0D0h+var_F0], xmm0
0x180066cd2  movsd   [rbp+0D0h+var_E0], xmm1
0x180066cd7  lea     rax, [rbp+0D0h+var_D0]
0x180066cdb  mov     [rsp+1D0h+ppv], rax
0x180066ce0  lea     r9, [rbp+0D0h+var_130]
0x180066ce4  lea     r8, [rbp+0D0h+var_110]
0x180066ce8  lea     rdx, [rbp+0D0h+var_F0]
0x180066cec  mov     rcx, rdi
0x180066cef  mov     rax, rbx
0x180066cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cf7  mov     ebx, eax
0x180066cf9  lea     rcx, [rbp+0D0h+var_B0]; pvarg
0x180066cfd  call    cs:__imp_VariantClear
0x180066d03  nop
0x180066d04  lea     rcx, [rbp+0D0h+var_98]; pvarg
0x180066d08  call    cs:__imp_VariantClear
0x180066d0e  nop
0x180066d0f  lea     rcx, [rsp+1D0h+var_168+8]; pvarg
0x180066d14  call    cs:__imp_VariantClear
0x180066d1a  nop
0x180066d1b  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x180066d1f  call    cs:__imp_VariantClear
0x180066d25  test    ebx, ebx
0x180066d27  jns     short loc_180066D54
0x180066d29  lea     rax, WPP_GLOBAL_Control
0x180066d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d37  cmp     rcx, rax
0x180066d3a  jz      loc_180066C3E
0x180066d40  test    byte ptr [rcx+1Ch], 1
0x180066d44  jz      loc_180066C3E
0x180066d4a  mov     edx, 39h ; '9'
0x180066d4f  jmp     loc_180066C2A
0x180066d54  mov     [rsp+1D0h+var_178], 0
0x180066d5d  mov     rbx, [rsp+1D0h+var_180]
0x180066d62  mov     rax, [rbx]
0x180066d65  mov     rdi, [rax+38h]
0x180066d69  lea     rdx, aMicrosoftWindo_3; "\\microsoft\\windows\\waasmedic"
0x180066d70  lea     rcx, [rsp+1D0h+var_168]; this
0x180066d75  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180066d7a  nop
0x180066d7b  mov     rdx, [rax]
0x180066d7e  test    rdx, rdx
0x180066d81  jz      short loc_180066D86
0x180066d83  mov     rdx, [rdx]
0x180066d86  lea     r8, [rsp+1D0h+var_178]
0x180066d8b  mov     rcx, rbx
0x180066d8e  mov     rax, rdi
0x180066d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d96  mov     ebx, eax
0x180066d98  lea     rcx, [rsp+1D0h+var_168]; this
0x180066d9d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180066da2  test    ebx, ebx
0x180066da4  jns     short loc_180066DE7
0x180066da6  lea     rax, WPP_GLOBAL_Control
0x180066dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180066db4  cmp     rcx, rax
0x180066db7  jz      short loc_180066DD8
0x180066db9  test    byte ptr [rcx+1Ch], 1
0x180066dbd  jz      short loc_180066DD8
0x180066dbf  mov     edx, 3Ah ; ':'
0x180066dc4  mov     r9d, ebx
0x180066dc7  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180066dce  mov     rcx, [rcx+10h]
0x180066dd2  call    WPP_SF_d
0x180066dd7  nop
0x180066dd8  lea     rcx, [rsp+1D0h+var_178]
0x180066ddd  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180066de2  jmp     loc_180066C3E
0x180066de7  mov     rbx, [rsp+1D0h+var_178]
0x180066dec  mov     rax, [rbx]
0x180066def  mov     rdi, [rax+88h]
0x180066df6  mov     rcx, [rsi]
0x180066df9  test    rcx, rcx
0x180066dfc  jz      short loc_180066E11
0x180066dfe  mov     rax, [rcx]
0x180066e01  mov     rax, [rax+10h]
0x180066e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e0a  mov     qword ptr [rsi], 0
0x180066e11  lea     rcx, [rbp+0D0h+var_D0]; this
0x180066e15  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180066e1a  nop
0x180066e1b  movups  xmm6, xmmword ptr [rax]
0x180066e1e  movsd   xmm7, qword ptr [rax+10h]
0x180066e23  lea     rcx, [rsp+1D0h+var_168+8]; pvarg
0x180066e28  call    cs:__imp_VariantInit
0x180066e2e  nop
0x180066e2f  movups  xmm8, xmmword ptr [rsp+1D0h+var_168+8]
0x180066e35  movsd   xmm9, [rbp+0D0h+var_150]
0x180066e3b  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x180066e3f  call    cs:__imp_VariantInit
0x180066e45  nop
0x180066e46  movups  xmm10, xmmword ptr [rbp+0D0h+pvarg]
0x180066e4b  movsd   xmm11, qword ptr [rbp+0D0h+pvarg+10h]
0x180066e51  mov     r15, [rsp+1D0h+var_170]
0x180066e56  lea     rdx, aPerformremedia; "performremediation"
0x180066e5d  lea     rcx, [rsp+1D0h+var_168]; this
0x180066e62  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180066e67  nop
0x180066e68  mov     rdx, [rax]
0x180066e6b  test    rdx, rdx
0x180066e6e  jz      short loc_180066E73
0x180066e70  mov     rdx, [rdx]
  ... truncated ...
```

# WSD::UpdateMonitor::UpdateMonitorTask::GetOrCreateTask(void)

- ea: `0x1800659e4`
- end: `0x180065eb9`
- name: `?GetOrCreateTask@UpdateMonitorTask@UpdateMonitor@WSD@@AEAAJXZ`
- size: `1237`
- prototype: `__int64 __fastcall(WSD::UpdateMonitor::UpdateMonitorTask *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180057fa4`

## callees

- `0x18000ccb0`
- `0x18000d7fc`
- `0x180010ff0`
- `0x180058070`
- `0x180063188`
- `0x180065574`
- `0x1800659e4`
- `0x1800e7010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180065a53`
- `ole32!CoCreateInstance` at `0x180065a53`
- `OLEAUT32!__imp_VariantInit` at `0x180065a9e`
- `OLEAUT32!__imp_VariantInit` at `0x180065ab7`
- `OLEAUT32!__imp_VariantInit` at `0x180065acf`
- `OLEAUT32!__imp_VariantInit` at `0x180065ae3`
- `OLEAUT32!__imp_VariantInit` at `0x180065d34`
- `OLEAUT32!__imp_VariantInit` at `0x180065d4d`
- `OLEAUT32!__imp_VariantInit` at `0x180065a9e`
- `OLEAUT32!__imp_VariantInit` at `0x180065ab7`
- `OLEAUT32!__imp_VariantInit` at `0x180065acf`
- `OLEAUT32!__imp_VariantInit` at `0x180065ae3`
- `OLEAUT32!__imp_VariantInit` at `0x180065d34`
- `OLEAUT32!__imp_VariantInit` at `0x180065d4d`
- `OLEAUT32!__imp_VariantClear` at `0x180065b41`
- `OLEAUT32!__imp_VariantClear` at `0x180065b4c`
- `OLEAUT32!__imp_VariantClear` at `0x180065b58`
- `OLEAUT32!__imp_VariantClear` at `0x180065b64`
- `OLEAUT32!__imp_VariantClear` at `0x180065e19`
- `OLEAUT32!__imp_VariantClear` at `0x180065e25`
- `OLEAUT32!__imp_VariantClear` at `0x180065e30`
- `OLEAUT32!__imp_VariantClear` at `0x180065b41`
- `OLEAUT32!__imp_VariantClear` at `0x180065b4c`
- `OLEAUT32!__imp_VariantClear` at `0x180065b58`
- `OLEAUT32!__imp_VariantClear` at `0x180065b64`
- `OLEAUT32!__imp_VariantClear` at `0x180065e19`
- `OLEAUT32!__imp_VariantClear` at `0x180065e25`
- `OLEAUT32!__imp_VariantClear` at `0x180065e30`

## string_xrefs

- `0x180065d61`: `<?xml version="1.0" encoding="UTF-16"?><Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" version="1.4">          <RegistrationInfo>                                                                              <Author>$(@%systemroot%\system32\WaasMedicSvc.dll,-102)</Author>                            <Source>$(@%systemroot%\system32\WaasMedicSvc.dll,-103)</Source>                            <Description>$(@%systemroot%\system32\WaasMedicSvc.dll,-104)</Description>               `

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WSD::UpdateMonitor::UpdateMonitorTask::GetOrCreateTask(WSD::UpdateMonitor::UpdateMonitorTask *this)
{
  HRESULT v2; // eax
  int v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, __int128 *, __int128 *, VARIANTARG *); // rbx
  __int128 v9; // xmm10
  IRecordInfo *v10; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  LPVOID v15; // rbx
  __int64 (__fastcall *v16)(LPVOID, _QWORD *, __int64 *); // rdi
  _QWORD *v17; // rdx
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64, char *); // rsi
  _QWORD *v20; // rdi
  __int64 v21; // rcx
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  int v24; // esi
  const unsigned __int16 *v25; // rdx
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64, _QWORD *, __int64, __int128 *, __int128 *, int, VARIANTARG *, char *); // r12
  _variant_t *v28; // rax
  __int128 v29; // xmm6
  IRecordInfo *v30; // xmm7_8
  __int128 v31; // xmm8
  IRecordInfo *v32; // xmm9_8
  __int128 v33; // xmm10
  IRecordInfo *v34; // xmm11_8
  _QWORD *v35; // r15
  _bstr_t *v36; // rax
  __int64 v37; // rdx
  VARIANTARG v39; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-A0h] BYREF
  IRecordInfo *v41; // [rsp+80h] [rbp-88h]
  _BYTE v42[16]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v43; // [rsp+98h] [rbp-70h] BYREF
  IRecordInfo *v44; // [rsp+A8h] [rbp-60h]
  __int128 v45; // [rsp+B8h] [rbp-50h] BYREF
  IRecordInfo *v46; // [rsp+C8h] [rbp-40h]
  VARIANTARG v47; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v48; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v49; // [rsp+118h] [rbp+10h] BYREF
  VARIANTARG v50; // [rsp+130h] [rbp+28h] BYREF
  __int64 v51; // [rsp+1F0h] [rbp+E8h] BYREF
  LPVOID ppv; // [rsp+1F8h] [rbp+F0h] BYREF
  char v53; // [rsp+200h] [rbp+F8h] BYREF

  ppv = 0;
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v7 = ppv;
    v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, VARIANTARG *))(*(_QWORD *)ppv + 80LL);
    VariantInit((VARIANTARG *)&pvarg.decVal.8);
    v9 = *(_OWORD *)&pvarg.decVal.Lo32;
    v10 = v41;
    VariantInit((VARIANTARG *)&v39.decVal.8);
    v11 = *(_OWORD *)&v39.decVal.Lo32;
    v12 = *(IRecordInfo **)&pvarg.vt;
    VariantInit(&v50);
    v13 = *(_OWORD *)&v50.vt;
    pRecInfo = v50.pRecInfo;
    VariantInit(&v49);
    *(_OWORD *)&v48.vt = v9;
    v48.pRecInfo = v10;
    v43 = v11;
    v44 = v12;
    v45 = v13;
    v46 = pRecInfo;
    v47 = v49;
    v3 = v8(v7, &v47, &v45, &v43, &v48);
    VariantClear(&v49);
    VariantClear(&v50);
    VariantClear((VARIANTARG *)&v39.decVal.8);
    VariantClear((VARIANTARG *)&pvarg.decVal.8);
    if ( v3 >= 0 )
    {
      v51 = 0;
      v15 = ppv;
      v16 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)ppv + 56LL);
      v17 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v53, L"\\microsoft\\windows\\waasmedic");
      if ( v17 )
        v17 = (_QWORD *)*v17;
      v3 = v16(v15, v17, &v51);
      _bstr_t::_Free((_bstr_t *)&v53);
      if ( v3 >= 0 )
      {
        v18 = v51;
        v19 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v51 + 104LL);
        v20 = (_QWORD *)((char *)this + 16);
        v21 = *((_QWORD *)this + 2);
        if ( v21 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          *v20 = 0;
        }
        v22 = _bstr_t::_bstr_t((_bstr_t *)&v53, L"performremediation");
        if ( *(_QWORD *)v22 )
          v23 = **(_QWORD **)v22;
        else
          v23 = 0;
        v24 = v19(v18, v23, (char *)this + 16);
        _bstr_t::_Free((_bstr_t *)&v53);
        if ( v24 == -2147024894 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids);
          v26 = v51;
          v27 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *, __int64, __int128 *, __int128 *, int, VARIANTARG *, char *))(*(_QWORD *)v51 + 128LL);
          if ( *v20 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 16LL))(*v20);
            *v20 = 0;
          }
          v28 = _variant_t::_variant_t((_variant_t *)&v48, v25);
          v29 = *(_OWORD *)v28;
          v30 = (IRecordInfo *)*((_QWORD *)v28 + 2);
          VariantInit((VARIANTARG *)&v39.decVal.8);
          v31 = *(_OWORD *)&v39.decVal.Lo32;
          v32 = *(IRecordInfo **)&pvarg.vt;
          VariantInit((VARIANTARG *)&pvarg.decVal.8);
          v33 = *(_OWORD *)&pvarg.decVal.Lo32;
          v34 = v41;
          v35 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v42, aXmlVersion10En);
          if ( v35 )
            v35 = (_QWORD *)*v35;
          v36 = _bstr_t::_bstr_t((_bstr_t *)&v53, L"performremediation");
          if ( *(_QWORD *)v36 )
            v37 = **(_QWORD **)v36;
          else
            v37 = 0;
          *(_OWORD *)&v47.vt = v29;
          v47.pRecInfo = v30;
          v45 = v31;
          v46 = v32;
          v43 = v33;
          v44 = v34;
          v24 = v27(v26, v37, v35, 2, &v43, &v45, 5, &v47, (char *)this + 16);
          _bstr_t::_Free((_bstr_t *)&v53);
          _bstr_t::_Free((_bstr_t *)v42);
          VariantClear((VARIANTARG *)&pvarg.decVal.8);
          VariantClear((VARIANTARG *)&v39.decVal.8);
          VariantClear(&v48);
          if ( v24 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids,
              (unsigned int)v24);
          *((_DWORD *)this + 6) |= 1u;
        }
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v51);
        v3 = v24;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids,
            (unsigned int)v3);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v51);
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 12;
        v6 = (unsigned int)v3;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 11;
      v6 = (unsigned int)v2;
LABEL_9:
      WPP_SF_d(v4[2], v5, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids, v6);
    }
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800659e4  mov     rax, rsp
0x1800659e7  push    rbp
0x1800659e8  push    rbx
0x1800659e9  push    rsi
0x1800659ea  push    rdi
0x1800659eb  push    r12
0x1800659ed  push    r14
0x1800659ef  push    r15
0x1800659f1  lea     rbp, [rax-0D8h]
0x1800659f8  sub     rsp, 1A0h
0x1800659ff  movaps  xmmword ptr [rax-48h], xmm6
0x180065a03  movaps  xmmword ptr [rax-58h], xmm7
0x180065a07  movaps  xmmword ptr [rax-68h], xmm8
0x180065a0c  movaps  xmmword ptr [rax-78h], xmm9
0x180065a11  movaps  xmmword ptr [rax-88h], xmm10
0x180065a19  movaps  xmmword ptr [rax-98h], xmm11
0x180065a21  mov     r14, rcx
0x180065a24  mov     [rbp+0D0h+arg_10], 0
0x180065a2f  lea     rax, [rbp+0D0h+arg_10]
0x180065a36  mov     [rsp+1D0h+ppv], rax; ppv
0x180065a3b  lea     r9, IID_ITaskService; riid
0x180065a42  mov     esi, 1
0x180065a47  mov     r8d, esi; dwClsContext
0x180065a4a  xor     edx, edx; pUnkOuter
0x180065a4c  lea     rcx, CLSID_TaskScheduler; rclsid
0x180065a53  call    cs:__imp_CoCreateInstance
0x180065a59  mov     edi, eax
0x180065a5b  test    eax, eax
0x180065a5d  jns     short loc_180065A8B
0x180065a5f  lea     rbx, WPP_GLOBAL_Control
0x180065a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180065a6d  cmp     rcx, rbx
0x180065a70  jz      loc_180065E77
0x180065a76  test    [rcx+1Ch], sil
0x180065a7a  jz      loc_180065E77
0x180065a80  lea     edx, [rsi+0Ah]
0x180065a83  mov     r9d, eax
0x180065a86  jmp     loc_180065B97
0x180065a8b  mov     rdi, [rbp+0D0h+arg_10]
0x180065a92  mov     rax, [rdi]
0x180065a95  mov     rbx, [rax+50h]
0x180065a99  lea     rcx, [rsp+1D0h+pvarg+8]; pvarg
0x180065a9e  call    cs:__imp_VariantInit
0x180065aa4  nop
0x180065aa5  movups  xmm10, xmmword ptr [rsp+1D0h+pvarg+8]
0x180065aab  movsd   xmm11, [rsp+1D0h+var_158]
0x180065ab2  lea     rcx, [rsp+1D0h+var_188+8]; pvarg
0x180065ab7  call    cs:__imp_VariantInit
0x180065abd  nop
0x180065abe  movups  xmm8, xmmword ptr [rsp+1D0h+var_188+8]
0x180065ac4  movsd   xmm9, qword ptr [rsp+1D0h+pvarg]
0x180065acb  lea     rcx, [rbp+0D0h+var_A8]; pvarg
0x180065acf  call    cs:__imp_VariantInit
0x180065ad5  nop
0x180065ad6  movups  xmm6, xmmword ptr [rbp+0D0h+var_A8]
0x180065ada  movsd   xmm7, qword ptr [rbp+0D0h+var_A8+10h]
0x180065adf  lea     rcx, [rbp+0D0h+var_C0]; pvarg
0x180065ae3  call    cs:__imp_VariantInit
0x180065ae9  nop
0x180065aea  movups  xmm0, xmmword ptr [rbp+0D0h+var_C0]
0x180065aee  movsd   xmm1, qword ptr [rbp+0D0h+var_C0+10h]
0x180065af3  movaps  xmmword ptr [rbp+0D0h+var_E0], xmm10
0x180065af8  movsd   qword ptr [rbp+0D0h+var_E0+10h], xmm11
0x180065afe  movaps  [rbp+0D0h+var_140], xmm8
0x180065b03  movsd   [rbp+0D0h+var_130], xmm9
0x180065b09  movaps  [rbp+0D0h+var_120], xmm6
0x180065b0d  movsd   [rbp+0D0h+var_110], xmm7
0x180065b12  movaps  [rbp+0D0h+var_100], xmm0
0x180065b16  movsd   [rbp+0D0h+var_F0], xmm1
0x180065b1b  lea     rax, [rbp+0D0h+var_E0]
0x180065b1f  mov     [rsp+1D0h+ppv], rax
0x180065b24  lea     r9, [rbp+0D0h+var_140]
0x180065b28  lea     r8, [rbp+0D0h+var_120]
0x180065b2c  lea     rdx, [rbp+0D0h+var_100]
0x180065b30  mov     rcx, rdi
0x180065b33  mov     rax, rbx
0x180065b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b3b  mov     edi, eax
0x180065b3d  lea     rcx, [rbp+0D0h+var_C0]; pvarg
0x180065b41  call    cs:__imp_VariantClear
0x180065b47  nop
0x180065b48  lea     rcx, [rbp+0D0h+var_A8]; pvarg
0x180065b4c  call    cs:__imp_VariantClear
0x180065b52  nop
0x180065b53  lea     rcx, [rsp+1D0h+var_188+8]; pvarg
0x180065b58  call    cs:__imp_VariantClear
0x180065b5e  nop
0x180065b5f  lea     rcx, [rsp+1D0h+pvarg+8]; pvarg
0x180065b64  call    cs:__imp_VariantClear
0x180065b6a  test    edi, edi
0x180065b6c  jns     short loc_180065BAC
0x180065b6e  lea     rbx, WPP_GLOBAL_Control
0x180065b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180065b7c  cmp     rcx, rbx
0x180065b7f  jz      loc_180065E77
0x180065b85  test    [rcx+1Ch], sil
0x180065b89  jz      loc_180065E77
0x180065b8f  mov     edx, 0Ch
0x180065b94  mov     r9d, edi
0x180065b97  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180065b9e  mov     rcx, [rcx+10h]
0x180065ba2  call    WPP_SF_d
0x180065ba7  jmp     loc_180065E77
0x180065bac  mov     [rbp+0D0h+arg_8], 0
0x180065bb7  mov     rbx, [rbp+0D0h+arg_10]
0x180065bbe  mov     rax, [rbx]
0x180065bc1  mov     rdi, [rax+38h]
0x180065bc5  lea     rdx, aMicrosoftWindo_3; "\\microsoft\\windows\\waasmedic"
0x180065bcc  lea     rcx, [rbp+0D0h+arg_18]; this
0x180065bd3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180065bd8  nop
0x180065bd9  mov     rdx, [rax]
0x180065bdc  test    rdx, rdx
0x180065bdf  jz      short loc_180065BE4
0x180065be1  mov     rdx, [rdx]
0x180065be4  lea     r8, [rbp+0D0h+arg_8]
0x180065beb  mov     rcx, rbx
0x180065bee  mov     rax, rdi
0x180065bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065bf6  mov     edi, eax
0x180065bf8  lea     rcx, [rbp+0D0h+arg_18]; this
0x180065bff  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180065c04  test    edi, edi
0x180065c06  jns     short loc_180065C4B
0x180065c08  lea     rbx, WPP_GLOBAL_Control
0x180065c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180065c16  cmp     rcx, rbx
0x180065c19  jz      short loc_180065C3A
0x180065c1b  test    [rcx+1Ch], sil
0x180065c1f  jz      short loc_180065C3A
0x180065c21  mov     edx, 0Dh
0x180065c26  mov     r9d, edi
0x180065c29  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180065c30  mov     rcx, [rcx+10h]
0x180065c34  call    WPP_SF_d
0x180065c39  nop
0x180065c3a  lea     rcx, [rbp+0D0h+arg_8]
0x180065c41  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180065c46  jmp     loc_180065E77
0x180065c4b  mov     rbx, [rbp+0D0h+arg_8]
0x180065c52  mov     rax, [rbx]
0x180065c55  mov     rsi, [rax+68h]
0x180065c59  lea     rdi, [r14+10h]
0x180065c5d  mov     rcx, [rdi]
0x180065c60  test    rcx, rcx
0x180065c63  jz      short loc_180065C78
0x180065c65  mov     rax, [rcx]
0x180065c68  mov     rax, [rax+10h]
0x180065c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c71  mov     qword ptr [rdi], 0
0x180065c78  lea     rdx, aPerformremedia; "performremediation"
0x180065c7f  lea     rcx, [rbp+0D0h+arg_18]; this
0x180065c86  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180065c8b  nop
0x180065c8c  mov     rcx, [rax]
0x180065c8f  test    rcx, rcx
0x180065c92  jz      short loc_180065C99
0x180065c94  mov     rdx, [rcx]
0x180065c97  jmp     short loc_180065C9B
0x180065c99  xor     edx, edx
0x180065c9b  mov     r8, rdi
0x180065c9e  mov     rcx, rbx
0x180065ca1  mov     rax, rsi
0x180065ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ca9  mov     esi, eax
0x180065cab  lea     rcx, [rbp+0D0h+arg_18]; this
0x180065cb2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180065cb7  cmp     esi, 80070002h
0x180065cbd  jnz     loc_180065E69
0x180065cc3  lea     rbx, WPP_GLOBAL_Control
0x180065cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180065cd1  cmp     rcx, rbx
0x180065cd4  jz      short loc_180065CF1
0x180065cd6  test    byte ptr [rcx+1Ch], 4
0x180065cda  jz      short loc_180065CF1
0x180065cdc  mov     edx, 0Eh
0x180065ce1  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180065ce8  mov     rcx, [rcx+10h]
0x180065cec  call    WPP_SF_
0x180065cf1  mov     rsi, [rbp+0D0h+arg_8]
0x180065cf8  mov     rax, [rsi]
0x180065cfb  mov     r12, [rax+80h]
0x180065d02  mov     rcx, [rdi]
0x180065d05  test    rcx, rcx
0x180065d08  jz      short loc_180065D1D
0x180065d0a  mov     rax, [rcx]
0x180065d0d  mov     rax, [rax+10h]
0x180065d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d16  mov     qword ptr [rdi], 0
0x180065d1d  lea     rcx, [rbp+0D0h+var_E0]; this
0x180065d21  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180065d26  nop
0x180065d27  movups  xmm6, xmmword ptr [rax]
0x180065d2a  movsd   xmm7, qword ptr [rax+10h]
0x180065d2f  lea     rcx, [rsp+1D0h+var_188+8]; pvarg
0x180065d34  call    cs:__imp_VariantInit
0x180065d3a  nop
0x180065d3b  movups  xmm8, xmmword ptr [rsp+1D0h+var_188+8]
0x180065d41  movsd   xmm9, qword ptr [rsp+1D0h+pvarg]
0x180065d48  lea     rcx, [rsp+1D0h+pvarg+8]; pvarg
0x180065d4d  call    cs:__imp_VariantInit
0x180065d53  nop
0x180065d54  movups  xmm10, xmmword ptr [rsp+1D0h+pvarg+8]
0x180065d5a  movsd   xmm11, [rsp+1D0h+var_158]
0x180065d61  lea     rdx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x180065d68  lea     rcx, [rbp+0D0h+var_150]; this
0x180065d6c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180065d71  nop
0x180065d72  mov     r15, [rax]
0x180065d75  test    r15, r15
0x180065d78  jz      short loc_180065D7D
0x180065d7a  mov     r15, [r15]
0x180065d7d  lea     rdx, aPerformremedia; "performremediation"
0x180065d84  lea     rcx, [rbp+0D0h+arg_18]; this
0x180065d8b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180065d90  nop
0x180065d91  mov     rcx, [rax]
0x180065d94  test    rcx, rcx
0x180065d97  jz      short loc_180065D9E
0x180065d99  mov     rdx, [rcx]
0x180065d9c  jmp     short loc_180065DA0
0x180065d9e  xor     edx, edx
0x180065da0  movaps  [rbp+0D0h+var_100], xmm6
0x180065da4  movsd   [rbp+0D0h+var_F0], xmm7
0x180065da9  movaps  [rbp+0D0h+var_120], xmm8
0x180065dae  movsd   [rbp+0D0h+var_110], xmm9
0x180065db4  movaps  [rbp+0D0h+var_140], xmm10
0x180065db9  movsd   [rbp+0D0h+var_130], xmm11
0x180065dbf  mov     [rsp+1D0h+var_190], rdi
0x180065dc4  lea     rax, [rbp+0D0h+var_100]
0x180065dc8  mov     [rsp+1D0h+var_198], rax
0x180065dcd  mov     dword ptr [rsp+1D0h+var_1A0], 5
0x180065dd5  lea     rax, [rbp+0D0h+var_120]
0x180065dd9  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x180065dde  lea     rax, [rbp+0D0h+var_140]
0x180065de2  mov     [rsp+1D0h+ppv], rax
0x180065de7  mov     r9d, 2
0x180065ded  mov     r8, r15
0x180065df0  mov     rcx, rsi
0x180065df3  mov     rax, r12
0x180065df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065dfb  mov     esi, eax
0x180065dfd  lea     rcx, [rbp+0D0h+arg_18]; this
0x180065e04  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180065e09  nop
0x180065e0a  lea     rcx, [rbp+0D0h+var_150]; this
0x180065e0e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180065e13  nop
0x180065e14  lea     rcx, [rsp+1D0h+pvarg+8]; pvarg
0x180065e19  call    cs:__imp_VariantClear
0x180065e1f  nop
0x180065e20  lea     rcx, [rsp+1D0h+var_188+8]; pvarg
0x180065e25  call    cs:__imp_VariantClear
0x180065e2b  nop
0x180065e2c  lea     rcx, [rbp+0D0h+var_E0]; pvarg
0x180065e30  call    cs:__imp_VariantClear
0x180065e36  test    esi, esi
0x180065e38  jns     short loc_180065E64
0x180065e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e41  cmp     rcx, rbx
0x180065e44  jz      short loc_180065E64
0x180065e46  test    byte ptr [rcx+1Ch], 1
0x180065e4a  jz      short loc_180065E64
0x180065e4c  mov     edx, 0Fh
0x180065e51  mov     r9d, esi
0x180065e54  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x180065e5b  mov     rcx, [rcx+10h]
0x180065e5f  call    WPP_SF_d
0x180065e64  or      dword ptr [r14+18h], 1
0x180065e69  lea     rcx, [rbp+0D0h+arg_8]
0x180065e70  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180065e75  mov     edi, esi
0x180065e77  lea     rcx, [rbp+0D0h+arg_10]
0x180065e7e  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180065e83  mov     eax, edi
0x180065e85  lea     r11, [rsp+1D0h+var_30]
0x180065e8d  movaps  xmm6, xmmword ptr [r11-10h]
0x180065e92  movaps  xmm7, xmmword ptr [r11-20h]
0x180065e97  movaps  xmm8, xmmword ptr [r11-30h]
0x180065e9c  movaps  xmm9, xmmword ptr [r11-40h]
0x180065ea1  movaps  xmm10, xmmword ptr [r11-50h]
0x180065ea6  movaps  xmm11, xmmword ptr [r11-60h]
0x180065eab  mov     rsp, r11
0x180065eae  pop     r15
0x180065eb0  pop     r14
0x180065eb2  pop     r12
0x180065eb4  pop     rdi
0x180065eb5  pop     rsi
0x180065eb6  pop     rbx
0x180065eb7  pop     rbp
0x180065eb8  retn
```

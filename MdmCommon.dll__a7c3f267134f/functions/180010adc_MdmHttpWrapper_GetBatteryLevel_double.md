# MdmHttpWrapper::GetBatteryLevel(double *)

- ea: `0x180010adc`
- end: `0x180010eae`
- name: `?GetBatteryLevel@MdmHttpWrapper@@CAJPEAN@Z`
- size: `978`
- prototype: `__int64 __fastcall(double *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f3b8`

## callees

- `0x180001520`
- `0x1800065c0`
- `0x180010adc`
- `0x1800117e4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010b7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180010ba1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180010ba1`

## string_xrefs

- `0x180010b48`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MdmHttpWrapper::GetBatteryLevel(double *a1, int a2)
{
  int ActivationFactory; // ebx
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  char v13; // [rsp+20h] [rbp-39h]
  const char *v14; // [rsp+28h] [rbp-31h]
  int v15; // [rsp+30h] [rbp-29h] BYREF
  int v16; // [rsp+34h] [rbp-25h] BYREF
  __int64 v17; // [rsp+38h] [rbp-21h] BYREF
  __int64 v18; // [rsp+40h] [rbp-19h] BYREF
  __int64 v19; // [rsp+48h] [rbp-11h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF

  v21 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( !a1 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_38;
    v14 = "CPR(pdLevel)";
    v13 = 44;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v13,
      v14);
    goto LABEL_38;
  }
  *a1 = -1.0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Devices.Power.Battery", 0x1Du, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x180010EADLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_79cd72b6_9e5e_4452_bea6_dfcd541e597f, &v21);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_38;
    v14 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Devices_Power_Battery).Get(), pBatteryStatics.GetAddressOf()))";
    v13 = 47;
    goto LABEL_4;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 48LL))(v21, &v20);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_38;
    v14 = "CHR(pBatteryStatics->get_AggregateBattery(pAggregateBattery.GetAddressOf()))";
    v13 = 49;
    goto LABEL_4;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 56LL))(v20, &v19);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_38;
    v14 = "CHR(pAggregateBattery->GetReport(pBatteryReport.GetAddressOf()))";
    v13 = 51;
    goto LABEL_4;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 64LL))(v19, &v18);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_38;
    v14 = "CHR(pBatteryReport->get_FullChargeCapacityInMilliwattHours(pFullChargeCapacity.GetAddressOf()))";
    v13 = 53;
    goto LABEL_4;
  }
  if ( v18 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 48LL))(v18, &v15);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_38;
      v14 = "CHR(pFullChargeCapacity->get_Value(&iFullChargeCapacity))";
      v13 = 55;
      goto LABEL_4;
    }
    if ( v15 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 72LL))(v19, &v17);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_38;
        v14 = "CHR(pBatteryReport->get_RemainingCapacityInMilliwattHours(pRemainingCapacity.GetAddressOf()))";
        v13 = 58;
        goto LABEL_4;
      }
      if ( v17 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 48LL))(v17, &v16);
        if ( ActivationFactory >= 0 )
        {
          *a1 = (double)v16 / (double)v15;
          goto LABEL_38;
        }
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_38;
        v14 = "CHR(pRemainingCapacity->get_Value(&iRemainingCapacity))";
        v13 = 60;
        goto LABEL_4;
      }
      ActivationFactory = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          a2,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          59,
          "CBR(pRemainingCapacity != nullptr)");
    }
    else
    {
      ActivationFactory = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          a2,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          56,
          "CBR(iFullChargeCapacity != 0)");
    }
  }
  else
  {
    ActivationFactory = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        54,
        "CBR(pFullChargeCapacity != nullptr)");
  }
LABEL_38:
  v7 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180010adc  push    rbp
0x180010ade  push    rbx
0x180010adf  push    rsi
0x180010ae0  push    rdi
0x180010ae1  lea     rbp, [rsp-3Fh]
0x180010ae6  sub     rsp, 98h
0x180010aed  mov     rax, cs:__security_cookie
0x180010af4  xor     rax, rsp
0x180010af7  mov     [rbp+57h+var_30], rax
0x180010afb  mov     rdi, rcx
0x180010afe  xor     esi, esi
0x180010b00  mov     [rbp+57h+var_58], rsi
0x180010b04  mov     [rbp+57h+var_60], rsi
0x180010b08  mov     [rbp+57h+var_68], rsi
0x180010b0c  mov     [rbp+57h+var_70], rsi
0x180010b10  mov     [rbp+57h+var_78], rsi
0x180010b14  mov     [rbp+57h+var_80], esi
0x180010b17  mov     [rbp+57h+var_7C], esi
0x180010b1a  test    rcx, rcx
0x180010b1d  jnz     short loc_180010B59
0x180010b1f  mov     ebx, 80070057h
0x180010b24  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010b2b  jz      loc_180010E09
0x180010b31  lea     rax, aCprPdlevel; "CPR(pdLevel)"
0x180010b38  mov     [rsp+0B0h+var_88], rax
0x180010b3d  mov     dword ptr [rsp+0B0h+var_90], 52Ch
0x180010b45  mov     r8d, ebx
0x180010b48  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180010b4f  call    McTemplateU0dsqs_EventWriteTransfer
0x180010b54  jmp     loc_180010E09
0x180010b59  mov     rax, 0BFF0000000000000h
0x180010b63  mov     [rcx], rax
0x180010b66  mov     [rbp+57h+string], rsi
0x180010b6a  lea     r9, [rbp+57h+string]; string
0x180010b6e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010b72  mov     edx, 1Dh; length
0x180010b77  lea     rcx, ?RuntimeClass_Windows_Devices_Power_Battery@@3QBGB; "Windows.Devices.Power.Battery"
0x180010b7e  call    cs:__imp_WindowsCreateStringReference
0x180010b85  nop     dword ptr [rax+rax+00h]
0x180010b8a  test    eax, eax
0x180010b8c  js      loc_180010EA6
0x180010b92  lea     r8, [rbp+57h+var_58]
0x180010b96  lea     rdx, _GUID_79cd72b6_9e5e_4452_bea6_dfcd541e597f
0x180010b9d  mov     rcx, [rbp+57h+string]
0x180010ba1  call    cs:__imp_RoGetActivationFactory
0x180010ba8  nop     dword ptr [rax+rax+00h]
0x180010bad  mov     ebx, eax
0x180010baf  test    eax, eax
0x180010bb1  jns     short loc_180010BD9
0x180010bb3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010bba  jz      loc_180010E09
0x180010bc0  lea     rax, aChrGetactivati_0; "CHR(GetActivationFactory(HStringReferen"...
0x180010bc7  mov     [rsp+0B0h+var_88], rax
0x180010bcc  mov     dword ptr [rsp+0B0h+var_90], 52Fh
0x180010bd4  jmp     loc_180010B45
0x180010bd9  mov     rcx, [rbp+57h+var_58]
0x180010bdd  mov     rax, [rcx]
0x180010be0  lea     rdx, [rbp+57h+var_60]
0x180010be4  mov     rax, [rax+30h]
0x180010be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bed  mov     ebx, eax
0x180010bef  test    eax, eax
0x180010bf1  jns     short loc_180010C19
0x180010bf3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010bfa  jz      loc_180010E09
0x180010c00  lea     rax, aChrPbatterysta; "CHR(pBatteryStatics->get_AggregateBatte"...
0x180010c07  mov     [rsp+0B0h+var_88], rax
0x180010c0c  mov     dword ptr [rsp+0B0h+var_90], 531h
0x180010c14  jmp     loc_180010B45
0x180010c19  mov     rcx, [rbp+57h+var_60]
0x180010c1d  mov     rax, [rcx]
0x180010c20  lea     rdx, [rbp+57h+var_68]
0x180010c24  mov     rax, [rax+38h]
0x180010c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c2d  mov     ebx, eax
0x180010c2f  test    eax, eax
0x180010c31  jns     short loc_180010C59
0x180010c33  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010c3a  jz      loc_180010E09
0x180010c40  lea     rax, aChrPaggregateb; "CHR(pAggregateBattery->GetReport(pBatte"...
0x180010c47  mov     [rsp+0B0h+var_88], rax
0x180010c4c  mov     dword ptr [rsp+0B0h+var_90], 533h
0x180010c54  jmp     loc_180010B45
0x180010c59  mov     rcx, [rbp+57h+var_68]
0x180010c5d  mov     rax, [rcx]
0x180010c60  lea     rdx, [rbp+57h+var_70]
0x180010c64  mov     rax, [rax+40h]
0x180010c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c6d  mov     ebx, eax
0x180010c6f  test    eax, eax
0x180010c71  jns     short loc_180010C99
0x180010c73  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010c7a  jz      loc_180010E09
0x180010c80  lea     rax, aChrPbatteryrep_0; "CHR(pBatteryReport->get_FullChargeCapac"...
0x180010c87  mov     [rsp+0B0h+var_88], rax
0x180010c8c  mov     dword ptr [rsp+0B0h+var_90], 535h
0x180010c94  jmp     loc_180010B45
0x180010c99  cmp     [rbp+57h+var_70], rsi
0x180010c9d  jnz     short loc_180010CCE
0x180010c9f  mov     r8d, 8000FFFFh
0x180010ca5  mov     ebx, r8d
0x180010ca8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010caf  jz      loc_180010E09
0x180010cb5  lea     rax, aCbrPfullcharge; "CBR(pFullChargeCapacity != nullptr)"
0x180010cbc  mov     [rsp+0B0h+var_88], rax
0x180010cc1  mov     dword ptr [rsp+0B0h+var_90], 536h
0x180010cc9  jmp     loc_180010B48
0x180010cce  mov     rcx, [rbp+57h+var_70]
0x180010cd2  mov     rax, [rcx]
0x180010cd5  lea     rdx, [rbp+57h+var_80]
0x180010cd9  mov     rax, [rax+30h]
0x180010cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce2  mov     ebx, eax
0x180010ce4  test    eax, eax
0x180010ce6  jns     short loc_180010D0E
0x180010ce8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010cef  jz      loc_180010E09
0x180010cf5  lea     rax, aChrPfullcharge; "CHR(pFullChargeCapacity->get_Value(&iFu"...
0x180010cfc  mov     [rsp+0B0h+var_88], rax
0x180010d01  mov     dword ptr [rsp+0B0h+var_90], 537h
0x180010d09  jmp     loc_180010B45
0x180010d0e  cmp     [rbp+57h+var_80], esi
0x180010d11  jnz     short loc_180010D42
0x180010d13  mov     r8d, 8000FFFFh
0x180010d19  mov     ebx, r8d
0x180010d1c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010d23  jz      loc_180010E09
0x180010d29  lea     rax, aCbrIfullcharge; "CBR(iFullChargeCapacity != 0)"
0x180010d30  mov     [rsp+0B0h+var_88], rax
0x180010d35  mov     dword ptr [rsp+0B0h+var_90], 538h
0x180010d3d  jmp     loc_180010B48
0x180010d42  mov     rcx, [rbp+57h+var_68]
0x180010d46  mov     rax, [rcx]
0x180010d49  lea     rdx, [rbp+57h+var_78]
0x180010d4d  mov     rax, [rax+48h]
0x180010d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d56  mov     ebx, eax
0x180010d58  test    eax, eax
0x180010d5a  jns     short loc_180010D82
0x180010d5c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010d63  jz      loc_180010E09
0x180010d69  lea     rax, aChrPbatteryrep; "CHR(pBatteryReport->get_RemainingCapaci"...
0x180010d70  mov     [rsp+0B0h+var_88], rax
0x180010d75  mov     dword ptr [rsp+0B0h+var_90], 53Ah
0x180010d7d  jmp     loc_180010B45
0x180010d82  cmp     [rbp+57h+var_78], rsi
0x180010d86  jnz     short loc_180010DB3
0x180010d88  mov     r8d, 8000FFFFh
0x180010d8e  mov     ebx, r8d
0x180010d91  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010d98  jz      short loc_180010E09
0x180010d9a  lea     rax, aCbrPremainingc; "CBR(pRemainingCapacity != nullptr)"
0x180010da1  mov     [rsp+0B0h+var_88], rax
0x180010da6  mov     dword ptr [rsp+0B0h+var_90], 53Bh
0x180010dae  jmp     loc_180010B48
0x180010db3  mov     rcx, [rbp+57h+var_78]
0x180010db7  mov     rax, [rcx]
0x180010dba  lea     rdx, [rbp+57h+var_7C]
0x180010dbe  mov     rax, [rax+30h]
0x180010dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dc7  mov     ebx, eax
0x180010dc9  test    eax, eax
0x180010dcb  jns     short loc_180010DEF
0x180010dcd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010dd4  jz      short loc_180010E09
0x180010dd6  lea     rax, aChrPremainingc; "CHR(pRemainingCapacity->get_Value(&iRem"...
0x180010ddd  mov     [rsp+0B0h+var_88], rax
0x180010de2  mov     dword ptr [rsp+0B0h+var_90], 53Ch
0x180010dea  jmp     loc_180010B45
0x180010def  movd    xmm1, [rbp+57h+var_7C]
0x180010df4  cvtdq2pd xmm1, xmm1
0x180010df8  movd    xmm0, [rbp+57h+var_80]
0x180010dfd  cvtdq2pd xmm0, xmm0
0x180010e01  divsd   xmm1, xmm0
0x180010e05  movsd   qword ptr [rdi], xmm1
0x180010e09  mov     rcx, [rbp+57h+var_78]
0x180010e0d  test    rcx, rcx
0x180010e10  jz      short loc_180010E23
0x180010e12  mov     [rbp+57h+var_78], rsi
0x180010e16  mov     rax, [rcx]
0x180010e19  mov     rax, [rax+10h]
0x180010e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e22  nop
0x180010e23  mov     rcx, [rbp+57h+var_70]
0x180010e27  test    rcx, rcx
0x180010e2a  jz      short loc_180010E3D
0x180010e2c  mov     [rbp+57h+var_70], rsi
0x180010e30  mov     rax, [rcx]
0x180010e33  mov     rax, [rax+10h]
0x180010e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e3c  nop
0x180010e3d  mov     rcx, [rbp+57h+var_68]
0x180010e41  test    rcx, rcx
0x180010e44  jz      short loc_180010E57
0x180010e46  mov     [rbp+57h+var_68], rsi
0x180010e4a  mov     rax, [rcx]
0x180010e4d  mov     rax, [rax+10h]
0x180010e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e56  nop
0x180010e57  mov     rcx, [rbp+57h+var_60]
0x180010e5b  test    rcx, rcx
0x180010e5e  jz      short loc_180010E71
0x180010e60  mov     [rbp+57h+var_60], rsi
0x180010e64  mov     rax, [rcx]
0x180010e67  mov     rax, [rax+10h]
0x180010e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e70  nop
0x180010e71  mov     rcx, [rbp+57h+var_58]
0x180010e75  test    rcx, rcx
0x180010e78  jz      short loc_180010E8B
0x180010e7a  mov     [rbp+57h+var_58], rsi
0x180010e7e  mov     rax, [rcx]
0x180010e81  mov     rax, [rax+10h]
0x180010e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e8a  nop
0x180010e8b  mov     eax, ebx
0x180010e8d  mov     rcx, [rbp+57h+var_30]
0x180010e91  xor     rcx, rsp; StackCookie
0x180010e94  call    __security_check_cookie
0x180010e99  add     rsp, 98h
0x180010ea0  pop     rdi
0x180010ea1  pop     rsi
0x180010ea2  pop     rbx
0x180010ea3  pop     rbp
0x180010ea4  retn
0x180010ea6  mov     ecx, eax; this
0x180010ea8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

# MdmHttpWrapper::GetBatteryLevel(double *)

- ea: `0x180010740`
- end: `0x180010b05`
- name: `?GetBatteryLevel@MdmHttpWrapper@@CAJPEAN@Z`
- size: `965`
- prototype: `__int64 __fastcall(double *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ef34`

## callees

- `0x180001520`
- `0x180006548`
- `0x180010740`
- `0x180011414`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800107e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800107e2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800107ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800107ff`

## string_xrefs

- `0x1800107ac`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
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
    JUMPOUT(0x180010B04LL);
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
0x180010740  push    rbp
0x180010742  push    rbx
0x180010743  push    rsi
0x180010744  push    rdi
0x180010745  lea     rbp, [rsp-3Fh]
0x18001074a  sub     rsp, 98h
0x180010751  mov     rax, cs:__security_cookie
0x180010758  xor     rax, rsp
0x18001075b  mov     [rbp+57h+var_30], rax
0x18001075f  mov     rdi, rcx
0x180010762  xor     esi, esi
0x180010764  mov     [rbp+57h+var_58], rsi
0x180010768  mov     [rbp+57h+var_60], rsi
0x18001076c  mov     [rbp+57h+var_68], rsi
0x180010770  mov     [rbp+57h+var_70], rsi
0x180010774  mov     [rbp+57h+var_78], rsi
0x180010778  mov     [rbp+57h+var_80], esi
0x18001077b  mov     [rbp+57h+var_7C], esi
0x18001077e  test    rcx, rcx
0x180010781  jnz     short loc_1800107BD
0x180010783  mov     ebx, 80070057h
0x180010788  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001078f  jz      loc_180010A61
0x180010795  lea     rax, aCprPdlevel; "CPR(pdLevel)"
0x18001079c  mov     [rsp+0B0h+var_88], rax
0x1800107a1  mov     dword ptr [rsp+0B0h+var_90], 52Ch
0x1800107a9  mov     r8d, ebx
0x1800107ac  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800107b3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800107b8  jmp     loc_180010A61
0x1800107bd  mov     rax, 0BFF0000000000000h
0x1800107c7  mov     [rcx], rax
0x1800107ca  mov     [rbp+57h+string], rsi
0x1800107ce  lea     r9, [rbp+57h+string]; string
0x1800107d2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800107d6  mov     edx, 1Dh; length
0x1800107db  lea     rcx, ?RuntimeClass_Windows_Devices_Power_Battery@@3QBGB; "Windows.Devices.Power.Battery"
0x1800107e2  call    cs:__imp_WindowsCreateStringReference
0x1800107e8  test    eax, eax
0x1800107ea  js      loc_180010AFD
0x1800107f0  lea     r8, [rbp+57h+var_58]
0x1800107f4  lea     rdx, _GUID_79cd72b6_9e5e_4452_bea6_dfcd541e597f
0x1800107fb  mov     rcx, [rbp+57h+string]
0x1800107ff  call    cs:__imp_RoGetActivationFactory
0x180010805  mov     ebx, eax
0x180010807  test    eax, eax
0x180010809  jns     short loc_180010831
0x18001080b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010812  jz      loc_180010A61
0x180010818  lea     rax, aChrGetactivati_0; "CHR(GetActivationFactory(HStringReferen"...
0x18001081f  mov     [rsp+0B0h+var_88], rax
0x180010824  mov     dword ptr [rsp+0B0h+var_90], 52Fh
0x18001082c  jmp     loc_1800107A9
0x180010831  mov     rcx, [rbp+57h+var_58]
0x180010835  mov     rax, [rcx]
0x180010838  lea     rdx, [rbp+57h+var_60]
0x18001083c  mov     rax, [rax+30h]
0x180010840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010845  mov     ebx, eax
0x180010847  test    eax, eax
0x180010849  jns     short loc_180010871
0x18001084b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010852  jz      loc_180010A61
0x180010858  lea     rax, aChrPbatterysta; "CHR(pBatteryStatics->get_AggregateBatte"...
0x18001085f  mov     [rsp+0B0h+var_88], rax
0x180010864  mov     dword ptr [rsp+0B0h+var_90], 531h
0x18001086c  jmp     loc_1800107A9
0x180010871  mov     rcx, [rbp+57h+var_60]
0x180010875  mov     rax, [rcx]
0x180010878  lea     rdx, [rbp+57h+var_68]
0x18001087c  mov     rax, [rax+38h]
0x180010880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010885  mov     ebx, eax
0x180010887  test    eax, eax
0x180010889  jns     short loc_1800108B1
0x18001088b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010892  jz      loc_180010A61
0x180010898  lea     rax, aChrPaggregateb; "CHR(pAggregateBattery->GetReport(pBatte"...
0x18001089f  mov     [rsp+0B0h+var_88], rax
0x1800108a4  mov     dword ptr [rsp+0B0h+var_90], 533h
0x1800108ac  jmp     loc_1800107A9
0x1800108b1  mov     rcx, [rbp+57h+var_68]
0x1800108b5  mov     rax, [rcx]
0x1800108b8  lea     rdx, [rbp+57h+var_70]
0x1800108bc  mov     rax, [rax+40h]
0x1800108c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108c5  mov     ebx, eax
0x1800108c7  test    eax, eax
0x1800108c9  jns     short loc_1800108F1
0x1800108cb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800108d2  jz      loc_180010A61
0x1800108d8  lea     rax, aChrPbatteryrep_0; "CHR(pBatteryReport->get_FullChargeCapac"...
0x1800108df  mov     [rsp+0B0h+var_88], rax
0x1800108e4  mov     dword ptr [rsp+0B0h+var_90], 535h
0x1800108ec  jmp     loc_1800107A9
0x1800108f1  cmp     [rbp+57h+var_70], rsi
0x1800108f5  jnz     short loc_180010926
0x1800108f7  mov     r8d, 8000FFFFh
0x1800108fd  mov     ebx, r8d
0x180010900  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010907  jz      loc_180010A61
0x18001090d  lea     rax, aCbrPfullcharge; "CBR(pFullChargeCapacity != nullptr)"
0x180010914  mov     [rsp+0B0h+var_88], rax
0x180010919  mov     dword ptr [rsp+0B0h+var_90], 536h
0x180010921  jmp     loc_1800107AC
0x180010926  mov     rcx, [rbp+57h+var_70]
0x18001092a  mov     rax, [rcx]
0x18001092d  lea     rdx, [rbp+57h+var_80]
0x180010931  mov     rax, [rax+30h]
0x180010935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001093a  mov     ebx, eax
0x18001093c  test    eax, eax
0x18001093e  jns     short loc_180010966
0x180010940  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010947  jz      loc_180010A61
0x18001094d  lea     rax, aChrPfullcharge; "CHR(pFullChargeCapacity->get_Value(&iFu"...
0x180010954  mov     [rsp+0B0h+var_88], rax
0x180010959  mov     dword ptr [rsp+0B0h+var_90], 537h
0x180010961  jmp     loc_1800107A9
0x180010966  cmp     [rbp+57h+var_80], esi
0x180010969  jnz     short loc_18001099A
0x18001096b  mov     r8d, 8000FFFFh
0x180010971  mov     ebx, r8d
0x180010974  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001097b  jz      loc_180010A61
0x180010981  lea     rax, aCbrIfullcharge; "CBR(iFullChargeCapacity != 0)"
0x180010988  mov     [rsp+0B0h+var_88], rax
0x18001098d  mov     dword ptr [rsp+0B0h+var_90], 538h
0x180010995  jmp     loc_1800107AC
0x18001099a  mov     rcx, [rbp+57h+var_68]
0x18001099e  mov     rax, [rcx]
0x1800109a1  lea     rdx, [rbp+57h+var_78]
0x1800109a5  mov     rax, [rax+48h]
0x1800109a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ae  mov     ebx, eax
0x1800109b0  test    eax, eax
0x1800109b2  jns     short loc_1800109DA
0x1800109b4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800109bb  jz      loc_180010A61
0x1800109c1  lea     rax, aChrPbatteryrep; "CHR(pBatteryReport->get_RemainingCapaci"...
0x1800109c8  mov     [rsp+0B0h+var_88], rax
0x1800109cd  mov     dword ptr [rsp+0B0h+var_90], 53Ah
0x1800109d5  jmp     loc_1800107A9
0x1800109da  cmp     [rbp+57h+var_78], rsi
0x1800109de  jnz     short loc_180010A0B
0x1800109e0  mov     r8d, 8000FFFFh
0x1800109e6  mov     ebx, r8d
0x1800109e9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800109f0  jz      short loc_180010A61
0x1800109f2  lea     rax, aCbrPremainingc; "CBR(pRemainingCapacity != nullptr)"
0x1800109f9  mov     [rsp+0B0h+var_88], rax
0x1800109fe  mov     dword ptr [rsp+0B0h+var_90], 53Bh
0x180010a06  jmp     loc_1800107AC
0x180010a0b  mov     rcx, [rbp+57h+var_78]
0x180010a0f  mov     rax, [rcx]
0x180010a12  lea     rdx, [rbp+57h+var_7C]
0x180010a16  mov     rax, [rax+30h]
0x180010a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a1f  mov     ebx, eax
0x180010a21  test    eax, eax
0x180010a23  jns     short loc_180010A47
0x180010a25  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010a2c  jz      short loc_180010A61
0x180010a2e  lea     rax, aChrPremainingc; "CHR(pRemainingCapacity->get_Value(&iRem"...
0x180010a35  mov     [rsp+0B0h+var_88], rax
0x180010a3a  mov     dword ptr [rsp+0B0h+var_90], 53Ch
0x180010a42  jmp     loc_1800107A9
0x180010a47  movd    xmm1, [rbp+57h+var_7C]
0x180010a4c  cvtdq2pd xmm1, xmm1
0x180010a50  movd    xmm0, [rbp+57h+var_80]
0x180010a55  cvtdq2pd xmm0, xmm0
0x180010a59  divsd   xmm1, xmm0
0x180010a5d  movsd   qword ptr [rdi], xmm1
0x180010a61  mov     rcx, [rbp+57h+var_78]
0x180010a65  test    rcx, rcx
0x180010a68  jz      short loc_180010A7B
0x180010a6a  mov     [rbp+57h+var_78], rsi
0x180010a6e  mov     rax, [rcx]
0x180010a71  mov     rax, [rax+10h]
0x180010a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a7a  nop
0x180010a7b  mov     rcx, [rbp+57h+var_70]
0x180010a7f  test    rcx, rcx
0x180010a82  jz      short loc_180010A95
0x180010a84  mov     [rbp+57h+var_70], rsi
0x180010a88  mov     rax, [rcx]
0x180010a8b  mov     rax, [rax+10h]
0x180010a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a94  nop
0x180010a95  mov     rcx, [rbp+57h+var_68]
0x180010a99  test    rcx, rcx
0x180010a9c  jz      short loc_180010AAF
0x180010a9e  mov     [rbp+57h+var_68], rsi
0x180010aa2  mov     rax, [rcx]
0x180010aa5  mov     rax, [rax+10h]
0x180010aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aae  nop
0x180010aaf  mov     rcx, [rbp+57h+var_60]
0x180010ab3  test    rcx, rcx
0x180010ab6  jz      short loc_180010AC9
0x180010ab8  mov     [rbp+57h+var_60], rsi
0x180010abc  mov     rax, [rcx]
0x180010abf  mov     rax, [rax+10h]
0x180010ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac8  nop
0x180010ac9  mov     rcx, [rbp+57h+var_58]
0x180010acd  test    rcx, rcx
0x180010ad0  jz      short loc_180010AE3
0x180010ad2  mov     [rbp+57h+var_58], rsi
0x180010ad6  mov     rax, [rcx]
0x180010ad9  mov     rax, [rax+10h]
0x180010add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ae2  nop
0x180010ae3  mov     eax, ebx
0x180010ae5  mov     rcx, [rbp+57h+var_30]
0x180010ae9  xor     rcx, rsp; StackCookie
0x180010aec  call    __security_check_cookie
0x180010af1  add     rsp, 98h
0x180010af8  pop     rdi
0x180010af9  pop     rsi
0x180010afa  pop     rbx
0x180010afb  pop     rbp
0x180010afc  retn
0x180010afd  mov     ecx, eax; this
0x180010aff  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

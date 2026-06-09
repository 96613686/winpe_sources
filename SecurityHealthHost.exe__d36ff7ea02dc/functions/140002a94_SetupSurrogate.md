# SetupSurrogate

- ea: `0x140002a94`
- end: `0x140002e78`
- name: `SetupSurrogate`
- size: `996`
- prototype: `__int64 __fastcall(unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140003188`

## callees

- `0x1400015f0`
- `0x14000285c`
- `0x140002a94`
- `0x140003040`
- `0x140004200`
- `0x14000d82c`
- `0x14000daa8`
- `0x14000ec30`
- `0x14000eca8`
- `0x140011010`

## import_xrefs

- `ole32!CoUninitialize` at `0x140002b70`
- `ole32!CoUninitialize` at `0x140002e4b`
- `ole32!CoUninitialize` at `0x140002b70`
- `ole32!CoUninitialize` at `0x140002e4b`
- `ole32!CoInitializeSecurity` at `0x140002ce4`
- `ole32!CoInitializeSecurity` at `0x140002ce4`
- `ole32!CoRegisterSurrogate` at `0x140002d73`
- `ole32!CoRegisterSurrogate` at `0x140002d73`
- `ole32!CLSIDFromString` at `0x140002da6`
- `ole32!CLSIDFromString` at `0x140002da6`
- `KERNEL32!CloseHandle` at `0x140002acf`
- `KERNEL32!CloseHandle` at `0x140002acf`

## pseudocode

```c
__int64 __fastcall SetupSurrogate(unsigned __int16 *a1, void **a2)
{
  int Event; // eax
  struct CommonUtil::MpCoLibraryType **v4; // rdx
  void *v5; // r8
  int AppIDFromClsid; // esi
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  __int64 v13; // r8
  char *v14; // r9
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  LPVOID ppv; // [rsp+50h] [rbp+7h] BYREF
  __int64 v18; // [rsp+58h] [rbp+Fh] BYREF
  LPSURROGATE pSurrogate; // [rsp+60h] [rbp+17h] BYREF
  GUID pSecDesc; // [rsp+68h] [rbp+1Fh] BYREF
  GUID pclsid; // [rsp+78h] [rbp+2Fh] BYREF

  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  Event = CommonUtil::UtilCreateEvent((CommonUtil *)&hObject, a2);
  AppIDFromClsid = Event;
  if ( Event < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
        (unsigned int)Event);
    return (unsigned int)AppIDFromClsid;
  }
  v18 = 0;
  v8 = CommonUtil::MpSmartCoInitialize((CommonUtil *)&v18, v4, v5);
  AppIDFromClsid = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
        (unsigned int)v8);
LABEL_12:
    if ( v18 )
      CoUninitialize();
    return (unsigned int)AppIDFromClsid;
  }
  ppv = 0;
  AppIDFromClsid = CommonUtil::UtilCoCreateInstanceImpl(
                     &ppv,
                     &CLSID_GlobalOptions,
                     &GUID_0000015b_0000_0000_c000_000000000046,
                     1u);
  if ( AppIDFromClsid < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 16;
LABEL_18:
      WPP_SF_d(v9[2], v10, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids, (unsigned int)AppIDFromClsid);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  if ( v11 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
      (unsigned int)v11);
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 4, 264);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
      (unsigned int)v12);
  }
  pSecDesc = 0;
  AppIDFromClsid = GetAppIDFromClsid(a1, &pSecDesc, v13, v14);
  if ( AppIDFromClsid < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 19;
      goto LABEL_18;
    }
LABEL_19:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_12;
  }
  AppIDFromClsid = CoInitializeSecurity(&pSecDesc, -1, 0, 0, 0, 0, 0, 8u, 0);
  if ( AppIDFromClsid < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 20;
      goto LABEL_18;
    }
    goto LABEL_19;
  }
  pSurrogate = 0;
  AppIDFromClsid = CSurrogate_CreateInstance(&pSurrogate);
  if ( AppIDFromClsid < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 21;
LABEL_41:
      WPP_SF_d(v15[2], v16, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids, (unsigned int)AppIDFromClsid);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  AppIDFromClsid = CoRegisterSurrogate(pSurrogate);
  if ( AppIDFromClsid < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 22;
      goto LABEL_41;
    }
LABEL_42:
    if ( pSurrogate )
      ((void (__fastcall *)(LPSURROGATE))pSurrogate->lpVtbl->Release)(pSurrogate);
    goto LABEL_19;
  }
  pclsid = 0;
  AppIDFromClsid = CLSIDFromString(a1, &pclsid);
  if ( AppIDFromClsid < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 23;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  AppIDFromClsid = ((__int64 (__fastcall *)(LPSURROGATE, GUID *))pSurrogate->lpVtbl->LoadDllServer)(pSurrogate, &pclsid);
  if ( AppIDFromClsid < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 24;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  CommonUtil::UtilWaitForSingleObject((CommonUtil *)hObject, (void *)0xFFFFFFFFLL);
  if ( pSurrogate )
    ((void (__fastcall *)(LPSURROGATE))pSurrogate->lpVtbl->Release)(pSurrogate);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v18 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140002a94  mov     [rsp-8+arg_8], rbx
0x140002a99  mov     [rsp-8+arg_10], rsi
0x140002a9e  push    rbp
0x140002a9f  push    r14
0x140002aa1  push    r15
0x140002aa3  lea     rbp, [rsp-47h]
0x140002aa8  sub     rsp, 90h
0x140002aaf  mov     rax, cs:__security_cookie
0x140002ab6  xor     rax, rsp
0x140002ab9  mov     [rbp+57h+var_18], rax
0x140002abd  mov     r14, rcx
0x140002ac0  xor     r15d, r15d
0x140002ac3  mov     rcx, cs:hObject; hObject
0x140002aca  test    rcx, rcx
0x140002acd  jz      short loc_140002ADC
0x140002acf  call    cs:__imp_CloseHandle
0x140002ad5  mov     cs:hObject, r15
0x140002adc  lea     rcx, hObject; this
0x140002ae3  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)
0x140002ae8  mov     esi, eax
0x140002aea  test    eax, eax
0x140002aec  jns     short loc_140002B26
0x140002aee  mov     rcx, cs:WPP_GLOBAL_Control
0x140002af5  lea     rbx, WPP_GLOBAL_Control
0x140002afc  cmp     rcx, rbx
0x140002aff  jz      short loc_140002B1F
0x140002b01  test    byte ptr [rcx+1Ch], 1
0x140002b05  jz      short loc_140002B1F
0x140002b07  mov     rcx, [rcx+10h]
0x140002b0b  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x140002b12  mov     edx, 0Eh
0x140002b17  mov     r9d, eax
0x140002b1a  call    WPP_SF_d
0x140002b1f  mov     eax, esi
0x140002b21  jmp     loc_140002E53
0x140002b26  lea     rcx, [rbp+57h+var_48]; this
0x140002b2a  mov     [rbp+57h+var_48], r15
0x140002b2e  call    ?MpSmartCoInitialize@CommonUtil@@YAJPEAPEAUMpCoLibraryType@1@PEAXK@Z; CommonUtil::MpSmartCoInitialize(CommonUtil::MpCoLibraryType * *,void *,ulong)
0x140002b33  mov     esi, eax
0x140002b35  test    eax, eax
0x140002b37  jns     short loc_140002B78
0x140002b39  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b40  lea     rbx, WPP_GLOBAL_Control
0x140002b47  cmp     rcx, rbx
0x140002b4a  jz      short loc_140002B6A
0x140002b4c  test    byte ptr [rcx+1Ch], 1
0x140002b50  jz      short loc_140002B6A
0x140002b52  mov     rcx, [rcx+10h]
0x140002b56  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x140002b5d  mov     edx, 0Fh
0x140002b62  mov     r9d, eax
0x140002b65  call    WPP_SF_d
0x140002b6a  cmp     [rbp+57h+var_48], r15
0x140002b6e  jz      short loc_140002B1F
0x140002b70  call    cs:__imp_CoUninitialize
0x140002b76  jmp     short loc_140002B1F
0x140002b78  mov     r9d, 1; dwClsContext
0x140002b7e  mov     [rbp+57h+ppv], r15
0x140002b82  lea     r8, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x140002b89  lea     rdx, CLSID_GlobalOptions; rclsid
0x140002b90  lea     rcx, [rbp+57h+ppv]; ppv
0x140002b94  call    ?UtilCoCreateInstanceImpl@CommonUtil@@YAJPEAPEAXAEBU_GUID@@1KPEAUIUnknown@@@Z; CommonUtil::UtilCoCreateInstanceImpl(void * *,_GUID const &,_GUID const &,ulong,IUnknown *)
0x140002b99  mov     esi, eax
0x140002b9b  test    eax, eax
0x140002b9d  jns     short loc_140002BE7
0x140002b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ba6  lea     rbx, WPP_GLOBAL_Control
0x140002bad  cmp     rcx, rbx
0x140002bb0  jz      short loc_140002BD0
0x140002bb2  test    byte ptr [rcx+1Ch], 1
0x140002bb6  jz      short loc_140002BD0
0x140002bb8  mov     edx, 10h
0x140002bbd  mov     rcx, [rcx+10h]
0x140002bc1  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x140002bc8  mov     r9d, esi
0x140002bcb  call    WPP_SF_d
0x140002bd0  mov     rcx, [rbp+57h+ppv]
0x140002bd4  test    rcx, rcx
0x140002bd7  jz      short loc_140002B6A
0x140002bd9  mov     rax, [rcx]
0x140002bdc  mov     rax, [rax+10h]
0x140002be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002be5  jmp     short loc_140002B6A
0x140002be7  mov     rcx, [rbp+57h+ppv]
0x140002beb  mov     edx, 5
0x140002bf0  mov     rax, [rcx]
0x140002bf3  lea     r8d, [rdx-4]
0x140002bf7  mov     rax, [rax+18h]
0x140002bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c00  lea     rbx, WPP_GLOBAL_Control
0x140002c07  test    eax, eax
0x140002c09  jns     short loc_140002C35
0x140002c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c12  cmp     rcx, rbx
0x140002c15  jz      short loc_140002C35
0x140002c17  test    byte ptr [rcx+1Ch], 1
0x140002c1b  jz      short loc_140002C35
0x140002c1d  mov     rcx, [rcx+10h]
0x140002c21  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x140002c28  mov     edx, 11h
0x140002c2d  mov     r9d, eax
0x140002c30  call    WPP_SF_d
0x140002c35  mov     rcx, [rbp+57h+ppv]
0x140002c39  mov     edx, 4
0x140002c3e  mov     r8d, 108h
0x140002c44  mov     rax, [rcx]
0x140002c47  mov     rax, [rax+18h]
0x140002c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c50  test    eax, eax
0x140002c52  jns     short loc_140002C7E
0x140002c54  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c5b  cmp     rcx, rbx
0x140002c5e  jz      short loc_140002C7E
0x140002c60  test    byte ptr [rcx+1Ch], 1
0x140002c64  jz      short loc_140002C7E
0x140002c66  mov     rcx, [rcx+10h]
0x140002c6a  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x140002c71  mov     edx, 12h
0x140002c76  mov     r9d, eax
0x140002c79  call    WPP_SF_d
0x140002c7e  xorps   xmm0, xmm0
0x140002c81  lea     rdx, [rbp+57h+pSecDesc]; lpiid
0x140002c85  mov     rcx, r14; unsigned __int16 *
0x140002c88  movups  [rbp+57h+pSecDesc], xmm0
0x140002c8c  call    GetAppIDFromClsid
0x140002c91  mov     esi, eax
0x140002c93  test    eax, eax
0x140002c95  jns     short loc_140002CBB
0x140002c97  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c9e  cmp     rcx, rbx
0x140002ca1  jz      loc_140002BD0
0x140002ca7  test    byte ptr [rcx+1Ch], 1
0x140002cab  jz      loc_140002BD0
0x140002cb1  mov     edx, 13h
0x140002cb6  jmp     loc_140002BBD
0x140002cbb  mov     [rsp+0A0h+pReserved3], r15; pReserved3
0x140002cc0  lea     rcx, [rbp+57h+pSecDesc]; pSecDesc
0x140002cc4  mov     [rsp+0A0h+dwCapabilities], 8; dwCapabilities
0x140002ccc  xor     r9d, r9d; pReserved1
0x140002ccf  mov     [rsp+0A0h+pAuthList], r15; pAuthList
0x140002cd4  xor     r8d, r8d; asAuthSvc
0x140002cd7  mov     [rsp+0A0h+dwImpLevel], r15d; dwImpLevel
0x140002cdc  or      edx, 0FFFFFFFFh; cAuthSvc
0x140002cdf  mov     [rsp+0A0h+dwAuthnLevel], r15d; dwAuthnLevel
0x140002ce4  call    cs:__imp_CoInitializeSecurity
0x140002cea  mov     esi, eax
0x140002cec  test    eax, eax
0x140002cee  jns     short loc_140002D14
0x140002cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140002cf7  cmp     rcx, rbx
0x140002cfa  jz      loc_140002BD0
0x140002d00  test    byte ptr [rcx+1Ch], 1
0x140002d04  jz      loc_140002BD0
0x140002d0a  mov     edx, 14h
0x140002d0f  jmp     loc_140002BBD
0x140002d14  lea     rcx, [rbp+57h+pSurrogate]; struct ISurrogate **
0x140002d18  mov     [rbp+57h+pSurrogate], r15
0x140002d1c  call    ?CSurrogate_CreateInstance@@YAJPEAPEAUISurrogate@@@Z; CSurrogate_CreateInstance(ISurrogate * *)
0x140002d21  mov     esi, eax
0x140002d23  test    eax, eax
0x140002d25  jns     short loc_140002D6F
0x140002d27  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d2e  cmp     rcx, rbx
0x140002d31  jz      short loc_140002D51
0x140002d33  test    byte ptr [rcx+1Ch], 1
0x140002d37  jz      short loc_140002D51
0x140002d39  mov     edx, 15h
0x140002d3e  mov     rcx, [rcx+10h]
0x140002d42  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x140002d49  mov     r9d, esi
0x140002d4c  call    WPP_SF_d
0x140002d51  mov     rcx, [rbp+57h+pSurrogate]
0x140002d55  test    rcx, rcx
0x140002d58  jz      loc_140002BD0
0x140002d5e  mov     rax, [rcx]
0x140002d61  mov     rax, [rax+10h]
0x140002d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d6a  jmp     loc_140002BD0
0x140002d6f  mov     rcx, [rbp+57h+pSurrogate]; pSurrogate
0x140002d73  call    cs:__imp_CoRegisterSurrogate
0x140002d79  mov     esi, eax
0x140002d7b  test    eax, eax
0x140002d7d  jns     short loc_140002D98
0x140002d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d86  cmp     rcx, rbx
0x140002d89  jz      short loc_140002D51
0x140002d8b  test    byte ptr [rcx+1Ch], 1
0x140002d8f  jz      short loc_140002D51
0x140002d91  mov     edx, 16h
0x140002d96  jmp     short loc_140002D3E
0x140002d98  xorps   xmm0, xmm0
0x140002d9b  lea     rdx, [rbp+57h+pclsid]; pclsid
0x140002d9f  mov     rcx, r14; lpsz
0x140002da2  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140002da6  call    cs:__imp_CLSIDFromString
0x140002dac  mov     esi, eax
0x140002dae  test    eax, eax
0x140002db0  jns     short loc_140002DCE
0x140002db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140002db9  cmp     rcx, rbx
0x140002dbc  jz      short loc_140002D51
0x140002dbe  test    byte ptr [rcx+1Ch], 1
0x140002dc2  jz      short loc_140002D51
0x140002dc4  mov     edx, 17h
0x140002dc9  jmp     loc_140002D3E
0x140002dce  mov     rcx, [rbp+57h+pSurrogate]
0x140002dd2  lea     rdx, [rbp+57h+pclsid]
0x140002dd6  mov     rax, [rcx]
0x140002dd9  mov     rax, [rax+18h]
0x140002ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002de2  mov     esi, eax
0x140002de4  test    eax, eax
0x140002de6  jns     short loc_140002E0C
0x140002de8  mov     rcx, cs:WPP_GLOBAL_Control
0x140002def  cmp     rcx, rbx
0x140002df2  jz      loc_140002D51
0x140002df8  test    byte ptr [rcx+1Ch], 1
0x140002dfc  jz      loc_140002D51
0x140002e02  mov     edx, 18h
0x140002e07  jmp     loc_140002D3E
0x140002e0c  mov     rcx, cs:hObject; this
0x140002e13  or      edx, 0FFFFFFFFh; void *
0x140002e16  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x140002e1b  mov     rcx, [rbp+57h+pSurrogate]
0x140002e1f  test    rcx, rcx
0x140002e22  jz      short loc_140002E30
0x140002e24  mov     rax, [rcx]
0x140002e27  mov     rax, [rax+10h]
0x140002e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e30  mov     rcx, [rbp+57h+ppv]
0x140002e34  test    rcx, rcx
0x140002e37  jz      short loc_140002E45
0x140002e39  mov     rax, [rcx]
0x140002e3c  mov     rax, [rax+10h]
0x140002e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e45  cmp     [rbp+57h+var_48], r15
0x140002e49  jz      short loc_140002E51
0x140002e4b  call    cs:__imp_CoUninitialize
0x140002e51  xor     eax, eax
0x140002e53  mov     rcx, [rbp+57h+var_18]
0x140002e57  xor     rcx, rsp; StackCookie
0x140002e5a  call    __security_check_cookie
0x140002e5f  lea     r11, [rsp+0A0h+var_10]
0x140002e67  mov     rbx, [r11+28h]
0x140002e6b  mov     rsi, [r11+30h]
0x140002e6f  mov     rsp, r11
0x140002e72  pop     r15
0x140002e74  pop     r14
0x140002e76  pop     rbp
0x140002e77  retn
```

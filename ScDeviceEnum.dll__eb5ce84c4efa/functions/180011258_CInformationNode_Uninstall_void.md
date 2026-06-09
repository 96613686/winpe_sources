# CInformationNode::_Uninstall(void)

- ea: `0x180011258`
- end: `0x1800115f5`
- name: `?_Uninstall@CInformationNode@@AEAAJXZ`
- size: `925`
- prototype: `__int64 __fastcall(CInformationNode *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010b54`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x18000d8d0`
- `0x18001008c`
- `0x180010350`
- `0x180011258`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800113c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800114b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011573`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800115c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800113c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800114b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011573`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800115c2`
- `DEVOBJ!DevObjUninstallDevice` at `0x1800114ce`
- `DEVOBJ!DevObjUninstallDevice` at `0x1800114ce`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180011300`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180011300`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180011404`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180011404`

## string_xrefs

- `0x18001127c`: `CInformationNode::_Uninstall`

## pseudocode

```c
__int64 __fastcall CInformationNode::_Uninstall(CInformationNode *this)
{
  _QWORD *v2; // rbx
  unsigned int v3; // edi
  __int64 DeviceInfoList; // rax
  signed int LastError; // eax
  __int64 v6; // rcx
  int v7; // eax
  _QWORD *v8; // rdx
  signed int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  signed int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // [rsp+30h] [rbp-79h] BYREF
  void **v19; // [rsp+38h] [rbp-71h] BYREF
  __int64 v20; // [rsp+40h] [rbp-69h]
  int v21; // [rsp+48h] [rbp-61h] BYREF
  int v22; // [rsp+4Ch] [rbp-5Dh] BYREF
  int v23; // [rsp+50h] [rbp-59h] BYREF
  _QWORD *v24; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v25[3]; // [rsp+60h] [rbp-49h] BYREF
  _OWORD v26[3]; // [rsp+78h] [rbp-31h] BYREF
  char v27[32]; // [rsp+A8h] [rbp-1h] BYREF

  v25[0] = v27;
  v18 = 0;
  v25[1] = &v21;
  strcpy(v27, "CInformationNode::_Uninstall");
  v25[2] = &v18;
  v21 = 0;
  lambda_45cc125f5585310d98afbd4f866fb652_::operator()(v25);
  v2 = (_QWORD *)((char *)this + 40);
  v24 = v25;
  v21 = 1;
  if ( !*v2 )
  {
    v3 = -2147467261;
    v18 = -2147467261;
LABEL_42:
    WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652____::_WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652____(&v24);
    return v3;
  }
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v20 = DeviceInfoList;
  v19 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v18 = LastError;
    WppTraceIndent(v6, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids,
        (_DWORD)WPP_pszIndent,
        v18);
    }
    v3 = v18;
    v19 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
    if ( v20 == -1 )
      goto LABEL_42;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v19) )
    {
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      RaiseException(v7, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_41;
  }
  v8 = (_QWORD *)*v2;
  v22 = 1;
  memset(v26, 0, sizeof(v26));
  LODWORD(v26[0]) = 48;
  if ( v8[3] < 8u )
    v8 = v2;
  if ( !(unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, *v8, 0, &v22, v26) )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v18 = v9;
    WppTraceIndent(v10, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids,
        (_DWORD)WPP_pszIndent,
        v18);
    }
    v3 = v18;
    v19 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
    if ( v20 == -1 )
      goto LABEL_42;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v19) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      RaiseException(v11, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_41;
  }
  v23 = 0;
  if ( !(unsigned int)DevObjUninstallDevice(v20, v26, 0, &v23) )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v18 = v12;
    WppTraceIndent(v13, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids,
        (_DWORD)WPP_pszIndent,
        v18);
    }
    v3 = v18;
    v19 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
    if ( v20 == -1 )
      goto LABEL_42;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v19) )
    {
      v14 = GetLastError();
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      RaiseException(v14, 1u, 0, 0);
      __debugbreak();
    }
LABEL_41:
    v20 = -1;
    goto LABEL_42;
  }
  v16 = v18;
  v19 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
  if ( v20 != -1 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v19) )
    {
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      RaiseException(v17, 1u, 0, 0);
      __debugbreak();
    }
    v20 = -1;
  }
  WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652____::_WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652____(&v24);
  return v16;
}

```

## disassembly

```asm
0x180011258  push    rbp
0x18001125a  push    rbx
0x18001125b  push    rdi
0x18001125c  push    r12
0x18001125e  push    r14
0x180011260  push    r15
0x180011262  lea     rbp, [rsp-2Fh]
0x180011267  sub     rsp, 0D8h
0x18001126e  mov     rax, cs:__security_cookie
0x180011275  xor     rax, rsp
0x180011278  mov     [rbp+57h+var_38], rax
0x18001127c  movups  xmm0, xmmword ptr cs:aCinformationno_6; "CInformationNode::_Uninstall"
0x180011283  lea     rax, [rbp+57h+var_58]
0x180011287  mov     rbx, rcx
0x18001128a  movups  xmm1, xmmword ptr cs:aCinformationno_6+0Dh; "ode::_Uninstall"
0x180011291  mov     [rbp+57h+var_A0], rax
0x180011295  lea     rcx, [rbp+57h+var_A0]
0x180011299  lea     rax, [rbp+57h+var_B8]
0x18001129d  mov     [rbp+57h+var_D0], 0
0x1800112a4  mov     [rbp+57h+var_98], rax
0x1800112a8  lea     rax, [rbp+57h+var_D0]
0x1800112ac  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800112b0  mov     [rbp+57h+var_90], rax
0x1800112b4  mov     [rbp+57h+var_B8], 0
0x1800112bb  movups  xmmword ptr [rbp+57h+var_58+0Dh], xmm1
0x1800112bf  call    _lambda_45cc125f5585310d98afbd4f866fb652___operator__
0x1800112c4  add     rbx, 28h ; '('
0x1800112c8  lea     rax, [rbp+57h+var_A0]
0x1800112cc  mov     r15d, 1
0x1800112d2  mov     [rbp+57h+var_A8], rax
0x1800112d6  mov     [rbp+57h+var_B8], r15d
0x1800112da  cmp     qword ptr [rbx], 0
0x1800112de  jnz     short loc_1800112ED
0x1800112e0  mov     edi, 80004003h
0x1800112e5  mov     [rbp+57h+var_D0], edi
0x1800112e8  jmp     loc_18001157E
0x1800112ed  xor     r9d, r9d
0x1800112f0  mov     [rsp+100h+var_E0], 0
0x1800112f9  xor     r8d, r8d
0x1800112fc  xor     edx, edx
0x1800112fe  xor     ecx, ecx
0x180011300  call    cs:__imp_DevObjCreateDeviceInfoList
0x180011306  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001130a  lea     r12, ??_7?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable'
0x180011311  mov     [rbp+57h+var_C0], rax
0x180011315  mov     [rbp+57h+var_C8], r12
0x180011319  cmp     rax, r14
0x18001131c  jnz     loc_1800113C8
0x180011322  call    cs:__imp_GetLastError
0x180011328  mov     ebx, 80070000h
0x18001132d  test    eax, eax
0x18001132f  jle     short loc_180011336
0x180011331  movzx   eax, ax
0x180011334  or      eax, ebx
0x180011336  mov     edx, 2
0x18001133b  mov     [rbp+57h+var_D0], eax
0x18001133e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180011343  mov     rcx, cs:WPP_GLOBAL_Control
0x18001134a  lea     rax, WPP_GLOBAL_Control
0x180011351  cmp     rcx, rax
0x180011354  jz      short loc_180011385
0x180011356  test    [rcx+1Ch], r15b
0x18001135a  jz      short loc_180011385
0x18001135c  cmp     byte ptr [rcx+19h], 2
0x180011360  jb      short loc_180011385
0x180011362  mov     eax, [rbp+57h+var_D0]
0x180011365  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x18001136c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180011373  mov     edx, 1Fh
0x180011378  mov     rcx, [rcx+10h]
0x18001137c  mov     dword ptr [rsp+100h+var_E0], eax
0x180011380  call    WPP_SF_sd
0x180011385  mov     edi, [rbp+57h+var_D0]
0x180011388  mov     [rbp+57h+var_C8], r12
0x18001138c  cmp     [rbp+57h+var_C0], r14
0x180011390  jz      loc_18001157E
0x180011396  lea     rcx, [rbp+57h+var_C8]
0x18001139a  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x18001139f  test    al, al
0x1800113a1  jnz     loc_18001157A
0x1800113a7  call    cs:__imp_GetLastError
0x1800113ad  test    eax, eax
0x1800113af  jle     short loc_1800113B6
0x1800113b1  movzx   eax, ax
0x1800113b4  or      eax, ebx
0x1800113b6  xor     r9d, r9d; lpArguments
0x1800113b9  xor     r8d, r8d; nNumberOfArguments
0x1800113bc  mov     edx, r15d; dwExceptionFlags
0x1800113bf  mov     ecx, eax; dwExceptionCode
0x1800113c1  call    cs:__imp_RaiseException
0x1800113c7  int     3; Trap to Debugger
0x1800113c8  mov     rdx, [rbx]
0x1800113cb  lea     rcx, [rbp+57h+var_88]
0x1800113cf  xorps   xmm0, xmm0
0x1800113d2  mov     [rbp+57h+var_B4], r15d
0x1800113d6  movups  [rbp+57h+var_88], xmm0
0x1800113da  mov     dword ptr [rbp+57h+var_88], 30h ; '0'
0x1800113e1  lea     r9, [rbp+57h+var_B4]
0x1800113e5  movups  [rbp+57h+var_78], xmm0
0x1800113e9  mov     [rsp+100h+var_E0], rcx
0x1800113ee  mov     rcx, rax
0x1800113f1  movups  [rbp+57h+var_68], xmm0
0x1800113f5  cmp     qword ptr [rdx+18h], 8
0x1800113fa  cmovb   rdx, rbx
0x1800113fe  xor     r8d, r8d
0x180011401  mov     rdx, [rdx]
0x180011404  call    cs:__imp_DevObjOpenDeviceInfo
0x18001140a  test    eax, eax
0x18001140c  jnz     loc_1800114B8
0x180011412  call    cs:__imp_GetLastError
0x180011418  mov     ebx, 80070000h
0x18001141d  test    eax, eax
0x18001141f  jle     short loc_180011426
0x180011421  movzx   eax, ax
0x180011424  or      eax, ebx
0x180011426  mov     edx, 2
0x18001142b  mov     [rbp+57h+var_D0], eax
0x18001142e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180011433  mov     rcx, cs:WPP_GLOBAL_Control
0x18001143a  lea     rax, WPP_GLOBAL_Control
0x180011441  cmp     rcx, rax
0x180011444  jz      short loc_180011475
0x180011446  test    [rcx+1Ch], r15b
0x18001144a  jz      short loc_180011475
0x18001144c  cmp     byte ptr [rcx+19h], 2
0x180011450  jb      short loc_180011475
0x180011452  mov     eax, [rbp+57h+var_D0]
0x180011455  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x18001145c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180011463  mov     edx, 20h ; ' '
0x180011468  mov     rcx, [rcx+10h]
0x18001146c  mov     dword ptr [rsp+100h+var_E0], eax
0x180011470  call    WPP_SF_sd
0x180011475  mov     edi, [rbp+57h+var_D0]
0x180011478  mov     [rbp+57h+var_C8], r12
0x18001147c  cmp     [rbp+57h+var_C0], r14
0x180011480  jz      loc_18001157E
0x180011486  lea     rcx, [rbp+57h+var_C8]
0x18001148a  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x18001148f  test    al, al
0x180011491  jnz     loc_18001157A
0x180011497  call    cs:__imp_GetLastError
0x18001149d  test    eax, eax
0x18001149f  jle     short loc_1800114A6
0x1800114a1  movzx   eax, ax
0x1800114a4  or      eax, ebx
0x1800114a6  xor     r9d, r9d; lpArguments
0x1800114a9  xor     r8d, r8d; nNumberOfArguments
0x1800114ac  mov     edx, r15d; dwExceptionFlags
0x1800114af  mov     ecx, eax; dwExceptionCode
0x1800114b1  call    cs:__imp_RaiseException
0x1800114b7  int     3; Trap to Debugger
0x1800114b8  mov     rcx, [rbp+57h+var_C0]
0x1800114bc  lea     r9, [rbp+57h+var_B0]
0x1800114c0  xor     r8d, r8d
0x1800114c3  mov     [rbp+57h+var_B0], 0
0x1800114ca  lea     rdx, [rbp+57h+var_88]
0x1800114ce  call    cs:__imp_DevObjUninstallDevice
0x1800114d4  test    eax, eax
0x1800114d6  jnz     loc_18001158B
0x1800114dc  call    cs:__imp_GetLastError
0x1800114e2  mov     ebx, 80070000h
0x1800114e7  test    eax, eax
0x1800114e9  jle     short loc_1800114F0
0x1800114eb  movzx   eax, ax
0x1800114ee  or      eax, ebx
0x1800114f0  mov     edx, 2
0x1800114f5  mov     [rbp+57h+var_D0], eax
0x1800114f8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800114fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180011504  lea     rax, WPP_GLOBAL_Control
0x18001150b  cmp     rcx, rax
0x18001150e  jz      short loc_18001153F
0x180011510  test    [rcx+1Ch], r15b
0x180011514  jz      short loc_18001153F
0x180011516  cmp     byte ptr [rcx+19h], 2
0x18001151a  jb      short loc_18001153F
0x18001151c  mov     eax, [rbp+57h+var_D0]
0x18001151f  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x180011526  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001152d  mov     edx, 21h ; '!'
0x180011532  mov     rcx, [rcx+10h]
0x180011536  mov     dword ptr [rsp+100h+var_E0], eax
0x18001153a  call    WPP_SF_sd
0x18001153f  mov     edi, [rbp+57h+var_D0]
0x180011542  mov     [rbp+57h+var_C8], r12
0x180011546  cmp     [rbp+57h+var_C0], r14
0x18001154a  jz      short loc_18001157E
0x18001154c  lea     rcx, [rbp+57h+var_C8]
0x180011550  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x180011555  test    al, al
0x180011557  jnz     short loc_18001157A
0x180011559  call    cs:__imp_GetLastError
0x18001155f  test    eax, eax
0x180011561  jle     short loc_180011568
0x180011563  movzx   eax, ax
0x180011566  or      eax, ebx
0x180011568  xor     r9d, r9d; lpArguments
0x18001156b  xor     r8d, r8d; nNumberOfArguments
0x18001156e  mov     edx, r15d; dwExceptionFlags
0x180011571  mov     ecx, eax; dwExceptionCode
0x180011573  call    cs:__imp_RaiseException
0x180011579  int     3; Trap to Debugger
0x18001157a  mov     [rbp+57h+var_C0], r14
0x18001157e  lea     rcx, [rbp+57h+var_A8]
0x180011582  call    WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652_______WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652____
0x180011587  mov     eax, edi
0x180011589  jmp     short loc_1800115D8
0x18001158b  mov     ebx, [rbp+57h+var_D0]
0x18001158e  mov     [rbp+57h+var_C8], r12
0x180011592  cmp     [rbp+57h+var_C0], r14
0x180011596  jz      short loc_1800115CD
0x180011598  lea     rcx, [rbp+57h+var_C8]
0x18001159c  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x1800115a1  test    al, al
0x1800115a3  jnz     short loc_1800115C9
0x1800115a5  call    cs:__imp_GetLastError
0x1800115ab  test    eax, eax
0x1800115ad  jle     short loc_1800115B7
0x1800115af  movzx   eax, ax
0x1800115b2  or      eax, 80070000h
0x1800115b7  xor     r9d, r9d; lpArguments
0x1800115ba  xor     r8d, r8d; nNumberOfArguments
0x1800115bd  mov     edx, r15d; dwExceptionFlags
0x1800115c0  mov     ecx, eax; dwExceptionCode
0x1800115c2  call    cs:__imp_RaiseException
0x1800115c8  int     3; Trap to Debugger
0x1800115c9  mov     [rbp+57h+var_C0], r14
0x1800115cd  lea     rcx, [rbp+57h+var_A8]
0x1800115d1  call    WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652_______WppTraceUnwinder__lambda_45cc125f5585310d98afbd4f866fb652____
0x1800115d6  mov     eax, ebx
0x1800115d8  mov     rcx, [rbp+57h+var_38]
0x1800115dc  xor     rcx, rsp; StackCookie
0x1800115df  call    __security_check_cookie
0x1800115e4  add     rsp, 0D8h
0x1800115eb  pop     r15
0x1800115ed  pop     r14
0x1800115ef  pop     r12
0x1800115f1  pop     rdi
0x1800115f2  pop     rbx
0x1800115f3  pop     rbp
0x1800115f4  retn
```

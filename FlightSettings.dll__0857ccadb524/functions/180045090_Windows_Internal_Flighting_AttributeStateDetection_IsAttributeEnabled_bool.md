# Windows::Internal::Flighting::AttributeStateDetection::IsAttributeEnabled(bool *)

- ea: `0x180045090`
- end: `0x180045491`
- name: `?IsAttributeEnabled@AttributeStateDetection@Flighting@Internal@Windows@@QEAAJPEA_N@Z`
- size: `1025`
- prototype: `__int64 __fastcall(Windows::Internal::Flighting::AttributeStateDetection *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045cfc`

## callees

- `0x18000cc8c`
- `0x1800175b4`
- `0x18001cff8`
- `0x180045090`
- `0x18004588c`
- `0x180045914`
- `0x180046480`
- `0x180046560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004514a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800451c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045214`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004539b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004514a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800451c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045214`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004539b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045275`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045304`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045346`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800453f7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045275`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045304`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180045346`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800453f7`

## string_xrefs

- `0x1800450b4`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180045172`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x18004522c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x1800453b3`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x18004540f`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180045458`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::AttributeStateDetection::IsAttributeEnabled(
        Windows::Internal::Flighting::AttributeStateDetection *this,
        bool *a2)
{
  signed int v4; // ebx
  const WCHAR *v6; // rdx
  HKEY v7; // rcx
  int v8; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  LSTATUS ValueW; // eax
  LSTATUS v12; // eax
  int v13; // eax
  bool v14; // sf
  unsigned int v15; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  int v19; // eax
  bool v20; // sf
  DWORD v21; // eax
  int v22; // eax
  bool v23; // sf
  __int64 v24; // rdx
  int v25; // eax
  int pdwType; // [rsp+20h] [rbp-40h]
  int pdwTypea; // [rsp+20h] [rbp-40h]
  LPDWORD pdwTyped; // [rsp+20h] [rbp-40h]
  int pdwTypeb; // [rsp+20h] [rbp-40h]
  int pdwTypec; // [rsp+20h] [rbp-40h]
  DWORD pcbData; // [rsp+40h] [rbp-20h] BYREF
  __int64 Data; // [rsp+48h] [rbp-18h] BYREF
  HKEY hkey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v35; // [rsp+A8h] [rbp+48h] BYREF
  int pvData; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v37; // [rsp+B8h] [rbp+58h] BYREF

  if ( a2 )
  {
    if ( !*((_BYTE *)this + 272) )
    {
      *a2 = 1;
      return 0;
    }
    v6 = (const WCHAR *)*((_QWORD *)this + 9);
    v7 = (HKEY)*((_QWORD *)this + 33);
    hkey[0] = 0;
    v8 = wil::reg::open_unique_key_nothrow(v7, v6);
    v4 = v8;
    if ( v8 < 0 )
    {
      v9 = (unsigned int)v8;
      v10 = 180;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
        (const char *)v9,
        pdwType);
LABEL_52:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
      return (unsigned int)v4;
    }
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey[0], 0, L"Disabled", 0x10u, 0, &pvData, &pcbData);
    v4 = ValueW;
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    if ( v4 < 0 )
    {
      v10 = 187;
LABEL_11:
      v9 = (unsigned int)v4;
      goto LABEL_12;
    }
    if ( pvData )
    {
      v37 = 0;
      pcbData = 4;
      v12 = RegGetValueW(hkey[0], 0, L"SkipCount", 0x10u, 0, &v37, &pcbData);
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 < 0 )
      {
        v10 = 201;
        goto LABEL_11;
      }
      pcbData = 4;
      v35 = 5;
      v13 = RegGetValueW(hkey[0], 0, L"SkipThreshold", 0x10u, 0, &v35, &pcbData);
      v14 = v13 < 0;
      if ( v13 > 0 )
      {
        v13 = (unsigned __int16)v13 | 0x80070000;
        v14 = v13 < 0;
      }
      if ( v14 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
          (const char *)(unsigned int)v13,
          pdwTypea);
        v15 = 5;
        v35 = 5;
      }
      else
      {
        v15 = v35;
      }
      if ( v37 < v15 )
      {
        *a2 = 0;
        goto LABEL_51;
      }
      LODWORD(Data) = 0;
      v16 = RegSetKeyValueW(hkey[0], 0, L"Disabled", 4u, &Data, 4u);
      v4 = v16;
      if ( v16 > 0 )
        v4 = (unsigned __int16)v16 | 0x80070000;
      if ( v4 < 0 )
      {
        v10 = 220;
        goto LABEL_11;
      }
      pdwTyped = (LPDWORD)*((_QWORD *)this + 36);
      Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeCollectionEvent(
        this,
        *((_QWORD *)this + 21),
        0,
        *((_QWORD *)this + 18));
      LODWORD(pdwTyped) = 0;
      Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(
        this,
        *((_QWORD *)this + 21),
        0,
        *((_QWORD *)this + 18),
        pdwTyped,
        0,
        0);
      LODWORD(Data) = 0;
      v17 = RegSetKeyValueW(hkey[0], 0, L"SkipCount", 4u, &Data, 4u);
      v4 = v17;
      if ( v17 > 0 )
        v4 = (unsigned __int16)v17 | 0x80070000;
      if ( v4 < 0 )
      {
        v10 = 240;
        goto LABEL_11;
      }
      LODWORD(Data) = 0;
      v18 = RegSetKeyValueW(hkey[0], 0, L"CrashCount", 4u, &Data, 4u);
      v4 = v18;
      if ( v18 > 0 )
        v4 = (unsigned __int16)v18 | 0x80070000;
      if ( v4 < 0 )
      {
        v10 = 245;
        goto LABEL_11;
      }
      pcbData = 5;
      LODWORD(Data) = 4;
      v19 = RegGetValueW(hkey[0], 0, L"CrashThreshold", 0x10u, 0, &pcbData, (LPDWORD)&Data);
      v20 = v19 < 0;
      if ( v19 > 0 )
      {
        v19 = (unsigned __int16)v19 | 0x80070000;
        v20 = v19 < 0;
      }
      if ( v20 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
          (const char *)(unsigned int)v19,
          pdwTypeb);
      v21 = pcbData >> 1;
      if ( pcbData >> 1 < 2 )
        v21 = 2;
      LODWORD(Data) = v21;
      v22 = RegSetKeyValueW(hkey[0], 0, L"CrashThreshold", 4u, &Data, 4u);
      v23 = v22 < 0;
      if ( v22 > 0 )
      {
        v22 = (unsigned __int16)v22 | 0x80070000;
        v23 = v22 < 0;
      }
      if ( v23 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
          (const char *)(unsigned int)v22,
          pdwTypec);
      v24 = *((_QWORD *)this + 12);
      Data = *((_QWORD *)this + 33);
      v25 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::delete_tree(&Data, v24);
      if ( v25 <= -2147024895 || (unsigned int)(v25 + 2147024892) <= 0x7FF8FFFB )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
          (const char *)(unsigned int)v25,
          pdwTypec);
    }
    *a2 = 1;
LABEL_51:
    v4 = 0;
    goto LABEL_52;
  }
  v4 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA7,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
    (const char *)0x80070057LL,
    pdwType);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180045090  push    rbp
0x180045092  push    rbx
0x180045093  push    rsi
0x180045094  push    rdi
0x180045095  push    r12
0x180045097  push    r14
0x180045099  push    r15
0x18004509b  mov     rbp, rsp
0x18004509e  sub     rsp, 60h
0x1800450a2  xor     r14d, r14d
0x1800450a5  mov     rsi, rdx
0x1800450a8  mov     rdi, rcx
0x1800450ab  test    rdx, rdx
0x1800450ae  jnz     short loc_1800450D2
0x1800450b0  mov     rcx, [rbp+38h]; this
0x1800450b4  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x1800450bb  mov     ebx, 80070057h
0x1800450c0  mov     edx, 0A7h; void *
0x1800450c5  mov     r9d, ebx; char *
0x1800450c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800450cd  jmp     loc_180045480
0x1800450d2  cmp     [rcx+110h], r14b
0x1800450d9  jnz     short loc_1800450E5
0x1800450db  mov     byte ptr [rdx], 1
0x1800450de  xor     eax, eax
0x1800450e0  jmp     loc_180045482
0x1800450e5  mov     rdx, [rcx+48h]; lpSubKey
0x1800450e9  lea     r8, [rbp+hkey]
0x1800450ed  mov     rcx, [rcx+108h]; hKey
0x1800450f4  mov     r9d, 1
0x1800450fa  mov     [rbp+hkey], r14
0x1800450fe  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180045103  mov     ebx, eax
0x180045105  test    eax, eax
0x180045107  jns     short loc_180045113
0x180045109  mov     r9d, eax
0x18004510c  mov     edx, 0B4h
0x180045111  jmp     short loc_18004516E
0x180045113  mov     rcx, [rbp+hkey]; hkey
0x180045117  lea     rax, [rbp+var_20]
0x18004511b  mov     [rsp+60h+pcbData], rax; pcbData
0x180045120  lea     r8, aDisabled; "Disabled"
0x180045127  mov     r12d, 4
0x18004512d  mov     [rbp+arg_10], r14d
0x180045131  lea     rax, [rbp+arg_10]
0x180045135  mov     [rbp+var_20], r12d
0x180045139  mov     [rsp+60h+pvData], rax; pvData
0x18004513e  xor     edx, edx; lpSubKey
0x180045140  mov     [rsp+60h+pdwType], r14; int
0x180045145  lea     r9d, [r12+0Ch]; dwFlags
0x18004514a  call    cs:__imp_RegGetValueW
0x180045150  mov     ebx, eax
0x180045152  mov     r15d, 80070000h
0x180045158  test    eax, eax
0x18004515a  jle     short loc_180045162
0x18004515c  movzx   ebx, ax
0x18004515f  or      ebx, r15d
0x180045162  test    ebx, ebx
0x180045164  jns     short loc_180045183
0x180045166  mov     edx, 0BBh; void *
0x18004516b  mov     r9d, ebx; char *
0x18004516e  mov     rcx, [rbp+38h]; this
0x180045172  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180045179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004517e  jmp     loc_180045477
0x180045183  cmp     [rbp+arg_10], r14d
0x180045187  jnz     short loc_180045191
0x180045189  mov     byte ptr [rsi], 1
0x18004518c  jmp     loc_180045474
0x180045191  mov     rcx, [rbp+hkey]; hkey
0x180045195  lea     rax, [rbp+var_20]
0x180045199  mov     [rsp+60h+pcbData], rax; pcbData
0x18004519e  lea     r8, aSkipcount; "SkipCount"
0x1800451a5  lea     rax, [rbp+arg_18]
0x1800451a9  mov     [rbp+arg_18], r14d
0x1800451ad  mov     [rsp+60h+pvData], rax; pvData
0x1800451b2  mov     r9d, 10h; dwFlags
0x1800451b8  xor     edx, edx; lpSubKey
0x1800451ba  mov     [rsp+60h+pdwType], r14; pdwType
0x1800451bf  mov     [rbp+var_20], r12d
0x1800451c3  call    cs:__imp_RegGetValueW
0x1800451c9  mov     ebx, eax
0x1800451cb  test    eax, eax
0x1800451cd  jle     short loc_1800451D5
0x1800451cf  movzx   ebx, ax
0x1800451d2  or      ebx, r15d
0x1800451d5  test    ebx, ebx
0x1800451d7  jns     short loc_1800451E0
0x1800451d9  mov     edx, 0C9h
0x1800451de  jmp     short loc_18004516B
0x1800451e0  mov     rcx, [rbp+hkey]; hkey
0x1800451e4  lea     rax, [rbp+var_20]
0x1800451e8  mov     [rsp+60h+pcbData], rax; pcbData
0x1800451ed  lea     r8, aSkipthreshold; "SkipThreshold"
0x1800451f4  mov     ebx, 5
0x1800451f9  mov     [rbp+var_20], r12d
0x1800451fd  lea     rax, [rbp+arg_8]
0x180045201  mov     [rbp+arg_8], ebx
0x180045204  mov     [rsp+60h+pvData], rax; pvData
0x180045209  xor     edx, edx; lpSubKey
0x18004520b  mov     [rsp+60h+pdwType], r14; int
0x180045210  lea     r9d, [rbx+0Bh]; dwFlags
0x180045214  call    cs:__imp_RegGetValueW
0x18004521a  test    eax, eax
0x18004521c  jle     short loc_180045226
0x18004521e  movzx   eax, ax
0x180045221  or      eax, r15d
0x180045224  test    eax, eax
0x180045226  jns     short loc_180045247
0x180045228  mov     rcx, [rbp+38h]; this
0x18004522c  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180045233  mov     r9d, eax; char *
0x180045236  mov     edx, 0D1h; void *
0x18004523b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045240  mov     eax, ebx
0x180045242  mov     [rbp+arg_8], ebx
0x180045245  jmp     short loc_18004524A
0x180045247  mov     eax, [rbp+arg_8]
0x18004524a  cmp     [rbp+arg_18], eax
0x18004524d  jb      loc_180045471
0x180045253  mov     rcx, [rbp+hkey]; hKey
0x180045257  lea     rax, [rbp+Data]
0x18004525b  mov     dword ptr [rsp+60h+pvData], r12d; cbData
0x180045260  lea     r8, aDisabled; "Disabled"
0x180045267  mov     r9d, r12d; dwType
0x18004526a  mov     [rsp+60h+pdwType], rax; lpData
0x18004526f  xor     edx, edx; lpSubKey
0x180045271  mov     dword ptr [rbp+Data], r14d
0x180045275  call    cs:__imp_RegSetKeyValueW
0x18004527b  mov     ebx, eax
0x18004527d  test    eax, eax
0x18004527f  jle     short loc_180045287
0x180045281  movzx   ebx, ax
0x180045284  or      ebx, r15d
0x180045287  test    ebx, ebx
0x180045289  jns     short loc_180045295
0x18004528b  mov     edx, 0DCh
0x180045290  jmp     loc_18004516B
0x180045295  mov     rax, [rdi+120h]
0x18004529c  xor     r8d, r8d
0x18004529f  mov     r9, [rdi+90h]
0x1800452a6  mov     rcx, rdi
0x1800452a9  mov     rdx, [rdi+0A8h]
0x1800452b0  mov     dword ptr [rsp+60h+pcbData], r14d
0x1800452b5  mov     dword ptr [rsp+60h+pvData], r14d
0x1800452ba  mov     [rsp+60h+pdwType], rax
0x1800452bf  call    ?RecordAttributeCollectionEvent@AttributeStateDetection@Flighting@Internal@Windows@@AEAAXPEBGW4AttributeEventType@Telemetry@CTAC@@0_KKJ@Z; Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeCollectionEvent(ushort const *,CTAC::Telemetry::AttributeEventType,ushort const *,unsigned __int64,ulong,long)
0x1800452c4  mov     r9, [rdi+90h]
0x1800452cb  xor     r8d, r8d
0x1800452ce  mov     rdx, [rdi+0A8h]
0x1800452d5  mov     rcx, rdi
0x1800452d8  mov     dword ptr [rsp+60h+pdwType], r14d
0x1800452dd  call    ?RecordAttributeStateEvent@AttributeStateDetection@Flighting@Internal@Windows@@AEAAXPEBGW4AttributeEventType@Telemetry@CTAC@@0K@Z; Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(ushort const *,CTAC::Telemetry::AttributeEventType,ushort const *,ulong)
0x1800452e2  mov     rcx, [rbp+hkey]; hKey
0x1800452e6  lea     rax, [rbp+Data]
0x1800452ea  mov     dword ptr [rsp+60h+pvData], r12d; cbData
0x1800452ef  lea     r8, aSkipcount; "SkipCount"
0x1800452f6  mov     r9d, r12d; dwType
0x1800452f9  mov     [rsp+60h+pdwType], rax; lpData
0x1800452fe  xor     edx, edx; lpSubKey
0x180045300  mov     dword ptr [rbp+Data], r14d
0x180045304  call    cs:__imp_RegSetKeyValueW
0x18004530a  mov     ebx, eax
0x18004530c  test    eax, eax
0x18004530e  jle     short loc_180045316
0x180045310  movzx   ebx, ax
0x180045313  or      ebx, r15d
0x180045316  test    ebx, ebx
0x180045318  jns     short loc_180045324
0x18004531a  mov     edx, 0F0h
0x18004531f  jmp     loc_18004516B
0x180045324  mov     rcx, [rbp+hkey]; hKey
0x180045328  lea     rax, [rbp+Data]
0x18004532c  mov     dword ptr [rsp+60h+pvData], r12d; cbData
0x180045331  lea     r8, Value; "CrashCount"
0x180045338  mov     r9d, r12d; dwType
0x18004533b  mov     [rsp+60h+pdwType], rax; lpData
0x180045340  xor     edx, edx; lpSubKey
0x180045342  mov     dword ptr [rbp+Data], r14d
0x180045346  call    cs:__imp_RegSetKeyValueW
0x18004534c  mov     ebx, eax
0x18004534e  test    eax, eax
0x180045350  jle     short loc_180045358
0x180045352  movzx   ebx, ax
0x180045355  or      ebx, r15d
0x180045358  test    ebx, ebx
0x18004535a  jns     short loc_180045366
0x18004535c  mov     edx, 0F5h
0x180045361  jmp     loc_18004516B
0x180045366  mov     rcx, [rbp+hkey]; hkey
0x18004536a  lea     rax, [rbp+Data]
0x18004536e  mov     [rsp+60h+pcbData], rax; pcbData
0x180045373  lea     r8, aCrashthreshold; "CrashThreshold"
0x18004537a  lea     rax, [rbp+var_20]
0x18004537e  mov     [rbp+var_20], 5
0x180045385  mov     [rsp+60h+pvData], rax; pvData
0x18004538a  mov     r9d, 10h; dwFlags
0x180045390  xor     edx, edx; lpSubKey
0x180045392  mov     [rsp+60h+pdwType], r14; int
0x180045397  mov     dword ptr [rbp+Data], r12d
0x18004539b  call    cs:__imp_RegGetValueW
0x1800453a1  test    eax, eax
0x1800453a3  jle     short loc_1800453AD
0x1800453a5  movzx   eax, ax
0x1800453a8  or      eax, r15d
0x1800453ab  test    eax, eax
0x1800453ad  jns     short loc_1800453C7
0x1800453af  mov     rcx, [rbp+38h]; this
0x1800453b3  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x1800453ba  mov     r9d, eax; char *
0x1800453bd  mov     edx, 0FBh; void *
0x1800453c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800453c7  mov     eax, [rbp+var_20]
0x1800453ca  lea     r8, aCrashthreshold; "CrashThreshold"
0x1800453d1  shr     eax, 1
0x1800453d3  mov     ecx, 2
0x1800453d8  cmp     eax, ecx
0x1800453da  mov     dword ptr [rsp+60h+pvData], r12d; cbData
0x1800453df  mov     r9d, r12d; dwType
0x1800453e2  cmovb   eax, ecx
0x1800453e5  mov     rcx, [rbp+hkey]; hKey
0x1800453e9  mov     dword ptr [rbp+Data], eax
0x1800453ec  xor     edx, edx; lpSubKey
0x1800453ee  lea     rax, [rbp+Data]
0x1800453f2  mov     [rsp+60h+pdwType], rax; int
0x1800453f7  call    cs:__imp_RegSetKeyValueW
0x1800453fd  test    eax, eax
0x1800453ff  jle     short loc_180045409
0x180045401  movzx   eax, ax
0x180045404  or      eax, r15d
0x180045407  test    eax, eax
0x180045409  jns     short loc_180045423
0x18004540b  mov     rcx, [rbp+38h]; this
0x18004540f  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180045416  mov     r9d, eax; char *
0x180045419  mov     edx, 103h; void *
0x18004541e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045423  mov     rax, [rdi+108h]
0x18004542a  lea     rcx, [rbp+Data]
0x18004542e  mov     rdx, [rdi+60h]
0x180045432  mov     [rbp+Data], rax
0x180045436  call    ?delete_tree@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@QEBAJPEBG@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::delete_tree(ushort const *)
0x18004543b  cmp     eax, 80070001h
0x180045440  jle     short loc_180045454
0x180045442  lea     ecx, [rax+7FF8FFFCh]
0x180045448  cmp     ecx, 7FF8FFFBh
0x18004544e  ja      loc_180045189
0x180045454  mov     rcx, [rbp+38h]; this
0x180045458  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x18004545f  mov     r9d, eax; char *
0x180045462  mov     edx, 10Ah; void *
0x180045467  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004546c  jmp     loc_180045189
0x180045471  mov     [rsi], r14b
0x180045474  mov     ebx, r14d
0x180045477  lea     rcx, [rbp+hkey]
0x18004547b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180045480  mov     eax, ebx
0x180045482  add     rsp, 60h
0x180045486  pop     r15
0x180045488  pop     r14
0x18004548a  pop     r12
0x18004548c  pop     rdi
0x18004548d  pop     rsi
0x18004548e  pop     rbx
0x18004548f  pop     rbp
0x180045490  retn
```

# CSoftwareUpdates::GetSettings(__MIDL___MIDL_itf_wmssvc_0000_0000_0022 *,ulong *,ushort * *,ulong *,__MIDL___MIDL_itf_wmssvc_0000_0000_0023 *)

- ea: `0x14002feb4`
- end: `0x14003046d`
- name: `?GetSettings@CSoftwareUpdates@@QEAAJPEAW4__MIDL___MIDL_itf_wmssvc_0000_0000_0022@@PEAKPEAPEAG1PEAW4__MIDL___MIDL_itf_wmssvc_0000_0000_0023@@@Z`
- size: `1465`
- prototype: `__int64 __fastcall(CSoftwareUpdates *__hidden this, enum __MIDL___MIDL_itf_wmssvc_0000_0000_0022 *, unsigned int *, unsigned __int16 **, unsigned int *, enum __MIDL___MIDL_itf_wmssvc_0000_0000_0023 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x140009380`
- `0x140035ec0`
- `0x140037a1c`
- `0x14003851c`

## callees

- `0x1400016b8`
- `0x14002feb4`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061a0c`
- `0x14006ea54`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140030010`
- `ADVAPI32!RegGetValueW` at `0x14003015f`
- `ADVAPI32!RegGetValueW` at `0x140030252`
- `ADVAPI32!RegGetValueW` at `0x14003032c`
- `ADVAPI32!RegGetValueW` at `0x140030010`
- `ADVAPI32!RegGetValueW` at `0x14003015f`
- `ADVAPI32!RegGetValueW` at `0x140030252`
- `ADVAPI32!RegGetValueW` at `0x14003032c`
- `ADVAPI32!RegCloseKey` at `0x14003044c`
- `ADVAPI32!RegCloseKey` at `0x14003044c`
- `ADVAPI32!RegCreateKeyExW` at `0x14002ff21`
- `ADVAPI32!RegCreateKeyExW` at `0x14002ff21`
- `KERNEL32!IsDebuggerPresent` at `0x14002ff7c`
- `KERNEL32!IsDebuggerPresent` at `0x14003007c`
- `KERNEL32!IsDebuggerPresent` at `0x1400300fb`
- `KERNEL32!IsDebuggerPresent` at `0x1400301e1`
- `KERNEL32!IsDebuggerPresent` at `0x1400302db`
- `KERNEL32!IsDebuggerPresent` at `0x1400303b0`
- `KERNEL32!IsDebuggerPresent` at `0x14002ff7c`
- `KERNEL32!IsDebuggerPresent` at `0x14003007c`
- `KERNEL32!IsDebuggerPresent` at `0x1400300fb`
- `KERNEL32!IsDebuggerPresent` at `0x1400301e1`
- `KERNEL32!IsDebuggerPresent` at `0x1400302db`
- `KERNEL32!IsDebuggerPresent` at `0x1400303b0`

## string_xrefs

- `0x14002ff58`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x14003005b`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400300e0`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400301c6`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400302c0`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030395`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x14002ffef`: `DpSoftwareUpdateMode`
- `0x14003013a`: `DpSoftwareUpdateStartTime`
- `0x1400301fd`: `DpSoftwareUpdateScript`
- `0x140030229`: `DpSoftwareUpdateScriptMaxRuntimeMinutes`
- `0x1400302ff`: `DpSoftwareUpdateReturnState`
- `0x14002ff4b`: `CSoftwareUpdates::GetSettings`
- `0x140030051`: `CSoftwareUpdates::GetSettings`
- `0x1400300ce`: `CSoftwareUpdates::GetSettings`
- `0x1400301b4`: `CSoftwareUpdates::GetSettings`
- `0x1400302ae`: `CSoftwareUpdates::GetSettings`
- `0x140030383`: `CSoftwareUpdates::GetSettings`
- `0x1400300bb`: `iTemp <= __SUM_Last`
- `0x140030103`: `iTemp <= __SUM_Last`
- `0x1400301a1`: `iTemp <= ( 23 )`
- `0x1400301e9`: `iTemp <= ( 23 )`
- `0x14003029b`: `(iTemp >= ( 15 )) && (iTemp <= ( 180 ))`
- `0x1400302e3`: `(iTemp >= ( 15 )) && (iTemp <= ( 180 ))`
- `0x140030370`: `iTemp <= __SUR_Last`
- `0x1400303b8`: `iTemp <= __SUR_Last`
- `0x14003042e`: `CSoftwareUpdates::GetSettings - eUpdateMode = %s, start time = %i, script = %s, time limit = %i, return state = %s\n`
- `0x14002fedf`: `System\CurrentControlSet\Services\WMS\Parameters\`
- `0x140030315`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CSoftwareUpdates::GetSettings(
        CSoftwareUpdates *this,
        enum __MIDL___MIDL_itf_wmssvc_0000_0000_0022 *a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned int *a5,
        enum __MIDL___MIDL_itf_wmssvc_0000_0000_0023 *a6)
{
  LSTATUS v8; // eax
  signed int StringValue; // r15d
  __int64 v10; // r9
  __int64 v11; // r8
  LSTATUS ValueW; // eax
  unsigned int v13; // esi
  unsigned int v14; // r13d
  bool v15; // zf
  const unsigned __int16 *v16; // rax
  LSTATUS v17; // eax
  unsigned int v18; // edi
  LSTATUS v19; // eax
  int v20; // ebx
  LSTATUS v21; // eax
  unsigned __int64 v22; // r9
  __int64 v23; // rcx
  unsigned __int16 *v24; // rax
  unsigned int *v25; // rdi
  enum __MIDL___MIDL_itf_wmssvc_0000_0000_0023 *v26; // rax
  const unsigned __int16 *v27; // rax
  __int64 v28; // rsi
  const unsigned __int16 *v29; // rbx
  unsigned int v30; // r14d
  unsigned __int64 v31; // r9
  const unsigned __int16 *v32; // rax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-50h]
  const unsigned __int16 *samDesired; // [rsp+28h] [rbp-48h]
  LPDWORD pcbData; // [rsp+30h] [rbp-40h]
  LPDWORD pcbDataa; // [rsp+30h] [rbp-40h]
  __int64 v38; // [rsp+38h] [rbp-38h]
  DWORD v39; // [rsp+50h] [rbp-20h] BYREF
  void *Block; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  unsigned int pvData; // [rsp+B0h] [rbp+40h] BYREF
  int v43; // [rsp+B4h] [rbp+44h]
  enum __MIDL___MIDL_itf_wmssvc_0000_0000_0022 *v44; // [rsp+B8h] [rbp+48h]

  v44 = a2;
  v43 = HIDWORD(this);
  hKey = 0;
  pvData = 0;
  v39 = 0;
  Block = 0;
  v8 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
         0,
         0,
         0,
         1u,
         0,
         &hKey,
         0);
  StringValue = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      StringValue = (unsigned __int16)v8 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0xBAu,
      L"CSoftwareUpdates::GetSettings",
      L"CBRAEx",
      L"err == 0L",
      StringValue);
    if ( IsDebuggerPresent() )
    {
      LODWORD(v38) = StringValue;
      v10 = 186;
      pcbDataa = (LPDWORD)L"err == 0L";
LABEL_6:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        v10,
        L"CSoftwareUpdates::GetSettings",
        L"CBRAEx",
        pcbDataa,
        v38);
      goto LABEL_57;
    }
    LODWORD(pcbData) = StringValue;
    v11 = 186;
    samDesired = L"err == 0L";
    goto LABEL_8;
  }
  v39 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
             L"DpSoftwareUpdateMode",
             0x18u,
             0,
             &pvData,
             &v39);
  StringValue = ValueW;
  if ( ValueW == 2 )
  {
    v13 = 0;
    pvData = 0;
  }
  else
  {
    if ( ValueW )
    {
      if ( ValueW > 0 )
        StringValue = (unsigned __int16)ValueW | 0x80070000;
      v14 = 199;
      goto LABEL_15;
    }
    v13 = pvData;
  }
  if ( v13 > 2 )
  {
    v14 = 201;
    StringValue = -2147418113;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0xC9u,
      L"CSoftwareUpdates::GetSettings",
      L"CBRAEx",
      L"iTemp <= __SUM_Last",
      -2147418113);
    v15 = !IsDebuggerPresent();
    v16 = L"iTemp <= __SUM_Last";
LABEL_23:
    if ( !v15 )
    {
      LODWORD(v38) = -2147418113;
      pcbDataa = (LPDWORD)v16;
      goto LABEL_17;
    }
    LODWORD(pcbData) = -2147418113;
    samDesired = v16;
    goto LABEL_19;
  }
  v39 = 4;
  v17 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
          L"DpSoftwareUpdateStartTime",
          0x18u,
          0,
          &pvData,
          &v39);
  StringValue = v17;
  if ( v17 == 2 )
  {
    v18 = 3;
    pvData = 3;
  }
  else
  {
    if ( v17 )
    {
      if ( v17 > 0 )
        StringValue = (unsigned __int16)v17 | 0x80070000;
      v14 = 216;
      goto LABEL_15;
    }
    v18 = pvData;
  }
  if ( v18 > 0x17 )
  {
    v14 = 218;
    StringValue = -2147418113;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0xDAu,
      L"CSoftwareUpdates::GetSettings",
      L"CBRAEx",
      L"iTemp <= ( 23 )",
      -2147418113);
    v15 = !IsDebuggerPresent();
    v16 = L"iTemp <= ( 23 )";
    goto LABEL_23;
  }
  StringValue = RegUtil::GetStringValue(1, hKey, L"DpSoftwareUpdateScript", &Block);
  if ( StringValue >= 0 )
  {
    v39 = 4;
    v19 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
            L"DpSoftwareUpdateScriptMaxRuntimeMinutes",
            0x18u,
            0,
            &pvData,
            &v39);
    if ( v19 == 2 )
    {
      v20 = 15;
      pvData = 15;
    }
    else
    {
      if ( v19 )
      {
        if ( v19 > 0 )
          StringValue = (unsigned __int16)v19 | 0x80070000;
        else
          StringValue = v19;
        v14 = 239;
        goto LABEL_15;
      }
      v20 = pvData;
    }
    if ( (unsigned int)(v20 - 15) > 0xA5 )
    {
      v14 = 241;
      StringValue = -2147418113;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        0xF1u,
        L"CSoftwareUpdates::GetSettings",
        L"CBRAEx",
        L"(iTemp >= ( 15 )) && (iTemp <= ( 180 ))",
        -2147418113);
      v15 = !IsDebuggerPresent();
      v16 = L"(iTemp >= ( 15 )) && (iTemp <= ( 180 ))";
      goto LABEL_23;
    }
    v39 = 4;
    v21 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
            L"DpSoftwareUpdateReturnState",
            0x18u,
            0,
            &pvData,
            &v39);
    if ( v21 == 2 )
    {
      v23 = 1;
      pvData = 1;
LABEL_54:
      if ( (unsigned int)v23 > 1 )
      {
        v14 = 257;
        StringValue = -2147418113;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          0x101u,
          L"CSoftwareUpdates::GetSettings",
          L"CBRAEx",
          L"iTemp <= __SUR_Last",
          -2147418113);
        v15 = !IsDebuggerPresent();
        v16 = L"iTemp <= __SUR_Last";
        goto LABEL_23;
      }
      *(_DWORD *)v44 = v13;
      v24 = (unsigned __int16 *)Block;
      *a3 = v18;
      v25 = a5;
      *a4 = v24;
      v26 = a6;
      Block = 0;
      *v25 = v20;
      *(_DWORD *)v26 = v23;
      v27 = Utils::StringTableHelper(
              (Utils *)v23,
              (unsigned int)&qword_14009C260,
              (const struct Utils::SStringMap *)2,
              v22);
      v28 = (__int64)*a4;
      LODWORD(v25) = *v25;
      v29 = v27;
      v30 = *a3;
      v32 = Utils::StringTableHelper(
              (Utils *)*(unsigned int *)v44,
              (unsigned int)&qword_14009C280,
              (const struct Utils::SStringMap *)3,
              v31);
      dwOptions[0] = (unsigned int)v25;
      DEBUGMSG(
        L"CSoftwareUpdates::GetSettings - eUpdateMode = %s, start time = %i, script = %s, time limit = %i, return state = %s\n",
        v32,
        v30,
        v28,
        *(_QWORD *)dwOptions,
        v29);
      goto LABEL_57;
    }
    if ( !v21 )
    {
      v23 = pvData;
      goto LABEL_54;
    }
    if ( v21 > 0 )
      StringValue = (unsigned __int16)v21 | 0x80070000;
    else
      StringValue = v21;
    v14 = 255;
LABEL_15:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      v14,
      L"CSoftwareUpdates::GetSettings",
      L"CBRAEx",
      L"err == 0L",
      StringValue);
    if ( IsDebuggerPresent() )
    {
      LODWORD(v38) = StringValue;
      pcbDataa = (LPDWORD)L"err == 0L";
LABEL_17:
      v10 = v14;
      goto LABEL_6;
    }
    LODWORD(pcbData) = StringValue;
    samDesired = L"err == 0L";
LABEL_19:
    v11 = v14;
LABEL_8:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      v11,
      L"CSoftwareUpdates::GetSettings",
      L"CBRAEx",
      samDesired,
      pcbData);
  }
LABEL_57:
  operator delete(Block);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x14002feb4  mov     r11, rsp
0x14002feb7  mov     [r11+18h], rbx
0x14002febb  mov     [r11+10h], rdx
0x14002febf  mov     [r11+8], rcx
0x14002fec3  push    rbp
0x14002fec4  push    rsi
0x14002fec5  push    rdi
0x14002fec6  push    r12
0x14002fec8  push    r13
0x14002feca  push    r14
0x14002fecc  push    r15
0x14002fece  mov     rbp, rsp
0x14002fed1  sub     rsp, 70h
0x14002fed5  xor     edi, edi
0x14002fed7  lea     rax, [rbp+hKey]
0x14002fedb  mov     [r11-68h], rdi
0x14002fedf  lea     rbx, ?s_szRegKey@CSoftwareUpdates@@0QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x14002fee6  mov     [r11-70h], rax
0x14002feea  mov     r14, r9
0x14002feed  mov     [r11-78h], rdi
0x14002fef1  mov     r13, r8
0x14002fef4  mov     rsi, 0FFFFFFFF80000002h
0x14002fefb  mov     [rsp+70h+samDesired], 1; samDesired
0x14002ff03  xor     r9d, r9d; lpClass
0x14002ff06  mov     [rsp+70h+dwOptions], edi; dwOptions
0x14002ff0a  xor     r8d, r8d; Reserved
0x14002ff0d  mov     [rbp+hKey], rdi
0x14002ff11  mov     rdx, rbx; lpSubKey
0x14002ff14  mov     [rbp+pvData], edi
0x14002ff17  mov     rcx, rsi; hKey
0x14002ff1a  mov     [rbp+var_20], edi
0x14002ff1d  mov     [rbp+Block], rdi
0x14002ff21  call    cs:__imp_RegCreateKeyExW
0x14002ff27  mov     r15d, eax
0x14002ff2a  test    eax, eax
0x14002ff2c  jz      loc_14002FFDF
0x14002ff32  jle     short loc_14002FF3F
0x14002ff34  movzx   r15d, ax
0x14002ff38  or      r15d, 80070000h
0x14002ff3f  lea     rsi, aCbraex; "CBRAEx"
0x14002ff46  mov     [rsp+70h+samDesired], r15d; int
0x14002ff4b  lea     rdi, aCsoftwareupdat_9; "CSoftwareUpdates::GetSettings"
0x14002ff52  mov     r12d, 0BAh
0x14002ff58  lea     rbx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x14002ff5f  mov     r9, rsi; unsigned __int16 *
0x14002ff62  lea     r14, aErr0l; "err == 0L"
0x14002ff69  mov     r8, rdi; unsigned __int16 *
0x14002ff6c  mov     edx, r12d; unsigned int
0x14002ff6f  mov     qword ptr [rsp+70h+dwOptions], r14; unsigned __int16 *
0x14002ff74  mov     rcx, rbx; unsigned __int16 *
0x14002ff77  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ff7c  call    cs:__imp_IsDebuggerPresent
0x14002ff82  test    eax, eax
0x14002ff84  jz      short loc_14002FFB6
0x14002ff86  mov     dword ptr [rsp+70h+var_38], r15d
0x14002ff8b  mov     r9d, r12d
0x14002ff8e  mov     [rsp+70h+pcbData], r14
0x14002ff93  mov     ecx, 2; unsigned __int8
0x14002ff98  mov     qword ptr [rsp+70h+samDesired], rsi
0x14002ff9d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002ffa4  mov     r8, rbx
0x14002ffa7  mov     qword ptr [rsp+70h+dwOptions], rdi
0x14002ffac  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002ffb1  jmp     loc_14003043A
0x14002ffb6  mov     dword ptr [rsp+70h+pcbData], r15d
0x14002ffbb  mov     r8d, r12d
0x14002ffbe  mov     qword ptr [rsp+70h+samDesired], r14
0x14002ffc3  mov     r9, rdi
0x14002ffc6  mov     qword ptr [rsp+70h+dwOptions], rsi
0x14002ffcb  mov     rdx, rbx
0x14002ffce  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002ffd5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002ffda  jmp     loc_14003043A
0x14002ffdf  lea     rax, [rbp+var_20]
0x14002ffe3  mov     [rbp+var_20], 4
0x14002ffea  mov     [rsp+70h+pcbData], rax; pcbData
0x14002ffef  lea     r8, aDpsoftwareupda_5; "DpSoftwareUpdateMode"
0x14002fff6  lea     rax, [rbp+pvData]
0x14002fffa  mov     r9d, 18h; dwFlags
0x140030000  mov     qword ptr [rsp+70h+samDesired], rax; pvData
0x140030005  mov     rdx, rbx; lpSubKey
0x140030008  mov     rcx, rsi; hkey
0x14003000b  mov     qword ptr [rsp+70h+dwOptions], rdi; pdwType
0x140030010  call    cs:__imp_RegGetValueW
0x140030016  mov     r12d, 2
0x14003001c  mov     r15d, eax
0x14003001f  cmp     eax, r12d
0x140030022  jnz     short loc_14003002E
0x140030024  mov     esi, edi
0x140030026  mov     [rbp+pvData], edi
0x140030029  jmp     loc_1400300B0
0x14003002e  test    eax, eax
0x140030030  jz      short loc_1400300AD
0x140030032  jle     short loc_14003003F
0x140030034  movzx   r15d, ax
0x140030038  or      r15d, 80070000h
0x14003003f  mov     r13d, 0C7h
0x140030045  lea     rsi, aCbraex; "CBRAEx"
0x14003004c  mov     [rsp+70h+samDesired], r15d; int
0x140030051  lea     rdi, aCsoftwareupdat_9; "CSoftwareUpdates::GetSettings"
0x140030058  mov     r9, rsi; unsigned __int16 *
0x14003005b  lea     rbx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030062  mov     r8, rdi; unsigned __int16 *
0x140030065  lea     r14, aErr0l; "err == 0L"
0x14003006c  mov     rcx, rbx; unsigned __int16 *
0x14003006f  mov     edx, r13d; unsigned int
0x140030072  mov     qword ptr [rsp+70h+dwOptions], r14; unsigned __int16 *
0x140030077  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003007c  call    cs:__imp_IsDebuggerPresent
0x140030082  test    eax, eax
0x140030084  jz      short loc_14003009B
0x140030086  mov     dword ptr [rsp+70h+var_38], r15d
0x14003008b  mov     [rsp+70h+pcbData], r14
0x140030090  mov     r9d, r13d
0x140030093  mov     ecx, r12d
0x140030096  jmp     loc_14002FF98
0x14003009b  mov     dword ptr [rsp+70h+pcbData], r15d
0x1400300a0  mov     qword ptr [rsp+70h+samDesired], r14
0x1400300a5  mov     r8d, r13d
0x1400300a8  jmp     loc_14002FFC3
0x1400300ad  mov     esi, [rbp+pvData]
0x1400300b0  cmp     esi, r12d
0x1400300b3  jbe     short loc_14003012A
0x1400300b5  mov     r14d, 8000FFFFh
0x1400300bb  lea     rax, aItempSumLast; "iTemp <= __SUM_Last"
0x1400300c2  lea     rsi, aCbraex; "CBRAEx"
0x1400300c9  mov     [rsp+70h+samDesired], r14d; int
0x1400300ce  lea     rdi, aCsoftwareupdat_9; "CSoftwareUpdates::GetSettings"
0x1400300d5  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int16 *
0x1400300da  mov     r13d, 0C9h
0x1400300e0  lea     rbx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400300e7  mov     r9, rsi; unsigned __int16 *
0x1400300ea  mov     r8, rdi; unsigned __int16 *
0x1400300ed  mov     edx, r13d; unsigned int
0x1400300f0  mov     rcx, rbx; unsigned __int16 *
0x1400300f3  mov     r15d, r14d
0x1400300f6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400300fb  call    cs:__imp_IsDebuggerPresent
0x140030101  test    eax, eax
0x140030103  lea     rax, aItempSumLast; "iTemp <= __SUM_Last"
0x14003010a  jz      short loc_14003011B
0x14003010c  mov     dword ptr [rsp+70h+var_38], r14d
0x140030111  mov     [rsp+70h+pcbData], rax
0x140030116  jmp     loc_140030090
0x14003011b  mov     dword ptr [rsp+70h+pcbData], r14d
0x140030120  mov     qword ptr [rsp+70h+samDesired], rax
0x140030125  jmp     loc_1400300A5
0x14003012a  lea     rax, [rbp+var_20]
0x14003012e  mov     [rbp+var_20], 4
0x140030135  mov     [rsp+70h+pcbData], rax; pcbData
0x14003013a  lea     r8, aDpsoftwareupda_4; "DpSoftwareUpdateStartTime"
0x140030141  lea     rax, [rbp+pvData]
0x140030145  mov     r9d, 18h; dwFlags
0x14003014b  mov     qword ptr [rsp+70h+samDesired], rax; pvData
0x140030150  mov     rdx, rbx; lpSubKey
0x140030153  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14003015a  mov     qword ptr [rsp+70h+dwOptions], rdi; pdwType
0x14003015f  call    cs:__imp_RegGetValueW
0x140030165  mov     r15d, eax
0x140030168  cmp     eax, r12d
0x14003016b  jnz     short loc_140030177
0x14003016d  mov     edi, 3
0x140030172  mov     [rbp+pvData], edi
0x140030175  jmp     short loc_140030196
0x140030177  test    eax, eax
0x140030179  jz      short loc_140030193
0x14003017b  jle     short loc_140030188
0x14003017d  movzx   r15d, ax
0x140030181  or      r15d, 80070000h
0x140030188  mov     r13d, 0D8h
0x14003018e  jmp     loc_140030045
0x140030193  mov     edi, [rbp+pvData]
0x140030196  cmp     edi, 17h
0x140030199  jbe     short loc_1400301F5
0x14003019b  mov     r14d, 8000FFFFh
0x1400301a1  lea     rax, aItemp23; "iTemp <= ( 23 )"
0x1400301a8  lea     rsi, aCbraex; "CBRAEx"
0x1400301af  mov     [rsp+70h+samDesired], r14d; int
0x1400301b4  lea     rdi, aCsoftwareupdat_9; "CSoftwareUpdates::GetSettings"
0x1400301bb  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int16 *
0x1400301c0  mov     r13d, 0DAh
0x1400301c6  lea     rbx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400301cd  mov     r9, rsi; unsigned __int16 *
0x1400301d0  mov     r8, rdi; unsigned __int16 *
0x1400301d3  mov     edx, r13d; unsigned int
0x1400301d6  mov     rcx, rbx; unsigned __int16 *
0x1400301d9  mov     r15d, r14d
0x1400301dc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400301e1  call    cs:__imp_IsDebuggerPresent
0x1400301e7  test    eax, eax
0x1400301e9  lea     rax, aItemp23; "iTemp <= ( 23 )"
0x1400301f0  jmp     loc_14003010A
0x1400301f5  mov     rdx, [rbp+hKey]
0x1400301f9  lea     r9, [rbp+Block]
0x1400301fd  lea     r8, aDpsoftwareupda; "DpSoftwareUpdateScript"
0x140030204  mov     ecx, 1
0x140030209  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x14003020e  mov     r15d, eax
0x140030211  test    eax, eax
0x140030213  js      loc_14003043A
0x140030219  lea     rax, [rbp+var_20]
0x14003021d  mov     [rbp+var_20], 4
0x140030224  mov     [rsp+70h+pcbData], rax; pcbData
0x140030229  lea     r8, aDpsoftwareupda_6; "DpSoftwareUpdateScriptMaxRuntimeMinutes"
0x140030230  lea     rax, [rbp+pvData]
0x140030234  mov     r9d, 18h; dwFlags
0x14003023a  mov     qword ptr [rsp+70h+samDesired], rax; pvData
0x14003023f  mov     rdx, rbx; lpSubKey
0x140030242  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140030249  mov     qword ptr [rsp+70h+dwOptions], 0; pdwType
0x140030252  call    cs:__imp_RegGetValueW
0x140030258  cmp     eax, r12d
0x14003025b  jnz     short loc_140030267
0x14003025d  mov     ebx, 0Fh
0x140030262  mov     [rbp+pvData], ebx
0x140030265  jmp     short loc_14003028B
0x140030267  test    eax, eax
0x140030269  jz      short loc_140030288
0x14003026b  jg      short loc_140030272
0x14003026d  mov     r15d, eax
0x140030270  jmp     short loc_14003027D
0x140030272  movzx   r15d, ax
0x140030276  or      r15d, 80070000h
0x14003027d  mov     r13d, 0EFh
0x140030283  jmp     loc_140030045
0x140030288  mov     ebx, [rbp+pvData]
0x14003028b  lea     eax, [rbx-0Fh]
0x14003028e  cmp     eax, 0A5h
0x140030293  jbe     short loc_1400302EF
0x140030295  mov     r14d, 8000FFFFh
0x14003029b  lea     rax, aItemp15Itemp18; "(iTemp >= ( 15 )) && (iTemp <= ( 180 ))"
0x1400302a2  lea     rsi, aCbraex; "CBRAEx"
0x1400302a9  mov     [rsp+70h+samDesired], r14d; int
0x1400302ae  lea     rdi, aCsoftwareupdat_9; "CSoftwareUpdates::GetSettings"
0x1400302b5  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int16 *
0x1400302ba  mov     r13d, 0F1h
0x1400302c0  lea     rbx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400302c7  mov     r9, rsi; unsigned __int16 *
0x1400302ca  mov     r8, rdi; unsigned __int16 *
0x1400302cd  mov     edx, r13d; unsigned int
0x1400302d0  mov     rcx, rbx; unsigned __int16 *
0x1400302d3  mov     r15d, r14d
0x1400302d6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400302db  call    cs:__imp_IsDebuggerPresent
0x1400302e1  test    eax, eax
0x1400302e3  lea     rax, aItemp15Itemp18; "(iTemp >= ( 15 )) && (iTemp <= ( 180 ))"
0x1400302ea  jmp     loc_14003010A
0x1400302ef  lea     rax, [rbp+var_20]
0x1400302f3  mov     [rbp+var_20], 4
0x1400302fa  mov     [rsp+70h+pcbData], rax; pcbData
0x1400302ff  lea     r8, aDpsoftwareupda_2; "DpSoftwareUpdateReturnState"
0x140030306  lea     rax, [rbp+pvData]
0x14003030a  mov     r9d, 18h; dwFlags
0x140030310  mov     qword ptr [rsp+70h+samDesired], rax; pvData
0x140030315  lea     rdx, ?s_szRegKey@CSoftwareUpdates@@0QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x14003031c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140030323  mov     qword ptr [rsp+70h+dwOptions], 0; pdwType
0x14003032c  call    cs:__imp_RegGetValueW
0x140030332  cmp     eax, r12d
0x140030335  jnz     short loc_140030341
0x140030337  mov     ecx, 1
0x14003033c  mov     [rbp+pvData], ecx
0x14003033f  jmp     short loc_140030365
0x140030341  test    eax, eax
0x140030343  jz      short loc_140030362
0x140030345  jg      short loc_14003034C
0x140030347  mov     r15d, eax
0x14003034a  jmp     short loc_140030357
0x14003034c  movzx   r15d, ax
0x140030350  or      r15d, 80070000h
0x140030357  mov     r13d, 0FFh
0x14003035d  jmp     loc_140030045
0x140030362  mov     ecx, [rbp+pvData]; this
0x140030365  cmp     ecx, 1
0x140030368  jbe     short loc_1400303C4
0x14003036a  mov     r14d, 8000FFFFh
0x140030370  lea     rax, aItempSurLast; "iTemp <= __SUR_Last"
0x140030377  lea     rsi, aCbraex; "CBRAEx"
0x14003037e  mov     [rsp+70h+samDesired], r14d; int
0x140030383  lea     rdi, aCsoftwareupdat_9; "CSoftwareUpdates::GetSettings"
0x14003038a  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned __int16 *
0x14003038f  mov     r13d, 101h
0x140030395  lea     rbx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x14003039c  mov     r9, rsi; unsigned __int16 *
0x14003039f  mov     r8, rdi; unsigned __int16 *
0x1400303a2  mov     edx, r13d; unsigned int
0x1400303a5  mov     rcx, rbx; unsigned __int16 *
0x1400303a8  mov     r15d, r14d
0x1400303ab  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400303b0  call    cs:__imp_IsDebuggerPresent
0x1400303b6  test    eax, eax
0x1400303b8  lea     rax, aItempSurLast; "iTemp <= __SUR_Last"
0x1400303bf  jmp     loc_14003010A
0x1400303c4  mov     rax, [rbp+arg_8]
0x1400303c8  lea     rdx, qword_14009C260; unsigned int
0x1400303cf  mov     r8, r12; struct Utils::SStringMap *
0x1400303d2  mov     [rax], esi
0x1400303d4  mov     rax, [rbp+Block]
0x1400303d8  mov     [r13+0], edi
0x1400303dc  mov     rdi, [rbp+arg_20]
  ... truncated ...
```

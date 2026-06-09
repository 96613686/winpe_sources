# DMCSP_DevInfo_GetHwDevID

- ea: `0x180008e10`
- end: `0x180009245`
- name: `DMCSP_DevInfo_GetHwDevID`
- size: `1077`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800052f8`
- `0x180005384`
- `0x180008318`
- `0x180008e10`
- `0x180009efe`
- `0x180009f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000912f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000912f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000914f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000914f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000906b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000906b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091f5`
- `DMCmnUtils!DMGetDeviceClientID` at `0x18000903f`
- `DMCmnUtils!DMGetDeviceClientID` at `0x18000903f`
- `DMCmnUtils!DmGetIMEI` at `0x180008fee`
- `DMCmnUtils!DmGetIMEI` at `0x180008fee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800091d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800091d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009192`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009192`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800090e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800090e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009206`
- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x180008f05`
- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x180008f05`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x180008f21`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x180008f21`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x180008f3d`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x180008f3d`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x180008f63`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x180008f63`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x180008ee3`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x180008ee3`
- `dmEnrollEngine!GetEnrollmentType` at `0x180008fc0`
- `dmEnrollEngine!GetEnrollmentType` at `0x180008fc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall DMCSP_DevInfo_GetHwDevID(unsigned __int16 *a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int64 v4; // r14
  int ValueFromStruct; // ebx
  int v7; // ecx
  LSTATUS v8; // eax
  LSTATUS ValueW; // eax
  bool v10; // sf
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v17; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v18; // [rsp+70h] [rbp-90h] BYREF
  __int128 v19; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem[2]; // [rsp+90h] [rbp-70h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v22[128]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Value[16]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 pvData; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v25[526]; // [rsp+2D2h] [rbp+1D2h] BYREF

  pguid = 0;
  v4 = a2;
  pcbData = 522;
  hKey = 0;
  pvData = 0;
  wcscpy(Value, L"DeviceID");
  memset_0(v25, 0, 0x208u);
  v14 = 63;
  memset_0(v22, 0, sizeof(v22));
  v18 = 0;
  v17 = 0;
  if ( !a3 )
  {
    ValueFromStruct = -2147024809;
    goto LABEL_39;
  }
  if ( a1 )
  {
    v22[0] = 512;
    ValueFromStruct = OmaDmSetNodeValuePresence(25, v22, 0xFFFFFFFFLL);
    if ( ValueFromStruct < 0 )
      goto LABEL_38;
    if ( (int)OmaDmGetAcctInfo(a1, 1, v22) >= 0 )
    {
      if ( (unsigned int)OmaDmIsNodePresent(25, v22, 0xFFFFFFFFLL) )
      {
        if ( (unsigned int)OmaDmIsNodeValuePresent(25, v22, 0xFFFFFFFFLL) )
        {
          ValueFromStruct = OmaDmGetValueFromStruct(25, v22, 0xFFFFFFFFLL, &v18, 0);
          if ( ValueFromStruct < 0 )
            goto LABEL_38;
        }
      }
    }
    if ( v18 && *v18 )
    {
      *(_OWORD *)hMem = 0;
      ValueFromStruct = _DmConvertInternalAccountIdToEnrollmentId(a1, (struct _GUID *)hMem);
      if ( ValueFromStruct < 0 )
        goto LABEL_38;
      v19 = *(_OWORD *)hMem;
      ValueFromStruct = GetEnrollmentType(&v19, &v14);
      if ( ValueFromStruct < 0 )
        goto LABEL_38;
      if ( v14 <= 0xB )
      {
        v7 = 2066;
        if ( _bittest(&v7, v14) )
        {
          ValueFromStruct = DmGetIMEI((unsigned __int16 **)&v17);
          if ( ValueFromStruct < 0 )
            goto LABEL_38;
          ValueFromStruct = StringCchCopyW(a3, v4, L"IMEI:");
          if ( ValueFromStruct < 0 )
            goto LABEL_38;
          ValueFromStruct = StringCchCatW(a3, v4, (const unsigned __int16 *)v17);
          goto LABEL_36;
        }
      }
    }
  }
  hMem[0] = 0;
  ValueFromStruct = DMGetDeviceClientID((unsigned __int16 **)hMem);
  if ( ValueFromStruct >= 0 )
    ValueFromStruct = StringCchCopyW(a3, v4, (const unsigned __int16 *)hMem[0]);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( ValueFromStruct < 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Provisioning\\OMADM\\HwDevID", 0, 0x20019u, &hKey);
    ValueFromStruct = v8;
    if ( !v8 )
    {
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Provisioning\\OMADM\\HwDevID",
                 Value,
                 2u,
                 0,
                 &pvData,
                 &pcbData);
      ValueFromStruct = ValueW;
      if ( ValueW > 0 )
        ValueFromStruct = (unsigned __int16)ValueW | 0x80070000;
      if ( ValueFromStruct < 0 )
        goto LABEL_38;
      ValueFromStruct = StringCchCopyW(a3, v4, &pvData);
      v10 = ValueFromStruct < 0;
      goto LABEL_37;
    }
    if ( v8 == 2 )
    {
      ValueFromStruct = CoCreateGuid(&pguid);
      if ( ValueFromStruct < 0 )
        goto LABEL_38;
      ValueFromStruct = StringFromGUID2(&pguid, a3, v4);
      if ( ValueFromStruct < 0 )
        goto LABEL_38;
      v11 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Provisioning\\OMADM\\HwDevID",
              0,
              0,
              0,
              0xF003Fu,
              0,
              &hKey,
              0);
      ValueFromStruct = v11;
      if ( v11 > 0 )
        ValueFromStruct = (unsigned __int16)v11 | 0x80070000;
      if ( ValueFromStruct < 0 )
        goto LABEL_38;
      v12 = RegSetValueExW(hKey, Value, 0, 1u, (const BYTE *)a3, v4);
      ValueFromStruct = v12;
      if ( v12 > 0 )
        ValueFromStruct = (unsigned __int16)v12 | 0x80070000;
    }
    else if ( v8 > 0 )
    {
      ValueFromStruct = (unsigned __int16)v8 | 0x80070000;
    }
LABEL_36:
    v10 = ValueFromStruct < 0;
LABEL_37:
    if ( !v10 )
      goto LABEL_39;
LABEL_38:
    *a3 = 0;
  }
LABEL_39:
  LocalFree(v17);
  RegCloseKey(hKey);
  return (unsigned int)ValueFromStruct;
}

```

## disassembly

```asm
0x180008e10  push    rbp
0x180008e12  push    rbx
0x180008e13  push    rsi
0x180008e14  push    rdi
0x180008e15  push    r12
0x180008e17  push    r14
0x180008e19  push    r15
0x180008e1b  lea     rbp, [rsp-3F0h]
0x180008e23  sub     rsp, 4F0h
0x180008e2a  mov     rax, cs:__security_cookie
0x180008e31  xor     rax, rsp
0x180008e34  mov     [rbp+420h+var_40], rax
0x180008e3b  movzx   eax, word ptr cs:aDeviceid+10h; ""
0x180008e42  xorps   xmm0, xmm0
0x180008e45  movups  xmmword ptr [rbp+420h+pguid.Data1], xmm0
0x180008e49  mov     rsi, r8
0x180008e4c  mov     r14d, edx
0x180008e4f  movups  xmm0, xmmword ptr cs:aDeviceid; "DeviceID"
0x180008e56  mov     rdi, rcx
0x180008e59  mov     [rbp+420h+var_260], ax
0x180008e60  xor     r15d, r15d
0x180008e63  mov     [rsp+520h+var_4C0], 20Ah
0x180008e6b  xor     edx, edx; Val
0x180008e6d  mov     [rsp+520h+hKey], r15
0x180008e72  mov     r8d, 208h; Size
0x180008e78  mov     [rbp+420h+var_250], r15w
0x180008e80  lea     rcx, [rbp+420h+var_24E]; void *
0x180008e87  movups  xmmword ptr [rbp+420h+Value], xmm0
0x180008e8e  call    memset_0
0x180008e93  mov     ebx, 200h
0x180008e98  mov     [rsp+520h+var_4D0], 3Fh ; '?'
0x180008ea0  mov     r8d, ebx; Size
0x180008ea3  lea     rcx, [rbp+420h+var_470]; void *
0x180008ea7  xor     edx, edx; Val
0x180008ea9  call    memset_0
0x180008eae  mov     [rsp+520h+var_4B0], r15
0x180008eb3  mov     [rsp+520h+var_4B8], r15
0x180008eb8  test    rsi, rsi
0x180008ebb  jnz     short loc_180008EC7
0x180008ebd  mov     ebx, 80070057h
0x180008ec2  jmp     loc_1800091F0
0x180008ec7  test    rdi, rdi
0x180008eca  jz      loc_180009037
0x180008ed0  or      r12d, 0FFFFFFFFh
0x180008ed4  mov     [rbp+420h+var_470], ebx
0x180008ed7  mov     r8d, r12d
0x180008eda  lea     rdx, [rbp+420h+var_470]
0x180008ede  lea     ecx, [r12+1Ah]
0x180008ee3  call    cs:__imp_OmaDmSetNodeValuePresence
0x180008eea  nop     dword ptr [rax+rax+00h]
0x180008eef  mov     ebx, eax
0x180008ef1  test    eax, eax
0x180008ef3  js      loc_1800091EC
0x180008ef9  lea     r8, [rbp+420h+var_470]
0x180008efd  mov     rcx, rdi
0x180008f00  lea     edx, [r12+2]
0x180008f05  call    cs:__imp_OmaDmGetAcctInfo
0x180008f0c  nop     dword ptr [rax+rax+00h]
0x180008f11  test    eax, eax
0x180008f13  js      short loc_180008F79
0x180008f15  mov     r8d, r12d
0x180008f18  lea     rdx, [rbp+420h+var_470]
0x180008f1c  lea     ecx, [r12+1Ah]
0x180008f21  call    cs:__imp_OmaDmIsNodePresent
0x180008f28  nop     dword ptr [rax+rax+00h]
0x180008f2d  test    eax, eax
0x180008f2f  jz      short loc_180008F79
0x180008f31  mov     r8d, r12d
0x180008f34  lea     rdx, [rbp+420h+var_470]
0x180008f38  lea     ecx, [r12+1Ah]
0x180008f3d  call    cs:__imp_OmaDmIsNodeValuePresent
0x180008f44  nop     dword ptr [rax+rax+00h]
0x180008f49  test    eax, eax
0x180008f4b  jz      short loc_180008F79
0x180008f4d  lea     r9, [rsp+520h+var_4B0]
0x180008f52  mov     [rsp+520h+phkResult], r15
0x180008f57  mov     r8d, r12d
0x180008f5a  lea     rdx, [rbp+420h+var_470]
0x180008f5e  lea     ecx, [r12+1Ah]
0x180008f63  call    cs:__imp_OmaDmGetValueFromStruct
0x180008f6a  nop     dword ptr [rax+rax+00h]
0x180008f6f  mov     ebx, eax
0x180008f71  test    eax, eax
0x180008f73  js      loc_1800091EC
0x180008f79  mov     rax, [rsp+520h+var_4B0]
0x180008f7e  test    rax, rax
0x180008f81  jz      loc_180009037
0x180008f87  cmp     [rax], r15w
0x180008f8b  jz      loc_180009037
0x180008f91  xorps   xmm0, xmm0
0x180008f94  lea     rdx, [rbp+420h+hMem]; struct _GUID *
0x180008f98  mov     rcx, rdi; unsigned __int16 *
0x180008f9b  movups  xmmword ptr [rbp+420h+hMem], xmm0
0x180008f9f  call    ?_DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z; _DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)
0x180008fa4  mov     ebx, eax
0x180008fa6  test    eax, eax
0x180008fa8  js      loc_1800091EC
0x180008fae  movaps  xmm0, xmmword ptr [rbp+420h+hMem]
0x180008fb2  lea     rdx, [rsp+520h+var_4D0]
0x180008fb7  lea     rcx, [rbp+420h+var_4A0]
0x180008fbb  movdqa  [rbp+420h+var_4A0], xmm0
0x180008fc0  call    cs:__imp_GetEnrollmentType
0x180008fc7  nop     dword ptr [rax+rax+00h]
0x180008fcc  mov     ebx, eax
0x180008fce  test    eax, eax
0x180008fd0  js      loc_1800091EC
0x180008fd6  mov     eax, [rsp+520h+var_4D0]
0x180008fda  cmp     eax, 0Bh
0x180008fdd  ja      short loc_180009037
0x180008fdf  mov     ecx, 812h
0x180008fe4  bt      ecx, eax
0x180008fe7  jnb     short loc_180009037
0x180008fe9  lea     rcx, [rsp+520h+var_4B8]
0x180008fee  call    cs:__imp_?DmGetIMEI@@YAJPEAPEAG@Z; DmGetIMEI(ushort * *)
0x180008ff5  nop     dword ptr [rax+rax+00h]
0x180008ffa  mov     ebx, eax
0x180008ffc  test    eax, eax
0x180008ffe  js      loc_1800091EC
0x180009004  lea     r8, aImei; "IMEI:"
0x18000900b  mov     rdx, r14; unsigned __int64
0x18000900e  mov     rcx, rsi; unsigned __int16 *
0x180009011  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009016  mov     ebx, eax
0x180009018  test    eax, eax
0x18000901a  js      loc_1800091EC
0x180009020  mov     r8, [rsp+520h+var_4B8]; unsigned __int16 *
0x180009025  mov     rdx, r14; unsigned __int64
0x180009028  mov     rcx, rsi; unsigned __int16 *
0x18000902b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009030  mov     ebx, eax
0x180009032  jmp     loc_1800091E8
0x180009037  lea     rcx, [rbp+420h+hMem]
0x18000903b  mov     [rbp+420h+hMem], r15
0x18000903f  call    cs:__imp_?DMGetDeviceClientID@@YAJPEAPEAG@Z; DMGetDeviceClientID(ushort * *)
0x180009046  nop     dword ptr [rax+rax+00h]
0x18000904b  mov     ebx, eax
0x18000904d  test    eax, eax
0x18000904f  js      short loc_180009062
0x180009051  mov     r8, [rbp+420h+hMem]; unsigned __int16 *
0x180009055  mov     rdx, r14; unsigned __int64
0x180009058  mov     rcx, rsi; unsigned __int16 *
0x18000905b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009060  mov     ebx, eax
0x180009062  mov     rcx, [rbp+420h+hMem]; hMem
0x180009066  test    rcx, rcx
0x180009069  jz      short loc_180009077
0x18000906b  call    cs:__imp_LocalFree
0x180009072  nop     dword ptr [rax+rax+00h]
0x180009077  test    ebx, ebx
0x180009079  jns     loc_1800091F0
0x18000907f  lea     rax, [rsp+520h+hKey]
0x180009084  mov     r12, 0FFFFFFFF80000002h
0x18000908b  lea     rdi, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\OMAD"...
0x180009092  mov     [rsp+520h+phkResult], rax; phkResult
0x180009097  mov     rdx, rdi; lpSubKey
0x18000909a  mov     rcx, r12; hKey
0x18000909d  mov     r9d, 20019h; samDesired
0x1800090a3  xor     r8d, r8d; ulOptions
0x1800090a6  call    cs:__imp_RegOpenKeyExW
0x1800090ad  nop     dword ptr [rax+rax+00h]
0x1800090b2  mov     ebx, eax
0x1800090b4  test    eax, eax
0x1800090b6  jnz     short loc_180009122
0x1800090b8  lea     rax, [rsp+520h+var_4C0]
0x1800090bd  mov     rdx, rdi; lpSubKey
0x1800090c0  mov     [rsp+520h+pcbData], rax; pcbData
0x1800090c5  lea     r9d, [rbx+2]; dwFlags
0x1800090c9  lea     rax, [rbp+420h+var_250]
0x1800090d0  mov     rcx, r12; hkey
0x1800090d3  mov     [rsp+520h+pvData], rax; pvData
0x1800090d8  lea     r8, [rbp+420h+Value]; lpValue
0x1800090df  mov     [rsp+520h+phkResult], r15; pdwType
0x1800090e4  call    cs:__imp_RegGetValueW
0x1800090eb  nop     dword ptr [rax+rax+00h]
0x1800090f0  mov     ebx, eax
0x1800090f2  test    eax, eax
0x1800090f4  jle     short loc_1800090FF
0x1800090f6  movzx   ebx, ax
0x1800090f9  or      ebx, 80070000h
0x1800090ff  test    ebx, ebx
0x180009101  js      loc_1800091EC
0x180009107  mov     rdx, r14; unsigned __int64
0x18000910a  lea     r8, [rbp+420h+var_250]; unsigned __int16 *
0x180009111  mov     rcx, rsi; unsigned __int16 *
0x180009114  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009119  mov     ebx, eax
0x18000911b  test    eax, eax
0x18000911d  jmp     loc_1800091EA
0x180009122  cmp     eax, 2
0x180009125  jnz     loc_180009236
0x18000912b  lea     rcx, [rbp+420h+pguid]; pguid
0x18000912f  call    cs:__imp_CoCreateGuid
0x180009136  nop     dword ptr [rax+rax+00h]
0x18000913b  mov     ebx, eax
0x18000913d  test    eax, eax
0x18000913f  js      loc_1800091EC
0x180009145  mov     r8d, r14d; cchMax
0x180009148  lea     rcx, [rbp+420h+pguid]; rguid
0x18000914c  mov     rdx, rsi; lpsz
0x18000914f  call    cs:__imp_StringFromGUID2
0x180009156  nop     dword ptr [rax+rax+00h]
0x18000915b  mov     ebx, eax
0x18000915d  test    eax, eax
0x18000915f  js      loc_1800091EC
0x180009165  mov     [rsp+520h+lpdwDisposition], r15; lpdwDisposition
0x18000916a  lea     rax, [rsp+520h+hKey]
0x18000916f  mov     [rsp+520h+var_4E8], rax; phkResult
0x180009174  xor     r9d, r9d; lpClass
0x180009177  mov     [rsp+520h+pcbData], r15; lpSecurityAttributes
0x18000917c  xor     r8d, r8d; Reserved
0x18000917f  mov     dword ptr [rsp+520h+pvData], 0F003Fh; samDesired
0x180009187  mov     rdx, rdi; lpSubKey
0x18000918a  mov     rcx, r12; hKey
0x18000918d  mov     dword ptr [rsp+520h+phkResult], r15d; dwOptions
0x180009192  call    cs:__imp_RegCreateKeyExW
0x180009199  nop     dword ptr [rax+rax+00h]
0x18000919e  mov     ebx, eax
0x1800091a0  mov     edi, 80070000h
0x1800091a5  test    eax, eax
0x1800091a7  jle     short loc_1800091AE
0x1800091a9  movzx   ebx, ax
0x1800091ac  or      ebx, edi
0x1800091ae  test    ebx, ebx
0x1800091b0  js      short loc_1800091EC
0x1800091b2  mov     rcx, [rsp+520h+hKey]; hKey
0x1800091b7  lea     rdx, [rbp+420h+Value]; lpValueName
0x1800091be  mov     dword ptr [rsp+520h+pvData], r14d; cbData
0x1800091c3  mov     r9d, 1; dwType
0x1800091c9  xor     r8d, r8d; Reserved
0x1800091cc  mov     [rsp+520h+phkResult], rsi; lpData
0x1800091d1  call    cs:__imp_RegSetValueExW
0x1800091d8  nop     dword ptr [rax+rax+00h]
0x1800091dd  mov     ebx, eax
0x1800091df  test    eax, eax
0x1800091e1  jle     short loc_1800091E8
0x1800091e3  movzx   ebx, ax
0x1800091e6  or      ebx, edi
0x1800091e8  test    ebx, ebx
0x1800091ea  jns     short loc_1800091F0
0x1800091ec  mov     [rsi], r15w
0x1800091f0  mov     rcx, [rsp+520h+var_4B8]; hMem
0x1800091f5  call    cs:__imp_LocalFree
0x1800091fc  nop     dword ptr [rax+rax+00h]
0x180009201  mov     rcx, [rsp+520h+hKey]; hKey
0x180009206  call    cs:__imp_RegCloseKey
0x18000920d  nop     dword ptr [rax+rax+00h]
0x180009212  mov     eax, ebx
0x180009214  mov     rcx, [rbp+420h+var_40]
0x18000921b  xor     rcx, rsp; StackCookie
0x18000921e  call    __security_check_cookie
0x180009223  add     rsp, 4F0h
0x18000922a  pop     r15
0x18000922c  pop     r14
0x18000922e  pop     r12
0x180009230  pop     rdi
0x180009231  pop     rsi
0x180009232  pop     rbx
0x180009233  pop     rbp
0x180009234  retn
0x180009236  test    eax, eax
0x180009238  jle     short loc_1800091E8
0x18000923a  movzx   ebx, ax
0x18000923d  or      ebx, 80070000h
0x180009243  jmp     short loc_1800091E8
```

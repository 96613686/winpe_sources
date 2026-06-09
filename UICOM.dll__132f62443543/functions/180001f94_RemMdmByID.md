# RemMdmByID

- ea: `0x180001f94`
- end: `0x180002266`
- name: `RemMdmByID`
- size: `722`
- prototype: `__int64 __fastcall(PCNZWCH lpString2, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005970`

## callees

- `0x180001f6c`
- `0x180001f94`
- `0x180005f60`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000210d`
- `KERNEL32!CompareStringW` at `0x18000210d`
- `KERNEL32!LocalAlloc` at `0x1800020b7`
- `KERNEL32!LocalAlloc` at `0x1800020b7`
- `KERNEL32!GetLastError` at `0x18000200d`
- `KERNEL32!GetLastError` at `0x180002026`
- `KERNEL32!GetLastError` at `0x180002093`
- `KERNEL32!GetLastError` at `0x180002163`
- `KERNEL32!GetLastError` at `0x180002175`
- `KERNEL32!GetLastError` at `0x1800021cc`
- `KERNEL32!GetLastError` at `0x18000220b`
- `KERNEL32!GetLastError` at `0x180002222`
- `KERNEL32!GetLastError` at `0x18000200d`
- `KERNEL32!GetLastError` at `0x180002026`
- `KERNEL32!GetLastError` at `0x180002093`
- `KERNEL32!GetLastError` at `0x180002163`
- `KERNEL32!GetLastError` at `0x180002175`
- `KERNEL32!GetLastError` at `0x1800021cc`
- `KERNEL32!GetLastError` at `0x18000220b`
- `KERNEL32!GetLastError` at `0x180002222`
- `KERNEL32!LocalFree` at `0x18000212a`
- `KERNEL32!LocalFree` at `0x180002191`
- `KERNEL32!LocalFree` at `0x18000212a`
- `KERNEL32!LocalFree` at `0x180002191`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x18000208b`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800020e3`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x18000208b`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800020e3`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180002201`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180002201`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180002155`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180002155`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000223a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000223a`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180002062`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180002062`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001ffe`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001ffe`

## string_xrefs

- `0x180002169`: `RemMdmByID: SetupDiSetClassInstallParams failed : %#lx`
- `0x180002211`: `RemMdmByID: SetupDiCallClassInstaller failed : %#lx`

## pseudocode

```c
__int64 __fastcall RemMdmByID(PCNZWCH lpString2, int a2)
{
  __int64 v3; // rdi
  HDEVINFO ClassDevsW; // r14
  DWORD LastError; // eax
  signed int v6; // eax
  DWORD v7; // r15d
  int v8; // r12d
  BOOL DeviceInstanceIdW; // ebx
  DWORD v10; // eax
  WCHAR *v11; // rax
  WCHAR *v12; // rbx
  int v13; // edi
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  signed int v17; // eax
  DWORD RequiredSize; // [rsp+30h] [rbp-40h] BYREF
  int v20; // [rsp+34h] [rbp-3Ch]
  _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+40h] [rbp-30h]
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+48h] [rbp-28h] BYREF

  v20 = a2;
  ClassInstallParams.cbSize = 8;
  ClassInstallParams.InstallFunction = 5;
  v22 = 1;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  if ( !lpString2 )
  {
    LODWORD(v3) = -2147024809;
    return (unsigned int)v3;
  }
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVCLASS_MODEM, 0, 0, 0);
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    OutputDebugMsgW(4, L"RemMdmByID: SetupDiGetClassDevs failed : %#lx", LastError);
    v6 = GetLastError();
    LODWORD(v3) = v6;
    if ( v6 > 0 )
      LODWORD(v3) = (unsigned __int16)v6 | 0x80070000;
    return (unsigned int)v3;
  }
  v7 = 0;
  DeviceInfoData.cbSize = 32;
  v8 = 0;
  do
  {
    RequiredSize = 0;
    if ( !SetupDiEnumDeviceInfo(ClassDevsW, v7, &DeviceInfoData) )
    {
      LODWORD(v3) = 1168;
      v15 = GetLastError();
      OutputDebugMsgW(4, L"RemMdmByID: SetupDiEnumDeviceInfo failed : %#lx", v15);
      goto LABEL_24;
    }
    DeviceInstanceIdW = SetupDiGetDeviceInstanceIdW(ClassDevsW, &DeviceInfoData, 0, 0, &RequiredSize);
    v10 = GetLastError();
    LODWORD(v3) = v10;
    if ( DeviceInstanceIdW || v10 != 122 )
    {
      OutputDebugMsgW(4, L"RemMdmByID: SetupGetDeviceInstanceId returned %#lx instead of %#lx", v10, 122);
      goto LABEL_24;
    }
    v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * (RequiredSize + 1));
    v12 = v11;
    if ( !v11 )
    {
      OutputDebugMsgW(4, L"RemMdmByID: Couldn't allocate memory for pCurDevInstID");
      LODWORD(v3) = 14;
      goto LABEL_24;
    }
    if ( !SetupDiGetDeviceInstanceIdW(ClassDevsW, &DeviceInfoData, v11, RequiredSize + 1, 0) )
    {
      v3 = GetLastError();
      OutputDebugMsgW(4, L"RemMdmByID: SetupDiGetDeviceInstanceId returned %#lx", v3);
      LocalFree(v12);
LABEL_24:
      if ( (int)v3 <= 0 )
        goto LABEL_31;
      LODWORD(v3) = (unsigned __int16)v3;
      goto LABEL_30;
    }
    v13 = CompareStringW(0x400u, 0, v12, RequiredSize, lpString2, v20 - 1);
    if ( v13 == 2 )
      v8 = 1;
    else
      DeviceInfoData.cbSize = 32;
    LocalFree(v12);
    if ( v13 != 2 )
      ++v7;
  }
  while ( !v8 );
  if ( SetupDiSetClassInstallParamsW(ClassDevsW, &DeviceInfoData, &ClassInstallParams, 0x10u) )
  {
    LODWORD(v3) = 0;
    if ( SetupDiCallClassInstaller(5u, ClassDevsW, &DeviceInfoData) )
      goto LABEL_31;
    v16 = GetLastError();
    OutputDebugMsgW(4, L"RemMdmByID: SetupDiCallClassInstaller failed : %#lx", v16);
  }
  else
  {
    v14 = GetLastError();
    OutputDebugMsgW(4, L"RemMdmByID: SetupDiSetClassInstallParams failed : %#lx", v14);
  }
  v17 = GetLastError();
  LODWORD(v3) = v17;
  if ( v17 > 0 )
  {
    LODWORD(v3) = (unsigned __int16)v17;
LABEL_30:
    LODWORD(v3) = v3 | 0x80070000;
  }
LABEL_31:
  SetupDiDestroyDeviceInfoList(ClassDevsW);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001f94  mov     [rsp-38h+arg_10], rbx
0x180001f99  push    rbp
0x180001f9a  push    rsi
0x180001f9b  push    rdi
0x180001f9c  push    r12
0x180001f9e  push    r13
0x180001fa0  push    r14
0x180001fa2  push    r15
0x180001fa4  mov     rbp, rsp
0x180001fa7  sub     rsp, 70h
0x180001fab  mov     rax, cs:__security_cookie
0x180001fb2  xor     rax, rsp
0x180001fb5  mov     [rbp+var_8], rax
0x180001fb9  mov     [rbp+var_3C], edx
0x180001fbc  xorps   xmm0, xmm0
0x180001fbf  mov     [rbp+ClassInstallParams.cbSize], 8
0x180001fc6  mov     r13, rcx
0x180001fc9  mov     [rbp+ClassInstallParams.InstallFunction], 5
0x180001fd0  mov     [rbp+var_30], 1
0x180001fd8  movups  xmmword ptr [rbp+DeviceInfoData.cbSize], xmm0
0x180001fdc  movups  xmmword ptr [rbp+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180001fe0  test    rcx, rcx
0x180001fe3  jnz     short loc_180001FEF
0x180001fe5  mov     edi, 80070057h
0x180001fea  jmp     loc_180002240
0x180001fef  xor     r9d, r9d; Flags
0x180001ff2  lea     rcx, GUID_DEVCLASS_MODEM; ClassGuid
0x180001ff9  xor     r8d, r8d; hwndParent
0x180001ffc  xor     edx, edx; Enumerator
0x180001ffe  call    cs:__imp_SetupDiGetClassDevsW
0x180002004  mov     r14, rax
0x180002007  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000200b  jnz     short loc_180002044
0x18000200d  call    cs:__imp_GetLastError
0x180002013  mov     r8d, eax
0x180002016  lea     rdx, aRemmdmbyidSetu_2; "RemMdmByID: SetupDiGetClassDevs failed "...
0x18000201d  lea     ecx, [r14+5]
0x180002021  call    OutputDebugMsgW
0x180002026  call    cs:__imp_GetLastError
0x18000202c  mov     edi, eax
0x18000202e  test    eax, eax
0x180002030  jle     loc_180002240
0x180002036  movzx   edi, ax
0x180002039  or      edi, 80070000h
0x18000203f  jmp     loc_180002240
0x180002044  xor     r15d, r15d
0x180002047  mov     [rbp+DeviceInfoData.cbSize], 20h ; ' '
0x18000204e  xor     r12d, r12d
0x180002051  lea     r8, [rbp+DeviceInfoData]; DeviceInfoData
0x180002055  mov     [rbp+var_40], 0
0x18000205c  mov     edx, r15d; MemberIndex
0x18000205f  mov     rcx, r14; DeviceInfoSet
0x180002062  call    cs:__imp_SetupDiEnumDeviceInfo
0x180002068  mov     esi, 4
0x18000206d  test    eax, eax
0x18000206f  jz      loc_1800021C7
0x180002075  lea     rax, [rbp+var_40]
0x180002079  xor     r9d, r9d; DeviceInstanceIdSize
0x18000207c  xor     r8d, r8d; DeviceInstanceId
0x18000207f  mov     [rsp+70h+RequiredSize], rax; RequiredSize
0x180002084  lea     rdx, [rbp+DeviceInfoData]; DeviceInfoData
0x180002088  mov     rcx, r14; DeviceInfoSet
0x18000208b  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180002091  mov     ebx, eax
0x180002093  call    cs:__imp_GetLastError
0x180002099  mov     edi, eax
0x18000209b  test    ebx, ebx
0x18000209d  jnz     loc_1800021AE
0x1800020a3  cmp     eax, 7Ah ; 'z'
0x1800020a6  jnz     loc_1800021AE
0x1800020ac  mov     edx, [rbp+var_40]
0x1800020af  lea     ecx, [rsi+3Ch]; uFlags
0x1800020b2  inc     edx
0x1800020b4  add     rdx, rdx; uBytes
0x1800020b7  call    cs:__imp_LocalAlloc
0x1800020bd  mov     rbx, rax
0x1800020c0  test    rax, rax
0x1800020c3  jz      loc_180002199
0x1800020c9  mov     r9d, [rbp+var_40]
0x1800020cd  lea     rdx, [rbp+DeviceInfoData]; DeviceInfoData
0x1800020d1  inc     r9d; DeviceInstanceIdSize
0x1800020d4  mov     [rsp+70h+RequiredSize], 0; RequiredSize
0x1800020dd  mov     r8, rax; DeviceInstanceId
0x1800020e0  mov     rcx, r14; DeviceInfoSet
0x1800020e3  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x1800020e9  test    eax, eax
0x1800020eb  jz      loc_180002175
0x1800020f1  mov     eax, [rbp+var_3C]
0x1800020f4  mov     r8, rbx; lpString1
0x1800020f7  mov     r9d, [rbp+var_40]; cchCount1
0x1800020fb  dec     eax
0x1800020fd  mov     [rsp+70h+cchCount2], eax; cchCount2
0x180002101  xor     edx, edx; dwCmpFlags
0x180002103  mov     ecx, 400h; Locale
0x180002108  mov     [rsp+70h+RequiredSize], r13; lpString2
0x18000210d  call    cs:__imp_CompareStringW
0x180002113  mov     edi, eax
0x180002115  cmp     eax, 2
0x180002118  jnz     short loc_180002120
0x18000211a  lea     r12d, [rsi-3]
0x18000211e  jmp     short loc_180002127
0x180002120  mov     [rbp+DeviceInfoData.cbSize], 20h ; ' '
0x180002127  mov     rcx, rbx; hMem
0x18000212a  call    cs:__imp_LocalFree
0x180002130  cmp     edi, 2
0x180002133  lea     eax, [r15+1]
0x180002137  cmovnz  r15d, eax
0x18000213b  test    r12d, r12d
0x18000213e  jz      loc_180002051
0x180002144  mov     r9d, 10h; ClassInstallParamsSize
0x18000214a  lea     r8, [rbp+ClassInstallParams]; ClassInstallParams
0x18000214e  lea     rdx, [rbp+DeviceInfoData]; DeviceInfoData
0x180002152  mov     rcx, r14; DeviceInfoSet
0x180002155  call    cs:__imp_SetupDiSetClassInstallParamsW
0x18000215b  test    eax, eax
0x18000215d  jnz     loc_1800021F5
0x180002163  call    cs:__imp_GetLastError
0x180002169  lea     rdx, aRemmdmbyidSetu_0; "RemMdmByID: SetupDiSetClassInstallParam"...
0x180002170  jmp     loc_180002218
0x180002175  call    cs:__imp_GetLastError
0x18000217b  lea     rdx, aRemmdmbyidSetu; "RemMdmByID: SetupDiGetDeviceInstanceId "...
0x180002182  mov     ecx, esi
0x180002184  mov     r8d, eax
0x180002187  mov     edi, eax
0x180002189  call    OutputDebugMsgW
0x18000218e  mov     rcx, rbx; hMem
0x180002191  call    cs:__imp_LocalFree
0x180002197  jmp     short loc_1800021E3
0x180002199  lea     rdx, aRemmdmbyidCoul; "RemMdmByID: Couldn't allocate memory fo"...
0x1800021a0  mov     ecx, esi
0x1800021a2  call    OutputDebugMsgW
0x1800021a7  mov     edi, 0Eh
0x1800021ac  jmp     short loc_1800021E3
0x1800021ae  mov     r9d, 7Ah ; 'z'
0x1800021b4  lea     rdx, aRemmdmbyidSetu_1; "RemMdmByID: SetupGetDeviceInstanceId re"...
0x1800021bb  mov     r8d, eax
0x1800021be  mov     ecx, esi
0x1800021c0  call    OutputDebugMsgW
0x1800021c5  jmp     short loc_1800021E3
0x1800021c7  mov     edi, 490h
0x1800021cc  call    cs:__imp_GetLastError
0x1800021d2  lea     rdx, aRemmdmbyidSetu_3; "RemMdmByID: SetupDiEnumDeviceInfo faile"...
0x1800021d9  mov     ecx, esi
0x1800021db  mov     r8d, eax
0x1800021de  call    OutputDebugMsgW
0x1800021e3  test    r12d, r12d
0x1800021e6  jnz     loc_180002144
0x1800021ec  test    edi, edi
0x1800021ee  jle     short loc_180002237
0x1800021f0  movzx   edi, di
0x1800021f3  jmp     short loc_180002231
0x1800021f5  xor     edi, edi
0x1800021f7  lea     r8, [rbp+DeviceInfoData]; DeviceInfoData
0x1800021fb  mov     rdx, r14; DeviceInfoSet
0x1800021fe  lea     ecx, [rdi+5]; InstallFunction
0x180002201  call    cs:__imp_SetupDiCallClassInstaller
0x180002207  test    eax, eax
0x180002209  jnz     short loc_180002237
0x18000220b  call    cs:__imp_GetLastError
0x180002211  lea     rdx, aRemmdmbyidSetu_4; "RemMdmByID: SetupDiCallClassInstaller f"...
0x180002218  mov     r8d, eax
0x18000221b  mov     ecx, esi
0x18000221d  call    OutputDebugMsgW
0x180002222  call    cs:__imp_GetLastError
0x180002228  mov     edi, eax
0x18000222a  test    eax, eax
0x18000222c  jle     short loc_180002237
0x18000222e  movzx   edi, ax
0x180002231  or      edi, 80070000h
0x180002237  mov     rcx, r14; DeviceInfoSet
0x18000223a  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180002240  mov     eax, edi
0x180002242  mov     rcx, [rbp+var_8]
0x180002246  xor     rcx, rsp; StackCookie
0x180002249  call    __security_check_cookie
0x18000224e  mov     rbx, [rsp+70h+arg_10]
0x180002256  add     rsp, 70h
0x18000225a  pop     r15
0x18000225c  pop     r14
0x18000225e  pop     r13
0x180002260  pop     r12
0x180002262  pop     rdi
0x180002263  pop     rsi
0x180002264  pop     rbp
0x180002265  retn
```

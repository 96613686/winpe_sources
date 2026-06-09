# LogDeviceAccessEnforcementForUserSession

- ea: `0x180013038`
- end: `0x180013797`
- name: `LogDeviceAccessEnforcementForUserSession`
- size: `1887`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014048`

## callees

- `0x180005670`
- `0x1800097d0`
- `0x18000a192`
- `0x1800105e4`
- `0x180012de4`
- `0x180013038`
- `0x180014150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800135c2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800135d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800136d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800136e4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800135c2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800135d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800136d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800136e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001328c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001328c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001333c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001333c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013350`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800134fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800134fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001330b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013328`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001330b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013328`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001313d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001313d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013230`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013230`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800132a7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800132a7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800131ad`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800131ad`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013197`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013197`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013541`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001355e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013541`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001355e`
- `WTSAPI32!WTSQueryUserToken` at `0x18001315b`
- `WTSAPI32!WTSQueryUserToken` at `0x18001315b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18001327e`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18001327e`
- `WTSAPI32!WTSFreeMemory` at `0x18001331a`
- `WTSAPI32!WTSFreeMemory` at `0x18001331a`

## string_xrefs

- `0x1800135b0`: `WPDDevicesDenyWriteAccess`
- `0x1800136c0`: `WPDDevicesDenyReadAccess`

## pseudocode

```c
__int64 __fastcall LogDeviceAccessEnforcementForUserSession(
        __int64 a1,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        ULONG *a4,
        unsigned int a5,
        __int64 a6,
        int a7)
{
  DWORD LastError; // ebx
  unsigned __int16 *v9; // r12
  unsigned __int16 *v10; // rdi
  unsigned __int16 *v11; // rsi
  unsigned __int16 *v12; // r15
  PSID *v13; // r14
  HLOCAL v14; // r13
  unsigned int i; // r13d
  PSID v16; // rdx
  int v17; // ecx
  DWORD DeviceProperty; // eax
  struct _SP_DEVINFO_DATA *v20; // r13
  HDEVINFO v21; // r14
  unsigned __int16 *v22; // rax
  wchar_t *v23; // rcx
  const wchar_t *v24; // r14
  OLECHAR *p_sz; // rax
  const unsigned __int16 *v26; // r11
  const unsigned __int16 *v27; // r10
  OLECHAR *v28; // rax
  const unsigned __int16 *v29; // r9
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *v32; // rcx
  OLECHAR *v33; // r14
  const unsigned __int16 *v34; // r11
  const unsigned __int16 *v35; // r10
  OLECHAR *v36; // rax
  const unsigned __int16 *v37; // r9
  const unsigned __int16 *v38; // r8
  const unsigned __int16 *v39; // rdx
  const unsigned __int16 *v40; // rcx
  HLOCAL v41; // [rsp+60h] [rbp-A0h] BYREF
  PSID *v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned int uBytes; // [rsp+70h] [rbp-90h] BYREF
  int uBytes_4; // [rsp+74h] [rbp-8Ch]
  unsigned __int16 *v45; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL IsMember; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h] BYREF
  PSID SidToCheck; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR ppBuffer; // [rsp+A0h] [rbp-60h] BYREF
  DWORD pBytesReturned; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+ACh] [rbp-54h] BYREF
  _DWORD v53[3]; // [rsp+B4h] [rbp-4Ch] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp-40h] BYREF
  HLOCAL v55; // [rsp+C8h] [rbp-38h] BYREF
  void *phToken; // [rsp+D0h] [rbp-30h] BYREF
  void *phNewToken; // [rsp+D8h] [rbp-28h] BYREF
  HDEVINFO DeviceInfoSet; // [rsp+E0h] [rbp-20h]
  __int64 v59; // [rsp+E8h] [rbp-18h]
  DWORD *v60; // [rsp+F0h] [rbp-10h]
  PSP_DEVINFO_DATA DeviceInfoData; // [rsp+F8h] [rbp-8h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz; // [rsp+110h] [rbp+10h] BYREF
  char v64[78]; // [rsp+112h] [rbp+12h] BYREF
  OLECHAR v65; // [rsp+160h] [rbp+60h] BYREF
  char v66[78]; // [rsp+162h] [rbp+62h] BYREF
  __int16 v67; // [rsp+1B0h] [rbp+B0h] BYREF
  char v68[78]; // [rsp+1B2h] [rbp+B2h] BYREF
  __int16 v69; // [rsp+200h] [rbp+100h] BYREF
  char v70[78]; // [rsp+202h] [rbp+102h] BYREF

  LastError = 0;
  DeviceInfoData = a3;
  DeviceInfoSet = a2;
  v60 = a4;
  v59 = a6;
  v9 = 0;
  ppBuffer = 0;
  sz = 0;
  memset_0(v64, 0, sizeof(v64));
  v65 = 0;
  memset_0(v66, 0, sizeof(v66));
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  hMem = 0;
  phToken = (void *)-1LL;
  phNewToken = (void *)-1LL;
  v10 = 0;
  v45 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v55 = 0;
  v48 = 0;
  v41 = 0;
  pBytesReturned = 0;
  uBytes = 0;
  v52 = 0;
  v47 = 0;
  memset(v53, 0, sizeof(v53));
  SidToCheck = 0;
  v42 = 0;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    LastError = GetLastError();
  if ( LastError )
    goto LABEL_6;
  if ( !WTSQueryUserToken(*a4, &phToken)
    || !DuplicateTokenEx(phToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken)
    || !CheckTokenMembership(phNewToken, SidToCheck, &IsMember) )
  {
    LastError = GetLastError();
LABEL_6:
    v14 = v41;
    goto LABEL_29;
  }
  if ( !IsMember )
    goto LABEL_6;
  LastError = GetUserInformation(*a4, 0, &v42, 0, 0, 0);
  if ( LastError )
    goto LABEL_27;
  uBytes_4 = 0;
  for ( i = 0; i < a5; ++i )
  {
    if ( !*(_DWORD *)(v59 + 48LL * i + 28) && *(_DWORD *)(v59 + 48LL * i + 4) == 3 )
    {
      v16 = a7 ? *v42 : SidToCheck;
      if ( EqualSid(*(PSID *)(v59 + 48LL * i + 40), v16) )
      {
        v17 = *(_DWORD *)(v59 + 48LL * i);
        uBytes_4 = v17;
        goto LABEL_22;
      }
    }
  }
  v17 = 0;
LABEL_22:
  *(_DWORD *)pIdentifierAuthority.Value = v17 & 0x120116;
  if ( (v17 & 0x120116) == 0 && (v17 & 0x120089) == 0 )
    goto LABEL_27;
  if ( !WTSQuerySessionInformationW(0, *v60, WTSUserName, &ppBuffer, &pBytesReturned) )
  {
    DeviceProperty = GetLastError();
LABEL_26:
    LastError = DeviceProperty;
    goto LABEL_27;
  }
  v20 = DeviceInfoData;
  v21 = DeviceInfoSet;
  DeviceProperty = GetDeviceProperty(
                     DeviceInfoSet,
                     DeviceInfoData,
                     (DEVPROPKEY *)&DEVPKEY_Device_HardwareIds,
                     (__int64)&hMem,
                     (__int64)&uBytes);
  if ( DeviceProperty && DeviceProperty != 1168 )
    goto LABEL_26;
  DeviceProperty = GetDeviceProperty(v21, v20, (DEVPROPKEY *)&DEVPKEY_Device_InstanceId, (__int64)&v45, (__int64)&v52);
  if ( DeviceProperty && DeviceProperty != 1168
    || (DeviceProperty = GetDeviceProperty(
                           v21,
                           v20,
                           (DEVPROPKEY *)&DEVPKEY_Device_BusTypeGuid,
                           (__int64)&v55,
                           (__int64)&v47)) != 0
    && DeviceProperty != 1168 )
  {
    v10 = v45;
    goto LABEL_26;
  }
  DeviceProperty = GetDeviceProperty(v21, v20, (DEVPROPKEY *)&DEVPKEY_Device_Class, (__int64)&v48, (__int64)&v52 + 4);
  if ( DeviceProperty && DeviceProperty != 1168
    || (DeviceProperty = GetDeviceProperty(
                           v21,
                           v20,
                           (DEVPROPKEY *)&DEVPKEY_Device_ClassGuid,
                           (__int64)&v41,
                           (__int64)&v47 + 4)) != 0
    && DeviceProperty != 1168 )
  {
    v10 = v45;
    v11 = (unsigned __int16 *)v48;
    goto LABEL_26;
  }
  DeviceProperty = GetDeviceProperty(v21, v20, (DEVPROPKEY *)&DEVPKEY_NAME, (__int64)&v53[1], (__int64)v53);
  if ( DeviceProperty && DeviceProperty != 1168 )
  {
    v10 = v45;
    v11 = (unsigned __int16 *)v48;
    v12 = *(unsigned __int16 **)&v53[1];
    goto LABEL_26;
  }
  v22 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes);
  v23 = (wchar_t *)hMem;
  v9 = v22;
  if ( !hMem || !*(_BYTE *)hMem )
    v23 = (wchar_t *)&Source;
  ConvertRegMultiSzToCsv(v23);
  if ( (_DWORD)v47 )
    StringFromGUID2((const GUID *const)v55, &sz, 40);
  v14 = v41;
  if ( HIDWORD(v47) )
    StringFromGUID2((const GUID *const)v41, &v65, 40);
  v10 = v45;
  v24 = L"PerUser";
  v11 = (unsigned __int16 *)v48;
  if ( !a7 )
    v24 = L"PerDevice";
  v12 = *(unsigned __int16 **)&v53[1];
  if ( *(_DWORD *)pIdentifierAuthority.Value )
  {
    v67 = 0;
    memset_0(v68, 0, sizeof(v68));
    _o_wcscat_s(&v67, 40, L"WPDDevicesDenyWriteAccess");
    _o_wcscat_s(&v67, 40, v24);
    p_sz = &sz;
    if ( !sz )
      p_sz = (OLECHAR *)&Source;
    DeviceInfoSet = p_sz;
    if ( !v10 || (v26 = v10, !*(_BYTE *)v10) )
      v26 = &Source;
    if ( !v9 || (v27 = v9, !*v9) )
      v27 = &Source;
    v28 = &v65;
    if ( !v65 )
      v28 = (OLECHAR *)&Source;
    if ( !v11 || (v29 = v11, !*(_BYTE *)v11) )
      v29 = &Source;
    if ( !v12 || (v30 = v12, !*(_BYTE *)v12) )
      v30 = &Source;
    v31 = ppBuffer;
    if ( !ppBuffer || !*ppBuffer )
      v31 = &Source;
    v32 = (const unsigned __int16 *)&v67;
    if ( !v67 )
      v32 = &Source;
    LogAccessDenial(v32, v31, v30, v29, v28, v27, v26, (const unsigned __int16 *)DeviceInfoSet);
    v14 = v41;
  }
  if ( (uBytes_4 & 0x120089) == 0 )
    goto LABEL_28;
  v69 = 0;
  memset_0(v70, 0, sizeof(v70));
  _o_wcscat_s(&v69, 40, L"WPDDevicesDenyReadAccess");
  _o_wcscat_s(&v69, 40, v24);
  v33 = &sz;
  if ( !sz )
    v33 = (OLECHAR *)&Source;
  if ( !v10 || (v34 = v10, !*(_BYTE *)v10) )
    v34 = &Source;
  if ( !v9 || (v35 = v9, !*v9) )
    v35 = &Source;
  v36 = &v65;
  if ( !v65 )
    v36 = (OLECHAR *)&Source;
  if ( !v11 || (v37 = v11, !*(_BYTE *)v11) )
    v37 = &Source;
  if ( !v12 || (v38 = v12, !*(_BYTE *)v12) )
    v38 = &Source;
  v39 = ppBuffer;
  if ( !ppBuffer || !*ppBuffer )
    v39 = &Source;
  v40 = (const unsigned __int16 *)&v69;
  if ( !v69 )
    v40 = &Source;
  LogAccessDenial(v40, v39, v38, v37, v36, v35, v34, v33);
LABEL_27:
  v14 = v41;
LABEL_28:
  v13 = v42;
LABEL_29:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( hMem )
    LocalFree(hMem);
  if ( v10 )
    LocalFree(v10);
  if ( v55 )
    LocalFree(v55);
  if ( v11 )
    LocalFree(v11);
  if ( v14 )
    LocalFree(v14);
  if ( v12 )
    LocalFree(v12);
  if ( v9 )
    LocalFree(v9);
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( v13 )
    LocalFree(v13);
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  if ( (char *)phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phNewToken);
  return LastError;
}

```

## disassembly

```asm
0x180013038  mov     [rsp-8+arg_0], rbx
0x18001303d  push    rbp
0x18001303e  push    rsi
0x18001303f  push    rdi
0x180013040  push    r12
0x180013042  push    r13
0x180013044  push    r14
0x180013046  push    r15
0x180013048  lea     rbp, [rsp-160h]
0x180013050  sub     rsp, 260h
0x180013057  mov     rax, cs:__security_cookie
0x18001305e  xor     rax, rsp
0x180013061  mov     [rbp+190h+var_40], rax
0x180013068  mov     rax, [rbp+190h+arg_28]
0x18001306f  lea     rcx, [rbp+190h+var_17E]; void *
0x180013073  xor     ebx, ebx
0x180013075  mov     [rbp+190h+DeviceInfoData], r8
0x180013079  mov     [rbp+190h+DeviceInfoSet], rdx
0x18001307d  mov     r13, r9
0x180013080  xor     edx, edx; Val
0x180013082  mov     [rbp+190h+var_1A0], r9
0x180013086  mov     [rbp+190h+var_1A8], rax
0x18001308a  mov     r12d, ebx
0x18001308d  lea     edi, [rbx+4Eh]
0x180013090  mov     [rbp+190h+ppBuffer], rbx
0x180013094  mov     r8d, edi; Size
0x180013097  mov     [rbp+190h+sz], bx
0x18001309b  call    memset_0
0x1800130a0  mov     r8d, edi; Size
0x1800130a3  mov     [rbp+190h+var_130], bx
0x1800130a7  xor     edx, edx; Val
0x1800130a9  lea     rcx, [rbp+190h+var_12E]; void *
0x1800130ad  call    memset_0
0x1800130b2  xor     ecx, ecx
0x1800130b4  mov     word ptr [rbp+190h+pIdentifierAuthority.Value+4], 500h
0x1800130ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800130be  mov     [rbp+190h+hMem], rcx
0x1800130c2  mov     [rbp+190h+phToken], rax
0x1800130c6  lea     r8d, [rbx+4]; nSubAuthority0
0x1800130ca  mov     [rbp+190h+phNewToken], rax
0x1800130ce  mov     edi, ecx
0x1800130d0  lea     rax, [rbp+190h+SidToCheck]
0x1800130d4  mov     [rsp+290h+var_218], rcx
0x1800130d9  mov     [rsp+290h+pSid], rax; pSid
0x1800130de  mov     esi, ecx
0x1800130e0  mov     [rsp+290h+nSubAuthority7], ecx; nSubAuthority7
0x1800130e4  mov     r15d, ecx
0x1800130e7  mov     [rsp+290h+nSubAuthority6], ecx; nSubAuthority6
0x1800130eb  mov     r14d, ecx
0x1800130ee  mov     [rsp+290h+nSubAuthority5], ecx; nSubAuthority5
0x1800130f2  xor     r9d, r9d; nSubAuthority1
0x1800130f5  mov     [rsp+290h+nSubAuthority4], ecx; nSubAuthority4
0x1800130f9  mov     dl, 1; nSubAuthorityCount
0x1800130fb  mov     [rsp+290h+nSubAuthority3], ecx; nSubAuthority3
0x1800130ff  mov     [rsp+290h+nSubAuthority2], ecx; nSubAuthority2
0x180013103  mov     [rbp+190h+var_1C8], rcx
0x180013107  mov     [rbp+190h+var_200], rcx
0x18001310b  mov     [rsp+290h+var_230], rcx
0x180013110  mov     qword ptr [rbp+190h+var_1DC+4], rcx
0x180013114  mov     [rbp+190h+pBytesReturned], ecx
0x180013117  mov     dword ptr [rsp+290h+uBytes], ecx
0x18001311b  mov     dword ptr [rbp+190h+var_1E4], ecx
0x18001311e  mov     dword ptr [rbp+190h+var_20C], ecx
0x180013121  mov     dword ptr [rbp+190h+var_1E4+4], ecx
0x180013124  mov     dword ptr [rbp+190h+var_20C+4], ecx
0x180013127  mov     dword ptr [rbp+190h+var_1DC], ecx
0x18001312a  mov     [rbp+190h+SidToCheck], rcx
0x18001312e  mov     [rsp+290h+var_228], rcx
0x180013133  mov     [rbp+190h+IsMember], ecx
0x180013136  mov     dword ptr [rbp+190h+pIdentifierAuthority.Value], ecx
0x180013139  lea     rcx, [rbp+190h+pIdentifierAuthority]; pIdentifierAuthority
0x18001313d  call    cs:__imp_AllocateAndInitializeSid
0x180013143  test    eax, eax
0x180013145  jnz     short loc_18001314F
0x180013147  call    cs:__imp_GetLastError
0x18001314d  mov     ebx, eax
0x18001314f  test    ebx, ebx
0x180013151  jnz     short loc_18001316D
0x180013153  mov     ecx, [r13+0]; SessionId
0x180013157  lea     rdx, [rbp+190h+phToken]; phToken
0x18001315b  call    cs:__imp_WTSQueryUserToken
0x180013161  test    eax, eax
0x180013163  jnz     short loc_180013177
0x180013165  call    cs:__imp_GetLastError
0x18001316b  mov     ebx, eax
0x18001316d  mov     r13, [rsp+290h+var_230]
0x180013172  jmp     loc_18001329E
0x180013177  mov     rcx, [rbp+190h+phToken]; hExistingToken
0x18001317b  lea     rax, [rbp+190h+phNewToken]
0x18001317f  mov     r9d, 2; ImpersonationLevel
0x180013185  mov     qword ptr [rsp+290h+nSubAuthority3], rax; phNewToken
0x18001318a  xor     r8d, r8d; lpTokenAttributes
0x18001318d  mov     [rsp+290h+nSubAuthority2], r9d; TokenType
0x180013192  mov     edx, 2000000h; dwDesiredAccess
0x180013197  call    cs:__imp_DuplicateTokenEx
0x18001319d  test    eax, eax
0x18001319f  jz      short loc_180013165
0x1800131a1  mov     rdx, [rbp+190h+SidToCheck]; SidToCheck
0x1800131a5  lea     r8, [rbp+190h+IsMember]; IsMember
0x1800131a9  mov     rcx, [rbp+190h+phNewToken]; TokenHandle
0x1800131ad  call    cs:__imp_CheckTokenMembership
0x1800131b3  xor     ecx, ecx
0x1800131b5  test    eax, eax
0x1800131b7  jz      short loc_180013165
0x1800131b9  cmp     [rbp+190h+IsMember], ecx
0x1800131bc  jz      short loc_18001316D
0x1800131be  mov     ecx, [r13+0]
0x1800131c2  lea     r8, [rsp+290h+var_228]
0x1800131c7  mov     [rsp+290h+nSubAuthority3], r14d
0x1800131cc  xor     r9d, r9d
0x1800131cf  xor     edx, edx
0x1800131d1  mov     qword ptr [rsp+290h+nSubAuthority2], r14
0x1800131d6  call    GetUserInformation
0x1800131db  mov     ebx, eax
0x1800131dd  test    eax, eax
0x1800131df  jnz     loc_180013294
0x1800131e5  mov     dword ptr [rsp+290h+uBytes+4], r14d
0x1800131ea  mov     r13d, r14d
0x1800131ed  cmp     r13d, [rbp+190h+arg_20]
0x1800131f4  jnb     short loc_18001324D
0x1800131f6  mov     eax, r13d
0x1800131f9  xor     ecx, ecx
0x1800131fb  lea     r14, [rax+rax*2]
0x1800131ff  mov     rax, [rbp+190h+var_1A8]
0x180013203  add     r14, r14
0x180013206  cmp     [rax+r14*8+1Ch], ecx
0x18001320b  jnz     short loc_18001323A
0x18001320d  cmp     dword ptr [rax+r14*8+4], 3
0x180013213  jnz     short loc_18001323A
0x180013215  cmp     [rbp+190h+arg_30], ecx
0x18001321b  jz      short loc_180013227
0x18001321d  mov     rcx, [rsp+290h+var_228]
0x180013222  mov     rdx, [rcx]
0x180013225  jmp     short loc_18001322B
0x180013227  mov     rdx, [rbp+190h+SidToCheck]; pSid2
0x18001322b  mov     rcx, [rax+r14*8+28h]; pSid1
0x180013230  call    cs:__imp_EqualSid
0x180013236  test    eax, eax
0x180013238  jnz     short loc_18001323F
0x18001323a  inc     r13d
0x18001323d  jmp     short loc_1800131ED
0x18001323f  mov     rax, [rbp+190h+var_1A8]
0x180013243  mov     ecx, [rax+r14*8]
0x180013247  mov     dword ptr [rsp+290h+uBytes+4], ecx
0x18001324b  jmp     short loc_18001324F
0x18001324d  mov     ecx, esi
0x18001324f  mov     eax, ecx
0x180013251  and     eax, 120116h
0x180013256  mov     dword ptr [rbp+190h+pIdentifierAuthority.Value], eax
0x180013259  jnz     short loc_180013263
0x18001325b  test    ecx, 120089h
0x180013261  jz      short loc_180013294
0x180013263  mov     rdx, [rbp+190h+var_1A0]
0x180013267  lea     rax, [rbp+190h+pBytesReturned]
0x18001326b  lea     r9, [rbp+190h+ppBuffer]; ppBuffer
0x18001326f  mov     qword ptr [rsp+290h+nSubAuthority2], rax; pBytesReturned
0x180013274  mov     r8d, 5; WTSInfoClass
0x18001327a  xor     ecx, ecx; hServer
0x18001327c  mov     edx, [rdx]; SessionId
0x18001327e  call    cs:__imp_WTSQuerySessionInformationW
0x180013284  test    eax, eax
0x180013286  jnz     loc_180013382
0x18001328c  call    cs:__imp_GetLastError
0x180013292  mov     ebx, eax
0x180013294  mov     r13, [rsp+290h+var_230]
0x180013299  mov     r14, [rsp+290h+var_228]
0x18001329e  mov     rcx, [rbp+190h+SidToCheck]; pSid
0x1800132a2  test    rcx, rcx
0x1800132a5  jz      short loc_1800132AD
0x1800132a7  call    cs:__imp_FreeSid
0x1800132ad  mov     rcx, [rbp+190h+hMem]; hMem
0x1800132b1  test    rcx, rcx
0x1800132b4  jz      short loc_1800132BC
0x1800132b6  call    cs:__imp_LocalFree
0x1800132bc  test    rdi, rdi
0x1800132bf  jz      short loc_1800132CA
0x1800132c1  mov     rcx, rdi; hMem
0x1800132c4  call    cs:__imp_LocalFree
0x1800132ca  mov     rcx, [rbp+190h+var_1C8]; hMem
0x1800132ce  test    rcx, rcx
0x1800132d1  jz      short loc_1800132D9
0x1800132d3  call    cs:__imp_LocalFree
0x1800132d9  test    rsi, rsi
0x1800132dc  jz      short loc_1800132E7
0x1800132de  mov     rcx, rsi; hMem
0x1800132e1  call    cs:__imp_LocalFree
0x1800132e7  test    r13, r13
0x1800132ea  jz      short loc_1800132F5
0x1800132ec  mov     rcx, r13; hMem
0x1800132ef  call    cs:__imp_LocalFree
0x1800132f5  test    r15, r15
0x1800132f8  jz      short loc_180013303
0x1800132fa  mov     rcx, r15; hMem
0x1800132fd  call    cs:__imp_LocalFree
0x180013303  test    r12, r12
0x180013306  jz      short loc_180013311
0x180013308  mov     rcx, r12; hMem
0x18001330b  call    cs:__imp_LocalFree
0x180013311  mov     rcx, [rbp+190h+ppBuffer]; pMemory
0x180013315  test    rcx, rcx
0x180013318  jz      short loc_180013320
0x18001331a  call    cs:__imp_WTSFreeMemory
0x180013320  test    r14, r14
0x180013323  jz      short loc_18001332E
0x180013325  mov     rcx, r14; hMem
0x180013328  call    cs:__imp_LocalFree
0x18001332e  mov     rcx, [rbp+190h+phToken]; hObject
0x180013332  lea     rax, [rcx-1]
0x180013336  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001333a  ja      short loc_180013342
0x18001333c  call    cs:__imp_CloseHandle
0x180013342  mov     rcx, [rbp+190h+phNewToken]; hObject
0x180013346  lea     rax, [rcx-1]
0x18001334a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001334e  ja      short loc_180013356
0x180013350  call    cs:__imp_CloseHandle
0x180013356  mov     eax, ebx
0x180013358  mov     rcx, [rbp+190h+var_40]
0x18001335f  xor     rcx, rsp; StackCookie
0x180013362  call    __security_check_cookie
0x180013367  mov     rbx, [rsp+290h+arg_0]
0x18001336f  add     rsp, 260h
0x180013376  pop     r15
0x180013378  pop     r14
0x18001337a  pop     r13
0x18001337c  pop     r12
0x18001337e  pop     rdi
0x18001337f  pop     rsi
0x180013380  pop     rbp
0x180013381  retn
0x180013382  mov     r13, [rbp+190h+DeviceInfoData]
0x180013386  lea     rax, [rsp+290h+uBytes]
0x18001338b  mov     r14, [rbp+190h+DeviceInfoSet]
0x18001338f  lea     r8, DEVPKEY_Device_HardwareIds; PropertyKey
0x180013396  mov     qword ptr [rsp+290h+nSubAuthority3], rax; __int64
0x18001339b  mov     r9d, 2012h
0x1800133a1  lea     rax, [rbp+190h+hMem]
0x1800133a5  mov     rdx, r13; DeviceInfoData
0x1800133a8  mov     rcx, r14; DeviceInfoSet
0x1800133ab  mov     qword ptr [rsp+290h+nSubAuthority2], rax; __int64
0x1800133b0  call    GetDeviceProperty
0x1800133b5  test    eax, eax
0x1800133b7  jz      short loc_1800133C4
0x1800133b9  cmp     eax, 490h
0x1800133be  jnz     loc_180013292
0x1800133c4  lea     rax, [rbp+190h+var_1E4]
0x1800133c8  mov     r9d, 12h
0x1800133ce  mov     qword ptr [rsp+290h+nSubAuthority3], rax; __int64
0x1800133d3  lea     r8, DEVPKEY_Device_InstanceId; PropertyKey
0x1800133da  lea     rax, [rsp+290h+var_218]
0x1800133df  mov     rdx, r13; DeviceInfoData
0x1800133e2  mov     rcx, r14; DeviceInfoSet
0x1800133e5  mov     qword ptr [rsp+290h+nSubAuthority2], rax; __int64
0x1800133ea  call    GetDeviceProperty
0x1800133ef  test    eax, eax
0x1800133f1  jz      short loc_180013404
0x1800133f3  cmp     eax, 490h
0x1800133f8  jz      short loc_180013404
0x1800133fa  mov     rdi, [rsp+290h+var_218]
0x1800133ff  jmp     loc_180013292
0x180013404  lea     rax, [rbp+190h+var_20C]
0x180013408  mov     r9d, 0Dh
0x18001340e  mov     qword ptr [rsp+290h+nSubAuthority3], rax; __int64
0x180013413  lea     r8, DEVPKEY_Device_BusTypeGuid; PropertyKey
0x18001341a  lea     rax, [rbp+190h+var_1C8]
0x18001341e  mov     rdx, r13; DeviceInfoData
0x180013421  mov     rcx, r14; DeviceInfoSet
0x180013424  mov     qword ptr [rsp+290h+nSubAuthority2], rax; __int64
0x180013429  call    GetDeviceProperty
0x18001342e  test    eax, eax
0x180013430  jz      short loc_180013439
0x180013432  cmp     eax, 490h
0x180013437  jnz     short loc_1800133FA
0x180013439  lea     rax, [rbp+190h+var_1E4+4]
0x18001343d  mov     r9d, 12h
0x180013443  mov     qword ptr [rsp+290h+nSubAuthority3], rax; __int64
0x180013448  lea     r8, DEVPKEY_Device_Class; PropertyKey
0x18001344f  lea     rax, [rbp+190h+var_200]
0x180013453  mov     rdx, r13; DeviceInfoData
0x180013456  mov     rcx, r14; DeviceInfoSet
0x180013459  mov     qword ptr [rsp+290h+nSubAuthority2], rax; __int64
0x18001345e  call    GetDeviceProperty
0x180013463  mov     esi, 490h
0x180013468  test    eax, eax
0x18001346a  jz      short loc_18001347E
0x18001346c  cmp     eax, esi
0x18001346e  jz      short loc_18001347E
0x180013470  mov     rdi, [rsp+290h+var_218]
0x180013475  mov     rsi, [rbp+190h+var_200]
0x180013479  jmp     loc_180013292
0x18001347e  lea     rax, [rbp+190h+var_20C+4]
0x180013482  mov     r9d, 0Dh
0x180013488  mov     qword ptr [rsp+290h+nSubAuthority3], rax; __int64
0x18001348d  lea     r8, DEVPKEY_Device_ClassGuid; PropertyKey
0x180013494  lea     rax, [rsp+290h+var_230]
0x180013499  mov     rdx, r13; DeviceInfoData
0x18001349c  mov     rcx, r14; DeviceInfoSet
0x18001349f  mov     qword ptr [rsp+290h+nSubAuthority2], rax; __int64
0x1800134a4  call    GetDeviceProperty
0x1800134a9  test    eax, eax
  ... truncated ...
```

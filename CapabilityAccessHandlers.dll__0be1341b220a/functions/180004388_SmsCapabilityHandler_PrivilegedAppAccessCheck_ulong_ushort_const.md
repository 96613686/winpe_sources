# SmsCapabilityHandler::PrivilegedAppAccessCheck(ulong,ushort const *)

- ea: `0x180004388`
- end: `0x180004762`
- name: `?PrivilegedAppAccessCheck@SmsCapabilityHandler@@AEAAJKPEBG@Z`
- size: `986`
- prototype: `__int64 __fastcall(SmsCapabilityHandler *this, DWORD, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004330`

## callees

- `0x180004388`
- `0x180004c70`
- `0x1800090d4`
- `0x1800090f4`
- `0x18000b370`
- `0x1800102b8`
- `0x180011b84`
- `0x18001227c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004620`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004620`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800044be`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800044be`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800045a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800045a0`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000444c`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800044f8`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180004670`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800046ab`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180004733`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000444c`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800044f8`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180004670`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800046ab`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180004733`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180004418`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000454e`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180004418`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000454e`

## pseudocode

```c
__int64 __fastcall SmsCapabilityHandler::PrivilegedAppAccessCheck(
        SmsCapabilityHandler *this,
        DWORD a2,
        const unsigned __int16 *a3)
{
  int ObjectProperties; // eax
  HRESULT LastError; // ebx
  __int64 v7; // rax
  __int64 v8; // rdx
  const WCHAR *v9; // rdi
  char *v10; // rbx
  const char *v11; // r9
  unsigned __int16 **v12; // r8
  int PackageFamilyNameFromProcess; // eax
  __int64 v14; // rax
  DEVPROPKEY *bIgnoreCase; // [rsp+20h] [rbp-79h]
  unsigned int v16; // [rsp+40h] [rbp-59h] BYREF
  __int64 v17; // [rsp+48h] [rbp-51h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-49h] BYREF
  LPCWCH lpString2; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v20[3]; // [rsp+60h] [rbp-39h] BYREF
  char v21; // [rsp+78h] [rbp-21h]
  IID rclsid; // [rsp+80h] [rbp-19h] BYREF
  DEVPROPKEY v23; // [rsp+90h] [rbp-9h] BYREF
  int v24; // [rsp+A4h] [rbp+Bh]
  __int64 v25; // [rsp+A8h] [rbp+Fh]
  DEVPROPKEY v26; // [rsp+B0h] [rbp+17h] BYREF
  int v27; // [rsp+C4h] [rbp+2Bh]
  __int64 v28; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v16 = 0;
  v17 = 0;
  v20[1] = &v16;
  v20[2] = &v17;
  v21 = 1;
  v23 = DEVPKEY_Device_ContainerId;
  v24 = 0;
  v25 = 0;
  bIgnoreCase = &v23;
  ObjectProperties = DevGetObjectProperties(1, a3, 0);
  LastError = ObjectProperties;
  if ( ObjectProperties < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sms\\smscapabilityhandler.cpp",
      (const char *)(unsigned int)ObjectProperties,
      (int)&v23);
LABEL_3:
    if ( v16 )
    {
      if ( v17 )
        DevFreeObjectProperties(v16, v17);
    }
    return (unsigned int)LastError;
  }
  if ( v16 != 1 || *(_DWORD *)(v17 + 16) != 2 )
    goto LABEL_42;
  v7 = *(_QWORD *)v17 - *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1;
  if ( *(_QWORD *)v17 == *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1 )
    v7 = *(_QWORD *)(v17 + 8) - *(_QWORD *)DEVPKEY_Device_ContainerId.fmtid.Data4;
  if ( v7 || *(_DWORD *)(v17 + 32) != 13 )
  {
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sms\\smscapabilityhandler.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v23);
LABEL_43:
    if ( v16 && v17 )
      DevFreeObjectProperties(v16, v17);
    return 2147549183LL;
  }
  rclsid = *(IID *)*(_QWORD *)(v17 + 40);
  lpsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  LastError = StringFromCLSID(&rclsid, &lpsz);
  if ( LastError < 0 )
  {
    v8 = 70;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sms\\smscapabilityhandler.cpp",
      (const char *)(unsigned int)LastError,
      (int)bIgnoreCase);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    goto LABEL_3;
  }
  DevFreeObjectProperties(v16, v17);
  v16 = 0;
  v17 = 0;
  v26 = DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames;
  v27 = 0;
  v28 = 0;
  bIgnoreCase = &v26;
  LastError = DevGetObjectProperties(2, lpsz, 0);
  if ( LastError < 0 )
  {
    v8 = 85;
    goto LABEL_15;
  }
  if ( v16 != 1 || *(_DWORD *)(v17 + 32) != 8210 || !*(_DWORD *)(v17 + 36) || (v9 = *(const WCHAR **)(v17 + 40)) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sms\\smscapabilityhandler.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v26);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    goto LABEL_43;
  }
  v10 = (char *)OpenProcess(0x1000u, 0, a2);
  v20[0] = v10;
  if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x64,
                  (unsigned int)"onecore\\base\\devices\\cam\\handler\\sms\\smscapabilityhandler.cpp",
                  v11);
    goto LABEL_40;
  }
  lpString2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpString2,
    0);
  PackageFamilyNameFromProcess = CallerIdentity::GetPackageFamilyNameFromProcess(v10, &lpString2, v12);
  LastError = PackageFamilyNameFromProcess;
  if ( PackageFamilyNameFromProcess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sms\\smscapabilityhandler.cpp",
      (const char *)(unsigned int)PackageFamilyNameFromProcess,
      (int)&v26);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
LABEL_40:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
    goto LABEL_16;
  }
  while ( *v9 )
  {
    if ( CompareStringOrdinal(v9, -1, lpString2, -1, 1) == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      if ( v16 && v17 )
        DevFreeObjectProperties(v16, v17);
      return 0;
    }
    v14 = -1;
    do
      ++v14;
    while ( v9[v14] );
    v9 += v14 + 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
  if ( v16 && v17 )
    DevFreeObjectProperties(v16, v17);
  return 2147942405LL;
}

```

## disassembly

```asm
0x180004388  mov     [rsp-8+arg_0], rbx
0x18000438d  mov     [rsp-8+arg_18], rsi
0x180004392  push    rbp
0x180004393  push    rdi
0x180004394  push    r14
0x180004396  lea     rbp, [rsp-47h]
0x18000439b  sub     rsp, 0E0h
0x1800043a2  mov     rax, cs:__security_cookie
0x1800043a9  xor     rax, rsp
0x1800043ac  mov     [rbp+57h+var_20], rax
0x1800043b0  mov     r10, r8
0x1800043b3  mov     esi, edx
0x1800043b5  xor     r14d, r14d
0x1800043b8  mov     [rbp+57h+var_B0], r14d
0x1800043bc  mov     [rbp+57h+var_A8], r14
0x1800043c0  lea     rax, [rbp+57h+var_B0]
0x1800043c4  mov     [rbp+57h+var_88], rax
0x1800043c8  lea     rax, [rbp+57h+var_A8]
0x1800043cc  mov     [rbp+57h+var_80], rax
0x1800043d0  mov     [rbp+57h+var_78], 1
0x1800043d4  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x1800043db  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800043df  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x1800043e5  mov     [rbp+57h+var_50], eax
0x1800043e8  mov     [rbp+57h+var_4C], r14d
0x1800043ec  mov     [rbp+57h+var_48], r14
0x1800043f0  lea     rax, [rbp+57h+var_A8]
0x1800043f4  mov     [rsp+0F0h+var_C0], rax
0x1800043f9  lea     rax, [rbp+57h+var_B0]
0x1800043fd  mov     [rsp+0F0h+var_C8], rax
0x180004402  lea     rax, [rbp+57h+var_60]
0x180004406  mov     qword ptr [rsp+0F0h+bIgnoreCase], rax; int
0x18000440b  lea     r9d, [r14+1]
0x18000440f  xor     r8d, r8d
0x180004412  mov     rdx, r10
0x180004415  mov     ecx, r9d
0x180004418  call    cs:__imp_DevGetObjectProperties
0x18000441e  mov     ebx, eax
0x180004420  test    eax, eax
0x180004422  jns     short loc_180004459
0x180004424  mov     rcx, [rbp+5Fh]; this
0x180004428  mov     r9d, eax; char *
0x18000442b  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\handler\\s"...
0x180004432  lea     edx, [r14+3Dh]; void *
0x180004436  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000443b  nop
0x18000443c  mov     ecx, [rbp+57h+var_B0]
0x18000443f  test    ecx, ecx
0x180004441  jz      short loc_180004452
0x180004443  mov     rdx, [rbp+57h+var_A8]
0x180004447  test    rdx, rdx
0x18000444a  jz      short loc_180004452
0x18000444c  call    cs:__imp_DevFreeObjectProperties
0x180004452  mov     eax, ebx
0x180004454  jmp     loc_18000473E
0x180004459  cmp     [rbp+57h+var_B0], 1
0x18000445d  jnz     loc_180004707
0x180004463  mov     rcx, [rbp+57h+var_A8]
0x180004467  cmp     dword ptr [rcx+10h], 2
0x18000446b  jnz     loc_180004707
0x180004471  mov     rax, [rcx]
0x180004474  sub     rax, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18000447b  jnz     short loc_180004488
0x18000447d  mov     rax, [rcx+8]
0x180004481  sub     rax, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data4
0x180004488  test    rax, rax
0x18000448b  jnz     loc_180004707
0x180004491  cmp     dword ptr [rcx+20h], 0Dh
0x180004495  jnz     loc_180004707
0x18000449b  mov     rax, [rcx+28h]
0x18000449f  movups  xmm0, xmmword ptr [rax]
0x1800044a2  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x1800044a7  mov     [rbp+57h+lpsz], r14
0x1800044ab  xor     edx, edx
0x1800044ad  lea     rcx, [rbp+57h+lpsz]
0x1800044b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800044b6  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800044ba  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1800044be  call    cs:__imp_StringFromCLSID
0x1800044c4  mov     ebx, eax
0x1800044c6  test    eax, eax
0x1800044c8  jns     short loc_1800044F1
0x1800044ca  mov     edx, 46h ; 'F'; void *
0x1800044cf  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\handler\\s"...
0x1800044d6  mov     r9d, ebx; char *
0x1800044d9  mov     rcx, [rbp+5Fh]; this
0x1800044dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800044e2  nop
0x1800044e3  lea     rcx, [rbp+57h+lpsz]
0x1800044e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800044ec  jmp     loc_18000443C
0x1800044f1  mov     rdx, [rbp+57h+var_A8]
0x1800044f5  mov     ecx, [rbp+57h+var_B0]
0x1800044f8  call    cs:__imp_DevFreeObjectProperties
0x1800044fe  mov     [rbp+57h+var_B0], r14d
0x180004502  mov     [rbp+57h+var_A8], r14
0x180004506  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.fmtid.Data1
0x18000450d  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180004511  mov     eax, cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.pid
0x180004517  mov     [rbp+57h+var_30], eax
0x18000451a  mov     [rbp+57h+var_2C], r14d
0x18000451e  mov     [rbp+57h+var_28], r14
0x180004522  lea     rax, [rbp+57h+var_A8]
0x180004526  mov     [rsp+0F0h+var_C0], rax
0x18000452b  lea     rax, [rbp+57h+var_B0]
0x18000452f  mov     [rsp+0F0h+var_C8], rax
0x180004534  lea     rax, [rbp+57h+var_40]
0x180004538  mov     qword ptr [rsp+0F0h+bIgnoreCase], rax; int
0x18000453d  mov     r9d, 1
0x180004543  xor     r8d, r8d
0x180004546  mov     rdx, [rbp+57h+lpsz]
0x18000454a  lea     ecx, [r9+1]
0x18000454e  call    cs:__imp_DevGetObjectProperties
0x180004554  mov     ebx, eax
0x180004556  test    eax, eax
0x180004558  jns     short loc_180004564
0x18000455a  mov     edx, 55h ; 'U'
0x18000455f  jmp     loc_1800044CF
0x180004564  cmp     [rbp+57h+var_B0], 1
0x180004568  jnz     loc_1800046E0
0x18000456e  mov     rdi, [rbp+57h+var_A8]
0x180004572  cmp     dword ptr [rdi+20h], 2012h
0x180004579  jnz     loc_1800046E0
0x18000457f  cmp     [rdi+24h], r14d
0x180004583  jz      loc_1800046E0
0x180004589  mov     rdi, [rdi+28h]
0x18000458d  test    rdi, rdi
0x180004590  jz      loc_1800046E0
0x180004596  mov     r8d, esi; dwProcessId
0x180004599  xor     edx, edx; bInheritHandle
0x18000459b  mov     ecx, 1000h; dwDesiredAccess
0x1800045a0  call    cs:__imp_OpenProcess
0x1800045a6  mov     rbx, rax
0x1800045a9  mov     [rbp+57h+var_90], rax
0x1800045ad  dec     rax
0x1800045b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800045b4  ja      loc_1800046BB
0x1800045ba  mov     [rbp+57h+lpString2], r14
0x1800045be  xor     edx, edx
0x1800045c0  lea     rcx, [rbp+57h+lpString2]
0x1800045c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800045c9  lea     rdx, [rbp+57h+lpString2]; void *
0x1800045cd  mov     rcx, rbx; hProcess
0x1800045d0  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x1800045d5  mov     ebx, eax
0x1800045d7  test    eax, eax
0x1800045d9  jns     short loc_180004602
0x1800045db  mov     rcx, [rbp+5Fh]; this
0x1800045df  mov     r9d, eax; char *
0x1800045e2  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\handler\\s"...
0x1800045e9  mov     edx, 66h ; 'f'; void *
0x1800045ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045f3  nop
0x1800045f4  lea     rcx, [rbp+57h+lpString2]
0x1800045f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800045fd  jmp     loc_1800046D2
0x180004602  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004606  cmp     [rdi], r14w
0x18000460a  jz      short loc_18000467D
0x18000460c  mov     [rsp+0F0h+bIgnoreCase], 1; bIgnoreCase
0x180004614  mov     r9d, ebx; cchCount2
0x180004617  mov     r8, [rbp+57h+lpString2]; lpString2
0x18000461b  mov     edx, ebx; cchCount1
0x18000461d  mov     rcx, rdi; lpString1
0x180004620  call    cs:__imp_CompareStringOrdinal
0x180004626  cmp     eax, 2
0x180004629  jz      short loc_180004642
0x18000462b  mov     rax, rbx
0x18000462e  inc     rax
0x180004631  cmp     [rdi+rax*2], r14w
0x180004636  jnz     short loc_18000462E
0x180004638  lea     rdi, [rdi+rax*2]
0x18000463c  add     rdi, 2
0x180004640  jmp     short loc_180004606
0x180004642  lea     rcx, [rbp+57h+lpString2]
0x180004646  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000464b  nop
0x18000464c  lea     rcx, [rbp+57h+var_90]
0x180004650  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180004655  nop
0x180004656  lea     rcx, [rbp+57h+lpsz]
0x18000465a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000465f  nop
0x180004660  mov     ecx, [rbp+57h+var_B0]
0x180004663  test    ecx, ecx
0x180004665  jz      short loc_180004676
0x180004667  mov     rdx, [rbp+57h+var_A8]
0x18000466b  test    rdx, rdx
0x18000466e  jz      short loc_180004676
0x180004670  call    cs:__imp_DevFreeObjectProperties
0x180004676  xor     eax, eax
0x180004678  jmp     loc_18000473E
0x18000467d  lea     rcx, [rbp+57h+lpString2]
0x180004681  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004686  nop
0x180004687  lea     rcx, [rbp+57h+var_90]
0x18000468b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180004690  nop
0x180004691  lea     rcx, [rbp+57h+lpsz]
0x180004695  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000469a  nop
0x18000469b  mov     ecx, [rbp+57h+var_B0]
0x18000469e  test    ecx, ecx
0x1800046a0  jz      short loc_1800046B1
0x1800046a2  mov     rdx, [rbp+57h+var_A8]
0x1800046a6  test    rdx, rdx
0x1800046a9  jz      short loc_1800046B1
0x1800046ab  call    cs:__imp_DevFreeObjectProperties
0x1800046b1  mov     eax, 80070005h
0x1800046b6  jmp     loc_18000473E
0x1800046bb  mov     rcx, [rbp+5Fh]; this
0x1800046bf  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\handler\\s"...
0x1800046c6  mov     edx, 64h ; 'd'; void *
0x1800046cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800046d0  mov     ebx, eax
0x1800046d2  lea     rcx, [rbp+57h+var_90]
0x1800046d6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800046db  jmp     loc_1800044E3
0x1800046e0  mov     rcx, [rbp+5Fh]; this
0x1800046e4  mov     r9d, 8000FFFFh; char *
0x1800046ea  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\handler\\s"...
0x1800046f1  mov     edx, 5Ch ; '\'; void *
0x1800046f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046fb  nop
0x1800046fc  lea     rcx, [rbp+57h+lpsz]
0x180004700  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004705  jmp     short loc_180004723
0x180004707  mov     rcx, [rbp+5Fh]; this
0x18000470b  mov     r9d, 8000FFFFh; char *
0x180004711  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\handler\\s"...
0x180004718  mov     edx, 42h ; 'B'; void *
0x18000471d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004722  nop
0x180004723  mov     ecx, [rbp+57h+var_B0]
0x180004726  test    ecx, ecx
0x180004728  jz      short loc_180004739
0x18000472a  mov     rdx, [rbp+57h+var_A8]
0x18000472e  test    rdx, rdx
0x180004731  jz      short loc_180004739
0x180004733  call    cs:__imp_DevFreeObjectProperties
0x180004739  mov     eax, 8000FFFFh
0x18000473e  mov     rcx, [rbp+57h+var_20]
0x180004742  xor     rcx, rsp; StackCookie
0x180004745  call    __security_check_cookie
0x18000474a  lea     r11, [rsp+0F0h+var_10]
0x180004752  mov     rbx, [r11+20h]
0x180004756  mov     rsi, [r11+38h]
0x18000475a  mov     rsp, r11
0x18000475d  pop     r14
0x18000475f  pop     rdi
0x180004760  pop     rbp
0x180004761  retn
```

# StoreFrontHelper::ResumeApp(ushort const *,ushort const *)

- ea: `0x18034b160`
- end: `0x18034b3c9`
- name: `?ResumeApp@StoreFrontHelper@@AEAAJPEBG0@Z`
- size: `617`
- prototype: `int(StoreFrontHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18011a4a0`

## callees

- `0x180009dfc`
- `0x1800378dc`
- `0x1800529c8`
- `0x18034b160`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034b398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034b398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18034b2be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18034b2be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18034b1a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18034b347`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18034b1a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18034b347`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18034b268`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18034b268`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18034b3a8`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18034b3a8`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18034b2a6`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18034b2e5`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18034b2a6`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18034b2e5`

## pseudocode

```c
__int64 __fastcall StoreFrontHelper::ResumeApp(
        StoreFrontHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  LONG v9; // eax
  bool v10; // sf
  BYTE *v11; // rax
  BYTE *v12; // rdi
  LONG PackageApplicationIds; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  int v15; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v16; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v17; // [rsp+40h] [rbp-10h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  StoreFrontHelper *count; // [rsp+70h] [rbp+20h] BYREF
  const unsigned __int16 *bufferLength; // [rsp+80h] [rbp+30h] BYREF
  int v22; // [rsp+88h] [rbp+38h] BYREF

  bufferLength = a3;
  count = this;
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  v4 = CoCreateInstance(&CLSID_PackageDebugSettings, 0, 1u, &GUID_f27c3930_8029_4ad1_94e3_3dba417810c1, &v16);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v22 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, int *))(*(_QWORD *)v16 + 120LL))(v16, a2, &v22);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 196;
      goto LABEL_5;
    }
    if ( v22 )
    {
      if ( v22 == 2 || v22 == 3 )
      {
        StoreFrontHelperTelemetry::TraceLoggingInfo("ResumeApp - resuming %ws", a2);
        v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v16 + 48LL))(v16, a2);
        v5 = v4;
        if ( v4 < 0 )
        {
          v6 = 203;
          goto LABEL_5;
        }
LABEL_11:
        v5 = 0;
        goto LABEL_12;
      }
      if ( v22 != 4 )
        goto LABEL_11;
    }
    packageInfoReference = 0;
    v9 = OpenPackageInfoByFullName(a2, 0, &packageInfoReference);
    v10 = v9 < 0;
    if ( v9 > 0 )
      v10 = 1;
    if ( !v10 )
    {
      LODWORD(bufferLength) = 0;
      LODWORD(count) = 0;
      v5 = -2147418113;
      if ( GetPackageApplicationIds(packageInfoReference, (UINT32 *)&bufferLength, 0, (UINT32 *)&count) == 122 )
      {
        v11 = (BYTE *)CoTaskMemAlloc((unsigned int)bufferLength);
        v12 = v11;
        if ( v11 )
        {
          PackageApplicationIds = GetPackageApplicationIds(
                                    packageInfoReference,
                                    (UINT32 *)&bufferLength,
                                    v11,
                                    (UINT32 *)&count);
          v5 = PackageApplicationIds;
          if ( PackageApplicationIds > 0 )
            v5 = (unsigned __int16)PackageApplicationIds | 0x80070000;
          if ( v5 >= 0 && (_DWORD)count )
          {
            v15 = 0;
            v17 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
            v5 = CoCreateInstance(
                   &CLSID_ApplicationActivationManager,
                   0,
                   1u,
                   &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
                   &v17);
            if ( v5 >= 0 )
            {
              StoreFrontHelperTelemetry::TraceLoggingInfo("ResumeApp - launching %ws", *(_QWORD *)v12);
              ppv = (LPVOID *)&v15;
              v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(
                     v17,
                     *(_QWORD *)v12,
                     0,
                     0);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          }
          CoTaskMemFree(v12);
        }
      }
      ClosePackageInfo(packageInfoReference);
      if ( v5 < 0 )
      {
        v7 = (unsigned int)v5;
        v6 = 238;
        goto LABEL_6;
      }
    }
    goto LABEL_11;
  }
  v6 = 193;
LABEL_5:
  v7 = (unsigned int)v4;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
    (const char *)v7,
    (int)ppv);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18034b160  mov     [rsp-18h+bufferLength], r8
0x18034b165  mov     [rsp-18h+count], rcx
0x18034b16a  push    rbp
0x18034b16b  push    rbx
0x18034b16c  push    rdi
0x18034b16d  mov     rbp, rsp
0x18034b170  sub     rsp, 50h
0x18034b174  lea     rcx, [rbp+var_18]
0x18034b178  mov     [rbp+var_18], 0
0x18034b180  mov     rdi, rdx
0x18034b183  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034b188  xor     edx, edx; pUnkOuter
0x18034b18a  lea     rax, [rbp+var_18]
0x18034b18e  lea     r9, _GUID_f27c3930_8029_4ad1_94e3_3dba417810c1; riid
0x18034b195  mov     [rsp+50h+ppv], rax; int
0x18034b19a  lea     rcx, CLSID_PackageDebugSettings; rclsid
0x18034b1a1  lea     r8d, [rdx+1]; dwClsContext
0x18034b1a5  call    cs:__imp_CoCreateInstance
0x18034b1ac  nop     dword ptr [rax+rax+00h]
0x18034b1b1  mov     ebx, eax
0x18034b1b3  test    eax, eax
0x18034b1b5  jns     short loc_18034B1BE
0x18034b1b7  mov     edx, 0C1h
0x18034b1bc  jmp     short loc_18034B1E7
0x18034b1be  mov     rcx, [rbp+var_18]
0x18034b1c2  lea     r8, [rbp+arg_18]
0x18034b1c6  mov     [rbp+arg_18], 0
0x18034b1cd  mov     rdx, rdi
0x18034b1d0  mov     rax, [rcx]
0x18034b1d3  mov     rax, [rax+78h]
0x18034b1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034b1dc  mov     ebx, eax
0x18034b1de  test    eax, eax
0x18034b1e0  jns     short loc_18034B1FC
0x18034b1e2  mov     edx, 0C4h; void *
0x18034b1e7  mov     r9d, eax; char *
0x18034b1ea  mov     rcx, [rbp+18h]; this
0x18034b1ee  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x18034b1f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034b1fa  jmp     short loc_18034B214
0x18034b1fc  mov     ecx, [rbp+arg_18]
0x18034b1ff  test    ecx, ecx
0x18034b201  jz      short loc_18034B257
0x18034b203  sub     ecx, 2
0x18034b206  jz      short loc_18034B228
0x18034b208  sub     ecx, 1
0x18034b20b  jz      short loc_18034B228
0x18034b20d  cmp     ecx, 1
0x18034b210  jz      short loc_18034B257
0x18034b212  xor     ebx, ebx
0x18034b214  lea     rcx, [rbp+var_18]
0x18034b218  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034b21d  mov     eax, ebx
0x18034b21f  add     rsp, 50h
0x18034b223  pop     rdi
0x18034b224  pop     rbx
0x18034b225  pop     rbp
0x18034b226  retn
0x18034b228  mov     rdx, rdi
0x18034b22b  lea     rcx, aResumeappResum; "ResumeApp - resuming %ws"
0x18034b232  call    ?TraceLoggingInfo@StoreFrontHelperTelemetry@@SAXPEBDZZ; StoreFrontHelperTelemetry::TraceLoggingInfo(char const *,...)
0x18034b237  mov     rcx, [rbp+var_18]
0x18034b23b  mov     rdx, rdi
0x18034b23e  mov     rax, [rcx]
0x18034b241  mov     rax, [rax+30h]
0x18034b245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034b24a  mov     ebx, eax
0x18034b24c  test    eax, eax
0x18034b24e  jns     short loc_18034B212
0x18034b250  mov     edx, 0CBh
0x18034b255  jmp     short loc_18034B1E7
0x18034b257  lea     r8, [rbp+packageInfoReference]; packageInfoReference
0x18034b25b  mov     [rbp+packageInfoReference], 0
0x18034b263  xor     edx, edx; reserved
0x18034b265  mov     rcx, rdi; packageFullName
0x18034b268  call    cs:__imp_OpenPackageInfoByFullName
0x18034b26f  nop     dword ptr [rax+rax+00h]
0x18034b274  test    eax, eax
0x18034b276  jle     short loc_18034B282
0x18034b278  movzx   eax, ax
0x18034b27b  or      eax, 80070000h
0x18034b280  test    eax, eax
0x18034b282  js      short loc_18034B212
0x18034b284  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18034b288  lea     r9, [rbp+count]; count
0x18034b28c  xor     r8d, r8d; buffer
0x18034b28f  mov     dword ptr [rbp+bufferLength], 0
0x18034b296  lea     rdx, [rbp+bufferLength]; bufferLength
0x18034b29a  mov     dword ptr [rbp+count], 0
0x18034b2a1  mov     ebx, 8000FFFFh
0x18034b2a6  call    cs:__imp_GetPackageApplicationIds
0x18034b2ad  nop     dword ptr [rax+rax+00h]
0x18034b2b2  cmp     eax, 7Ah ; 'z'
0x18034b2b5  jnz     loc_18034B3A4
0x18034b2bb  mov     ecx, dword ptr [rbp+bufferLength]; cb
0x18034b2be  call    cs:__imp_CoTaskMemAlloc
0x18034b2c5  nop     dword ptr [rax+rax+00h]
0x18034b2ca  mov     rdi, rax
0x18034b2cd  test    rax, rax
0x18034b2d0  jz      loc_18034B3A4
0x18034b2d6  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18034b2da  lea     r9, [rbp+count]; count
0x18034b2de  mov     r8, rax; buffer
0x18034b2e1  lea     rdx, [rbp+bufferLength]; bufferLength
0x18034b2e5  call    cs:__imp_GetPackageApplicationIds
0x18034b2ec  nop     dword ptr [rax+rax+00h]
0x18034b2f1  mov     ebx, eax
0x18034b2f3  test    eax, eax
0x18034b2f5  jle     short loc_18034B300
0x18034b2f7  movzx   ebx, ax
0x18034b2fa  or      ebx, 80070000h
0x18034b300  test    ebx, ebx
0x18034b302  js      loc_18034B395
0x18034b308  cmp     dword ptr [rbp+count], 0
0x18034b30c  jz      loc_18034B395
0x18034b312  lea     rcx, [rbp+var_10]
0x18034b316  mov     [rbp+var_20], 0
0x18034b31d  mov     [rbp+var_10], 0
0x18034b325  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034b32a  xor     edx, edx; pUnkOuter
0x18034b32c  lea     rax, [rbp+var_10]
0x18034b330  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x18034b337  mov     [rsp+50h+ppv], rax; ppv
0x18034b33c  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x18034b343  lea     r8d, [rdx+1]; dwClsContext
0x18034b347  call    cs:__imp_CoCreateInstance
0x18034b34e  nop     dword ptr [rax+rax+00h]
0x18034b353  mov     ebx, eax
0x18034b355  test    eax, eax
0x18034b357  js      short loc_18034B38C
0x18034b359  mov     rdx, [rdi]
0x18034b35c  lea     rcx, aResumeappLaunc; "ResumeApp - launching %ws"
0x18034b363  call    ?TraceLoggingInfo@StoreFrontHelperTelemetry@@SAXPEBDZZ; StoreFrontHelperTelemetry::TraceLoggingInfo(char const *,...)
0x18034b368  mov     rcx, [rbp+var_10]
0x18034b36c  lea     rdx, [rbp+var_20]
0x18034b370  mov     [rsp+50h+ppv], rdx
0x18034b375  xor     r9d, r9d
0x18034b378  mov     rdx, [rdi]
0x18034b37b  xor     r8d, r8d
0x18034b37e  mov     rax, [rcx]
0x18034b381  mov     rax, [rax+18h]
0x18034b385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034b38a  mov     ebx, eax
0x18034b38c  lea     rcx, [rbp+var_10]
0x18034b390  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034b395  mov     rcx, rdi; pv
0x18034b398  call    cs:__imp_CoTaskMemFree
0x18034b39f  nop     dword ptr [rax+rax+00h]
0x18034b3a4  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18034b3a8  call    cs:__imp_ClosePackageInfo
0x18034b3af  nop     dword ptr [rax+rax+00h]
0x18034b3b4  test    ebx, ebx
0x18034b3b6  jns     loc_18034B212
0x18034b3bc  mov     r9d, ebx
0x18034b3bf  mov     edx, 0EEh
0x18034b3c4  jmp     loc_18034B1EA
```

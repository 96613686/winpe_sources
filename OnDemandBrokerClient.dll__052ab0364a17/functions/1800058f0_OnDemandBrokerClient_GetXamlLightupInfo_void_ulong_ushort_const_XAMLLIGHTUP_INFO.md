# OnDemandBrokerClient::GetXamlLightupInfo(void *,ulong,ushort const *,_XAMLLIGHTUP_INFO *)

- ea: `0x1800058f0`
- end: `0x180005b2a`
- name: `?GetXamlLightupInfo@OnDemandBrokerClient@@AEAAJPEAXKPEBGPEAU_XAMLLIGHTUP_INFO@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, void *, unsigned int, const unsigned __int16 *, wchar_t *Destination)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005b70`

## callees

- `0x18000506c`
- `0x1800050ac`
- `0x180005474`
- `0x1800058f0`
- `0x180006298`
- `0x180006546`
- `0x180006570`
- `0x180007010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180005aa2`
- `msvcrt!wcscpy_s` at `0x180005aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800059ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800059ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180005adb`
- `OLEAUT32!__imp_SysFreeString` at `0x180005adb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005ad0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005ad0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005a28`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005a28`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x180005a6e`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x180005a6e`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::GetXamlLightupInfo(
        OnDemandBrokerClient *this,
        void *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        wchar_t *Destination)
{
  struct _GUID v8; // xmm6
  int v9; // ebx
  __int64 v10; // r8
  signed int LastError; // eax
  LONG PackagesByPackageFamily; // eax
  OnDemandBrokerClient *v13; // rcx
  unsigned int v14; // r9d
  UINT32 count[2]; // [rsp+38h] [rbp-D0h] BYREF
  PCWSTR packageFamilyName; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  void (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  PWSTR packageFullNames[3]; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR buffer[128]; // [rsp+78h] [rbp-90h] BYREF

  ppv = 0;
  v19 = 0;
  v18 = 0;
  packageFamilyName = 0;
  packageFullNames[0] = 0;
  memset_0(buffer, 0, sizeof(buffer));
  count[1] = 128;
  count[0] = 1;
  v8 = *GetProductId((struct _GUID *)&packageFullNames[1], a4);
  v9 = CoCreateInstance(
         &GUID_b9e511fc_e364_497a_a121_b7b3612cedce,
         0,
         0x17u,
         &GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a,
         &ppv);
  if ( v9 >= 0 )
  {
    *(struct _GUID *)&packageFullNames[1] = v8;
    v9 = (*(__int64 (__fastcall **)(LPVOID, PWSTR *, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, &packageFullNames[1], &v19);
    if ( v9 >= 0 )
    {
      ATL::CComQIPtr<IPMApplicationInfo2,&__s_GUID const _GUID_2925390a_d947_4062_9dad_cf6f60e6a707>::operator=(
        &v18,
        v19,
        v10);
      if ( v18 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v18 + 24LL))(v18, &packageFamilyName);
        if ( v9 >= 0 )
        {
          if ( ImpersonateLoggedOnUser(a2) )
          {
            PackagesByPackageFamily = GetPackagesByPackageFamily(
                                        packageFamilyName,
                                        count,
                                        packageFullNames,
                                        &count[1],
                                        buffer);
            v9 = PackagesByPackageFamily;
            if ( PackagesByPackageFamily > 0 )
              v9 = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
            if ( v9 >= 0 )
            {
              if ( count[0] != 1 || wcscpy_s(Destination, 0x80u, packageFullNames[0]) )
              {
                v9 = -2147418113;
              }
              else
              {
                v9 = OnDemandBrokerClient::XamlLightupAgentEntryPointFromSessionType(v13, a3, Destination + 128, v14);
                if ( v9 >= 0 )
                  *(_OWORD *)(Destination + 388) = c_guidXamlLightupAgentEventDetailsClassId;
              }
            }
            RevertToSelf();
          }
          else
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
      else
      {
        v9 = -2147418113;
      }
    }
  }
  SysFreeString((BSTR)packageFamilyName);
  ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>(&v18);
  ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>((__int64 *)&v19);
  ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>((__int64 *)&ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800058f0  mov     rax, rsp
0x1800058f3  mov     [rax+8], rbx
0x1800058f7  mov     [rax+18h], rsi
0x1800058fb  push    rbp
0x1800058fc  push    rdi
0x1800058fd  push    r14
0x1800058ff  lea     rbp, [rax-0A8h]
0x180005906  sub     rsp, 190h
0x18000590d  movaps  xmmword ptr [rax-28h], xmm6
0x180005911  mov     rax, cs:__security_cookie
0x180005918  xor     rax, rsp
0x18000591b  mov     [rbp+0A0h+var_30], rax
0x18000591f  mov     rdi, [rbp+0A0h+Destination]
0x180005926  lea     rcx, [rsp+1A0h+buffer]; void *
0x18000592b  mov     r14d, r8d
0x18000592e  mov     [rsp+1A0h+var_150], 0
0x180005937  mov     rsi, rdx
0x18000593a  mov     [rsp+1A0h+var_158], 0
0x180005943  xor     edx, edx; Val
0x180005945  mov     [rsp+1A0h+var_160], 0
0x18000594e  mov     r8d, 100h; Size
0x180005954  mov     [rsp+1A0h+packageFamilyName], 0
0x18000595d  mov     rbx, r9
0x180005960  mov     qword ptr [rsp+1A0h+packageFullNames], 0
0x180005969  call    memset_0
0x18000596e  mov     rdx, rbx; unsigned __int16 *
0x180005971  mov     [rsp+1A0h+count+4], 80h
0x180005979  lea     rcx, [rsp+1A0h+packageFullNames+8]; retstr
0x18000597e  mov     [rsp+1A0h+count], 1
0x180005986  call    ?GetProductId@@YA?AU_GUID@@PEBG@Z; GetProductId(ushort const *)
0x18000598b  xor     edx, edx; pUnkOuter
0x18000598d  lea     r9, _GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a; riid
0x180005994  lea     rcx, _GUID_b9e511fc_e364_497a_a121_b7b3612cedce; rclsid
0x18000599b  movups  xmm6, xmmword ptr [rax]
0x18000599e  lea     rax, [rsp+1A0h+var_150]
0x1800059a3  lea     r8d, [rdx+17h]; dwClsContext
0x1800059a7  mov     [rsp+1A0h+ppv], rax; ppv
0x1800059ac  call    cs:__imp_CoCreateInstance
0x1800059b2  mov     ebx, eax
0x1800059b4  test    eax, eax
0x1800059b6  js      loc_180005AD6
0x1800059bc  mov     rcx, [rsp+1A0h+var_150]
0x1800059c1  lea     r8, [rsp+1A0h+var_158]
0x1800059c6  lea     rdx, [rsp+1A0h+packageFullNames+8]
0x1800059cb  movdqa  xmmword ptr [rsp+1A0h+packageFullNames+8], xmm6
0x1800059d1  mov     rax, [rcx]
0x1800059d4  mov     rax, [rax+48h]
0x1800059d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059dd  mov     ebx, eax
0x1800059df  test    eax, eax
0x1800059e1  js      loc_180005AD6
0x1800059e7  mov     rdx, [rsp+1A0h+var_158]
0x1800059ec  lea     rcx, [rsp+1A0h+var_160]
0x1800059f1  call    ??4?$CComQIPtr@UIPMApplicationInfo2@@$1?_GUID_2925390a_d947_4062_9dad_cf6f60e6a707@@3U__s_GUID@@B@ATL@@QEAAPEAUIPMApplicationInfo2@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPMApplicationInfo2,&__s_GUID const _GUID_2925390a_d947_4062_9dad_cf6f60e6a707>::operator=(IUnknown *)
0x1800059f6  mov     rcx, [rsp+1A0h+var_160]
0x1800059fb  test    rcx, rcx
0x1800059fe  jnz     short loc_180005A0A
0x180005a00  mov     ebx, 8000FFFFh
0x180005a05  jmp     loc_180005AD6
0x180005a0a  mov     rax, [rcx]
0x180005a0d  lea     rdx, [rsp+1A0h+packageFamilyName]
0x180005a12  mov     rax, [rax+18h]
0x180005a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1b  mov     ebx, eax
0x180005a1d  test    eax, eax
0x180005a1f  js      loc_180005AD6
0x180005a25  mov     rcx, rsi; hToken
0x180005a28  call    cs:__imp_ImpersonateLoggedOnUser
0x180005a2e  test    eax, eax
0x180005a30  jnz     short loc_180005A50
0x180005a32  call    cs:__imp_GetLastError
0x180005a38  mov     ebx, eax
0x180005a3a  test    eax, eax
0x180005a3c  jle     loc_180005AD6
0x180005a42  movzx   ebx, ax
0x180005a45  or      ebx, 80070000h
0x180005a4b  jmp     loc_180005AD6
0x180005a50  mov     rcx, [rsp+1A0h+packageFamilyName]; packageFamilyName
0x180005a55  lea     rax, [rsp+1A0h+buffer]
0x180005a5a  lea     r9, [rsp+1A0h+count+4]; bufferLength
0x180005a5f  mov     [rsp+1A0h+ppv], rax; buffer
0x180005a64  lea     r8, [rsp+1A0h+packageFullNames]; packageFullNames
0x180005a69  lea     rdx, [rsp+1A0h+count]; count
0x180005a6e  call    cs:__imp_GetPackagesByPackageFamily
0x180005a74  mov     ebx, eax
0x180005a76  test    eax, eax
0x180005a78  jle     short loc_180005A83
0x180005a7a  movzx   ebx, ax
0x180005a7d  or      ebx, 80070000h
0x180005a83  test    ebx, ebx
0x180005a85  js      short loc_180005AD0
0x180005a87  cmp     [rsp+1A0h+count], 1
0x180005a8c  jz      short loc_180005A95
0x180005a8e  mov     ebx, 8000FFFFh
0x180005a93  jmp     short loc_180005AD0
0x180005a95  mov     r8, qword ptr [rsp+1A0h+packageFullNames]; Source
0x180005a9a  mov     edx, 80h; SizeInWords
0x180005a9f  mov     rcx, rdi; Destination
0x180005aa2  call    cs:__imp_wcscpy_s
0x180005aa8  test    eax, eax
0x180005aaa  jnz     short loc_180005A8E
0x180005aac  lea     r8, [rdi+100h]; unsigned __int16 *
0x180005ab3  mov     edx, r14d; unsigned int
0x180005ab6  call    ?XamlLightupAgentEntryPointFromSessionType@OnDemandBrokerClient@@AEAAJKPEAGK@Z; OnDemandBrokerClient::XamlLightupAgentEntryPointFromSessionType(ulong,ushort *,ulong)
0x180005abb  mov     ebx, eax
0x180005abd  test    eax, eax
0x180005abf  js      short loc_180005AD0
0x180005ac1  movups  xmm0, cs:c_guidXamlLightupAgentEventDetailsClassId
0x180005ac8  movdqu  xmmword ptr [rdi+308h], xmm0
0x180005ad0  call    cs:__imp_RevertToSelf
0x180005ad6  mov     rcx, [rsp+1A0h+packageFamilyName]; bstrString
0x180005adb  call    cs:__imp_SysFreeString
0x180005ae1  lea     rcx, [rsp+1A0h+var_160]
0x180005ae6  call    ??1?$CComPtrBase@UIPMApplicationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>(void)
0x180005aeb  lea     rcx, [rsp+1A0h+var_158]
0x180005af0  call    ??1?$CComPtrBase@UIPMApplicationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>(void)
0x180005af5  lea     rcx, [rsp+1A0h+var_150]
0x180005afa  call    ??1?$CComPtrBase@UIPMApplicationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>(void)
0x180005aff  mov     eax, ebx
0x180005b01  mov     rcx, [rbp+0A0h+var_30]
0x180005b05  xor     rcx, rsp; StackCookie
0x180005b08  call    __security_check_cookie
0x180005b0d  lea     r11, [rsp+1A0h+var_10]
0x180005b15  mov     rbx, [r11+20h]
0x180005b19  mov     rsi, [r11+30h]
0x180005b1d  movaps  xmm6, xmmword ptr [r11-10h]
0x180005b22  mov     rsp, r11
0x180005b25  pop     r14
0x180005b27  pop     rdi
0x180005b28  pop     rbp
0x180005b29  retn
```

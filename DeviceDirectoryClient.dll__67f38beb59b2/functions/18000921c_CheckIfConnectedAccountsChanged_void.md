# CheckIfConnectedAccountsChanged(void)

- ea: `0x18000921c`
- end: `0x180009371`
- name: `?CheckIfConnectedAccountsChanged@@YAJXZ`
- size: `341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ca4c`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x180007350`
- `0x18000921c`
- `0x18001c8a4`

## import_xrefs

- `MdmCommon!MdmConnectedAccountsChanged` at `0x1800092cc`
- `MdmCommon!MdmConnectedAccountsChanged` at `0x1800092cc`

## string_xrefs

- `0x180009331`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`
- `0x18000931d`: `CHR(DdcCommandController::NotifyClient(WNF_SHEL_DDC_CONNECTED_ACCOUNTS_CHANGED))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CheckIfConnectedAccountsChanged(void)
{
  int v0; // edx
  int v1; // ecx
  int v2; // ebx
  int v3; // edx
  int v4; // ecx
  int v5; // edx
  int v6; // ecx
  unsigned int *v8; // [rsp+38h] [rbp-20h]
  struct Windows::Data::Json::IJsonValue *v9[3]; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  struct Windows::Data::Json::IJsonValue *v11; // [rsp+78h] [rbp+20h] BYREF
  struct Windows::Data::Json::IJsonValue *v12; // [rsp+80h] [rbp+28h] BYREF
  struct Windows::Data::Json::IJsonValue *v13; // [rsp+88h] [rbp+30h] BYREF

  v9[0] = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  v2 = DdcAccountHelper::EnumerateUsers(v9, &v13, &v12, &v11, 0, 0, 0, v8);
  if ( v2 >= 0 )
  {
    v2 = MdmConnectedAccountsChanged(2, v9[0], v13, v12, v11, &v10);
    if ( v2 >= 0 )
    {
      if ( v10 )
      {
        v2 = DdcCommandController::NotifyClient(WNF_SHEL_DDC_CONNECTED_ACCOUNTS_CHANGED, 0, 0);
        if ( v2 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v6,
            v5,
            v2,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            19,
            (__int64)"CHR(DdcCommandController::NotifyClient(WNF_SHEL_DDC_CONNECTED_ACCOUNTS_CHANGED))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        v2,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        12,
        (__int64)"CHR(MdmConnectedAccountsChanged(MdmDeviceContext_Desktop, pAdmins.Get(), pDeviceOwners.Get(), pStandard"
                 "Users.Get(), pConnectedAdmins.Get(), &fConnectedAccountsChanged))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v1,
      v0,
      v2,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
      11,
      (__int64)"CHR(DdcAccountHelper::EnumerateUsers(pAdmins.GetAddressOf(), pDeviceOwners.GetAddressOf(), pStandardUsers"
               ".GetAddressOf(), pConnectedAdmins.GetAddressOf()))");
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000921c  push    rbp
0x18000921e  push    rbx
0x18000921f  mov     rbp, rsp
0x180009222  sub     rsp, 58h
0x180009226  mov     [rbp+var_18], 0
0x18000922e  mov     [rbp+arg_18], 0
0x180009236  mov     [rbp+arg_10], 0
0x18000923e  mov     [rbp+arg_8], 0
0x180009246  mov     [rbp+arg_0], 0
0x18000924d  mov     [rsp+58h+var_28], 0; unsigned int *
0x180009256  mov     [rsp+58h+var_30], 0; unsigned int *
0x18000925f  mov     [rsp+58h+var_38], 0; unsigned int *
0x180009268  lea     r9, [rbp+arg_8]; struct Windows::Data::Json::IJsonValue **
0x18000926c  lea     r8, [rbp+arg_10]; struct Windows::Data::Json::IJsonValue **
0x180009270  lea     rdx, [rbp+arg_18]; struct Windows::Data::Json::IJsonValue **
0x180009274  lea     rcx, [rbp+var_18]; struct Windows::Data::Json::IJsonValue **
0x180009278  call    ?EnumerateUsers@DdcAccountHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@000PEAK111@Z; DdcAccountHelper::EnumerateUsers(Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *,ulong *)
0x18000927d  mov     ebx, eax
0x18000927f  test    eax, eax
0x180009281  jns     short loc_1800092A9
0x180009283  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000928a  jz      loc_180009341
0x180009290  lea     rax, aChrDdcaccounth; "CHR(DdcAccountHelper::EnumerateUsers(pA"...
0x180009297  mov     [rsp+58h+var_30], rax
0x18000929c  mov     dword ptr [rsp+58h+var_38], 10Bh
0x1800092a4  jmp     loc_180009331
0x1800092a9  mov     rax, [rbp+arg_8]
0x1800092ad  lea     rcx, [rbp+arg_0]
0x1800092b1  mov     [rsp+58h+var_30], rcx
0x1800092b6  mov     [rsp+58h+var_38], rax
0x1800092bb  mov     r9, [rbp+arg_10]
0x1800092bf  mov     r8, [rbp+arg_18]
0x1800092c3  mov     rdx, [rbp+var_18]
0x1800092c7  mov     ecx, 2
0x1800092cc  call    cs:__imp_?MdmConnectedAccountsChanged@@YAJW4MdmDeviceContext@@PEAUIJsonValue@Json@Data@Windows@@111PEAH@Z; MdmConnectedAccountsChanged(MdmDeviceContext,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *)
0x1800092d2  mov     ebx, eax
0x1800092d4  test    eax, eax
0x1800092d6  jns     short loc_1800092F7
0x1800092d8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800092df  jz      short loc_180009341
0x1800092e1  lea     rax, aChrMdmconnecte; "CHR(MdmConnectedAccountsChanged(MdmDevi"...
0x1800092e8  mov     [rsp+58h+var_30], rax
0x1800092ed  mov     dword ptr [rsp+58h+var_38], 10Ch
0x1800092f5  jmp     short loc_180009331
0x1800092f7  cmp     [rbp+arg_0], 0
0x1800092fb  jz      short loc_180009341
0x1800092fd  xor     r8d, r8d; unsigned int
0x180009300  xor     edx, edx; unsigned __int8 *
0x180009302  mov     rcx, qword ptr cs:WNF_SHEL_DDC_CONNECTED_ACCOUNTS_CHANGED.Data; struct _WNF_STATE_NAME
0x180009309  call    ?NotifyClient@DdcCommandController@@SAJU_WNF_STATE_NAME@@PEAEK@Z; DdcCommandController::NotifyClient(_WNF_STATE_NAME,uchar *,ulong)
0x18000930e  mov     ebx, eax
0x180009310  test    eax, eax
0x180009312  jns     short loc_180009341
0x180009314  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000931b  jz      short loc_180009341
0x18000931d  lea     rax, aChrDdccommandc; "CHR(DdcCommandController::NotifyClient("...
0x180009324  mov     [rsp+58h+var_30], rax
0x180009329  mov     dword ptr [rsp+58h+var_38], 113h
0x180009331  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180009338  mov     r8d, ebx
0x18000933b  call    McTemplateU0dsqs_EventWriteTransfer
0x180009340  nop
0x180009341  lea     rcx, [rbp+arg_8]
0x180009345  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000934a  nop
0x18000934b  lea     rcx, [rbp+arg_10]
0x18000934f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009354  nop
0x180009355  lea     rcx, [rbp+arg_18]
0x180009359  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000935e  nop
0x18000935f  lea     rcx, [rbp+var_18]
0x180009363  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009368  mov     eax, ebx
0x18000936a  add     rsp, 58h
0x18000936e  pop     rbx
0x18000936f  pop     rbp
0x180009370  retn
```

# DdcWnsListener::RegisterApplication(void)

- ea: `0x180024ae0`
- end: `0x180024d05`
- name: `?RegisterApplication@DdcWnsListener@@CAJXZ`
- size: `549`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024d0c`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x180024954`
- `0x180024ae0`
- `0x18002a010`

## string_xrefs

- `0x180024b97`: `MICROSOFT.WINDOWSPHONECCPSERVICE_8WEKYB3D8BBWE`
- `0x180024c69`: `MICROSOFT.WINDOWSPHONECCPSERVICE_8WEKYB3D8BBWE`
- `0x180024c9c`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcwnslistener.cpp`
- `0x180024b70`: `CHR(spWpnPlatform->CreateAppEndpoint(spAppEndpoint.GetAddressOf()))`
- `0x180024bd6`: `CHR(spWpnPlatform->CreateRegistrationEndpoint(spWpnRegistrationEndpoint.GetAddressOf()))`
- `0x180024c88`: `CHR(spWpnRegistrationSystemEndpoint->RegisterSystemApplication( wszPfn, wszAppId, CAPABLE_INTERNET | CAPABLE_CLOUD, sizeof(WNS_COMMAND_WNF_STATE), (PBYTE)(&(WNS_COMMAND_WNF_STATE.Data))))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 DdcWnsListener::RegisterApplication(void)
{
  int v0; // edx
  int v1; // ecx
  HRESULT SystemOrDefaultWpnPlatform; // ebx
  int v3; // edx
  int v4; // ecx
  int v5; // edx
  int v6; // ecx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v14; // rcx
  LPVOID ppv; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+30h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
  SystemOrDefaultWpnPlatform = GetSystemOrDefaultWpnPlatform(&ppv);
  if ( SystemOrDefaultWpnPlatform >= 0 )
  {
    SystemOrDefaultWpnPlatform = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v19);
    if ( SystemOrDefaultWpnPlatform >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v19 + 104LL))(
             v19,
             L"MICROSOFT.WINDOWSPHONECCPSERVICE_8WEKYB3D8BBWE",
             L"7bf7f519-2c1b-439d-b296-0878bd5c4991") < 0 )
      {
        SystemOrDefaultWpnPlatform = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)ppv + 40LL))(
                                       ppv,
                                       &v18);
        if ( SystemOrDefaultWpnPlatform >= 0 )
        {
          v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
          v8 = **v18;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
          SystemOrDefaultWpnPlatform = v8(v7, &GUID_7d85494e_d99e_493a_bf51_80d2c9feab49, &v17);
          if ( SystemOrDefaultWpnPlatform >= 0 )
          {
            SystemOrDefaultWpnPlatform = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64, int, __int64 *))(*(_QWORD *)v17 + 24LL))(
                                           v17,
                                           L"MICROSOFT.WINDOWSPHONECCPSERVICE_8WEKYB3D8BBWE",
                                           L"7bf7f519-2c1b-439d-b296-0878bd5c4991",
                                           2304,
                                           8,
                                           qword_180049348);
            if ( SystemOrDefaultWpnPlatform < 0
              && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v12,
                v11,
                SystemOrDefaultWpnPlatform,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
                167,
                "CHR(spWpnRegistrationSystemEndpoint->RegisterSystemApplication( wszPfn, wszAppId, CAPABLE_INTERNET | CAP"
                "ABLE_CLOUD, sizeof(WNS_COMMAND_WNF_STATE), (PBYTE)(&(WNS_COMMAND_WNF_STATE.Data))))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v10,
              v9,
              SystemOrDefaultWpnPlatform,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
              161,
              "CHR(spWpnRegistrationEndpoint.As(&spWpnRegistrationSystemEndpoint))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v6,
            v5,
            SystemOrDefaultWpnPlatform,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
            160,
            "CHR(spWpnPlatform->CreateRegistrationEndpoint(spWpnRegistrationEndpoint.GetAddressOf()))");
        }
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        SystemOrDefaultWpnPlatform,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
        153,
        "CHR(spWpnPlatform->CreateAppEndpoint(spAppEndpoint.GetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v1,
      v0,
      SystemOrDefaultWpnPlatform,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
      151,
      "CHR(GetSystemOrDefaultWpnPlatform(&spWpnPlatform))");
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
  if ( v18 )
  {
    v18 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
  }
  v14 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
  return (unsigned int)SystemOrDefaultWpnPlatform;
}

```

## disassembly

```asm
0x180024ae0  push    rbp
0x180024ae2  push    rbx
0x180024ae3  push    rdi
0x180024ae4  mov     rbp, rsp
0x180024ae7  sub     rsp, 40h
0x180024aeb  mov     [rbp+ppv], 0
0x180024af3  mov     [rbp+arg_18], 0
0x180024afb  mov     [rbp+arg_10], 0
0x180024b03  mov     [rbp+arg_8], 0
0x180024b0b  lea     rcx, [rbp+ppv]
0x180024b0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024b14  lea     rcx, [rbp+ppv]; ppv
0x180024b18  call    ?GetSystemOrDefaultWpnPlatform@@YAJPEAPEAUIWpnPlatform@@@Z; GetSystemOrDefaultWpnPlatform(IWpnPlatform * *)
0x180024b1d  mov     ebx, eax
0x180024b1f  test    eax, eax
0x180024b21  jns     short loc_180024B49
0x180024b23  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024b2a  jz      loc_180024CAC
0x180024b30  lea     rax, aChrGetsystemor; "CHR(GetSystemOrDefaultWpnPlatform(&spWp"...
0x180024b37  mov     [rsp+40h+var_18], rax
0x180024b3c  mov     [rsp+40h+var_20], 97h
0x180024b44  jmp     loc_180024C9C
0x180024b49  mov     rcx, [rbp+ppv]
0x180024b4d  mov     rax, [rcx]
0x180024b50  lea     rdx, [rbp+arg_18]
0x180024b54  mov     rax, [rax+18h]
0x180024b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b5d  mov     ebx, eax
0x180024b5f  test    eax, eax
0x180024b61  jns     short loc_180024B89
0x180024b63  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024b6a  jz      loc_180024CAC
0x180024b70  lea     rax, aChrSpwpnplatfo_0; "CHR(spWpnPlatform->CreateAppEndpoint(sp"...
0x180024b77  mov     [rsp+40h+var_18], rax
0x180024b7c  mov     [rsp+40h+var_20], 99h
0x180024b84  jmp     loc_180024C9C
0x180024b89  mov     rcx, [rbp+arg_18]
0x180024b8d  mov     rax, [rcx]
0x180024b90  lea     r8, a7bf7f5192c1b43; "7bf7f519-2c1b-439d-b296-0878bd5c4991"
0x180024b97  lea     rdx, aMicrosoftWindo_0; "MICROSOFT.WINDOWSPHONECCPSERVICE_8WEKYB"...
0x180024b9e  mov     rax, [rax+68h]
0x180024ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ba7  test    eax, eax
0x180024ba9  jns     loc_180024CAC
0x180024baf  mov     rcx, [rbp+ppv]
0x180024bb3  mov     rax, [rcx]
0x180024bb6  lea     rdx, [rbp+arg_10]
0x180024bba  mov     rax, [rax+28h]
0x180024bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bc3  mov     ebx, eax
0x180024bc5  test    eax, eax
0x180024bc7  jns     short loc_180024BEF
0x180024bc9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024bd0  jz      loc_180024CAC
0x180024bd6  lea     rax, aChrSpwpnplatfo; "CHR(spWpnPlatform->CreateRegistrationEn"...
0x180024bdd  mov     [rsp+40h+var_18], rax
0x180024be2  mov     [rsp+40h+var_20], 0A0h
0x180024bea  jmp     loc_180024C9C
0x180024bef  mov     rbx, [rbp+arg_10]
0x180024bf3  mov     rax, [rbx]
0x180024bf6  mov     rdi, [rax]
0x180024bf9  lea     rcx, [rbp+arg_8]
0x180024bfd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024c02  lea     r8, [rbp+arg_8]
0x180024c06  lea     rdx, _GUID_7d85494e_d99e_493a_bf51_80d2c9feab49
0x180024c0d  mov     rcx, rbx
0x180024c10  mov     rax, rdi
0x180024c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c18  mov     ebx, eax
0x180024c1a  test    eax, eax
0x180024c1c  jns     short loc_180024C41
0x180024c1e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024c25  jz      loc_180024CAC
0x180024c2b  lea     rax, aChrSpwpnregist_0; "CHR(spWpnRegistrationEndpoint.As(&spWpn"...
0x180024c32  mov     [rsp+40h+var_18], rax
0x180024c37  mov     [rsp+40h+var_20], 0A1h
0x180024c3f  jmp     short loc_180024C9C
0x180024c41  mov     rcx, [rbp+arg_8]
0x180024c45  mov     rax, [rcx]
0x180024c48  lea     r9, qword_180049348
0x180024c4f  mov     [rsp+40h+var_18], r9
0x180024c54  mov     [rsp+40h+var_20], 8
0x180024c5c  mov     r9d, 900h
0x180024c62  lea     r8, a7bf7f5192c1b43; "7bf7f519-2c1b-439d-b296-0878bd5c4991"
0x180024c69  lea     rdx, aMicrosoftWindo_0; "MICROSOFT.WINDOWSPHONECCPSERVICE_8WEKYB"...
0x180024c70  mov     rax, [rax+18h]
0x180024c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c79  mov     ebx, eax
0x180024c7b  test    eax, eax
0x180024c7d  jns     short loc_180024CAC
0x180024c7f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024c86  jz      short loc_180024CAC
0x180024c88  lea     rax, aChrSpwpnregist; "CHR(spWpnRegistrationSystemEndpoint->Re"...
0x180024c8f  mov     [rsp+40h+var_18], rax
0x180024c94  mov     [rsp+40h+var_20], 0A7h
0x180024c9c  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180024ca3  mov     r8d, ebx
0x180024ca6  call    McTemplateU0dsqs_EventWriteTransfer
0x180024cab  nop
0x180024cac  lea     rcx, [rbp+arg_8]
0x180024cb0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024cb5  nop
0x180024cb6  mov     rcx, [rbp+arg_10]
0x180024cba  test    rcx, rcx
0x180024cbd  jz      short loc_180024CD4
0x180024cbf  mov     [rbp+arg_10], 0
0x180024cc7  mov     rax, [rcx]
0x180024cca  mov     rax, [rax+10h]
0x180024cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cd3  nop
0x180024cd4  mov     rcx, [rbp+arg_18]
0x180024cd8  test    rcx, rcx
0x180024cdb  jz      short loc_180024CF2
0x180024cdd  mov     [rbp+arg_18], 0
0x180024ce5  mov     rax, [rcx]
0x180024ce8  mov     rax, [rax+10h]
0x180024cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cf1  nop
0x180024cf2  lea     rcx, [rbp+ppv]
0x180024cf6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024cfb  mov     eax, ebx
0x180024cfd  add     rsp, 40h
0x180024d01  pop     rdi
0x180024d02  pop     rbx
0x180024d03  pop     rbp
0x180024d04  retn
```

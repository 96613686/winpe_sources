# DdcCommandController::HandleSmsCommands(void)

- ea: `0x180006c00`
- end: `0x180006d9c`
- name: `?HandleSmsCommands@DdcCommandController@@SAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800024c0`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x180006748`
- `0x180006c00`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d41`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c78`

## string_xrefs

- `0x180006ca5`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x180006c91`: `CHR(CoCreateInstance(CLSID_SmsSharedSecret, 0, CLSCTX_INPROC_SERVER, IID_ISmsSharedSecret, (LPVOID *)pSmsSharedSecret.GetAddressOf()))`
- `0x180006cdd`: `CHR(pSmsSharedSecret->GetSmsCommands(&pwszCommands, &cCommands))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcCommandController::HandleSmsCommands(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edx
  int v4; // ecx
  HRESULT Instance; // ebx
  int v6; // edx
  int v7; // ecx
  __int64 i; // rdi
  LPVOID *v9; // rcx
  __int64 j; // rdi
  struct ISmsSharedSecret *v11; // rcx
  unsigned int v13; // [rsp+30h] [rbp-30h] BYREF
  struct ISmsSharedSecret *ppv; // [rsp+38h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v16[16]; // [rsp+48h] [rbp-18h] BYREF

  ppv = 0;
  pv = 0;
  v13 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, DEVICE_DIRECTORY_CLIENT_HANDLE_SMS_COMMANDS, a3, 1, v16);
  Instance = CoCreateInstance(&CLSID_SmsSharedSecret, 0, 1u, &IID_ISmsSharedSecret, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *, LPVOID *, unsigned int *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 &pv,
                 &v13);
    if ( Instance >= 0 )
    {
      for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
        Instance = DdcCommandController::HandleSmsCommand(*((wchar_t **)pv + i), ppv);
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        Instance,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        83,
        "CHR(pSmsSharedSecret->GetSmsCommands(&pwszCommands, &cCommands))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v4,
      v3,
      Instance,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
      82,
      "CHR(CoCreateInstance(CLSID_SmsSharedSecret, 0, CLSCTX_INPROC_SERVER, IID_ISmsSharedSecret, (LPVOID *)pSmsSharedSec"
      "ret.GetAddressOf()))");
  }
  v9 = (LPVOID *)pv;
  if ( pv )
  {
    for ( j = 0; (unsigned int)j < v13; j = (unsigned int)(j + 1) )
    {
      if ( v9[j] )
      {
        CoTaskMemFree(v9[j]);
        v9 = (LPVOID *)pv;
      }
    }
    CoTaskMemFree(v9);
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v9, DEVICE_DIRECTORY_CLIENT_HANDLE_SMS_COMMANDS_RESULT, (unsigned int)Instance);
  v11 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(struct ISmsSharedSecret *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180006c00  mov     [rsp-8+arg_0], rbx
0x180006c05  mov     [rsp-8+arg_8], rdi
0x180006c0a  push    rbp
0x180006c0b  mov     rbp, rsp
0x180006c0e  sub     rsp, 60h
0x180006c12  mov     rax, cs:__security_cookie
0x180006c19  xor     rax, rsp
0x180006c1c  mov     [rbp+var_8], rax
0x180006c20  mov     [rbp+var_28], 0
0x180006c28  mov     [rbp+pv], 0
0x180006c30  mov     [rbp+var_30], 0
0x180006c37  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180006c3e  jz      short loc_180006C5B
0x180006c40  lea     rax, [rbp+var_18]
0x180006c44  mov     [rsp+60h+ppv], rax
0x180006c49  mov     r9d, 1
0x180006c4f  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_SMS_COMMANDS
0x180006c56  call    McGenEventWrite_EventWriteTransfer
0x180006c5b  lea     rax, [rbp+var_28]
0x180006c5f  mov     [rsp+60h+ppv], rax; ppv
0x180006c64  lea     r9, IID_ISmsSharedSecret; riid
0x180006c6b  xor     edx, edx; pUnkOuter
0x180006c6d  lea     r8d, [rdx+1]; dwClsContext
0x180006c71  lea     rcx, CLSID_SmsSharedSecret; rclsid
0x180006c78  call    cs:__imp_CoCreateInstance
0x180006c7e  mov     ebx, eax
0x180006c80  test    eax, eax
0x180006c82  jns     short loc_180006CB6
0x180006c84  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006c8b  jz      loc_180006D14
0x180006c91  lea     rax, aChrCocreateins_1; "CHR(CoCreateInstance(CLSID_SmsSharedSec"...
0x180006c98  mov     [rsp+60h+var_38], rax
0x180006c9d  mov     dword ptr [rsp+60h+ppv], 52h ; 'R'
0x180006ca5  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180006cac  mov     r8d, ebx
0x180006caf  call    McTemplateU0dsqs_EventWriteTransfer
0x180006cb4  jmp     short loc_180006D14
0x180006cb6  mov     rcx, [rbp+var_28]
0x180006cba  mov     rax, [rcx]
0x180006cbd  lea     r8, [rbp+var_30]
0x180006cc1  lea     rdx, [rbp+pv]
0x180006cc5  mov     rax, [rax+18h]
0x180006cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cce  mov     ebx, eax
0x180006cd0  test    eax, eax
0x180006cd2  jns     short loc_180006CF3
0x180006cd4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006cdb  jz      short loc_180006D14
0x180006cdd  lea     rax, aChrPsmsshareds_1; "CHR(pSmsSharedSecret->GetSmsCommands(&p"...
0x180006ce4  mov     [rsp+60h+var_38], rax
0x180006ce9  mov     dword ptr [rsp+60h+ppv], 53h ; 'S'
0x180006cf1  jmp     short loc_180006CA5
0x180006cf3  xor     edi, edi
0x180006cf5  cmp     [rbp+var_30], edi
0x180006cf8  jbe     short loc_180006D14
0x180006cfa  mov     rdx, [rbp+var_28]; struct ISmsSharedSecret *
0x180006cfe  mov     rcx, [rbp+pv]
0x180006d02  mov     rcx, [rcx+rdi*8]; String1
0x180006d06  call    ?HandleSmsCommand@DdcCommandController@@SAJPEAGPEAUISmsSharedSecret@@@Z; DdcCommandController::HandleSmsCommand(ushort *,ISmsSharedSecret *)
0x180006d0b  mov     ebx, eax
0x180006d0d  inc     edi
0x180006d0f  cmp     edi, [rbp+var_30]
0x180006d12  jb      short loc_180006CFA
0x180006d14  mov     rcx, [rbp+pv]
0x180006d18  test    rcx, rcx
0x180006d1b  jz      short loc_180006D47
0x180006d1d  xor     edi, edi
0x180006d1f  cmp     [rbp+var_30], edi
0x180006d22  jbe     short loc_180006D41
0x180006d24  mov     rdx, [rcx+rdi*8]
0x180006d28  test    rdx, rdx
0x180006d2b  jz      short loc_180006D3A
0x180006d2d  mov     rcx, rdx; pv
0x180006d30  call    cs:__imp_CoTaskMemFree
0x180006d36  mov     rcx, [rbp+pv]; pv
0x180006d3a  inc     edi
0x180006d3c  cmp     edi, [rbp+var_30]
0x180006d3f  jb      short loc_180006D24
0x180006d41  call    cs:__imp_CoTaskMemFree
0x180006d47  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180006d4e  jz      short loc_180006D60
0x180006d50  mov     r8d, ebx
0x180006d53  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_SMS_COMMANDS_RESULT
0x180006d5a  call    McTemplateU0q_EventWriteTransfer
0x180006d5f  nop
0x180006d60  mov     rcx, [rbp+var_28]
0x180006d64  test    rcx, rcx
0x180006d67  jz      short loc_180006D7E
0x180006d69  mov     [rbp+var_28], 0
0x180006d71  mov     rax, [rcx]
0x180006d74  mov     rax, [rax+10h]
0x180006d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7d  nop
0x180006d7e  mov     eax, ebx
0x180006d80  mov     rcx, [rbp+var_8]
0x180006d84  xor     rcx, rsp; StackCookie
0x180006d87  call    __security_check_cookie
0x180006d8c  mov     rbx, [rsp+60h+arg_0]
0x180006d91  mov     rdi, [rsp+60h+arg_8]
0x180006d96  add     rsp, 60h
0x180006d9a  pop     rbp
0x180006d9b  retn
```

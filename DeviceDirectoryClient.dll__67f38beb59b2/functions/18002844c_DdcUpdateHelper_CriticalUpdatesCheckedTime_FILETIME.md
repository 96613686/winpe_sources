# DdcUpdateHelper::CriticalUpdatesCheckedTime(_FILETIME *)

- ea: `0x18002844c`
- end: `0x1800285c6`
- name: `?CriticalUpdatesCheckedTime@DdcUpdateHelper@@SAJPEAU_FILETIME@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(struct _FILETIME *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800183c4`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18002844c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800284db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800284db`

## string_xrefs

- `0x1800284a1`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcupdatehelper.cpp`
- `0x18002848d`: `CPR(pftLastUpdateCheckedTime)`
- `0x1800284f4`: `CHR(CoCreateInstance(__uuidof(UpdateSessionOrchestrator), nullptr, CLSCTX_LOCAL_SERVER, __uuidof(**(&pOrchestrator)), IID_PPV_ARGS_Helper(&pOrchestrator)))`
- `0x180028548`: `CHR(pOrchestrator->CreateUpdateSession(UpdateSessionTypeOTAOS, __uuidof(**(&pSession)), IID_PPV_ARGS_Helper(&pSession)))`
- `0x180028584`: `CHR(pSession->get_LastUpdateCheckTime(&ftLastUpdateCheckTime))`

## pseudocode

```c
__int64 __fastcall DdcUpdateHelper::CriticalUpdatesCheckedTime(struct _FILETIME *a1, int a2)
{
  HRESULT v3; // ebx
  int v4; // edx
  int v5; // ecx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, __int64, GUID *, __int64 *); // rbx
  int v8; // edx
  int v9; // ecx
  int v10; // edx
  int v11; // ecx
  __int64 v13; // [rsp+50h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF
  struct _FILETIME v15; // [rsp+60h] [rbp+30h] BYREF

  ppv = 0;
  v13 = 0;
  v15 = 0;
  if ( a1 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v3 = CoCreateInstance(
           &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
           0,
           4u,
           &GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0,
           &ppv);
    if ( v3 >= 0 )
    {
      v6 = ppv;
      v7 = *(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      v3 = v7(v6, 1, &GUID_b357f841_2130_454e_802c_5c398b549f8e, &v13);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME *))(*(_QWORD *)v13 + 72LL))(v13, &v15);
        if ( v3 >= 0 )
        {
          *a1 = v15;
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v11,
            v10,
            v3,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcupdatehelper.cpp",
            75,
            (__int64)"CHR(pSession->get_LastUpdateCheckTime(&ftLastUpdateCheckTime))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          v3,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcupdatehelper.cpp",
          74,
          (__int64)"CHR(pOrchestrator->CreateUpdateSession(UpdateSessionTypeOTAOS, __uuidof(**(&pSession)), IID_PPV_ARGS_"
                   "Helper(&pSession)))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        v3,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcupdatehelper.cpp",
        73,
        (__int64)"CHR(CoCreateInstance(__uuidof(UpdateSessionOrchestrator), nullptr, CLSCTX_LOCAL_SERVER, __uuidof(**(&pO"
                 "rchestrator)), IID_PPV_ARGS_Helper(&pOrchestrator)))");
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcupdatehelper.cpp",
        71,
        (__int64)"CPR(pftLastUpdateCheckedTime)");
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002844c  mov     [rsp-18h+arg_18], rbx
0x180028451  push    rbp
0x180028452  push    rsi
0x180028453  push    rdi
0x180028454  mov     rbp, rsp
0x180028457  sub     rsp, 30h
0x18002845b  mov     rsi, rcx
0x18002845e  mov     [rbp+arg_8], 0
0x180028466  mov     [rbp+arg_0], 0
0x18002846e  mov     [rbp+arg_10], 0
0x180028476  test    rcx, rcx
0x180028479  jnz     short loc_1800284B5
0x18002847b  mov     ebx, 80070057h
0x180028480  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180028487  jz      loc_1800285A4
0x18002848d  lea     rax, aCprPftlastupda; "CPR(pftLastUpdateCheckedTime)"
0x180028494  mov     [rsp+30h+var_8], rax
0x180028499  mov     dword ptr [rsp+30h+ppv], 47h ; 'G'
0x1800284a1  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800284a8  mov     r8d, ebx
0x1800284ab  call    McTemplateU0dsqs_EventWriteTransfer
0x1800284b0  jmp     loc_1800285A4
0x1800284b5  lea     rcx, [rbp+arg_8]
0x1800284b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800284be  lea     rax, [rbp+arg_8]
0x1800284c2  mov     [rsp+30h+ppv], rax; ppv
0x1800284c7  lea     r9, _GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0; riid
0x1800284ce  xor     edx, edx; pUnkOuter
0x1800284d0  lea     r8d, [rdx+4]; dwClsContext
0x1800284d4  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x1800284db  call    cs:__imp_CoCreateInstance
0x1800284e1  mov     ebx, eax
0x1800284e3  test    eax, eax
0x1800284e5  jns     short loc_18002850A
0x1800284e7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800284ee  jz      loc_1800285A4
0x1800284f4  lea     rax, aChrCocreateins_2; "CHR(CoCreateInstance(__uuidof(UpdateSes"...
0x1800284fb  mov     [rsp+30h+var_8], rax
0x180028500  mov     dword ptr [rsp+30h+ppv], 49h ; 'I'
0x180028508  jmp     short loc_1800284A1
0x18002850a  mov     rdi, [rbp+arg_8]
0x18002850e  mov     rax, [rdi]
0x180028511  mov     rbx, [rax+18h]
0x180028515  lea     rcx, [rbp+arg_0]
0x180028519  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002851e  lea     r9, [rbp+arg_0]
0x180028522  lea     r8, _GUID_b357f841_2130_454e_802c_5c398b549f8e
0x180028529  mov     edx, 1
0x18002852e  mov     rcx, rdi
0x180028531  mov     rax, rbx
0x180028534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028539  mov     ebx, eax
0x18002853b  test    eax, eax
0x18002853d  jns     short loc_180028561
0x18002853f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180028546  jz      short loc_1800285A4
0x180028548  lea     rax, aChrPorchestrat; "CHR(pOrchestrator->CreateUpdateSession("...
0x18002854f  mov     [rsp+30h+var_8], rax
0x180028554  mov     dword ptr [rsp+30h+ppv], 4Ah ; 'J'
0x18002855c  jmp     loc_1800284A1
0x180028561  mov     rcx, [rbp+arg_0]
0x180028565  mov     rax, [rcx]
0x180028568  lea     rdx, [rbp+arg_10]
0x18002856c  mov     rax, [rax+48h]
0x180028570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028575  mov     ebx, eax
0x180028577  test    eax, eax
0x180028579  jns     short loc_18002859D
0x18002857b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180028582  jz      short loc_1800285A4
0x180028584  lea     rax, aChrPsessionGet; "CHR(pSession->get_LastUpdateCheckTime(&"...
0x18002858b  mov     [rsp+30h+var_8], rax
0x180028590  mov     dword ptr [rsp+30h+ppv], 4Bh ; 'K'
0x180028598  jmp     loc_1800284A1
0x18002859d  mov     rax, [rbp+arg_10]
0x1800285a1  mov     [rsi], rax
0x1800285a4  lea     rcx, [rbp+arg_0]
0x1800285a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800285ad  nop
0x1800285ae  lea     rcx, [rbp+arg_8]
0x1800285b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800285b7  mov     eax, ebx
0x1800285b9  mov     rbx, [rsp+30h+arg_18]
0x1800285be  add     rsp, 30h
0x1800285c2  pop     rdi
0x1800285c3  pop     rsi
0x1800285c4  pop     rbp
0x1800285c5  retn
```

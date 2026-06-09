# HostAppEnvironment::_SetupVolumeControlServer(void *)

- ea: `0x180040ed4`
- end: `0x180040fc3`
- name: `?_SetupVolumeControlServer@HostAppEnvironment@@AEAAJPEAX@Z`
- size: `239`
- prototype: `int(HostAppEnvironment *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800408d0`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x18003ffac`
- `0x18003ffc0`
- `0x18003ffd0`
- `0x180040ed4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040f9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040f9a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040f16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040f16`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180040f51`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180040f51`

## pseudocode

```c
__int64 __fastcall HostAppEnvironment::_SetupVolumeControlServer(HostAppEnvironment *this, void *a2)
{
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rax
  int ppv; // [rsp+20h] [rbp-28h]
  _BYTE v9[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HostAppEnvironment *dwRegister; // [rsp+50h] [rbp+8h] BYREF
  char v12; // [rsp+60h] [rbp+18h] BYREF
  LPUNKNOWN pUnk; // [rsp+68h] [rbp+20h] BYREF

  dwRegister = this;
  pUnk = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
  Instance = CoCreateInstance(
               &GUID_53eadd15_d8b4_4b89_9d35_c1c7a7718960,
               0,
               1u,
               &GUID_00000001_0000_0000_c000_000000000046,
               (LPVOID *)&pUnk);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    LODWORD(dwRegister) = 0;
    Instance = CoRegisterClassObject(&GUID_c751d52a_f7ac_4280_886e_b6341626fd22, pUnk, 4u, 1u, (LPDWORD)&dwRegister);
    v4 = Instance;
    if ( Instance >= 0 )
    {
      v6 = lambda_a23e843b62804e11cc15255fd86bcbdc_::_lambda_a23e843b62804e11cc15255fd86bcbdc_(&v12, &dwRegister);
      wil::ScopeExit__lambda_a23e843b62804e11cc15255fd86bcbdc___(v9, v6);
      WaitForSingleObject(a2, 0xFFFFFFFF);
      wil::details::ScopeExitFn__lambda_3487551f4e1881115ab3112cef1670aa___::_ScopeExitFn__lambda_3487551f4e1881115ab3112cef1670aa___(v9);
      v4 = 0;
      goto LABEL_7;
    }
    v5 = 222;
  }
  else
  {
    v5 = 214;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
  return v4;
}

```

## disassembly

```asm
0x180040ed4  mov     rax, rsp
0x180040ed7  mov     [rax+10h], rbx
0x180040edb  mov     [rax+8], rcx
0x180040edf  push    rdi
0x180040ee0  sub     rsp, 40h
0x180040ee4  lea     rcx, [rax+20h]
0x180040ee8  mov     qword ptr [rax+20h], 0
0x180040ef0  mov     rdi, rdx
0x180040ef3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040ef8  xor     edx, edx; pUnkOuter
0x180040efa  lea     rax, [rsp+48h+pUnk]
0x180040eff  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180040f06  mov     qword ptr [rsp+48h+ppv], rax; ppv
0x180040f0b  lea     rcx, _GUID_53eadd15_d8b4_4b89_9d35_c1c7a7718960; rclsid
0x180040f12  lea     r8d, [rdx+1]; dwClsContext
0x180040f16  call    cs:__imp_CoCreateInstance
0x180040f1c  mov     ebx, eax
0x180040f1e  test    eax, eax
0x180040f20  jns     short loc_180040F29
0x180040f22  mov     edx, 0D6h
0x180040f27  jmp     short loc_180040F62
0x180040f29  mov     rdx, [rsp+48h+pUnk]; pUnk
0x180040f2e  lea     rax, [rsp+48h+dwRegister]
0x180040f33  mov     r9d, 1; flags
0x180040f39  mov     dword ptr [rsp+48h+dwRegister], 0
0x180040f41  lea     rcx, _GUID_c751d52a_f7ac_4280_886e_b6341626fd22; rclsid
0x180040f48  mov     qword ptr [rsp+48h+ppv], rax; int
0x180040f4d  lea     r8d, [r9+3]; dwClsContext
0x180040f51  call    cs:__imp_CoRegisterClassObject
0x180040f57  mov     ebx, eax
0x180040f59  test    eax, eax
0x180040f5b  jns     short loc_180040F78
0x180040f5d  mov     edx, 0DEh; void *
0x180040f62  mov     rcx, [rsp+48h]; this
0x180040f67  lea     r8, aShellLibCloude_1; "shell\\lib\\cloudexperiencehostappmanag"...
0x180040f6e  mov     r9d, eax; char *
0x180040f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f76  jmp     short loc_180040FAC
0x180040f78  lea     rdx, [rsp+48h+dwRegister]
0x180040f7d  lea     rcx, [rsp+48h+arg_10]
0x180040f82  call    _lambda_a23e843b62804e11cc15255fd86bcbdc____lambda_a23e843b62804e11cc15255fd86bcbdc_
0x180040f87  mov     rdx, rax
0x180040f8a  lea     rcx, [rsp+48h+var_18]
0x180040f8f  call    wil__ScopeExit__lambda_a23e843b62804e11cc15255fd86bcbdc___
0x180040f94  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180040f97  mov     rcx, rdi; hHandle
0x180040f9a  call    cs:__imp_WaitForSingleObject
0x180040fa0  lea     rcx, [rsp+48h+var_18]
0x180040fa5  call    wil__details__ScopeExitFn__lambda_3487551f4e1881115ab3112cef1670aa______ScopeExitFn__lambda_3487551f4e1881115ab3112cef1670aa___
0x180040faa  xor     ebx, ebx
0x180040fac  lea     rcx, [rsp+48h+pUnk]
0x180040fb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040fb6  mov     eax, ebx
0x180040fb8  mov     rbx, [rsp+48h+arg_8]
0x180040fbd  add     rsp, 40h
0x180040fc1  pop     rdi
0x180040fc2  retn
```

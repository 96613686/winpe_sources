# HostAppEnvironment::_SetupInputSwitchServer(void *)

- ea: `0x180040d48`
- end: `0x180040ecb`
- name: `?_SetupInputSwitchServer@HostAppEnvironment@@AEAAJPEAX@Z`
- size: `387`
- prototype: `int(HostAppEnvironment *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040900`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x18000e270`
- `0x18003ffac`
- `0x18003ffc0`
- `0x180040010`
- `0x180040d48`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040e9c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040e9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040d88`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040e31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040d88`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040e31`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180040dc0`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180040dc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HostAppEnvironment::_SetupInputSwitchServer(HostAppEnvironment *this, void *a2)
{
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rax
  HRESULT v7; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  LPUNKNOWN pUnk; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HostAppEnvironment *dwRegister; // [rsp+60h] [rbp+20h] BYREF
  char v17; // [rsp+70h] [rbp+30h] BYREF
  LPVOID v18; // [rsp+78h] [rbp+38h] BYREF

  dwRegister = this;
  pUnk = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
  Instance = CoCreateInstance(
               &GUID_1d697619_5d35_44a1_a0f6_1c305324c9d0,
               0,
               1u,
               &GUID_00000001_0000_0000_c000_000000000046,
               (LPVOID *)&pUnk);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    LODWORD(dwRegister) = 0;
    Instance = CoRegisterClassObject(&GUID_0b86ccd2_7513_4f0a_ae1a_791a6d4db81d, pUnk, 4u, 1u, (LPDWORD)&dwRegister);
    v4 = Instance;
    if ( Instance < 0 )
    {
      v5 = 184;
      goto LABEL_5;
    }
    v6 = lambda_a23e843b62804e11cc15255fd86bcbdc_::_lambda_a23e843b62804e11cc15255fd86bcbdc_(&v17, &dwRegister);
    wil::ScopeExit__lambda_a23e843b62804e11cc15255fd86bcbdc___(v14, v6);
    v18 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    v7 = CoCreateInstance(
           &GUID_b9bc2a50_43c3_41aa_a086_5db14e184bae,
           0,
           1u,
           &GUID_b9bc2a50_43c3_41aa_a082_5db14e184bae,
           &v18);
    v8 = retaddr;
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v18 + 24LL))(v18, 6);
      v8 = retaddr;
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 64LL))(v18);
        v8 = retaddr;
        if ( v7 >= 0 )
        {
LABEL_13:
          WaitForSingleObject(a2, 0xFFFFFFFF);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
          wil::details::ScopeExitFn__lambda_a23e843b62804e11cc15255fd86bcbdc___::_ScopeExitFn__lambda_a23e843b62804e11cc15255fd86bcbdc___(v14);
          v4 = 0;
          goto LABEL_14;
        }
        v9 = 198;
      }
      else
      {
        v9 = 196;
      }
    }
    else
    {
      v9 = 195;
    }
    wil::details::in1diag3::_Log_Hr(
      v8,
      (void *)v9,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
      (const char *)(unsigned int)v7,
      ppva);
    goto LABEL_13;
  }
  v5 = 176;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
  return v4;
}

```

## disassembly

```asm
0x180040d48  mov     [rsp-18h+dwRegister], rcx
0x180040d4d  push    rbp
0x180040d4e  push    rbx
0x180040d4f  push    rdi
0x180040d50  mov     rbp, rsp
0x180040d53  sub     rsp, 40h
0x180040d57  mov     rdi, rdx
0x180040d5a  mov     [rbp+pUnk], 0
0x180040d62  lea     rcx, [rbp+pUnk]
0x180040d66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040d6b  lea     rax, [rbp+pUnk]
0x180040d6f  mov     qword ptr [rsp+40h+ppv], rax; ppv
0x180040d74  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180040d7b  xor     edx, edx; pUnkOuter
0x180040d7d  lea     r8d, [rdx+1]; dwClsContext
0x180040d81  lea     rcx, _GUID_1d697619_5d35_44a1_a0f6_1c305324c9d0; rclsid
0x180040d88  call    cs:__imp_CoCreateInstance
0x180040d8e  mov     ebx, eax
0x180040d90  test    eax, eax
0x180040d92  jns     short loc_180040D9B
0x180040d94  mov     edx, 0B0h
0x180040d99  jmp     short loc_180040DD1
0x180040d9b  mov     dword ptr [rbp+dwRegister], 0
0x180040da2  lea     rax, [rbp+dwRegister]
0x180040da6  mov     qword ptr [rsp+40h+ppv], rax; int
0x180040dab  mov     r9d, 1; flags
0x180040db1  lea     r8d, [r9+3]; dwClsContext
0x180040db5  mov     rdx, [rbp+pUnk]; pUnk
0x180040db9  lea     rcx, _GUID_0b86ccd2_7513_4f0a_ae1a_791a6d4db81d; rclsid
0x180040dc0  call    cs:__imp_CoRegisterClassObject
0x180040dc6  mov     ebx, eax
0x180040dc8  test    eax, eax
0x180040dca  jns     short loc_180040DE9
0x180040dcc  mov     edx, 0B8h; void *
0x180040dd1  lea     r8, aShellLibCloude_1; "shell\\lib\\cloudexperiencehostappmanag"...
0x180040dd8  mov     r9d, eax; char *
0x180040ddb  mov     rcx, [rbp+18h]; this
0x180040ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040de4  jmp     loc_180040EB8
0x180040de9  lea     rdx, [rbp+dwRegister]
0x180040ded  lea     rcx, [rbp+arg_10]
0x180040df1  call    _lambda_a23e843b62804e11cc15255fd86bcbdc____lambda_a23e843b62804e11cc15255fd86bcbdc_
0x180040df6  mov     rdx, rax
0x180040df9  lea     rcx, [rbp+var_8]
0x180040dfd  call    wil__ScopeExit__lambda_a23e843b62804e11cc15255fd86bcbdc___
0x180040e02  nop
0x180040e03  mov     [rbp+arg_18], 0
0x180040e0b  lea     rcx, [rbp+arg_18]
0x180040e0f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040e14  lea     rax, [rbp+arg_18]
0x180040e18  mov     qword ptr [rsp+40h+ppv], rax; int
0x180040e1d  lea     r9, _GUID_b9bc2a50_43c3_41aa_a082_5db14e184bae; riid
0x180040e24  xor     edx, edx; pUnkOuter
0x180040e26  lea     r8d, [rdx+1]; dwClsContext
0x180040e2a  lea     rcx, _GUID_b9bc2a50_43c3_41aa_a086_5db14e184bae; rclsid
0x180040e31  call    cs:__imp_CoCreateInstance
0x180040e37  mov     rcx, [rbp+18h]
0x180040e3b  test    eax, eax
0x180040e3d  jns     short loc_180040E46
0x180040e3f  mov     edx, 0C3h
0x180040e44  jmp     short loc_180040E87
0x180040e46  mov     rcx, [rbp+arg_18]
0x180040e4a  mov     rax, [rcx]
0x180040e4d  mov     edx, 6
0x180040e52  mov     rax, [rax+18h]
0x180040e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e5b  mov     rcx, [rbp+18h]
0x180040e5f  test    eax, eax
0x180040e61  jns     short loc_180040E6A
0x180040e63  mov     edx, 0C4h
0x180040e68  jmp     short loc_180040E87
0x180040e6a  mov     rcx, [rbp+arg_18]
0x180040e6e  mov     rax, [rcx]
0x180040e71  mov     rax, [rax+40h]
0x180040e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e7a  mov     rcx, [rbp+18h]; this
0x180040e7e  test    eax, eax
0x180040e80  jns     short loc_180040E96
0x180040e82  mov     edx, 0C6h; void *
0x180040e87  mov     r9d, eax; char *
0x180040e8a  lea     r8, aShellLibCloude_1; "shell\\lib\\cloudexperiencehostappmanag"...
0x180040e91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040e96  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180040e99  mov     rcx, rdi; hHandle
0x180040e9c  call    cs:__imp_WaitForSingleObject
0x180040ea2  nop
0x180040ea3  lea     rcx, [rbp+arg_18]
0x180040ea7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040eac  nop
0x180040ead  lea     rcx, [rbp+var_8]
0x180040eb1  call    wil__details__ScopeExitFn__lambda_a23e843b62804e11cc15255fd86bcbdc______ScopeExitFn__lambda_a23e843b62804e11cc15255fd86bcbdc___
0x180040eb6  xor     ebx, ebx
0x180040eb8  lea     rcx, [rbp+pUnk]
0x180040ebc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040ec1  mov     eax, ebx
0x180040ec3  add     rsp, 40h
0x180040ec7  pop     rdi
0x180040ec8  pop     rbx
0x180040ec9  pop     rbp
0x180040eca  retn
```

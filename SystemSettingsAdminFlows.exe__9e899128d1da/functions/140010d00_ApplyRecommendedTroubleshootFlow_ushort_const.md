# ApplyRecommendedTroubleshootFlow(ushort const *)

- ea: `0x140010d00`
- end: `0x140010f4d`
- name: `?ApplyRecommendedTroubleshootFlow@@YAJPEBG@Z`
- size: `589`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x140010d00`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x14007d010`

## import_xrefs

- `ole32!CoGetClassObject` at `0x140010e57`
- `ole32!CoGetClassObject` at `0x140010e57`
- `ole32!CLSIDFromString` at `0x140010d52`
- `ole32!CLSIDFromString` at `0x140010d52`
- `ole32!CoCreateInstance` at `0x140010dc8`
- `ole32!CoCreateInstance` at `0x140010dc8`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140010d2f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140010d2f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140010d8e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140010f24`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140010d8e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140010f24`
- `RPCRT4!UuidFromStringW` at `0x140010d63`
- `RPCRT4!UuidFromStringW` at `0x140010d63`

## string_xrefs

- `0x140010d76`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x140010dd9`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x140010e6f`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ApplyRecommendedTroubleshootFlow(RPC_WSTR StringUuid, __int64 a2)
{
  RPC_STATUS v3; // eax
  HRESULT ClassObject; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, _QWORD, GUID *, __int64 *); // rbx
  int ppv; // [rsp+20h] [rbp-29h]
  int ppva; // [rsp+20h] [rbp-29h]
  int ppvb; // [rsp+20h] [rbp-29h]
  int v13; // [rsp+30h] [rbp-19h] BYREF
  LPVOID v14; // [rsp+38h] [rbp-11h] BYREF
  LPVOID v15; // [rsp+40h] [rbp-9h] BYREF
  __int64 v16; // [rsp+48h] [rbp-1h] BYREF
  int v17; // [rsp+50h] [rbp+7h] BYREF
  int *v18; // [rsp+58h] [rbp+Fh]
  char v19; // [rsp+60h] [rbp+17h]
  GUID v20; // [rsp+70h] [rbp+27h] BYREF
  GUID pclsid; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v13 = RoInitialize(1, a2);
  v18 = &v13;
  v19 = 1;
  pclsid = 0;
  if ( CLSIDFromString(StringUuid, &pclsid) < 0 )
  {
    v3 = UuidFromStringW(StringUuid, &pclsid);
    ClassObject = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70F,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
        (const char *)(unsigned int)v3,
        ppv);
LABEL_4:
      if ( v13 >= 0 )
        RoUninitialize();
      return (unsigned int)ClassObject;
    }
  }
  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  ClassObject = CoCreateInstance(&CLSID_MitigationState, 0, 1u, &GUID_d555b534_8777_464a_8acc_781e36aa123e, &v14);
  if ( ClassObject < 0 )
  {
    v6 = 1812;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
      (const char *)(unsigned int)ClassObject,
      ppva);
LABEL_10:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    goto LABEL_4;
  }
  v17 = 0;
  ClassObject = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v14 + 40LL))(v14, &v17);
  if ( ClassObject < 0 )
  {
    v6 = 1816;
    goto LABEL_9;
  }
  v16 = 0;
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  ClassObject = CoGetClassObject(&CLSID_MitigationAPIBroker, 4u, 0, &GUID_00000001_0000_0000_c000_000000000046, &v15);
  if ( ClassObject < 0 )
  {
    v7 = 1821;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
      (const char *)(unsigned int)ClassObject,
      ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    goto LABEL_10;
  }
  v8 = v15;
  v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)v15 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  ClassObject = v9(v8, 0, &GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe, &v16);
  if ( ClassObject < 0 )
  {
    v7 = 1822;
    goto LABEL_15;
  }
  if ( v17 == 2 )
  {
    v20 = pclsid;
    ClassObject = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v16 + 32LL))(v16, &v20);
    if ( ClassObject < 0 )
    {
      v7 = 1826;
      goto LABEL_15;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  if ( v13 >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140010d00  mov     [rsp-8+arg_8], rbx
0x140010d05  mov     [rsp-8+arg_10], rdi
0x140010d0a  push    rbp
0x140010d0b  lea     rbp, [rsp-57h]
0x140010d10  sub     rsp, 0A0h
0x140010d17  mov     rax, cs:__security_cookie
0x140010d1e  xor     rax, rsp
0x140010d21  mov     [rbp+57h+var_10], rax
0x140010d25  mov     rbx, rcx
0x140010d28  mov     edi, 1
0x140010d2d  mov     ecx, edi
0x140010d2f  call    cs:__imp_RoInitialize
0x140010d35  mov     [rbp+57h+var_70], eax
0x140010d38  lea     rax, [rbp+57h+var_70]
0x140010d3c  mov     [rbp+57h+var_48], rax
0x140010d40  mov     [rbp+57h+var_40], dil
0x140010d44  xorps   xmm0, xmm0
0x140010d47  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140010d4b  lea     rdx, [rbp+57h+pclsid]; pclsid
0x140010d4f  mov     rcx, rbx; lpsz
0x140010d52  call    cs:__imp_CLSIDFromString
0x140010d58  test    eax, eax
0x140010d5a  jns     short loc_140010D9B
0x140010d5c  lea     rdx, [rbp+57h+pclsid]; Uuid
0x140010d60  mov     rcx, rbx; StringUuid
0x140010d63  call    cs:__imp_UuidFromStringW
0x140010d69  mov     ebx, eax
0x140010d6b  test    eax, eax
0x140010d6d  jns     short loc_140010D9B
0x140010d6f  mov     rcx, [rbp+5Fh]; this
0x140010d73  mov     r9d, eax; char *
0x140010d76  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x140010d7d  mov     edx, 70Fh; void *
0x140010d82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010d87  nop
0x140010d88  cmp     [rbp+57h+var_70], 0
0x140010d8c  jl      short loc_140010D94
0x140010d8e  call    cs:__imp_RoUninitialize
0x140010d94  mov     eax, ebx
0x140010d96  jmp     loc_140010F2C
0x140010d9b  mov     [rbp+57h+var_68], 0
0x140010da3  lea     rcx, [rbp+57h+var_68]
0x140010da7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010dac  lea     rax, [rbp+57h+var_68]
0x140010db0  mov     qword ptr [rsp+0A0h+ppv], rax; int
0x140010db5  lea     r9, _GUID_d555b534_8777_464a_8acc_781e36aa123e; riid
0x140010dbc  mov     r8d, edi; dwClsContext
0x140010dbf  xor     edx, edx; pUnkOuter
0x140010dc1  lea     rcx, CLSID_MitigationState; rclsid
0x140010dc8  call    cs:__imp_CoCreateInstance
0x140010dce  mov     ebx, eax
0x140010dd0  test    eax, eax
0x140010dd2  jns     short loc_140010DF8
0x140010dd4  mov     edx, 714h; void *
0x140010dd9  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x140010de0  mov     r9d, ebx; char *
0x140010de3  mov     rcx, [rbp+5Fh]; this
0x140010de7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010dec  nop
0x140010ded  lea     rcx, [rbp+57h+var_68]
0x140010df1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010df6  jmp     short loc_140010D88
0x140010df8  mov     [rbp+57h+var_50], 0
0x140010dff  mov     rcx, [rbp+57h+var_68]
0x140010e03  mov     rax, [rcx]
0x140010e06  lea     rdx, [rbp+57h+var_50]
0x140010e0a  mov     rax, [rax+28h]
0x140010e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e13  mov     ebx, eax
0x140010e15  test    eax, eax
0x140010e17  jns     short loc_140010E20
0x140010e19  mov     edx, 718h
0x140010e1e  jmp     short loc_140010DD9
0x140010e20  mov     [rbp+57h+var_58], 0
0x140010e28  mov     [rbp+57h+var_60], 0
0x140010e30  lea     rcx, [rbp+57h+var_60]
0x140010e34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010e39  lea     rax, [rbp+57h+var_60]
0x140010e3d  mov     qword ptr [rsp+0A0h+ppv], rax; int
0x140010e42  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x140010e49  xor     r8d, r8d; pvReserved
0x140010e4c  lea     edx, [r8+4]; dwClsContext
0x140010e50  lea     rcx, CLSID_MitigationAPIBroker; rclsid
0x140010e57  call    cs:__imp_CoGetClassObject
0x140010e5d  mov     ebx, eax
0x140010e5f  test    eax, eax
0x140010e61  jns     short loc_140010E94
0x140010e63  mov     edx, 71Dh; void *
0x140010e68  mov     rcx, [rbp+5Fh]; this
0x140010e6c  mov     r9d, ebx; char *
0x140010e6f  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x140010e76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010e7b  nop
0x140010e7c  lea     rcx, [rbp+57h+var_60]
0x140010e80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010e85  nop
0x140010e86  lea     rcx, [rbp+57h+var_58]
0x140010e8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010e8f  jmp     loc_140010DED
0x140010e94  mov     rdi, [rbp+57h+var_60]
0x140010e98  mov     rax, [rdi]
0x140010e9b  mov     rbx, [rax+18h]
0x140010e9f  lea     rcx, [rbp+57h+var_58]
0x140010ea3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010ea8  lea     r9, [rbp+57h+var_58]
0x140010eac  lea     r8, _GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe
0x140010eb3  xor     edx, edx
0x140010eb5  mov     rcx, rdi
0x140010eb8  mov     rax, rbx
0x140010ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ec0  mov     ebx, eax
0x140010ec2  test    eax, eax
0x140010ec4  jns     short loc_140010ECD
0x140010ec6  mov     edx, 71Eh
0x140010ecb  jmp     short loc_140010E68
0x140010ecd  cmp     [rbp+57h+var_50], 2
0x140010ed1  jnz     short loc_140010F00
0x140010ed3  mov     rcx, [rbp+57h+var_58]
0x140010ed7  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x140010edb  movdqa  [rbp+57h+var_30], xmm0
0x140010ee0  mov     rax, [rcx]
0x140010ee3  lea     rdx, [rbp+57h+var_30]
0x140010ee7  mov     rax, [rax+20h]
0x140010eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ef0  mov     ebx, eax
0x140010ef2  test    eax, eax
0x140010ef4  jns     short loc_140010F00
0x140010ef6  mov     edx, 722h
0x140010efb  jmp     loc_140010E68
0x140010f00  lea     rcx, [rbp+57h+var_60]
0x140010f04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010f09  nop
0x140010f0a  lea     rcx, [rbp+57h+var_58]
0x140010f0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010f13  nop
0x140010f14  lea     rcx, [rbp+57h+var_68]
0x140010f18  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010f1d  nop
0x140010f1e  cmp     [rbp+57h+var_70], 0
0x140010f22  jl      short loc_140010F2A
0x140010f24  call    cs:__imp_RoUninitialize
0x140010f2a  xor     eax, eax
0x140010f2c  mov     rcx, [rbp+57h+var_10]
0x140010f30  xor     rcx, rsp; StackCookie
0x140010f33  call    __security_check_cookie
0x140010f38  lea     r11, [rsp+0A0h+var_s0]
0x140010f40  mov     rbx, [r11+18h]
0x140010f44  mov     rdi, [r11+20h]
0x140010f48  mov     rsp, r11
0x140010f4b  pop     rbp
0x140010f4c  retn
```

# Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaBridgeImpl::s_SetProxyBlanket(IUnknown *)

- ea: `0x180028cf0`
- end: `0x180028e12`
- name: `?s_SetProxyBlanket@AvrcpMediaBridgeImpl@Avrcp@Profiles@Bluetooth@Microsoft@@CAJPEAUIUnknown@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(IUnknown *pProxy)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180028970`

## callees

- `0x18000751c`
- `0x18000d0c0`
- `0x180028900`
- `0x180028cf0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180028cfd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180028cfd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180028d41`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180028dca`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180028d41`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180028dca`

## string_xrefs

- `0x180028d52`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avrcpmediabridge.cpp`
- `0x180028dde`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avrcpmediabridge.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaBridgeImpl::s_SetProxyBlanket(IUnknown *pProxy)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  HRESULT v5; // eax
  __int64 v6; // rdx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HRESULT v10; // [rsp+58h] [rbp+10h] BYREF
  IUnknown *pProxya; // [rsp+60h] [rbp+18h] BYREF

  v2 = CoImpersonateClient();
  v3 = v2;
  v10 = v2;
  if ( v2 >= 0 )
  {
    v2 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, 0, 0, 2u, 0, 0x20u);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = 75;
      goto LABEL_5;
    }
    pProxya = 0;
    v5 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
           pProxy,
           &GUID_00000000_0000_0000_c000_000000000046,
           &pProxya);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v5 = CoSetProxyBlanket(pProxya, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0x20u);
      v3 = v5;
      if ( v5 >= 0 )
      {
LABEL_11:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxya);
        goto LABEL_12;
      }
      v6 = 90;
    }
    else
    {
      v6 = 79;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avrcpmediabridge.cpp",
      (const char *)(unsigned int)v5,
      dwAuthnLevel);
    goto LABEL_11;
  }
  v4 = 64;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avrcpmediabridge.cpp",
    (const char *)(unsigned int)v2,
    dwAuthnLevel);
LABEL_12:
  Microsoft::Bluetooth::Foundation::ComImpersonation::~ComImpersonation((Microsoft::Bluetooth::Foundation::ComImpersonation *)&v10);
  return v3;
}

```

## disassembly

```asm
0x180028cf0  mov     [rsp+arg_0], rbx
0x180028cf5  push    rdi
0x180028cf6  sub     rsp, 40h
0x180028cfa  mov     rdi, rcx
0x180028cfd  call    cs:__imp_CoImpersonateClient
0x180028d03  mov     ebx, eax
0x180028d05  mov     [rsp+48h+arg_8], eax
0x180028d09  test    eax, eax
0x180028d0b  jns     short loc_180028D14
0x180028d0d  mov     edx, 40h ; '@'
0x180028d12  jmp     short loc_180028D52
0x180028d14  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180028d1c  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x180028d25  mov     [rsp+48h+dwImpLevel], 2; dwImpLevel
0x180028d2d  mov     [rsp+48h+dwAuthnLevel], 0; int
0x180028d35  xor     r9d, r9d; pServerPrincName
0x180028d38  xor     r8d, r8d; dwAuthzSvc
0x180028d3b  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180028d3e  mov     rcx, rdi; pProxy
0x180028d41  call    cs:__imp_CoSetProxyBlanket
0x180028d47  mov     ebx, eax
0x180028d49  test    eax, eax
0x180028d4b  jns     short loc_180028D6B
0x180028d4d  mov     edx, 4Bh ; 'K'; void *
0x180028d52  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180028d59  mov     r9d, eax; char *
0x180028d5c  mov     rcx, [rsp+48h]; this
0x180028d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d66  jmp     loc_180028DFB
0x180028d6b  mov     [rsp+48h+pProxy], 0
0x180028d74  mov     rax, [rdi]
0x180028d77  lea     r8, [rsp+48h+pProxy]
0x180028d7c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180028d83  mov     rcx, rdi
0x180028d86  mov     rax, [rax]
0x180028d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d8e  mov     ebx, eax
0x180028d90  test    eax, eax
0x180028d92  jns     short loc_180028D9B
0x180028d94  mov     edx, 4Fh ; 'O'
0x180028d99  jmp     short loc_180028DDB
0x180028d9b  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180028da3  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x180028dac  mov     [rsp+48h+dwImpLevel], 0; dwImpLevel
0x180028db4  mov     [rsp+48h+dwAuthnLevel], 0; int
0x180028dbc  xor     r9d, r9d; pServerPrincName
0x180028dbf  xor     r8d, r8d; dwAuthzSvc
0x180028dc2  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180028dc5  mov     rcx, [rsp+48h+pProxy]; pProxy
0x180028dca  call    cs:__imp_CoSetProxyBlanket
0x180028dd0  mov     ebx, eax
0x180028dd2  test    eax, eax
0x180028dd4  jns     short loc_180028DF0
0x180028dd6  mov     edx, 5Ah ; 'Z'; void *
0x180028ddb  mov     r9d, eax; char *
0x180028dde  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180028de5  mov     rcx, [rsp+48h]; this
0x180028dea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028def  nop
0x180028df0  lea     rcx, [rsp+48h+pProxy]
0x180028df5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028dfa  nop
0x180028dfb  lea     rcx, [rsp+48h+arg_8]; this
0x180028e00  call    ??1ComImpersonation@Foundation@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Foundation::ComImpersonation::~ComImpersonation(void)
0x180028e05  mov     eax, ebx
0x180028e07  mov     rbx, [rsp+48h+arg_0]
0x180028e0c  add     rsp, 40h
0x180028e10  pop     rdi
0x180028e11  retn
```

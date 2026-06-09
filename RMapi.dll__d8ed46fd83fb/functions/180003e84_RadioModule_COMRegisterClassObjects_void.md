# RadioModule::COMRegisterClassObjects(void)

- ea: `0x180003e84`
- end: `0x180003f93`
- name: `?COMRegisterClassObjects@RadioModule@@AEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(RadioModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003d78`

## callees

- `0x180002ec0`
- `0x180003e84`
- `0x180003fa0`
- `0x18000d2a0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003eca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003eca`

## pseudocode

```c
__int64 __fastcall RadioModule::COMRegisterClassObjects(RadioModule *this)
{
  LPVOID *ppv; // rdi
  HRESULT Instance; // ebx
  __int64 v4; // rcx
  __int64 v5; // rdx
  _QWORD v7[2]; // [rsp+40h] [rbp-28h] BYREF

  ppv = (LPVOID *)((char *)this + 16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, ppv);
  if ( Instance < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return (unsigned int)Instance;
    v5 = 25;
LABEL_5:
    WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids, (unsigned int)Instance);
    return (unsigned int)Instance;
  }
  v7[0] = 0;
  v7[1] = this;
  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *, int, _QWORD))(*(_QWORD *)*ppv + 24LL))(
               *ppv,
               COMRegisterClassFromContext,
               v7,
               &IID_IContextCallback,
               5,
               0);
  if ( Instance < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return (unsigned int)Instance;
    v5 = 26;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180003e84  mov     [rsp+arg_8], rbx
0x180003e89  mov     [rsp+arg_10], rsi
0x180003e8e  push    rdi
0x180003e8f  sub     rsp, 60h
0x180003e93  mov     rax, cs:__security_cookie
0x180003e9a  xor     rax, rsp
0x180003e9d  mov     [rsp+68h+var_18], rax
0x180003ea2  mov     rsi, rcx
0x180003ea5  lea     rdi, [rcx+10h]
0x180003ea9  mov     rcx, rdi
0x180003eac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003eb1  mov     [rsp+68h+ppv], rdi; ppv
0x180003eb6  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180003ebd  xor     edx, edx; pUnkOuter
0x180003ebf  lea     r8d, [rdx+1]; dwClsContext
0x180003ec3  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180003eca  call    cs:__imp_CoCreateInstance
0x180003ed0  mov     ebx, eax
0x180003ed2  test    eax, eax
0x180003ed4  jns     short loc_180003F0B
0x180003ed6  lea     rdx, WPP_GLOBAL_Control
0x180003edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ee4  cmp     rcx, rdx
0x180003ee7  jz      short loc_180003F07
0x180003ee9  test    byte ptr [rcx+1Ch], 1
0x180003eed  jz      short loc_180003F07
0x180003eef  mov     edx, 19h
0x180003ef4  mov     r9d, ebx
0x180003ef7  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180003efe  mov     rcx, [rcx+10h]
0x180003f02  call    WPP_SF_d
0x180003f07  mov     eax, ebx
0x180003f09  jmp     short loc_180003F74
0x180003f0b  mov     [rsp+68h+var_28], 0
0x180003f14  mov     [rsp+68h+var_20], rsi
0x180003f19  mov     rcx, [rdi]
0x180003f1c  mov     rax, [rcx]
0x180003f1f  mov     [rsp+68h+var_40], 0
0x180003f28  mov     dword ptr [rsp+68h+ppv], 5
0x180003f30  lea     r9, IID_IContextCallback
0x180003f37  lea     r8, [rsp+68h+var_28]
0x180003f3c  lea     rdx, ?COMRegisterClassFromContext@@YAJPEAUtagComCallData@@@Z; COMRegisterClassFromContext(tagComCallData *)
0x180003f43  mov     rax, [rax+18h]
0x180003f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f4c  mov     ebx, eax
0x180003f4e  test    eax, eax
0x180003f50  jns     short loc_180003F72
0x180003f52  lea     rdx, WPP_GLOBAL_Control
0x180003f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f60  cmp     rcx, rdx
0x180003f63  jz      short loc_180003F07
0x180003f65  test    byte ptr [rcx+1Ch], 1
0x180003f69  jz      short loc_180003F07
0x180003f6b  mov     edx, 1Ah
0x180003f70  jmp     short loc_180003EF4
0x180003f72  xor     eax, eax
0x180003f74  mov     rcx, [rsp+68h+var_18]
0x180003f79  xor     rcx, rsp; StackCookie
0x180003f7c  call    __security_check_cookie
0x180003f81  lea     r11, [rsp+68h+var_8]
0x180003f86  mov     rbx, [r11+18h]
0x180003f8a  mov     rsi, [r11+20h]
0x180003f8e  mov     rsp, r11
0x180003f91  pop     rdi
0x180003f92  retn
```

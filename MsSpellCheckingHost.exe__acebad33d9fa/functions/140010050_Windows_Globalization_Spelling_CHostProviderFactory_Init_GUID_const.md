# Windows::Globalization::Spelling::CHostProviderFactory::Init(_GUID const &)

- ea: `0x140010050`
- end: `0x1400100f8`
- name: `?Init@CHostProviderFactory@Spelling@Globalization@Windows@@UEAAJAEBU_GUID@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(LPVOID *this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000f9b0`
- `0x140010050`
- `0x140011e10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010085`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010085`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostProviderFactory::Init(LPVOID *this, const struct _GUID *a2)
{
  HRESULT Instance; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // ebx
  HRESULT v8; // [rsp+30h] [rbp-48h] BYREF
  char v9[16]; // [rsp+38h] [rbp-40h] BYREF
  const struct _GUID *v10; // [rsp+48h] [rbp-30h]
  __int64 v11; // [rsp+50h] [rbp-28h]
  HRESULT *v12; // [rsp+58h] [rbp-20h]
  __int64 v13; // [rsp+60h] [rbp-18h]

  Instance = CoCreateInstance(a2, 0, 1u, &GUID_9f671e11_77d6_4c92_aefb_615215e3a4be, this + 4);
  v6 = Instance;
  if ( Instance < 0 && (Microsoft_Windows_Spellchecking_HostEnableBits & 1) != 0 )
  {
    v8 = Instance;
    v10 = a2;
    v12 = &v8;
    v11 = 16;
    v13 = 4;
    McGenEventWrite_EventWriteTransfer(v4, ThirdPartyProviderInstantiationFailed, v5, 3, v9);
  }
  return v6;
}

```

## disassembly

```asm
0x140010050  mov     [rsp+arg_10], rbx
0x140010055  push    rdi
0x140010056  sub     rsp, 70h
0x14001005a  mov     rax, cs:__security_cookie
0x140010061  xor     rax, rsp
0x140010064  mov     [rsp+78h+var_10], rax
0x140010069  mov     rdi, rdx
0x14001006c  lea     rax, [rcx+20h]
0x140010070  xor     edx, edx; pUnkOuter
0x140010072  mov     [rsp+78h+ppv], rax; ppv
0x140010077  lea     r9, _GUID_9f671e11_77d6_4c92_aefb_615215e3a4be; riid
0x14001007e  mov     rcx, rdi; rclsid
0x140010081  lea     r8d, [rdx+1]; dwClsContext
0x140010085  call    cs:__imp_CoCreateInstance
0x14001008b  mov     ebx, eax
0x14001008d  test    eax, eax
0x14001008f  jns     short loc_1400100DB
0x140010091  test    cs:Microsoft_Windows_Spellchecking_HostEnableBits, 1
0x140010098  jz      short loc_1400100DB
0x14001009a  mov     [rsp+78h+var_48], eax
0x14001009e  lea     rdx, ThirdPartyProviderInstantiationFailed
0x1400100a5  lea     rax, [rsp+78h+var_48]
0x1400100aa  mov     [rsp+78h+var_30], rdi
0x1400100af  mov     [rsp+78h+var_20], rax
0x1400100b4  mov     r9d, 3
0x1400100ba  lea     rax, [rsp+78h+var_40]
0x1400100bf  mov     [rsp+78h+var_28], 10h
0x1400100c8  mov     [rsp+78h+ppv], rax
0x1400100cd  mov     [rsp+78h+var_18], 4
0x1400100d6  call    McGenEventWrite_EventWriteTransfer
0x1400100db  mov     eax, ebx
0x1400100dd  mov     rcx, [rsp+78h+var_10]
0x1400100e2  xor     rcx, rsp; StackCookie
0x1400100e5  call    __security_check_cookie
0x1400100ea  mov     rbx, [rsp+78h+arg_10]
0x1400100f2  add     rsp, 70h
0x1400100f6  pop     rdi
0x1400100f7  retn
```

# SensorsCustomCapabilityHandler::GetConsentIdFromObjectId(ushort const *,ushort const *,ushort * *)

- ea: `0x180011760`
- end: `0x180011884`
- name: `?GetConsentIdFromObjectId@SensorsCustomCapabilityHandler@@UEAAJPEBG0PEAPEAG@Z`
- size: `292`
- prototype: `__int64 __fastcall(SensorsCustomCapabilityHandler *this, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011aa0`

## callees

- `0x180003e68`
- `0x180004c70`
- `0x1800090f4`
- `0x180011760`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011804`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011804`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180011827`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18001185e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180011827`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18001185e`

## pseudocode

```c
__int64 __fastcall SensorsCustomCapabilityHandler::GetConsentIdFromObjectId(
        SensorsCustomCapabilityHandler *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int DevPropertiesFromInterfacePath; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-50h]
  __int64 v8; // [rsp+38h] [rbp-38h] BYREF
  DEVPROPKEY v9; // [rsp+40h] [rbp-30h]
  int v10; // [rsp+54h] [rbp-1Ch]
  __int64 v11; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v9 = DEVPKEY_DeviceInterface_ClassGuid;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  DevPropertiesFromInterfacePath = DeviceHelperGetDevPropertiesFromInterfacePath(a3, (__int64)&v8, 0);
  if ( DevPropertiesFromInterfacePath >= 0 )
  {
    DevPropertiesFromInterfacePath = -2147467259;
    v5 = 38;
  }
  else
  {
    v5 = 31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\devices\\cam\\handler\\sensorscustom\\sensorscustomcapabilityhandler.cpp",
    (const char *)(unsigned int)DevPropertiesFromInterfacePath,
    v7);
  return (unsigned int)DevPropertiesFromInterfacePath;
}

```

## disassembly

```asm
0x180011760  mov     r11, rsp
0x180011763  mov     [r11+8], rbx
0x180011767  mov     [r11+10h], rdi
0x18001176b  push    rbp
0x18001176c  mov     rbp, rsp
0x18001176f  sub     rsp, 70h
0x180011773  mov     rax, cs:__security_cookie
0x18001177a  xor     rax, rsp
0x18001177d  mov     [rbp+var_10], rax
0x180011781  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180011787  mov     rdi, r9
0x18001178a  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180011791  mov     [rbp+var_20], eax
0x180011794  lea     r9, [rbp+var_40]
0x180011798  lea     rax, [rbp+var_38]
0x18001179c  mov     qword ptr [r11-50h], 0
0x1800117a4  mov     rcx, r8; unsigned __int16 *
0x1800117a7  mov     [r11-58h], rax
0x1800117ab  lea     r8, [rbp+var_30]
0x1800117af  mov     [rbp+var_40], 0
0x1800117b6  movups  [rbp+var_30], xmm0
0x1800117ba  mov     [rbp+var_38], 0
0x1800117c2  mov     [rbp+var_1C], 0
0x1800117c9  mov     [rbp+var_18], 0
0x1800117d1  call    DeviceHelperGetDevPropertiesFromInterfacePath
0x1800117d6  mov     ebx, eax
0x1800117d8  test    eax, eax
0x1800117da  jns     short loc_1800117E3
0x1800117dc  mov     edx, 1Fh
0x1800117e1  jmp     short loc_18001183B
0x1800117e3  cmp     [rbp+var_40], 1
0x1800117e7  jnz     short loc_180011831
0x1800117e9  mov     rax, [rbp+var_38]
0x1800117ed  test    rax, rax
0x1800117f0  jz      short loc_180011831
0x1800117f2  cmp     dword ptr [rax+20h], 0Dh
0x1800117f6  jnz     short loc_180011831
0x1800117f8  mov     rcx, [rax+28h]; rclsid
0x1800117fc  test    rcx, rcx
0x1800117ff  jz      short loc_180011831
0x180011801  mov     rdx, rdi; lplpsz
0x180011804  call    cs:__imp_StringFromCLSID
0x18001180a  mov     ebx, eax
0x18001180c  test    eax, eax
0x18001180e  jns     short loc_180011817
0x180011810  mov     edx, 29h ; ')'
0x180011815  jmp     short loc_18001183B
0x180011817  mov     ecx, [rbp+var_40]
0x18001181a  test    ecx, ecx
0x18001181c  jz      short loc_18001182D
0x18001181e  mov     rdx, [rbp+var_38]
0x180011822  test    rdx, rdx
0x180011825  jz      short loc_18001182D
0x180011827  call    cs:__imp_DevFreeObjectProperties
0x18001182d  xor     eax, eax
0x18001182f  jmp     short loc_180011866
0x180011831  mov     ebx, 80004005h
0x180011836  mov     edx, 26h ; '&'; void *
0x18001183b  mov     rcx, [rbp+8]; this
0x18001183f  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\handler\\s"...
0x180011846  mov     r9d, ebx; char *
0x180011849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001184e  mov     ecx, [rbp+var_40]
0x180011851  test    ecx, ecx
0x180011853  jz      short loc_180011864
0x180011855  mov     rdx, [rbp+var_38]
0x180011859  test    rdx, rdx
0x18001185c  jz      short loc_180011864
0x18001185e  call    cs:__imp_DevFreeObjectProperties
0x180011864  mov     eax, ebx
0x180011866  mov     rcx, [rbp+var_10]
0x18001186a  xor     rcx, rsp; StackCookie
0x18001186d  call    __security_check_cookie
0x180011872  lea     r11, [rsp+70h+var_s0]
0x180011877  mov     rbx, [r11+10h]
0x18001187b  mov     rdi, [r11+18h]
0x18001187f  mov     rsp, r11
0x180011882  pop     rbp
0x180011883  retn
```

# SensorsCustomCapabilityHandler::AccessChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800116c0`
- end: `0x180011753`
- name: `?AccessChanged@SensorsCustomCapabilityHandler@@UEAAJPEBG0000K@Z`
- size: `147`
- prototype: `__int64 __fastcall(SensorsCustomCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCOLESTR lpsz)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004c70`
- `0x1800090f4`
- `0x1800116c0`
- `0x180012bbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800116fb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800116fb`

## pseudocode

```c
__int64 __fastcall SensorsCustomCapabilityHandler::AccessChanged(
        SensorsCustomCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCOLESTR lpsz)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  GUID pclsid; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( lpsz )
  {
    pclsid = 0;
    v7 = CLSIDFromString(lpsz, &pclsid);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecore\\base\\devices\\cam\\handler\\sensorscustom\\sensorscustomcapabilityhandler.cpp",
        (const char *)(unsigned int)v7,
        pclsid.Data1);
      return v8;
    }
    DeviceHelperAccessCheckRevokeInterfaceHandles((__int64)&pclsid, a3, a4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800116c0  mov     [rsp+arg_0], rbx
0x1800116c5  mov     [rsp+arg_8], rsi
0x1800116ca  push    rdi
0x1800116cb  sub     rsp, 40h
0x1800116cf  mov     rax, cs:__security_cookie
0x1800116d6  xor     rax, rsp
0x1800116d9  mov     [rsp+48h+var_18], rax
0x1800116de  mov     rcx, [rsp+48h+lpsz]; lpsz
0x1800116e3  mov     rsi, r9
0x1800116e6  mov     rdi, r8
0x1800116e9  test    rcx, rcx
0x1800116ec  jz      short loc_180011734
0x1800116ee  xorps   xmm0, xmm0
0x1800116f1  lea     rdx, [rsp+48h+pclsid]; pclsid
0x1800116f6  movups  xmmword ptr [rsp+48h+pclsid.Data1], xmm0; int
0x1800116fb  call    cs:__imp_CLSIDFromString
0x180011701  mov     ebx, eax
0x180011703  test    eax, eax
0x180011705  jns     short loc_180011724
0x180011707  mov     rcx, [rsp+48h]; this
0x18001170c  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\handler\\s"...
0x180011713  mov     r9d, eax; char *
0x180011716  mov     edx, 83h; void *
0x18001171b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011720  mov     eax, ebx
0x180011722  jmp     short loc_180011736
0x180011724  mov     r8, rsi
0x180011727  lea     rcx, [rsp+48h+pclsid]
0x18001172c  mov     rdx, rdi
0x18001172f  call    DeviceHelperAccessCheckRevokeInterfaceHandles
0x180011734  xor     eax, eax
0x180011736  mov     rcx, [rsp+48h+var_18]
0x18001173b  xor     rcx, rsp; StackCookie
0x18001173e  call    __security_check_cookie
0x180011743  mov     rbx, [rsp+48h+arg_0]
0x180011748  mov     rsi, [rsp+48h+arg_8]
0x18001174d  add     rsp, 40h
0x180011751  pop     rdi
0x180011752  retn
```

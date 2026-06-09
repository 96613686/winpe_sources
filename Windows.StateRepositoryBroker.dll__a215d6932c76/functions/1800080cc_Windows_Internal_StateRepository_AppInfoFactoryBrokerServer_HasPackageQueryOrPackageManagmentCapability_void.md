# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::HasPackageQueryOrPackageManagmentCapability(void)

- ea: `0x1800080cc`
- end: `0x18000815a`
- name: `?HasPackageQueryOrPackageManagmentCapability@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@AEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007bc0`

## callees

- `0x180006224`
- `0x180007ac8`
- `0x1800080cc`

## string_xrefs

- `0x1800080ff`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.appinfofactorybroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::HasPackageQueryOrPackageManagmentCapability(
        Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  int v5; // ebx
  bool *v6; // r9
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int16 v11; // [rsp+38h] [rbp+10h] BYREF

  LOBYTE(v11) = 0;
  v5 = wil::CheckCapabilityForClientOfObject_nothrow(this, (struct IUnknown *)&stru_18000F7F8, &v11, a4);
  if ( v5 < 0 )
  {
    v7 = 68;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appin"
                    "fofactorybroker.cpp",
      (const char *)(unsigned int)v5,
      v9);
    return (unsigned int)v5;
  }
  if ( !(_BYTE)v11 )
  {
    v5 = wil::CheckCapabilityForClientOfObject_nothrow(this, (struct IUnknown *)&stru_18000F818, &v11, v6);
    if ( v5 < 0 )
    {
      v7 = 71;
      goto LABEL_3;
    }
    if ( !(_BYTE)v11 )
    {
      v5 = -2147024891;
      v7 = 73;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800080cc  mov     [rsp+arg_0], rbx
0x1800080d1  push    rdi; int
0x1800080d2  sub     rsp, 20h
0x1800080d6  lea     r8, [rsp+28h+arg_8]; unsigned __int16 *
0x1800080db  mov     byte ptr [rsp+28h+arg_8], 0
0x1800080e0  lea     rdx, stru_18000F7F8; struct IUnknown *
0x1800080e7  mov     rdi, rcx
0x1800080ea  call    ?CheckCapabilityForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@PEBGPEA_N@Z; wil::CheckCapabilityForClientOfObject_nothrow(IUnknown *,ushort const *,bool *)
0x1800080ef  mov     ebx, eax
0x1800080f1  test    eax, eax
0x1800080f3  jns     short loc_180008112
0x1800080f5  mov     edx, 44h ; 'D'; void *
0x1800080fa  mov     rcx, [rsp+28h]; this
0x1800080ff  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180008106  mov     r9d, ebx; char *
0x180008109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000810e  mov     eax, ebx
0x180008110  jmp     short loc_18000814F
0x180008112  cmp     byte ptr [rsp+28h+arg_8], 0
0x180008117  jnz     short loc_18000814D
0x180008119  lea     r8, [rsp+28h+arg_8]; unsigned __int16 *
0x18000811e  mov     rcx, rdi; this
0x180008121  lea     rdx, stru_18000F818; struct IUnknown *
0x180008128  call    ?CheckCapabilityForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@PEBGPEA_N@Z; wil::CheckCapabilityForClientOfObject_nothrow(IUnknown *,ushort const *,bool *)
0x18000812d  mov     ebx, eax
0x18000812f  test    eax, eax
0x180008131  jns     short loc_18000813A
0x180008133  mov     edx, 47h ; 'G'
0x180008138  jmp     short loc_1800080FA
0x18000813a  cmp     byte ptr [rsp+28h+arg_8], 0
0x18000813f  jnz     short loc_18000814D
0x180008141  mov     ebx, 80070005h
0x180008146  mov     edx, 49h ; 'I'
0x18000814b  jmp     short loc_1800080FA
0x18000814d  xor     eax, eax
0x18000814f  mov     rbx, [rsp+28h+arg_0]
0x180008154  add     rsp, 20h
0x180008158  pop     rdi
0x180008159  retn
```

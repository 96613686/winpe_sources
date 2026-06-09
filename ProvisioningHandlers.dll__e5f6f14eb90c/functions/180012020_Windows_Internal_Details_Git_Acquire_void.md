# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x180012020`
- end: `0x1800120b7`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800101fc`
- `0x180019440`
- `0x180019538`

## callees

- `0x1800067fc`
- `0x180012020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012070`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012070`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_18003F030 )
  {
    v1 = 0;
    _InterlockedIncrement(&Windows::Internal::Details::_git);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&ppv);
    v1 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v1 >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&qword_18003F030, (signed __int64)ppv, 0) )
        ppv = 0;
      _InterlockedIncrement(&Windows::Internal::Details::_git);
    }
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&ppv);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180012020  mov     [rsp+arg_0], rcx
0x180012025  push    rbx
0x180012026  sub     rsp, 30h
0x18001202a  cmp     cs:qword_18003F030, 0
0x180012032  jz      short loc_18001203F
0x180012034  xor     ebx, ebx
0x180012036  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x18001203d  jmp     short loc_1800120AE
0x18001203f  lea     rcx, [rsp+38h+arg_0]
0x180012044  mov     [rsp+38h+arg_0], 0
0x18001204d  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180012052  xor     edx, edx; pUnkOuter
0x180012054  lea     rax, [rsp+38h+arg_0]
0x180012059  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180012060  mov     [rsp+38h+ppv], rax; ppv
0x180012065  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001206c  lea     r8d, [rdx+1]; dwClsContext
0x180012070  call    cs:__imp_CoCreateInstance
0x180012077  nop     dword ptr [rax+rax+00h]
0x18001207c  mov     ebx, eax
0x18001207e  test    eax, eax
0x180012080  js      short loc_1800120A4
0x180012082  mov     rcx, [rsp+38h+arg_0]
0x180012087  xor     eax, eax
0x180012089  lock cmpxchg cs:qword_18003F030, rcx
0x180012092  jnz     short loc_18001209D
0x180012094  mov     [rsp+38h+arg_0], 0
0x18001209d  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x1800120a4  lea     rcx, [rsp+38h+arg_0]
0x1800120a9  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800120ae  mov     eax, ebx
0x1800120b0  add     rsp, 30h
0x1800120b4  pop     rbx
0x1800120b5  retn
```

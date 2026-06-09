# InitLocked

- ea: `0x180025194`
- end: `0x18002524b`
- name: `InitLocked`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180025254`

## callees

- `0x18000c164`
- `0x180024d90`
- `0x180025194`
- `0x180025390`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800251d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800251d9`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180025206`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180025206`

## pseudocode

```c
__int64 InitLocked()
{
  HRESULT AgileReference; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v6; // [rsp+40h] [rbp+8h] BYREF

  if ( !pUnk )
  {
    v6 = 0;
    Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(&v6);
    AgileReference = CoCreateInstance(
                       &CLSID_IsolatedAppLauncher,
                       0,
                       4u,
                       &GUID_f686878f_7b42_4cc4_96fb_f4f3b6e3d24d,
                       &v6);
    v1 = AgileReference;
    if ( AgileReference < 0 )
    {
      v2 = 107;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v2,
        (unsigned int)"onecoreuap\\inetcore\\lib\\hvsi\\hvsiutilities\\hvsimgrlib.cpp",
        (const char *)(unsigned int)AgileReference,
        ppv);
      Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(&v6);
      return v1;
    }
    wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset();
    AgileReference = RoGetAgileReference(0, &GUID_f686878f_7b42_4cc4_96fb_f4f3b6e3d24d, v6, &pUnk);
    v1 = AgileReference;
    if ( AgileReference < 0 )
    {
      v2 = 108;
      goto LABEL_6;
    }
    Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(&v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180025194  push    rbx
0x180025196  sub     rsp, 30h
0x18002519a  cmp     cs:pUnk, 0
0x1800251a2  jnz     loc_180025243
0x1800251a8  lea     rcx, [rsp+38h+arg_0]
0x1800251ad  mov     [rsp+38h+arg_0], 0
0x1800251b6  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics2@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(void)
0x1800251bb  xor     edx, edx; pUnkOuter
0x1800251bd  lea     rax, [rsp+38h+arg_0]
0x1800251c2  lea     r9, _GUID_f686878f_7b42_4cc4_96fb_f4f3b6e3d24d; riid
0x1800251c9  mov     qword ptr [rsp+38h+ppv], rax; int
0x1800251ce  lea     rcx, CLSID_IsolatedAppLauncher; rclsid
0x1800251d5  lea     r8d, [rdx+4]; dwClsContext
0x1800251d9  call    cs:__imp_CoCreateInstance
0x1800251df  mov     ebx, eax
0x1800251e1  test    eax, eax
0x1800251e3  jns     short loc_1800251EC
0x1800251e5  mov     edx, 6Bh ; 'k'
0x1800251ea  jmp     short loc_180025217
0x1800251ec  call    ?reset@?$com_ptr_t@UIAgileReference@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset(void)
0x1800251f1  mov     r8, [rsp+38h+arg_0]
0x1800251f6  lea     r9, pUnk
0x1800251fd  lea     rdx, _GUID_f686878f_7b42_4cc4_96fb_f4f3b6e3d24d
0x180025204  xor     ecx, ecx
0x180025206  call    cs:__imp_RoGetAgileReference
0x18002520c  mov     ebx, eax
0x18002520e  test    eax, eax
0x180025210  jns     short loc_180025239
0x180025212  mov     edx, 6Ch ; 'l'; void *
0x180025217  mov     rcx, [rsp+38h]; this
0x18002521c  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\lib\\hvsi\\hvsiut"...
0x180025223  mov     r9d, eax; char *
0x180025226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002522b  lea     rcx, [rsp+38h+arg_0]
0x180025230  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics2@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(void)
0x180025235  mov     eax, ebx
0x180025237  jmp     short loc_180025245
0x180025239  lea     rcx, [rsp+38h+arg_0]
0x18002523e  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics2@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(void)
0x180025243  xor     eax, eax
0x180025245  add     rsp, 30h
0x180025249  pop     rbx
0x18002524a  retn
```

# StorageWriter::SetFeatureStates(_RTL_FEATURE_CONFIGURATION_UPDATE *,unsigned __int64,ushort const *)

- ea: `0x180119dc8`
- end: `0x18011a028`
- name: `?SetFeatureStates@StorageWriter@@SAJPEAU_RTL_FEATURE_CONFIGURATION_UPDATE@@_KPEBG@Z`
- size: `608`
- prototype: `__int64 __fastcall(struct _RTL_FEATURE_CONFIGURATION_UPDATE *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1801158d0`

## callees

- `0x18000da88`
- `0x180118d90`
- `0x180119dc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119fa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011a018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119fa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011a018`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119e51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119e9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119ee8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119f33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119f7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119e51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119e9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119ee8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119f33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119f7e`

## string_xrefs

- `0x180119ffb`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageWriter::SetFeatureStates(
        struct _RTL_FEATURE_CONFIGURATION_UPDATE *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rdi
  int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  __int64 v15; // rdx
  int lpData; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  int Data; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+58h] BYREF

  v6 = 0;
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    hKey = 0;
    v7 = 32 * v6;
    v8 = StorageWriter::CreateFeatureKey(*((_DWORD *)a1 + 8 * v6 + 1), *((_DWORD *)a1 + 8 * v6), &hKey, a3);
    if ( v8 < 0 )
      break;
    Data = *(_DWORD *)((char *)a1 + v7 + 8);
    v9 = RegSetValueExW(hKey, L"EnabledState", 0, 4u, (const BYTE *)&Data, 4u);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 < 0 )
    {
      v15 = 475;
      goto LABEL_28;
    }
    Data = *(_DWORD *)((char *)a1 + v7 + 12);
    v10 = RegSetValueExW(hKey, L"EnabledStateOptions", 0, 4u, (const BYTE *)&Data, 4u);
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    if ( v8 < 0 )
    {
      v15 = 476;
      goto LABEL_28;
    }
    Data = *((unsigned __int8 *)a1 + v7 + 16);
    v11 = RegSetValueExW(hKey, L"Variant", 0, 4u, (const BYTE *)&Data, 4u);
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( v8 < 0 )
    {
      v15 = 477;
      goto LABEL_28;
    }
    Data = *(_DWORD *)((char *)a1 + v7 + 20);
    v12 = RegSetValueExW(hKey, L"VariantPayloadKind", 0, 4u, (const BYTE *)&Data, 4u);
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
    {
      v15 = 478;
      goto LABEL_28;
    }
    Data = *(_DWORD *)((char *)a1 + v7 + 24);
    v13 = RegSetValueExW(hKey, L"VariantPayload", 0, 4u, (const BYTE *)&Data, 4u);
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 < 0 )
    {
      v15 = 479;
      goto LABEL_28;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( ++v6 >= a2 )
      return 0;
  }
  v15 = 473;
LABEL_28:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
    (const char *)(unsigned int)v8,
    lpData);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180119dc8  mov     [rsp-38h+arg_0], rbx
0x180119dcd  push    rbp
0x180119dce  push    rsi
0x180119dcf  push    rdi
0x180119dd0  push    r12
0x180119dd2  push    r13
0x180119dd4  push    r14
0x180119dd6  push    r15
0x180119dd8  mov     rbp, rsp
0x180119ddb  sub     rsp, 30h
0x180119ddf  mov     r12, r8
0x180119de2  mov     r15, rdx
0x180119de5  mov     r14, rcx
0x180119de8  xor     esi, esi
0x180119dea  test    rdx, rdx
0x180119ded  jz      loc_180119FBB
0x180119df3  mov     r13d, 80070000h
0x180119df9  mov     [rbp+hKey], 0
0x180119e01  mov     rdi, rsi
0x180119e04  shl     rdi, 5
0x180119e08  mov     r9, r12
0x180119e0b  lea     r8, [rbp+hKey]
0x180119e0f  mov     edx, [rdi+r14]
0x180119e13  mov     ecx, [rdi+r14+4]
0x180119e18  call    ?CreateFeatureKey@StorageWriter@@CAJW4_RTL_FEATURE_CONFIGURATION_PRIORITY@@IAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageWriter::CreateFeatureKey(_RTL_FEATURE_CONFIGURATION_PRIORITY,uint,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)
0x180119e1d  mov     ebx, eax
0x180119e1f  test    eax, eax
0x180119e21  js      loc_180119FF6
0x180119e27  mov     eax, [rdi+r14+8]
0x180119e2c  mov     [rbp+Data], eax
0x180119e2f  mov     r9d, 4; dwType
0x180119e35  mov     [rsp+30h+cbData], r9d; cbData
0x180119e3a  lea     rax, [rbp+Data]
0x180119e3e  mov     [rsp+30h+lpData], rax; lpData
0x180119e43  xor     r8d, r8d; Reserved
0x180119e46  lea     rdx, ValueName; "EnabledState"
0x180119e4d  mov     rcx, [rbp+hKey]; hKey
0x180119e51  call    cs:__imp_RegSetValueExW
0x180119e58  nop     dword ptr [rax+rax+00h]
0x180119e5d  mov     ebx, eax
0x180119e5f  test    eax, eax
0x180119e61  jle     short loc_180119E69
0x180119e63  movzx   ebx, ax
0x180119e66  or      ebx, r13d
0x180119e69  test    ebx, ebx
0x180119e6b  js      loc_180119FEF
0x180119e71  mov     eax, [rdi+r14+0Ch]
0x180119e76  mov     [rbp+Data], eax
0x180119e79  mov     ecx, 4
0x180119e7e  mov     [rsp+30h+cbData], ecx; cbData
0x180119e82  lea     rax, [rbp+Data]
0x180119e86  mov     [rsp+30h+lpData], rax; lpData
0x180119e8b  mov     r9d, ecx; dwType
0x180119e8e  xor     r8d, r8d; Reserved
0x180119e91  lea     rdx, aEnabledstateop; "EnabledStateOptions"
0x180119e98  mov     rcx, [rbp+hKey]; hKey
0x180119e9c  call    cs:__imp_RegSetValueExW
0x180119ea3  nop     dword ptr [rax+rax+00h]
0x180119ea8  mov     ebx, eax
0x180119eaa  test    eax, eax
0x180119eac  jle     short loc_180119EB4
0x180119eae  movzx   ebx, ax
0x180119eb1  or      ebx, r13d
0x180119eb4  test    ebx, ebx
0x180119eb6  js      loc_180119FE8
0x180119ebc  movzx   eax, byte ptr [rdi+r14+10h]
0x180119ec2  mov     [rbp+Data], eax
0x180119ec5  mov     ecx, 4
0x180119eca  mov     [rsp+30h+cbData], ecx; cbData
0x180119ece  lea     rax, [rbp+Data]
0x180119ed2  mov     [rsp+30h+lpData], rax; lpData
0x180119ed7  mov     r9d, ecx; dwType
0x180119eda  xor     r8d, r8d; Reserved
0x180119edd  lea     rdx, aVariant; "Variant"
0x180119ee4  mov     rcx, [rbp+hKey]; hKey
0x180119ee8  call    cs:__imp_RegSetValueExW
0x180119eef  nop     dword ptr [rax+rax+00h]
0x180119ef4  mov     ebx, eax
0x180119ef6  test    eax, eax
0x180119ef8  jle     short loc_180119F00
0x180119efa  movzx   ebx, ax
0x180119efd  or      ebx, r13d
0x180119f00  test    ebx, ebx
0x180119f02  js      loc_180119FE1
0x180119f08  mov     eax, [rdi+r14+14h]
0x180119f0d  mov     [rbp+Data], eax
0x180119f10  mov     ecx, 4
0x180119f15  mov     [rsp+30h+cbData], ecx; cbData
0x180119f19  lea     rax, [rbp+Data]
0x180119f1d  mov     [rsp+30h+lpData], rax; lpData
0x180119f22  mov     r9d, ecx; dwType
0x180119f25  xor     r8d, r8d; Reserved
0x180119f28  lea     rdx, aVariantpayload_0; "VariantPayloadKind"
0x180119f2f  mov     rcx, [rbp+hKey]; hKey
0x180119f33  call    cs:__imp_RegSetValueExW
0x180119f3a  nop     dword ptr [rax+rax+00h]
0x180119f3f  mov     ebx, eax
0x180119f41  test    eax, eax
0x180119f43  jle     short loc_180119F4B
0x180119f45  movzx   ebx, ax
0x180119f48  or      ebx, r13d
0x180119f4b  test    ebx, ebx
0x180119f4d  js      loc_180119FDA
0x180119f53  mov     eax, [rdi+r14+18h]
0x180119f58  mov     [rbp+Data], eax
0x180119f5b  mov     ecx, 4
0x180119f60  mov     [rsp+30h+cbData], ecx; cbData
0x180119f64  lea     rax, [rbp+Data]
0x180119f68  mov     [rsp+30h+lpData], rax; lpData
0x180119f6d  mov     r9d, ecx; dwType
0x180119f70  xor     r8d, r8d; Reserved
0x180119f73  lea     rdx, aVariantpayload; "VariantPayload"
0x180119f7a  mov     rcx, [rbp+hKey]; hKey
0x180119f7e  call    cs:__imp_RegSetValueExW
0x180119f85  nop     dword ptr [rax+rax+00h]
0x180119f8a  mov     ebx, eax
0x180119f8c  test    eax, eax
0x180119f8e  jle     short loc_180119F96
0x180119f90  movzx   ebx, ax
0x180119f93  or      ebx, r13d
0x180119f96  test    ebx, ebx
0x180119f98  js      short loc_180119FD3
0x180119f9a  mov     rcx, [rbp+hKey]; hKey
0x180119f9e  test    rcx, rcx
0x180119fa1  jz      short loc_180119FAF
0x180119fa3  call    cs:__imp_RegCloseKey
0x180119faa  nop     dword ptr [rax+rax+00h]
0x180119faf  inc     rsi
0x180119fb2  cmp     rsi, r15
0x180119fb5  jb      loc_180119DF9
0x180119fbb  xor     eax, eax
0x180119fbd  mov     rbx, [rsp+30h+arg_0]
0x180119fc2  add     rsp, 30h
0x180119fc6  pop     r15
0x180119fc8  pop     r14
0x180119fca  pop     r13
0x180119fcc  pop     r12
0x180119fce  pop     rdi
0x180119fcf  pop     rsi
0x180119fd0  pop     rbp
0x180119fd1  retn
0x180119fd3  mov     edx, 1DFh
0x180119fd8  jmp     short loc_180119FFB
0x180119fda  mov     edx, 1DEh
0x180119fdf  jmp     short loc_180119FFB
0x180119fe1  mov     edx, 1DDh
0x180119fe6  jmp     short loc_180119FFB
0x180119fe8  mov     edx, 1DCh
0x180119fed  jmp     short loc_180119FFB
0x180119fef  mov     edx, 1DBh
0x180119ff4  jmp     short loc_180119FFB
0x180119ff6  mov     edx, 1D9h; void *
0x180119ffb  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x18011a002  mov     r9d, ebx; char *
0x18011a005  mov     rcx, [rbp+38h]; this
0x18011a009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a00e  nop
0x18011a00f  mov     rcx, [rbp+hKey]; hKey
0x18011a013  test    rcx, rcx
0x18011a016  jz      short loc_18011A024
0x18011a018  call    cs:__imp_RegCloseKey
0x18011a01f  nop     dword ptr [rax+rax+00h]
0x18011a024  mov     eax, ebx
0x18011a026  jmp     short loc_180119FBD
```

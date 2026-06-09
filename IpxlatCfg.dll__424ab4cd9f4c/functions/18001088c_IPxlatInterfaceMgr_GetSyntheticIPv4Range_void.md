# IPxlatInterfaceMgr::GetSyntheticIPv4Range(void)

- ea: `0x18001088c`
- end: `0x180010bed`
- name: `?GetSyntheticIPv4Range@IPxlatInterfaceMgr@@AEAAXXZ`
- size: `865`
- prototype: `void __fastcall(IPxlatInterfaceMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ea3c`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x180002a34`
- `0x18000c224`
- `0x18000e5a4`
- `0x18000f184`
- `0x18001088c`
- `0x180011efc`
- `0x180012290`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010976`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010976`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010937`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a15`
- `IPHLPAPI!ParseNetworkString` at `0x1800109a2`
- `IPHLPAPI!ParseNetworkString` at `0x180010a5c`
- `IPHLPAPI!ParseNetworkString` at `0x1800109a2`
- `IPHLPAPI!ParseNetworkString` at `0x180010a5c`

## string_xrefs

- `0x18001091d`: `System\CurrentControlSet\Services\IpxlatCfgSvc`
- `0x1800109c4`: `Prefix length of address pool in registry not valid`
- `0x180010a2c`: `Using synthetic IPv4 address pool from registry`
- `0x18001090b`: `System\CurrentControlSet\Services\IPxlatCfgSvc`

## pseudocode

```c
void __fastcall IPxlatInterfaceMgr::GetSyntheticIPv4Range(IPxlatInterfaceMgr *this)
{
  char IsEnabled; // al
  const WCHAR *v3; // rdx
  LSTATUS ValueW; // ebx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  const char *v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  unsigned __int8 v12; // di
  _QWORD *v13; // rdx
  const struct std::error_category *v14; // rax
  int v15; // edx
  _BYTE v16[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v22; // [rsp+78h] [rbp-88h]
  _BYTE pExceptionObject[16]; // [rsp+280h] [rbp+180h] BYREF
  int *v24; // [rsp+290h] [rbp+190h]
  __int64 v25; // [rsp+298h] [rbp+198h]
  int *v26; // [rsp+2A0h] [rbp+1A0h]
  __int64 v27; // [rsp+2A8h] [rbp+1A8h]
  _OWORD pvData[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v29; // [rsp+2D0h] [rbp+1D0h]

  pcbData = 40;
  v16[0] = 0;
  v29 = 0;
  memset(pvData, 0, sizeof(pvData));
  memset_0(v21, 0, 0x210u);
  hkey = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Netsh>::GetImpl'::`2'::impl);
  v3 = L"System\\CurrentControlSet\\Services\\IpxlatCfgSvc";
  if ( !IsEnabled )
    v3 = L"System\\CurrentControlSet\\Services\\IPxlatCfgSvc";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hkey) )
  {
    ValueW = RegGetValueW(hkey, 0, L"SyntheticIPv4Range", 2u, 0, pvData, &pcbData);
    if ( !ValueW )
    {
      ValueW = ParseNetworkString(pvData, 4, v21, 0, v16);
      if ( !ValueW && (unsigned __int8)(v16[0] - 25) > 6u )
      {
        ValueW = 13;
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
        {
          v17 = 13;
          v24 = (int *)"Prefix length of address pool in registry not valid";
          v25 = 52;
          v26 = &v17;
          v27 = 4;
          McGenEventWrite_EventWriteTransfer(v5, IPXLATCFG_ERROR_EVENT, v6, 3, pExceptionObject);
        }
      }
    }
    RegCloseKey(hkey);
    if ( !ValueW )
    {
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) == 0 )
        goto LABEL_16;
      v9 = "Using synthetic IPv4 address pool from registry";
      v25 = 48;
      goto LABEL_15;
    }
  }
  if ( (unsigned int)ParseNetworkString(L"192.0.0.0/29", 4, v21, 0, v16) )
  {
    v14 = std::system_category();
    std::system_error::system_error((std::system_error *)pExceptionObject, v15, v14, "ParseNetworkString failed");
    throw (std::system_error *)pExceptionObject;
  }
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
  {
    v9 = "Using default synthetic IPv4 address pool";
    v25 = 42;
LABEL_15:
    v24 = (int *)v9;
    McGenEventWrite_EventWriteTransfer(v7, IPXLATCFG_INFO_EVENT, v8, 2, pExceptionObject);
  }
LABEL_16:
  v10 = v16[0];
  v11 = v22;
  *((_BYTE *)this + 100) = v16[0];
  *((_DWORD *)this + 24) = v11;
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
  {
    LODWORD(v18) = v10;
    v17 = v11;
    v24 = &v17;
    v25 = 4;
    v26 = (int *)&v18;
    v27 = 4;
    McGenEventWrite_EventWriteTransfer(v11, IPXLATCFG_SYNTHETIC_IPV4_RANGE_EVENT, v8, 3, pExceptionObject);
    LOBYTE(v10) = v16[0];
  }
  v12 = 1;
  if ( (unsigned __int8)(1 << (32 - v10)) > 1u )
  {
    do
    {
      v13 = (_QWORD *)*((_QWORD *)this + 14);
      v17 = *((_DWORD *)this + 24);
      LOWORD(v18) = v17;
      BYTE2(v18) = BYTE2(v17);
      BYTE3(v18) = v12 + HIBYTE(v17);
      BYTE4(v18) = 1;
      if ( v13 == *((_QWORD **)this + 15) )
      {
        std::vector<std::pair<in_addr,bool>>::_Emplace_reallocate<std::pair<in_addr,bool>>(
          (char *)this + 104,
          v13,
          &v18);
      }
      else
      {
        *v13 = v18;
        *((_QWORD *)this + 14) += 8LL;
      }
      ++v12;
    }
    while ( v12 < (unsigned __int8)(1 << (32 - v16[0])) );
  }
}

```

## disassembly

```asm
0x18001088c  mov     [rsp-8+arg_8], rbx
0x180010891  mov     [rsp-8+arg_10], rsi
0x180010896  push    rbp
0x180010897  push    rdi
0x180010898  push    r12
0x18001089a  lea     rbp, [rsp-1E0h]
0x1800108a2  sub     rsp, 2E0h
0x1800108a9  mov     rax, cs:__security_cookie
0x1800108b0  xor     rax, rsp
0x1800108b3  mov     [rbp+1F0h+var_18], rax
0x1800108ba  xorps   xmm0, xmm0
0x1800108bd  mov     [rsp+2F0h+var_298], 28h ; '('
0x1800108c5  mov     rsi, rcx
0x1800108c8  xor     edi, edi
0x1800108ca  xor     eax, eax
0x1800108cc  mov     [rsp+2F0h+var_2B0], dil
0x1800108d1  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800108d6  mov     [rbp+1F0h+var_20], rax
0x1800108dd  xor     edx, edx; Val
0x1800108df  mov     r8d, 210h; Size
0x1800108e5  movups  [rbp+1F0h+var_40], xmm0
0x1800108ec  movups  [rbp+1F0h+var_30], xmm0
0x1800108f3  call    memset_0
0x1800108f8  mov     [rsp+2F0h+hkey], rdi
0x1800108fd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Netsh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Netsh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Netsh>::GetImpl(void)'::`2'::impl
0x180010904  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Netsh@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh>::__private_IsEnabled(void)
0x180010909  test    al, al
0x18001090b  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\IP"...
0x180010912  lea     rax, [rsp+2F0h+hkey]
0x180010917  mov     r9d, 20019h; samDesired
0x18001091d  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ip"...
0x180010924  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180010929  cmovz   rdx, rcx; lpSubKey
0x18001092d  xor     r8d, r8d; ulOptions
0x180010930  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010937  call    cs:__imp_RegOpenKeyExW
0x18001093d  lea     r12d, [rdi+4]
0x180010941  test    eax, eax
0x180010943  jnz     loc_180010A40
0x180010949  mov     rcx, [rsp+2F0h+hkey]; hkey
0x18001094e  lea     rax, [rsp+2F0h+var_298]
0x180010953  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180010958  lea     r9d, [rdi+2]; dwFlags
0x18001095c  lea     rax, [rbp+1F0h+var_40]
0x180010963  xor     edx, edx; lpSubKey
0x180010965  mov     [rsp+2F0h+pvData], rax; pvData
0x18001096a  lea     r8, Value; "SyntheticIPv4Range"
0x180010971  mov     [rsp+2F0h+phkResult], rdi; pdwType
0x180010976  call    cs:__imp_RegGetValueW
0x18001097c  mov     ebx, eax
0x18001097e  test    eax, eax
0x180010980  jnz     loc_180010A10
0x180010986  lea     rax, [rsp+2F0h+var_2B0]
0x18001098b  xor     r9d, r9d
0x18001098e  lea     r8, [rsp+2F0h+var_280]
0x180010993  mov     [rsp+2F0h+phkResult], rax
0x180010998  mov     edx, r12d
0x18001099b  lea     rcx, [rbp+1F0h+var_40]
0x1800109a2  call    cs:__imp_ParseNetworkString
0x1800109a8  mov     ebx, eax
0x1800109aa  test    eax, eax
0x1800109ac  jnz     short loc_180010A10
0x1800109ae  mov     al, [rsp+2F0h+var_2B0]
0x1800109b2  sub     al, 19h
0x1800109b4  cmp     al, 6
0x1800109b6  jbe     short loc_180010A10
0x1800109b8  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x1800109bf  lea     ebx, [rdi+0Dh]
0x1800109c2  jz      short loc_180010A10
0x1800109c4  lea     rax, aPrefixLengthOf; "Prefix length of address pool in regist"...
0x1800109cb  mov     [rsp+2F0h+var_2A8], ebx
0x1800109cf  mov     [rbp+1F0h+var_60], rax
0x1800109d6  lea     r9d, [rdi+3]
0x1800109da  lea     rax, [rsp+2F0h+var_2A8]
0x1800109df  mov     [rbp+1F0h+var_58], 34h ; '4'
0x1800109ea  mov     [rbp+1F0h+var_50], rax
0x1800109f1  lea     rdx, IPXLATCFG_ERROR_EVENT
0x1800109f8  lea     rax, [rbp+1F0h+pExceptionObject]
0x1800109ff  mov     [rbp+1F0h+var_48], r12
0x180010a06  mov     [rsp+2F0h+phkResult], rax
0x180010a0b  call    McGenEventWrite_EventWriteTransfer
0x180010a10  mov     rcx, [rsp+2F0h+hkey]; hKey
0x180010a15  call    cs:__imp_RegCloseKey
0x180010a1b  test    ebx, ebx
0x180010a1d  jnz     short loc_180010A40
0x180010a1f  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180010a26  jz      loc_180010AAC
0x180010a2c  lea     rax, aUsingSynthetic; "Using synthetic IPv4 address pool from "...
0x180010a33  mov     [rbp+1F0h+var_58], 30h ; '0'
0x180010a3e  jmp     short loc_180010A87
0x180010a40  lea     rax, [rsp+2F0h+var_2B0]
0x180010a45  xor     r9d, r9d
0x180010a48  lea     r8, [rsp+2F0h+var_280]
0x180010a4d  mov     [rsp+2F0h+phkResult], rax
0x180010a52  mov     edx, r12d
0x180010a55  lea     rcx, a19200029; "192.0.0.0/29"
0x180010a5c  call    cs:__imp_ParseNetworkString
0x180010a62  mov     edx, eax
0x180010a64  test    eax, eax
0x180010a66  jnz     loc_180010BBE
0x180010a6c  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180010a73  jz      short loc_180010AAC
0x180010a75  lea     rax, aUsingDefaultSy; "Using default synthetic IPv4 address po"...
0x180010a7c  mov     [rbp+1F0h+var_58], 2Ah ; '*'
0x180010a87  mov     [rbp+1F0h+var_60], rax
0x180010a8e  lea     rdx, IPXLATCFG_INFO_EVENT
0x180010a95  lea     rax, [rbp+1F0h+pExceptionObject]
0x180010a9c  mov     r9d, 2
0x180010aa2  mov     [rsp+2F0h+phkResult], rax
0x180010aa7  call    McGenEventWrite_EventWriteTransfer
0x180010aac  movzx   eax, [rsp+2F0h+var_2B0]
0x180010ab1  mov     ecx, [rsp+2F0h+var_278]
0x180010ab5  mov     [rsi+64h], al
0x180010ab8  mov     [rsi+60h], ecx
0x180010abb  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180010ac2  jz      short loc_180010B14
0x180010ac4  mov     dword ptr [rsp+2F0h+var_2A0], eax
0x180010ac8  lea     rdx, IPXLATCFG_SYNTHETIC_IPV4_RANGE_EVENT
0x180010acf  lea     rax, [rsp+2F0h+var_2A8]
0x180010ad4  mov     [rsp+2F0h+var_2A8], ecx
0x180010ad8  mov     [rbp+1F0h+var_60], rax
0x180010adf  mov     r9d, 3
0x180010ae5  lea     rax, [rsp+2F0h+var_2A0]
0x180010aea  mov     [rbp+1F0h+var_58], r12
0x180010af1  mov     [rbp+1F0h+var_50], rax
0x180010af8  lea     rax, [rbp+1F0h+pExceptionObject]
0x180010aff  mov     [rsp+2F0h+phkResult], rax
0x180010b04  mov     [rbp+1F0h+var_48], r12
0x180010b0b  call    McGenEventWrite_EventWriteTransfer
0x180010b10  mov     al, [rsp+2F0h+var_2B0]
0x180010b14  movzx   eax, al
0x180010b17  mov     ecx, 20h ; ' '
0x180010b1c  sub     ecx, eax
0x180010b1e  mov     dil, 1
0x180010b21  mov     eax, 1
0x180010b26  shl     al, cl
0x180010b28  cmp     al, dil
0x180010b2b  jbe     short loc_180010B97
0x180010b2d  mov     ecx, [rsi+60h]
0x180010b30  mov     rdx, [rsi+70h]
0x180010b34  mov     [rsp+2F0h+var_2A8], ecx
0x180010b38  movzx   eax, word ptr [rsp+2F0h+var_2A8]
0x180010b3d  shr     ecx, 18h
0x180010b40  add     cl, dil
0x180010b43  mov     word ptr [rsp+2F0h+var_2A0], ax
0x180010b48  mov     al, byte ptr [rsp+2F0h+var_2A8+2]
0x180010b4c  mov     byte ptr [rsp+2F0h+var_2A0+2], al
0x180010b50  mov     byte ptr [rsp+2F0h+var_2A0+3], cl
0x180010b54  mov     byte ptr [rsp+2F0h+var_2A0+4], 1
0x180010b59  cmp     rdx, [rsi+78h]
0x180010b5d  jz      short loc_180010B6E
0x180010b5f  mov     rax, [rsp+2F0h+var_2A0]
0x180010b64  mov     [rdx], rax
0x180010b67  add     qword ptr [rsi+70h], 8
0x180010b6c  jmp     short loc_180010B7C
0x180010b6e  lea     r8, [rsp+2F0h+var_2A0]
0x180010b73  lea     rcx, [rsi+68h]
0x180010b77  call    ??$_Emplace_reallocate@U?$pair@Uin_addr@@_N@std@@@?$vector@U?$pair@Uin_addr@@_N@std@@V?$allocator@U?$pair@Uin_addr@@_N@std@@@2@@std@@AEAAPEAU?$pair@Uin_addr@@_N@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<in_addr,bool>>::_Emplace_reallocate<std::pair<in_addr,bool>>(std::pair<in_addr,bool> * const,std::pair<in_addr,bool> &&)
0x180010b7c  movzx   eax, [rsp+2F0h+var_2B0]
0x180010b81  mov     ecx, 20h ; ' '
0x180010b86  sub     ecx, eax
0x180010b88  inc     dil
0x180010b8b  mov     eax, 1
0x180010b90  shl     al, cl
0x180010b92  cmp     dil, al
0x180010b95  jb      short loc_180010B2D
0x180010b97  mov     rcx, [rbp+1F0h+var_18]
0x180010b9e  xor     rcx, rsp; StackCookie
0x180010ba1  call    __security_check_cookie
0x180010ba6  lea     r11, [rsp+2F0h+var_10]
0x180010bae  mov     rbx, [r11+28h]
0x180010bb2  mov     rsi, [r11+30h]
0x180010bb6  mov     rsp, r11
0x180010bb9  pop     r12
0x180010bbb  pop     rdi
0x180010bbc  pop     rbp
0x180010bbd  retn
0x180010bbe  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x180010bc3  mov     r8, rax; struct std::error_category *
0x180010bc6  lea     r9, aParsenetworkst_0; "ParseNetworkString failed"
0x180010bcd  lea     rcx, [rbp+1F0h+pExceptionObject]; this
0x180010bd4  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180010bd9  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180010be0  lea     rcx, [rbp+1F0h+pExceptionObject]; pExceptionObject
0x180010be7  call    _CxxThrowException_0
```

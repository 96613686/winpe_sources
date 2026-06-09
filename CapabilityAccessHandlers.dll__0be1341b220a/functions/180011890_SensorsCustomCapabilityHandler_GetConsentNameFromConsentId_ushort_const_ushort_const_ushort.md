# SensorsCustomCapabilityHandler::GetConsentNameFromConsentId(ushort const *,ushort const *,ushort * *)

- ea: `0x180011890`
- end: `0x180011a91`
- name: `?GetConsentNameFromConsentId@SensorsCustomCapabilityHandler@@UEAAJPEBG0PEAPEAG@Z`
- size: `513`
- prototype: `__int64 __fastcall(SensorsCustomCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011aa0`

## callees

- `0x180004c70`
- `0x1800090f4`
- `0x18000b370`
- `0x1800115f4`
- `0x180011890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800118c6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800118c6`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180011993`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180011993`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180011a31`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180011a68`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180011a31`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180011a68`

## pseudocode

```c
__int64 __fastcall SensorsCustomCapabilityHandler::GetConsentNameFromConsentId(
        SensorsCustomCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  HRESULT v5; // eax
  unsigned int Objects; // ebx
  __int64 v7; // r8
  const char *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rax
  char *v11; // rdx
  unsigned __int16 *v12; // rax
  int v14; // [rsp+20h] [rbp-59h]
  int v15; // [rsp+20h] [rbp-59h]
  unsigned int v16; // [rsp+40h] [rbp-39h] BYREF
  __int64 v17; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v18; // [rsp+50h] [rbp-29h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-21h] BYREF
  int v20; // [rsp+68h] [rbp-11h] BYREF
  DEVPROPKEY v21; // [rsp+70h] [rbp-9h]
  int v22; // [rsp+84h] [rbp+Bh]
  __int64 v23; // [rsp+88h] [rbp+Fh]
  int v24; // [rsp+90h] [rbp+17h]
  int v25; // [rsp+94h] [rbp+1Bh]
  GUID *p_pclsid; // [rsp+98h] [rbp+1Fh]
  DEVPROPKEY v27; // [rsp+A0h] [rbp+27h] BYREF
  int v28; // [rsp+B4h] [rbp+3Bh]
  __int64 v29; // [rsp+B8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  pclsid = 0;
  v5 = CLSIDFromString(a3, &pclsid);
  Objects = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sensorscustom\\sensorscustomcapabilityhandler.cpp",
      (const char *)(unsigned int)v5,
      v14);
    return Objects;
  }
  v27 = DEVPKEY_DeviceInterface_FriendlyName;
  v21 = DEVPKEY_DeviceInterface_ClassGuid;
  p_pclsid = &pclsid;
  v28 = 0;
  v29 = 0;
  v20 = 2;
  v22 = 0;
  v23 = 0;
  v24 = 13;
  v25 = 16;
  v16 = 0;
  v17 = 0;
  Objects = DevGetObjects(1, 4, 1, &v27, 1, &v20, &v16, &v17);
  if ( (Objects & 0x80000000) != 0 )
  {
    v9 = 84;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sensorscustom\\sensorscustomcapabilityhandler.cpp",
      (const char *)Objects,
      v15);
LABEL_18:
    if ( v16 )
    {
      if ( v17 )
        DevFreeObjects(v16);
    }
    return Objects;
  }
  if ( !v16
    || *(_DWORD *)(v17 + 16) != 1
    || (v10 = *(_QWORD *)(v17 + 24)) == 0
    || *(_DWORD *)(v10 + 32) != 18
    || (v11 = *(char **)(v10 + 40)) == 0 )
  {
    Objects = -2147467259;
    v9 = 93;
    goto LABEL_17;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v18,
    v11,
    v7,
    v8);
  v12 = v18;
  if ( !v18 )
  {
    Objects = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\base\\devices\\cam\\handler\\sensorscustom\\sensorscustomcapabilityhandler.cpp",
      (const char *)0x8007000ELL,
      v15);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v18);
    goto LABEL_18;
  }
  v18 = 0;
  *a4 = v12;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v18);
  if ( v16 && v17 )
    DevFreeObjects(v16);
  return 0;
}

```

## disassembly

```asm
0x180011890  mov     [rsp-8+arg_0], rbx
0x180011895  mov     [rsp-8+arg_8], rdi
0x18001189a  push    rbp
0x18001189b  lea     rbp, [rsp-57h]
0x1800118a0  sub     rsp, 0D0h
0x1800118a7  mov     rax, cs:__security_cookie
0x1800118ae  xor     rax, rsp
0x1800118b1  mov     [rbp+57h+var_10], rax
0x1800118b5  xorps   xmm0, xmm0
0x1800118b8  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800118bc  mov     rcx, r8; lpsz
0x1800118bf  mov     rdi, r9
0x1800118c2  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1800118c6  call    cs:__imp_CLSIDFromString
0x1800118cc  mov     ebx, eax
0x1800118ce  test    eax, eax
0x1800118d0  jns     short loc_1800118EF
0x1800118d2  mov     rcx, [rbp+5Fh]; this
0x1800118d6  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\handler\\s"...
0x1800118dd  mov     r9d, eax; char *
0x1800118e0  mov     edx, 33h ; '3'; void *
0x1800118e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118ea  jmp     loc_180011A6E
0x1800118ef  mov     eax, cs:DEVPKEY_DeviceInterface_FriendlyName.pid
0x1800118f5  lea     r9, [rbp+57h+var_30]
0x1800118f9  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_FriendlyName.fmtid.Data1
0x180011900  mov     [rbp+57h+var_20], eax
0x180011903  mov     edx, 4
0x180011908  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18001190e  mov     [rbp+57h+var_50], eax
0x180011911  lea     rax, [rbp+57h+pclsid]
0x180011915  mov     [rbp+57h+var_38], rax
0x180011919  lea     rax, [rbp+57h+var_88]
0x18001191d  mov     [rsp+0D0h+var_98], rax
0x180011922  lea     ecx, [rdx-3]
0x180011925  lea     rax, [rbp+57h+var_90]
0x180011929  mov     [rbp+57h+var_1C], 0
0x180011930  mov     [rsp+0D0h+var_A0], rax
0x180011935  mov     r8d, ecx
0x180011938  movups  [rbp+57h+var_30], xmm0
0x18001193c  lea     rax, [rbp+57h+var_68]
0x180011940  mov     [rbp+57h+var_18], 0
0x180011948  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18001194f  mov     [rsp+0D0h+var_A8], rax
0x180011954  mov     [rsp+0D0h+var_B0], 1; int
0x18001195c  mov     [rbp+57h+var_68], 2
0x180011963  movups  [rbp+57h+var_60], xmm0
0x180011967  mov     [rbp+57h+var_4C], 0
0x18001196e  mov     [rbp+57h+var_48], 0
0x180011976  mov     [rbp+57h+var_40], 0Dh
0x18001197d  mov     [rbp+57h+var_3C], 10h
0x180011984  mov     [rbp+57h+var_90], 0
0x18001198b  mov     [rbp+57h+var_88], 0
0x180011993  call    cs:__imp_DevGetObjects
0x180011999  mov     ebx, eax
0x18001199b  test    eax, eax
0x18001199d  jns     short loc_1800119A9
0x18001199f  mov     edx, 54h ; 'T'
0x1800119a4  jmp     loc_180011A45
0x1800119a9  cmp     [rbp+57h+var_90], 0
0x1800119ad  jz      loc_180011A3B
0x1800119b3  mov     rax, [rbp+57h+var_88]
0x1800119b7  cmp     dword ptr [rax+10h], 1
0x1800119bb  jnz     short loc_180011A3B
0x1800119bd  mov     rax, [rax+18h]
0x1800119c1  test    rax, rax
0x1800119c4  jz      short loc_180011A3B
0x1800119c6  cmp     dword ptr [rax+20h], 12h
0x1800119ca  jnz     short loc_180011A3B
0x1800119cc  mov     rdx, [rax+28h]
0x1800119d0  test    rdx, rdx
0x1800119d3  jz      short loc_180011A3B
0x1800119d5  lea     rcx, [rbp+57h+var_80]
0x1800119d9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800119de  mov     rax, [rbp+57h+var_80]
0x1800119e2  test    rax, rax
0x1800119e5  jnz     short loc_180011A0D
0x1800119e7  mov     rcx, [rbp+5Fh]; this
0x1800119eb  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\handler\\s"...
0x1800119f2  mov     ebx, 8007000Eh
0x1800119f7  lea     edx, [rax+62h]; void *
0x1800119fa  mov     r9d, ebx; char *
0x1800119fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a02  lea     rcx, [rbp+57h+var_80]
0x180011a06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011a0b  jmp     short loc_180011A58
0x180011a0d  lea     rcx, [rbp+57h+var_80]
0x180011a11  mov     [rbp+57h+var_80], 0
0x180011a19  mov     [rdi], rax
0x180011a1c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011a21  mov     ecx, [rbp+57h+var_90]
0x180011a24  test    ecx, ecx
0x180011a26  jz      short loc_180011A37
0x180011a28  mov     rdx, [rbp+57h+var_88]
0x180011a2c  test    rdx, rdx
0x180011a2f  jz      short loc_180011A37
0x180011a31  call    cs:__imp_DevFreeObjects
0x180011a37  xor     eax, eax
0x180011a39  jmp     short loc_180011A70
0x180011a3b  mov     ebx, 80004005h
0x180011a40  mov     edx, 5Dh ; ']'; void *
0x180011a45  mov     rcx, [rbp+5Fh]; this
0x180011a49  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\handler\\s"...
0x180011a50  mov     r9d, ebx; char *
0x180011a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a58  mov     ecx, [rbp+57h+var_90]
0x180011a5b  test    ecx, ecx
0x180011a5d  jz      short loc_180011A6E
0x180011a5f  mov     rdx, [rbp+57h+var_88]
0x180011a63  test    rdx, rdx
0x180011a66  jz      short loc_180011A6E
0x180011a68  call    cs:__imp_DevFreeObjects
0x180011a6e  mov     eax, ebx
0x180011a70  mov     rcx, [rbp+57h+var_10]
0x180011a74  xor     rcx, rsp; StackCookie
0x180011a77  call    __security_check_cookie
0x180011a7c  lea     r11, [rsp+0D0h+var_s0]
0x180011a84  mov     rbx, [r11+10h]
0x180011a88  mov     rdi, [r11+18h]
0x180011a8c  mov     rsp, r11
0x180011a8f  pop     rbp
0x180011a90  retn
```

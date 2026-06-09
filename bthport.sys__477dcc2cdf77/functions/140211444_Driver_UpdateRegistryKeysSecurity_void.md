# Driver::UpdateRegistryKeysSecurity(void)

- ea: `0x140211444`
- end: `0x14021193d`
- name: `?UpdateRegistryKeysSecurity@Driver@@CAJXZ`
- size: `1273`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402102b0`

## callees

- `0x14000434c`
- `0x140005690`
- `0x14000f27c`
- `0x14000fab4`
- `0x1400276fc`
- `0x140027738`
- `0x140165516`
- `0x140165540`
- `0x140209168`
- `0x1402091b8`
- `0x14020940c`
- `0x140209628`
- `0x140211444`

## import_xrefs

- `ntoskrnl!ZwQueryKey` at `0x1402115d9`
- `ntoskrnl!ZwQueryKey` at `0x1402115d9`
- `ntoskrnl!ZwEnumerateKey` at `0x140211627`
- `ntoskrnl!ZwEnumerateKey` at `0x140211627`
- `ntoskrnl!ZwSetValueKey` at `0x1402118a4`
- `ntoskrnl!ZwSetValueKey` at `0x1402118a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140211823`
- `ntoskrnl!RtlInitUnicodeString` at `0x140211823`

## string_xrefs

- `0x1402114d8`: `RegTreeSecDescUpdated`
- `0x140211814`: `RegTreeSecDescUpdated`

## pseudocode

```c
__int64 __fastcall Driver::UpdateRegistryKeysSecurity(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  int v4; // edx
  NTSTATUS v5; // ebx
  int v6; // r8d
  PDEVICE_OBJECT v7; // r10
  void *DeviceExtension; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  char v10; // si
  void **v11; // rcx
  void *v12; // rbx
  int v13; // edx
  NTSTATUS v14; // edi
  int v15; // r8d
  ULONG i; // edi
  int v17; // edx
  int v18; // r8d
  NTSTATUS v19; // r14d
  __int64 v20; // rax
  PDEVICE_OBJECT v21; // rcx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rax
  char ResultLength; // [rsp+20h] [rbp-E0h]
  __int16 v26; // [rsp+30h] [rbp-D0h]
  __int16 v27; // [rsp+30h] [rbp-D0h]
  __int16 v28; // [rsp+30h] [rbp-D0h]
  char v29; // [rsp+40h] [rbp-C0h]
  char v30; // [rsp+40h] [rbp-C0h]
  char v31; // [rsp+40h] [rbp-C0h]
  char v32[8]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  void *v35; // [rsp+68h] [rbp-98h] BYREF
  void **v36; // [rsp+70h] [rbp-90h] BYREF
  void **v37; // [rsp+78h] [rbp-88h]
  ULONG v38; // [rsp+88h] [rbp-78h] BYREF
  ULONG v39; // [rsp+8Ch] [rbp-74h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+B0h] [rbp-50h]
  __int128 KeyInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v44; // [rsp+C8h] [rbp-38h]
  __int128 v45; // [rsp+D8h] [rbp-28h]
  char v46[12]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v47; // [rsp+FCh] [rbp-4h]
  wchar_t Str1[264]; // [rsp+100h] [rbp+0h] BYREF

  utl::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>(
    &v36,
    a2,
    a3);
  KeyHandle = 0;
  v3 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&KeyHandle);
  v5 = BthOpenKeyBthPortParams(0, v3);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    LOBYTE(v4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    v29 = v5;
    v26 = 42;
LABEL_61:
    AttachedDevice = v7->AttachedDevice;
    DeviceExtension = v7->DeviceExtension;
    ResultLength = 3;
LABEL_62:
    LOBYTE(v6) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      (_DWORD)AttachedDevice,
      v4,
      v6,
      (_DWORD)DeviceExtension,
      ResultLength,
      6,
      v26,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v29);
    goto LABEL_63;
  }
  v42 = 0;
  v32[0] = 0;
  v41 = 0;
  BthQueryKeyValueBool((_DWORD)KeyHandle, (unsigned int)&v41, (unsigned int)L"RegTreeSecDescUpdated", 0, (__int64)v32);
  if ( v32[0] )
  {
    LOBYTE(v4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v29 = v5;
    v26 = 43;
    ResultLength = 4;
    goto LABEL_62;
  }
  v10 = 0;
  utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::push_back(
    &v36,
    &KeyHandle);
LABEL_14:
  if ( v36 == v37 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RegTreeSecDescUpdated");
    v24 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&KeyHandle);
    v5 = BthOpenKeyBthPortParams(0, v24);
    if ( v5 >= 0 )
    {
      v5 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &qword_140179138, 4u);
      if ( v5 >= 0 )
      {
LABEL_63:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
        utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::_Uninit(&v36);
        return (unsigned int)v5;
      }
      v7 = WPP_GLOBAL_Control;
      LOBYTE(v4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      v29 = v5;
      v26 = 49;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      LOBYTE(v4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      v29 = v5;
      v26 = 48;
    }
    goto LABEL_61;
  }
  v11 = v37 - 1;
  v37 = v11;
  v35 = *v11;
  v12 = v35;
  *v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v11);
  v14 = EnforceDefaultPermissions(v12);
  if ( v14 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    v31 = v14;
    v28 = 44;
    goto LABEL_48;
  }
  v38 = 48;
  KeyInformation = 0;
  v44 = 0;
  v45 = 0;
  v14 = ZwQueryKey(v12, KeyFullInformation, &KeyInformation, 0x30u, &v38);
  if ( v14 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    v31 = v14;
    v28 = 45;
LABEL_48:
    LOBYTE(v15) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      v23->AttachedDevice,
      v13,
      v15,
      v23->DeviceExtension,
      3,
      6,
      v28,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v31);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
    utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::_Uninit(&v36);
    return (unsigned int)v14;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= DWORD1(v44) )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
      goto LABEL_14;
    }
    v34 = 0;
    v39 = 0;
    v19 = ZwEnumerateKey(v12, i, KeyBasicInformation, v46, 0x216u, &v39);
    if ( v19 < 0 )
      break;
    Str1[(unsigned __int64)v47 >> 1] = 0;
    if ( v10 || wcscmp_0(Str1, L"Keys") )
    {
      v20 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v34);
      v19 = BthOpenKey(v12, Str1, v20);
      if ( v19 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        LOBYTE(v17) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        v30 = v19;
        v27 = 47;
        goto LABEL_37;
      }
      utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::push_back(
        &v36,
        &v34);
    }
    else
    {
      v10 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
  }
  v21 = WPP_GLOBAL_Control;
  LOBYTE(v17) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
  v30 = v19;
  v27 = 46;
LABEL_37:
  LOBYTE(v18) = 1;
  WPP_RECORDER_AND_TRACE_SF_d(
    v21->AttachedDevice,
    v17,
    v18,
    v21->DeviceExtension,
    3,
    6,
    v27,
    (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
    v30);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
  utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::_Uninit(&v36);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140211444  push    rbp
0x140211446  push    rbx
0x140211447  push    rsi
0x140211448  push    rdi
0x140211449  push    r12
0x14021144b  push    r14
0x14021144d  lea     rbp, [rsp-228h]
0x140211455  sub     rsp, 328h
0x14021145c  mov     rax, cs:__security_cookie
0x140211463  xor     rax, rsp
0x140211466  mov     [rbp+250h+var_40], rax
0x14021146d  lea     rcx, [rsp+350h+var_2E0]
0x140211472  call    ??0?$vector@V?$shared_ptr@VCentralConnectedStream@@@utl@@V?$allocator@V?$shared_ptr@VCentralConnectedStream@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>(void)
0x140211477  lea     rcx, [rsp+350h+KeyHandle]
0x14021147c  mov     [rsp+350h+KeyHandle], 0
0x140211485  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x14021148a  mov     rdx, rax
0x14021148d  xor     ecx, ecx
0x14021148f  call    BthOpenKeyBthPortParams
0x140211494  mov     ebx, eax
0x140211496  test    eax, eax
0x140211498  jns     short loc_1402114D3
0x14021149a  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1402114a1  mov     ecx, [r10+2Ch]
0x1402114a5  test    cl, 20h
0x1402114a8  jz      short loc_1402114B5
0x1402114aa  cmp     byte ptr [r10+29h], 3
0x1402114af  jb      short loc_1402114B5
0x1402114b1  mov     dl, 1
0x1402114b3  jmp     short loc_1402114B7
0x1402114b5  xor     dl, dl
0x1402114b7  mov     dword ptr [rsp+350h+var_310], ebx
0x1402114bb  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x1402114c2  mov     [rsp+350h+var_318], rax
0x1402114c7  mov     [rsp+350h+var_320], 2Ah ; '*'
0x1402114ce  jmp     loc_1402118EA
0x1402114d3  mov     rcx, [rsp+350h+KeyHandle]
0x1402114d8  lea     r8, aRegtreesecdesc; "RegTreeSecDescUpdated"
0x1402114df  xor     eax, eax
0x1402114e1  lea     rdx, [rbp+250h+var_2B0]
0x1402114e5  mov     [rbp+250h+var_2A0], eax
0x1402114e8  xorps   xmm0, xmm0
0x1402114eb  mov     [rsp+350h+var_300], al
0x1402114ef  xor     r9d, r9d
0x1402114f2  lea     rax, [rsp+350h+var_300]
0x1402114f7  mov     [rsp+350h+ResultLength], rax
0x1402114fc  movups  [rbp+250h+var_2B0], xmm0
0x140211500  call    BthQueryKeyValueBool
0x140211505  cmp     [rsp+350h+var_300], 0
0x14021150a  jz      short loc_140211557
0x14021150c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140211513  mov     eax, [rcx+2Ch]
0x140211516  test    al, 20h
0x140211518  jz      short loc_140211524
0x14021151a  cmp     byte ptr [rcx+29h], 4
0x14021151e  jb      short loc_140211524
0x140211520  mov     dl, 1
0x140211522  jmp     short loc_140211526
0x140211524  xor     dl, dl
0x140211526  mov     r9, [rcx+40h]
0x14021152a  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140211531  mov     rcx, [rcx+18h]
0x140211535  mov     dword ptr [rsp+350h+var_310], ebx
0x140211539  mov     [rsp+350h+var_318], rax
0x14021153e  mov     [rsp+350h+var_320], 2Bh ; '+'
0x140211545  mov     dword ptr [rsp+350h+var_328], 6
0x14021154d  mov     byte ptr [rsp+350h+ResultLength], 4
0x140211552  jmp     loc_1402118FF
0x140211557  xor     sil, sil
0x14021155a  lea     rdx, [rsp+350h+KeyHandle]
0x14021155f  lea     rcx, [rsp+350h+var_2E0]
0x140211564  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@QEAA_N$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::push_back(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x140211569  mov     r12d, 30h ; '0'
0x14021156f  mov     rcx, [rsp+350h+var_2D8]
0x140211574  cmp     [rsp+350h+var_2E0], rcx
0x140211579  jz      loc_140211811
0x14021157f  add     rcx, 0FFFFFFFFFFFFFFF8h
0x140211583  mov     [rsp+350h+var_2D8], rcx
0x140211588  mov     rbx, [rcx]
0x14021158b  mov     [rsp+350h+var_2E8], rbx
0x140211590  mov     qword ptr [rcx], 0
0x140211597  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14021159c  mov     rcx, rbx
0x14021159f  call    EnforceDefaultPermissions
0x1402115a4  mov     edi, eax
0x1402115a6  test    eax, eax
0x1402115a8  js      loc_14021179E
0x1402115ae  xorps   xmm0, xmm0
0x1402115b1  mov     [rbp+250h+var_2C8], r12d
0x1402115b5  lea     rax, [rbp+250h+var_2C8]
0x1402115b9  mov     r9d, r12d; Length
0x1402115bc  lea     r8, [rbp+250h+KeyInformation]; KeyInformation
0x1402115c0  mov     [rsp+350h+ResultLength], rax; ResultLength
0x1402115c5  mov     edx, 2; KeyInformationClass
0x1402115ca  mov     rcx, rbx; KeyHandle
0x1402115cd  movups  [rbp+250h+KeyInformation], xmm0
0x1402115d1  movups  [rbp+250h+var_288], xmm0
0x1402115d5  movups  [rbp+250h+var_278], xmm0
0x1402115d9  call    cs:__imp_ZwQueryKey
0x1402115e0  nop     dword ptr [rax+rax+00h]
0x1402115e5  mov     edi, eax
0x1402115e7  test    eax, eax
0x1402115e9  js      loc_14021176B
0x1402115ef  xor     edi, edi
0x1402115f1  cmp     edi, dword ptr [rbp+250h+var_288+4]
0x1402115f4  jnb     loc_1402116A9
0x1402115fa  lea     rax, [rbp+250h+var_2C4]
0x1402115fe  mov     [rsp+350h+var_2F0], 0
0x140211607  mov     [rsp+350h+var_328], rax; ResultLength
0x14021160c  lea     r9, [rbp+250h+var_260]; KeyInformation
0x140211610  xor     r8d, r8d; KeyInformationClass
0x140211613  mov     dword ptr [rsp+350h+ResultLength], 216h; Length
0x14021161b  mov     edx, edi; Index
0x14021161d  mov     [rbp+250h+var_2C4], 0
0x140211624  mov     rcx, rbx; KeyHandle
0x140211627  call    cs:__imp_ZwEnumerateKey
0x14021162e  nop     dword ptr [rax+rax+00h]
0x140211633  mov     r14d, eax
0x140211636  test    eax, eax
0x140211638  js      loc_1402116EC
0x14021163e  mov     ecx, [rbp+250h+var_254]
0x140211641  xor     eax, eax
0x140211643  shr     rcx, 1
0x140211646  mov     [rbp+rcx*2+250h+Str1], ax
0x14021164b  test    sil, sil
0x14021164e  jnz     short loc_140211669
0x140211650  lea     rdx, aKeys; "Keys"
0x140211657  lea     rcx, [rbp+250h+Str1]; Str1
0x14021165b  call    wcscmp_0
0x140211660  test    eax, eax
0x140211662  jnz     short loc_140211669
0x140211664  mov     sil, 1
0x140211667  jmp     short loc_140211698
0x140211669  lea     rcx, [rsp+350h+var_2F0]
0x14021166e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x140211673  mov     r8, rax
0x140211676  lea     rdx, [rbp+250h+Str1]
0x14021167a  mov     rcx, rbx
0x14021167d  call    BthOpenKey
0x140211682  mov     r14d, eax
0x140211685  test    eax, eax
0x140211687  js      short loc_1402116B8
0x140211689  lea     rdx, [rsp+350h+var_2F0]
0x14021168e  lea     rcx, [rsp+350h+var_2E0]
0x140211693  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@QEAA_N$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::push_back(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x140211698  lea     rcx, [rsp+350h+var_2F0]
0x14021169d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402116a2  inc     edi
0x1402116a4  jmp     loc_1402115F1
0x1402116a9  lea     rcx, [rsp+350h+var_2E8]
0x1402116ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402116b3  jmp     loc_14021156F
0x1402116b8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1402116bf  mov     eax, [rcx+2Ch]
0x1402116c2  test    al, 20h
0x1402116c4  jz      short loc_1402116D0
0x1402116c6  cmp     byte ptr [rcx+29h], 3
0x1402116ca  jb      short loc_1402116D0
0x1402116cc  mov     dl, 1
0x1402116ce  jmp     short loc_1402116D2
0x1402116d0  xor     dl, dl
0x1402116d2  mov     dword ptr [rsp+350h+var_310], r14d
0x1402116d7  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x1402116de  mov     [rsp+350h+var_318], rax
0x1402116e3  mov     [rsp+350h+var_320], 2Fh ; '/'
0x1402116ea  jmp     short loc_14021171E
0x1402116ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1402116f3  mov     eax, [rcx+2Ch]
0x1402116f6  test    al, 20h
0x1402116f8  jz      short loc_140211704
0x1402116fa  cmp     byte ptr [rcx+29h], 3
0x1402116fe  jb      short loc_140211704
0x140211700  mov     dl, 1
0x140211702  jmp     short loc_140211706
0x140211704  xor     dl, dl
0x140211706  mov     dword ptr [rsp+350h+var_310], r14d
0x14021170b  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140211712  mov     [rsp+350h+var_318], rax
0x140211717  mov     [rsp+350h+var_320], 2Eh ; '.'
0x14021171e  mov     r9, [rcx+40h]
0x140211722  mov     r8b, 1
0x140211725  mov     rcx, [rcx+18h]
0x140211729  mov     dword ptr [rsp+350h+var_328], 6
0x140211731  mov     byte ptr [rsp+350h+ResultLength], 3
0x140211736  call    WPP_RECORDER_AND_TRACE_SF_d
0x14021173b  lea     rcx, [rsp+350h+var_2F0]
0x140211740  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140211745  lea     rcx, [rsp+350h+var_2E8]
0x14021174a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14021174f  lea     rcx, [rsp+350h+KeyHandle]
0x140211754  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140211759  lea     rcx, [rsp+350h+var_2E0]
0x14021175e  call    ?_Uninit@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@AEAAXXZ; utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::_Uninit(void)
0x140211763  mov     eax, r14d
0x140211766  jmp     loc_14021191D
0x14021176b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140211772  mov     eax, [rcx+2Ch]
0x140211775  test    al, 20h
0x140211777  jz      short loc_140211783
0x140211779  cmp     byte ptr [rcx+29h], 3
0x14021177d  jb      short loc_140211783
0x14021177f  mov     dl, 1
0x140211781  jmp     short loc_140211785
0x140211783  xor     dl, dl
0x140211785  mov     dword ptr [rsp+350h+var_310], edi
0x140211789  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140211790  mov     [rsp+350h+var_318], rax
0x140211795  mov     [rsp+350h+var_320], 2Dh ; '-'
0x14021179c  jmp     short loc_1402117CF
0x14021179e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1402117a5  mov     eax, [rcx+2Ch]
0x1402117a8  test    al, 20h
0x1402117aa  jz      short loc_1402117B6
0x1402117ac  cmp     byte ptr [rcx+29h], 3
0x1402117b0  jb      short loc_1402117B6
0x1402117b2  mov     dl, 1
0x1402117b4  jmp     short loc_1402117B8
0x1402117b6  xor     dl, dl
0x1402117b8  mov     dword ptr [rsp+350h+var_310], edi
0x1402117bc  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x1402117c3  mov     [rsp+350h+var_318], rax
0x1402117c8  mov     [rsp+350h+var_320], 2Ch ; ','
0x1402117cf  mov     r9, [rcx+40h]
0x1402117d3  mov     r8b, 1
0x1402117d6  mov     rcx, [rcx+18h]
0x1402117da  mov     dword ptr [rsp+350h+var_328], 6
0x1402117e2  mov     byte ptr [rsp+350h+ResultLength], 3
0x1402117e7  call    WPP_RECORDER_AND_TRACE_SF_d
0x1402117ec  lea     rcx, [rsp+350h+var_2E8]
0x1402117f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402117f6  lea     rcx, [rsp+350h+KeyHandle]
0x1402117fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140211800  lea     rcx, [rsp+350h+var_2E0]
0x140211805  call    ?_Uninit@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@AEAAXXZ; utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::_Uninit(void)
0x14021180a  mov     eax, edi
0x14021180c  jmp     loc_14021191D
0x140211811  xorps   xmm0, xmm0
0x140211814  lea     rdx, aRegtreesecdesc; "RegTreeSecDescUpdated"
0x14021181b  lea     rcx, [rbp+250h+DestinationString]; DestinationString
0x14021181f  movups  xmmword ptr [rbp+250h+DestinationString.Length], xmm0
0x140211823  call    cs:__imp_RtlInitUnicodeString
0x14021182a  nop     dword ptr [rax+rax+00h]
0x14021182f  lea     rcx, [rsp+350h+KeyHandle]
0x140211834  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x140211839  mov     rdx, rax
0x14021183c  xor     ecx, ecx
0x14021183e  call    BthOpenKeyBthPortParams
0x140211843  mov     ebx, eax
0x140211845  test    eax, eax
0x140211847  jns     short loc_14021187E
0x140211849  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140211850  mov     ecx, [r10+2Ch]
0x140211854  test    cl, 20h
0x140211857  jz      short loc_140211864
0x140211859  cmp     byte ptr [r10+29h], 3
0x14021185e  jb      short loc_140211864
0x140211860  mov     dl, 1
0x140211862  jmp     short loc_140211866
0x140211864  xor     dl, dl
0x140211866  mov     dword ptr [rsp+350h+var_310], ebx
0x14021186a  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140211871  mov     [rsp+350h+var_318], rax
0x140211876  mov     [rsp+350h+var_320], r12w
0x14021187c  jmp     short loc_1402118EA
0x14021187e  mov     rcx, [rsp+350h+KeyHandle]; KeyHandle
0x140211883  lea     rax, qword_140179138
0x14021188a  mov     dword ptr [rsp+350h+var_328], 4; DataSize
0x140211892  lea     rdx, [rbp+250h+DestinationString]; ValueName
0x140211896  mov     r9d, 4; Type
0x14021189c  mov     [rsp+350h+ResultLength], rax; Data
0x1402118a1  xor     r8d, r8d; TitleIndex
0x1402118a4  call    cs:__imp_ZwSetValueKey
0x1402118ab  nop     dword ptr [rax+rax+00h]
0x1402118b0  mov     ebx, eax
0x1402118b2  test    eax, eax
0x1402118b4  jns     short loc_140211907
0x1402118b6  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1402118bd  mov     ecx, [r10+2Ch]
0x1402118c1  test    cl, 20h
0x1402118c4  jz      short loc_1402118D1
0x1402118c6  cmp     byte ptr [r10+29h], 3
0x1402118cb  jb      short loc_1402118D1
0x1402118cd  mov     dl, 1
0x1402118cf  jmp     short loc_1402118D3
0x1402118d1  xor     dl, dl
0x1402118d3  mov     dword ptr [rsp+350h+var_310], ebx
0x1402118d7  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x1402118de  mov     [rsp+350h+var_318], rax
0x1402118e3  mov     [rsp+350h+var_320], 31h ; '1'
0x1402118ea  mov     rcx, [r10+18h]
0x1402118ee  mov     r9, [r10+40h]
0x1402118f2  mov     dword ptr [rsp+350h+var_328], 6
0x1402118fa  mov     byte ptr [rsp+350h+ResultLength], 3
0x1402118ff  mov     r8b, 1
0x140211902  call    WPP_RECORDER_AND_TRACE_SF_d
0x140211907  lea     rcx, [rsp+350h+KeyHandle]
0x14021190c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140211911  lea     rcx, [rsp+350h+var_2E0]
0x140211916  call    ?_Uninit@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@AEAAXXZ; utl::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,utl::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::_Uninit(void)
0x14021191b  mov     eax, ebx
  ... truncated ...
```

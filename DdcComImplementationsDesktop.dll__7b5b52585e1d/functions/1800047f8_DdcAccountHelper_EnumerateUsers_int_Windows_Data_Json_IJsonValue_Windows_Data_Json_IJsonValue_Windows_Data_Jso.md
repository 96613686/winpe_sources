# DdcAccountHelper::EnumerateUsers(int,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *)

- ea: `0x1800047f8`
- end: `0x180004afa`
- name: `?EnumerateUsers@DdcAccountHelper@@SAJHPEAPEAUIJsonValue@Json@Data@Windows@@00PEAK11@Z`
- size: `770`
- prototype: `__int64 __fastcall(__int64, struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonValue **, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003680`

## callees

- `0x1800016b0`
- `0x1800026ac`
- `0x1800027e4`
- `0x1800047f8`
- `0x180004b00`
- `0x18000c010`

## import_xrefs

- `MdmCommon!MdmEnumerateUsers` at `0x180004903`
- `MdmCommon!MdmEnumerateUsers` at `0x180004903`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004895`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800048b3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800048b3`

## string_xrefs

- `0x18000488e`: `Windows.Data.Json.JsonValue`
- `0x1800048e0`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcaccounthelper.cpp`
- `0x1800048cc`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`

## pseudocode

```c
__int64 __fastcall DdcAccountHelper::EnumerateUsers(
        __int64 a1,
        struct Windows::Data::Json::IJsonValue **a2,
        struct Windows::Data::Json::IJsonValue **a3,
        struct Windows::Data::Json::IJsonValue **a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // edx
  int v11; // ecx
  int ActivationFactory; // ebx
  int v13; // edx
  int v14; // ecx
  unsigned int v15; // r8d
  __int64 i; // rax
  unsigned int v17; // edx
  __int64 j; // rax
  unsigned int v19; // ecx
  __int64 k; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h]
  __int64 v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  __int64 v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+58h] [rbp-A8h]
  __int64 v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h]
  __int64 v41; // [rsp+70h] [rbp-90h]
  __int64 v42; // [rsp+78h] [rbp-88h]
  __int64 v43; // [rsp+80h] [rbp-80h]
  __int128 v44; // [rsp+88h] [rbp-78h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h]
  __int128 v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-50h]
  __int128 v48; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING string; // [rsp+E8h] [rbp-18h] BYREF

  v43 = 0;
  v33 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v48 = 0;
  v49 = 0;
  v46 = 0;
  v47 = 0;
  v44 = 0;
  v45 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x180004AF9LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v33);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = MdmEnumerateUsers(&v48, &v46, &v44, 0);
    if ( ActivationFactory >= 0 )
    {
      v15 = 0;
      for ( i = v48; i != *((_QWORD *)&v48 + 1); i += 32 )
        ++v15;
      v17 = 0;
      for ( j = v46; j != *((_QWORD *)&v46 + 1); j += 32 )
        ++v17;
      v19 = 0;
      for ( k = v44; k != *((_QWORD *)&v44 + 1); k += 32 )
        ++v19;
      if ( a5 )
        *a5 = v15;
      if ( a6 )
        *a6 = v17;
      if ( a7 )
        *a7 = v19;
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
        105,
        (__int64)"CHR(MdmEnumerateUsers(&vAdmins, &vDeviceOwners, &vStandardUsers, fConnectedOnly))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v11,
      v10,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
      85,
      (__int64)"CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStat"
               "ics.GetAddressOf()))");
  }
  std::vector<std::wstring>::~vector<std::wstring>(&v44);
  std::vector<std::wstring>::~vector<std::wstring>(&v46);
  std::vector<std::wstring>::~vector<std::wstring>(&v48);
  v21 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800047f8  push    rbp
0x1800047fa  push    rbx
0x1800047fb  push    rsi
0x1800047fc  push    rdi
0x1800047fd  push    r14
0x1800047ff  push    r15
0x180004801  lea     rbp, [rsp-8]
0x180004806  sub     rsp, 108h
0x18000480d  mov     rax, cs:__security_cookie
0x180004814  xor     rax, rsp
0x180004817  mov     [rbp+30h+var_40], rax
0x18000481b  mov     r14, [rbp+30h+arg_20]
0x18000481f  mov     rsi, [rbp+30h+arg_28]
0x180004823  mov     rdi, [rbp+30h+arg_30]
0x180004827  xor     r15d, r15d
0x18000482a  mov     [rbp+30h+var_B0], r15
0x18000482e  mov     [rsp+130h+var_100], r15
0x180004833  mov     [rsp+130h+var_B8], r15
0x180004838  mov     [rsp+130h+var_C0], r15
0x18000483d  mov     [rsp+130h+var_C8], r15
0x180004842  mov     [rsp+130h+var_D0], r15
0x180004847  mov     [rsp+130h+var_D8], r15
0x18000484c  mov     [rsp+130h+var_E0], r15
0x180004851  mov     [rsp+130h+var_E8], r15
0x180004856  mov     [rsp+130h+var_F0], r15
0x18000485b  mov     [rsp+130h+var_F8], r15
0x180004860  xorps   xmm0, xmm0
0x180004863  movdqu  [rbp+30h+var_78], xmm0
0x180004868  mov     [rbp+30h+var_68], r15
0x18000486c  movdqu  [rbp+30h+var_90], xmm0
0x180004871  mov     [rbp+30h+var_80], r15
0x180004875  movdqu  [rbp+30h+var_A8], xmm0
0x18000487a  mov     [rbp+30h+var_98], r15
0x18000487e  mov     [rbp+30h+string], r15
0x180004882  lea     r9, [rbp+30h+string]; string
0x180004886  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18000488a  lea     edx, [r15+1Bh]; length
0x18000488e  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180004895  call    cs:__imp_WindowsCreateStringReference
0x18000489b  test    eax, eax
0x18000489d  js      loc_180004AF2
0x1800048a3  lea     r8, [rsp+130h+var_100]
0x1800048a8  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800048af  mov     rcx, [rbp+30h+string]
0x1800048b3  call    cs:__imp_RoGetActivationFactory
0x1800048b9  mov     ebx, eax
0x1800048bb  test    eax, eax
0x1800048bd  jns     short loc_1800048F4
0x1800048bf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800048c6  jz      loc_180004984
0x1800048cc  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x1800048d3  mov     [rsp+130h+var_108], rax
0x1800048d8  mov     [rsp+130h+var_110], 55h ; 'U'
0x1800048e0  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800048e7  mov     r8d, ebx
0x1800048ea  call    McTemplateU0dsqs_EventWriteTransfer
0x1800048ef  jmp     loc_180004984
0x1800048f4  xor     r9d, r9d
0x1800048f7  lea     r8, [rbp+30h+var_A8]
0x1800048fb  lea     rdx, [rbp+30h+var_90]
0x1800048ff  lea     rcx, [rbp+30h+var_78]
0x180004903  call    cs:__imp_?MdmEnumerateUsers@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00H@Z; MdmEnumerateUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *,int)
0x180004909  mov     ebx, eax
0x18000490b  test    eax, eax
0x18000490d  jns     short loc_18000492E
0x18000490f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004916  jz      short loc_180004984
0x180004918  lea     rax, aChrMdmenumerat; "CHR(MdmEnumerateUsers(&vAdmins, &vDevic"...
0x18000491f  mov     [rsp+130h+var_108], rax
0x180004924  mov     [rsp+130h+var_110], 69h ; 'i'
0x18000492c  jmp     short loc_1800048E0
0x18000492e  mov     r8d, r15d
0x180004931  mov     rax, qword ptr [rbp+30h+var_78]
0x180004935  jmp     short loc_18000493E
0x180004937  inc     r8d
0x18000493a  add     rax, 20h ; ' '
0x18000493e  cmp     rax, qword ptr [rbp+30h+var_78+8]
0x180004942  jnz     short loc_180004937
0x180004944  mov     edx, r15d
0x180004947  mov     rax, qword ptr [rbp+30h+var_90]
0x18000494b  jmp     short loc_180004953
0x18000494d  inc     edx
0x18000494f  add     rax, 20h ; ' '
0x180004953  cmp     rax, qword ptr [rbp+30h+var_90+8]
0x180004957  jnz     short loc_18000494D
0x180004959  mov     ecx, r15d
0x18000495c  mov     rax, qword ptr [rbp+30h+var_A8]
0x180004960  jmp     short loc_180004968
0x180004962  inc     ecx
0x180004964  add     rax, 20h ; ' '
0x180004968  cmp     rax, qword ptr [rbp+30h+var_A8+8]
0x18000496c  jnz     short loc_180004962
0x18000496e  test    r14, r14
0x180004971  jz      short loc_180004976
0x180004973  mov     [r14], r8d
0x180004976  test    rsi, rsi
0x180004979  jz      short loc_18000497D
0x18000497b  mov     [rsi], edx
0x18000497d  test    rdi, rdi
0x180004980  jz      short loc_180004984
0x180004982  mov     [rdi], ecx
0x180004984  lea     rcx, [rbp+30h+var_A8]
0x180004988  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18000498d  nop
0x18000498e  lea     rcx, [rbp+30h+var_90]
0x180004992  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180004997  nop
0x180004998  lea     rcx, [rbp+30h+var_78]
0x18000499c  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800049a1  nop
0x1800049a2  mov     rcx, [rsp+130h+var_F8]
0x1800049a7  test    rcx, rcx
0x1800049aa  jz      short loc_1800049BE
0x1800049ac  mov     [rsp+130h+var_F8], r15
0x1800049b1  mov     rax, [rcx]
0x1800049b4  mov     rax, [rax+10h]
0x1800049b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049bd  nop
0x1800049be  mov     rcx, [rsp+130h+var_F0]
0x1800049c3  test    rcx, rcx
0x1800049c6  jz      short loc_1800049DA
0x1800049c8  mov     [rsp+130h+var_F0], r15
0x1800049cd  mov     rax, [rcx]
0x1800049d0  mov     rax, [rax+10h]
0x1800049d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d9  nop
0x1800049da  mov     rcx, [rsp+130h+var_E8]
0x1800049df  test    rcx, rcx
0x1800049e2  jz      short loc_1800049F6
0x1800049e4  mov     [rsp+130h+var_E8], r15
0x1800049e9  mov     rax, [rcx]
0x1800049ec  mov     rax, [rax+10h]
0x1800049f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f5  nop
0x1800049f6  mov     rcx, [rsp+130h+var_E0]
0x1800049fb  test    rcx, rcx
0x1800049fe  jz      short loc_180004A12
0x180004a00  mov     [rsp+130h+var_E0], r15
0x180004a05  mov     rax, [rcx]
0x180004a08  mov     rax, [rax+10h]
0x180004a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a11  nop
0x180004a12  mov     rcx, [rsp+130h+var_D8]
0x180004a17  test    rcx, rcx
0x180004a1a  jz      short loc_180004A2E
0x180004a1c  mov     [rsp+130h+var_D8], r15
0x180004a21  mov     rax, [rcx]
0x180004a24  mov     rax, [rax+10h]
0x180004a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2d  nop
0x180004a2e  mov     rcx, [rsp+130h+var_D0]
0x180004a33  test    rcx, rcx
0x180004a36  jz      short loc_180004A4A
0x180004a38  mov     [rsp+130h+var_D0], r15
0x180004a3d  mov     rax, [rcx]
0x180004a40  mov     rax, [rax+10h]
0x180004a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a49  nop
0x180004a4a  mov     rcx, [rsp+130h+var_C8]
0x180004a4f  test    rcx, rcx
0x180004a52  jz      short loc_180004A66
0x180004a54  mov     [rsp+130h+var_C8], r15
0x180004a59  mov     rax, [rcx]
0x180004a5c  mov     rax, [rax+10h]
0x180004a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a65  nop
0x180004a66  mov     rcx, [rsp+130h+var_C0]
0x180004a6b  test    rcx, rcx
0x180004a6e  jz      short loc_180004A82
0x180004a70  mov     [rsp+130h+var_C0], r15
0x180004a75  mov     rax, [rcx]
0x180004a78  mov     rax, [rax+10h]
0x180004a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a81  nop
0x180004a82  mov     rcx, [rsp+130h+var_B8]
0x180004a87  test    rcx, rcx
0x180004a8a  jz      short loc_180004A9E
0x180004a8c  mov     [rsp+130h+var_B8], r15
0x180004a91  mov     rax, [rcx]
0x180004a94  mov     rax, [rax+10h]
0x180004a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a9d  nop
0x180004a9e  mov     rcx, [rsp+130h+var_100]
0x180004aa3  test    rcx, rcx
0x180004aa6  jz      short loc_180004ABA
0x180004aa8  mov     [rsp+130h+var_100], r15
0x180004aad  mov     rax, [rcx]
0x180004ab0  mov     rax, [rax+10h]
0x180004ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab9  nop
0x180004aba  mov     rcx, [rbp+30h+var_B0]
0x180004abe  test    rcx, rcx
0x180004ac1  jz      short loc_180004AD4
0x180004ac3  mov     [rbp+30h+var_B0], r15
0x180004ac7  mov     rax, [rcx]
0x180004aca  mov     rax, [rax+10h]
0x180004ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad3  nop
0x180004ad4  mov     eax, ebx
0x180004ad6  mov     rcx, [rbp+30h+var_40]
0x180004ada  xor     rcx, rsp; StackCookie
0x180004add  call    __security_check_cookie
0x180004ae2  add     rsp, 108h
0x180004ae9  pop     r15
0x180004aeb  pop     r14
0x180004aed  pop     rdi
0x180004aee  pop     rsi
0x180004aef  pop     rbx
0x180004af0  pop     rbp
0x180004af1  retn
0x180004af2  mov     ecx, eax; this
0x180004af4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

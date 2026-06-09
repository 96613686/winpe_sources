# Dynamo::SyncmlPackProcessor::ApplySettingsPack(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x140041cc0`
- end: `0x14004200a`
- name: `?ApplySettingsPack@SyncmlPackProcessor@Dynamo@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG000@Z`
- size: `842`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14000a6e4`
- `0x14000bb88`
- `0x14003d008`
- `0x140041ab4`
- `0x140041c44`
- `0x140041cc0`
- `0x14004217c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140041d32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140041d32`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140041f61`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140041f61`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140041cef`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140041cef`

## string_xrefs

- `0x140041f7a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140041d7d`: `OMADM::TargetedUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Dynamo::SyncmlPackProcessor::ApplySettingsPack(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  HRESULT v9; // eax
  BOOL v10; // ebx
  HRESULT v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  const char *v16; // r9
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const char *v20; // r9
  const char *v21; // r9
  LPVOID v22; // rcx
  int ppv; // [rsp+20h] [rbp-B9h]
  int ppva; // [rsp+20h] [rbp-B9h]
  LPVOID v26; // [rsp+30h] [rbp-A9h] BYREF
  __int128 v27; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v28; // [rsp+48h] [rbp-91h]
  const wchar_t *v29; // [rsp+50h] [rbp-89h] BYREF
  __int64 v30; // [rsp+58h] [rbp-81h]
  int v31; // [rsp+60h] [rbp-79h]
  BOOL v32; // [rsp+64h] [rbp-75h]
  _QWORD v33[3]; // [rsp+68h] [rbp-71h] BYREF
  int v34; // [rsp+80h] [rbp-59h]
  int v35; // [rsp+84h] [rbp-55h]
  __int64 v36; // [rsp+88h] [rbp-51h]
  __int64 v37; // [rsp+90h] [rbp-49h] BYREF
  int v38; // [rsp+98h] [rbp-41h]
  int v39; // [rsp+9Ch] [rbp-3Dh]
  __int128 v40; // [rsp+A0h] [rbp-39h]
  __int128 v41; // [rsp+B0h] [rbp-29h]
  _OWORD v42[6]; // [rsp+C0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  v31 = 0;
  v9 = CoInitializeEx(0, 0);
  v10 = v9 >= 0;
  v32 = v10;
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  v26 = 0;
  v11 = CoCreateInstance(
          &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
          0,
          1u,
          &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
          &v26);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v11,
      ppva);
  v27 = 0;
  v28 = 0;
  v29 = L"OMADM::AccountID";
  v30 = a3;
  std::vector<tagSyncMLAttribute>::_Emplace_reallocate<tagSyncMLAttribute>(&v27, 0, &v29);
  if ( a4 )
  {
    v29 = L"OMADM::TargetedUserSID";
    v30 = a4;
    v12 = *((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) == v28 )
    {
      std::vector<tagSyncMLAttribute>::_Emplace_reallocate<tagSyncMLAttribute>(&v27, *((_QWORD *)&v27 + 1), &v29);
    }
    else
    {
      **((_QWORD **)&v27 + 1) = L"OMADM::TargetedUserSID";
      *(_QWORD *)(v12 + 8) = a4;
      *((_QWORD *)&v27 + 1) += 16LL;
    }
  }
  v29 = L"DYNAMO::CONTEXTID";
  v30 = a6;
  v13 = *((_QWORD *)&v27 + 1);
  if ( *((_QWORD *)&v27 + 1) == v28 )
  {
    std::vector<tagSyncMLAttribute>::_Emplace_reallocate<tagSyncMLAttribute>(&v27, *((_QWORD *)&v27 + 1), &v29);
    v14 = *((_QWORD *)&v27 + 1);
  }
  else
  {
    **((_QWORD **)&v27 + 1) = L"DYNAMO::CONTEXTID";
    *(_QWORD *)(v13 + 8) = a6;
    v14 = *((_QWORD *)&v27 + 1) + 16LL;
    *((_QWORD *)&v27 + 1) += 16LL;
  }
  v33[0] = 1;
  v34 = 0;
  v33[1] = a3;
  v33[2] = L"SyncmlPackProcessor";
  v15 = (v14 - (__int64)v27) >> 4;
  v35 = v15;
  if ( v15 > 0xFFFFFFFF )
    v35 = -1;
  v16 = v15 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
  if ( v15 > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x45,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      v16,
      ppva);
  v36 = v27;
  v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64, const char *))(*(_QWORD *)v26 + 24LL))(v26, v33, 40, v16);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x48,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v17,
      ppva);
  v40 = 0;
  v41 = 0;
  v38 = 1;
  v37 = a5;
  v39 = 1;
  memset(v42, 0, 48);
  v18 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64))(*(_QWORD *)v26 + 32LL))(v26, &v37, 48);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x50,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v18,
      0);
  v19 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, __int64))(*(_QWORD *)v26 + 40LL))(v26, v42, 48);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x51,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v19,
      0);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    a2,
    *((char **)&v42[0] + 1),
    0xFFFFFFFFFFFFFFFFuLL,
    v20);
  v31 = 4;
  if ( !*a2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xFF8,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  anonymous_namespace_::SyncmlResultsClear(v42);
  std::vector<tagSyncMLAttribute>::~vector<tagSyncMLAttribute>(&v27);
  v22 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v10 )
    CoUninitialize();
  return a2;
}

```

## disassembly

```asm
0x140041cc0  mov     [rsp-8+arg_8], rdx
0x140041cc5  push    rbp
0x140041cc6  push    rbx
0x140041cc7  push    rsi
0x140041cc8  push    rdi
0x140041cc9  push    r12
0x140041ccb  push    r14
0x140041ccd  lea     rbp, [rsp-1Fh]
0x140041cd2  sub     rsp, 0F8h
0x140041cd9  mov     rsi, r9
0x140041cdc  mov     r14, r8
0x140041cdf  mov     rdi, rdx
0x140041ce2  mov     [rbp+47h+var_C0], 0
0x140041ce9  xor     ebx, ebx
0x140041ceb  xor     edx, edx; dwCoInit
0x140041ced  xor     ecx, ecx; pvReserved
0x140041cef  call    cs:__imp_CoInitializeEx
0x140041cf5  lea     r12d, [rbx+1]
0x140041cf9  test    eax, eax
0x140041cfb  cmovns  ebx, r12d
0x140041cff  mov     [rbp+47h+var_BC], ebx
0x140041d02  mov     rcx, [rbp+4Fh]; this
0x140041d06  js      loc_140041F8C
0x140041d0c  mov     [rsp+120h+var_F0], 0
0x140041d15  lea     rax, [rsp+120h+var_F0]
0x140041d1a  mov     qword ptr [rsp+120h+ppv], rax; int
0x140041d1f  lea     r9, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd; riid
0x140041d26  mov     r8d, r12d; dwClsContext
0x140041d29  xor     edx, edx; pUnkOuter
0x140041d2b  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x140041d32  call    cs:__imp_CoCreateInstance
0x140041d38  mov     rcx, [rbp+4Fh]; this
0x140041d3c  test    eax, eax
0x140041d3e  js      loc_140041FA1
0x140041d44  xorps   xmm0, xmm0
0x140041d47  movdqu  [rsp+120h+var_E8], xmm0
0x140041d4d  mov     [rsp+120h+var_D8], 0
0x140041d56  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x140041d5d  mov     [rsp+120h+var_D0], rax
0x140041d62  mov     [rsp+120h+var_C8], r14
0x140041d67  lea     r8, [rsp+120h+var_D0]
0x140041d6c  xor     edx, edx
0x140041d6e  lea     rcx, [rsp+120h+var_E8]
0x140041d73  call    ??$_Emplace_reallocate@UtagSyncMLAttribute@@@?$vector@UtagSyncMLAttribute@@V?$allocator@UtagSyncMLAttribute@@@std@@@std@@AEAAPEAUtagSyncMLAttribute@@QEAU2@$$QEAU2@@Z; std::vector<tagSyncMLAttribute>::_Emplace_reallocate<tagSyncMLAttribute>(tagSyncMLAttribute * const,tagSyncMLAttribute &&)
0x140041d78  test    rsi, rsi
0x140041d7b  jz      short loc_140041DB8
0x140041d7d  lea     rax, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x140041d84  mov     [rsp+120h+var_D0], rax
0x140041d89  mov     [rsp+120h+var_C8], rsi
0x140041d8e  mov     rdx, qword ptr [rsp+120h+var_E8+8]
0x140041d93  cmp     rdx, [rsp+120h+var_D8]
0x140041d98  jz      short loc_140041DA9
0x140041d9a  mov     [rdx], rax
0x140041d9d  mov     [rdx+8], rsi
0x140041da1  add     qword ptr [rsp+120h+var_E8+8], 10h
0x140041da7  jmp     short loc_140041DB8
0x140041da9  lea     r8, [rsp+120h+var_D0]
0x140041dae  lea     rcx, [rsp+120h+var_E8]
0x140041db3  call    ??$_Emplace_reallocate@UtagSyncMLAttribute@@@?$vector@UtagSyncMLAttribute@@V?$allocator@UtagSyncMLAttribute@@@std@@@std@@AEAAPEAUtagSyncMLAttribute@@QEAU2@$$QEAU2@@Z; std::vector<tagSyncMLAttribute>::_Emplace_reallocate<tagSyncMLAttribute>(tagSyncMLAttribute * const,tagSyncMLAttribute &&)
0x140041db8  lea     rcx, aDynamoContexti; "DYNAMO::CONTEXTID"
0x140041dbf  mov     [rsp+120h+var_D0], rcx
0x140041dc4  mov     rax, [rbp+47h+arg_28]
0x140041dc8  mov     [rsp+120h+var_C8], rax
0x140041dcd  mov     rdx, qword ptr [rsp+120h+var_E8+8]
0x140041dd2  cmp     rdx, [rsp+120h+var_D8]
0x140041dd7  jz      short loc_140041DF0
0x140041dd9  mov     [rdx], rcx
0x140041ddc  mov     [rdx+8], rax
0x140041de0  mov     rax, qword ptr [rsp+120h+var_E8+8]
0x140041de5  add     rax, 10h
0x140041de9  mov     qword ptr [rsp+120h+var_E8+8], rax
0x140041dee  jmp     short loc_140041E04
0x140041df0  lea     r8, [rsp+120h+var_D0]
0x140041df5  lea     rcx, [rsp+120h+var_E8]
0x140041dfa  call    ??$_Emplace_reallocate@UtagSyncMLAttribute@@@?$vector@UtagSyncMLAttribute@@V?$allocator@UtagSyncMLAttribute@@@std@@@std@@AEAAPEAUtagSyncMLAttribute@@QEAU2@$$QEAU2@@Z; std::vector<tagSyncMLAttribute>::_Emplace_reallocate<tagSyncMLAttribute>(tagSyncMLAttribute * const,tagSyncMLAttribute &&)
0x140041dff  mov     rax, qword ptr [rsp+120h+var_E8+8]
0x140041e04  mov     [rbp+47h+var_B8], 1
0x140041e0c  mov     [rbp+47h+var_A0], 0
0x140041e13  mov     [rbp+47h+var_B0], r14
0x140041e17  lea     rcx, aSyncmlpackproc; "SyncmlPackProcessor"
0x140041e1e  mov     [rbp+47h+var_A8], rcx
0x140041e22  mov     rcx, qword ptr [rsp+120h+var_E8]
0x140041e27  sub     rax, rcx
0x140041e2a  sar     rax, 4
0x140041e2e  mov     edx, 0FFFFFFFFh
0x140041e33  cmp     rax, rdx
0x140041e36  mov     [rbp+47h+var_9C], eax
0x140041e39  jbe     short loc_140041E3E
0x140041e3b  mov     [rbp+47h+var_9C], edx
0x140041e3e  cmp     rdx, rax
0x140041e41  sbb     r9d, r9d
0x140041e44  and     r9d, 80070216h; char *
0x140041e4b  mov     r10, [rbp+4Fh]
0x140041e4f  cmp     rax, rdx
0x140041e52  ja      loc_140041FB6
0x140041e58  mov     [rbp+47h+var_98], rcx
0x140041e5c  mov     rcx, [rsp+120h+var_F0]
0x140041e61  mov     rax, [rcx]
0x140041e64  mov     r8d, 28h ; '('
0x140041e6a  lea     rdx, [rbp+47h+var_B8]
0x140041e6e  mov     rax, [rax+18h]
0x140041e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041e77  mov     rcx, [rbp+4Fh]; this
0x140041e7b  test    eax, eax
0x140041e7d  js      loc_140041FCB
0x140041e83  xorps   xmm0, xmm0
0x140041e86  movdqu  [rbp+47h+var_80], xmm0
0x140041e8b  xorps   xmm1, xmm1
0x140041e8e  movdqu  [rbp+47h+var_70], xmm1
0x140041e93  mov     [rbp+47h+var_88], r12d
0x140041e97  mov     rax, [rbp+47h+arg_20]
0x140041e9b  mov     [rbp+47h+var_90], rax
0x140041e9f  mov     [rbp+47h+var_84], r12d
0x140041ea3  movups  [rbp+47h+var_60], xmm0
0x140041ea7  movups  [rbp+47h+var_50], xmm0
0x140041eab  movups  [rbp+47h+var_40], xmm0
0x140041eaf  mov     rcx, [rsp+120h+var_F0]
0x140041eb4  mov     rax, [rcx]
0x140041eb7  mov     qword ptr [rsp+120h+ppv], 0; int
0x140041ec0  xor     r9d, r9d
0x140041ec3  lea     esi, [r9+30h]
0x140041ec7  mov     r8d, esi
0x140041eca  lea     rdx, [rbp+47h+var_90]
0x140041ece  mov     rax, [rax+20h]
0x140041ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041ed7  mov     rcx, [rbp+4Fh]; this
0x140041edb  test    eax, eax
0x140041edd  js      loc_140041FE0
0x140041ee3  mov     rcx, [rsp+120h+var_F0]
0x140041ee8  mov     rax, [rcx]
0x140041eeb  mov     r8d, esi
0x140041eee  lea     rdx, [rbp+47h+var_60]
0x140041ef2  mov     rax, [rax+28h]
0x140041ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041efb  mov     rcx, [rbp+4Fh]; this
0x140041eff  test    eax, eax
0x140041f01  js      loc_140041FF5
0x140041f07  or      r8, 0FFFFFFFFFFFFFFFFh
0x140041f0b  mov     rdx, qword ptr [rbp+47h+var_60+8]
0x140041f0f  mov     rcx, rdi
0x140041f12  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140041f17  mov     [rbp+47h+var_C0], 4
0x140041f1e  mov     rcx, [rbp+4Fh]; this
0x140041f22  cmp     qword ptr [rdi], 0
0x140041f26  jz      short loc_140041F7A
0x140041f28  lea     rcx, [rbp+47h+var_60]
0x140041f2c  call    _anonymous_namespace___SyncmlResultsClear
0x140041f31  nop
0x140041f32  lea     rcx, [rsp+120h+var_E8]
0x140041f37  call    ??1?$vector@UtagSyncMLAttribute@@V?$allocator@UtagSyncMLAttribute@@@std@@@std@@QEAA@XZ; std::vector<tagSyncMLAttribute>::~vector<tagSyncMLAttribute>(void)
0x140041f3c  nop
0x140041f3d  mov     rcx, [rsp+120h+var_F0]
0x140041f42  test    rcx, rcx
0x140041f45  jz      short loc_140041F5D
0x140041f47  mov     [rsp+120h+var_F0], 0
0x140041f50  mov     rax, [rcx]
0x140041f53  mov     rax, [rax+10h]
0x140041f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f5c  nop
0x140041f5d  test    ebx, ebx
0x140041f5f  jz      short loc_140041F67
0x140041f61  call    cs:__imp_CoUninitialize
0x140041f67  mov     rax, rdi
0x140041f6a  add     rsp, 0F8h
0x140041f71  pop     r14
0x140041f73  pop     r12
0x140041f75  pop     rdi
0x140041f76  pop     rsi
0x140041f77  pop     rbx
0x140041f78  pop     rbp
0x140041f79  retn
0x140041f7a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140041f81  mov     edx, 0FF8h; void *
0x140041f86  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140041f8c  mov     r9d, eax; char *
0x140041f8f  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041f96  mov     edx, 32h ; '2'; void *
0x140041f9b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041fa1  mov     r9d, eax; char *
0x140041fa4  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041fab  mov     edx, 35h ; '5'; void *
0x140041fb0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041fb6  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041fbd  mov     edx, 45h ; 'E'; void *
0x140041fc2  mov     rcx, r10; this
0x140041fc5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041fcb  mov     r9d, eax; char *
0x140041fce  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041fd5  mov     edx, 48h ; 'H'; void *
0x140041fda  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041fe0  mov     r9d, eax; char *
0x140041fe3  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041fea  mov     edx, 50h ; 'P'; void *
0x140041fef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041ff5  mov     r9d, eax; char *
0x140041ff8  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041fff  mov     edx, 51h ; 'Q'; void *
0x140042004  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

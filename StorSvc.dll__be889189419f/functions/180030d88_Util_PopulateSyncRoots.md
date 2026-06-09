# Util::PopulateSyncRoots

- ea: `0x180030d88`
- end: `0x180031076`
- name: `Util::PopulateSyncRoots`
- size: `750`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003253c`

## callees

- `0x18000d030`
- `0x180012734`
- `0x180014a00`
- `0x1800176ec`
- `0x180018d54`
- `0x180019bc4`
- `0x18001c208`
- `0x18001f634`
- `0x18001fcac`
- `0x18002ce80`
- `0x18002e284`
- `0x18002e740`
- `0x18002e9d8`
- `0x180030d88`
- `0x18008a010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180030ff6`
- `RPCRT4!RpcRevertToSelf` at `0x180030ff6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030df6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030df6`

## string_xrefs

- `0x180030e23`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Util::PopulateSyncRoots(__int64 a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  unsigned int i; // esi
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, __int64 *); // rbx
  LPVOID v12; // rdi
  int (__fastcall *v13)(LPVOID, __int64, _QWORD, __int64 *); // rbx
  bool v14; // zf
  int ppv; // [rsp+20h] [rbp-E0h]
  _BYTE v17[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  _BYTE *v29; // [rsp+88h] [rbp-78h]
  _BYTE v30[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v32; // [rsp+C0h] [rbp-40h]
  _BYTE v33[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[48]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v20 = 0;
  v22 = 0;
  v19 = 0;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  v2 = CoCreateInstance(&stru_1800956D8, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v20);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 1969;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    goto LABEL_19;
  }
  v2 = Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(&v20, &v22);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 1970;
    goto LABEL_5;
  }
  v5 = v22;
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 24LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  v2 = v6(v5, &v19);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 1971;
    goto LABEL_5;
  }
  v2 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 24LL))(v19, &v18);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 1972;
    goto LABEL_5;
  }
  for ( i = 0; i < v18; ++i )
  {
    v21 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v8 = v19;
    v9 = *(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v19 + 32LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
    if ( v9(v8, i, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v21) >= 0 )
    {
      v10 = v21;
      v11 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 24LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
      v24 = -1;
      v25 = -1;
      if ( v11(v10, &v23) >= 0 )
      {
        AutoRpcImpersonateClient(v17);
        v12 = v20;
        v13 = *(int (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 136LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
        v27 = -1;
        v28 = -1;
        if ( v13(v12, v23, 0, &v26) >= 0 )
        {
          std::wstring::wstring(v31);
          std::wstring::assign(v31, v23);
          v32 = 0;
          std::wstring::wstring(v33, v26);
          v29 = v34;
          std::wstring::wstring(v34, v31);
          v34[32] = v32;
          std::_Hash<std::_Umap_traits<std::wstring,SYNC_ROOT_INFO,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SYNC_ROOT_INFO>>,0>>::emplace<std::pair<std::wstring const,SYNC_ROOT_INFO>>(
            a1,
            v30,
            v33);
          std::pair<std::wstring const,SYNC_ROOT_INFO>::~pair<std::wstring const,SYNC_ROOT_INFO>(v33);
          std::wstring::_Tidy_deallocate(v31);
        }
        v14 = v17[0] == 0;
        v17[0] = 0;
        if ( !v14 )
          RpcRevertToSelf();
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  }
  v3 = 0;
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  return v3;
}

```

## disassembly

```asm
0x180030d88  mov     [rsp-8+arg_8], rbx
0x180030d8d  mov     [rsp-8+arg_10], rsi
0x180030d92  push    rbp
0x180030d93  push    rdi
0x180030d94  push    r12
0x180030d96  push    r14
0x180030d98  push    r15
0x180030d9a  lea     rbp, [rsp-30h]
0x180030d9f  sub     rsp, 130h
0x180030da6  mov     rax, cs:__security_cookie
0x180030dad  xor     rax, rsp
0x180030db0  mov     [rbp+50h+var_30], rax
0x180030db4  mov     r14, rcx
0x180030db7  xor     r15d, r15d
0x180030dba  mov     [rsp+150h+var_110], r15
0x180030dbf  mov     [rsp+150h+var_100], r15
0x180030dc4  mov     [rsp+150h+var_118], r15
0x180030dc9  mov     [rsp+150h+var_11C], r15d
0x180030dce  lea     rcx, [rsp+150h+var_110]
0x180030dd3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030dd8  lea     rax, [rsp+150h+var_110]
0x180030ddd  mov     qword ptr [rsp+150h+ppv], rax; int
0x180030de2  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180030de9  xor     edx, edx; pUnkOuter
0x180030deb  lea     r8d, [r15+1]; dwClsContext
0x180030def  lea     rcx, stru_1800956D8; rclsid
0x180030df6  call    cs:__imp_CoCreateInstance
0x180030dfc  mov     ebx, eax
0x180030dfe  test    eax, eax
0x180030e00  jns     short loc_180030E09
0x180030e02  mov     edx, 7B1h
0x180030e07  jmp     short loc_180030E23
0x180030e09  lea     rdx, [rsp+150h+var_100]
0x180030e0e  lea     rcx, [rsp+150h+var_110]
0x180030e13  call    ??$As@UISyncRootManagerPriv@@@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISyncRootManagerPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManagerPriv>>)
0x180030e18  mov     ebx, eax
0x180030e1a  test    eax, eax
0x180030e1c  jns     short loc_180030E3B
0x180030e1e  mov     edx, 7B2h; void *
0x180030e23  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030e2a  mov     r9d, eax; char *
0x180030e2d  mov     rcx, [rbp+58h]; this
0x180030e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030e36  jmp     loc_18003102C
0x180030e3b  mov     rdi, [rsp+150h+var_100]
0x180030e40  mov     rax, [rdi]
0x180030e43  mov     rbx, [rax+18h]
0x180030e47  lea     rcx, [rsp+150h+var_118]
0x180030e4c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030e51  lea     rdx, [rsp+150h+var_118]
0x180030e56  mov     rcx, rdi
0x180030e59  mov     rax, rbx
0x180030e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e61  mov     ebx, eax
0x180030e63  test    eax, eax
0x180030e65  jns     short loc_180030E6E
0x180030e67  mov     edx, 7B3h
0x180030e6c  jmp     short loc_180030E23
0x180030e6e  mov     rcx, [rsp+150h+var_118]
0x180030e73  mov     rax, [rcx]
0x180030e76  lea     rdx, [rsp+150h+var_11C]
0x180030e7b  mov     rax, [rax+18h]
0x180030e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e84  mov     ebx, eax
0x180030e86  test    eax, eax
0x180030e88  jns     short loc_180030E91
0x180030e8a  mov     edx, 7B4h
0x180030e8f  jmp     short loc_180030E23
0x180030e91  mov     esi, r15d
0x180030e94  cmp     [rsp+150h+var_11C], r15d
0x180030e99  jbe     loc_180031029
0x180030e9f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180030ea3  mov     [rsp+150h+var_108], r15
0x180030ea8  mov     [rsp+150h+var_F8], r15
0x180030ead  mov     [rsp+150h+var_F0], r15
0x180030eb2  mov     [rsp+150h+var_E8], r15
0x180030eb7  mov     [rsp+150h+var_E0], r15
0x180030ebc  mov     [rsp+150h+var_D8], r15
0x180030ec1  mov     [rbp+50h+var_D0], r15
0x180030ec5  mov     rdi, [rsp+150h+var_118]
0x180030eca  mov     rax, [rdi]
0x180030ecd  mov     rbx, [rax+20h]
0x180030ed1  lea     rcx, [rsp+150h+var_108]
0x180030ed6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030edb  lea     r9, [rsp+150h+var_108]
0x180030ee0  lea     r8, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86
0x180030ee7  mov     edx, esi
0x180030ee9  mov     rcx, rdi
0x180030eec  mov     rax, rbx
0x180030eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ef4  test    eax, eax
0x180030ef6  js      loc_180030FFD
0x180030efc  mov     rdi, [rsp+150h+var_108]
0x180030f01  mov     rax, [rdi]
0x180030f04  mov     rbx, [rax+18h]
0x180030f08  lea     rcx, [rsp+150h+var_F8]
0x180030f0d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030f12  mov     [rsp+150h+var_F0], r12
0x180030f17  mov     [rsp+150h+var_E8], r12
0x180030f1c  lea     rdx, [rsp+150h+var_F8]
0x180030f21  mov     rcx, rdi
0x180030f24  mov     rax, rbx
0x180030f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f2c  test    eax, eax
0x180030f2e  js      loc_180030FFD
0x180030f34  lea     rcx, [rsp+150h+var_120]
0x180030f39  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x180030f3e  nop
0x180030f3f  mov     rdi, [rsp+150h+var_110]
0x180030f44  mov     rax, [rdi]
0x180030f47  mov     rbx, [rax+88h]
0x180030f4e  lea     rcx, [rsp+150h+var_E0]
0x180030f53  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030f58  mov     [rsp+150h+var_D8], r12
0x180030f5d  mov     [rbp+50h+var_D0], r12
0x180030f61  lea     r9, [rsp+150h+var_E0]
0x180030f66  xor     r8d, r8d
0x180030f69  mov     rdx, [rsp+150h+var_F8]
0x180030f6e  mov     rcx, rdi
0x180030f71  mov     rax, rbx
0x180030f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f79  test    eax, eax
0x180030f7b  js      short loc_180030FE9
0x180030f7d  lea     rcx, [rbp+50h+var_B0]
0x180030f81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180030f86  nop
0x180030f87  mov     rdx, [rsp+150h+var_F8]
0x180030f8c  lea     rcx, [rbp+50h+var_B0]
0x180030f90  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180030f95  mov     [rbp+50h+var_90], r15b
0x180030f99  mov     rdx, [rsp+150h+var_E0]
0x180030f9e  lea     rcx, [rbp+50h+var_80]
0x180030fa2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030fa7  nop
0x180030fa8  lea     rax, [rbp+50h+var_60]
0x180030fac  mov     [rbp+50h+var_C8], rax
0x180030fb0  lea     rdx, [rbp+50h+var_B0]
0x180030fb4  lea     rcx, [rbp+50h+var_60]
0x180030fb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030fbd  nop
0x180030fbe  mov     al, [rbp+50h+var_90]
0x180030fc1  mov     [rbp+50h+var_40], al
0x180030fc4  lea     r8, [rbp+50h+var_80]
0x180030fc8  lea     rdx, [rbp+50h+var_C0]
0x180030fcc  mov     rcx, r14
0x180030fcf  call    ??$emplace@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,SYNC_ROOT_INFO,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SYNC_ROOT_INFO>>,0>>::emplace<std::pair<std::wstring const,SYNC_ROOT_INFO>>(std::pair<std::wstring const,SYNC_ROOT_INFO> &&)
0x180030fd4  nop
0x180030fd5  lea     rcx, [rbp+50h+var_80]
0x180030fd9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@@std@@QEAA@XZ; std::pair<std::wstring const,SYNC_ROOT_INFO>::~pair<std::wstring const,SYNC_ROOT_INFO>(void)
0x180030fde  nop
0x180030fdf  lea     rcx, [rbp+50h+var_B0]
0x180030fe3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030fe8  nop
0x180030fe9  mov     al, [rsp+150h+var_120]
0x180030fed  test    al, al
0x180030fef  mov     [rsp+150h+var_120], r15b
0x180030ff4  jz      short loc_180030FFD
0x180030ff6  call    cs:__imp_RpcRevertToSelf
0x180030ffc  nop
0x180030ffd  lea     rcx, [rsp+150h+var_E0]
0x180031002  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031007  nop
0x180031008  lea     rcx, [rsp+150h+var_F8]
0x18003100d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031012  nop
0x180031013  lea     rcx, [rsp+150h+var_108]
0x180031018  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003101d  inc     esi
0x18003101f  cmp     esi, [rsp+150h+var_11C]
0x180031023  jb      loc_180030EA3
0x180031029  mov     ebx, r15d
0x18003102c  lea     rcx, [rsp+150h+var_118]
0x180031031  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031036  nop
0x180031037  lea     rcx, [rsp+150h+var_100]
0x18003103c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031041  nop
0x180031042  lea     rcx, [rsp+150h+var_110]
0x180031047  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003104c  mov     eax, ebx
0x18003104e  mov     rcx, [rbp+50h+var_30]
0x180031052  xor     rcx, rsp; StackCookie
0x180031055  call    __security_check_cookie
0x18003105a  lea     r11, [rsp+150h+var_20]
0x180031062  mov     rbx, [r11+38h]
0x180031066  mov     rsi, [r11+40h]
0x18003106a  mov     rsp, r11
0x18003106d  pop     r15
0x18003106f  pop     r14
0x180031071  pop     r12
0x180031073  pop     rdi
0x180031074  pop     rbp
0x180031075  retn
```

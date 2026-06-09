# UiaManagerImpl::RegisterCrossMachineHwndHost(__MIDL___MIDL_itf_uiamanager_0000_0030_0001,__MIDL___MIDL_itf_uiamanager_0000_0025_0002)

- ea: `0x18006fa80`
- end: `0x18006fcc7`
- name: `?RegisterCrossMachineHwndHost@UiaManagerImpl@@UEAAJU__MIDL___MIDL_itf_uiamanager_0000_0030_0001@@U__MIDL___MIDL_itf_uiamanager_0000_0025_0002@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c7f0`
- `0x18000dc9c`
- `0x1800114c4`
- `0x180018868`
- `0x180018978`
- `0x1800189fc`
- `0x180031540`
- `0x18003c6c4`
- `0x180043680`
- `0x180044188`
- `0x18006f684`
- `0x18006fa80`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18006fc35`
- `msvcp_win!_Mtx_unlock` at `0x18006fc35`

## string_xrefs

- `0x18006fc66`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006fc7d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006fc94`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006fcb4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UiaManagerImpl::RegisterCrossMachineHwndHost(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int128 v10; // xmm1
  const char *v11; // r9
  __int64 result; // rax
  char *v13; // [rsp+20h] [rbp-B8h]
  __int64 v14; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v15[16]; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+48h] [rbp-90h] BYREF
  __int64 v17; // [rsp+58h] [rbp-80h]
  __int128 v18; // [rsp+60h] [rbp-78h] BYREF
  __int128 v19; // [rsp+70h] [rbp-68h]
  __int64 *v20; // [rsp+80h] [rbp-58h]
  __int64 v21; // [rsp+88h] [rbp-50h]
  _QWORD *v22; // [rsp+90h] [rbp-48h]
  __int64 v23; // [rsp+98h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    if ( !UiaManagerSecurityUtils::IsAccessAllowed(1) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x226,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80070005LL,
        (int)v13);
    if ( !*a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80070057LL,
        (int)v13);
    if ( !memcmp_0(a2 + 1, &GUID_NULL, 0x10u) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x229,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80070057LL,
        (int)v13);
    v6 = UiaManagerTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(v14) = *(_DWORD *)a2;
      v22 = a2 + 1;
      v23 = 16;
      v20 = &v14;
      v21 = 4;
      tlgWriteTransfer_EventWriteTransfer(v6, byte_1800AD71B, 0, 0, 4, &v18, v14);
    }
    if ( *a3 )
    {
      switch ( *a3 )
      {
        case 1:
          LODWORD(v18) = a3[2];
          LOBYTE(v19) = 0;
          break;
        case 2:
          v18 = *(_OWORD *)(a3 + 2);
          LOBYTE(v19) = 1;
          break;
        case 3:
          *(_QWORD *)&v18 = *((_QWORD *)a3 + 1);
          LOBYTE(v19) = 2;
          break;
        default:
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
            "unreachable",
            v13);
      }
      BYTE8(v19) = 1;
    }
    else
    {
      BYTE8(v19) = 0;
    }
    v16 = *(_OWORD *)(a2 + 1);
    v17 = *a2;
    v14 = a1 + 456;
    std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 456));
    v8 = std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>::operator()<std::pair<_GUID,HWND__ *>>(
           v7,
           &v16);
    v9 = std::_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>::_Find<std::pair<_GUID,HWND__ *>>(
           a1 + 536,
           &v16,
           v8);
    if ( v9 == *(_QWORD *)(a1 + 544) )
    {
      std::_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>::emplace<std::pair<_GUID,HWND__ *> const &,std::optional<ProviderEntrypointId>>(
        a1 + 536,
        v15,
        &v16,
        &v18);
    }
    else
    {
      v10 = v19;
      *(_OWORD *)(v9 + 40) = v18;
      *(_OWORD *)(v9 + 56) = v10;
    }
    _Mtx_unlock((_Mtx_t)(a1 + 456));
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x237,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18006fa80  push    rbx
0x18006fa82  push    rsi
0x18006fa83  push    rdi
0x18006fa84  push    r14
0x18006fa86  sub     rsp, 0B8h
0x18006fa8d  mov     rax, cs:__security_cookie
0x18006fa94  xor     rax, rsp
0x18006fa97  mov     [rsp+0D8h+var_38], rax
0x18006fa9f  mov     rbx, r8
0x18006faa2  mov     rdi, rdx
0x18006faa5  mov     r14, rcx
0x18006faa8  mov     ecx, 1
0x18006faad  call    ?IsAccessAllowed@UiaManagerSecurityUtils@@CA_NW4AppContainerAccessCapability@1@@Z; UiaManagerSecurityUtils::IsAccessAllowed(UiaManagerSecurityUtils::AppContainerAccessCapability)
0x18006fab2  mov     rcx, [rsp+0D8h]; this
0x18006faba  test    al, al
0x18006fabc  jz      loc_18006FC60
0x18006fac2  mov     rcx, [rsp+0D8h]; this
0x18006faca  cmp     qword ptr [rdi], 0
0x18006face  jz      loc_18006FC77
0x18006fad4  lea     rsi, [rdi+8]
0x18006fad8  mov     r8d, 10h; Size
0x18006fade  lea     rdx, GUID_NULL; Buf2
0x18006fae5  mov     rcx, rsi; Buf1
0x18006fae8  call    memcmp_0
0x18006faed  test    eax, eax
0x18006faef  setz    al
0x18006faf2  mov     rcx, [rsp+0D8h]; this
0x18006fafa  test    al, al
0x18006fafc  jnz     loc_18006FC8E
0x18006fb02  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x18006fb07  mov     ecx, [rax]
0x18006fb09  mov     edx, 4
0x18006fb0e  cmp     ecx, edx
0x18006fb10  jbe     short loc_18006FB64
0x18006fb12  mov     ecx, [rdi]
0x18006fb14  mov     dword ptr [rsp+0D8h+var_A8], ecx
0x18006fb18  mov     [rsp+0D8h+var_48], rsi
0x18006fb20  mov     [rsp+0D8h+var_40], 10h
0x18006fb2c  lea     rcx, [rsp+0D8h+var_A8]
0x18006fb31  mov     [rsp+0D8h+var_58], rcx
0x18006fb39  mov     [rsp+0D8h+var_50], rdx
0x18006fb41  lea     rcx, [rsp+0D8h+var_78]
0x18006fb46  mov     [rsp+0D8h+var_B0], rcx
0x18006fb4b  mov     dword ptr [rsp+0D8h+var_B8], edx; char *
0x18006fb4f  xor     r9d, r9d
0x18006fb52  xor     r8d, r8d
0x18006fb55  lea     rdx, byte_1800AD71B
0x18006fb5c  mov     rcx, rax
0x18006fb5f  call    _tlgWriteTransfer_EventWriteTransfer
0x18006fb64  mov     ecx, [rbx]
0x18006fb66  test    ecx, ecx
0x18006fb68  jz      short loc_18006FBB9
0x18006fb6a  sub     ecx, 1
0x18006fb6d  jz      short loc_18006FBA6
0x18006fb6f  sub     ecx, 1
0x18006fb72  jz      short loc_18006FB8D
0x18006fb74  cmp     ecx, 1
0x18006fb77  jnz     loc_18006FCA5
0x18006fb7d  mov     rax, [rbx+8]
0x18006fb81  mov     qword ptr [rsp+0D8h+var_78], rax
0x18006fb86  mov     byte ptr [rsp+0D8h+var_68], 2
0x18006fb8b  jmp     short loc_18006FBB2
0x18006fb8d  mov     rax, [rbx+8]
0x18006fb91  mov     qword ptr [rsp+0D8h+var_78], rax
0x18006fb96  mov     rax, [rbx+10h]
0x18006fb9a  mov     qword ptr [rsp+0D8h+var_78+8], rax
0x18006fb9f  mov     byte ptr [rsp+0D8h+var_68], 1
0x18006fba4  jmp     short loc_18006FBB2
0x18006fba6  mov     eax, [rbx+8]
0x18006fba9  mov     dword ptr [rsp+0D8h+var_78], eax
0x18006fbad  mov     byte ptr [rsp+0D8h+var_68], 0
0x18006fbb2  mov     byte ptr [rsp+0D8h+var_68+8], 1
0x18006fbb7  jmp     short loc_18006FBBE
0x18006fbb9  mov     byte ptr [rsp+0D8h+var_68+8], 0
0x18006fbbe  lea     rbx, [r14+1C8h]
0x18006fbc5  movups  xmm0, xmmword ptr [rsi]
0x18006fbc8  movdqu  [rsp+0D8h+var_90], xmm0
0x18006fbce  mov     rax, [rdi]
0x18006fbd1  mov     [rsp+0D8h+var_80], rax
0x18006fbd6  mov     [rsp+0D8h+var_A8], rbx
0x18006fbdb  mov     rcx, rbx; this
0x18006fbde  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18006fbe3  nop
0x18006fbe4  lea     rdx, [rsp+0D8h+var_90]
0x18006fbe9  call    ??$?RU?$pair@U_GUID@@PEAUHWND__@@@std@@@?$_Uhash_compare@U?$pair@U_GUID@@PEAUHWND__@@@std@@U?$hash@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@U?$equal_to@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@@std@@QEBA_KAEBU?$pair@U_GUID@@PEAUHWND__@@@1@@Z; std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>::operator()<std::pair<_GUID,HWND__ *>>(std::pair<_GUID,HWND__ *> const &)
0x18006fbee  mov     r8, rax
0x18006fbf1  lea     rdx, [rsp+0D8h+var_90]
0x18006fbf6  lea     rcx, [rbx+50h]
0x18006fbfa  call    ??$_Find@U?$pair@U_GUID@@PEAUHWND__@@@std@@@?$_Hash@V?$_Umap_traits@U?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@V?$_Uhash_compare@U?$pair@U_GUID@@PEAUHWND__@@@std@@U?$hash@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@U?$equal_to@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@@2@V?$allocator@U?$pair@$$CBU?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBU?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@@std@@PEAX@1@AEBU?$pair@U_GUID@@PEAUHWND__@@@1@_K@Z; std::_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>::_Find<std::pair<_GUID,HWND__ *>>(std::pair<_GUID,HWND__ *> const &,unsigned __int64)
0x18006fbff  cmp     rax, [rbx+58h]
0x18006fc03  jz      short loc_18006FC19
0x18006fc05  movups  xmm0, [rsp+0D8h+var_78]
0x18006fc0a  movups  xmm1, [rsp+0D8h+var_68]
0x18006fc0f  movups  xmmword ptr [rax+28h], xmm0
0x18006fc13  movups  xmmword ptr [rax+38h], xmm1
0x18006fc17  jmp     short loc_18006FC32
0x18006fc19  lea     r9, [rsp+0D8h+var_78]
0x18006fc1e  lea     r8, [rsp+0D8h+var_90]
0x18006fc23  lea     rdx, [rsp+0D8h+var_A0]
0x18006fc28  lea     rcx, [rbx+50h]
0x18006fc2c  call    ??$emplace@AEBU?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@@?$_Hash@V?$_Umap_traits@U?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@V?$_Uhash_compare@U?$pair@U_GUID@@PEAUHWND__@@@std@@U?$hash@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@U?$equal_to@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@@2@V?$allocator@U?$pair@$$CBU?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@U_GUID@@PEAUHWND__@@@1@$$QEAV?$optional@VProviderEntrypointId@@@1@@Z; std::_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>::emplace<std::pair<_GUID,HWND__ *> const &,std::optional<ProviderEntrypointId>>(std::pair<_GUID,HWND__ *> const &,std::optional<ProviderEntrypointId> &&)
0x18006fc31  nop
0x18006fc32  mov     rcx, rbx; _Mtx_t
0x18006fc35  call    cs:__imp__Mtx_unlock
0x18006fc3b  xor     eax, eax
0x18006fc3d  jmp     short loc_18006FC43
0x18006fc3f  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18006fc43  mov     rcx, [rsp+0D8h+var_38]
0x18006fc4b  xor     rcx, rsp; StackCookie
0x18006fc4e  call    __security_check_cookie
0x18006fc53  add     rsp, 0B8h
0x18006fc5a  pop     r14
0x18006fc5c  pop     rdi
0x18006fc5d  pop     rsi
0x18006fc5e  pop     rbx
0x18006fc5f  retn
0x18006fc60  mov     r9d, 80070005h; char *
0x18006fc66  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006fc6d  mov     edx, 226h; void *
0x18006fc72  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fc77  mov     r9d, 80070057h; char *
0x18006fc7d  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006fc84  mov     edx, 228h; void *
0x18006fc89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fc8e  mov     r9d, 80070057h; char *
0x18006fc94  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006fc9b  mov     edx, 229h; void *
0x18006fca0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fca5  mov     rcx, [rsp+0D8h]; this
0x18006fcad  lea     r9, aUnreachable; "unreachable"
0x18006fcb4  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006fcbb  mov     edx, 7Ch ; '|'; void *
0x18006fcc0  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```

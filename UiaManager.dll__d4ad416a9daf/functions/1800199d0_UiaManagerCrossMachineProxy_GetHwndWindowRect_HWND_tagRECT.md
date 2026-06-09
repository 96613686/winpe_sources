# UiaManagerCrossMachineProxy::GetHwndWindowRect(HWND__ *,tagRECT *)

- ea: `0x1800199d0`
- end: `0x180019bc1`
- name: `?GetHwndWindowRect@UiaManagerCrossMachineProxy@@UEAAJPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `497`
- prototype: `int(UiaManagerCrossMachineProxy *__hidden this, HWND, struct tagRECT *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800078ec`
- `0x18000f968`
- `0x180016c4c`
- `0x180018868`
- `0x1800188c8`
- `0x1800188f8`
- `0x180018930`
- `0x1800199d0`
- `0x18001b698`
- `0x18001eca4`
- `0x180031540`
- `0x180043680`
- `0x180058df8`
- `0x180076c20`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180019aaf`
- `msvcp_win!_Mtx_unlock` at `0x180019ac8`
- `msvcp_win!_Mtx_unlock` at `0x180019aaf`
- `msvcp_win!_Mtx_unlock` at `0x180019ac8`

## string_xrefs

- `0x180019a20`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`
- `0x180019afc`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`
- `0x180019b71`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall UiaManagerCrossMachineProxy::GetHwndWindowRect(
        UiaManagerCrossMachineProxy *this,
        HWND a2,
        struct tagRECT *a3)
{
  UiaManagerCrossMachineProxy *v6; // r15
  char IsFeatureSupportedByPeer; // al
  std::_Mutex_base *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r14
  char v13; // r12
  struct tagRECT v14; // xmm6
  unsigned int HwndWindowRect; // eax
  int v17; // eax
  int v18[2]; // [rsp+20h] [rbp-F8h] BYREF
  _BYTE v19[20]; // [rsp+28h] [rbp-F0h] BYREF
  _BYTE v20[112]; // [rsp+40h] [rbp-D8h] BYREF
  struct tagRECT v21; // [rsp+B0h] [rbp-68h]
  char v22; // [rsp+C0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  *a3 = 0;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
      (const char *)0x80070057LL,
      v18[0]);
  UiaManagerTraceLoggingProvider::CrossMachineProxyGetHwndWindowRect(a2);
  v6 = (UiaManagerCrossMachineProxy *)((char *)this - 48);
  IsFeatureSupportedByPeer = IoDispatcher::IsFeatureSupportedByPeer(*((_QWORD *)this + 5));
  *(_QWORD *)v18 = a2;
  if ( IsFeatureSupportedByPeer )
  {
    v8 = (UiaManagerCrossMachineProxy *)((char *)this + 528);
    std::_Mutex_base::lock(v8);
    v10 = std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>::operator()<HWND__ *>(v9, v18);
    v11 = std::_Hash<std::_Umap_traits<HWND__ *,HwndInfoCache::CachedHwndInfo,std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>,std::allocator<std::pair<HWND__ * const,HwndInfoCache::CachedHwndInfo>>,0>>::_Find<HWND__ *>(
            (char *)v8 + 80,
            v18,
            v10);
    v12 = v11;
    if ( v11 == *((_QWORD *)v8 + 11) )
    {
      _Mtx_unlock(v8);
    }
    else
    {
      v13 = 0;
      if ( HwndInfoCache::IsEntryValid((const struct HwndInfoCache::CachedHwndInfo *)(v11 + 24)) )
      {
        v14 = *(struct tagRECT *)(v12 + 144);
        v13 = *(_BYTE *)(v12 + 160);
      }
      else
      {
        v14 = *(struct tagRECT *)v19;
      }
      _Mtx_unlock(v8);
      if ( v13 )
      {
        *a3 = v14;
        return 0;
      }
    }
    UiaManagerCrossMachineProxy::ExecuteGetHwndInfoService(v6, v20, a2);
    if ( !v22 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
        (const char *)0x8000FFFFLL,
        v18[0]);
    *a3 = v21;
    UiaManagerCrossMachineProxy::InsertHwndCacheEntry(v6, a2, (struct HwndInfoPayload *)v20);
    GetHwndInfoService::ResponsePayload::~ResponsePayload((GetHwndInfoService::ResponsePayload *)v20);
  }
  else
  {
    memset(v19, 0, sizeof(v19));
    HwndWindowRect = IoDispatcher::Request<GetHwndWindowRectService>(*((_QWORD *)this + 5), v18, v19);
    v17 = anonymous_namespace_::ValidateResponse(HwndWindowRect, *(unsigned int *)v19);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x41A,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
        (const char *)(unsigned int)v17,
        v18[0]);
    *a3 = *(struct tagRECT *)&v19[4];
  }
  return 0;
}

```

## disassembly

```asm
0x1800199d0  mov     rax, rsp
0x1800199d3  mov     [rax+20h], rbx
0x1800199d7  push    rsi
0x1800199d8  push    rdi
0x1800199d9  push    r12
0x1800199db  push    r14
0x1800199dd  push    r15
0x1800199df  sub     rsp, 0F0h
0x1800199e6  movaps  xmmword ptr [rax-38h], xmm6
0x1800199ea  mov     rax, cs:__security_cookie
0x1800199f1  xor     rax, rsp
0x1800199f4  mov     [rsp+118h+var_48], rax
0x1800199fc  mov     rsi, r8
0x1800199ff  mov     rbx, rdx
0x180019a02  mov     rdi, rcx
0x180019a05  xorps   xmm0, xmm0
0x180019a08  movdqu  xmmword ptr [r8], xmm0
0x180019a0d  mov     rcx, [rsp+118h]; this
0x180019a15  test    rdx, rdx
0x180019a18  jnz     short loc_180019A31
0x180019a1a  mov     r9d, 80070057h; char *
0x180019a20  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x180019a27  mov     edx, 3FEh; void *
0x180019a2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019a31  mov     rcx, rbx; HWND
0x180019a34  call    ?CrossMachineProxyGetHwndWindowRect@UiaManagerTraceLoggingProvider@@SAXPEAUHWND__@@@Z; UiaManagerTraceLoggingProvider::CrossMachineProxyGetHwndWindowRect(HWND__ *)
0x180019a39  lea     r15, [rdi-30h]
0x180019a3d  mov     rcx, [r15+58h]
0x180019a41  call    ?IsFeatureSupportedByPeer@IoDispatcher@@QEBA_NW4PeerVersionDependentFeature@@@Z; IoDispatcher::IsFeatureSupportedByPeer(PeerVersionDependentFeature)
0x180019a46  mov     qword ptr [rsp+118h+var_F8], rbx; int
0x180019a4b  test    al, al
0x180019a4d  jz      loc_180019B36
0x180019a53  add     rdi, 210h
0x180019a5a  mov     rcx, rdi; this
0x180019a5d  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180019a62  lea     rdx, [rsp+118h+var_F8]
0x180019a67  call    ??$?RPEAUHWND__@@@?$_Uhash_compare@PEAUHWND__@@U?$hash@PEAUHWND__@@@std@@U?$equal_to@PEAUHWND__@@@3@@std@@QEBA_KAEBQEAUHWND__@@@Z; std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>::operator()<HWND__ *>(HWND__ * const &)
0x180019a6c  mov     r8, rax
0x180019a6f  lea     rcx, [rdi+50h]
0x180019a73  lea     rdx, [rsp+118h+var_F8]
0x180019a78  call    ??$_Find@PEAUHWND__@@@?$_Hash@V?$_Umap_traits@PEAUHWND__@@UCachedHwndInfo@HwndInfoCache@@V?$_Uhash_compare@PEAUHWND__@@U?$hash@PEAUHWND__@@@std@@U?$equal_to@PEAUHWND__@@@3@@std@@V?$allocator@U?$pair@QEAUHWND__@@UCachedHwndInfo@HwndInfoCache@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@QEAUHWND__@@UCachedHwndInfo@HwndInfoCache@@@std@@PEAX@1@AEBQEAUHWND__@@_K@Z; std::_Hash<std::_Umap_traits<HWND__ *,HwndInfoCache::CachedHwndInfo,std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>,std::allocator<std::pair<HWND__ * const,HwndInfoCache::CachedHwndInfo>>,0>>::_Find<HWND__ *>(HWND__ * const &,unsigned __int64)
0x180019a7d  mov     r14, rax
0x180019a80  cmp     rax, [rdi+58h]
0x180019a84  jz      short loc_180019AC5
0x180019a86  xor     r12b, r12b
0x180019a89  lea     rcx, [rax+18h]; struct HwndInfoCache::CachedHwndInfo *
0x180019a8d  call    ?IsEntryValid@HwndInfoCache@@CA_NAEBUCachedHwndInfo@1@@Z; HwndInfoCache::IsEntryValid(HwndInfoCache::CachedHwndInfo const &)
0x180019a92  test    al, al
0x180019a94  jz      short loc_180019AA7
0x180019a96  movups  xmm6, xmmword ptr [r14+90h]
0x180019a9e  mov     r12b, [r14+0A0h]
0x180019aa5  jmp     short loc_180019AAC
0x180019aa7  movups  xmm6, [rsp+118h+var_F0]
0x180019aac  mov     rcx, rdi; _Mtx_t
0x180019aaf  call    cs:__imp__Mtx_unlock
0x180019ab5  test    r12b, r12b
0x180019ab8  jz      short loc_180019ACE
0x180019aba  movdqu  xmmword ptr [rsi], xmm6
0x180019abe  xor     eax, eax
0x180019ac0  jmp     loc_180019B93
0x180019ac5  mov     rcx, rdi; _Mtx_t
0x180019ac8  call    cs:__imp__Mtx_unlock
0x180019ace  mov     r8, rbx
0x180019ad1  lea     rdx, [rsp+118h+var_D8]
0x180019ad6  mov     rcx, r15
0x180019ad9  call    ?ExecuteGetHwndInfoService@UiaManagerCrossMachineProxy@@AEAA?AUHwndInfoPayload@@PEAUHWND__@@@Z; UiaManagerCrossMachineProxy::ExecuteGetHwndInfoService(HWND__ *)
0x180019ade  nop
0x180019adf  cmp     [rsp+118h+var_58], 0
0x180019ae7  setz    al
0x180019aea  mov     rcx, [rsp+118h]; this
0x180019af2  test    al, al
0x180019af4  jz      short loc_180019B0D
0x180019af6  mov     r9d, 8000FFFFh; char *
0x180019afc  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x180019b03  mov     edx, 40Ch; void *
0x180019b08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019b0d  movaps  xmm0, [rsp+118h+var_68]
0x180019b15  movdqu  xmmword ptr [rsi], xmm0
0x180019b19  lea     r8, [rsp+118h+var_D8]; struct HwndInfoPayload *
0x180019b1e  mov     rdx, rbx; HWND
0x180019b21  mov     rcx, r15; this
0x180019b24  call    ?InsertHwndCacheEntry@UiaManagerCrossMachineProxy@@AEAAXPEAUHWND__@@AEAUHwndInfoPayload@@@Z; UiaManagerCrossMachineProxy::InsertHwndCacheEntry(HWND__ *,HwndInfoPayload &)
0x180019b29  nop
0x180019b2a  lea     rcx, [rsp+118h+var_D8]; this
0x180019b2f  call    ??1ResponsePayload@GetHwndInfoService@@QEAA@XZ; GetHwndInfoService::ResponsePayload::~ResponsePayload(void)
0x180019b34  jmp     short loc_180019B8B
0x180019b36  xorps   xmm0, xmm0
0x180019b39  xor     eax, eax
0x180019b3b  movups  [rsp+118h+var_F0], xmm0
0x180019b40  mov     [rsp+118h+var_E0], eax
0x180019b44  lea     r8, [rsp+118h+var_F0]
0x180019b49  lea     rdx, [rsp+118h+var_F8]
0x180019b4e  mov     rcx, [rdi+28h]
0x180019b52  call    ??$Request@UGetHwndWindowRectService@@@IoDispatcher@@QEAA?AW4ResponseStatus@@AEBUGetHwndWindowRectRequestPayload@@AEAU?$HrResponse@UResponsePayload@GetHwndWindowRectService@@@@I@Z; IoDispatcher::Request<GetHwndWindowRectService>(GetHwndWindowRectRequestPayload const &,HrResponse<GetHwndWindowRectService::ResponsePayload> &,uint)
0x180019b57  mov     edx, dword ptr [rsp+118h+var_F0]
0x180019b5b  mov     ecx, eax
0x180019b5d  call    _anonymous_namespace___ValidateResponse
0x180019b62  mov     rcx, [rsp+118h]; this
0x180019b6a  test    eax, eax
0x180019b6c  jns     short loc_180019B82
0x180019b6e  mov     r9d, eax; char *
0x180019b71  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x180019b78  mov     edx, 41Ah; void *
0x180019b7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019b82  movups  xmm0, [rsp+118h+var_F0+4]
0x180019b87  movdqu  xmmword ptr [rsi], xmm0
0x180019b8b  xor     eax, eax
0x180019b8d  jmp     short loc_180019B93
0x180019b8f  mov     eax, [rsp+118h+var_F8]
0x180019b93  mov     rcx, [rsp+118h+var_48]
0x180019b9b  xor     rcx, rsp; StackCookie
0x180019b9e  call    __security_check_cookie
0x180019ba3  lea     r11, [rsp+118h+var_28]
0x180019bab  mov     rbx, [r11+48h]
0x180019baf  movaps  xmm6, xmmword ptr [r11-10h]
0x180019bb4  mov     rsp, r11
0x180019bb7  pop     r15
0x180019bb9  pop     r14
0x180019bbb  pop     r12
0x180019bbd  pop     rdi
0x180019bbe  pop     rsi
0x180019bbf  retn
```

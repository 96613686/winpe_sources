# UiaManagerCrossMachineProxy::GetHwndParent(HWND__ *,HWND__ * *,HWND__ * *)

- ea: `0x180019830`
- end: `0x1800199bf`
- name: `?GetHwndParent@UiaManagerCrossMachineProxy@@UEAAJPEAUHWND__@@PEAPEAU2@1@Z`
- size: `399`
- prototype: `int(UiaManagerCrossMachineProxy *__hidden this, HWND, HWND *, HWND *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180018868`
- `0x1800188c8`
- `0x1800188f8`
- `0x180018930`
- `0x180019830`
- `0x18001b698`
- `0x18001c89c`
- `0x180031540`
- `0x180058db8`
- `0x18007bd94`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800198f4`
- `msvcp_win!_Mtx_unlock` at `0x180019904`
- `msvcp_win!_Mtx_unlock` at `0x1800198f4`
- `msvcp_win!_Mtx_unlock` at `0x180019904`

## string_xrefs

- `0x180019876`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`
- `0x18001994d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`
- `0x180019984`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`

## pseudocode

```c
__int64 __fastcall UiaManagerCrossMachineProxy::GetHwndParent(
        UiaManagerCrossMachineProxy *this,
        HWND a2,
        HWND *a3,
        HWND *a4)
{
  struct _Mtx_internal_imp_t *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  char v13; // r13
  HWND v14; // r14
  HWND v15; // rbx
  const char *v16; // r9
  unsigned int HwndParent; // eax
  int v18; // eax
  __int64 result; // rax
  int v20[4]; // [rsp+20h] [rbp-48h] BYREF
  HWND v21; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HWND v24; // [rsp+78h] [rbp+10h] BYREF

  try
  {
    *a3 = 0;
    *a4 = 0;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
        (const char *)0x80070057LL,
        v20[0]);
    UiaManagerTraceLoggingProvider::CrossMachineProxyGetHwndParent(a2);
    v8 = (UiaManagerCrossMachineProxy *)((char *)this + 528);
    v24 = a2;
    std::_Mutex_base::lock((UiaManagerCrossMachineProxy *)((char *)this + 528));
    v10 = std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>::operator()<HWND__ *>(v9, &v24);
    v11 = std::_Hash<std::_Umap_traits<HWND__ *,HwndInfoCache::CachedHwndInfo,std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>,std::allocator<std::pair<HWND__ * const,HwndInfoCache::CachedHwndInfo>>,0>>::_Find<HWND__ *>(
            (char *)this + 608,
            &v24,
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
        v14 = *(HWND *)(v12 + 120);
        v15 = *(HWND *)(v12 + 128);
        v13 = 1;
      }
      else
      {
        v15 = v24;
        v14 = v24;
      }
      _Mtx_unlock(v8);
      if ( v13 )
      {
LABEL_14:
        if ( v15 && !(unsigned int)BasicHwndUtils::IsTopLevelWindow(v15) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x27E,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
            (const char *)0x80070006LL,
            v20[0]);
        *a3 = v14;
        *a4 = v15;
        return 0;
      }
    }
    *(_OWORD *)v20 = 0;
    v21 = 0;
    v24 = a2;
    HwndParent = IoDispatcher::Request<GetHwndParentService>(*((_QWORD *)this + 5), &v24, v20);
    v18 = anonymous_namespace_::ValidateResponse(HwndParent, (unsigned int)v20[0]);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x275,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
        (const char *)(unsigned int)v18,
        v20[0]);
    v14 = *(HWND *)&v20[2];
    v15 = v21;
    goto LABEL_14;
  }
  catch ( ... )
  {
    LODWORD(v24) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x285,
                     (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
                     v16);
    return (unsigned int)v24;
  }
  return result;
}

```

## disassembly

```asm
0x180019830  mov     [rsp+arg_10], rbx
0x180019835  mov     [rsp+arg_18], rsi
0x18001983a  mov     [rsp+arg_0], rcx
0x18001983f  push    rdi
0x180019840  push    r12
0x180019842  push    r13
0x180019844  push    r14
0x180019846  push    r15
0x180019848  sub     rsp, 40h
0x18001984c  mov     r15, r9
0x18001984f  mov     r12, r8
0x180019852  mov     rsi, rdx
0x180019855  mov     rbx, rcx
0x180019858  mov     qword ptr [r8], 0
0x18001985f  mov     qword ptr [r9], 0
0x180019866  mov     rcx, [rsp+68h]; this
0x18001986b  test    rdx, rdx
0x18001986e  jnz     short loc_180019887
0x180019870  mov     r9d, 80070057h; char *
0x180019876  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x18001987d  mov     edx, 25Fh; void *
0x180019882  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019887  mov     rcx, rsi; HWND
0x18001988a  call    ?CrossMachineProxyGetHwndParent@UiaManagerTraceLoggingProvider@@SAXPEAUHWND__@@@Z; UiaManagerTraceLoggingProvider::CrossMachineProxyGetHwndParent(HWND__ *)
0x18001988f  lea     rdi, [rbx+210h]
0x180019896  mov     [rsp+68h+arg_8], rsi
0x18001989b  mov     rcx, rdi; this
0x18001989e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800198a3  lea     rdx, [rsp+68h+arg_8]
0x1800198a8  call    ??$?RPEAUHWND__@@@?$_Uhash_compare@PEAUHWND__@@U?$hash@PEAUHWND__@@@std@@U?$equal_to@PEAUHWND__@@@3@@std@@QEBA_KAEBQEAUHWND__@@@Z; std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>::operator()<HWND__ *>(HWND__ * const &)
0x1800198ad  mov     r8, rax
0x1800198b0  lea     rcx, [rdi+50h]
0x1800198b4  lea     rdx, [rsp+68h+arg_8]
0x1800198b9  call    ??$_Find@PEAUHWND__@@@?$_Hash@V?$_Umap_traits@PEAUHWND__@@UCachedHwndInfo@HwndInfoCache@@V?$_Uhash_compare@PEAUHWND__@@U?$hash@PEAUHWND__@@@std@@U?$equal_to@PEAUHWND__@@@3@@std@@V?$allocator@U?$pair@QEAUHWND__@@UCachedHwndInfo@HwndInfoCache@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@QEAUHWND__@@UCachedHwndInfo@HwndInfoCache@@@std@@PEAX@1@AEBQEAUHWND__@@_K@Z; std::_Hash<std::_Umap_traits<HWND__ *,HwndInfoCache::CachedHwndInfo,std::_Uhash_compare<HWND__ *,std::hash<HWND__ *>,std::equal_to<HWND__ *>>,std::allocator<std::pair<HWND__ * const,HwndInfoCache::CachedHwndInfo>>,0>>::_Find<HWND__ *>(HWND__ * const &,unsigned __int64)
0x1800198be  mov     rbx, rax
0x1800198c1  cmp     rax, [rdi+58h]
0x1800198c5  jz      short loc_180019901
0x1800198c7  xor     r13b, r13b
0x1800198ca  lea     rcx, [rax+18h]; struct HwndInfoCache::CachedHwndInfo *
0x1800198ce  call    ?IsEntryValid@HwndInfoCache@@CA_NAEBUCachedHwndInfo@1@@Z; HwndInfoCache::IsEntryValid(HwndInfoCache::CachedHwndInfo const &)
0x1800198d3  test    al, al
0x1800198d5  jz      short loc_1800198E7
0x1800198d7  mov     r14, [rbx+78h]
0x1800198db  mov     rbx, [rbx+80h]
0x1800198e2  mov     r13b, 1
0x1800198e5  jmp     short loc_1800198F1
0x1800198e7  mov     rbx, [rsp+68h+arg_8]
0x1800198ec  mov     r14, [rsp+68h+arg_8]
0x1800198f1  mov     rcx, rdi; _Mtx_t
0x1800198f4  call    cs:__imp__Mtx_unlock
0x1800198fa  test    r13b, r13b
0x1800198fd  jz      short loc_18001990A
0x1800198ff  jmp     short loc_180019968
0x180019901  mov     rcx, rdi; _Mtx_t
0x180019904  call    cs:__imp__Mtx_unlock
0x18001990a  xorps   xmm0, xmm0
0x18001990d  xor     eax, eax
0x18001990f  movups  xmmword ptr [rsp+68h+var_48], xmm0; int
0x180019914  mov     [rsp+68h+var_38], rax
0x180019919  mov     [rsp+68h+arg_8], rsi
0x18001991e  lea     r8, [rsp+68h+var_48]
0x180019923  lea     rdx, [rsp+68h+arg_8]
0x180019928  mov     rcx, [rsp+68h+arg_0]
0x18001992d  mov     rcx, [rcx+28h]
0x180019931  call    ??$Request@UGetHwndParentService@@@IoDispatcher@@QEAA?AW4ResponseStatus@@AEBUGetHwndParentRequestPayload@@AEAU?$HrResponse@UResponsePayload@GetHwndParentService@@@@I@Z; IoDispatcher::Request<GetHwndParentService>(GetHwndParentRequestPayload const &,HrResponse<GetHwndParentService::ResponsePayload> &,uint)
0x180019936  mov     edx, [rsp+68h+var_48]
0x18001993a  mov     ecx, eax
0x18001993c  call    _anonymous_namespace___ValidateResponse
0x180019941  mov     rcx, [rsp+68h]; this
0x180019946  test    eax, eax
0x180019948  jns     short loc_18001995E
0x18001994a  mov     r9d, eax; char *
0x18001994d  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x180019954  mov     edx, 275h; void *
0x180019959  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001995e  mov     r14, qword ptr [rsp+68h+var_48+8]
0x180019963  mov     rbx, [rsp+68h+var_38]
0x180019968  test    rbx, rbx
0x18001996b  jz      short loc_180019995
0x18001996d  mov     rcx, rbx; HWND
0x180019970  call    ?IsTopLevelWindow@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsTopLevelWindow(HWND__ *)
0x180019975  test    eax, eax
0x180019977  jnz     short loc_180019995
0x180019979  mov     rcx, [rsp+68h]; this
0x18001997e  mov     r9d, 80070006h; char *
0x180019984  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x18001998b  mov     edx, 27Eh; void *
0x180019990  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019995  mov     [r12], r14
0x180019999  mov     [r15], rbx
0x18001999c  xor     eax, eax
0x18001999e  jmp     short loc_1800199A4
0x1800199a0  mov     eax, dword ptr [rsp+68h+arg_8]
0x1800199a4  lea     r11, [rsp+68h+var_28]
0x1800199a9  mov     rbx, [r11+40h]
0x1800199ad  mov     rsi, [r11+48h]
0x1800199b1  mov     rsp, r11
0x1800199b4  pop     r15
0x1800199b6  pop     r14
0x1800199b8  pop     r13
0x1800199ba  pop     r12
0x1800199bc  pop     rdi
0x1800199bd  retn
```

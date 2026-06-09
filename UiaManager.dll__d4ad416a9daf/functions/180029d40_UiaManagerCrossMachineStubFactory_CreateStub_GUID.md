# UiaManagerCrossMachineStubFactory::CreateStub(_GUID)

- ea: `0x180029d40`
- end: `0x180029ea9`
- name: `?CreateStub@UiaManagerCrossMachineStubFactory@@UEAAJU_GUID@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(UiaManagerCrossMachineStubFactory *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800065c4`
- `0x1800067f8`
- `0x180006edc`
- `0x1800092c0`
- `0x1800114c4`
- `0x180018868`
- `0x180029d40`
- `0x180029eb0`
- `0x18002c980`
- `0x180031540`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180029e89`
- `msvcp_win!_Mtx_unlock` at `0x180029e89`

## string_xrefs

- `0x180029d6b`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestubfactory.cpp`
- `0x180029e53`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestubfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UiaManagerCrossMachineStubFactory::CreateStub(
        UiaManagerCrossMachineStubFactory *this,
        struct _GUID *a2)
{
  const char *v4; // r9
  __int64 result; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int128 v9; // xmm0
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13[4]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v14[17]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v15; // [rsp+41h] [rbp-27h]
  char v16; // [rsp+43h] [rbp-25h]
  char *v17; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    if ( UiaManagerSecurityUtils::IsAccessAllowed(0) )
    {
      v17 = (char *)this + 88;
      std::_Mutex_base::lock((UiaManagerCrossMachineStubFactory *)((char *)this + 88));
      v7 = std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(v6, a2);
      v8 = *(_QWORD *)(std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::_Find_last<_GUID>(
                         (char *)this + 24,
                         v13,
                         a2,
                         v7)
                     + 8);
      if ( !v8 )
        v8 = *((_QWORD *)this + 4);
      if ( v8 == *((_QWORD *)this + 4) )
      {
        v9 = (__int128)*a2;
        v10 = 1;
        while ( _InterlockedExchange(&UiaManagerCrossMachineStubFactory::s_machineIdInRemoteSession, 1) )
        {
          while ( UiaManagerCrossMachineStubFactory::s_machineIdInRemoteSession )
          {
            v11 = v10;
            if ( !v10 )
              goto LABEL_12;
            do
            {
              _mm_pause();
              --v11;
            }
            while ( v11 );
            if ( v10 >= 64 )
              v10 = 64;
            else
LABEL_12:
              v10 *= 2;
          }
        }
        xmmword_1800C4FDC = v9;
        byte_1800C4FEC = 1;
        word_1800C4FED = v15;
        byte_1800C4FEF = v16;
        UiaManagerCrossMachineStubFactory::s_machineIdInRemoteSession = 0;
        *(_QWORD *)v13 = 0;
        v12 = Microsoft::WRL::Details::MakeAndInitialize<UiaManagerCrossMachineStub,UiaManagerCrossMachineStub,_GUID &>(
                v13,
                a2);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x22,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactory.cpp",
            (const char *)(unsigned int)v12,
            v13[0]);
        std::unordered_map<_GUID,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy>>::_Insert_or_assign<_GUID const &,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy> &>(
          (char *)this + 24,
          v14,
          a2,
          v13);
        wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(v13);
      }
      _Mtx_unlock((UiaManagerCrossMachineStubFactory *)((char *)this + 88));
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactory.cpp",
        (const char *)0x80070005LL,
        v13[0]);
      result = 2147942405LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x28,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactory.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180029d40  mov     [rsp+arg_10], rbx
0x180029d45  push    rsi
0x180029d46  push    rdi
0x180029d47  push    r14
0x180029d49  sub     rsp, 50h
0x180029d4d  mov     rsi, rdx
0x180029d50  mov     rdi, rcx
0x180029d53  xor     ecx, ecx
0x180029d55  call    ?IsAccessAllowed@UiaManagerSecurityUtils@@CA_NW4AppContainerAccessCapability@1@@Z; UiaManagerSecurityUtils::IsAccessAllowed(UiaManagerSecurityUtils::AppContainerAccessCapability)
0x180029d5a  test    al, al
0x180029d5c  jnz     short loc_180029D83
0x180029d5e  mov     rcx, [rsp+68h]; this
0x180029d63  mov     ebx, 80070005h
0x180029d68  mov     r9d, ebx; char *
0x180029d6b  lea     r8, aOnecoreWindows_11; "onecore\\windows\\accessibletech\\uiama"...
0x180029d72  mov     edx, 12h; void *
0x180029d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d7c  mov     eax, ebx
0x180029d7e  jmp     loc_180029E97
0x180029d83  lea     rbx, [rdi+58h]
0x180029d87  mov     [rsp+68h+var_20], rbx
0x180029d8c  mov     rcx, rbx; this
0x180029d8f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180029d94  nop
0x180029d95  mov     rdx, rsi
0x180029d98  call    ??$?RU_GUID@@@?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@QEBA_KAEBU_GUID@@@Z; std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(_GUID const &)
0x180029d9d  mov     r9, rax
0x180029da0  mov     r8, rsi
0x180029da3  lea     rdx, [rsp+68h+var_48]
0x180029da8  lea     rcx, [rdi+18h]
0x180029dac  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x180029db1  mov     rcx, [rax+8]
0x180029db5  test    rcx, rcx
0x180029db8  jnz     short loc_180029DBE
0x180029dba  mov     rcx, [rdi+20h]
0x180029dbe  cmp     rcx, [rdi+20h]
0x180029dc2  jnz     loc_180029E86
0x180029dc8  movups  xmm0, xmmword ptr [rsi]
0x180029dcb  mov     edx, 1
0x180029dd0  mov     ecx, edx
0x180029dd2  jmp     short loc_180029DF6
0x180029dd4  mov     eax, ecx
0x180029dd6  test    ecx, ecx
0x180029dd8  jz      short loc_180029DEA
0x180029dda  pause
0x180029ddc  sub     eax, edx
0x180029dde  jnz     short loc_180029DDA
0x180029de0  cmp     ecx, 40h ; '@'
0x180029de3  jl      short loc_180029DEA
0x180029de5  lea     ecx, [rax+40h]
0x180029de8  jmp     short loc_180029DEC
0x180029dea  add     ecx, ecx
0x180029dec  mov     eax, cs:?s_machineIdInRemoteSession@UiaManagerCrossMachineStubFactory@@0U?$atomic@V?$optional@U_GUID@@@std@@@std@@A; std::atomic<std::optional<_GUID>> UiaManagerCrossMachineStubFactory::s_machineIdInRemoteSession
0x180029df2  test    eax, eax
0x180029df4  jnz     short loc_180029DD4
0x180029df6  mov     eax, edx
0x180029df8  xchg    eax, cs:?s_machineIdInRemoteSession@UiaManagerCrossMachineStubFactory@@0U?$atomic@V?$optional@U_GUID@@@std@@@std@@A; std::atomic<std::optional<_GUID>> UiaManagerCrossMachineStubFactory::s_machineIdInRemoteSession
0x180029dfe  test    eax, eax
0x180029e00  jnz     short loc_180029DEC
0x180029e02  movdqu  cs:xmmword_1800C4FDC, xmm0
0x180029e0a  mov     cs:byte_1800C4FEC, dl
0x180029e10  movzx   eax, [rsp+68h+var_27]
0x180029e15  mov     cs:word_1800C4FED, ax
0x180029e1c  mov     al, [rsp+68h+var_25]
0x180029e20  mov     cs:byte_1800C4FEF, al
0x180029e26  nop
0x180029e27  mov     cs:?s_machineIdInRemoteSession@UiaManagerCrossMachineStubFactory@@0U?$atomic@V?$optional@U_GUID@@@std@@@std@@A, 0; std::atomic<std::optional<_GUID>> UiaManagerCrossMachineStubFactory::s_machineIdInRemoteSession
0x180029e31  mov     qword ptr [rsp+68h+var_48], 0; int
0x180029e3a  mov     rdx, rsi
0x180029e3d  lea     rcx, [rsp+68h+var_48]
0x180029e42  call    ??$MakeAndInitialize@VUiaManagerCrossMachineStub@@V1@AEAU_GUID@@@Details@WRL@Microsoft@@YAJPEAPEAVUiaManagerCrossMachineStub@@AEAU_GUID@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UiaManagerCrossMachineStub,UiaManagerCrossMachineStub,_GUID &>(UiaManagerCrossMachineStub * *,_GUID &)
0x180029e47  mov     rcx, [rsp+68h]; this
0x180029e4c  test    eax, eax
0x180029e4e  jns     short loc_180029E64
0x180029e50  mov     r9d, eax; char *
0x180029e53  lea     r8, aOnecoreWindows_11; "onecore\\windows\\accessibletech\\uiama"...
0x180029e5a  mov     edx, 22h ; '"'; void *
0x180029e5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029e64  lea     r9, [rsp+68h+var_48]
0x180029e69  mov     r8, rsi
0x180029e6c  lea     rdx, [rsp+68h+var_38]
0x180029e71  lea     rcx, [rdi+18h]
0x180029e75  call    ??$_Insert_or_assign@AEBU_GUID@@AEAV?$com_ptr_t@VUiaManagerCrossMachineStub@@Uerr_exception_policy@wil@@@wil@@@?$unordered_map@U_GUID@@V?$com_ptr_t@VUiaManagerCrossMachineStub@@Uerr_exception_policy@wil@@@wil@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@5@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VUiaManagerCrossMachineStub@@Uerr_exception_policy@wil@@@wil@@@std@@@5@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VUiaManagerCrossMachineStub@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@AEAV?$com_ptr_t@VUiaManagerCrossMachineStub@@Uerr_exception_policy@wil@@@wil@@@Z; std::unordered_map<_GUID,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy>>::_Insert_or_assign<_GUID const &,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy> &>(_GUID const &,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy> &)
0x180029e7a  nop
0x180029e7b  lea     rcx, [rsp+68h+var_48]
0x180029e80  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180029e85  nop
0x180029e86  mov     rcx, rbx; _Mtx_t
0x180029e89  call    cs:__imp__Mtx_unlock
0x180029e8f  xor     eax, eax
0x180029e91  jmp     short loc_180029E97
0x180029e93  mov     eax, [rsp+68h+var_48]
0x180029e97  mov     rbx, [rsp+68h+arg_10]
0x180029e9f  add     rsp, 50h
0x180029ea3  pop     r14
0x180029ea5  pop     rdi
0x180029ea6  pop     rsi
0x180029ea7  retn
```

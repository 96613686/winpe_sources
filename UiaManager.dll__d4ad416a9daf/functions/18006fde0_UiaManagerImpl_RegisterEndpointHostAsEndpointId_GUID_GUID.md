# UiaManagerImpl::RegisterEndpointHostAsEndpointId(_GUID,_GUID)

- ea: `0x18006fde0`
- end: `0x18006fff9`
- name: `?RegisterEndpointHostAsEndpointId@UiaManagerImpl@@UEAAJU_GUID@@0@Z`
- size: `537`
- prototype: `int(UiaManagerImpl *__hidden this, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800054f8`
- `0x180005610`
- `0x1800065c4`
- `0x18000c7f0`
- `0x18000dc9c`
- `0x18000e4d0`
- `0x180018868`
- `0x180031540`
- `0x180043680`
- `0x180044188`
- `0x18006e7ec`
- `0x18006fde0`
- `0x180091010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18006ff39`
- `msvcp_win!_Mtx_unlock` at `0x18006ff39`

## string_xrefs

- `0x18006ffba`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006ffd1`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006ffe6`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UiaManagerImpl::RegisterEndpointHostAsEndpointId(
        UiaManagerImpl *this,
        struct _GUID *a2,
        struct _GUID *a3)
{
  const struct _tlgProvider_t *v6; // rax
  struct _GUID v7; // xmm6
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  bool v11; // zf
  int v12; // eax
  const char *v13; // r9
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-C8h]
  __int64 v16; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v17[17]; // [rsp+38h] [rbp-B0h] BYREF
  int v18; // [rsp+49h] [rbp-9Fh]
  __int16 v19; // [rsp+4Dh] [rbp-9Bh]
  char v20; // [rsp+4Fh] [rbp-99h]
  char *v21; // [rsp+50h] [rbp-98h]
  struct _GUID v22; // [rsp+60h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+70h] [rbp-78h] BYREF
  struct _GUID *v24; // [rsp+90h] [rbp-58h]
  __int64 v25; // [rsp+98h] [rbp-50h]
  struct _GUID *v26; // [rsp+A0h] [rbp-48h]
  __int64 v27; // [rsp+A8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      v15);
  if ( !memcmp_0(a3, &GUID_NULL, 0x10u) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      v15);
  v6 = UiaManagerTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v6 > 4u )
  {
    v26 = a3;
    v27 = 16;
    v24 = a2;
    v25 = 16;
    tlgWriteTransfer_EventWriteTransfer((__int64)v6, (unsigned __int8 *)&word_1800AD856, 0, 0, 4u, &v23);
  }
  try
  {
    v7 = *a3;
    v22 = *a3;
    v21 = (char *)this + 328;
    std::_Mutex_base::lock((UiaManagerImpl *)((char *)this + 328));
    v9 = std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(v8, a2);
    v10 = std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::_Find<_GUID>(
            (char *)this + 408,
            a2,
            v9);
    if ( v10 == *((_QWORD *)this + 52) )
    {
      std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::emplace<_GUID const &,WrapperType<_GUID>>(
        (char *)this + 408,
        v17,
        a2,
        &v22);
    }
    else
    {
      v11 = *(_BYTE *)(v10 + 56) == 0;
      *(struct _GUID *)(v10 + 32) = v7;
      *(_BYTE *)(v10 + 48) = 1;
      if ( v11 )
      {
        *(_BYTE *)(v10 + 56) = 1;
      }
      else
      {
        *(_DWORD *)(v10 + 49) = v18;
        *(_WORD *)(v10 + 53) = v19;
        *(_BYTE *)(v10 + 55) = v20;
      }
    }
    _Mtx_unlock((UiaManagerImpl *)((char *)this + 328));
    UiaManagerImpl::GetUiaManagerEndpointStateNotifier((__int64)this - 48, &v16);
    v22 = *a2;
    v12 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v16 + 40LL))(v16, &v22);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)(unsigned int)v12,
        v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x18B,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18006fde0  mov     rax, rsp
0x18006fde3  mov     [rax+18h], rbx
0x18006fde7  push    rsi
0x18006fde8  push    rdi
0x18006fde9  push    r14
0x18006fdeb  sub     rsp, 0D0h
0x18006fdf2  movaps  xmmword ptr [rax-28h], xmm6
0x18006fdf6  mov     rax, cs:__security_cookie
0x18006fdfd  xor     rax, rsp
0x18006fe00  mov     [rsp+0E8h+var_38], rax
0x18006fe08  mov     rsi, r8
0x18006fe0b  mov     rdi, rdx
0x18006fe0e  mov     r14, rcx
0x18006fe11  mov     ebx, 10h
0x18006fe16  mov     r8d, ebx; Size
0x18006fe19  lea     rdx, GUID_NULL; Buf2
0x18006fe20  mov     rcx, rdi; Buf1
0x18006fe23  call    memcmp_0
0x18006fe28  test    eax, eax
0x18006fe2a  setz    al
0x18006fe2d  mov     rcx, [rsp+0E8h]; this
0x18006fe35  test    al, al
0x18006fe37  jnz     loc_18006FFB4
0x18006fe3d  mov     r8, rbx; Size
0x18006fe40  lea     rdx, GUID_NULL; Buf2
0x18006fe47  mov     rcx, rsi; Buf1
0x18006fe4a  call    memcmp_0
0x18006fe4f  test    eax, eax
0x18006fe51  setz    al
0x18006fe54  mov     rcx, [rsp+0E8h]; this
0x18006fe5c  test    al, al
0x18006fe5e  jnz     loc_18006FFCB
0x18006fe64  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x18006fe69  mov     ecx, [rax]
0x18006fe6b  cmp     ecx, 4
0x18006fe6e  jbe     short loc_18006FEB7
0x18006fe70  mov     [rsp+0E8h+var_48], rsi
0x18006fe78  mov     [rsp+0E8h+var_40], rbx
0x18006fe80  mov     [rsp+0E8h+var_58], rdi
0x18006fe88  mov     [rsp+0E8h+var_50], rbx
0x18006fe90  lea     rcx, [rsp+0E8h+var_78]
0x18006fe95  mov     [rsp+0E8h+var_C0], rcx
0x18006fe9a  mov     [rsp+0E8h+var_C8], 4; int
0x18006fea2  xor     r9d, r9d
0x18006fea5  xor     r8d, r8d
0x18006fea8  lea     rdx, word_1800AD856
0x18006feaf  mov     rcx, rax
0x18006feb2  call    _tlgWriteTransfer_EventWriteTransfer
0x18006feb7  lea     rbx, [r14+148h]
0x18006febe  movups  xmm6, xmmword ptr [rsi]
0x18006fec1  movups  [rsp+0E8h+var_88], xmm6
0x18006fec6  mov     [rsp+0E8h+var_98], rbx
0x18006fecb  mov     rcx, rbx; this
0x18006fece  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18006fed3  nop
0x18006fed4  mov     rdx, rdi
0x18006fed7  call    ??$?RU_GUID@@@?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@QEBA_KAEBU_GUID@@@Z; std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(_GUID const &)
0x18006fedc  mov     r8, rax
0x18006fedf  mov     rdx, rdi
0x18006fee2  lea     rcx, [rbx+50h]
0x18006fee6  call    ??$_Find@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$optional@VProviderEntrypointId@@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$optional@VProviderEntrypointId@@@std@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$optional@VProviderEntrypointId@@@std@@@std@@PEAX@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::_Find<_GUID>(_GUID const &,unsigned __int64)
0x18006feeb  cmp     rax, [rbx+58h]
0x18006feef  jz      short loc_18006FF1F
0x18006fef1  cmp     byte ptr [rax+38h], 0
0x18006fef5  movdqu  xmmword ptr [rax+20h], xmm6
0x18006fefa  mov     byte ptr [rax+30h], 1
0x18006fefe  jz      short loc_18006FF19
0x18006ff00  mov     ecx, [rsp+0E8h+var_9F]
0x18006ff04  mov     [rax+31h], ecx
0x18006ff07  movzx   ecx, [rsp+0E8h+var_9B]
0x18006ff0c  mov     [rax+35h], cx
0x18006ff10  mov     cl, [rsp+0E8h+var_99]
0x18006ff14  mov     [rax+37h], cl
0x18006ff17  jmp     short loc_18006FF36
0x18006ff19  mov     byte ptr [rax+38h], 1
0x18006ff1d  jmp     short loc_18006FF36
0x18006ff1f  lea     r9, [rsp+0E8h+var_88]
0x18006ff24  mov     r8, rdi
0x18006ff27  lea     rdx, [rsp+0E8h+var_B0]
0x18006ff2c  lea     rcx, [rbx+50h]
0x18006ff30  call    ??$emplace@AEBU_GUID@@U?$WrapperType@U_GUID@@@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$optional@VProviderEntrypointId@@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$optional@VProviderEntrypointId@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@V?$optional@VProviderEntrypointId@@@std@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAU?$WrapperType@U_GUID@@@@@Z; std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::emplace<_GUID const &,WrapperType<_GUID>>(_GUID const &,WrapperType<_GUID> &&)
0x18006ff35  nop
0x18006ff36  mov     rcx, rbx; _Mtx_t
0x18006ff39  call    cs:__imp__Mtx_unlock
0x18006ff3f  lea     rcx, [r14-30h]
0x18006ff43  lea     rdx, [rsp+0E8h+var_B8]
0x18006ff48  call    ?GetUiaManagerEndpointStateNotifier@UiaManagerImpl@@AEAA?AV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@XZ; UiaManagerImpl::GetUiaManagerEndpointStateNotifier(void)
0x18006ff4d  nop
0x18006ff4e  mov     rcx, [rsp+0E8h+var_B8]
0x18006ff53  movups  xmm0, xmmword ptr [rdi]
0x18006ff56  movdqu  [rsp+0E8h+var_88], xmm0
0x18006ff5c  mov     rax, [rcx]
0x18006ff5f  lea     rdx, [rsp+0E8h+var_88]
0x18006ff64  mov     rax, [rax+28h]
0x18006ff68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff6d  mov     rcx, [rsp+0E8h]; this
0x18006ff75  test    eax, eax
0x18006ff77  js      short loc_18006FFE3
0x18006ff79  lea     rcx, [rsp+0E8h+var_B8]
0x18006ff7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ff83  xor     eax, eax
0x18006ff85  jmp     short loc_18006FF8B
0x18006ff87  mov     eax, dword ptr [rsp+0E8h+var_B8]
0x18006ff8b  mov     rcx, [rsp+0E8h+var_38]
0x18006ff93  xor     rcx, rsp; StackCookie
0x18006ff96  call    __security_check_cookie
0x18006ff9b  lea     r11, [rsp+0E8h+var_18]
0x18006ffa3  mov     rbx, [r11+30h]
0x18006ffa7  movaps  xmm6, xmmword ptr [r11-10h]
0x18006ffac  mov     rsp, r11
0x18006ffaf  pop     r14
0x18006ffb1  pop     rdi
0x18006ffb2  pop     rsi
0x18006ffb3  retn
0x18006ffb4  mov     r9d, 80070057h; char *
0x18006ffba  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006ffc1  mov     edx, 17Dh; void *
0x18006ffc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ffcb  mov     r9d, 80070057h; char *
0x18006ffd1  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006ffd8  mov     edx, 17Eh; void *
0x18006ffdd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ffe3  mov     r9d, eax; char *
0x18006ffe6  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006ffed  mov     edx, 187h; void *
0x18006fff2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

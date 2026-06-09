# PluginGetOrCreateInternalUvKeyName

- ea: `0x18004363c`
- end: `0x180043940`
- name: `PluginGetOrCreateInternalUvKeyName`
- size: `772`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020a7c`

## callees

- `0x18000c050`
- `0x180017a88`
- `0x1800205e4`
- `0x1800328b8`
- `0x180036da4`
- `0x18004363c`
- `0x180043948`
- `0x180043a18`
- `0x180043a6c`
- `0x180043a94`
- `0x180043ab4`
- `0x1800859d8`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800437dc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800437dc`
- `bcrypt!BCryptGenRandom` at `0x1800436d6`
- `bcrypt!BCryptGenRandom` at `0x1800436d6`
- `RPCRT4!UuidToStringW` at `0x18004371e`
- `RPCRT4!UuidToStringW` at `0x18004371e`
- `cryptngc!NgcGetUserIdKeyName` at `0x1800438e1`
- `cryptngc!NgcGetUserIdKeyName` at `0x1800438e1`

## string_xrefs

- `0x18004369e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800438b8`: `PluginUvKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PluginGetOrCreateInternalUvKeyName(
        wil::reg::reg_view_details::reg_value_type_info *hKey,
        __int64 a2)
{
  __int64 v4; // rdx
  int v5; // eax
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // rdx
  DWORD cbData; // eax
  LPCVOID v14; // rcx
  LSTATUS v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // ebx
  int UserIdKeyName; // eax
  unsigned int v21; // ebx
  unsigned int lpData; // [rsp+20h] [rbp-88h]
  int lpDataa; // [rsp+20h] [rbp-88h]
  __int64 v24; // [rsp+30h] [rbp-78h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-70h] BYREF
  wil::reg::reg_view_details::reg_value_type_info *v26; // [rsp+40h] [rbp-68h] BYREF
  wil::reg::reg_view_details::reg_value_type_info *v27; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v28[3]; // [rsp+50h] [rbp-58h] BYREF
  UCHAR pbBuffer[16]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v24 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v24,
    0);
  v26 = hKey;
  v5 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
         &v26,
         v4,
         L"UvKeyId",
         &v24);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v5,
      268435462);
    *(_OWORD *)pbBuffer = 0;
    v6 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
    if ( v6 < 0 )
    {
      v7 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x56,
             (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
             (const char *)(unsigned int)v6,
             lpData);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
      result = v7;
      goto LABEL_18;
    }
    StringUuid = 0;
    v10 = UuidToStringW((const UUID *)pbBuffer, &StringUuid);
    if ( v10 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x59,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
              (const char *)v10,
              lpData);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
      result = v11;
      goto LABEL_18;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v26,
      StringUuid,
      -1);
    if ( !v26 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)0x8007000ELL,
        lpData);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
      result = 2147942414LL;
      goto LABEL_18;
    }
    cbData = wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(v26, v12);
    v15 = RegSetKeyValueW((HKEY)hKey, 0, L"UvKeyId", 1u, v14, cbData);
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    if ( (v16 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)v16,
        lpDataa);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
      result = v16;
      goto LABEL_18;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v24,
      0);
    v27 = hKey;
    v18 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
            &v27,
            v17,
            L"UvKeyId",
            &v24);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v18,
        268435462);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
      result = v19;
      goto LABEL_18;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v26);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
  }
  v28[0] = L"PluginUvKey";
  v28[1] = 0;
  v28[2] = v24;
  UserIdKeyName = NgcGetUserIdKeyName(v28, 0, a2);
  v21 = UserIdKeyName;
  if ( UserIdKeyName >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
    result = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)UserIdKeyName,
      268435462);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
    result = v21;
  }
LABEL_18:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      LODWORD(v24) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x6B,
                       (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
                       v8);
      result = (unsigned int)v24;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18004363c  push    rbx
0x18004363e  push    rsi
0x18004363f  push    rdi
0x180043640  push    r14
0x180043642  sub     rsp, 88h
0x180043649  mov     rax, cs:__security_cookie
0x180043650  xor     rax, rsp
0x180043653  mov     [rsp+0A8h+var_30], rax
0x180043658  mov     r14, rdx
0x18004365b  mov     rsi, rcx
0x18004365e  mov     [rsp+0A8h+var_78], 0
0x180043667  xor     edx, edx
0x180043669  lea     rcx, [rsp+0A8h+var_78]
0x18004366e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180043673  mov     [rsp+0A8h+var_68], rsi
0x180043678  mov     dword ptr [rsp+0A8h+lpData], 10000006h; int
0x180043680  lea     r9, [rsp+0A8h+var_78]
0x180043685  lea     r8, aUvkeyid; "UvKeyId"
0x18004368c  lea     rcx, [rsp+0A8h+var_68]
0x180043691  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x180043696  mov     rcx, [rsp+0A8h]; this
0x18004369e  lea     rdi, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800436a5  test    eax, eax
0x1800436a7  jns     loc_1800438B8
0x1800436ad  mov     r9d, eax; char *
0x1800436b0  mov     r8, rdi; unsigned int
0x1800436b3  mov     edx, 52h ; 'R'; void *
0x1800436b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800436bd  xorps   xmm0, xmm0
0x1800436c0  movups  xmmword ptr [rsp+0A8h+pbBuffer], xmm0
0x1800436c5  mov     r9d, 2; dwFlags
0x1800436cb  lea     r8d, [r9+0Eh]; cbBuffer
0x1800436cf  lea     rdx, [rsp+0A8h+pbBuffer]; pbBuffer
0x1800436d4  xor     ecx, ecx; hAlgorithm
0x1800436d6  call    cs:__imp_BCryptGenRandom
0x1800436dc  test    eax, eax
0x1800436de  jns     short loc_18004370B
0x1800436e0  mov     rcx, [rsp+0A8h]; this
0x1800436e8  mov     r9d, eax; char *
0x1800436eb  mov     r8, rdi; unsigned int
0x1800436ee  mov     edx, 56h ; 'V'; void *
0x1800436f3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800436f8  mov     ebx, eax
0x1800436fa  lea     rcx, [rsp+0A8h+var_78]
0x1800436ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180043704  mov     eax, ebx
0x180043706  jmp     loc_180043925
0x18004370b  mov     [rsp+0A8h+StringUuid], 0
0x180043714  lea     rdx, [rsp+0A8h+StringUuid]; StringUuid
0x180043719  lea     rcx, [rsp+0A8h+pbBuffer]; Uuid
0x18004371e  call    cs:__imp_UuidToStringW
0x180043724  test    eax, eax
0x180043726  jz      short loc_18004375D
0x180043728  mov     rcx, [rsp+0A8h]; this
0x180043730  mov     r9d, eax; char *
0x180043733  mov     r8, rdi; unsigned int
0x180043736  mov     edx, 59h ; 'Y'; void *
0x18004373b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180043740  mov     ebx, eax
0x180043742  lea     rcx, [rsp+0A8h+StringUuid]
0x180043747  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004374c  lea     rcx, [rsp+0A8h+var_78]
0x180043751  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180043756  mov     eax, ebx
0x180043758  jmp     loc_180043925
0x18004375d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180043761  mov     rdx, [rsp+0A8h+StringUuid]
0x180043766  lea     rcx, [rsp+0A8h+var_68]
0x18004376b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180043770  mov     rcx, [rsp+0A8h+var_68]; this
0x180043775  test    rcx, rcx
0x180043778  jnz     short loc_1800437BC
0x18004377a  mov     rcx, [rsp+0A8h]; this
0x180043782  mov     ebx, 8007000Eh
0x180043787  mov     r9d, ebx; char *
0x18004378a  mov     r8, rdi; unsigned int
0x18004378d  mov     edx, 5Ch ; '\'; void *
0x180043792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043797  lea     rcx, [rsp+0A8h+var_68]
0x18004379c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800437a1  lea     rcx, [rsp+0A8h+StringUuid]
0x1800437a6  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800437ab  lea     rcx, [rsp+0A8h+var_78]
0x1800437b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800437b5  mov     eax, ebx
0x1800437b7  jmp     loc_180043925
0x1800437bc  call    ?get_buffer_size_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAKPEBG@Z; wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(ushort const *)
0x1800437c1  mov     [rsp+0A8h+cbData], eax; cbData
0x1800437c5  mov     [rsp+0A8h+lpData], rcx; int
0x1800437ca  mov     r9d, 1; dwType
0x1800437d0  lea     r8, aUvkeyid; "UvKeyId"
0x1800437d7  xor     edx, edx; lpSubKey
0x1800437d9  mov     rcx, rsi; hKey
0x1800437dc  call    cs:__imp_RegSetKeyValueW
0x1800437e2  mov     ebx, eax
0x1800437e4  test    eax, eax
0x1800437e6  jle     short loc_1800437F1
0x1800437e8  movzx   ebx, ax
0x1800437eb  or      ebx, 80070000h
0x1800437f1  test    ebx, ebx
0x1800437f3  jns     short loc_180043832
0x1800437f5  mov     rcx, [rsp+0A8h]; this
0x1800437fd  mov     r9d, ebx; char *
0x180043800  mov     r8, rdi; unsigned int
0x180043803  mov     edx, 5Eh ; '^'; void *
0x180043808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004380d  lea     rcx, [rsp+0A8h+var_68]
0x180043812  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180043817  lea     rcx, [rsp+0A8h+StringUuid]
0x18004381c  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043821  lea     rcx, [rsp+0A8h+var_78]
0x180043826  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004382b  mov     eax, ebx
0x18004382d  jmp     loc_180043925
0x180043832  xor     edx, edx
0x180043834  lea     rcx, [rsp+0A8h+var_78]
0x180043839  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004383e  mov     [rsp+0A8h+var_60], rsi
0x180043843  mov     dword ptr [rsp+0A8h+lpData], 10000006h; int
0x18004384b  lea     r9, [rsp+0A8h+var_78]
0x180043850  lea     r8, aUvkeyid; "UvKeyId"
0x180043857  lea     rcx, [rsp+0A8h+var_60]
0x18004385c  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x180043861  mov     ebx, eax
0x180043863  test    eax, eax
0x180043865  jns     short loc_1800438A4
0x180043867  mov     rcx, [rsp+0A8h]; this
0x18004386f  mov     r9d, eax; char *
0x180043872  mov     r8, rdi; unsigned int
0x180043875  mov     edx, 5Fh ; '_'; void *
0x18004387a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004387f  lea     rcx, [rsp+0A8h+var_68]
0x180043884  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180043889  lea     rcx, [rsp+0A8h+StringUuid]
0x18004388e  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043893  lea     rcx, [rsp+0A8h+var_78]
0x180043898  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004389d  mov     eax, ebx
0x18004389f  jmp     loc_180043925
0x1800438a4  lea     rcx, [rsp+0A8h+var_68]
0x1800438a9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800438ae  lea     rcx, [rsp+0A8h+StringUuid]
0x1800438b3  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800438b8  lea     rax, aPluginuvkey; "PluginUvKey"
0x1800438bf  mov     [rsp+0A8h+var_58], rax
0x1800438c4  mov     [rsp+0A8h+var_50], 0
0x1800438cd  mov     rax, [rsp+0A8h+var_78]
0x1800438d2  mov     [rsp+0A8h+var_48], rax
0x1800438d7  mov     r8, r14
0x1800438da  xor     edx, edx
0x1800438dc  lea     rcx, [rsp+0A8h+var_58]
0x1800438e1  call    cs:__imp_NgcGetUserIdKeyName
0x1800438e7  mov     ebx, eax
0x1800438e9  test    eax, eax
0x1800438eb  jns     short loc_180043913
0x1800438ed  mov     rcx, [rsp+0A8h]; this
0x1800438f5  mov     r9d, eax; char *
0x1800438f8  mov     r8, rdi; unsigned int
0x1800438fb  mov     edx, 67h ; 'g'; void *
0x180043900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043905  lea     rcx, [rsp+0A8h+var_78]
0x18004390a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004390f  mov     eax, ebx
0x180043911  jmp     short loc_180043925
0x180043913  lea     rcx, [rsp+0A8h+var_78]
0x180043918  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004391d  xor     eax, eax
0x18004391f  jmp     short loc_180043925
0x180043921  mov     eax, dword ptr [rsp+0A8h+var_78]
0x180043925  mov     rcx, [rsp+0A8h+var_30]
0x18004392a  xor     rcx, rsp; StackCookie
0x18004392d  call    __security_check_cookie
0x180043932  add     rsp, 88h
0x180043939  pop     r14
0x18004393b  pop     rdi
0x18004393c  pop     rsi
0x18004393d  pop     rbx
0x18004393e  retn
```

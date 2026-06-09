# PhoneController::_GetApplicationUserModelIdFromRpcClient(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18003b8c0`
- end: `0x18003b9ea`
- name: `?_GetApplicationUserModelIdFromRpcClient@PhoneController@@AEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `298`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180029990`
- `0x1800368d0`
- `0x18003993c`
- `0x180039b14`

## callees

- `0x1800045b4`
- `0x180007750`
- `0x180009094`
- `0x18002c580`
- `0x18003b8c0`
- `0x18008d95a`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b9c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b9c1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003b948`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003b948`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18003b8ff`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18003b8ff`

## string_xrefs

- `0x18003b90f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_GetApplicationUserModelIdFromRpcClient(__int64 a1, __int64 a2)
{
  void **v3; // rax
  int RpcClientThreadToken; // eax
  int ApplicationUserModelIdFromToken; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v11; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE token; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+50h] [rbp-B0h] BYREF

  token = 0;
  v3 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&token);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v3);
  if ( RpcClientThreadToken < 0 )
    Log_HREvent_7(
      (unsigned int)RpcClientThreadToken,
      0,
      "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
      5663);
  memset_0(applicationUserModelId, 0, 0x106u);
  applicationUserModelIdLength = 131;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken && (unsigned int)dword_1800B3200 > 3 )
  {
    v11 = applicationUserModelId;
    if ( ApplicationUserModelIdFromToken > 0 )
      ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
    v10 = ApplicationUserModelIdFromToken;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)applicationUserModelId,
      (int)&dword_1800A7FFC,
      v6,
      v7,
      (__int64)&v10,
      (const unsigned __int16 **)&v11);
  }
  v8 = -1;
  do
    ++v8;
  while ( applicationUserModelId[v8] );
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
    a2,
    applicationUserModelId);
  if ( token )
    CloseHandle(token);
  return 0;
}

```

## disassembly

```asm
0x18003b8c0  mov     [rsp-8+arg_0], rbx
0x18003b8c5  mov     [rsp-8+arg_10], rdi
0x18003b8ca  push    rbp
0x18003b8cb  lea     rbp, [rsp-70h]
0x18003b8d0  sub     rsp, 170h
0x18003b8d7  mov     rax, cs:__security_cookie
0x18003b8de  xor     rax, rsp
0x18003b8e1  mov     [rbp+70h+var_10], rax
0x18003b8e5  xor     edi, edi
0x18003b8e7  lea     rcx, [rsp+170h+token]
0x18003b8ec  mov     [rsp+170h+token], rdi
0x18003b8f1  mov     rbx, rdx
0x18003b8f4  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x18003b8f9  mov     rdx, rax
0x18003b8fc  lea     ecx, [rdi+8]
0x18003b8ff  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x18003b905  test    eax, eax
0x18003b907  jns     short loc_18003B91F
0x18003b909  mov     r9d, 161Fh
0x18003b90f  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003b916  xor     edx, edx
0x18003b918  mov     ecx, eax
0x18003b91a  call    Log_HREvent_7
0x18003b91f  xor     edx, edx; Val
0x18003b921  lea     rcx, [rsp+170h+applicationUserModelId]; void *
0x18003b926  mov     r8d, 106h; Size
0x18003b92c  call    memset_0
0x18003b931  mov     rcx, [rsp+170h+token]; token
0x18003b936  lea     r8, [rsp+170h+applicationUserModelId]; applicationUserModelId
0x18003b93b  lea     rdx, [rsp+170h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18003b940  mov     [rsp+170h+applicationUserModelIdLength], 83h
0x18003b948  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18003b94e  test    eax, eax
0x18003b950  jz      short loc_18003B997
0x18003b952  mov     ecx, cs:dword_1800B3200
0x18003b958  cmp     ecx, 3
0x18003b95b  jbe     short loc_18003B997
0x18003b95d  lea     rcx, [rsp+170h+applicationUserModelId]
0x18003b962  mov     [rsp+170h+var_138], rcx
0x18003b967  test    eax, eax
0x18003b969  jle     short loc_18003B973
0x18003b96b  movzx   eax, ax
0x18003b96e  or      eax, 80070000h
0x18003b973  mov     [rsp+170h+var_140], eax
0x18003b977  lea     rdx, dword_1800A7FFC
0x18003b97e  lea     rax, [rsp+170h+var_138]
0x18003b983  mov     [rsp+170h+var_148], rax
0x18003b988  lea     rax, [rsp+170h+var_140]
0x18003b98d  mov     [rsp+170h+var_150], rax
0x18003b992  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003b997  lea     rax, [rsp+170h+applicationUserModelId]
0x18003b99c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b9a0  inc     r8
0x18003b9a3  cmp     [rax+r8*2], di
0x18003b9a8  jnz     short loc_18003B9A0
0x18003b9aa  lea     rdx, [rsp+170h+applicationUserModelId]
0x18003b9af  mov     rcx, rbx
0x18003b9b2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18003b9b7  mov     rcx, [rsp+170h+token]; hObject
0x18003b9bc  test    rcx, rcx
0x18003b9bf  jz      short loc_18003B9C7
0x18003b9c1  call    cs:__imp_CloseHandle
0x18003b9c7  xor     eax, eax
0x18003b9c9  mov     rcx, [rbp+70h+var_10]
0x18003b9cd  xor     rcx, rsp; StackCookie
0x18003b9d0  call    __security_check_cookie
0x18003b9d5  lea     r11, [rsp+170h+var_s0]
0x18003b9dd  mov     rbx, [r11+10h]
0x18003b9e1  mov     rdi, [r11+20h]
0x18003b9e5  mov     rsp, r11
0x18003b9e8  pop     rbp
0x18003b9e9  retn
```

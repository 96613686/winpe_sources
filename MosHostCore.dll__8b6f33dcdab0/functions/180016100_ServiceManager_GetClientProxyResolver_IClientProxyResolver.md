# ServiceManager::GetClientProxyResolver(IClientProxyResolver * *)

- ea: `0x180016100`
- end: `0x18001622f`
- name: `?GetClientProxyResolver@ServiceManager@@UEAAJPEAPEAUIClientProxyResolver@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, struct IClientProxyResolver **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x180003410`
- `0x180008e44`
- `0x180009a4c`
- `0x180009d0c`
- `0x180009db4`
- `0x180011694`
- `0x180013dc8`
- `0x180016100`
- `0x1800171fc`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800161e0`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800161e0`
- `ZTrace_Maps!ZTraceHelper` at `0x18001618e`
- `ZTrace_Maps!ZTraceHelper` at `0x18001618e`

## string_xrefs

- `0x18001616d`: `Proxy resolver requested. Token %s available.`
- `0x180016182`: `ServiceManager::GetClientProxyResolver`
- `0x1800161d7`: `ServiceManager::GetClientProxyResolver`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetClientProxyResolver(ServiceManager *this, struct IClientProxyResolver **a2)
{
  bool v4; // bl
  const char *v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int8 v7; // cl
  OfflineMapsTelemetry *v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  struct IClientProxyResolver *v11; // rax
  struct IClientProxyResolver *v13; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-30h] BYREF

  v13 = 0;
  ClientsTracker::GetLatestUserInfo((char *)this + 3816, v14);
  v4 = v14[0] && *(_QWORD *)v14[0];
  v5 = "is";
  if ( !v4 )
    v5 = "is NOT";
  ZTraceHelper(
    5,
    "ServiceManager::GetClientProxyResolver",
    4131,
    this,
    "Proxy resolver requested. Token %s available.",
    v5);
  if ( OfflineMapsTelemetry::IsEnabled(v7, v6) )
  {
    v8 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::ClientProxyResolverRequested_(v8, v4);
  }
  Microsoft::WRL::ComPtr<ClientProxyResolver>::InternalRelease(&v13);
  v9 = Microsoft::WRL::Details::MakeAndInitialize<ClientProxyResolver,ClientProxyResolver,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> &,std::wstring &>(
         &v13,
         v14,
         v15);
  if ( v9 >= 0 )
  {
    v10 = 0;
    v11 = v13;
    v13 = 0;
    *a2 = v11;
  }
  else
  {
    v10 = ZTraceReportPropagation(v9, "ServiceManager::GetClientProxyResolver", 4134, this);
  }
  ClientsTracker::ClientInfo::~ClientInfo((ClientsTracker::ClientInfo *)v14);
  Microsoft::WRL::ComPtr<ClientProxyResolver>::InternalRelease(&v13);
  return v10;
}

```

## disassembly

```asm
0x180016100  mov     r11, rsp
0x180016103  mov     [r11+18h], rbx
0x180016107  mov     [r11+20h], rsi
0x18001610b  push    rdi
0x18001610c  sub     rsp, 70h
0x180016110  mov     rax, cs:__security_cookie
0x180016117  xor     rax, rsp
0x18001611a  mov     [rsp+78h+var_10], rax
0x18001611f  mov     rsi, rdx
0x180016122  mov     rdi, rcx
0x180016125  mov     qword ptr [r11-48h], 0
0x18001612d  add     rcx, 0EE8h
0x180016134  lea     rdx, [r11-40h]
0x180016138  call    ?GetLatestUserInfo@ClientsTracker@@QEAA?AUClientInfo@1@XZ; ClientsTracker::GetLatestUserInfo(void)
0x18001613d  nop
0x18001613e  mov     rax, [rsp+78h+var_40]
0x180016143  test    rax, rax
0x180016146  jz      short loc_180016152
0x180016148  cmp     qword ptr [rax], 0
0x18001614c  jz      short loc_180016152
0x18001614e  mov     bl, 1
0x180016150  jmp     short loc_180016154
0x180016152  xor     bl, bl
0x180016154  lea     rcx, aIsNot; "is NOT"
0x18001615b  lea     rax, aIs; "is"
0x180016162  test    bl, bl
0x180016164  cmovz   rax, rcx
0x180016168  mov     [rsp+78h+var_50], rax
0x18001616d  lea     rax, aProxyResolverR; "Proxy resolver requested. Token %s avai"...
0x180016174  mov     [rsp+78h+var_58], rax
0x180016179  mov     r9, rdi
0x18001617c  mov     r8d, 1023h
0x180016182  lea     rdx, aServicemanager_63; "ServiceManager::GetClientProxyResolver"
0x180016189  mov     ecx, 5
0x18001618e  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180016194  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180016199  test    al, al
0x18001619b  jz      short loc_1800161AC
0x18001619d  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800161a2  mov     dl, bl; bool
0x1800161a4  mov     rcx, rax; this
0x1800161a7  call    ?ClientProxyResolverRequested_@OfflineMapsTelemetry@@QEAAX_N@Z; OfflineMapsTelemetry::ClientProxyResolverRequested_(bool)
0x1800161ac  lea     rcx, [rsp+78h+var_48]
0x1800161b1  call    ?InternalRelease@?$ComPtr@VClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ClientProxyResolver>::InternalRelease(void)
0x1800161b6  lea     r8, [rsp+78h+var_30]
0x1800161bb  lea     rdx, [rsp+78h+var_40]
0x1800161c0  lea     rcx, [rsp+78h+var_48]
0x1800161c5  call    ??$MakeAndInitialize@VClientProxyResolver@@V1@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAVClientProxyResolver@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ClientProxyResolver,ClientProxyResolver,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,std::wstring &>(ClientProxyResolver * *,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,std::wstring &)
0x1800161ca  test    eax, eax
0x1800161cc  jns     short loc_1800161EA
0x1800161ce  mov     r9, rdi
0x1800161d1  mov     r8d, 1026h
0x1800161d7  lea     rdx, aServicemanager_63; "ServiceManager::GetClientProxyResolver"
0x1800161de  mov     ecx, eax
0x1800161e0  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800161e6  mov     ebx, eax
0x1800161e8  jmp     short loc_1800161F9
0x1800161ea  xor     ebx, ebx
0x1800161ec  mov     rax, [rsp+78h+var_48]
0x1800161f1  mov     [rsp+78h+var_48], rbx
0x1800161f6  mov     [rsi], rax
0x1800161f9  lea     rcx, [rsp+78h+var_40]; this
0x1800161fe  call    ??1ClientInfo@ClientsTracker@@QEAA@XZ; ClientsTracker::ClientInfo::~ClientInfo(void)
0x180016203  nop
0x180016204  lea     rcx, [rsp+78h+var_48]
0x180016209  call    ?InternalRelease@?$ComPtr@VClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ClientProxyResolver>::InternalRelease(void)
0x18001620e  mov     eax, ebx
0x180016210  mov     rcx, [rsp+78h+var_10]
0x180016215  xor     rcx, rsp; StackCookie
0x180016218  call    __security_check_cookie
0x18001621d  lea     r11, [rsp+78h+var_8]
0x180016222  mov     rbx, [r11+20h]
0x180016226  mov     rsi, [r11+28h]
0x18001622a  mov     rsp, r11
0x18001622d  pop     rdi
0x18001622e  retn
```

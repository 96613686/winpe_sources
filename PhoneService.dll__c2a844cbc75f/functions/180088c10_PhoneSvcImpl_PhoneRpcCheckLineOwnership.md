# PhoneSvcImpl_PhoneRpcCheckLineOwnership

- ea: `0x180088c10`
- end: `0x180088e88`
- name: `PhoneSvcImpl_PhoneRpcCheckLineOwnership`
- size: `632`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800045b4`
- `0x180006e94`
- `0x180007750`
- `0x18004c2ac`
- `0x180086b10`
- `0x180088c10`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e5f`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180088cb8`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180088cb8`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x180088d15`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x180088d15`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180088c53`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180088c53`

## pseudocode

```c
__int64 __fastcall PhoneSvcImpl_PhoneRpcCheckLineOwnership(__int64 a1, __int64 a2)
{
  void **v3; // rax
  int RpcClientThreadToken; // eax
  BackTraceCollection *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r8
  int ApplicationUserModelIdFromToken; // eax
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  BackTraceCollection *v13; // rcx
  __int64 v14; // r8
  int v15; // eax
  BackTraceCollection *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rbx
  int v19; // eax
  BackTraceCollection *v20; // rcx
  unsigned int v21; // edi
  __int64 v22; // r8
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v24; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  struct ISecurityToken *v26; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 applicationUserModelIdLength[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+60h] [rbp-A0h] BYREF

  hObject = 0;
  v3 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&hObject);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v3);
  v6 = RpcClientThreadToken;
  if ( RpcClientThreadToken < 0 )
  {
    BackTraceCollection::Capture(v5, RpcClientThreadToken);
    Log_HREvent_31(v6, 1, v7, 727);
LABEL_3:
    if ( hObject )
      CloseHandle(hObject);
    return v6;
  }
  memset_0(applicationUserModelId, 0, 0x106u);
  applicationUserModelIdLength[0] = 131;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      hObject,
                                      applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken && (unsigned int)dword_1800B3200 > 3 )
  {
    v24 = applicationUserModelId;
    if ( ApplicationUserModelIdFromToken > 0 )
      ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
    LODWORD(v23) = ApplicationUserModelIdFromToken;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (unsigned int)applicationUserModelId,
      (unsigned int)&byte_1800AB537,
      v10,
      v11,
      (__int64)&v23,
      (__int64)&v24);
  }
  v26 = 0;
  v12 = CreatePerUserSecurityTokenForRpcClient(&v26);
  v6 = v12;
  if ( v12 < 0 )
  {
    BackTraceCollection::Capture(v13, v12);
    Log_HREvent_31(v6, 1, v14, 743);
LABEL_13:
    if ( v26 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v26 + 16LL))(v26);
    goto LABEL_3;
  }
  v23 = 0;
  v15 = WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(&g_phoneRpcServer);
  v6 = v15;
  if ( v15 < 0 )
  {
    BackTraceCollection::Capture(v16, v15);
    Log_HREvent_31(v6, 1, v17, 746);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    goto LABEL_13;
  }
  v18 = v23;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64, WCHAR *, struct ISecurityToken *))(*(_QWORD *)v23 + 816LL))(
          v23,
          a2,
          applicationUserModelId,
          v26);
  v21 = v19;
  if ( v19 >= 0 )
  {
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v26 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( hObject )
      CloseHandle(hObject);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v20, v19);
    Log_HREvent_31(v21, 1, v22, 747);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v26 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( hObject )
      CloseHandle(hObject);
    return v21;
  }
}

```

## disassembly

```asm
0x180088c10  mov     [rsp-8+arg_0], rbx
0x180088c15  mov     [rsp-8+arg_10], rdi
0x180088c1a  push    rbp
0x180088c1b  lea     rbp, [rsp-80h]
0x180088c20  sub     rsp, 180h
0x180088c27  mov     rax, cs:__security_cookie
0x180088c2e  xor     rax, rsp
0x180088c31  mov     [rbp+80h+var_10], rax
0x180088c35  lea     rcx, [rsp+180h+hObject]
0x180088c3a  mov     [rsp+180h+hObject], 0
0x180088c43  mov     rdi, rdx
0x180088c46  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x180088c4b  mov     rdx, rax
0x180088c4e  mov     ecx, 8
0x180088c53  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x180088c59  mov     ebx, eax
0x180088c5b  test    eax, eax
0x180088c5d  jns     short loc_180088C8F
0x180088c5f  mov     edx, eax; int
0x180088c61  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180088c66  mov     edx, 1
0x180088c6b  mov     r9d, 2D7h
0x180088c71  mov     ecx, ebx
0x180088c73  call    Log_HREvent_31
0x180088c78  mov     rcx, [rsp+180h+hObject]; hObject
0x180088c7d  test    rcx, rcx
0x180088c80  jz      short loc_180088C88
0x180088c82  call    cs:__imp_CloseHandle
0x180088c88  mov     eax, ebx
0x180088c8a  jmp     loc_180088E67
0x180088c8f  xor     edx, edx; Val
0x180088c91  lea     rcx, [rsp+180h+applicationUserModelId]; void *
0x180088c96  mov     r8d, 106h; Size
0x180088c9c  call    memset_0
0x180088ca1  mov     rcx, [rsp+180h+hObject]; token
0x180088ca6  lea     r8, [rsp+180h+applicationUserModelId]; applicationUserModelId
0x180088cab  lea     rdx, [rsp+180h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180088cb0  mov     [rsp+180h+applicationUserModelIdLength], 83h
0x180088cb8  call    cs:__imp_GetApplicationUserModelIdFromToken
0x180088cbe  test    eax, eax
0x180088cc0  jz      short loc_180088D07
0x180088cc2  mov     ecx, cs:dword_1800B3200
0x180088cc8  cmp     ecx, 3
0x180088ccb  jbe     short loc_180088D07
0x180088ccd  lea     rcx, [rsp+180h+applicationUserModelId]
0x180088cd2  mov     [rsp+180h+var_148], rcx
0x180088cd7  test    eax, eax
0x180088cd9  jle     short loc_180088CE3
0x180088cdb  movzx   eax, ax
0x180088cde  or      eax, 80070000h
0x180088ce3  mov     dword ptr [rsp+180h+var_150], eax
0x180088ce7  lea     rdx, byte_1800AB537
0x180088cee  lea     rax, [rsp+180h+var_148]
0x180088cf3  mov     [rsp+180h+var_158], rax
0x180088cf8  lea     rax, [rsp+180h+var_150]
0x180088cfd  mov     [rsp+180h+var_160], rax
0x180088d02  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180088d07  lea     rcx, [rsp+180h+var_138]
0x180088d0c  mov     [rsp+180h+var_138], 0
0x180088d15  call    cs:__imp_?CreatePerUserSecurityTokenForRpcClient@@YAJPEAPEAUISecurityToken@@@Z; CreatePerUserSecurityTokenForRpcClient(ISecurityToken * *)
0x180088d1b  mov     ebx, eax
0x180088d1d  test    eax, eax
0x180088d1f  jns     short loc_180088D59
0x180088d21  mov     edx, eax; int
0x180088d23  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180088d28  mov     edx, 1
0x180088d2d  mov     r9d, 2E7h
0x180088d33  mov     ecx, ebx
0x180088d35  call    Log_HREvent_31
0x180088d3a  mov     rcx, [rsp+180h+var_138]
0x180088d3f  test    rcx, rcx
0x180088d42  jz      loc_180088C78
0x180088d48  mov     rax, [rcx]
0x180088d4b  mov     rax, [rax+10h]
0x180088d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d54  jmp     loc_180088C78
0x180088d59  lea     rdx, [rsp+180h+var_150]
0x180088d5e  mov     [rsp+180h+var_150], 0
0x180088d67  lea     rcx, ?g_phoneRpcServer@@3VSecurePhoneRpcServer@@A; lpCriticalSection
0x180088d6e  call    ?Get@?$WrappedComPtrBase@UIPhoneController@@VDoesNotSupportShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneController@@@Z; WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(IPhoneController * *)
0x180088d73  mov     ebx, eax
0x180088d75  test    eax, eax
0x180088d77  jns     short loc_180088DAA
0x180088d79  mov     edx, eax; int
0x180088d7b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180088d80  mov     edx, 1
0x180088d85  mov     r9d, 2EAh
0x180088d8b  mov     ecx, ebx
0x180088d8d  call    Log_HREvent_31
0x180088d92  mov     rcx, [rsp+180h+var_150]
0x180088d97  test    rcx, rcx
0x180088d9a  jz      short loc_180088D3A
0x180088d9c  mov     rax, [rcx]
0x180088d9f  mov     rax, [rax+10h]
0x180088da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088da8  jmp     short loc_180088D3A
0x180088daa  mov     rbx, [rsp+180h+var_150]
0x180088daf  lea     r8, [rsp+180h+applicationUserModelId]
0x180088db4  mov     r9, [rsp+180h+var_138]
0x180088db9  mov     rdx, rdi
0x180088dbc  mov     rcx, rbx
0x180088dbf  mov     rax, [rbx]
0x180088dc2  mov     rax, [rax+330h]
0x180088dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088dce  mov     edi, eax
0x180088dd0  test    eax, eax
0x180088dd2  jns     short loc_180088E2B
0x180088dd4  mov     edx, eax; int
0x180088dd6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180088ddb  mov     edx, 1
0x180088de0  mov     r9d, 2EBh
0x180088de6  mov     ecx, edi
0x180088de8  call    Log_HREvent_31
0x180088ded  test    rbx, rbx
0x180088df0  jz      short loc_180088E01
0x180088df2  mov     rcx, [rbx]
0x180088df5  mov     rax, [rcx+10h]
0x180088df9  mov     rcx, rbx
0x180088dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e01  mov     rcx, [rsp+180h+var_138]
0x180088e06  test    rcx, rcx
0x180088e09  jz      short loc_180088E17
0x180088e0b  mov     rax, [rcx]
0x180088e0e  mov     rax, [rax+10h]
0x180088e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e17  mov     rcx, [rsp+180h+hObject]; hObject
0x180088e1c  test    rcx, rcx
0x180088e1f  jz      short loc_180088E27
0x180088e21  call    cs:__imp_CloseHandle
0x180088e27  mov     eax, edi
0x180088e29  jmp     short loc_180088E67
0x180088e2b  test    rbx, rbx
0x180088e2e  jz      short loc_180088E3F
0x180088e30  mov     rax, [rbx]
0x180088e33  mov     rcx, rbx
0x180088e36  mov     rax, [rax+10h]
0x180088e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e3f  mov     rcx, [rsp+180h+var_138]
0x180088e44  test    rcx, rcx
0x180088e47  jz      short loc_180088E55
0x180088e49  mov     rax, [rcx]
0x180088e4c  mov     rax, [rax+10h]
0x180088e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e55  mov     rcx, [rsp+180h+hObject]; hObject
0x180088e5a  test    rcx, rcx
0x180088e5d  jz      short loc_180088E65
0x180088e5f  call    cs:__imp_CloseHandle
0x180088e65  xor     eax, eax
0x180088e67  mov     rcx, [rbp+80h+var_10]
0x180088e6b  xor     rcx, rsp; StackCookie
0x180088e6e  call    __security_check_cookie
0x180088e73  lea     r11, [rsp+180h+var_s0]
0x180088e7b  mov     rbx, [r11+10h]
0x180088e7f  mov     rdi, [r11+20h]
0x180088e83  mov     rsp, r11
0x180088e86  pop     rbp
0x180088e87  retn
```

# PhoneRpcNotifyHandle_rundown

- ea: `0x180087c30`
- end: `0x1800880e8`
- name: `PhoneRpcNotifyHandle_rundown`
- size: `1208`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800012b8`
- `0x18000151c`
- `0x180004370`
- `0x1800047d0`
- `0x180004f20`
- `0x1800056a0`
- `0x18000c058`
- `0x18000c960`
- `0x18004c2ac`
- `0x180080894`
- `0x180085c64`
- `0x180086b10`
- `0x180087a78`
- `0x180087c30`
- `0x18008c870`
- `0x18008d94e`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087cf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087cf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087d27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087d53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087d27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ebd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180087eb3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180087eb3`
- `PhoneUtil!CreatePerUserSecurityToken` at `0x180087ef1`
- `PhoneUtil!CreatePerUserSecurityToken` at `0x180087ef1`

## string_xrefs

- `0x180087d0e`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x180087ca2`: `PublicPhoneRpc: Phone service listener rundown.`
- `0x180087f92`: `Remove rpcClient from map as no more handles.`

## pseudocode

```c
__int64 __fastcall PhoneRpcNotifyHandle_rundown(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  PhoneNotificationManager *v5; // rdi
  __int64 v6; // r8
  int ListenerIdentity; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rsi
  const char *v14; // rax
  unsigned __int16 *v15; // r15
  unsigned __int16 *v16; // r14
  __int64 v17; // r12
  __int64 v18; // r13
  signed int LastError; // eax
  __int64 v20; // r8
  int PerUserSecurityToken; // eax
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r14
  int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r15
  __int64 v33; // [rsp+50h] [rbp-79h] BYREF
  const char *v34; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR v35; // [rsp+60h] [rbp-69h] BYREF
  LPCWSTR v36; // [rsp+68h] [rbp-61h] BYREF
  __int64 v37; // [rsp+70h] [rbp-59h] BYREF
  PSID Sid; // [rsp+78h] [rbp-51h] BYREF
  __int64 v39; // [rsp+80h] [rbp-49h] BYREF
  LPCWSTR StringSid[2]; // [rsp+90h] [rbp-39h] BYREF
  _WORD v41[8]; // [rsp+A0h] [rbp-29h] BYREF
  void *Block[2]; // [rsp+B0h] [rbp-19h] BYREF
  _WORD v43[8]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v44; // [rsp+130h] [rbp+67h] BYREF

  v44 = a1;
  if ( (unsigned int)dword_1800B3200 > 3
    && (qword_1800B3210 & 0x200000000000LL) != 0
    && (qword_1800B3218 & 0x200000000000LL) == qword_1800B3218 )
  {
    LODWORD(v33) = v44;
    v37 = 2048;
    Sid = "PublicPhoneRpc: Phone service listener rundown.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (int)&dword_1800B3200,
      (int)byte_1800AB383,
      a3,
      a4,
      (const unsigned __int16 **)&Sid,
      (__int64)&v33,
      (__int64)&v37);
  }
  v4 = v44;
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
  EnterCriticalSection(&stru_1800B4150);
  v5 = qword_1800B4178;
  if ( qword_1800B4178 )
  {
    (*(void (__fastcall **)(PhoneNotificationManager *))(*(_QWORD *)qword_1800B4178 + 8LL))(qword_1800B4178);
    LeaveCriticalSection(&stru_1800B4150);
    StringSid[0] = v41;
    StringSid[1] = v41;
    v41[0] = 0;
    Block[0] = v43;
    Block[1] = v43;
    v43[0] = 0;
    ListenerIdentity = PhoneNotificationManager::GetListenerIdentity(v5, v4, StringSid, Block);
    if ( ListenerIdentity < 0 )
      Log_HREvent_31((unsigned int)ListenerIdentity, 0, v9, 1068);
    v37 = 0;
    utl::_HashTable<PhoneServiceListenerIdentity::RpcClientIdentity,utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>,PhoneServiceListenerIdentity::HasherRpcClientIdentity,utl::equal_to<PhoneServiceListenerIdentity::RpcClientIdentity>,utl::allocator<utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>>,0>::find<void>(
      v8,
      &v37,
      StringSid);
    v13 = v37;
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v14 = "rpcClient found from map.";
      LOBYTE(v10) = v37 != (_QWORD)&off_1800B3460;
      if ( (_UNKNOWN **)v37 == &off_1800B3460 )
        v14 = "rpcClient not found from map.";
      v37 = (__int64)v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (int)&unk_1800AB2E8,
        v11,
        v12,
        (const unsigned __int16 **)&v37);
    }
    if ( (_UNKNOWN **)v13 != &off_1800B3460 )
    {
      v15 = *(unsigned __int16 **)(v13 + 96);
      v16 = *(unsigned __int16 **)(v13 + 88);
      v34 = (const char *)v16;
      while ( v16 != v15 )
      {
        if ( *(_QWORD *)v16 == v44 )
        {
          if ( (unsigned int)dword_1800B3200 > 4 )
          {
            LODWORD(v33) = *(_DWORD *)v16;
            v37 = (__int64)"Found listener in rpcClient map.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v10,
              (int)byte_1800AB315,
              v11,
              v12,
              (const unsigned __int16 **)&v37,
              (__int64)&v33);
          }
          memmove_0(v16, v16 + 4, (*(_QWORD *)(v13 + 96) - (_QWORD)v16 - 8LL) & 0xFFFFFFFFFFFFFFF8uLL);
          *(_QWORD *)(v13 + 96) -= 8LL;
          v17 = *(_QWORD *)(v13 + 96);
          v18 = *(_QWORD *)(v13 + 88);
          if ( v18 == v17 )
          {
            Sid = 0;
            if ( ConvertStringSidToSidW(StringSid[0], &Sid) )
            {
              v37 = 0;
              PerUserSecurityToken = CreatePerUserSecurityToken(Sid, 0, (struct ISecurityToken **)&v37);
              if ( PerUserSecurityToken >= 0 )
              {
                v39 = 0;
                v23 = WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(&g_phoneRpcServer);
                v25 = v39;
                if ( v23 >= 0 )
                {
                  v26 = (*(__int64 (__fastcall **)(__int64, __int64, void *, __int64))(*(_QWORD *)v39 + 808LL))(
                          v39,
                          1,
                          Block[0],
                          v37);
                  if ( v26 < 0 )
                    Log_HREvent_31((unsigned int)v26, 0, v27, 1117);
                }
                utl::_HashTable<PhoneServiceListenerIdentity::RpcClientIdentity,utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>,PhoneServiceListenerIdentity::HasherRpcClientIdentity,utl::equal_to<PhoneServiceListenerIdentity::RpcClientIdentity>,utl::allocator<utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>>,0>::erase(
                  v24,
                  &v35,
                  v13);
                if ( (unsigned int)dword_1800B3200 > 4 )
                {
                  v31 = (char *)v15 - v34;
                  v36 = StringSid[0];
                  v35 = (LPCWSTR)Block[0];
                  v34 = "Remove rpcClient from map as no more handles.";
                  LODWORD(v33) = (v17 - v18) >> 3;
                  LODWORD(v39) = v31 >> 3;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                    v28,
                    (int)&byte_1800AB277,
                    v29,
                    v30,
                    (const unsigned __int16 **)&v34,
                    (__int64)&v39,
                    (__int64)&v33,
                    &v35,
                    &v36);
                }
                if ( v25 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              }
              else
              {
                Log_HREvent_31((unsigned int)PerUserSecurityToken, 0, v22, 1109);
              }
              if ( v37 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            }
            else
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              Log_HREvent_31((unsigned int)LastError, 0, v20, 1101);
            }
            if ( Sid )
              _HeapFreer<_SID>(Sid);
          }
          goto LABEL_42;
        }
        v16 += 4;
      }
      if ( (unsigned int)dword_1800B3200 > 3 )
      {
        v35 = StringSid[0];
        v36 = (LPCWSTR)Block[0];
        v34 = "listener handle not found from map for the identified rpcClient.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v10,
          (int)&word_1800AB23E,
          v11,
          v12,
          (const unsigned __int16 **)&v34,
          &v36,
          &v35);
      }
    }
LABEL_42:
    if ( Block[0] != v43 )
      operator delete(Block[0]);
    if ( StringSid[0] != v41 )
      operator delete((void *)StringSid[0]);
    if ( v5 )
      (*(void (__fastcall **)(PhoneNotificationManager *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    Log_HREvent_28(2147947423LL, 0, "onecoreuap\\private\\net\\inc\\phone\\RevokableComPtr.h", 140);
    LeaveCriticalSection(&stru_1800B4150);
    Log_HREvent_31(2147947423LL, 0, v6, 1064);
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return PhoneSvcImpl_PhoneRpcUnadvise(&v44);
}

```

## disassembly

```asm
0x180087c30  mov     [rsp-8+arg_0], rcx
0x180087c35  push    rbp
0x180087c36  push    rbx
0x180087c37  push    rsi
0x180087c38  push    rdi
0x180087c39  push    r12
0x180087c3b  push    r13
0x180087c3d  push    r14
0x180087c3f  push    r15
0x180087c41  lea     rbp, [rsp-1Fh]
0x180087c46  sub     rsp, 0E8h
0x180087c4d  mov     rax, cs:__security_cookie
0x180087c54  xor     rax, rsp
0x180087c57  mov     [rbp+57h+var_50], rax
0x180087c5b  mov     eax, cs:dword_1800B3200
0x180087c61  cmp     eax, 3
0x180087c64  jbe     short loc_180087CD5
0x180087c66  mov     rcx, cs:qword_1800B3218
0x180087c6d  mov     rdx, 200000000000h
0x180087c77  mov     rax, cs:qword_1800B3210
0x180087c7e  test    rdx, rax
0x180087c81  jz      short loc_180087CD5
0x180087c83  mov     rax, rcx
0x180087c86  and     rax, rdx
0x180087c89  cmp     rax, rcx
0x180087c8c  jnz     short loc_180087CD5
0x180087c8e  mov     eax, dword ptr [rbp+57h+arg_0]
0x180087c91  lea     rdx, byte_1800AB383
0x180087c98  mov     dword ptr [rbp+57h+var_D0], eax
0x180087c9b  lea     rcx, dword_1800B3200; int
0x180087ca2  lea     rax, aPublicphonerpc_2; "PublicPhoneRpc: Phone service listener "...
0x180087ca9  mov     [rbp+57h+var_B0], 800h
0x180087cb1  mov     [rbp+57h+Sid], rax
0x180087cb5  lea     rax, [rbp+57h+var_B0]
0x180087cb9  mov     [rsp+120h+var_F0], rax; __int64
0x180087cbe  lea     rax, [rbp+57h+var_D0]
0x180087cc2  mov     [rsp+120h+var_F8], rax; __int64
0x180087cc7  lea     rax, [rbp+57h+Sid]
0x180087ccb  mov     [rsp+120h+var_100], rax; __int64
0x180087cd0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180087cd5  mov     rbx, [rbp+57h+arg_0]
0x180087cd9  test    rbx, rbx
0x180087cdc  jz      short loc_180087CED
0x180087cde  mov     rax, [rbx]
0x180087ce1  mov     rcx, rbx
0x180087ce4  mov     rax, [rax+8]
0x180087ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ced  lea     rsi, stru_1800B4150
0x180087cf4  mov     rcx, rsi; lpCriticalSection
0x180087cf7  call    cs:__imp_EnterCriticalSection
0x180087cfd  mov     rdi, cs:qword_1800B4178
0x180087d04  test    rdi, rdi
0x180087d07  jnz     short loc_180087D41
0x180087d09  mov     edi, 8007139Fh
0x180087d0e  lea     r8, aOnecoreuapPriv_3; "onecoreuap\\private\\net\\inc\\phone\\R"...
0x180087d15  mov     ecx, edi
0x180087d17  mov     r9d, 8Ch
0x180087d1d  xor     edx, edx
0x180087d1f  call    Log_HREvent_28
0x180087d24  mov     rcx, rsi; lpCriticalSection
0x180087d27  call    cs:__imp_LeaveCriticalSection
0x180087d2d  xor     edx, edx
0x180087d2f  mov     r9d, 428h
0x180087d35  mov     ecx, edi
0x180087d37  call    Log_HREvent_31
0x180087d3c  jmp     loc_1800880AB
0x180087d41  mov     rax, [rdi]
0x180087d44  mov     rcx, rdi
0x180087d47  mov     rax, [rax+8]
0x180087d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d50  mov     rcx, rsi; lpCriticalSection
0x180087d53  call    cs:__imp_LeaveCriticalSection
0x180087d59  lea     rax, [rbp+57h+var_80]
0x180087d5d  mov     rdx, rbx
0x180087d60  mov     [rbp+57h+StringSid], rax
0x180087d64  lea     r9, [rbp+57h+Block]
0x180087d68  lea     rax, [rbp+57h+var_80]
0x180087d6c  mov     rcx, rdi
0x180087d6f  mov     [rbp+57h+var_88], rax
0x180087d73  lea     r8, [rbp+57h+StringSid]
0x180087d77  xor     eax, eax
0x180087d79  mov     [rbp+57h+var_80], ax
0x180087d7d  lea     rax, [rbp+57h+var_60]
0x180087d81  mov     [rbp+57h+Block], rax
0x180087d85  lea     rax, [rbp+57h+var_60]
0x180087d89  mov     [rbp+57h+var_68], rax
0x180087d8d  xor     eax, eax
0x180087d8f  mov     [rbp+57h+var_60], ax
0x180087d93  call    ?GetListenerIdentity@PhoneNotificationManager@@QEAAJPEAUIPhoneServiceListener@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@1@Z; PhoneNotificationManager::GetListenerIdentity(IPhoneServiceListener *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180087d98  test    eax, eax
0x180087d9a  jns     short loc_180087DAB
0x180087d9c  xor     edx, edx
0x180087d9e  mov     r9d, 42Ch
0x180087da4  mov     ecx, eax
0x180087da6  call    Log_HREvent_31
0x180087dab  lea     r8, [rbp+57h+StringSid]
0x180087daf  mov     [rbp+57h+var_B0], 0
0x180087db7  lea     rdx, [rbp+57h+var_B0]
0x180087dbb  call    ??$find@X@?$_HashTable@URpcClientIdentity@PhoneServiceListenerIdentity@@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@utl@@VHasherRpcClientIdentity@2@U?$equal_to@URpcClientIdentity@PhoneServiceListenerIdentity@@@4@V?$allocator@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@utl@@@4@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@utl@@@utl@@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@2@@1@AEBURpcClientIdentity@PhoneServiceListenerIdentity@@@Z; utl::_HashTable<PhoneServiceListenerIdentity::RpcClientIdentity,utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>,PhoneServiceListenerIdentity::HasherRpcClientIdentity,utl::equal_to<PhoneServiceListenerIdentity::RpcClientIdentity>,utl::allocator<utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>>,0>::find<void>(PhoneServiceListenerIdentity::RpcClientIdentity const &)
0x180087dc0  mov     eax, cs:dword_1800B3200
0x180087dc6  lea     r14, off_1800B3460
0x180087dcd  mov     rsi, [rbp+57h+var_B0]
0x180087dd1  cmp     eax, 4
0x180087dd4  jbe     short loc_180087E09
0x180087dd6  cmp     rsi, r14
0x180087dd9  lea     rdx, aRpcclientNotFo; "rpcClient not found from map."
0x180087de0  lea     rax, aRpcclientFound; "rpcClient found from map."
0x180087de7  setnz   cl
0x180087dea  test    cl, cl
0x180087dec  cmovz   rax, rdx
0x180087df0  lea     rdx, unk_1800AB2E8
0x180087df7  mov     [rbp+57h+var_B0], rax
0x180087dfb  lea     rax, [rbp+57h+var_B0]
0x180087dff  mov     [rsp+120h+var_100], rax
0x180087e04  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180087e09  cmp     rsi, r14
0x180087e0c  jz      loc_180088065
0x180087e12  mov     rax, [rsi+58h]
0x180087e16  mov     r15, [rsi+60h]
0x180087e1a  mov     r14, rax
0x180087e1d  mov     [rbp+57h+var_C8], rax
0x180087e21  mov     rax, [rbp+57h+arg_0]
0x180087e25  cmp     r14, r15
0x180087e28  jz      loc_180088018
0x180087e2e  cmp     [r14], rax
0x180087e31  jz      short loc_180087E39
0x180087e33  add     r14, 8
0x180087e37  jmp     short loc_180087E25
0x180087e39  mov     eax, cs:dword_1800B3200
0x180087e3f  cmp     eax, 4
0x180087e42  jbe     short loc_180087E73
0x180087e44  mov     eax, [r14]
0x180087e47  lea     rdx, byte_1800AB315
0x180087e4e  mov     dword ptr [rbp+57h+var_D0], eax
0x180087e51  lea     rax, aFoundListenerI; "Found listener in rpcClient map."
0x180087e58  mov     [rbp+57h+var_B0], rax
0x180087e5c  lea     rax, [rbp+57h+var_D0]
0x180087e60  mov     [rsp+120h+var_F8], rax
0x180087e65  lea     rax, [rbp+57h+var_B0]
0x180087e69  mov     [rsp+120h+var_100], rax
0x180087e6e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180087e73  mov     r8, [rsi+60h]
0x180087e77  lea     rdx, [r14+8]; Src
0x180087e7b  sub     r8, r14
0x180087e7e  mov     rcx, r14; void *
0x180087e81  sub     r8, 8
0x180087e85  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180087e89  call    memmove_0
0x180087e8e  add     qword ptr [rsi+60h], 0FFFFFFFFFFFFFFF8h
0x180087e93  mov     r12, [rsi+60h]
0x180087e97  mov     r13, [rsi+58h]
0x180087e9b  cmp     r13, r12
0x180087e9e  jnz     loc_180088065
0x180087ea4  mov     rcx, [rbp+57h+StringSid]; StringSid
0x180087ea8  lea     rdx, [rbp+57h+Sid]; Sid
0x180087eac  xor     r14d, r14d
0x180087eaf  mov     [rbp+57h+Sid], r14
0x180087eb3  call    cs:__imp_ConvertStringSidToSidW
0x180087eb9  test    eax, eax
0x180087ebb  jnz     short loc_180087EE3
0x180087ebd  call    cs:__imp_GetLastError
0x180087ec3  test    eax, eax
0x180087ec5  jle     short loc_180087ECF
0x180087ec7  movzx   eax, ax
0x180087eca  or      eax, 80070000h
0x180087ecf  xor     edx, edx
0x180087ed1  mov     r9d, 44Dh
0x180087ed7  mov     ecx, eax
0x180087ed9  call    Log_HREvent_31
0x180087ede  jmp     loc_180088008
0x180087ee3  mov     rcx, [rbp+57h+Sid]
0x180087ee7  lea     r8, [rbp+57h+var_B0]
0x180087eeb  xor     edx, edx
0x180087eed  mov     [rbp+57h+var_B0], r14
0x180087ef1  call    cs:__imp_?CreatePerUserSecurityToken@@YAJPEAXPEAU_TOKEN_GROUPS@@PEAPEAUISecurityToken@@@Z; CreatePerUserSecurityToken(void *,_TOKEN_GROUPS *,ISecurityToken * *)
0x180087ef7  test    eax, eax
0x180087ef9  jns     short loc_180087F0F
0x180087efb  xor     edx, edx
0x180087efd  mov     r9d, 455h
0x180087f03  mov     ecx, eax
0x180087f05  call    Log_HREvent_31
0x180087f0a  jmp     loc_180087FF3
0x180087f0f  lea     rdx, [rbp+57h+var_A0]
0x180087f13  mov     [rbp+57h+var_A0], r14
0x180087f17  lea     rcx, ?g_phoneRpcServer@@3VSecurePhoneRpcServer@@A; lpCriticalSection
0x180087f1e  call    ?Get@?$WrappedComPtrBase@UIPhoneController@@VDoesNotSupportShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneController@@@Z; WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(IPhoneController * *)
0x180087f23  mov     r14, [rbp+57h+var_A0]
0x180087f27  test    eax, eax
0x180087f29  js      short loc_180087F5D
0x180087f2b  mov     rax, [r14]
0x180087f2e  mov     edx, 1
0x180087f33  mov     r9, [rbp+57h+var_B0]
0x180087f37  mov     rcx, r14
0x180087f3a  mov     r8, [rbp+57h+Block]
0x180087f3e  mov     rax, [rax+328h]
0x180087f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f4a  test    eax, eax
0x180087f4c  jns     short loc_180087F5D
0x180087f4e  xor     edx, edx
0x180087f50  mov     r9d, 45Dh
0x180087f56  mov     ecx, eax
0x180087f58  call    Log_HREvent_31
0x180087f5d  mov     r8, rsi
0x180087f60  lea     rdx, [rbp+57h+var_C0]
0x180087f64  call    ?erase@?$_HashTable@URpcClientIdentity@PhoneServiceListenerIdentity@@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@utl@@VHasherRpcClientIdentity@2@U?$equal_to@URpcClientIdentity@PhoneServiceListenerIdentity@@@4@V?$allocator@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@utl@@@4@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@utl@@@utl@@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@2@@2@V?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@utl@@@utl@@U?$pair@$$CBURpcClientIdentity@PhoneServiceListenerIdentity@@V?$vector@PEAU__MIDL_PublicPhoneRpc_0001@@V?$allocator@PEAU__MIDL_PublicPhoneRpc_0001@@@utl@@@utl@@@2@@2@@Z; utl::_HashTable<PhoneServiceListenerIdentity::RpcClientIdentity,utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>,PhoneServiceListenerIdentity::HasherRpcClientIdentity,utl::equal_to<PhoneServiceListenerIdentity::RpcClientIdentity>,utl::allocator<utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>>,0>::erase(utl::_DlistConstIt<utl::_HashNode<utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>>,utl::pair<PhoneServiceListenerIdentity::RpcClientIdentity const,utl::vector<__MIDL_PublicPhoneRpc_0001 *,utl::allocator<__MIDL_PublicPhoneRpc_0001 *>>>>)
0x180087f69  mov     eax, cs:dword_1800B3200
0x180087f6f  cmp     eax, 4
0x180087f72  jbe     short loc_180087FDF
0x180087f74  mov     rax, [rbp+57h+StringSid]
0x180087f78  lea     rdx, byte_1800AB277
0x180087f7f  sub     r15, [rbp+57h+var_C8]
0x180087f83  sub     r12, r13
0x180087f86  mov     [rbp+57h+var_B8], rax
0x180087f8a  mov     rax, [rbp+57h+Block]
0x180087f8e  mov     [rbp+57h+var_C0], rax
0x180087f92  lea     rax, aRemoveRpcclien; "Remove rpcClient from map as no more ha"...
0x180087f99  mov     [rbp+57h+var_C8], rax
0x180087f9d  lea     rax, [rbp+57h+var_B8]
0x180087fa1  mov     [rsp+120h+var_E0], rax
0x180087fa6  lea     rax, [rbp+57h+var_C0]
0x180087faa  mov     [rsp+120h+var_E8], rax
0x180087faf  lea     rax, [rbp+57h+var_D0]
0x180087fb3  mov     [rsp+120h+var_F0], rax
0x180087fb8  lea     rax, [rbp+57h+var_A0]
0x180087fbc  mov     [rsp+120h+var_F8], rax
0x180087fc1  lea     rax, [rbp+57h+var_C8]
0x180087fc5  sar     r12, 3
0x180087fc9  sar     r15, 3
0x180087fcd  mov     [rsp+120h+var_100], rax
0x180087fd2  mov     dword ptr [rbp+57h+var_D0], r12d
0x180087fd6  mov     dword ptr [rbp+57h+var_A0], r15d
0x180087fda  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180087fdf  test    r14, r14
0x180087fe2  jz      short loc_180087FF3
0x180087fe4  mov     rax, [r14]
0x180087fe7  mov     rcx, r14
0x180087fea  mov     rax, [rax+10h]
0x180087fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ff3  mov     rcx, [rbp+57h+var_B0]
0x180087ff7  test    rcx, rcx
0x180087ffa  jz      short loc_180088008
0x180087ffc  mov     rax, [rcx]
0x180087fff  mov     rax, [rax+10h]
0x180088003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088008  mov     rcx, [rbp+57h+Sid]
0x18008800c  test    rcx, rcx
0x18008800f  jz      short loc_180088065
0x180088011  call    ??$_HeapFreer@U_SID@@@@YAXPEAU_SID@@@Z; _HeapFreer<_SID>(_SID *)
0x180088016  jmp     short loc_180088065
0x180088018  mov     eax, cs:dword_1800B3200
0x18008801e  cmp     eax, 3
0x180088021  jbe     short loc_180088065
0x180088023  mov     rax, [rbp+57h+StringSid]
0x180088027  lea     rdx, word_1800AB23E
0x18008802e  mov     [rbp+57h+var_C0], rax
0x180088032  mov     rax, [rbp+57h+Block]
0x180088036  mov     [rbp+57h+var_B8], rax
0x18008803a  lea     rax, aListenerHandle; "listener handle not found from map for "...
0x180088041  mov     [rbp+57h+var_C8], rax
0x180088045  lea     rax, [rbp+57h+var_C0]
0x180088049  mov     [rsp+120h+var_F0], rax
0x18008804e  lea     rax, [rbp+57h+var_B8]
0x180088052  mov     [rsp+120h+var_F8], rax
0x180088057  lea     rax, [rbp+57h+var_C8]
0x18008805b  mov     [rsp+120h+var_100], rax
0x180088060  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180088065  mov     rcx, [rbp+57h+Block]; Block
0x180088069  lea     rax, [rbp+57h+var_60]
0x18008806d  cmp     rcx, rax
0x180088070  jz      short loc_18008807E
0x180088072  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180088079  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008807e  mov     rcx, [rbp+57h+StringSid]; Block
0x180088082  lea     rax, [rbp+57h+var_80]
0x180088086  cmp     rcx, rax
0x180088089  jz      short loc_180088097
0x18008808b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180088092  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180088097  test    rdi, rdi
0x18008809a  jz      short loc_1800880AB
0x18008809c  mov     rax, [rdi]
0x18008809f  mov     rcx, rdi
0x1800880a2  mov     rax, [rax+10h]
0x1800880a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800880ab  test    rbx, rbx
0x1800880ae  jz      short loc_1800880BF
0x1800880b0  mov     rax, [rbx]
0x1800880b3  mov     rcx, rbx
0x1800880b6  mov     rax, [rax+10h]
0x1800880ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800880bf  lea     rcx, [rbp+57h+arg_0]
0x1800880c3  call    PhoneSvcImpl_PhoneRpcUnadvise
0x1800880c8  mov     rcx, [rbp+57h+var_50]
0x1800880cc  xor     rcx, rsp; StackCookie
0x1800880cf  call    __security_check_cookie
0x1800880d4  add     rsp, 0E8h
0x1800880db  pop     r15
0x1800880dd  pop     r14
0x1800880df  pop     r13
0x1800880e1  pop     r12
  ... truncated ...
```

# DiscoverApi::AsyncRepairCallback(_DISCOVERY_METADATA *,struct_dsreg_server_response,unsigned __int64,long)

- ea: `0x180092b20`
- end: `0x180092f64`
- name: `?AsyncRepairCallback@DiscoverApi@@CAXPEAU_DISCOVERY_METADATA@@Ustruct_dsreg_server_response@@_KJ@Z`
- size: `1092`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callees

- `0x180001cfc`
- `0x1800025e8`
- `0x1800878c4`
- `0x180087b58`
- `0x180088388`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008b0e0`
- `0x18008b1b8`
- `0x18008c778`
- `0x18008e124`
- `0x1800929f8`
- `0x180092b20`
- `0x180093cf8`
- `0x180094390`
- `0x1800a8010`

## string_xrefs

- `0x180092b4b`: `DiscoverApi::AsyncRepairCallback`
- `0x180092c74`: `DiscoverApi::AsyncRepairCallback`
- `0x180092ca3`: `DiscoverApi::AsyncRepairCallback`
- `0x180092cb7`: `DiscoverApi::AsyncRepairCallback`
- `0x180092d27`: `DiscoverApi::AsyncRepairCallback`
- `0x180092d9f`: `DiscoverApi::AsyncRepairCallback`
- `0x180092ed1`: `DiscoverApi::AsyncRepairCallback`
- `0x180092f2c`: `DiscoverApi::AsyncRepairCallback`
- `0x180092cbe`: `%s: Flushed repaire join info into registry`
- `0x180092d2e`: `%s: Repair join info callback succeeded. Tenant ID: "%s", Device ID: "%s", Join UPN: "%s", Join type: %d, Request Id: "%s", HTTP status: %lu, Time: "%s".`
- `0x180092c7b`: `%s: Repaired join info successfully written to registry`
- `0x180092da6`: `%s: Repair join info callback failed with error code: 0x%08x. Tenant ID: "%s", Device ID: "%s", Join type: %d, Request Id: "%s", HTTP status: %lu, Time: "%s", Error Code: "%s", Error Subcode: "%s", Server Message: "%s", Server Operation: "%s".`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DiscoverApi::AsyncRepairCallback(struct _DISCOVERY_METADATA *a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int *v8; // rbx
  _WORD *v9; // rax
  _WORD *v10; // rax
  int v11; // r9d
  int v12; // r15d
  __int64 v13; // rax
  __int64 JoinTypeName; // rax
  __int64 v15; // r9
  const WCHAR *v16; // r15
  int v17; // r13d
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v21; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v22; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR *v23; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v24; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v25; // [rsp+A8h] [rbp-58h] BYREF
  const WCHAR *v26; // [rsp+B0h] [rbp-50h] BYREF
  const WCHAR *v27; // [rsp+B8h] [rbp-48h] BYREF
  const WCHAR *v28; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v30[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v31; // [rsp+100h] [rbp+0h]
  __int64 v32; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v33; // [rsp+118h] [rbp+18h]
  __int64 v34; // [rsp+120h] [rbp+20h]
  __int64 v35; // [rsp+128h] [rbp+28h]
  int v36; // [rsp+1E8h] [rbp+E8h]
  __int64 v37; // [rsp+200h] [rbp+100h]
  __int64 v38; // [rsp+208h] [rbp+108h]
  BOOL v39; // [rsp+210h] [rbp+110h]
  __int64 v40; // [rsp+218h] [rbp+118h]
  __int64 v41; // [rsp+220h] [rbp+120h]
  int v42; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v43; // [rsp+2A8h] [rbp+1A8h] BYREF

  Logger::TraceVerbose(L"%s started", L"DiscoverApi::AsyncRepairCallback");
  if ( a4 >= 0 )
    Logger::TraceVerbose(L"%s: Discovery succeeded.", L"DiscoverApi::AsyncRepairCallback");
  else
    Logger::TraceError(
      L"%s: Discovery failed with error code : 0x%08x.",
      L"DiscoverApi::AsyncRepairCallback",
      (unsigned int)a4);
  v8 = *(unsigned int **)(*(_QWORD *)(a3 + 32) + 8LL);
  struct_join_status::Clear((struct_join_status *)&v32);
  v32 = *((_QWORD *)v8 + 2);
  v34 = *((_QWORD *)v8 + 4);
  v9 = (_WORD *)*((_QWORD *)v8 + 3);
  if ( v9 && *v9 )
    v33 = 0;
  else
    v33 = L"login.windows.net";
  v10 = (_WORD *)*((_QWORD *)v8 + 5);
  if ( v10 && *v10 )
    v35 = 0;
  else
    v35 = *(_QWORD *)(a3 + 16);
  struct_join_status::Set((struct_join_status *)&v32, a1);
  v36 = *(_DWORD *)(a3 + 24);
  v37 = *((_QWORD *)v8 + 32);
  v41 = *((_QWORD *)v8 + 36);
  v38 = *((_QWORD *)v8 + 33);
  v39 = v8[68] != 0;
  v40 = *((_QWORD *)v8 + 35);
  v12 = JoinStatusStorage::SaveJoinStatus(
          *v8 == 1,
          *((const struct _CERT_CONTEXT **)v8 + 1),
          (struct struct_join_status *)&v32,
          v11);
  if ( v12 >= 0 )
  {
    Logger::TraceInformation(
      L"%s: Repaired join info successfully written to registry",
      L"DiscoverApi::AsyncRepairCallback");
    v12 = JoinStatusStorage::FlushJoinStatus(*v8);
    if ( v12 >= 0 )
    {
      Logger::TraceVerbose(L"%s: Flushed repaire join info into registry", L"DiscoverApi::AsyncRepairCallback");
    }
    else
    {
      JoinTypeName = GetJoinTypeName(*v8);
      Logger::TraceError(
        L"%s: JoinStatusStorage::FlushJoinStatus(%s) failed with error code : 0x%08x.",
        L"DiscoverApi::AsyncRepairCallback",
        JoinTypeName,
        (unsigned int)v12);
    }
  }
  else
  {
    v13 = GetJoinTypeName(*v8);
    Logger::TraceError(
      L"%s: JoinStatusStorage::SaveJoinStatus(%s) failed with error code : 0x%08x.",
      L"DiscoverApi::AsyncRepairCallback",
      v13,
      (unsigned int)v12);
  }
  struct_join_status::Clear((struct_join_status *)&v32);
  if ( a4 >= 0 )
    a4 = v12;
  v15 = *v8;
  if ( a4 < 0 )
  {
    Logger::WriteRepairJoinInfoCallbackFailureEvent((unsigned int)a4, *((_QWORD *)v8 + 4), *((_QWORD *)v8 + 2), v15, a2);
    v16 = *(const WCHAR **)(a2 + 8);
    v17 = *(_DWORD *)(a2 + 16);
    Logger::TraceError(
      L"%s: Repair join info callback failed with error code: 0x%08x. Tenant ID: \"%s\", Device ID: \"%s\", Join type: %d,"
       " Request Id: \"%s\", HTTP status: %lu, Time: \"%s\", Error Code: \"%s\", Error Subcode: \"%s\", Server Message: \""
       "%s\", Server Operation: \"%s\".",
      L"DiscoverApi::AsyncRepairCallback",
      (unsigned int)a4,
      *((_QWORD *)v8 + 4),
      *((_QWORD *)v8 + 2),
      *v8,
      *(_QWORD *)a2,
      v17,
      v16,
      *(_QWORD *)(a2 + 24),
      *(_QWORD *)(a2 + 32),
      *(_QWORD *)(a2 + 40),
      *(_QWORD *)(a2 + 48));
  }
  else
  {
    Logger::WriteRepairJoinInfoCallbackSuccessEvent(
      *((_QWORD *)v8 + 4),
      *((_QWORD *)v8 + 2),
      *((_QWORD *)v8 + 5),
      v15,
      a2);
    v16 = *(const WCHAR **)(a2 + 8);
    v17 = *(_DWORD *)(a2 + 16);
    Logger::TraceVerbose(
      L"%s: Repair join info callback succeeded. Tenant ID: \"%s\", Device ID: \"%s\", Join UPN: \"%s\", Join type: %d, Re"
       "quest Id: \"%s\", HTTP status: %lu, Time: \"%s\".",
      L"DiscoverApi::AsyncRepairCallback",
      *((_QWORD *)v8 + 4),
      *((_QWORD *)v8 + 2),
      *((_QWORD *)v8 + 5),
      *v8,
      *(_QWORD *)a2,
      v17,
      v16);
  }
  **(_DWORD **)(a3 + 40) = 2;
  if ( (unsigned int)dword_1800E5118 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5118, 0x400000000000LL) )
  {
    v21 = *(const WCHAR **)(a2 + 48);
    v22 = *(const WCHAR **)(a2 + 40);
    v23 = *(const WCHAR **)(a2 + 32);
    v24 = *(const WCHAR **)(a2 + 24);
    v25 = v16;
    v43 = v17;
    v26 = *(const WCHAR **)a2;
    v42 = *v8;
    v27 = (const WCHAR *)*((_QWORD *)v8 + 2);
    v28 = (const WCHAR *)*((_QWORD *)v8 + 4);
    v20 = a4;
    v29 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800E5118,
      (__int64)&byte_1800D33E7,
      v18 + 8,
      v19,
      (__int64)&v29,
      (__int64)&v20,
      &v28,
      &v27,
      (__int64)&v42,
      &v26,
      (__int64)&v43,
      &v25,
      &v24,
      &v23,
      &v22,
      &v21);
  }
  if ( *(_QWORD *)a3 )
  {
    Logger::TraceVerbose(
      L"%s: Calling callback function. OperationResult = 0x%08x.",
      L"DiscoverApi::AsyncRepairCallback",
      (unsigned int)a4);
    v30[0] = *(_OWORD *)a2;
    v30[1] = *(_OWORD *)(a2 + 16);
    v30[2] = *(_OWORD *)(a2 + 32);
    v31 = *(_QWORD *)(a2 + 48);
    (*(void (__fastcall **)(_OWORD *, _QWORD, _QWORD))a3)(v30, *(_QWORD *)(a3 + 8), (unsigned int)a4);
  }
  _JOIN_INFO_REPAIR_CALLBACK_CONTEXT::`scalar deleting destructor'((void **)a3);
  DsrFreeDiscoveryMetadata(a1);
  Logger::TraceVerbose(L"%s finished", L"DiscoverApi::AsyncRepairCallback");
  struct_join_status::~struct_join_status((struct_join_status *)&v32);
}

```

## disassembly

```asm
0x180092b20  mov     [rsp-8+arg_0], rbx
0x180092b25  push    rbp
0x180092b26  push    rsi
0x180092b27  push    rdi
0x180092b28  push    r12
0x180092b2a  push    r13
0x180092b2c  push    r14
0x180092b2e  push    r15
0x180092b30  lea     rbp, [rsp-150h]
0x180092b38  sub     rsp, 250h
0x180092b3f  mov     edi, r9d
0x180092b42  mov     rsi, r8
0x180092b45  mov     r14, rdx
0x180092b48  mov     r12, rcx
0x180092b4b  lea     rbx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092b52  mov     rdx, rbx
0x180092b55  lea     rcx, aSStarted; "%s started"
0x180092b5c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092b61  xor     r13d, r13d
0x180092b64  mov     rdx, rbx
0x180092b67  test    edi, edi
0x180092b69  jns     short loc_180092B7C
0x180092b6b  mov     r8d, edi
0x180092b6e  lea     rcx, aSDiscoveryFail; "%s: Discovery failed with error code : "...
0x180092b75  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180092b7a  jmp     short loc_180092B88
0x180092b7c  lea     rcx, aSDiscoverySucc; "%s: Discovery succeeded."
0x180092b83  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092b88  mov     rax, [rsi+20h]
0x180092b8c  mov     rbx, [rax+8]
0x180092b90  lea     rcx, [rbp+180h+var_170]; this
0x180092b94  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x180092b99  nop
0x180092b9a  mov     rax, [rbx+10h]
0x180092b9e  mov     [rbp+180h+var_170], rax
0x180092ba2  mov     rax, [rbx+20h]
0x180092ba6  mov     [rbp+180h+var_160], rax
0x180092baa  mov     rax, [rbx+18h]
0x180092bae  test    rax, rax
0x180092bb1  jz      short loc_180092BBF
0x180092bb3  cmp     [rax], r13w
0x180092bb7  jz      short loc_180092BBF
0x180092bb9  mov     [rbp+180h+var_168], r13
0x180092bbd  jmp     short loc_180092BCA
0x180092bbf  lea     rax, aLoginWindowsNe; "login.windows.net"
0x180092bc6  mov     [rbp+180h+var_168], rax
0x180092bca  mov     rax, [rbx+28h]
0x180092bce  test    rax, rax
0x180092bd1  jz      short loc_180092BDF
0x180092bd3  cmp     [rax], r13w
0x180092bd7  jz      short loc_180092BDF
0x180092bd9  mov     [rbp+180h+var_158], r13
0x180092bdd  jmp     short loc_180092BE7
0x180092bdf  mov     rax, [rsi+10h]
0x180092be3  mov     [rbp+180h+var_158], rax
0x180092be7  mov     rdx, r12; struct _DISCOVERY_METADATA *
0x180092bea  lea     rcx, [rbp+180h+var_170]; this
0x180092bee  call    ?Set@struct_join_status@@QEAAXPEAU_DISCOVERY_METADATA@@@Z; struct_join_status::Set(_DISCOVERY_METADATA *)
0x180092bf3  mov     ecx, [rsi+18h]
0x180092bf6  mov     [rbp+180h+var_98], ecx
0x180092bfc  mov     rax, [rbx+100h]
0x180092c03  mov     [rbp+180h+var_80], rax
0x180092c0a  mov     rax, [rbx+120h]
0x180092c11  mov     [rbp+180h+var_60], rax
0x180092c18  mov     rax, [rbx+108h]
0x180092c1f  mov     [rbp+180h+var_78], rax
0x180092c26  mov     eax, r13d
0x180092c29  cmp     [rbx+110h], r13d
0x180092c30  setnz   al
0x180092c33  mov     [rbp+180h+var_70], eax
0x180092c39  mov     rax, [rbx+118h]
0x180092c40  mov     [rbp+180h+var_68], rax
0x180092c47  mov     ecx, r13d
0x180092c4a  cmp     dword ptr [rbx], 1
0x180092c4d  setz    cl; int
0x180092c50  lea     r8, [rbp+180h+var_170]; struct struct_join_status *
0x180092c54  mov     rdx, [rbx+8]; struct _CERT_CONTEXT *
0x180092c58  call    ?SaveJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@PEAUstruct_join_status@@H@Z; JoinStatusStorage::SaveJoinStatus(int,_CERT_CONTEXT const *,struct_join_status *,int)
0x180092c5d  mov     r15d, eax
0x180092c60  test    eax, eax
0x180092c62  jns     short loc_180092C74
0x180092c64  mov     ecx, [rbx]
0x180092c66  call    ?GetJoinTypeName@@YAPEBGW4_DSREG_JOIN_TYPE@@@Z; GetJoinTypeName(_DSREG_JOIN_TYPE)
0x180092c6b  lea     rcx, aSJoinstatussto_1; "%s: JoinStatusStorage::SaveJoinStatus(%"...
0x180092c72  jmp     short loc_180092CA3
0x180092c74  lea     rdx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092c7b  lea     rcx, aSRepairedJoinI; "%s: Repaired join info successfully wri"...
0x180092c82  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180092c87  mov     ecx, [rbx]; int
0x180092c89  call    ?FlushJoinStatus@JoinStatusStorage@@SAJH@Z; JoinStatusStorage::FlushJoinStatus(int)
0x180092c8e  mov     r15d, eax
0x180092c91  test    eax, eax
0x180092c93  jns     short loc_180092CB7
0x180092c95  mov     ecx, [rbx]
0x180092c97  call    ?GetJoinTypeName@@YAPEBGW4_DSREG_JOIN_TYPE@@@Z; GetJoinTypeName(_DSREG_JOIN_TYPE)
0x180092c9c  lea     rcx, aSJoinstatussto; "%s: JoinStatusStorage::FlushJoinStatus("...
0x180092ca3  lea     rdx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092caa  mov     r9d, r15d
0x180092cad  mov     r8, rax
0x180092cb0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180092cb5  jmp     short loc_180092CCA
0x180092cb7  lea     rdx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092cbe  lea     rcx, aSFlushedRepair; "%s: Flushed repaire join info into regi"...
0x180092cc5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092cca  lea     rcx, [rbp+180h+var_170]; this
0x180092cce  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x180092cd3  test    edi, edi
0x180092cd5  cmovns  edi, r15d
0x180092cd9  mov     [rsp+280h+var_260], r14
0x180092cde  mov     r9d, [rbx]
0x180092ce1  test    edi, edi
0x180092ce3  js      short loc_180092D3C
0x180092ce5  mov     r8, [rbx+28h]
0x180092ce9  mov     rdx, [rbx+10h]
0x180092ced  mov     rcx, [rbx+20h]
0x180092cf1  call    ?WriteRepairJoinInfoCallbackSuccessEvent@Logger@@SAJPEBG00W4_DSREG_JOIN_TYPE@@AEBUstruct_dsreg_server_response@@@Z; Logger::WriteRepairJoinInfoCallbackSuccessEvent(ushort const *,ushort const *,ushort const *,_DSREG_JOIN_TYPE,struct_dsreg_server_response const &)
0x180092cf6  mov     r15, [r14+8]
0x180092cfa  mov     r13d, [r14+10h]
0x180092cfe  mov     rax, [r14]
0x180092d01  mov     [rsp+280h+var_240], r15
0x180092d06  mov     dword ptr [rsp+280h+var_248], r13d
0x180092d0b  mov     [rsp+280h+var_250], rax
0x180092d10  mov     eax, [rbx]
0x180092d12  mov     dword ptr [rsp+280h+var_258], eax
0x180092d16  mov     rax, [rbx+28h]
0x180092d1a  mov     [rsp+280h+var_260], rax
0x180092d1f  mov     r9, [rbx+10h]
0x180092d23  mov     r8, [rbx+20h]
0x180092d27  lea     rdx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092d2e  lea     rcx, aSRepairJoinInf_1; "%s: Repair join info callback succeeded"...
0x180092d35  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092d3a  jmp     short loc_180092DB2
0x180092d3c  mov     r8, [rbx+10h]
0x180092d40  mov     rdx, [rbx+20h]
0x180092d44  mov     ecx, edi
0x180092d46  call    ?WriteRepairJoinInfoCallbackFailureEvent@Logger@@SAJJPEBG0W4_DSREG_JOIN_TYPE@@AEBUstruct_dsreg_server_response@@@Z; Logger::WriteRepairJoinInfoCallbackFailureEvent(long,ushort const *,ushort const *,_DSREG_JOIN_TYPE,struct_dsreg_server_response const &)
0x180092d4b  mov     r15, [r14+8]
0x180092d4f  mov     r13d, [r14+10h]
0x180092d53  mov     rcx, [r14]
0x180092d56  mov     rax, [r14+30h]
0x180092d5a  mov     [rsp+280h+var_220], rax
0x180092d5f  mov     rax, [r14+28h]
0x180092d63  mov     [rsp+280h+var_228], rax
0x180092d68  mov     rax, [r14+20h]
0x180092d6c  mov     [rsp+280h+var_230], rax
0x180092d71  mov     rax, [r14+18h]
0x180092d75  mov     [rsp+280h+var_238], rax
0x180092d7a  mov     [rsp+280h+var_240], r15
0x180092d7f  mov     dword ptr [rsp+280h+var_248], r13d
0x180092d84  mov     [rsp+280h+var_250], rcx
0x180092d89  mov     eax, [rbx]
0x180092d8b  mov     dword ptr [rsp+280h+var_258], eax
0x180092d8f  mov     rax, [rbx+10h]
0x180092d93  mov     [rsp+280h+var_260], rax
0x180092d98  mov     r9, [rbx+20h]
0x180092d9c  mov     r8d, edi
0x180092d9f  lea     rdx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092da6  lea     rcx, aSRepairJoinInf; "%s: Repair join info callback failed wi"...
0x180092dad  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180092db2  mov     r8, [rsi+28h]
0x180092db6  mov     dword ptr [r8], 2
0x180092dbd  mov     eax, cs:dword_1800E5118
0x180092dc3  cmp     eax, 5
0x180092dc6  jbe     loc_180092EC8
0x180092dcc  mov     rdx, 400000000000h
0x180092dd6  lea     rcx, dword_1800E5118
0x180092ddd  call    _tlgKeywordOn
0x180092de2  test    al, al
0x180092de4  jz      loc_180092EC8
0x180092dea  mov     rax, [r14+30h]
0x180092dee  mov     [rbp+180h+var_1F8], rax
0x180092df2  mov     rax, [r14+28h]
0x180092df6  mov     [rbp+180h+var_1F0], rax
0x180092dfa  mov     rax, [r14+20h]
0x180092dfe  mov     [rbp+180h+var_1E8], rax
0x180092e02  mov     rax, [r14+18h]
0x180092e06  mov     [rbp+180h+var_1E0], rax
0x180092e0a  mov     [rbp+180h+var_1D8], r15
0x180092e0e  mov     [rbp+180h+arg_18], r13d
0x180092e15  mov     rax, [r14]
0x180092e18  mov     [rbp+180h+var_1D0], rax
0x180092e1c  mov     eax, [rbx]
0x180092e1e  mov     [rbp+180h+arg_10], eax
0x180092e24  mov     rax, [rbx+10h]
0x180092e28  mov     [rbp+180h+var_1C8], rax
0x180092e2c  mov     rax, [rbx+20h]
0x180092e30  mov     [rbp+180h+var_1C0], rax
0x180092e34  mov     [rbp+180h+var_200], edi
0x180092e37  mov     [rbp+180h+var_1B8], 1000800h
0x180092e3f  add     r8, 8
0x180092e43  lea     rax, [rbp+180h+var_1F8]
0x180092e47  mov     [rsp+280h+var_208], rax
0x180092e4c  lea     rax, [rbp+180h+var_1F0]
0x180092e50  mov     [rsp+280h+var_210], rax
0x180092e55  lea     rax, [rbp+180h+var_1E8]
0x180092e59  mov     [rsp+280h+var_218], rax
0x180092e5e  lea     rax, [rbp+180h+var_1E0]
0x180092e62  mov     [rsp+280h+var_220], rax
0x180092e67  lea     rax, [rbp+180h+var_1D8]
0x180092e6b  mov     [rsp+280h+var_228], rax
0x180092e70  lea     rax, [rbp+180h+arg_18]
0x180092e77  mov     [rsp+280h+var_230], rax
0x180092e7c  lea     rax, [rbp+180h+var_1D0]
0x180092e80  mov     [rsp+280h+var_238], rax
0x180092e85  lea     rax, [rbp+180h+arg_10]
0x180092e8c  mov     [rsp+280h+var_240], rax
0x180092e91  lea     rax, [rbp+180h+var_1C8]
0x180092e95  mov     [rsp+280h+var_248], rax
0x180092e9a  lea     rax, [rbp+180h+var_1C0]
0x180092e9e  mov     [rsp+280h+var_250], rax
0x180092ea3  lea     rax, [rbp+180h+var_200]
0x180092ea7  mov     [rsp+280h+var_258], rax
0x180092eac  lea     rax, [rbp+180h+var_1B8]
0x180092eb0  mov     [rsp+280h+var_260], rax
0x180092eb5  lea     rdx, byte_1800D33E7
0x180092ebc  lea     rcx, dword_1800E5118
0x180092ec3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@U3@U2@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@545455555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180092ec8  cmp     qword ptr [rsi], 0
0x180092ecc  jz      short loc_180092F1C
0x180092ece  mov     r8d, edi
0x180092ed1  lea     rdx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092ed8  lea     rcx, aSCallingCallba; "%s: Calling callback function. Operatio"...
0x180092edf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092ee4  movups  xmm0, xmmword ptr [r14]
0x180092ee8  movaps  [rbp+180h+var_1B0], xmm0
0x180092eec  movups  xmm1, xmmword ptr [r14+10h]
0x180092ef1  movaps  [rbp+180h+var_1A0], xmm1
0x180092ef5  movups  xmm0, xmmword ptr [r14+20h]
0x180092efa  movaps  [rbp+180h+var_190], xmm0
0x180092efe  movsd   xmm1, qword ptr [r14+30h]
0x180092f04  movsd   [rbp+180h+var_180], xmm1
0x180092f09  mov     r8d, edi
0x180092f0c  mov     rdx, [rsi+8]
0x180092f10  lea     rcx, [rbp+180h+var_1B0]
0x180092f14  mov     rax, [rsi]
0x180092f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092f1c  mov     rcx, rsi; this
0x180092f1f  call    ??_G_JOIN_INFO_REPAIR_CALLBACK_CONTEXT@@QEAAPEAXI@Z; _JOIN_INFO_REPAIR_CALLBACK_CONTEXT::`scalar deleting destructor'(uint)
0x180092f24  mov     rcx, r12; void *
0x180092f27  call    DsrFreeDiscoveryMetadata
0x180092f2c  lea     rdx, aDiscoverapiAsy_0; "DiscoverApi::AsyncRepairCallback"
0x180092f33  lea     rcx, aSFinished; "%s finished"
0x180092f3a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092f3f  nop
0x180092f40  lea     rcx, [rbp+180h+var_170]; this
0x180092f44  call    ??1struct_join_status@@QEAA@XZ; struct_join_status::~struct_join_status(void)
0x180092f49  mov     rbx, [rsp+280h+arg_0]
0x180092f51  add     rsp, 250h
0x180092f58  pop     r15
0x180092f5a  pop     r14
0x180092f5c  pop     r13
0x180092f5e  pop     r12
0x180092f60  pop     rdi
0x180092f61  pop     rsi
0x180092f62  pop     rbp
0x180092f63  retn
```

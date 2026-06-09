# PhoneSvcImpl_PhoneRpcGetDefaultOutgoingLine

- ea: `0x180089ee0`
- end: `0x18008a1cd`
- name: `PhoneSvcImpl_PhoneRpcGetDefaultOutgoingLine`
- size: `749`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180083050`

## callees

- `0x1800045b4`
- `0x1800056a0`
- `0x180006e94`
- `0x180007750`
- `0x180009094`
- `0x18004c2ac`
- `0x180086b10`
- `0x180089ee0`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a0b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a13d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a0b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a13d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a196`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180089fb1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180089fb1`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008a050`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008a050`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180089f71`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180089f71`

## pseudocode

```c
__int64 __fastcall PhoneSvcImpl_PhoneRpcGetDefaultOutgoingLine(__int64 a1, __int64 a2)
{
  int v3; // eax
  BackTraceCollection *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // r8
  void **v8; // rax
  int RpcClientThreadToken; // eax
  __int64 v10; // r8
  int ApplicationUserModelIdFromToken; // eax
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // r8
  int v15; // eax
  BackTraceCollection *v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  BackTraceCollection *v19; // rcx
  unsigned int v20; // edi
  __int64 v21; // r8
  int v22; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR *v23; // [rsp+40h] [rbp-C0h] BYREF
  struct ISecurityToken *v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE token; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+58h] [rbp-A8h] BYREF
  void *Block[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+72h] [rbp-8Eh]
  int v30; // [rsp+7Ah] [rbp-86h]
  __int16 v31; // [rsp+7Eh] [rbp-82h]
  WCHAR applicationUserModelId[136]; // [rsp+80h] [rbp-80h] BYREF

  v3 = WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(&g_phoneRpcServer);
  v5 = v3;
  if ( v3 < 0 )
  {
    BackTraceCollection::Capture(v4, v3);
    Log_HREvent_31(v5, 1, v6, 860);
    return v5;
  }
  token = 0;
  v8 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&token);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v8);
  if ( RpcClientThreadToken < 0 )
    Log_HREvent_31((unsigned int)RpcClientThreadToken, 0, v10, 863);
  memset_0(applicationUserModelId, 0, 0x106u);
  applicationUserModelIdLength = 131;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken && (unsigned int)dword_1800B3200 > 3 )
  {
    v23 = applicationUserModelId;
    if ( ApplicationUserModelIdFromToken > 0 )
      ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
    v22 = ApplicationUserModelIdFromToken;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (unsigned int)applicationUserModelId,
      (unsigned int)&word_1800AB46E,
      v12,
      v13,
      (__int64)&v22,
      (__int64)&v23);
  }
  v29 = 0;
  Block[0] = &v28;
  v14 = -1;
  v30 = 0;
  Block[1] = &v28;
  v31 = 0;
  v28 = 0;
  do
    ++v14;
  while ( applicationUserModelId[v14] );
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
    Block,
    applicationUserModelId);
  v24 = 0;
  v15 = CreatePerUserSecurityTokenForRpcClient(&v24);
  v5 = v15;
  if ( v15 < 0 )
  {
    BackTraceCollection::Capture(v16, v15);
    Log_HREvent_31(v5, 1, v17, 881);
    if ( v24 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( Block[0] != &v28 )
      operator delete(Block[0]);
    if ( token )
      CloseHandle(token);
    return v5;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, void **, struct ISecurityToken *))(MEMORY[0] + 520LL))(
          0,
          a2,
          Block,
          v24);
  v20 = v18;
  if ( v18 >= 0 )
  {
    if ( v24 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( Block[0] != &v28 )
      operator delete(Block[0]);
    if ( token )
      CloseHandle(token);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v19, v18);
    Log_HREvent_31(v20, 1, v21, 883);
    if ( v24 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( Block[0] != &v28 )
      operator delete(Block[0]);
    if ( token )
      CloseHandle(token);
    return v20;
  }
}

```

## disassembly

```asm
0x180089ee0  push    rbp
0x180089ee2  push    rbx
0x180089ee3  push    rsi
0x180089ee4  push    rdi
0x180089ee5  lea     rbp, [rsp-0A8h]
0x180089eed  sub     rsp, 1A8h
0x180089ef4  mov     rax, cs:__security_cookie
0x180089efb  xor     rax, rsp
0x180089efe  mov     [rbp+0C0h+var_30], rax
0x180089f05  mov     rdi, rdx
0x180089f08  lea     rcx, ?g_phoneRpcServer@@3VSecurePhoneRpcServer@@A; lpCriticalSection
0x180089f0f  xor     esi, esi
0x180089f11  lea     rdx, [rsp+1C0h+var_190]
0x180089f16  mov     [rsp+1C0h+var_190], rsi
0x180089f1b  call    ?Get@?$WrappedComPtrBase@UIPhoneController@@VDoesNotSupportShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneController@@@Z; WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(IPhoneController * *)
0x180089f20  mov     ebx, eax
0x180089f22  test    eax, eax
0x180089f24  jns     short loc_180089F5A
0x180089f26  mov     edx, eax; int
0x180089f28  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180089f2d  lea     edx, [rsi+1]
0x180089f30  mov     r9d, 35Ch
0x180089f36  mov     ecx, ebx
0x180089f38  call    Log_HREvent_31
0x180089f3d  mov     rcx, [rsp+1C0h+var_190]
0x180089f42  test    rcx, rcx
0x180089f45  jz      short loc_180089F53
0x180089f47  mov     rax, [rcx]
0x180089f4a  mov     rax, [rax+10h]
0x180089f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089f53  mov     eax, ebx
0x180089f55  jmp     loc_18008A1B2
0x180089f5a  lea     rcx, [rsp+1C0h+token]
0x180089f5f  mov     [rsp+1C0h+token], rsi
0x180089f64  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x180089f69  mov     rdx, rax
0x180089f6c  mov     ecx, 8
0x180089f71  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x180089f77  test    eax, eax
0x180089f79  jns     short loc_180089F8A
0x180089f7b  xor     edx, edx
0x180089f7d  mov     r9d, 35Fh
0x180089f83  mov     ecx, eax
0x180089f85  call    Log_HREvent_31
0x180089f8a  xor     edx, edx; Val
0x180089f8c  lea     rcx, [rbp+0C0h+applicationUserModelId]; void *
0x180089f90  mov     r8d, 106h; Size
0x180089f96  call    memset_0
0x180089f9b  mov     rcx, [rsp+1C0h+token]; token
0x180089fa0  lea     r8, [rbp+0C0h+applicationUserModelId]; applicationUserModelId
0x180089fa4  lea     rdx, [rsp+1C0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180089fa9  mov     [rsp+1C0h+applicationUserModelIdLength], 83h
0x180089fb1  call    cs:__imp_GetApplicationUserModelIdFromToken
0x180089fb7  test    eax, eax
0x180089fb9  jz      short loc_180089FFF
0x180089fbb  mov     ecx, cs:dword_1800B3200
0x180089fc1  cmp     ecx, 3
0x180089fc4  jbe     short loc_180089FFF
0x180089fc6  lea     rcx, [rbp+0C0h+applicationUserModelId]
0x180089fca  mov     [rsp+1C0h+var_180], rcx
0x180089fcf  test    eax, eax
0x180089fd1  jle     short loc_180089FDB
0x180089fd3  movzx   eax, ax
0x180089fd6  or      eax, 80070000h
0x180089fdb  mov     [rsp+1C0h+var_188], eax
0x180089fdf  lea     rdx, word_1800AB46E
0x180089fe6  lea     rax, [rsp+1C0h+var_180]
0x180089feb  mov     [rsp+1C0h+var_198], rax
0x180089ff0  lea     rax, [rsp+1C0h+var_188]
0x180089ff5  mov     [rsp+1C0h+var_1A0], rax
0x180089ffa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180089fff  lea     rax, [rsp+1C0h+var_150]
0x18008a004  mov     [rsp+1C0h+var_14E], rsi
0x18008a009  mov     [rsp+1C0h+Block], rax
0x18008a00e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008a012  lea     rax, [rsp+1C0h+var_150]
0x18008a017  mov     [rsp+1C0h+var_146], esi
0x18008a01b  mov     [rsp+1C0h+var_158], rax
0x18008a020  lea     rax, [rbp+0C0h+applicationUserModelId]
0x18008a024  mov     [rsp+1C0h+var_142], si
0x18008a029  mov     [rsp+1C0h+var_150], si
0x18008a02e  inc     r8
0x18008a031  cmp     [rax+r8*2], si
0x18008a036  jnz     short loc_18008A02E
0x18008a038  lea     rdx, [rbp+0C0h+applicationUserModelId]
0x18008a03c  lea     rcx, [rsp+1C0h+Block]
0x18008a041  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008a046  lea     rcx, [rsp+1C0h+var_178]
0x18008a04b  mov     [rsp+1C0h+var_178], rsi
0x18008a050  call    cs:__imp_?CreatePerUserSecurityTokenForRpcClient@@YAJPEAPEAUISecurityToken@@@Z; CreatePerUserSecurityTokenForRpcClient(ISecurityToken * *)
0x18008a056  mov     ebx, eax
0x18008a058  test    eax, eax
0x18008a05a  jns     short loc_18008A0BF
0x18008a05c  mov     edx, eax; int
0x18008a05e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008a063  mov     edx, 1
0x18008a068  mov     r9d, 371h
0x18008a06e  mov     ecx, ebx
0x18008a070  call    Log_HREvent_31
0x18008a075  mov     rcx, [rsp+1C0h+var_178]
0x18008a07a  test    rcx, rcx
0x18008a07d  jz      short loc_18008A08B
0x18008a07f  mov     rax, [rcx]
0x18008a082  mov     rax, [rax+10h]
0x18008a086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a08b  mov     rcx, [rsp+1C0h+Block]; Block
0x18008a090  lea     rax, [rsp+1C0h+var_150]
0x18008a095  cmp     rcx, rax
0x18008a098  jz      short loc_18008A0A6
0x18008a09a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18008a0a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008a0a6  mov     rcx, [rsp+1C0h+token]; hObject
0x18008a0ab  test    rcx, rcx
0x18008a0ae  jz      loc_180089F3D
0x18008a0b4  call    cs:__imp_CloseHandle
0x18008a0ba  jmp     loc_180089F3D
0x18008a0bf  mov     rbx, [rsp+1C0h+var_190]
0x18008a0c4  lea     r8, [rsp+1C0h+Block]
0x18008a0c9  mov     r9, [rsp+1C0h+var_178]
0x18008a0ce  mov     rdx, rdi
0x18008a0d1  mov     rcx, rbx
0x18008a0d4  mov     rax, [rbx]
0x18008a0d7  mov     rax, [rax+208h]
0x18008a0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a0e3  mov     edi, eax
0x18008a0e5  test    eax, eax
0x18008a0e7  jns     short loc_18008A15B
0x18008a0e9  mov     edx, eax; int
0x18008a0eb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008a0f0  mov     edx, 1
0x18008a0f5  mov     r9d, 373h
0x18008a0fb  mov     ecx, edi
0x18008a0fd  call    Log_HREvent_31
0x18008a102  mov     rcx, [rsp+1C0h+var_178]
0x18008a107  test    rcx, rcx
0x18008a10a  jz      short loc_18008A118
0x18008a10c  mov     rax, [rcx]
0x18008a10f  mov     rax, [rax+10h]
0x18008a113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a118  mov     rcx, [rsp+1C0h+Block]; Block
0x18008a11d  lea     rax, [rsp+1C0h+var_150]
0x18008a122  cmp     rcx, rax
0x18008a125  jz      short loc_18008A133
0x18008a127  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18008a12e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008a133  mov     rcx, [rsp+1C0h+token]; hObject
0x18008a138  test    rcx, rcx
0x18008a13b  jz      short loc_18008A143
0x18008a13d  call    cs:__imp_CloseHandle
0x18008a143  test    rbx, rbx
0x18008a146  jz      short loc_18008A157
0x18008a148  mov     rax, [rbx]
0x18008a14b  mov     rcx, rbx
0x18008a14e  mov     rax, [rax+10h]
0x18008a152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a157  mov     eax, edi
0x18008a159  jmp     short loc_18008A1B2
0x18008a15b  mov     rcx, [rsp+1C0h+var_178]
0x18008a160  test    rcx, rcx
0x18008a163  jz      short loc_18008A171
0x18008a165  mov     rax, [rcx]
0x18008a168  mov     rax, [rax+10h]
0x18008a16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a171  mov     rcx, [rsp+1C0h+Block]; Block
0x18008a176  lea     rax, [rsp+1C0h+var_150]
0x18008a17b  cmp     rcx, rax
0x18008a17e  jz      short loc_18008A18C
0x18008a180  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18008a187  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008a18c  mov     rcx, [rsp+1C0h+token]; hObject
0x18008a191  test    rcx, rcx
0x18008a194  jz      short loc_18008A19C
0x18008a196  call    cs:__imp_CloseHandle
0x18008a19c  test    rbx, rbx
0x18008a19f  jz      short loc_18008A1B0
0x18008a1a1  mov     rax, [rbx]
0x18008a1a4  mov     rcx, rbx
0x18008a1a7  mov     rax, [rax+10h]
0x18008a1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1b0  xor     eax, eax
0x18008a1b2  mov     rcx, [rbp+0C0h+var_30]
0x18008a1b9  xor     rcx, rsp; StackCookie
0x18008a1bc  call    __security_check_cookie
0x18008a1c1  add     rsp, 1A8h
0x18008a1c8  pop     rdi
0x18008a1c9  pop     rsi
0x18008a1ca  pop     rbx
0x18008a1cb  pop     rbp
0x18008a1cc  retn
```

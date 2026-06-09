# PhoneSvcImpl_PhoneRpcPublicDial

- ea: `0x18008b4e0`
- end: `0x18008b7cf`
- name: `PhoneSvcImpl_PhoneRpcPublicDial`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, __int64, __int64, int *, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006e94`
- `0x180007750`
- `0x18004c2ac`
- `0x180051540`
- `0x180086b10`
- `0x180086b28`
- `0x18008b4e0`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b60e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b76a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b7a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b60e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b76a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b7a6`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18008b62c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18008b62c`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008b665`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008b665`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18008b5dc`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18008b5dc`

## pseudocode

```c
__int64 __fastcall PhoneSvcImpl_PhoneRpcPublicDial(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int *a6,
        int a7,
        int a8)
{
  int v11; // eax
  BackTraceCollection *v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // eax
  BackTraceCollection *v18; // rcx
  __int64 v19; // rax
  __int128 v20; // xmm0
  void **v21; // rax
  int RpcClientThreadToken; // eax
  BackTraceCollection *v23; // rcx
  __int64 v24; // r8
  int ApplicationUserModelIdFromToken; // eax
  __int64 v26; // r8
  int v27; // eax
  BackTraceCollection *v28; // rcx
  __int64 v29; // r8
  int v30; // eax
  BackTraceCollection *v31; // rcx
  __int64 v32; // r8
  int v33; // eax
  BackTraceCollection *v34; // rcx
  unsigned int v35; // edi
  __int64 v36; // r8
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-A0h]
  __int128 v42; // [rsp+70h] [rbp-90h]
  int v43; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+84h] [rbp-7Ch]
  WCHAR *v45; // [rsp+90h] [rbp-70h]
  HANDLE hObject; // [rsp+A0h] [rbp-60h] BYREF
  struct ISecurityToken *v47; // [rsp+A8h] [rbp-58h] BYREF
  UINT32 applicationUserModelIdLength[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+C0h] [rbp-40h] BYREF

  v11 = RpcClientForegroundProcessCheck();
  v13 = v11;
  if ( v11 < 0 )
  {
    BackTraceCollection::Capture(v12, v11);
    v15 = 271;
LABEL_3:
    Log_HREvent_31(v13, 1, v14, v15);
    return v13;
  }
  v17 = PhoneCallSoftwareCapabilityAccessCheck(0);
  v13 = v17;
  if ( v17 < 0 )
  {
    BackTraceCollection::Capture(v18, v17);
    v15 = 273;
    goto LABEL_3;
  }
  memset_0(&v37, 0, 0x58u);
  v19 = v40;
  v20 = *a2;
  if ( a5 )
    v19 = a5;
  v38 = a3;
  v40 = v19;
  v39 = a4;
  v42 = v20;
  if ( a6 )
    v41 = *a6;
  v43 = a8;
  v44 = a7;
  v37 = 4352;
  hObject = 0;
  v21 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&hObject);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v21);
  v13 = RpcClientThreadToken;
  if ( RpcClientThreadToken < 0 )
  {
    BackTraceCollection::Capture(v23, RpcClientThreadToken);
    Log_HREvent_31(v13, 1, v24, 296);
LABEL_13:
    if ( hObject )
      CloseHandle(hObject);
    return v13;
  }
  applicationUserModelIdLength[0] = 132;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      hObject,
                                      applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
  {
    if ( ApplicationUserModelIdFromToken > 0 )
      ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
    Log_HREvent_31((unsigned int)ApplicationUserModelIdFromToken, 0, v26, 307);
  }
  else
  {
    v45 = applicationUserModelId;
  }
  v47 = 0;
  v27 = CreatePerUserSecurityTokenForRpcClient(&v47);
  v13 = v27;
  if ( v27 < 0 )
  {
    BackTraceCollection::Capture(v28, v27);
    Log_HREvent_31(v13, 1, v29, 311);
    goto LABEL_22;
  }
  v30 = WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(&g_phoneRpcServer);
  v13 = v30;
  if ( v30 < 0 )
  {
    BackTraceCollection::Capture(v31, v30);
    Log_HREvent_31(v13, 1, v32, 314);
LABEL_22:
    if ( v47 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_13;
  }
  v33 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD, struct ISecurityToken *))(MEMORY[0] + 72LL))(0, &v37, 0, v47);
  v35 = v33;
  if ( v33 >= 0 )
  {
    if ( v47 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v47 + 16LL))(v47);
    if ( hObject )
      CloseHandle(hObject);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v34, v33);
    Log_HREvent_31(v35, 1, v36, 315);
    if ( v47 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v47 + 16LL))(v47);
    if ( hObject )
      CloseHandle(hObject);
    return v35;
  }
}

```

## disassembly

```asm
0x18008b4e0  push    rbp
0x18008b4e2  push    rbx
0x18008b4e3  push    rsi
0x18008b4e4  push    rdi
0x18008b4e5  push    r12
0x18008b4e7  push    r14
0x18008b4e9  push    r15
0x18008b4eb  lea     rbp, [rsp-0E0h]
0x18008b4f3  sub     rsp, 1E0h
0x18008b4fa  mov     rax, cs:__security_cookie
0x18008b501  xor     rax, rsp
0x18008b504  mov     [rbp+110h+var_40], rax
0x18008b50b  mov     rsi, [rbp+110h+arg_20]
0x18008b512  mov     r12, r9
0x18008b515  mov     rdi, [rbp+110h+arg_28]
0x18008b51c  mov     r15, r8
0x18008b51f  mov     r14, rdx
0x18008b522  call    RpcClientForegroundProcessCheck
0x18008b527  mov     ebx, eax
0x18008b529  test    eax, eax
0x18008b52b  jns     short loc_18008B54D
0x18008b52d  mov     edx, eax; int
0x18008b52f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008b534  mov     r9d, 10Fh
0x18008b53a  mov     edx, 1
0x18008b53f  mov     ecx, ebx
0x18008b541  call    Log_HREvent_31
0x18008b546  mov     eax, ebx
0x18008b548  jmp     loc_18008B7AE
0x18008b54d  xor     ecx, ecx; unsigned int
0x18008b54f  call    ?PhoneCallSoftwareCapabilityAccessCheck@@YAJK@Z; PhoneCallSoftwareCapabilityAccessCheck(ulong)
0x18008b554  mov     ebx, eax
0x18008b556  test    eax, eax
0x18008b558  jns     short loc_18008B569
0x18008b55a  mov     edx, eax; int
0x18008b55c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008b561  mov     r9d, 111h
0x18008b567  jmp     short loc_18008B53A
0x18008b569  xor     edx, edx; Val
0x18008b56b  lea     rcx, [rsp+210h+var_1D0]; void *
0x18008b570  lea     r8d, [rdx+58h]; Size
0x18008b574  call    memset_0
0x18008b579  mov     rax, [rsp+210h+var_1B8]
0x18008b57e  test    rsi, rsi
0x18008b581  movups  xmm0, xmmword ptr [r14]
0x18008b585  cmovnz  rax, rsi
0x18008b589  mov     [rsp+210h+var_1C8], r15
0x18008b58e  mov     [rsp+210h+var_1B8], rax
0x18008b593  mov     [rsp+210h+var_1C0], r12
0x18008b598  movdqu  [rsp+210h+var_1A0], xmm0
0x18008b59e  test    rdi, rdi
0x18008b5a1  jz      short loc_18008B5A9
0x18008b5a3  mov     eax, [rdi]
0x18008b5a5  mov     [rsp+210h+var_1B0], eax
0x18008b5a9  mov     eax, [rbp+110h+arg_38]
0x18008b5af  lea     rcx, [rbp+110h+hObject]
0x18008b5b3  mov     [rbp+110h+var_190], eax
0x18008b5b6  mov     eax, [rbp+110h+arg_30]
0x18008b5bc  mov     [rbp+110h+var_18C], eax
0x18008b5bf  mov     [rsp+210h+var_1D0], 1100h
0x18008b5c7  mov     [rbp+110h+hObject], 0
0x18008b5cf  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x18008b5d4  mov     rdx, rax
0x18008b5d7  mov     ecx, 8
0x18008b5dc  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x18008b5e2  mov     ebx, eax
0x18008b5e4  test    eax, eax
0x18008b5e6  jns     short loc_18008B619
0x18008b5e8  mov     edx, eax; int
0x18008b5ea  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008b5ef  mov     edx, 1
0x18008b5f4  mov     r9d, 128h
0x18008b5fa  mov     ecx, ebx
0x18008b5fc  call    Log_HREvent_31
0x18008b601  mov     rcx, [rbp+110h+hObject]; hObject
0x18008b605  test    rcx, rcx
0x18008b608  jz      loc_18008B546
0x18008b60e  call    cs:__imp_CloseHandle
0x18008b614  jmp     loc_18008B546
0x18008b619  mov     rcx, [rbp+110h+hObject]; token
0x18008b61d  lea     r8, [rbp+110h+applicationUserModelId]; applicationUserModelId
0x18008b621  lea     rdx, [rbp+110h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18008b625  mov     [rbp+110h+applicationUserModelIdLength], 84h
0x18008b62c  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18008b632  test    eax, eax
0x18008b634  jnz     short loc_18008B640
0x18008b636  lea     rax, [rbp+110h+applicationUserModelId]
0x18008b63a  mov     [rbp+110h+var_180], rax
0x18008b63e  jmp     short loc_18008B659
0x18008b640  jle     short loc_18008B64A
0x18008b642  movzx   eax, ax
0x18008b645  or      eax, 80070000h
0x18008b64a  xor     edx, edx
0x18008b64c  mov     r9d, 133h
0x18008b652  mov     ecx, eax
0x18008b654  call    Log_HREvent_31
0x18008b659  lea     rcx, [rbp+110h+var_168]
0x18008b65d  mov     [rbp+110h+var_168], 0
0x18008b665  call    cs:__imp_?CreatePerUserSecurityTokenForRpcClient@@YAJPEAPEAUISecurityToken@@@Z; CreatePerUserSecurityTokenForRpcClient(ISecurityToken * *)
0x18008b66b  mov     ebx, eax
0x18008b66d  test    eax, eax
0x18008b66f  jns     short loc_18008B6A8
0x18008b671  mov     edx, eax; int
0x18008b673  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008b678  mov     edx, 1
0x18008b67d  mov     r9d, 137h
0x18008b683  mov     ecx, ebx
0x18008b685  call    Log_HREvent_31
0x18008b68a  mov     rcx, [rbp+110h+var_168]
0x18008b68e  test    rcx, rcx
0x18008b691  jz      loc_18008B601
0x18008b697  mov     rax, [rcx]
0x18008b69a  mov     rax, [rax+10h]
0x18008b69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6a3  jmp     loc_18008B601
0x18008b6a8  lea     rdx, [rsp+210h+var_1E0]
0x18008b6ad  mov     [rsp+210h+var_1E0], 0
0x18008b6b6  lea     rcx, ?g_phoneRpcServer@@3VSecurePhoneRpcServer@@A; lpCriticalSection
0x18008b6bd  call    ?Get@?$WrappedComPtrBase@UIPhoneController@@VDoesNotSupportShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneController@@@Z; WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(IPhoneController * *)
0x18008b6c2  mov     ebx, eax
0x18008b6c4  test    eax, eax
0x18008b6c6  jns     short loc_18008B6F9
0x18008b6c8  mov     edx, eax; int
0x18008b6ca  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008b6cf  mov     edx, 1
0x18008b6d4  mov     r9d, 13Ah
0x18008b6da  mov     ecx, ebx
0x18008b6dc  call    Log_HREvent_31
0x18008b6e1  mov     rcx, [rsp+210h+var_1E0]
0x18008b6e6  test    rcx, rcx
0x18008b6e9  jz      short loc_18008B68A
0x18008b6eb  mov     rax, [rcx]
0x18008b6ee  mov     rax, [rax+10h]
0x18008b6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6f7  jmp     short loc_18008B68A
0x18008b6f9  mov     rbx, [rsp+210h+var_1E0]
0x18008b6fe  lea     rdx, [rsp+210h+var_1D0]
0x18008b703  mov     r9, [rbp+110h+var_168]
0x18008b707  xor     r8d, r8d
0x18008b70a  mov     rcx, rbx
0x18008b70d  mov     rax, [rbx]
0x18008b710  mov     rax, [rax+48h]
0x18008b714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b719  mov     edi, eax
0x18008b71b  test    eax, eax
0x18008b71d  jns     short loc_18008B774
0x18008b71f  mov     edx, eax; int
0x18008b721  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008b726  mov     edx, 1
0x18008b72b  mov     r9d, 13Bh
0x18008b731  mov     ecx, edi
0x18008b733  call    Log_HREvent_31
0x18008b738  test    rbx, rbx
0x18008b73b  jz      short loc_18008B74C
0x18008b73d  mov     rcx, [rbx]
0x18008b740  mov     rax, [rcx+10h]
0x18008b744  mov     rcx, rbx
0x18008b747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b74c  mov     rcx, [rbp+110h+var_168]
0x18008b750  test    rcx, rcx
0x18008b753  jz      short loc_18008B761
0x18008b755  mov     rax, [rcx]
0x18008b758  mov     rax, [rax+10h]
0x18008b75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b761  mov     rcx, [rbp+110h+hObject]; hObject
0x18008b765  test    rcx, rcx
0x18008b768  jz      short loc_18008B770
0x18008b76a  call    cs:__imp_CloseHandle
0x18008b770  mov     eax, edi
0x18008b772  jmp     short loc_18008B7AE
0x18008b774  test    rbx, rbx
0x18008b777  jz      short loc_18008B788
0x18008b779  mov     rax, [rbx]
0x18008b77c  mov     rcx, rbx
0x18008b77f  mov     rax, [rax+10h]
0x18008b783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b788  mov     rcx, [rbp+110h+var_168]
0x18008b78c  test    rcx, rcx
0x18008b78f  jz      short loc_18008B79D
0x18008b791  mov     rax, [rcx]
0x18008b794  mov     rax, [rax+10h]
0x18008b798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b79d  mov     rcx, [rbp+110h+hObject]; hObject
0x18008b7a1  test    rcx, rcx
0x18008b7a4  jz      short loc_18008B7AC
0x18008b7a6  call    cs:__imp_CloseHandle
0x18008b7ac  xor     eax, eax
0x18008b7ae  mov     rcx, [rbp+110h+var_40]
0x18008b7b5  xor     rcx, rsp; StackCookie
0x18008b7b8  call    __security_check_cookie
0x18008b7bd  add     rsp, 1E0h
0x18008b7c4  pop     r15
0x18008b7c6  pop     r14
0x18008b7c8  pop     r12
0x18008b7ca  pop     rdi
0x18008b7cb  pop     rsi
0x18008b7cc  pop     rbx
0x18008b7cd  pop     rbp
0x18008b7ce  retn
```

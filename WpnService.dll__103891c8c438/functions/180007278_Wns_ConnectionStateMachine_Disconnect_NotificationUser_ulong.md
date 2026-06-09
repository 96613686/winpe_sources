# Wns::ConnectionStateMachine::Disconnect(_NotificationUser,ulong)

- ea: `0x180007278`
- end: `0x1800074bc`
- name: `?Disconnect@ConnectionStateMachine@Wns@@QEAAXU_NotificationUser@@K@Z`
- size: `580`
- prototype: `void __fastcall(__int64, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025530`

## callees

- `0x180003190`
- `0x180007278`
- `0x180007760`
- `0x180008cc0`
- `0x18000a910`
- `0x18000a980`
- `0x180021048`
- `0x180032318`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800073b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800073b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007387`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007461`

## pseudocode

```c
void __fastcall Wns::ConnectionStateMachine::Disconnect(__int64 a1, unsigned __int64 *a2, unsigned int a3)
{
  unsigned __int64 v6; // r15
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  char v9; // r14
  int v10; // edi
  void *v11; // rcx
  void *v12; // rcx
  _QWORD *v13; // rcx
  unsigned __int64 v14; // r15
  __int64 v15; // rdi
  int v16; // eax
  LPVOID v17; // rcx
  void *v18; // rcx
  int v19; // edi
  int v20; // [rsp+20h] [rbp-30h]
  LPVOID *p_pv; // [rsp+30h] [rbp-20h] BYREF
  void *v22; // [rsp+38h] [rbp-18h] BYREF
  char v23; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  _QWORD *v26; // [rsp+98h] [rbp+48h] BYREF

  v6 = *a2;
  v7 = a2[1];
  Wns::CPTransactionRequestManager::ClearUserContext((Wns::CPTransactionRequestManager *)(a1 + 64), *a2);
  Wns::ConnectionStateMachine::VerifyConnected((LPCRITICAL_SECTION)a1);
  Wns::ConnectionProviderLoader::Get(*(_QWORD *)(a1 + 368), &v26);
  pv = 0;
  v8 = *v26;
  p_pv = &pv;
  v22 = 0;
  v9 = 1;
  v23 = 1;
  v10 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int64, void **))(v8 + 80))(v26, v6, &v22);
  if ( v23 )
  {
    v11 = *p_pv;
    *p_pv = v22;
    if ( v11 )
      CoTaskMemFree(v11);
  }
  if ( v10 == -2013002772 )
  {
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    v13 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    }
LABEL_9:
    Wns::ConnectionMultiplexer::OnConnectionChanged(*(_QWORD *)(a1 + 360), v6, 7);
    goto LABEL_10;
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
      (const char *)(unsigned int)v10,
      v20);
  v18 = pv;
  v19 = *((_DWORD *)pv + 3);
  pv = 0;
  if ( v18 )
    CoTaskMemFree(v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  if ( (unsigned int)(v19 - 1) > 1 )
    goto LABEL_9;
  Wns::ConnectionProviderLoader::Get(*(_QWORD *)(a1 + 368), &pv);
  p_pv = (LPVOID *)v6;
  v22 = (void *)v7;
  v16 = (*(__int64 (__fastcall **)(LPVOID, LPVOID **))(*(_QWORD *)pv + 48LL))(pv, &p_pv);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
      (const char *)(unsigned int)v16,
      v20);
  v17 = pv;
  if ( pv )
  {
    pv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  }
LABEL_10:
  v14 = *a2;
  v15 = *(_QWORD *)(a1 + 360);
  AcquireSRWLockShared((PSRWLOCK)(v15 + 8));
  if ( *(_QWORD *)(v15 + 32) != 1 || *(_QWORD *)(**(_QWORD **)(v15 + 24) + 32LL) != v14 )
    v9 = 0;
  if ( v15 != -8 )
    ReleaseSRWLockShared((PSRWLOCK)(v15 + 8));
  if ( v9 )
    Wns::ConnectionStateMachine::Disconnect((LPCRITICAL_SECTION)a1, a3);
}

```

## disassembly

```asm
0x180007278  mov     [rsp-38h+arg_10], rbx
0x18000727d  push    rbp
0x18000727e  push    rsi
0x18000727f  push    rdi
0x180007280  push    r12
0x180007282  push    r13
0x180007284  push    r14
0x180007286  push    r15
0x180007288  mov     rbp, rsp
0x18000728b  sub     rsp, 50h
0x18000728f  mov     r13d, r8d
0x180007292  mov     r12, rdx
0x180007295  mov     rsi, rcx
0x180007298  xor     edi, edi
0x18000729a  mov     r15, [rdx]
0x18000729d  mov     rbx, [rdx+8]
0x1800072a1  add     rcx, 40h ; '@'; this
0x1800072a5  mov     rdx, r15; unsigned __int64
0x1800072a8  call    ?ClearUserContext@CPTransactionRequestManager@Wns@@QEAAX_K@Z; Wns::CPTransactionRequestManager::ClearUserContext(unsigned __int64)
0x1800072ad  mov     rcx, rsi; lpCriticalSection
0x1800072b0  call    ?VerifyConnected@ConnectionStateMachine@Wns@@AEAAXXZ; Wns::ConnectionStateMachine::VerifyConnected(void)
0x1800072b5  lea     rdx, [rbp+arg_8]
0x1800072b9  mov     rcx, [rsi+170h]
0x1800072c0  call    ?Get@ConnectionProviderLoader@Wns@@QEBA?AV?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@XZ; Wns::ConnectionProviderLoader::Get(void)
0x1800072c5  nop
0x1800072c6  mov     [rbp+pv], rdi
0x1800072ca  mov     rcx, [rbp+arg_8]
0x1800072ce  mov     rax, [rcx]
0x1800072d1  lea     rdx, [rbp+pv]
0x1800072d5  mov     [rbp+var_20], rdx
0x1800072d9  mov     [rbp+var_18], rdi
0x1800072dd  lea     r14d, [rdi+1]
0x1800072e1  mov     [rbp+var_10], r14b
0x1800072e5  lea     r8, [rbp+var_18]
0x1800072e9  mov     rdx, r15
0x1800072ec  mov     rax, [rax+50h]
0x1800072f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f5  mov     edi, eax
0x1800072f7  cmp     [rbp+var_10], 0
0x1800072fb  jz      short loc_180007316
0x1800072fd  mov     r8, [rbp+var_20]
0x180007301  mov     rcx, [r8]; pv
0x180007304  mov     rdx, [rbp+var_18]
0x180007308  mov     [r8], rdx
0x18000730b  test    rcx, rcx
0x18000730e  jz      short loc_180007316
0x180007310  call    cs:__imp_CoTaskMemFree
0x180007316  cmp     edi, 880403ECh
0x18000731c  jnz     loc_180007441
0x180007322  mov     rcx, [rbp+pv]; pv
0x180007326  mov     [rbp+pv], 0
0x18000732e  test    rcx, rcx
0x180007331  jz      short loc_18000733A
0x180007333  call    cs:__imp_CoTaskMemFree
0x180007339  nop
0x18000733a  mov     rcx, [rbp+arg_8]
0x18000733e  test    rcx, rcx
0x180007341  jz      short loc_180007358
0x180007343  mov     [rbp+arg_8], 0
0x18000734b  mov     rax, [rcx]
0x18000734e  mov     rax, [rax+10h]
0x180007352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007357  nop
0x180007358  mov     word ptr [rsp+50h+var_30], 0FFFFh
0x18000735f  xor     r9d, r9d
0x180007362  lea     r8d, [r9+7]
0x180007366  mov     rdx, r15
0x180007369  mov     rcx, [rsi+168h]
0x180007370  call    ?OnConnectionChanged@ConnectionMultiplexer@Wns@@QEAAX_KW4__MIDL___MIDL_itf_wpnprivate_0000_0000_0001@@W4__MIDL___MIDL_itf_wpnconn_0000_0000_0001@@F@Z; Wns::ConnectionMultiplexer::OnConnectionChanged(unsigned __int64,__MIDL___MIDL_itf_wpnprivate_0000_0000_0001,__MIDL___MIDL_itf_wpnconn_0000_0000_0001,short)
0x180007375  mov     r15, [r12]
0x180007379  mov     rdi, [rsi+168h]
0x180007380  lea     rbx, [rdi+8]
0x180007384  mov     rcx, rbx; SRWLock
0x180007387  call    cs:__imp_AcquireSRWLockShared
0x18000738d  cmp     [rdi+20h], r14
0x180007391  jnz     loc_1800074A4
0x180007397  mov     rax, [rdi+18h]
0x18000739b  mov     rcx, [rax]
0x18000739e  cmp     [rcx+20h], r15
0x1800073a2  jnz     loc_1800074A4
0x1800073a8  test    rbx, rbx
0x1800073ab  jz      short loc_1800073B6
0x1800073ad  mov     rcx, rbx; SRWLock
0x1800073b0  call    cs:__imp_ReleaseSRWLockShared
0x1800073b6  test    r14b, r14b
0x1800073b9  jnz     loc_1800074AC
0x1800073bf  mov     rbx, [rsp+50h+arg_10]
0x1800073c7  add     rsp, 50h
0x1800073cb  pop     r15
0x1800073cd  pop     r14
0x1800073cf  pop     r13
0x1800073d1  pop     r12
0x1800073d3  pop     rdi
0x1800073d4  pop     rsi
0x1800073d5  pop     rbp
0x1800073d6  retn
0x1800073d7  lea     rcx, [rbp+arg_8]
0x1800073db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800073e0  sub     edi, 1
0x1800073e3  jnz     loc_180007481
0x1800073e9  lea     rdx, [rbp+pv]
0x1800073ed  mov     rcx, [rsi+170h]
0x1800073f4  call    ?Get@ConnectionProviderLoader@Wns@@QEBA?AV?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@XZ; Wns::ConnectionProviderLoader::Get(void)
0x1800073f9  nop
0x1800073fa  mov     rcx, [rbp+pv]
0x1800073fe  mov     [rbp+var_20], r15
0x180007402  mov     [rbp+var_18], rbx
0x180007406  mov     rax, [rcx]
0x180007409  lea     rdx, [rbp+var_20]
0x18000740d  mov     rax, [rax+30h]
0x180007411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007416  mov     rcx, [rbp+38h]; this
0x18000741a  test    eax, eax
0x18000741c  js      short loc_18000748F
0x18000741e  mov     rcx, [rbp+pv]
0x180007422  test    rcx, rcx
0x180007425  jz      short loc_18000743C
0x180007427  mov     [rbp+pv], 0
0x18000742f  mov     rax, [rcx]
0x180007432  mov     rax, [rax+10h]
0x180007436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743b  nop
0x18000743c  jmp     loc_180007375
0x180007441  mov     rcx, [rbp+38h]; this
0x180007445  test    edi, edi
0x180007447  js      short loc_18000746C
0x180007449  mov     rcx, [rbp+pv]; pv
0x18000744d  mov     edi, [rcx+0Ch]
0x180007450  mov     [rbp+pv], 0
0x180007458  test    rcx, rcx
0x18000745b  jz      loc_1800073D7
0x180007461  call    cs:__imp_CoTaskMemFree
0x180007467  jmp     loc_1800073D7
0x18000746c  mov     r9d, edi; char *
0x18000746f  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007476  mov     edx, 0ABh; void *
0x18000747b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007481  cmp     edi, 1
0x180007484  jz      loc_1800073E9
0x18000748a  jmp     loc_180007358
0x18000748f  mov     r9d, eax; char *
0x180007492  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007499  mov     edx, 0CBh; void *
0x18000749e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800074a4  xor     r14b, r14b
0x1800074a7  jmp     loc_1800073A8
0x1800074ac  mov     edx, r13d; unsigned int
0x1800074af  mov     rcx, rsi; lpCriticalSection
0x1800074b2  call    ?Disconnect@ConnectionStateMachine@Wns@@AEAAXI@Z; Wns::ConnectionStateMachine::Disconnect(uint)
0x1800074b7  jmp     loc_1800073BF
```

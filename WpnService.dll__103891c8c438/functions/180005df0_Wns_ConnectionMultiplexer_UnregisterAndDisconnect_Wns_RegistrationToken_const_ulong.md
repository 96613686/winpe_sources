# Wns::ConnectionMultiplexer::UnregisterAndDisconnect(Wns::RegistrationToken const &,ulong)

- ea: `0x180005df0`
- end: `0x18000613e`
- name: `?UnregisterAndDisconnect@ConnectionMultiplexer@Wns@@QEAAXAEBVRegistrationToken@2@K@Z`
- size: `846`
- prototype: `void __fastcall(Wns::ConnectionMultiplexer *__hidden this, const struct Wns::RegistrationToken *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800058d4`

## callees

- `0x180003190`
- `0x180005df0`
- `0x180006144`
- `0x180006160`
- `0x1800061a0`
- `0x180007760`
- `0x180008cc0`
- `0x18000a910`
- `0x18000a980`
- `0x180021048`
- `0x180032318`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000610f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000610f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800060eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800060eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000603c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000603c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Wns::ConnectionMultiplexer::UnregisterAndDisconnect(
        Wns::ConnectionMultiplexer *this,
        const struct Wns::RegistrationToken *a2,
        unsigned int a3)
{
  unsigned __int64 v5; // r15
  char v6; // r14
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 *i; // rbx
  LPVOID **v10; // rcx
  char v11; // al
  __int64 *v12; // rax
  __int64 *j; // rdx
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // ebx
  void *v17; // rcx
  void *v18; // rcx
  _QWORD *v19; // rcx
  void *v20; // rcx
  int v21; // ebx
  int v22; // eax
  LPVOID v23; // rcx
  __int64 v24; // rdi
  int v25; // [rsp+20h] [rbp-50h]
  LPVOID *p_pv; // [rsp+30h] [rbp-40h] BYREF
  LPVOID *v27; // [rsp+38h] [rbp-38h] BYREF
  char v28; // [rsp+40h] [rbp-30h]
  __int64 v29; // [rsp+50h] [rbp-20h]
  unsigned __int64 v30; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  LPVOID pv; // [rsp+B0h] [rbp+40h] BYREF
  _QWORD *v33; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v34; // [rsp+C0h] [rbp+50h]

  v34 = a3;
  v5 = *(_QWORD *)this;
  if ( *(_QWORD *)a2 != *(_QWORD *)this )
    v5 = *(_QWORD *)a2;
  v6 = 1;
  LODWORD(pv) = (*(_QWORD *)a2 != *(_QWORD *)this) + 1;
  p_pv = 0;
  v27 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  v33 = (_QWORD *)((char *)this + 8);
  v7 = (__int64 *)*((_QWORD *)this + 3);
  v8 = (__int64 *)v7[1];
  HIDWORD(v30) = 0;
  for ( i = v7; !*((_BYTE *)v8 + 25); v8 = (__int64 *)*v8 )
  {
    if ( (unsigned __int64)v8[4] >= *(_QWORD *)a2 )
      i = v8;
    else
      v8 += 2;
  }
  if ( *((_BYTE *)i + 25) || *(_QWORD *)a2 < (unsigned __int64)i[4] )
  {
    i = v7;
    goto LABEL_14;
  }
  if ( i == v7 )
  {
LABEL_14:
    v10 = (LPVOID **)(i + 5);
    goto LABEL_15;
  }
  v10 = (LPVOID **)(i + 5);
  if ( i[5] == *((_QWORD *)a2 + 1) )
  {
    v11 = 0;
    goto LABEL_16;
  }
LABEL_15:
  v11 = 1;
LABEL_16:
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmultiplexer.cpp",
      (const char *)0x8000FFFFLL,
      v25);
  v29 = 0;
  p_pv = *v10;
  v27 = v10[1];
  *v10 = 0;
  v30 = 0;
  v10[1] = 0;
  std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>((__int64 (__fastcall ****)(_QWORD, __int64))&v30);
  if ( *(_BYTE *)(i[2] + 25) )
  {
    v12 = i;
    for ( j = (__int64 *)i[1]; !*((_BYTE *)j + 25) && v12 == (__int64 *)j[2]; j = (__int64 *)j[1] )
      v12 = j;
  }
  v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,Wns::RegistrationEntry>>>::_Extract(
          (char *)this + 24,
          i);
  std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>((__int64 (__fastcall ****)(_QWORD, __int64))(v14 + 48));
  std::_Deallocate<16>((_QWORD *)v14, 0x38u);
  if ( this != (Wns::ConnectionMultiplexer *)-8LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 1);
  std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>((__int64 (__fastcall ****)(_QWORD, __int64))&v27);
  v30 = (unsigned int)pv;
  Wns::CPTransactionRequestManager::ClearUserContext((Wns::ConnectionMultiplexer *)((char *)this + 104), v5);
  Wns::ConnectionStateMachine::VerifyConnected((LPCRITICAL_SECTION)this + 1);
  Wns::ConnectionProviderLoader::Get(*((_QWORD *)this + 51), &v33);
  pv = 0;
  v15 = *v33;
  p_pv = &pv;
  v27 = 0;
  v28 = 1;
  v16 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int64, LPVOID **))(v15 + 80))(v33, v5, &v27);
  if ( v28 )
  {
    v17 = *p_pv;
    *p_pv = v27;
    if ( v17 )
      CoTaskMemFree(v17);
  }
  if ( v16 == -2013002772 )
  {
    v18 = pv;
    pv = 0;
    if ( v18 )
      CoTaskMemFree(v18);
    v19 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
LABEL_39:
    Wns::ConnectionMultiplexer::OnConnectionChanged(*((_QWORD *)this + 50), v5, 7);
    goto LABEL_44;
  }
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
      (const char *)(unsigned int)v16,
      v25);
  v20 = pv;
  v21 = *((_DWORD *)pv + 3);
  pv = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  if ( (unsigned int)(v21 - 1) >= 2 )
    goto LABEL_39;
  Wns::ConnectionProviderLoader::Get(*((_QWORD *)this + 51), &pv);
  p_pv = (LPVOID *)v5;
  v27 = (LPVOID *)v30;
  v22 = (*(__int64 (__fastcall **)(LPVOID, LPVOID **))(*(_QWORD *)pv + 48LL))(pv, &p_pv);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
      (const char *)(unsigned int)v22,
      v25);
  v23 = pv;
  if ( pv )
  {
    pv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
  }
LABEL_44:
  v24 = *((_QWORD *)this + 50);
  AcquireSRWLockShared((PSRWLOCK)(v24 + 8));
  if ( *(_QWORD *)(v24 + 32) != 1 || *(_QWORD *)(**(_QWORD **)(v24 + 24) + 32LL) != v5 )
    v6 = 0;
  if ( v24 != -8 )
    ReleaseSRWLockShared((PSRWLOCK)(v24 + 8));
  if ( v6 )
    Wns::ConnectionStateMachine::Disconnect((LPCRITICAL_SECTION)this + 1, v34);
}

```

## disassembly

```asm
0x180005df0  mov     [rsp-38h+arg_18], rbx
0x180005df5  mov     [rsp-38h+arg_10], r8d
0x180005dfa  push    rbp
0x180005dfb  push    rsi
0x180005dfc  push    rdi
0x180005dfd  push    r12
0x180005dff  push    r13
0x180005e01  push    r14
0x180005e03  push    r15
0x180005e05  mov     rbp, rsp
0x180005e08  sub     rsp, 70h
0x180005e0c  mov     rdi, rdx
0x180005e0f  mov     r13, rcx
0x180005e12  xor     edx, edx
0x180005e14  mov     r15, [rcx]
0x180005e17  cmp     [rdi], r15
0x180005e1a  cmovnz  r15, [rdi]
0x180005e1e  mov     ecx, edx
0x180005e20  setnz   cl
0x180005e23  lea     r14d, [rdx+1]
0x180005e27  add     ecx, r14d
0x180005e2a  mov     dword ptr [rbp+pv], ecx
0x180005e2d  mov     [rbp+var_40], rdx
0x180005e31  mov     [rbp+var_38], rdx
0x180005e35  lea     rsi, [r13+8]
0x180005e39  mov     rcx, rsi; SRWLock
0x180005e3c  call    cs:__imp_AcquireSRWLockExclusive
0x180005e42  mov     [rbp+arg_8], rsi
0x180005e46  mov     rcx, [r13+18h]
0x180005e4a  mov     rax, [rcx+8]
0x180005e4e  xor     edx, edx
0x180005e50  mov     dword ptr [rbp+var_18+4], edx
0x180005e53  mov     rbx, rcx
0x180005e56  xor     r8d, r8d
0x180005e59  cmp     [rax+19h], r8b
0x180005e5d  jnz     short loc_180005E7A
0x180005e5f  mov     rdx, [rdi]
0x180005e62  cmp     [rax+20h], rdx
0x180005e66  jnb     short loc_180005E6E
0x180005e68  add     rax, 10h
0x180005e6c  jmp     short loc_180005E71
0x180005e6e  mov     rbx, rax
0x180005e71  mov     rax, [rax]
0x180005e74  cmp     [rax+19h], r8b
0x180005e78  jz      short loc_180005E62
0x180005e7a  cmp     [rbx+19h], r8b
0x180005e7e  jnz     short loc_180005EA2
0x180005e80  mov     rax, [rbx+20h]
0x180005e84  cmp     [rdi], rax
0x180005e87  jb      short loc_180005EA2
0x180005e89  cmp     rbx, rcx
0x180005e8c  jz      short loc_180005EA5
0x180005e8e  lea     rcx, [rbx+28h]
0x180005e92  mov     rax, [rdi+8]
0x180005e96  cmp     [rcx], rax
0x180005e99  jnz     short loc_180005EA9
0x180005e9b  xor     edi, edi
0x180005e9d  mov     al, dil
0x180005ea0  jmp     short loc_180005EAE
0x180005ea2  mov     rbx, rcx
0x180005ea5  lea     rcx, [rbx+28h]
0x180005ea9  mov     al, r14b
0x180005eac  xor     edi, edi
0x180005eae  mov     r10, [rbp+38h]
0x180005eb2  test    al, al
0x180005eb4  jz      short loc_180005ED1
0x180005eb6  mov     r9d, 8000FFFFh; char *
0x180005ebc  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005ec3  mov     edx, 72h ; 'r'; void *
0x180005ec8  mov     rcx, r10; this
0x180005ecb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005ed1  mov     [rbp+var_20], rdi
0x180005ed5  mov     rax, [rcx]
0x180005ed8  mov     [rbp+var_40], rax
0x180005edc  mov     rax, [rcx+8]
0x180005ee0  mov     [rbp+var_38], rax
0x180005ee4  mov     [rcx], rdi
0x180005ee7  mov     [rbp-18h], rdi
0x180005eeb  mov     [rcx+8], rdi
0x180005eef  lea     rcx, [rbp+var_18]
0x180005ef3  call    ??1?$unique_ptr@UCallback@Wns@@U?$default_delete@UCallback@Wns@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>(void)
0x180005ef8  mov     rax, [rbx+10h]
0x180005efc  cmp     [rax+19h], dil
0x180005f00  jz      short loc_180005F1E
0x180005f02  mov     rax, rbx
0x180005f05  mov     rdx, [rbx+8]
0x180005f09  jmp     short loc_180005F18
0x180005f0b  cmp     rax, [rdx+10h]
0x180005f0f  jnz     short loc_180005F1E
0x180005f11  mov     rax, rdx
0x180005f14  mov     rdx, [rdx+8]
0x180005f18  cmp     [rdx+19h], dil
0x180005f1c  jz      short loc_180005F0B
0x180005f1e  mov     rdx, rbx
0x180005f21  lea     rcx, [r13+18h]
0x180005f25  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KVRegistrationEntry@Wns@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KVRegistrationEntry@Wns@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KVRegistrationEntry@Wns@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,Wns::RegistrationEntry>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,Wns::RegistrationEntry>>>,std::_Iterator_base0>)
0x180005f2a  mov     rbx, rax
0x180005f2d  lea     rcx, [rax+30h]
0x180005f31  call    ??1?$unique_ptr@UCallback@Wns@@U?$default_delete@UCallback@Wns@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>(void)
0x180005f36  mov     edx, 38h ; '8'
0x180005f3b  mov     rcx, rbx
0x180005f3e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180005f43  nop
0x180005f44  test    rsi, rsi
0x180005f47  jz      short loc_180005F53
0x180005f49  mov     rcx, rsi; SRWLock
0x180005f4c  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f52  nop
0x180005f53  lea     rcx, [rbp+var_38]
0x180005f57  call    ??1?$unique_ptr@UCallback@Wns@@U?$default_delete@UCallback@Wns@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>(void)
0x180005f5c  mov     eax, dword ptr [rbp+pv]
0x180005f5f  mov     dword ptr [rbp+var_18], eax
0x180005f62  mov     dword ptr [rbp+var_18+4], edi
0x180005f65  lea     rcx, [r13+68h]; this
0x180005f69  mov     rdx, r15; unsigned __int64
0x180005f6c  call    ?ClearUserContext@CPTransactionRequestManager@Wns@@QEAAX_K@Z; Wns::CPTransactionRequestManager::ClearUserContext(unsigned __int64)
0x180005f71  lea     rcx, [r13+28h]; lpCriticalSection
0x180005f75  call    ?VerifyConnected@ConnectionStateMachine@Wns@@AEAAXXZ; Wns::ConnectionStateMachine::VerifyConnected(void)
0x180005f7a  lea     rdx, [rbp+arg_8]
0x180005f7e  mov     rcx, [r13+198h]
0x180005f85  call    ?Get@ConnectionProviderLoader@Wns@@QEBA?AV?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@XZ; Wns::ConnectionProviderLoader::Get(void)
0x180005f8a  nop
0x180005f8b  mov     [rbp+pv], rdi
0x180005f8f  mov     rcx, [rbp+arg_8]
0x180005f93  mov     rax, [rcx]
0x180005f96  lea     rdx, [rbp+pv]
0x180005f9a  mov     [rbp+var_40], rdx
0x180005f9e  mov     [rbp+var_38], rdi
0x180005fa2  mov     [rbp+var_30], r14b
0x180005fa6  lea     r8, [rbp+var_38]
0x180005faa  mov     rdx, r15
0x180005fad  mov     rax, [rax+50h]
0x180005fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb6  mov     ebx, eax
0x180005fb8  cmp     [rbp+var_30], dil
0x180005fbc  jz      short loc_180005FD7
0x180005fbe  mov     r8, [rbp+var_40]
0x180005fc2  mov     rcx, [r8]; pv
0x180005fc5  mov     rdx, [rbp+var_38]
0x180005fc9  mov     [r8], rdx
0x180005fcc  test    rcx, rcx
0x180005fcf  jz      short loc_180005FD7
0x180005fd1  call    cs:__imp_CoTaskMemFree
0x180005fd7  cmp     ebx, 880403ECh
0x180005fdd  jnz     short loc_18000600F
0x180005fdf  mov     rcx, [rbp+pv]; pv
0x180005fe3  mov     [rbp+pv], rdi
0x180005fe7  test    rcx, rcx
0x180005fea  jz      short loc_180005FF3
0x180005fec  call    cs:__imp_CoTaskMemFree
0x180005ff2  nop
0x180005ff3  mov     rcx, [rbp+arg_8]
0x180005ff7  test    rcx, rcx
0x180005ffa  jz      short loc_18000600D
0x180005ffc  mov     [rbp+arg_8], rdi
0x180006000  mov     rax, [rcx]
0x180006003  mov     rax, [rax+10h]
0x180006007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600c  nop
0x18000600d  jmp     short loc_180006056
0x18000600f  mov     rcx, [rbp+38h]; this
0x180006013  test    ebx, ebx
0x180006015  jns     short loc_18000602C
0x180006017  mov     r9d, ebx; char *
0x18000601a  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006021  mov     edx, 0ABh; void *
0x180006026  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000602c  mov     rcx, [rbp+pv]; pv
0x180006030  mov     ebx, [rcx+0Ch]
0x180006033  mov     [rbp+pv], rdi
0x180006037  test    rcx, rcx
0x18000603a  jz      short loc_180006043
0x18000603c  call    cs:__imp_CoTaskMemFree
0x180006042  nop
0x180006043  lea     rcx, [rbp+arg_8]
0x180006047  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000604c  sub     ebx, 1
0x18000604f  jz      short loc_180006075
0x180006051  cmp     ebx, 1
0x180006054  jz      short loc_180006075
0x180006056  mov     word ptr [rsp+70h+var_50], 0FFFFh
0x18000605d  xor     r9d, r9d
0x180006060  lea     r8d, [r9+7]
0x180006064  mov     rdx, r15
0x180006067  mov     rcx, [r13+190h]
0x18000606e  call    ?OnConnectionChanged@ConnectionMultiplexer@Wns@@QEAAX_KW4__MIDL___MIDL_itf_wpnprivate_0000_0000_0001@@W4__MIDL___MIDL_itf_wpnconn_0000_0000_0001@@F@Z; Wns::ConnectionMultiplexer::OnConnectionChanged(unsigned __int64,__MIDL___MIDL_itf_wpnprivate_0000_0000_0001,__MIDL___MIDL_itf_wpnconn_0000_0000_0001,short)
0x180006073  jmp     short loc_1800060DD
0x180006075  lea     rdx, [rbp+pv]
0x180006079  mov     rcx, [r13+198h]
0x180006080  call    ?Get@ConnectionProviderLoader@Wns@@QEBA?AV?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@XZ; Wns::ConnectionProviderLoader::Get(void)
0x180006085  nop
0x180006086  mov     rcx, [rbp+pv]
0x18000608a  mov     [rbp+var_40], r15
0x18000608e  mov     rax, [rbp+var_18]
0x180006092  mov     [rbp+var_38], rax
0x180006096  mov     rax, [rcx]
0x180006099  lea     rdx, [rbp+var_40]
0x18000609d  mov     rax, [rax+30h]
0x1800060a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a6  mov     rcx, [rbp+38h]; this
0x1800060aa  test    eax, eax
0x1800060ac  jns     short loc_1800060C3
0x1800060ae  mov     r9d, eax; char *
0x1800060b1  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800060b8  mov     edx, 0CBh; void *
0x1800060bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800060c3  mov     rcx, [rbp+pv]
0x1800060c7  test    rcx, rcx
0x1800060ca  jz      short loc_1800060DD
0x1800060cc  mov     [rbp+pv], rdi
0x1800060d0  mov     rax, [rcx]
0x1800060d3  mov     rax, [rax+10h]
0x1800060d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060dc  nop
0x1800060dd  mov     rdi, [r13+190h]
0x1800060e4  lea     rbx, [rdi+8]
0x1800060e8  mov     rcx, rbx; SRWLock
0x1800060eb  call    cs:__imp_AcquireSRWLockShared
0x1800060f1  cmp     [rdi+20h], r14
0x1800060f5  jnz     short loc_180006104
0x1800060f7  mov     rax, [rdi+18h]
0x1800060fb  mov     rcx, [rax]
0x1800060fe  cmp     [rcx+20h], r15
0x180006102  jz      short loc_180006107
0x180006104  xor     r14b, r14b
0x180006107  test    rbx, rbx
0x18000610a  jz      short loc_180006115
0x18000610c  mov     rcx, rbx; SRWLock
0x18000610f  call    cs:__imp_ReleaseSRWLockShared
0x180006115  test    r14b, r14b
0x180006118  jz      short loc_180006126
0x18000611a  mov     edx, [rbp+arg_10]; unsigned int
0x18000611d  lea     rcx, [r13+28h]; lpCriticalSection
0x180006121  call    ?Disconnect@ConnectionStateMachine@Wns@@AEAAXI@Z; Wns::ConnectionStateMachine::Disconnect(uint)
0x180006126  mov     rbx, [rsp+70h+arg_18]
0x18000612e  add     rsp, 70h
0x180006132  pop     r15
0x180006134  pop     r14
0x180006136  pop     r13
0x180006138  pop     r12
0x18000613a  pop     rdi
0x18000613b  pop     rsi
0x18000613c  pop     rbp
0x18000613d  retn
```

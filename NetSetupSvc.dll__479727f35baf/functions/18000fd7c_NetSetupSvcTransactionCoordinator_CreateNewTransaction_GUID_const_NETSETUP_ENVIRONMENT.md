# NetSetupSvcTransactionCoordinator::CreateNewTransaction(_GUID const &,_NETSETUP_ENVIRONMENT *)

- ea: `0x18000fd7c`
- end: `0x18000ffce`
- name: `?CreateNewTransaction@NetSetupSvcTransactionCoordinator@@QEAA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@std@@AEBU_GUID@@PEAU_NETSETUP_ENVIRONMENT@@@Z`
- size: `594`
- prototype: `_QWORD *__fastcall(struct StackLock *, _QWORD *, _QWORD *, __int64)`
- caller_count: `4`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180009cfc`
- `0x18000c5e0`
- `0x1800137fc`
- `0x180022fd4`

## callees

- `0x1800027c0`
- `0x180002bcc`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x18000d8ec`
- `0x18000f8ac`
- `0x18000fab0`
- `0x18000faf4`
- `0x18000fb84`
- `0x18000fd7c`
- `0x18001023c`
- `0x180010284`
- `0x180028b20`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ff1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ff1e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ff9a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ff9a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000ff2c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000ff2c`
- `NetSetupApi!NetSetupInitialize` at `0x18000ff38`
- `NetSetupApi!NetSetupInitialize` at `0x18000ff38`

## pseudocode

```c
_QWORD *__fastcall NetSetupSvcTransactionCoordinator::CreateNewTransaction(
        struct StackLock *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 *v7; // r15
  __int64 v8; // rdi
  __int64 v9; // r12
  __int64 v10; // rax
  std::_Ref_count_base *v11; // rbx
  _DWORD *v12; // rdi
  PCONDITION_VARIABLE v13; // rbx
  char v14; // r14
  char *Ptr; // rax
  int v16; // ebx
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v20; // [rsp+100h] [rbp+0h] BYREF
  std::_Ref_count_base *v21; // [rsp+108h] [rbp+8h]
  PCONDITION_VARIABLE ConditionVariable[4]; // [rsp+110h] [rbp+10h] BYREF
  char v23; // [rsp+130h] [rbp+30h]

  v7 = (__int64 *)((char *)a1 + 32);
  AcquiredStackLock::AcquiredStackLock((AcquiredStackLock *)ConditionVariable, a1, (unsigned __int64)a3);
  v8 = *v7;
  v9 = v7[1];
  while ( v8 != v9 )
  {
    std::weak_ptr<NetSetupSvcTxHolder>::lock(v8, &v20);
    if ( v20 )
    {
      v10 = *((_QWORD *)v20 + 1) - *a3;
      if ( !v10 )
        v10 = *((_QWORD *)v20 + 2) - a3[1];
      if ( !v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF__guid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_d596e939d82835bb85264efd7f900c46_Traceguids,
            a3,
            0,
            a2);
        HResultException::HResultException((HResultException *)pExceptionObject, -2147024713);
        throw (HResultException *)pExceptionObject;
      }
    }
    v11 = v21;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(std::_Ref_count_base *))v11)(v11);
        std::_Ref_count_base::_Decwref(v11);
      }
    }
    v8 += 16;
  }
  v12 = operator new(0x30u);
  v20 = v12;
  *(_OWORD *)v12 = 0;
  v12[2] = 1;
  v12[3] = 1;
  *(_QWORD *)v12 = &std::_Ref_count_obj2<NetSetupSvcTxHolder>::`vftable';
  std::_Construct_in_place<NetSetupSvcTxHolder,_GUID const &>(v12 + 4, a3);
  *a2 = v12 + 4;
  a2[1] = v12;
  std::vector<std::weak_ptr<NetSetupSvcTxHolder>>::emplace_back<std::shared_ptr<NetSetupSvcTxHolder> &>(v7, a2);
  v23 = 0;
  v13 = ConditionVariable[0];
  RtlSrwLock::AcquireExclusive((RtlSrwLock *)&ConditionVariable[0][1]);
  --*((_DWORD *)v13[3].Ptr + 2);
  v14 = 0;
  Ptr = (char *)v13[3].Ptr;
  if ( !*((_DWORD *)Ptr + 2) )
  {
    v13[3].Ptr = *(PVOID *)(Ptr + 16);
    v14 = 1;
  }
  LODWORD(v13[2].Ptr) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)&v13[1]);
  if ( v14 )
    WakeAllConditionVariable(v13);
  v16 = NetSetupInitialize(a4, *a2);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_d596e939d82835bb85264efd7f900c46_Traceguids,
        (unsigned int)v16);
    HResultException::HResultException((HResultException *)pExceptionObject, v16);
    throw (HResultException *)pExceptionObject;
  }
  SetEvent(*(HANDLE *)(*a2 + 24LL));
  StackLockHolder::~StackLockHolder((StackLockHolder *)ConditionVariable);
  return a2;
}

```

## disassembly

```asm
0x18000fd7c  push    rbp
0x18000fd7e  push    rbx
0x18000fd7f  push    rsi
0x18000fd80  push    rdi
0x18000fd81  push    r12
0x18000fd83  push    r13
0x18000fd85  push    r14
0x18000fd87  push    r15
0x18000fd89  lea     rbp, [rsp-48h]
0x18000fd8e  sub     rsp, 148h
0x18000fd95  mov     rax, cs:__security_cookie
0x18000fd9c  xor     rax, rsp
0x18000fd9f  mov     [rbp+80h+var_48], rax
0x18000fda3  mov     r13, r9
0x18000fda6  mov     r14, r8
0x18000fda9  mov     rsi, rdx
0x18000fdac  lea     r15, [rcx+20h]
0x18000fdb0  mov     [rsp+180h+var_158], rdx
0x18000fdb5  mov     [rsp+180h+var_160], 0
0x18000fdbd  mov     rdx, rcx; struct StackLock *
0x18000fdc0  lea     rcx, [rbp+80h+ConditionVariable]; this
0x18000fdc4  call    ??0AcquiredStackLock@@QEAA@AEAVStackLock@@_K@Z; AcquiredStackLock::AcquiredStackLock(StackLock &,unsigned __int64)
0x18000fdc9  nop
0x18000fdca  mov     rdi, [r15]
0x18000fdcd  mov     r12, [r15+8]
0x18000fdd1  cmp     rdi, r12
0x18000fdd4  jz      loc_18000FE8A
0x18000fdda  lea     rdx, [rbp+80h+var_80]
0x18000fdde  mov     rcx, rdi
0x18000fde1  call    ?lock@?$weak_ptr@UNetSetupSvcTxHolder@@@std@@QEBA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@2@XZ; std::weak_ptr<NetSetupSvcTxHolder>::lock(void)
0x18000fde6  nop
0x18000fde7  mov     rcx, [rbp+80h+var_80]
0x18000fdeb  test    rcx, rcx
0x18000fdee  jz      short loc_18000FE06
0x18000fdf0  mov     rax, [rcx+8]
0x18000fdf4  sub     rax, [r14]
0x18000fdf7  jnz     short loc_18000FE01
0x18000fdf9  mov     rax, [rcx+10h]
0x18000fdfd  sub     rax, [r14+8]
0x18000fe01  test    rax, rax
0x18000fe04  jz      short loc_18000FE38
0x18000fe06  mov     rbx, [rbp+80h+var_78]
0x18000fe0a  test    rbx, rbx
0x18000fe0d  jz      short loc_18000FE32
0x18000fe0f  or      eax, 0FFFFFFFFh
0x18000fe12  lock xadd [rbx+8], eax
0x18000fe17  cmp     eax, 1
0x18000fe1a  jnz     short loc_18000FE32
0x18000fe1c  mov     rax, [rbx]
0x18000fe1f  mov     rcx, rbx
0x18000fe22  mov     rax, [rax]
0x18000fe25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe2a  mov     rcx, rbx; this
0x18000fe2d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000fe32  add     rdi, 10h
0x18000fe36  jmp     short loc_18000FDD1
0x18000fe38  lea     rax, WPP_GLOBAL_Control
0x18000fe3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe46  cmp     rcx, rax
0x18000fe49  jz      short loc_18000FE69
0x18000fe4b  cmp     byte ptr [rcx+19h], 2
0x18000fe4f  jb      short loc_18000FE69
0x18000fe51  mov     edx, 0Ah
0x18000fe56  mov     r9, r14
0x18000fe59  lea     r8, WPP_d596e939d82835bb85264efd7f900c46_Traceguids
0x18000fe60  mov     rcx, [rcx+10h]
0x18000fe64  call    WPP_SF__guid_
0x18000fe69  mov     edx, 800700B7h; int
0x18000fe6e  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000fe73  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000fe78  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000fe7f  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18000fe84  call    _CxxThrowException_0
0x18000fe8a  mov     ecx, 30h ; '0'; Size
0x18000fe8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fe94  mov     rdi, rax
0x18000fe97  mov     [rbp+80h+var_80], rax
0x18000fe9b  xorps   xmm0, xmm0
0x18000fe9e  movups  xmmword ptr [rax], xmm0
0x18000fea1  mov     r12d, 1
0x18000fea7  mov     [rax+8], r12d
0x18000feab  mov     [rax+0Ch], r12d
0x18000feaf  lea     rax, ??_7?$_Ref_count_obj2@UNetSetupSvcTxHolder@@@std@@6B@; const std::_Ref_count_obj2<NetSetupSvcTxHolder>::`vftable'
0x18000feb6  mov     [rdi], rax
0x18000feb9  lea     rbx, [rdi+10h]
0x18000febd  mov     rdx, r14
0x18000fec0  mov     rcx, rbx
0x18000fec3  call    ??$_Construct_in_place@UNetSetupSvcTxHolder@@AEBU_GUID@@@std@@YAXAEAUNetSetupSvcTxHolder@@AEBU_GUID@@@Z; std::_Construct_in_place<NetSetupSvcTxHolder,_GUID const &>(NetSetupSvcTxHolder &,_GUID const &)
0x18000fec8  nop
0x18000fec9  mov     [rsi], rbx
0x18000fecc  mov     [rsi+8], rdi
0x18000fed0  mov     [rsp+180h+var_160], 3
0x18000fed8  mov     rdx, rsi
0x18000fedb  mov     rcx, r15
0x18000fede  call    ??$emplace_back@AEAV?$shared_ptr@UNetSetupSvcTxHolder@@@std@@@?$vector@V?$weak_ptr@UNetSetupSvcTxHolder@@@std@@V?$allocator@V?$weak_ptr@UNetSetupSvcTxHolder@@@std@@@2@@std@@QEAAAEAV?$weak_ptr@UNetSetupSvcTxHolder@@@1@AEAV?$shared_ptr@UNetSetupSvcTxHolder@@@1@@Z; std::vector<std::weak_ptr<NetSetupSvcTxHolder>>::emplace_back<std::shared_ptr<NetSetupSvcTxHolder> &>(std::shared_ptr<NetSetupSvcTxHolder> &)
0x18000fee3  xor     r15d, r15d
0x18000fee6  mov     [rbp+80h+var_50], r15b
0x18000feea  mov     rbx, [rbp+80h+ConditionVariable]
0x18000feee  lea     rcx, [rbx+8]; this
0x18000fef2  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18000fef7  mov     rax, [rbx+18h]
0x18000fefb  dec     dword ptr [rax+8]
0x18000fefe  mov     r14b, r15b
0x18000ff01  mov     rax, [rbx+18h]
0x18000ff05  cmp     [rax+8], r15d
0x18000ff09  jnz     short loc_18000FF16
0x18000ff0b  mov     rax, [rax+10h]
0x18000ff0f  mov     [rbx+18h], rax
0x18000ff13  mov     r14b, r12b
0x18000ff16  mov     [rbx+10h], r15d
0x18000ff1a  lea     rcx, [rbx+8]; SRWLock
0x18000ff1e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ff24  test    r14b, r14b
0x18000ff27  jz      short loc_18000FF32
0x18000ff29  mov     rcx, rbx; ConditionVariable
0x18000ff2c  call    cs:__imp_WakeAllConditionVariable
0x18000ff32  mov     rdx, [rsi]
0x18000ff35  mov     rcx, r13
0x18000ff38  call    cs:__imp_NetSetupInitialize
0x18000ff3e  mov     ebx, eax
0x18000ff40  test    eax, eax
0x18000ff42  jns     short loc_18000FF93
0x18000ff44  lea     rax, WPP_GLOBAL_Control
0x18000ff4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff52  cmp     rcx, rax
0x18000ff55  jz      short loc_18000FF75
0x18000ff57  cmp     byte ptr [rcx+19h], 2
0x18000ff5b  jb      short loc_18000FF75
0x18000ff5d  mov     edx, 0Bh
0x18000ff62  mov     r9d, ebx
0x18000ff65  lea     r8, WPP_d596e939d82835bb85264efd7f900c46_Traceguids
0x18000ff6c  mov     rcx, [rcx+10h]
0x18000ff70  call    WPP_SF_d
0x18000ff75  mov     edx, ebx; int
0x18000ff77  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000ff7c  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000ff81  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000ff88  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18000ff8d  call    _CxxThrowException_0
0x18000ff93  mov     rcx, [rsi]
0x18000ff96  mov     rcx, [rcx+18h]; hEvent
0x18000ff9a  call    cs:__imp_SetEvent
0x18000ffa0  nop
0x18000ffa1  lea     rcx, [rbp+80h+ConditionVariable]; this
0x18000ffa5  call    ??1StackLockHolder@@QEAA@XZ; StackLockHolder::~StackLockHolder(void)
0x18000ffaa  mov     rax, rsi
0x18000ffad  mov     rcx, [rbp+80h+var_48]
0x18000ffb1  xor     rcx, rsp; StackCookie
0x18000ffb4  call    __security_check_cookie
0x18000ffb9  add     rsp, 148h
0x18000ffc0  pop     r15
0x18000ffc2  pop     r14
0x18000ffc4  pop     r13
0x18000ffc6  pop     r12
0x18000ffc8  pop     rdi
0x18000ffc9  pop     rsi
0x18000ffca  pop     rbx
0x18000ffcb  pop     rbp
0x18000ffcc  retn
```

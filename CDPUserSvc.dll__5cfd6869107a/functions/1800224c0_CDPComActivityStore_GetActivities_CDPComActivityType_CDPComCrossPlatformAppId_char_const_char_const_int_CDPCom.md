# CDPComActivityStore::GetActivities(CDPComActivityType,CDPComCrossPlatformAppId *,char const *,char const *,int,CDPComActivityData * *,ushort,ushort *)

- ea: `0x1800224c0`
- end: `0x1800226da`
- name: `?GetActivities@CDPComActivityStore@@UEAAJW4CDPComActivityType@@PEAUCDPComCrossPlatformAppId@@PEBD2HPEAPEAUCDPComActivityData@@GPEAG@Z`
- size: `538`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x1800097d0`
- `0x18000b270`
- `0x1800112cc`
- `0x180011450`
- `0x180013908`
- `0x180014cdc`
- `0x180021b3c`
- `0x1800224c0`
- `0x180023b70`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022534`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022534`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022646`

## pseudocode

```c
__int64 __fastcall CDPComActivityStore::GetActivities(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _QWORD *a7,
        unsigned __int16 a8,
        unsigned __int16 *a9)
{
  _QWORD *v12; // r15
  int v13; // edi
  unsigned __int16 *v15; // r14
  __int64 v16; // rbx
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r9
  unsigned __int16 v21; // bx
  LPVOID v22; // rbx
  unsigned __int16 i; // si
  __int64 v24; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-39h] BYREF
  __int64 v26; // [rsp+68h] [rbp-29h] BYREF
  std::_Ref_count_base *v27[2]; // [rsp+70h] [rbp-21h] BYREF
  _QWORD v28[10]; // [rsp+80h] [rbp-11h] BYREF
  unsigned int v29; // [rsp+E8h] [rbp+57h]

  v29 = a2;
  v12 = a7;
  v13 = 0;
  if ( !a7 )
  {
    LODWORD(v24) = 525;
LABEL_3:
    LODWORD(a7) = -2147467261;
    Log<long &,char const (&)[27],int>(a1, a2, &a7, a4, &v24);
    return (unsigned int)a7;
  }
  v15 = a9;
  if ( !a9 )
  {
    LODWORD(v24) = 526;
    goto LABEL_3;
  }
  v16 = a1 + 32;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 32));
  v26 = v16;
  *v15 = 0;
  *v12 = 0;
  *(_OWORD *)v27 = 0;
  if ( !a3 )
    goto LABEL_11;
  v25[0] = 0;
  v25[1] = v27;
  v17 = CDPCrossPlatformAppIdFromComCrossPlatformAppId(a3, v25);
  cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(v25);
  if ( v17 != -2147024809 )
    v13 = v17;
  if ( v13 < 0 )
  {
    LODWORD(a7) = v13;
    LODWORD(v24) = 542;
    Log<long &,char const (&)[27],int>(v19, v18, &a7, v20, &v24);
    v13 = (int)a7;
  }
  else
  {
LABEL_11:
    v21 = a8;
    if ( a8 )
    {
      std::make_unique<ICDPActivity * [0],0>(&v24, a8);
      LOWORD(a7) = 0;
      v28[0] = &a7;
      v28[1] = &v24;
      v25[0] = v28;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, std::_Ref_count_base *, __int64, __int64, bool, __int64, unsigned __int16, _QWORD **))(**(_QWORD **)(a1 + 16) + 56LL))(
              *(_QWORD *)(a1 + 16),
              v29,
              v27[0],
              a4,
              a5,
              a6 == 1,
              v24,
              v21,
              &a7);
      if ( v13 >= 0 && (_WORD)a7 )
      {
        v22 = CoTaskMemAlloc(232LL * (unsigned __int16)a7);
        if ( v22 )
        {
          for ( i = 0; i < (unsigned __int16)a7; ++i )
          {
            v13 = CDPActivityToComActivityData(*(__int64 **)(v24 + 8LL * i), (__int64)v22 + 232 * i);
            if ( v13 < 0 )
              break;
          }
          *v12 = v22;
          *v15 = i;
        }
        else
        {
          v13 = -2147024882;
        }
      }
      ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22___::_ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22___(v25);
      std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(&v24);
    }
  }
  if ( v27[1] )
    std::_Ref_count_base::_Decref(v27[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v26);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800224c0  mov     [rsp-8+arg_8], edx
0x1800224c4  push    rbp
0x1800224c5  push    rbx
0x1800224c6  push    rsi
0x1800224c7  push    rdi
0x1800224c8  push    r12
0x1800224ca  push    r13
0x1800224cc  push    r14
0x1800224ce  push    r15
0x1800224d0  lea     rbp, [rsp-7]
0x1800224d5  sub     rsp, 98h
0x1800224dc  mov     r12, r9
0x1800224df  mov     rsi, r8
0x1800224e2  mov     r13, rcx
0x1800224e5  mov     r15, [rbp+3Fh+arg_30]
0x1800224e9  xor     edi, edi
0x1800224eb  test    r15, r15
0x1800224ee  jnz     short loc_180022518
0x1800224f0  mov     dword ptr [rbp+3Fh+var_80], 20Dh
0x1800224f7  mov     dword ptr [rbp+3Fh+arg_30], 80004003h
0x1800224fe  lea     rax, [rbp+3Fh+var_80]
0x180022502  mov     [rsp+0D0h+var_B0], rax
0x180022507  lea     r8, [rbp+3Fh+arg_30]
0x18002250b  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180022510  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x180022513  jmp     loc_1800226C6
0x180022518  mov     r14, [rbp+3Fh+arg_40]
0x18002251f  test    r14, r14
0x180022522  jnz     short loc_18002252D
0x180022524  mov     dword ptr [rbp+3Fh+var_80], 20Eh
0x18002252b  jmp     short loc_1800224F7
0x18002252d  lea     rbx, [rcx+20h]
0x180022531  mov     rcx, rbx; SRWLock
0x180022534  call    cs:__imp_AcquireSRWLockShared
0x18002253a  mov     [rbp+3Fh+var_68], rbx
0x18002253e  mov     [r14], di
0x180022542  mov     [r15], rdi
0x180022545  xorps   xmm0, xmm0
0x180022548  movdqu  xmmword ptr [rbp+3Fh+var_60], xmm0
0x18002254d  xor     eax, eax
0x18002254f  test    rsi, rsi
0x180022552  jz      short loc_1800225AA
0x180022554  mov     [rbp+3Fh+var_78], rax
0x180022558  lea     rax, [rbp+3Fh+var_60]
0x18002255c  mov     [rbp+3Fh+var_70], rax
0x180022560  lea     rdx, [rbp+3Fh+var_78]
0x180022564  mov     rcx, rsi
0x180022567  call    CDPCrossPlatformAppIdFromComCrossPlatformAppId
0x18002256c  mov     ebx, eax
0x18002256e  lea     rcx, [rbp+3Fh+var_78]
0x180022572  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x180022577  xor     eax, eax
0x180022579  cmp     ebx, 80070057h
0x18002257f  cmovnz  edi, ebx
0x180022582  test    edi, edi
0x180022584  jns     short loc_1800225AA
0x180022586  mov     dword ptr [rbp+3Fh+arg_30], edi
0x180022589  mov     dword ptr [rbp+3Fh+var_80], 21Eh
0x180022590  lea     rax, [rbp+3Fh+var_80]
0x180022594  mov     [rsp+0D0h+var_B0], rax
0x180022599  lea     r8, [rbp+3Fh+arg_30]
0x18002259d  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x1800225a2  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x1800225a5  jmp     loc_1800226AD
0x1800225aa  cmp     [rbp+3Fh+arg_28], 1
0x1800225ae  setz    sil
0x1800225b2  movzx   ebx, [rbp+3Fh+arg_38]
0x1800225b9  test    bx, bx
0x1800225bc  jz      loc_1800226AD
0x1800225c2  mov     edx, ebx
0x1800225c4  lea     rcx, [rbp+3Fh+var_80]
0x1800225c8  call    ??$make_unique@$$BY0A@PEAVICDPActivity@@$0A@@std@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@0@_K@Z; std::make_unique<ICDPActivity * [0],0>(unsigned __int64)
0x1800225cd  xor     eax, eax
0x1800225cf  mov     word ptr [rbp+3Fh+arg_30], ax
0x1800225d3  lea     rax, [rbp+3Fh+arg_30]
0x1800225d7  mov     [rbp+3Fh+var_50], rax
0x1800225db  lea     rax, [rbp+3Fh+var_80]
0x1800225df  mov     [rbp+3Fh+var_48], rax
0x1800225e3  lea     rax, [rbp+3Fh+var_50]
0x1800225e7  mov     [rbp+3Fh+var_78], rax
0x1800225eb  mov     rcx, [r13+10h]
0x1800225ef  mov     rdx, [rbp+3Fh+var_80]
0x1800225f3  mov     rax, [rcx]
0x1800225f6  mov     r10, [rax+38h]
0x1800225fa  lea     rax, [rbp+3Fh+arg_30]
0x1800225fe  mov     [rsp+0D0h+var_90], rax
0x180022603  mov     [rsp+0D0h+var_98], bx
0x180022608  mov     [rsp+0D0h+var_A0], rdx
0x18002260d  mov     [rsp+0D0h+var_A8], sil
0x180022612  mov     rax, [rbp+3Fh+arg_20]
0x180022616  mov     [rsp+0D0h+var_B0], rax
0x18002261b  mov     r9, r12
0x18002261e  mov     r8, [rbp+3Fh+var_60]
0x180022622  mov     edx, [rbp+3Fh+arg_8]
0x180022625  mov     rax, r10
0x180022628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002262d  mov     edi, eax
0x18002262f  xor     r12d, r12d
0x180022632  test    eax, eax
0x180022634  js      short loc_18002269B
0x180022636  movzx   eax, word ptr [rbp+3Fh+arg_30]
0x18002263a  test    ax, ax
0x18002263d  jz      short loc_18002269B
0x18002263f  imul    rcx, rax, 0E8h; cb
0x180022646  call    cs:__imp_CoTaskMemAlloc
0x18002264c  mov     rbx, rax
0x18002264f  test    rax, rax
0x180022652  jz      short loc_180022696
0x180022654  mov     esi, r12d
0x180022657  cmp     r12w, word ptr [rbp+3Fh+arg_30]
0x18002265c  jnb     short loc_18002268D
0x18002265e  lea     r13d, [r12+1]
0x180022663  movzx   eax, si
0x180022666  imul    rdx, rax, 0E8h
0x18002266d  add     rdx, rbx
0x180022670  mov     rcx, [rbp+3Fh+var_80]
0x180022674  mov     rcx, [rcx+rax*8]
0x180022678  call    CDPActivityToComActivityData
0x18002267d  mov     edi, eax
0x18002267f  test    eax, eax
0x180022681  js      short loc_18002268D
0x180022683  add     si, r13w
0x180022687  cmp     si, word ptr [rbp+3Fh+arg_30]
0x18002268b  jb      short loc_180022663
0x18002268d  mov     [r15], rbx
0x180022690  mov     [r14], si
0x180022694  jmp     short loc_18002269B
0x180022696  mov     edi, 8007000Eh
0x18002269b  lea     rcx, [rbp+3Fh+var_78]
0x18002269f  call    ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22______ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22___
0x1800226a4  lea     rcx, [rbp+3Fh+var_80]
0x1800226a8  call    ??1?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@std@@QEAA@XZ; std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(void)
0x1800226ad  mov     rcx, [rbp+3Fh+var_60+8]; this
0x1800226b1  test    rcx, rcx
0x1800226b4  jz      short loc_1800226BB
0x1800226b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800226bb  lea     rcx, [rbp+3Fh+var_68]
0x1800226bf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800226c4  mov     eax, edi
0x1800226c6  add     rsp, 98h
0x1800226cd  pop     r15
0x1800226cf  pop     r14
0x1800226d1  pop     r13
0x1800226d3  pop     r12
0x1800226d5  pop     rdi
0x1800226d6  pop     rsi
0x1800226d7  pop     rbx
0x1800226d8  pop     rbp
0x1800226d9  retn
```

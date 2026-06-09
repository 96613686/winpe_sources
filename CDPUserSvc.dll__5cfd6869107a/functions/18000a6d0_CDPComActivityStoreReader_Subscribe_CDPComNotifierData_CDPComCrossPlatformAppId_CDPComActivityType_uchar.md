# CDPComActivityStoreReader::Subscribe(CDPComNotifierData *,CDPComCrossPlatformAppId *,CDPComActivityType *,uchar)

- ea: `0x18000a6d0`
- end: `0x18000a93c`
- name: `?Subscribe@CDPComActivityStoreReader@@UEAAJPEAUCDPComNotifierData@@PEAUCDPComCrossPlatformAppId@@PEAW4CDPComActivityType@@E@Z`
- size: `620`
- prototype: `__int64 __fastcall(CDPComActivityStoreReader *__hidden this, struct CDPComNotifierData *, struct CDPComCrossPlatformAppId *, enum CDPComActivityType *, char)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800097d0`
- `0x18000a6d0`
- `0x18000b270`
- `0x18000b504`
- `0x180014aa0`
- `0x18001e798`
- `0x1800250a4`
- `0x180025a8c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a888`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a888`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a908`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a908`
- `cdp!CDPCreateCrossPlatformAppId` at `0x18000a7a4`
- `cdp!CDPCreateCrossPlatformAppId` at `0x18000a7a4`

## string_xrefs

- `0x18000a7c1`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
__int64 __fastcall CDPComActivityStoreReader::Subscribe(
        RTL_SRWLOCK *this,
        struct CDPComNotifierData *a2,
        struct CDPComCrossPlatformAppId *a3,
        std::_Ref_count_base **a4,
        char a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r9
  int v12; // ebx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _QWORD *v15; // rdi
  _QWORD *v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 *Ptr; // rcx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r9
  int v28; // [rsp+20h] [rbp-51h]
  int v29; // [rsp+30h] [rbp-41h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-3Dh] BYREF
  std::_Ref_count_base *v31[2]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v32; // [rsp+48h] [rbp-29h] BYREF
  std::_Ref_count_base *v33; // [rsp+50h] [rbp-21h]
  std::_Ref_count_base *v34[2]; // [rsp+58h] [rbp-19h] BYREF
  std::_Ref_count_base *v35; // [rsp+68h] [rbp-9h] BYREF
  std::_Ref_count_base **v36; // [rsp+70h] [rbp-1h]
  char v37; // [rsp+78h] [rbp+7h]
  _QWORD v38[8]; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]
  struct CDPComNotifierData *v40; // [rsp+D8h] [rbp+67h] BYREF

  v40 = a2;
  if ( !a2 )
  {
    LODWORD(v40) = -2147024809;
    v29 = 155;
    Log<long &,char const (&)[33],int>((__int64)this, 0, &v40, (__int64)a4, &v29);
    return (unsigned int)v40;
  }
  cdp::MakeSharedNoThrow<ActivityStoreReaderCallback,CDPComNotifierData * &>(&v32, (__int64 *)&v40);
  if ( !v32 )
  {
    LODWORD(v40) = -2147024882;
    v29 = 158;
    Log<long &,char const (&)[33],int>(v10, v9, &v40, v11, &v29);
LABEL_6:
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    return (unsigned int)v40;
  }
  v30 = 0;
  *(_OWORD *)v34 = 0;
  if ( a3 )
  {
    v36 = v34;
    v35 = 0;
    *(_OWORD *)v31 = 0;
    v38[0] = 0;
    v38[1] = v31;
    v12 = CDPCreateCrossPlatformAppId(v38);
    cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(v38);
    if ( v12 >= 0 )
    {
      v15 = (_QWORD *)*((_QWORD *)a3 + 1);
      v16 = &v15[2 * *(unsigned int *)a3];
      while ( 1 )
      {
        v17 = *(_QWORD *)v31[0];
        if ( v15 == v16 )
          break;
        v18 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD))(v17 + 64))(v31[0], *v15, v15[1]);
        v12 = v18;
        if ( v18 < 0 )
        {
          v13 = (unsigned int)v18;
          v14 = 74;
          goto LABEL_11;
        }
        v15 += 2;
      }
      (*(void (**)(void))(v17 + 8))();
      v35 = v31[0];
      if ( v31[1] )
        std::_Ref_count_base::_Decref(v31[1]);
      v12 = 0;
    }
    else
    {
      v13 = (unsigned int)v12;
      v14 = 71;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)v13,
        v28);
      if ( v31[1] )
        std::_Ref_count_base::_Decref(v31[1]);
    }
    cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(&v35);
    if ( v12 < 0 )
    {
      LODWORD(v40) = v12;
      v29 = 165;
      Log<long &,char const (&)[33],int>(v20, v19, &v40, v21, &v29);
      goto LABEL_23;
    }
  }
  AcquireSRWLockExclusive(this + 9);
  v31[0] = (std::_Ref_count_base *)&this[9];
  Ptr = (__int64 *)this[7].Ptr;
  v23 = *Ptr;
  v35 = v34[0];
  v36 = a4;
  v37 = a5;
  v24 = (*(__int64 (__fastcall **)(__int64 *, __int64, std::_Ref_count_base **, unsigned int *))(v23 + 56))(
          Ptr,
          v32,
          &v35,
          &v30);
  if ( v24 < 0 )
  {
    LODWORD(v40) = v24;
    v29 = 171;
    Log<long &,char const (&)[33],int>(v26, v25, &v40, v27, &v29);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v31);
LABEL_23:
    if ( v34[1] )
      std::_Ref_count_base::_Decref(v34[1]);
    goto LABEL_6;
  }
  CDPComActivityStoreReader::SwapSubscriptionToken(this, &v32, v30);
  if ( this != (RTL_SRWLOCK *)-72LL )
    ReleaseSRWLockExclusive(this + 9);
  if ( v34[1] )
    std::_Ref_count_base::_Decref(v34[1]);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  return 0;
}

```

## disassembly

```asm
0x18000a6d0  mov     [rsp-8+arg_8], rdx
0x18000a6d5  push    rbp
0x18000a6d6  push    rbx
0x18000a6d7  push    rsi
0x18000a6d8  push    rdi
0x18000a6d9  push    r12
0x18000a6db  push    r14
0x18000a6dd  lea     rbp, [rsp-27h]
0x18000a6e2  sub     rsp, 98h
0x18000a6e9  mov     r12, r9
0x18000a6ec  mov     rsi, r8
0x18000a6ef  mov     r14, rcx
0x18000a6f2  test    rdx, rdx
0x18000a6f5  jnz     short loc_18000A71F
0x18000a6f7  mov     dword ptr [rbp+4Fh+arg_8], 80070057h
0x18000a6fe  mov     [rbp+4Fh+var_90], 9Bh
0x18000a705  lea     rax, [rbp+4Fh+var_90]
0x18000a709  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000a70e  lea     r8, [rbp+4Fh+arg_8]
0x18000a712  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18000a717  mov     eax, dword ptr [rbp+4Fh+arg_8]
0x18000a71a  jmp     loc_18000A92C
0x18000a71f  lea     rdx, [rbp+4Fh+arg_8]
0x18000a723  lea     rcx, [rbp+4Fh+var_78]
0x18000a727  call    ??$MakeSharedNoThrow@VActivityStoreReaderCallback@@AEAPEAUCDPComNotifierData@@@cdp@@YA?AV?$shared_ptr@VActivityStoreReaderCallback@@@std@@AEAPEAUCDPComNotifierData@@@Z; cdp::MakeSharedNoThrow<ActivityStoreReaderCallback,CDPComNotifierData * &>(CDPComNotifierData * &)
0x18000a72c  cmp     [rbp+4Fh+var_78], 0
0x18000a731  jnz     short loc_18000A763
0x18000a733  mov     dword ptr [rbp+4Fh+arg_8], 8007000Eh
0x18000a73a  mov     [rbp+4Fh+var_90], 9Eh
0x18000a741  lea     rax, [rbp+4Fh+var_90]
0x18000a745  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000a74a  lea     r8, [rbp+4Fh+arg_8]
0x18000a74e  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18000a753  mov     rcx, [rbp+4Fh+var_70]; this
0x18000a757  test    rcx, rcx
0x18000a75a  jz      short loc_18000A717
0x18000a75c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a761  jmp     short loc_18000A717
0x18000a763  mov     [rbp+4Fh+var_8C], 0
0x18000a76a  xorps   xmm0, xmm0
0x18000a76d  movdqu  xmmword ptr [rbp+4Fh+var_68], xmm0
0x18000a772  test    rsi, rsi
0x18000a775  jz      loc_18000A881
0x18000a77b  lea     rax, [rbp+4Fh+var_68]
0x18000a77f  mov     [rbp+4Fh+var_50], rax
0x18000a783  mov     [rbp+4Fh+var_58], 0
0x18000a78b  movdqu  xmmword ptr [rbp+4Fh+var_88], xmm0
0x18000a790  mov     [rbp+4Fh+var_40], 0
0x18000a798  lea     rax, [rbp+4Fh+var_88]
0x18000a79c  mov     [rbp+4Fh+var_38], rax
0x18000a7a0  lea     rcx, [rbp+4Fh+var_40]
0x18000a7a4  call    cs:__imp_CDPCreateCrossPlatformAppId
0x18000a7aa  mov     ebx, eax
0x18000a7ac  lea     rcx, [rbp+4Fh+var_40]
0x18000a7b0  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x18000a7b5  test    ebx, ebx
0x18000a7b7  jns     short loc_18000A7E1
0x18000a7b9  mov     r9d, ebx; char *
0x18000a7bc  mov     edx, 47h ; 'G'; void *
0x18000a7c1  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000a7c8  mov     rcx, [rbp+57h]; this
0x18000a7cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7d1  mov     rcx, [rbp+4Fh+var_88+8]; this
0x18000a7d5  test    rcx, rcx
0x18000a7d8  jz      short loc_18000A841
0x18000a7da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a7df  jmp     short loc_18000A841
0x18000a7e1  mov     rdi, [rsi+8]
0x18000a7e5  mov     esi, [rsi]
0x18000a7e7  shl     rsi, 4
0x18000a7eb  add     rsi, rdi
0x18000a7ee  mov     rcx, [rbp+4Fh+var_88]
0x18000a7f2  mov     rax, [rcx]
0x18000a7f5  cmp     rdi, rsi
0x18000a7f8  jz      short loc_18000A820
0x18000a7fa  mov     r8, [rdi+8]
0x18000a7fe  mov     rdx, [rdi]
0x18000a801  mov     rax, [rax+40h]
0x18000a805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a80a  mov     ebx, eax
0x18000a80c  test    eax, eax
0x18000a80e  js      short loc_18000A816
0x18000a810  add     rdi, 10h
0x18000a814  jmp     short loc_18000A7EE
0x18000a816  mov     r9d, eax
0x18000a819  mov     edx, 4Ah ; 'J'
0x18000a81e  jmp     short loc_18000A7C1
0x18000a820  mov     rax, [rax+8]
0x18000a824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a829  mov     rax, [rbp+4Fh+var_88]
0x18000a82d  mov     [rbp+4Fh+var_58], rax
0x18000a831  mov     rcx, [rbp+4Fh+var_88+8]; this
0x18000a835  test    rcx, rcx
0x18000a838  jz      short loc_18000A83F
0x18000a83a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a83f  xor     ebx, ebx
0x18000a841  lea     rcx, [rbp+4Fh+var_58]
0x18000a845  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x18000a84a  test    ebx, ebx
0x18000a84c  jns     short loc_18000A881
0x18000a84e  mov     dword ptr [rbp+4Fh+arg_8], ebx
0x18000a851  mov     [rbp+4Fh+var_90], 0A5h
0x18000a858  lea     rax, [rbp+4Fh+var_90]
0x18000a85c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000a861  lea     r8, [rbp+4Fh+arg_8]
0x18000a865  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18000a86a  mov     rcx, [rbp+4Fh+var_68+8]; this
0x18000a86e  test    rcx, rcx
0x18000a871  jz      loc_18000A753
0x18000a877  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a87c  jmp     loc_18000A753
0x18000a881  lea     rbx, [r14+48h]
0x18000a885  mov     rcx, rbx; SRWLock
0x18000a888  call    cs:__imp_AcquireSRWLockExclusive
0x18000a88e  mov     [rbp+4Fh+var_88], rbx
0x18000a892  mov     rcx, [r14+38h]
0x18000a896  mov     rax, [rcx]
0x18000a899  mov     r8, [rbp+4Fh+var_68]
0x18000a89d  mov     [rbp+4Fh+var_58], r8
0x18000a8a1  mov     [rbp+4Fh+var_50], r12
0x18000a8a5  mov     r8b, [rbp+4Fh+arg_20]
0x18000a8a9  mov     [rbp+4Fh+var_48], r8b
0x18000a8ad  lea     r9, [rbp+4Fh+var_8C]
0x18000a8b1  lea     r8, [rbp+4Fh+var_58]
0x18000a8b5  mov     rdx, [rbp+4Fh+var_78]
0x18000a8b9  mov     rax, [rax+38h]
0x18000a8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c2  test    eax, eax
0x18000a8c4  jns     short loc_18000A8F0
0x18000a8c6  mov     dword ptr [rbp+4Fh+arg_8], eax
0x18000a8c9  mov     [rbp+4Fh+var_90], 0ABh
0x18000a8d0  lea     rax, [rbp+4Fh+var_90]
0x18000a8d4  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000a8d9  lea     r8, [rbp+4Fh+arg_8]
0x18000a8dd  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18000a8e2  lea     rcx, [rbp+4Fh+var_88]
0x18000a8e6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18000a8eb  jmp     loc_18000A86A
0x18000a8f0  mov     r8d, [rbp+4Fh+var_8C]
0x18000a8f4  lea     rdx, [rbp+4Fh+var_78]
0x18000a8f8  mov     rcx, r14
0x18000a8fb  call    ?SwapSubscriptionToken@CDPComActivityStoreReader@@AEAAXAEBV?$shared_ptr@VActivityStoreReaderCallback@@@std@@I@Z; CDPComActivityStoreReader::SwapSubscriptionToken(std::shared_ptr<ActivityStoreReaderCallback> const &,uint)
0x18000a900  test    rbx, rbx
0x18000a903  jz      short loc_18000A90E
0x18000a905  mov     rcx, rbx; SRWLock
0x18000a908  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a90e  mov     rcx, [rbp+4Fh+var_68+8]; this
0x18000a912  test    rcx, rcx
0x18000a915  jz      short loc_18000A91C
0x18000a917  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a91c  mov     rcx, [rbp+4Fh+var_70]; this
0x18000a920  test    rcx, rcx
0x18000a923  jz      short loc_18000A92A
0x18000a925  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a92a  xor     eax, eax
0x18000a92c  add     rsp, 98h
0x18000a933  pop     r14
0x18000a935  pop     r12
0x18000a937  pop     rdi
0x18000a938  pop     rsi
0x18000a939  pop     rbx
0x18000a93a  pop     rbp
0x18000a93b  retn
```

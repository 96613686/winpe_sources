# BioIsoSrvPresenceMonitorEnumAll

- ea: `0x14000a8d0`
- end: `0x14000accd`
- name: `BioIsoSrvPresenceMonitorEnumAll`
- size: `1021`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000a8d0`
- `0x14000acd4`
- `0x14000ad00`
- `0x14000d5d0`
- `0x14001bd40`
- `0x140041648`
- `0x140059830`
- `0x14005cf30`
- `0x140085010`

## string_xrefs

- `0x14000a940`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000a98c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000a9f8`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000aa82`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000ac81`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BioIsoSrvPresenceMonitorEnumAll(int *a1, _QWORD *a2, _DWORD *a3)
{
  int BiometricUnit; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  char *v11; // r9
  __int64 v12; // r11
  _OWORD *v13; // r8
  _OWORD *v14; // rcx
  _OWORD *v15; // rax
  _OWORD *v16; // rdx
  __int64 v17; // r10
  char *v18; // rdx
  _OWORD *v19; // rax
  __int64 v20; // r10
  unsigned __int64 v21; // rcx
  int v22; // [rsp+20h] [rbp-398h]
  _OWORD *v23; // [rsp+28h] [rbp-390h] BYREF
  _OWORD *v24; // [rsp+30h] [rbp-388h]
  std::_Ref_count_base *v25[2]; // [rsp+40h] [rbp-378h] BYREF
  _BYTE v26[496]; // [rsp+50h] [rbp-368h] BYREF
  _QWORD v27[42]; // [rsp+240h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  BioIsoProvider::PresenceMonitorEnumAll::Start<>((BioIsoProvider::PresenceMonitorEnumAll *)v27);
  if ( !a1 || !a2 || !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA23,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v22);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v27);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA24,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v22);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v27);
    return 2147942487LL;
  }
  *(_OWORD *)v25 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v25);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v22);
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v27);
    return v8;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v23);
  v9 = (*(__int64 (__fastcall **)(_QWORD, _OWORD **))(**((_QWORD **)v25[0] + 5) + 32LL))(*((_QWORD *)v25[0] + 5), &v23);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v9,
      v22);
    std::vector<_WINBIO_PRESENCE>::_Tidy(&v23);
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v27);
    return v10;
  }
  if ( 0xEF7BDEF7BDEF7BDFuLL * (v24 - v23) )
  {
    v11 = (char *)MIDL_user_allocate(16 * (v24 - v23));
    if ( !v11 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA34,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x8007000ELL,
        v22);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v23);
      if ( v25[1] )
        std::_Ref_count_base::_Decref(v25[1]);
      BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v27);
      return 2147942414LL;
    }
    v12 = 0;
    v13 = v23;
    v14 = v24;
    if ( v23 != v24 )
    {
      do
      {
        v15 = v13;
        v16 = v26;
        v17 = 3;
        do
        {
          *v16 = *v15;
          v16[1] = v15[1];
          v16[2] = v15[2];
          v16[3] = v15[3];
          v16[4] = v15[4];
          v16[5] = v15[5];
          v16[6] = v15[6];
          v16[7] = v15[7];
          v16 += 8;
          v15 += 8;
          --v17;
        }
        while ( v17 );
        *v16 = *v15;
        v16[1] = v15[1];
        v16[2] = v15[2];
        v16[3] = v15[3];
        v16[4] = v15[4];
        v16[5] = v15[5];
        v16[6] = v15[6];
        v18 = &v11[496 * v12];
        v19 = v26;
        v20 = 3;
        do
        {
          *(_OWORD *)v18 = *v19;
          *((_OWORD *)v18 + 1) = v19[1];
          *((_OWORD *)v18 + 2) = v19[2];
          *((_OWORD *)v18 + 3) = v19[3];
          *((_OWORD *)v18 + 4) = v19[4];
          *((_OWORD *)v18 + 5) = v19[5];
          *((_OWORD *)v18 + 6) = v19[6];
          *((_OWORD *)v18 + 7) = v19[7];
          v18 += 128;
          v19 += 8;
          --v20;
        }
        while ( v20 );
        *(_OWORD *)v18 = *v19;
        *((_OWORD *)v18 + 1) = v19[1];
        *((_OWORD *)v18 + 2) = v19[2];
        *((_OWORD *)v18 + 3) = v19[3];
        *((_OWORD *)v18 + 4) = v19[4];
        *((_OWORD *)v18 + 5) = v19[5];
        *((_OWORD *)v18 + 6) = v19[6];
        ++v12;
        v13 += 31;
      }
      while ( v13 != v14 );
      v14 = v24;
      v13 = v23;
    }
    v21 = 0xEF7BDEF7BDEF7BDFuLL * (v14 - v13);
  }
  else
  {
    LODWORD(v21) = 0;
    v11 = 0;
  }
  *a2 = v11;
  *a3 = v21;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v27, 0);
  std::vector<_WINBIO_PRESENCE>::_Tidy(&v23);
  if ( v25[1] )
    std::_Ref_count_base::_Decref(v25[1]);
  BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v27);
  return 0;
}

```

## disassembly

```asm
0x14000a8d0  mov     [rsp+arg_18], rbx
0x14000a8d5  push    rsi
0x14000a8d6  push    rdi
0x14000a8d7  push    r14
0x14000a8d9  sub     rsp, 3A0h
0x14000a8e0  mov     rax, cs:__security_cookie
0x14000a8e7  xor     rax, rsp
0x14000a8ea  mov     [rsp+3B8h+var_28], rax
0x14000a8f2  mov     rdi, r8
0x14000a8f5  mov     rsi, rdx
0x14000a8f8  mov     rbx, rcx
0x14000a8fb  lea     rcx, [rsp+3B8h+var_178]; this
0x14000a903  call    ??$Start@$$V@PresenceMonitorEnumAll@BioIsoProvider@@SA?AV01@XZ; BioIsoProvider::PresenceMonitorEnumAll::Start<>(void)
0x14000a908  nop
0x14000a909  test    rbx, rbx
0x14000a90c  jz      loc_14000AC71
0x14000a912  test    rsi, rsi
0x14000a915  jz      loc_14000AC71
0x14000a91b  test    rdi, rdi
0x14000a91e  jz      loc_14000AC71
0x14000a924  mov     rcx, rbx; void *
0x14000a927  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14000a92c  test    al, al
0x14000a92e  jnz     short loc_14000A966
0x14000a930  mov     rcx, [rsp+3B8h]; this
0x14000a938  mov     ebx, 80070057h
0x14000a93d  mov     r9d, ebx; char *
0x14000a940  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000a947  mov     edx, 0A24h; void *
0x14000a94c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a951  nop
0x14000a952  lea     rcx, [rsp+3B8h+var_178]; this
0x14000a95a  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x14000a95f  mov     eax, ebx
0x14000a961  jmp     loc_14000ACA8
0x14000a966  xorps   xmm0, xmm0
0x14000a969  movdqu  xmmword ptr [rsp+3B8h+var_378], xmm0
0x14000a96f  lea     rdx, [rsp+3B8h+var_378]
0x14000a974  mov     ecx, [rbx]
0x14000a976  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14000a97b  mov     ebx, eax
0x14000a97d  test    eax, eax
0x14000a97f  jns     short loc_14000A9C2
0x14000a981  mov     rcx, [rsp+3B8h]; this
0x14000a989  mov     r9d, eax; char *
0x14000a98c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000a993  mov     edx, 0A2Ah; void *
0x14000a998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a99d  nop
0x14000a99e  mov     rcx, [rsp+3B8h+var_378+8]; this
0x14000a9a3  test    rcx, rcx
0x14000a9a6  jz      short loc_14000A9AE
0x14000a9a8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000a9ad  nop
0x14000a9ae  lea     rcx, [rsp+3B8h+var_178]; this
0x14000a9b6  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x14000a9bb  mov     eax, ebx
0x14000a9bd  jmp     loc_14000ACA8
0x14000a9c2  lea     rcx, [rsp+3B8h+var_390]
0x14000a9c7  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14000a9cc  nop
0x14000a9cd  mov     rax, [rsp+3B8h+var_378]
0x14000a9d2  mov     rcx, [rax+28h]
0x14000a9d6  mov     rax, [rcx]
0x14000a9d9  lea     rdx, [rsp+3B8h+var_390]
0x14000a9de  mov     rax, [rax+20h]
0x14000a9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9e7  mov     ebx, eax
0x14000a9e9  test    eax, eax
0x14000a9eb  jns     short loc_14000AA39
0x14000a9ed  mov     rcx, [rsp+3B8h]; this
0x14000a9f5  mov     r9d, eax; char *
0x14000a9f8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000a9ff  mov     edx, 0A2Fh; void *
0x14000aa04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000aa09  nop
0x14000aa0a  lea     rcx, [rsp+3B8h+var_390]
0x14000aa0f  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x14000aa14  nop
0x14000aa15  mov     rcx, [rsp+3B8h+var_378+8]; this
0x14000aa1a  test    rcx, rcx
0x14000aa1d  jz      short loc_14000AA25
0x14000aa1f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000aa24  nop
0x14000aa25  lea     rcx, [rsp+3B8h+var_178]; this
0x14000aa2d  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x14000aa32  mov     eax, ebx
0x14000aa34  jmp     loc_14000ACA8
0x14000aa39  mov     rax, [rsp+3B8h+var_388]
0x14000aa3e  sub     rax, [rsp+3B8h+var_390]
0x14000aa43  sar     rax, 4
0x14000aa47  mov     r14, 0EF7BDEF7BDEF7BDFh
0x14000aa51  imul    rax, r14
0x14000aa55  test    rax, rax
0x14000aa58  jz      loc_14000AC2B
0x14000aa5e  imul    rcx, rax, 1F0h; size
0x14000aa65  call    MIDL_user_allocate
0x14000aa6a  mov     r9, rax
0x14000aa6d  test    rax, rax
0x14000aa70  jnz     short loc_14000AAC3
0x14000aa72  mov     rcx, [rsp+3B8h]; this
0x14000aa7a  mov     ebx, 8007000Eh
0x14000aa7f  mov     r9d, ebx; char *
0x14000aa82  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000aa89  mov     edx, 0A34h; void *
0x14000aa8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000aa93  nop
0x14000aa94  lea     rcx, [rsp+3B8h+var_390]
0x14000aa99  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x14000aa9e  nop
0x14000aa9f  mov     rcx, [rsp+3B8h+var_378+8]; this
0x14000aaa4  test    rcx, rcx
0x14000aaa7  jz      short loc_14000AAAF
0x14000aaa9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000aaae  nop
0x14000aaaf  lea     rcx, [rsp+3B8h+var_178]; this
0x14000aab7  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x14000aabc  mov     eax, ebx
0x14000aabe  jmp     loc_14000ACA8
0x14000aac3  xor     r11d, r11d
0x14000aac6  mov     r8, [rsp+3B8h+var_390]
0x14000aacb  mov     rcx, [rsp+3B8h+var_388]
0x14000aad0  cmp     r8, rcx
0x14000aad3  jz      loc_14000AC1E
0x14000aad9  mov     ebx, 80h
0x14000aade  mov     rax, r8
0x14000aae1  lea     rdx, [rsp+3B8h+var_368]
0x14000aae6  mov     r10d, 3
0x14000aaec  movups  xmm0, xmmword ptr [rax]
0x14000aaef  movups  xmmword ptr [rdx], xmm0
0x14000aaf2  movups  xmm1, xmmword ptr [rax+10h]
0x14000aaf6  movups  xmmword ptr [rdx+10h], xmm1
0x14000aafa  movups  xmm0, xmmword ptr [rax+20h]
0x14000aafe  movups  xmmword ptr [rdx+20h], xmm0
0x14000ab02  movups  xmm1, xmmword ptr [rax+30h]
0x14000ab06  movups  xmmword ptr [rdx+30h], xmm1
0x14000ab0a  movups  xmm0, xmmword ptr [rax+40h]
0x14000ab0e  movups  xmmword ptr [rdx+40h], xmm0
0x14000ab12  movups  xmm1, xmmword ptr [rax+50h]
0x14000ab16  movups  xmmword ptr [rdx+50h], xmm1
0x14000ab1a  movups  xmm0, xmmword ptr [rax+60h]
0x14000ab1e  movups  xmmword ptr [rdx+60h], xmm0
0x14000ab22  movups  xmm1, xmmword ptr [rax+70h]
0x14000ab26  movups  xmmword ptr [rdx+70h], xmm1
0x14000ab2a  add     rdx, rbx
0x14000ab2d  add     rax, rbx
0x14000ab30  sub     r10, 1
0x14000ab34  jnz     short loc_14000AAEC
0x14000ab36  movups  xmm0, xmmword ptr [rax]
0x14000ab39  movups  xmmword ptr [rdx], xmm0
0x14000ab3c  movups  xmm1, xmmword ptr [rax+10h]
0x14000ab40  movups  xmmword ptr [rdx+10h], xmm1
0x14000ab44  movups  xmm0, xmmword ptr [rax+20h]
0x14000ab48  movups  xmmword ptr [rdx+20h], xmm0
0x14000ab4c  movups  xmm1, xmmword ptr [rax+30h]
0x14000ab50  movups  xmmword ptr [rdx+30h], xmm1
0x14000ab54  movups  xmm0, xmmword ptr [rax+40h]
0x14000ab58  movups  xmmword ptr [rdx+40h], xmm0
0x14000ab5c  movups  xmm1, xmmword ptr [rax+50h]
0x14000ab60  movups  xmmword ptr [rdx+50h], xmm1
0x14000ab64  movups  xmm0, xmmword ptr [rax+60h]
0x14000ab68  movups  xmmword ptr [rdx+60h], xmm0
0x14000ab6c  imul    rdx, r11, 1F0h
0x14000ab73  add     rdx, r9
0x14000ab76  lea     rax, [rsp+3B8h+var_368]
0x14000ab7b  mov     r10d, 3
0x14000ab81  movups  xmm0, xmmword ptr [rax]
0x14000ab84  movups  xmmword ptr [rdx], xmm0
0x14000ab87  movups  xmm1, xmmword ptr [rax+10h]
0x14000ab8b  movups  xmmword ptr [rdx+10h], xmm1
0x14000ab8f  movups  xmm0, xmmword ptr [rax+20h]
0x14000ab93  movups  xmmword ptr [rdx+20h], xmm0
0x14000ab97  movups  xmm1, xmmword ptr [rax+30h]
0x14000ab9b  movups  xmmword ptr [rdx+30h], xmm1
0x14000ab9f  movups  xmm0, xmmword ptr [rax+40h]
0x14000aba3  movups  xmmword ptr [rdx+40h], xmm0
0x14000aba7  movups  xmm1, xmmword ptr [rax+50h]
0x14000abab  movups  xmmword ptr [rdx+50h], xmm1
0x14000abaf  movups  xmm0, xmmword ptr [rax+60h]
0x14000abb3  movups  xmmword ptr [rdx+60h], xmm0
0x14000abb7  movups  xmm1, xmmword ptr [rax+70h]
0x14000abbb  movups  xmmword ptr [rdx+70h], xmm1
0x14000abbf  add     rdx, rbx
0x14000abc2  add     rax, rbx
0x14000abc5  sub     r10, 1
0x14000abc9  jnz     short loc_14000AB81
0x14000abcb  movups  xmm0, xmmword ptr [rax]
0x14000abce  movups  xmmword ptr [rdx], xmm0
0x14000abd1  movups  xmm1, xmmword ptr [rax+10h]
0x14000abd5  movups  xmmword ptr [rdx+10h], xmm1
0x14000abd9  movups  xmm0, xmmword ptr [rax+20h]
0x14000abdd  movups  xmmword ptr [rdx+20h], xmm0
0x14000abe1  movups  xmm1, xmmword ptr [rax+30h]
0x14000abe5  movups  xmmword ptr [rdx+30h], xmm1
0x14000abe9  movups  xmm0, xmmword ptr [rax+40h]
0x14000abed  movups  xmmword ptr [rdx+40h], xmm0
0x14000abf1  movups  xmm1, xmmword ptr [rax+50h]
0x14000abf5  movups  xmmword ptr [rdx+50h], xmm1
0x14000abf9  movups  xmm0, xmmword ptr [rax+60h]
0x14000abfd  movups  xmmword ptr [rdx+60h], xmm0
0x14000ac01  inc     r11
0x14000ac04  add     r8, 1F0h
0x14000ac0b  cmp     r8, rcx
0x14000ac0e  jnz     loc_14000AADE
0x14000ac14  mov     rcx, [rsp+3B8h+var_388]
0x14000ac19  mov     r8, [rsp+3B8h+var_390]
0x14000ac1e  sub     rcx, r8
0x14000ac21  sar     rcx, 4
0x14000ac25  imul    rcx, r14
0x14000ac29  jmp     short loc_14000AC30
0x14000ac2b  xor     ecx, ecx
0x14000ac2d  xor     r9d, r9d
0x14000ac30  mov     [rsi], r9
0x14000ac33  mov     [rdi], ecx
0x14000ac35  xor     edx, edx
0x14000ac37  lea     rcx, [rsp+3B8h+var_178]
0x14000ac3f  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000ac44  nop
0x14000ac45  lea     rcx, [rsp+3B8h+var_390]
0x14000ac4a  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x14000ac4f  nop
0x14000ac50  mov     rcx, [rsp+3B8h+var_378+8]; this
0x14000ac55  test    rcx, rcx
0x14000ac58  jz      short loc_14000AC60
0x14000ac5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000ac5f  nop
0x14000ac60  lea     rcx, [rsp+3B8h+var_178]; this
0x14000ac68  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x14000ac6d  xor     eax, eax
0x14000ac6f  jmp     short loc_14000ACA8
0x14000ac71  mov     rcx, [rsp+3B8h]; this
0x14000ac79  mov     ebx, 80004003h
0x14000ac7e  mov     r9d, ebx; char *
0x14000ac81  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000ac88  mov     edx, 0A23h; void *
0x14000ac8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ac92  nop
0x14000ac93  lea     rcx, [rsp+3B8h+var_178]; this
0x14000ac9b  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x14000aca0  mov     eax, ebx
0x14000aca2  jmp     short loc_14000ACA8
0x14000aca4  mov     eax, [rsp+3B8h+var_398]
0x14000aca8  mov     rcx, [rsp+3B8h+var_28]
0x14000acb0  xor     rcx, rsp; StackCookie
0x14000acb3  call    __security_check_cookie
0x14000acb8  mov     rbx, [rsp+3B8h+arg_18]
0x14000acc0  add     rsp, 3A0h
0x14000acc7  pop     r14
0x14000acc9  pop     rdi
0x14000acca  pop     rsi
0x14000accb  retn
```

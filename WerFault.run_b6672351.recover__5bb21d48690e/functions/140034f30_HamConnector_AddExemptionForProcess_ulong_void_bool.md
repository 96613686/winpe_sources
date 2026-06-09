# HamConnector::AddExemptionForProcess(ulong,void *,bool)

- ea: `0x140034f30`
- end: `0x140035363`
- name: `?AddExemptionForProcess@HamConnector@@QEAAJKPEAX_N@Z`
- size: `1075`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, DWORD dwProcessId, void *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140027d70`

## callees

- `0x140002490`
- `0x1400024b4`
- `0x140002748`
- `0x1400030f8`
- `0x140014f14`
- `0x140014f58`
- `0x140034f30`
- `0x140035774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400350b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140035132`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400350b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140035132`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003511e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400351a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003511e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400351a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035004`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035329`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035329`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140034fec`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140034fec`
- `RMCLIENT!HamStartActivityAsync` at `0x140035250`
- `RMCLIENT!HamStartActivityAsync` at `0x140035250`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x140034f92`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x140034f92`
- `RMCLIENT!HamCreateActivityForProcess` at `0x140035156`
- `RMCLIENT!HamCreateActivityForProcess` at `0x140035156`

## pseudocode

```c
__int64 __fastcall HamConnector::AddExemptionForProcess(PSRWLOCK SRWLock, DWORD dwProcessId, void *a3, char a4)
{
  RTL_SRWLOCK *v8; // r12
  int v9; // edi
  char *v10; // rbx
  unsigned int v11; // edi
  signed int LastError; // eax
  RTL_SRWLOCK *v13; // r14
  PVOID Ptr; // rax
  PSRWLOCK v15; // rsi
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rax
  int ActivityForProcess; // edi
  __int64 v21; // r8
  CUserModeHangReport *v22; // rcx
  __int64 v23; // rdx
  char *v24; // rax
  char *v25; // rcx
  PVOID v26; // r13
  _BYTE *v27; // rdi
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  char *v30; // r9
  void **v31; // rdx
  void *v32; // rax
  RTL_SRWLOCK *v34; // [rsp+38h] [rbp-1E0h] BYREF
  _BYTE v35[400]; // [rsp+40h] [rbp-1D8h] BYREF

  v8 = 0;
  memset_0(v35, 0, 0x188u);
  v9 = HamPopulateActivityPropertiesByClass(L"Windows Error Reporting", 0, 6, v35);
  if ( v9 < 0 )
  {
    v10 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b6936b066fab37677c58fa622b799e39_Traceguids);
    }
    v11 = v9 | 0x10000000;
    goto LABEL_49;
  }
  v10 = (char *)OpenProcess(0x1001u, 0, dwProcessId);
  if ( v10 == (char *)-1LL || v10 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b6936b066fab37677c58fa622b799e39_Traceguids);
    }
    goto LABEL_49;
  }
  v13 = (RTL_SRWLOCK *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v13 )
  {
    Ptr = SRWLock[1].Ptr;
    v13->Ptr = 0;
    v8 = v13;
    v13[5].Ptr = Ptr;
    LODWORD(v13[1].Ptr) = dwProcessId;
    v13[2].Ptr = (PVOID)-1LL;
    v13[3].Ptr = a3;
    LOBYTE(v13[4].Ptr) = a4;
    HIDWORD(v13[4].Ptr) = 4;
    v34 = v13;
    AcquireSRWLockExclusive(SRWLock);
    v15 = SRWLock + 2;
    v16 = (((char *)SRWLock[3].Ptr - (char *)SRWLock[2].Ptr) >> 3) + 1;
    v17 = ((char *)SRWLock[4].Ptr - (char *)SRWLock[2].Ptr) >> 3;
    if ( v16 > v17 )
    {
      v18 = (((char *)SRWLock[3].Ptr - (char *)SRWLock[2].Ptr) >> 3) + 1;
      v19 = 7 * (v17 >> 2) + 8;
      if ( v19 >= v16 )
        v18 = v19;
      if ( v18 > 0xFFFFFFFFFFFFFFFLL )
        v18 = 0xFFFFFFFFFFFFFFFLL;
      if ( v16 > v18
        || !(unsigned __int8)utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(
                               &SRWLock[2],
                               v18,
                               0xFFFFFFFFFFFFFFFLL) )
      {
        v11 = -2147024882;
LABEL_21:
        ReleaseSRWLockExclusive(SRWLock);
        goto LABEL_49;
      }
    }
    AcquireSRWLockExclusive(v13);
    ActivityForProcess = HamCreateActivityForProcess(SRWLock[1].Ptr, v13, v10, v35, &v13[2]);
    if ( ActivityForProcess < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_27;
      }
      v23 = 20;
      goto LABEL_26;
    }
    v24 = (char *)SRWLock[3].Ptr;
    v25 = (char *)SRWLock[4].Ptr;
    v26 = v13[2].Ptr;
    if ( v24 == v25 )
    {
      v27 = v15->Ptr;
      v28 = (v25 - (char *)v15->Ptr) >> 3;
      v29 = 7 * (v28 >> 2) + 8;
      if ( v29 > 0xFFFFFFFFFFFFFFFLL )
        v29 = 0xFFFFFFFFFFFFFFFLL;
      if ( v28 >= v29
        || !(unsigned __int8)utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(
                               &SRWLock[2],
                               v29,
                               v21) )
      {
        goto LABEL_39;
      }
      v30 = (char *)SRWLock[3].Ptr;
      v31 = (void **)&v34;
      if ( (char *)&v34 - v27 < (unsigned __int64)(v30 - (char *)SRWLock[2].Ptr) )
        v31 = (void **)((char *)v15->Ptr + (char *)&v34 - v27);
      v32 = *v31;
      *v31 = 0;
      v8 = v34;
      *(_QWORD *)v30 = v32;
    }
    else
    {
      v8 = 0;
      *(_QWORD *)v24 = v13;
    }
    SRWLock[3].Ptr = (char *)SRWLock[3].Ptr + 8;
LABEL_39:
    ActivityForProcess = HamStartActivityAsync(SRWLock[1].Ptr, v26, 0, 0);
    if ( ActivityForProcess >= 0 )
    {
      v11 = 0;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_b6936b066fab37677c58fa622b799e39_Traceguids);
      }
      goto LABEL_28;
    }
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_27:
      v11 = ActivityForProcess | 0x10000000;
LABEL_28:
      ReleaseSRWLockExclusive(v13);
      goto LABEL_21;
    }
    v23 = 21;
LABEL_26:
    WPP_SF_Dd(*((_QWORD *)v22 + 2), v23, WPP_b6936b066fab37677c58fa622b799e39_Traceguids);
    goto LABEL_27;
  }
  v11 = -2147024882;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b6936b066fab37677c58fa622b799e39_Traceguids, 2147942414LL);
  }
LABEL_49:
  if ( v8 )
    operator delete(v8, (const struct std::nothrow_t *)0x30);
  if ( (unsigned __int64)(v10 + 1) > 1 )
    CloseHandle(v10);
  return v11;
}

```

## disassembly

```asm
0x140034f30  mov     [rsp+arg_10], rbx
0x140034f35  push    rbp
0x140034f36  push    rsi
0x140034f37  push    rdi
0x140034f38  push    r12
0x140034f3a  push    r13
0x140034f3c  push    r14
0x140034f3e  push    r15
0x140034f40  sub     rsp, 1E0h
0x140034f47  mov     rax, cs:__security_cookie
0x140034f4e  xor     rax, rsp
0x140034f51  mov     [rsp+218h+var_48], rax
0x140034f59  mov     rsi, r8
0x140034f5c  mov     [rsp+218h+var_1E8], r9b
0x140034f61  mov     r15d, edx
0x140034f64  mov     rbp, rcx
0x140034f67  xor     edx, edx; Val
0x140034f69  lea     rcx, [rsp+218h+var_1D8]; void *
0x140034f6e  mov     r8d, 188h; Size
0x140034f74  mov     r13b, r9b
0x140034f77  xor     r12d, r12d
0x140034f7a  call    memset_0
0x140034f7f  lea     r9, [rsp+218h+var_1D8]
0x140034f84  xor     edx, edx
0x140034f86  lea     r8d, [r12+6]
0x140034f8b  lea     rcx, aWindowsErrorRe; "Windows Error Reporting"
0x140034f92  call    cs:__imp_HamPopulateActivityPropertiesByClass
0x140034f99  nop     dword ptr [rax+rax+00h]
0x140034f9e  mov     edi, eax
0x140034fa0  test    eax, eax
0x140034fa2  jns     short loc_140034FE2
0x140034fa4  xor     ebx, ebx
0x140034fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x140034fad  lea     rax, WPP_GLOBAL_Control
0x140034fb4  cmp     rcx, rax
0x140034fb7  jz      short loc_140034FD9
0x140034fb9  test    byte ptr [rcx+1Ch], 1
0x140034fbd  jz      short loc_140034FD9
0x140034fbf  mov     rcx, [rcx+10h]
0x140034fc3  lea     edx, [rbx+11h]
0x140034fc6  mov     r9d, r15d
0x140034fc9  mov     dword ptr [rsp+218h+var_1F8], edi
0x140034fcd  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140034fd4  call    WPP_SF_Dd
0x140034fd9  bts     edi, 1Ch
0x140034fdd  jmp     loc_14003530A
0x140034fe2  mov     r8d, r15d; dwProcessId
0x140034fe5  xor     edx, edx; bInheritHandle
0x140034fe7  mov     ecx, 1001h; dwDesiredAccess
0x140034fec  call    cs:__imp_OpenProcess
0x140034ff3  nop     dword ptr [rax+rax+00h]
0x140034ff8  mov     rbx, rax
0x140034ffb  inc     rax
0x140034ffe  cmp     rax, 1
0x140035002  ja      short loc_140035061
0x140035004  call    cs:__imp_GetLastError
0x14003500b  nop     dword ptr [rax+rax+00h]
0x140035010  mov     edi, eax
0x140035012  test    eax, eax
0x140035014  jle     short loc_14003501F
0x140035016  movzx   edi, ax
0x140035019  or      edi, 80070000h
0x14003501f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035026  lea     rax, WPP_GLOBAL_Control
0x14003502d  cmp     rcx, rax
0x140035030  jz      loc_14003530A
0x140035036  test    byte ptr [rcx+1Ch], 1
0x14003503a  jz      loc_14003530A
0x140035040  mov     rcx, [rcx+10h]
0x140035044  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x14003504b  mov     edx, 12h
0x140035050  mov     dword ptr [rsp+218h+var_1F8], edi
0x140035054  mov     r9d, r15d
0x140035057  call    WPP_SF_Dd
0x14003505c  jmp     loc_14003530A
0x140035061  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140035068  mov     ecx, 30h ; '0'; unsigned __int64
0x14003506d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140035072  mov     r14, rax
0x140035075  test    rax, rax
0x140035078  jz      loc_1400352D4
0x14003507e  mov     rax, [rbp+8]
0x140035082  mov     rcx, rbp; SRWLock
0x140035085  mov     [r14], r12
0x140035088  mov     r12, r14
0x14003508b  mov     [r14+28h], rax
0x14003508f  mov     [r14+8], r15d
0x140035093  mov     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x14003509b  mov     [r14+18h], rsi
0x14003509f  mov     [r14+20h], r13b
0x1400350a3  mov     dword ptr [r14+24h], 4
0x1400350ab  mov     [rsp+218h+var_1E0], r14
0x1400350b0  call    cs:__imp_AcquireSRWLockExclusive
0x1400350b7  nop     dword ptr [rax+rax+00h]
0x1400350bc  lea     rsi, [rbp+10h]
0x1400350c0  mov     r8, 0FFFFFFFFFFFFFFFh
0x1400350ca  mov     rcx, [rsi+8]
0x1400350ce  sub     rcx, [rsi]
0x1400350d1  mov     rax, [rsi+10h]
0x1400350d5  sub     rax, [rsi]
0x1400350d8  sar     rcx, 3
0x1400350dc  inc     rcx
0x1400350df  sar     rax, 3
0x1400350e3  cmp     rcx, rax
0x1400350e6  jbe     short loc_14003512F
0x1400350e8  shr     rax, 2
0x1400350ec  mov     rdx, rcx
0x1400350ef  imul    rax, 7
0x1400350f3  add     rax, 8
0x1400350f7  cmp     rax, rcx
0x1400350fa  cmovnb  rdx, rax
0x1400350fe  cmp     rdx, r8
0x140035101  cmova   rdx, r8
0x140035105  cmp     rcx, rdx
0x140035108  ja      short loc_140035116
0x14003510a  mov     rcx, rsi
0x14003510d  call    ?_SetCapacity@?$vector@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(unsigned __int64)
0x140035112  test    al, al
0x140035114  jnz     short loc_14003512F
0x140035116  mov     edi, 8007000Eh
0x14003511b  mov     rcx, rbp; SRWLock
0x14003511e  call    cs:__imp_ReleaseSRWLockExclusive
0x140035125  nop     dword ptr [rax+rax+00h]
0x14003512a  jmp     loc_14003530A
0x14003512f  mov     rcx, r14; SRWLock
0x140035132  call    cs:__imp_AcquireSRWLockExclusive
0x140035139  nop     dword ptr [rax+rax+00h]
0x14003513e  mov     rcx, [rbp+8]
0x140035142  lea     r13, [r14+10h]
0x140035146  lea     r9, [rsp+218h+var_1D8]
0x14003514b  mov     [rsp+218h+var_1F8], r13
0x140035150  mov     r8, rbx
0x140035153  mov     rdx, r14
0x140035156  call    cs:__imp_HamCreateActivityForProcess
0x14003515d  nop     dword ptr [rax+rax+00h]
0x140035162  mov     edi, eax
0x140035164  test    eax, eax
0x140035166  jns     short loc_1400351B5
0x140035168  mov     rcx, cs:WPP_GLOBAL_Control
0x14003516f  lea     rax, WPP_GLOBAL_Control
0x140035176  cmp     rcx, rax
0x140035179  jz      short loc_14003519D
0x14003517b  test    byte ptr [rcx+1Ch], 1
0x14003517f  jz      short loc_14003519D
0x140035181  mov     edx, 14h
0x140035186  mov     rcx, [rcx+10h]
0x14003518a  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140035191  mov     r9d, r15d
0x140035194  mov     dword ptr [rsp+218h+var_1F8], edi
0x140035198  call    WPP_SF_Dd
0x14003519d  bts     edi, 1Ch
0x1400351a1  mov     rcx, r14; SRWLock
0x1400351a4  call    cs:__imp_ReleaseSRWLockExclusive
0x1400351ab  nop     dword ptr [rax+rax+00h]
0x1400351b0  jmp     loc_14003511B
0x1400351b5  mov     rax, [rsi+8]
0x1400351b9  mov     rcx, [rsi+10h]
0x1400351bd  mov     r13, [r13+0]
0x1400351c1  cmp     rax, rcx
0x1400351c4  jz      short loc_1400351CE
0x1400351c6  xor     r12d, r12d
0x1400351c9  mov     [rax], r14
0x1400351cc  jmp     short loc_14003523E
0x1400351ce  mov     rdi, [rsi]
0x1400351d1  sub     rcx, rdi
0x1400351d4  sar     rcx, 3
0x1400351d8  mov     rax, rcx
0x1400351db  shr     rax, 2
0x1400351df  imul    rdx, rax, 7
0x1400351e3  mov     rax, 0FFFFFFFFFFFFFFFh
0x1400351ed  add     rdx, 8
0x1400351f1  cmp     rdx, rax
0x1400351f4  cmova   rdx, rax
0x1400351f8  cmp     rcx, rdx
0x1400351fb  jnb     short loc_140035243
0x1400351fd  mov     rcx, rsi
0x140035200  call    ?_SetCapacity@?$vector@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(unsigned __int64)
0x140035205  test    al, al
0x140035207  jz      short loc_140035243
0x140035209  mov     r9, [rsi+8]
0x14003520d  lea     rcx, [rsp+218h+var_1E0]
0x140035212  mov     r8, [rsi]
0x140035215  lea     rdx, [rsp+218h+var_1E0]
0x14003521a  mov     rax, r9
0x14003521d  sub     rcx, rdi
0x140035220  sub     rax, r8
0x140035223  cmp     rcx, rax
0x140035226  jnb     short loc_14003522C
0x140035228  lea     rdx, [rcx+r8]
0x14003522c  mov     rax, [rdx]
0x14003522f  mov     qword ptr [rdx], 0
0x140035236  mov     r12, [rsp+218h+var_1E0]
0x14003523b  mov     [r9], rax
0x14003523e  add     qword ptr [rsi+8], 8
0x140035243  mov     rcx, [rbp+8]
0x140035247  xor     r9d, r9d
0x14003524a  xor     r8d, r8d
0x14003524d  mov     rdx, r13
0x140035250  call    cs:__imp_HamStartActivityAsync
0x140035257  nop     dword ptr [rax+rax+00h]
0x14003525c  mov     edi, eax
0x14003525e  test    eax, eax
0x140035260  js      short loc_1400352A9
0x140035262  xor     edi, edi
0x140035264  mov     rcx, cs:WPP_GLOBAL_Control
0x14003526b  lea     rax, WPP_GLOBAL_Control
0x140035272  cmp     rcx, rax
0x140035275  jz      loc_1400351A1
0x14003527b  test    byte ptr [rcx+1Ch], 4
0x14003527f  jz      loc_1400351A1
0x140035285  movzx   eax, [rsp+218h+var_1E8]
0x14003528a  lea     edx, [rdi+16h]
0x14003528d  mov     rcx, [rcx+10h]
0x140035291  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140035298  mov     r9d, r15d
0x14003529b  mov     dword ptr [rsp+218h+var_1F8], eax
0x14003529f  call    WPP_SF_Dd
0x1400352a4  jmp     loc_1400351A1
0x1400352a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352b0  lea     rax, WPP_GLOBAL_Control
0x1400352b7  cmp     rcx, rax
0x1400352ba  jz      loc_14003519D
0x1400352c0  test    byte ptr [rcx+1Ch], 1
0x1400352c4  jz      loc_14003519D
0x1400352ca  mov     edx, 15h
0x1400352cf  jmp     loc_140035186
0x1400352d4  mov     edi, 8007000Eh
0x1400352d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352e0  lea     rax, WPP_GLOBAL_Control
0x1400352e7  cmp     rcx, rax
0x1400352ea  jz      short loc_14003530A
0x1400352ec  test    byte ptr [rcx+1Ch], 1
0x1400352f0  jz      short loc_14003530A
0x1400352f2  mov     rcx, [rcx+10h]
0x1400352f6  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x1400352fd  mov     edx, 13h
0x140035302  mov     r9d, edi
0x140035305  call    WPP_SF_d
0x14003530a  test    r12, r12
0x14003530d  jz      short loc_14003531C
0x14003530f  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x140035314  mov     rcx, r12; void *
0x140035317  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003531c  lea     rcx, [rbx+1]
0x140035320  cmp     rcx, 1
0x140035324  jbe     short loc_140035335
0x140035326  mov     rcx, rbx; hObject
0x140035329  call    cs:__imp_CloseHandle
0x140035330  nop     dword ptr [rax+rax+00h]
0x140035335  mov     eax, edi
0x140035337  mov     rcx, [rsp+218h+var_48]
0x14003533f  xor     rcx, rsp; StackCookie
0x140035342  call    __security_check_cookie
0x140035347  mov     rbx, [rsp+218h+arg_10]
0x14003534f  add     rsp, 1E0h
0x140035356  pop     r15
0x140035358  pop     r14
0x14003535a  pop     r13
0x14003535c  pop     r12
0x14003535e  pop     rdi
0x14003535f  pop     rsi
0x140035360  pop     rbp
0x140035361  retn
```

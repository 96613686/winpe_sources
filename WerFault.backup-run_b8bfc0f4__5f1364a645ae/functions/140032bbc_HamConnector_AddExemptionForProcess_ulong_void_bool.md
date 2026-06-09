# HamConnector::AddExemptionForProcess(ulong,void *,bool)

- ea: `0x140032bbc`
- end: `0x140032faf`
- name: `?AddExemptionForProcess@HamConnector@@QEAAJKPEAX_N@Z`
- size: `1011`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, DWORD dwProcessId, void *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140026410`

## callees

- `0x140002470`
- `0x140002494`
- `0x140002728`
- `0x1400030a8`
- `0x140014474`
- `0x1400144b4`
- `0x140032bbc`
- `0x140033384`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140032d2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140032da0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140032d2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140032da0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140032d92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140032e06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140032d92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140032e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032c84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032f7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032f7c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140032c72`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140032c72`
- `RMCLIENT!HamStartActivityAsync` at `0x140032ea9`
- `RMCLIENT!HamStartActivityAsync` at `0x140032ea9`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x140032c1e`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x140032c1e`
- `RMCLIENT!HamCreateActivityForProcess` at `0x140032dbe`
- `RMCLIENT!HamCreateActivityForProcess` at `0x140032dbe`

## pseudocode

```c
__int64 __fastcall HamConnector::AddExemptionForProcess(
        PSRWLOCK SRWLock,
        DWORD dwProcessId,
        void *a3,
        unsigned __int8 a4)
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
  RTL_SRWLOCK *v35; // [rsp+38h] [rbp-1E0h] BYREF
  _BYTE v36[400]; // [rsp+40h] [rbp-1D8h] BYREF

  v8 = 0;
  memset_0(v36, 0, 0x188u);
  v9 = HamPopulateActivityPropertiesByClass(L"Windows Error Reporting", 0, 6, v36);
  if ( v9 < 0 )
  {
    v10 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_b6936b066fab37677c58fa622b799e39_Traceguids,
        dwProcessId,
        v9);
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
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_b6936b066fab37677c58fa622b799e39_Traceguids,
        dwProcessId,
        v11);
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
    v35 = v13;
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
    ActivityForProcess = HamCreateActivityForProcess(SRWLock[1].Ptr, v13, v10, v36, &v13[2]);
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
      v31 = (void **)&v35;
      if ( (char *)&v35 - v27 < (unsigned __int64)(v30 - (char *)SRWLock[2].Ptr) )
        v31 = (void **)((char *)v15->Ptr + (char *)&v35 - v27);
      v32 = *v31;
      *v31 = 0;
      v8 = v35;
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
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_b6936b066fab37677c58fa622b799e39_Traceguids,
          dwProcessId,
          a4);
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
    WPP_SF_Dd(
      *((_QWORD *)v22 + 2),
      v23,
      WPP_b6936b066fab37677c58fa622b799e39_Traceguids,
      dwProcessId,
      ActivityForProcess);
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
0x140032bbc  mov     [rsp+arg_10], rbx
0x140032bc1  push    rbp
0x140032bc2  push    rsi
0x140032bc3  push    rdi
0x140032bc4  push    r12
0x140032bc6  push    r13
0x140032bc8  push    r14
0x140032bca  push    r15
0x140032bcc  sub     rsp, 1E0h
0x140032bd3  mov     rax, cs:__security_cookie
0x140032bda  xor     rax, rsp
0x140032bdd  mov     [rsp+218h+var_48], rax
0x140032be5  mov     rsi, r8
0x140032be8  mov     [rsp+218h+var_1E8], r9b
0x140032bed  mov     r15d, edx
0x140032bf0  mov     rbp, rcx
0x140032bf3  xor     edx, edx; Val
0x140032bf5  lea     rcx, [rsp+218h+var_1D8]; void *
0x140032bfa  mov     r8d, 188h; Size
0x140032c00  mov     r13b, r9b
0x140032c03  xor     r12d, r12d
0x140032c06  call    memset_0
0x140032c0b  lea     r9, [rsp+218h+var_1D8]
0x140032c10  xor     edx, edx
0x140032c12  lea     r8d, [r12+6]
0x140032c17  lea     rcx, aWindowsErrorRe; "Windows Error Reporting"
0x140032c1e  call    cs:__imp_HamPopulateActivityPropertiesByClass
0x140032c24  mov     edi, eax
0x140032c26  test    eax, eax
0x140032c28  jns     short loc_140032C68
0x140032c2a  xor     ebx, ebx
0x140032c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c33  lea     rax, WPP_GLOBAL_Control
0x140032c3a  cmp     rcx, rax
0x140032c3d  jz      short loc_140032C5F
0x140032c3f  test    byte ptr [rcx+1Ch], 1
0x140032c43  jz      short loc_140032C5F
0x140032c45  mov     rcx, [rcx+10h]
0x140032c49  lea     edx, [rbx+11h]
0x140032c4c  mov     r9d, r15d
0x140032c4f  mov     dword ptr [rsp+218h+var_1F8], edi
0x140032c53  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140032c5a  call    WPP_SF_Dd
0x140032c5f  bts     edi, 1Ch
0x140032c63  jmp     loc_140032F5D
0x140032c68  mov     r8d, r15d; dwProcessId
0x140032c6b  xor     edx, edx; bInheritHandle
0x140032c6d  mov     ecx, 1001h; dwDesiredAccess
0x140032c72  call    cs:__imp_OpenProcess
0x140032c78  mov     rbx, rax
0x140032c7b  inc     rax
0x140032c7e  cmp     rax, 1
0x140032c82  ja      short loc_140032CDB
0x140032c84  call    cs:__imp_GetLastError
0x140032c8a  mov     edi, eax
0x140032c8c  test    eax, eax
0x140032c8e  jle     short loc_140032C99
0x140032c90  movzx   edi, ax
0x140032c93  or      edi, 80070000h
0x140032c99  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ca0  lea     rax, WPP_GLOBAL_Control
0x140032ca7  cmp     rcx, rax
0x140032caa  jz      loc_140032F5D
0x140032cb0  test    byte ptr [rcx+1Ch], 1
0x140032cb4  jz      loc_140032F5D
0x140032cba  mov     rcx, [rcx+10h]
0x140032cbe  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140032cc5  mov     edx, 12h
0x140032cca  mov     dword ptr [rsp+218h+var_1F8], edi
0x140032cce  mov     r9d, r15d
0x140032cd1  call    WPP_SF_Dd
0x140032cd6  jmp     loc_140032F5D
0x140032cdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140032ce2  mov     ecx, 30h ; '0'; unsigned __int64
0x140032ce7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140032cec  mov     r14, rax
0x140032cef  test    rax, rax
0x140032cf2  jz      loc_140032F27
0x140032cf8  mov     rax, [rbp+8]
0x140032cfc  mov     rcx, rbp; SRWLock
0x140032cff  mov     [r14], r12
0x140032d02  mov     r12, r14
0x140032d05  mov     [r14+28h], rax
0x140032d09  mov     [r14+8], r15d
0x140032d0d  mov     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x140032d15  mov     [r14+18h], rsi
0x140032d19  mov     [r14+20h], r13b
0x140032d1d  mov     dword ptr [r14+24h], 4
0x140032d25  mov     [rsp+218h+var_1E0], r14
0x140032d2a  call    cs:__imp_AcquireSRWLockExclusive
0x140032d30  lea     rsi, [rbp+10h]
0x140032d34  mov     r8, 0FFFFFFFFFFFFFFFh
0x140032d3e  mov     rcx, [rsi+8]
0x140032d42  sub     rcx, [rsi]
0x140032d45  mov     rax, [rsi+10h]
0x140032d49  sub     rax, [rsi]
0x140032d4c  sar     rcx, 3
0x140032d50  inc     rcx
0x140032d53  sar     rax, 3
0x140032d57  cmp     rcx, rax
0x140032d5a  jbe     short loc_140032D9D
0x140032d5c  shr     rax, 2
0x140032d60  mov     rdx, rcx
0x140032d63  imul    rax, 7
0x140032d67  add     rax, 8
0x140032d6b  cmp     rax, rcx
0x140032d6e  cmovnb  rdx, rax
0x140032d72  cmp     rdx, r8
0x140032d75  cmova   rdx, r8
0x140032d79  cmp     rcx, rdx
0x140032d7c  ja      short loc_140032D8A
0x140032d7e  mov     rcx, rsi
0x140032d81  call    ?_SetCapacity@?$vector@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(unsigned __int64)
0x140032d86  test    al, al
0x140032d88  jnz     short loc_140032D9D
0x140032d8a  mov     edi, 8007000Eh
0x140032d8f  mov     rcx, rbp; SRWLock
0x140032d92  call    cs:__imp_ReleaseSRWLockExclusive
0x140032d98  jmp     loc_140032F5D
0x140032d9d  mov     rcx, r14; SRWLock
0x140032da0  call    cs:__imp_AcquireSRWLockExclusive
0x140032da6  mov     rcx, [rbp+8]
0x140032daa  lea     r13, [r14+10h]
0x140032dae  lea     r9, [rsp+218h+var_1D8]
0x140032db3  mov     [rsp+218h+var_1F8], r13
0x140032db8  mov     r8, rbx
0x140032dbb  mov     rdx, r14
0x140032dbe  call    cs:__imp_HamCreateActivityForProcess
0x140032dc4  mov     edi, eax
0x140032dc6  test    eax, eax
0x140032dc8  jns     short loc_140032E0E
0x140032dca  mov     rcx, cs:WPP_GLOBAL_Control
0x140032dd1  lea     rax, WPP_GLOBAL_Control
0x140032dd8  cmp     rcx, rax
0x140032ddb  jz      short loc_140032DFF
0x140032ddd  test    byte ptr [rcx+1Ch], 1
0x140032de1  jz      short loc_140032DFF
0x140032de3  mov     edx, 14h
0x140032de8  mov     rcx, [rcx+10h]
0x140032dec  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140032df3  mov     r9d, r15d
0x140032df6  mov     dword ptr [rsp+218h+var_1F8], edi
0x140032dfa  call    WPP_SF_Dd
0x140032dff  bts     edi, 1Ch
0x140032e03  mov     rcx, r14; SRWLock
0x140032e06  call    cs:__imp_ReleaseSRWLockExclusive
0x140032e0c  jmp     short loc_140032D8F
0x140032e0e  mov     rax, [rsi+8]
0x140032e12  mov     rcx, [rsi+10h]
0x140032e16  mov     r13, [r13+0]
0x140032e1a  cmp     rax, rcx
0x140032e1d  jz      short loc_140032E27
0x140032e1f  xor     r12d, r12d
0x140032e22  mov     [rax], r14
0x140032e25  jmp     short loc_140032E97
0x140032e27  mov     rdi, [rsi]
0x140032e2a  sub     rcx, rdi
0x140032e2d  sar     rcx, 3
0x140032e31  mov     rax, rcx
0x140032e34  shr     rax, 2
0x140032e38  imul    rdx, rax, 7
0x140032e3c  mov     rax, 0FFFFFFFFFFFFFFFh
0x140032e46  add     rdx, 8
0x140032e4a  cmp     rdx, rax
0x140032e4d  cmova   rdx, rax
0x140032e51  cmp     rcx, rdx
0x140032e54  jnb     short loc_140032E9C
0x140032e56  mov     rcx, rsi
0x140032e59  call    ?_SetCapacity@?$vector@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(unsigned __int64)
0x140032e5e  test    al, al
0x140032e60  jz      short loc_140032E9C
0x140032e62  mov     r9, [rsi+8]
0x140032e66  lea     rcx, [rsp+218h+var_1E0]
0x140032e6b  mov     r8, [rsi]
0x140032e6e  lea     rdx, [rsp+218h+var_1E0]
0x140032e73  mov     rax, r9
0x140032e76  sub     rcx, rdi
0x140032e79  sub     rax, r8
0x140032e7c  cmp     rcx, rax
0x140032e7f  jnb     short loc_140032E85
0x140032e81  lea     rdx, [rcx+r8]
0x140032e85  mov     rax, [rdx]
0x140032e88  mov     qword ptr [rdx], 0
0x140032e8f  mov     r12, [rsp+218h+var_1E0]
0x140032e94  mov     [r9], rax
0x140032e97  add     qword ptr [rsi+8], 8
0x140032e9c  mov     rcx, [rbp+8]
0x140032ea0  xor     r9d, r9d
0x140032ea3  xor     r8d, r8d
0x140032ea6  mov     rdx, r13
0x140032ea9  call    cs:__imp_HamStartActivityAsync
0x140032eaf  mov     edi, eax
0x140032eb1  test    eax, eax
0x140032eb3  js      short loc_140032EFC
0x140032eb5  xor     edi, edi
0x140032eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ebe  lea     rax, WPP_GLOBAL_Control
0x140032ec5  cmp     rcx, rax
0x140032ec8  jz      loc_140032E03
0x140032ece  test    byte ptr [rcx+1Ch], 4
0x140032ed2  jz      loc_140032E03
0x140032ed8  movzx   eax, [rsp+218h+var_1E8]
0x140032edd  lea     edx, [rdi+16h]
0x140032ee0  mov     rcx, [rcx+10h]
0x140032ee4  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140032eeb  mov     r9d, r15d
0x140032eee  mov     dword ptr [rsp+218h+var_1F8], eax
0x140032ef2  call    WPP_SF_Dd
0x140032ef7  jmp     loc_140032E03
0x140032efc  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f03  lea     rax, WPP_GLOBAL_Control
0x140032f0a  cmp     rcx, rax
0x140032f0d  jz      loc_140032DFF
0x140032f13  test    byte ptr [rcx+1Ch], 1
0x140032f17  jz      loc_140032DFF
0x140032f1d  mov     edx, 15h
0x140032f22  jmp     loc_140032DE8
0x140032f27  mov     edi, 8007000Eh
0x140032f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f33  lea     rax, WPP_GLOBAL_Control
0x140032f3a  cmp     rcx, rax
0x140032f3d  jz      short loc_140032F5D
0x140032f3f  test    byte ptr [rcx+1Ch], 1
0x140032f43  jz      short loc_140032F5D
0x140032f45  mov     rcx, [rcx+10h]
0x140032f49  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x140032f50  mov     edx, 13h
0x140032f55  mov     r9d, edi
0x140032f58  call    WPP_SF_d
0x140032f5d  test    r12, r12
0x140032f60  jz      short loc_140032F6F
0x140032f62  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x140032f67  mov     rcx, r12; void *
0x140032f6a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140032f6f  lea     rcx, [rbx+1]
0x140032f73  cmp     rcx, 1
0x140032f77  jbe     short loc_140032F82
0x140032f79  mov     rcx, rbx; hObject
0x140032f7c  call    cs:__imp_CloseHandle
0x140032f82  mov     eax, edi
0x140032f84  mov     rcx, [rsp+218h+var_48]
0x140032f8c  xor     rcx, rsp; StackCookie
0x140032f8f  call    __security_check_cookie
0x140032f94  mov     rbx, [rsp+218h+arg_10]
0x140032f9c  add     rsp, 1E0h
0x140032fa3  pop     r15
0x140032fa5  pop     r14
0x140032fa7  pop     r13
0x140032fa9  pop     r12
0x140032fab  pop     rdi
0x140032fac  pop     rsi
0x140032fad  pop     rbp
0x140032fae  retn
```

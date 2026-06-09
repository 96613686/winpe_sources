# Windows::System::CMemoryManager::GetAppMemoryInformation(unsigned __int64 *,unsigned __int64 *,_PROCESS_JOB_MEMORY_INFO *)

- ea: `0x180002860`
- end: `0x180002ca0`
- name: `?GetAppMemoryInformation@CMemoryManager@System@Windows@@AEAAJPEA_K0PEAU_PROCESS_JOB_MEMORY_INFO@@@Z`
- size: `1088`
- prototype: `signed int __fastcall(Windows::System::CMemoryManager *this, unsigned __int64 *, unsigned __int64 *, struct _PROCESS_JOB_MEMORY_INFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800190b0`

## callees

- `0x180001f68`
- `0x180002860`
- `0x180002cb0`
- `0x180002ee8`
- `0x180002f50`
- `0x1800148c0`
- `0x18001aec0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a51`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000296f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002a1b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002abd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002ad1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002b98`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002bbf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c01`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c40`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000296f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002a1b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002abd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002ad1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002b98`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002bbf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c01`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c40`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002910`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800029b3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002a4b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002910`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800029b3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002a4b`
- `ntdll!NtQueryInformationProcess` at `0x1800028e3`
- `ntdll!NtQueryInformationProcess` at `0x1800028e3`
- `ntdll!RtlNtStatusToDosError` at `0x180002ba5`
- `ntdll!RtlNtStatusToDosError` at `0x180002c0e`
- `ntdll!RtlNtStatusToDosError` at `0x180002c2b`
- `ntdll!RtlNtStatusToDosError` at `0x180002c59`
- `ntdll!RtlNtStatusToDosError` at `0x180002ba5`
- `ntdll!RtlNtStatusToDosError` at `0x180002c0e`
- `ntdll!RtlNtStatusToDosError` at `0x180002c2b`
- `ntdll!RtlNtStatusToDosError` at `0x180002c59`
- `ntdll!NtQueryWnfStateData` at `0x180002a00`
- `ntdll!NtQueryWnfStateData` at `0x180002a97`
- `ntdll!NtQueryWnfStateData` at `0x180002a00`
- `ntdll!NtQueryWnfStateData` at `0x180002a97`
- `ntdll!NtQuerySystemInformation` at `0x180002af9`
- `ntdll!NtQuerySystemInformation` at `0x180002b16`
- `ntdll!NtQuerySystemInformation` at `0x180002af9`
- `ntdll!NtQuerySystemInformation` at `0x180002b16`

## pseudocode

```c
signed int __fastcall Windows::System::CMemoryManager::GetAppMemoryInformation(
        Windows::System::CMemoryManager *this,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        struct _PROCESS_JOB_MEMORY_INFO *a4)
{
  unsigned __int64 *v6; // r14
  int v7; // eax
  ModernResourceManagerProxy *v8; // rax
  ModernResourceManagerProxy *v9; // rbx
  int v10; // eax
  void (*v11)(struct _RM_COMMIT_LEVEL_CHANGE_PAYLOAD *); // rdx
  void (*v12)(unsigned __int64, unsigned __int64); // r8
  int v13; // edi
  ModernResourceManagerProxy *v14; // r15
  unsigned __int64 v15; // rbx
  signed int v16; // r14d
  NTSTATUS v17; // eax
  unsigned __int64 v18; // r15
  ModernResourceManagerProxy *v19; // r13
  char *v20; // r14
  signed int v21; // edi
  NTSTATUS v22; // eax
  __int64 v23; // rbx
  int v24; // eax
  __int128 v25; // xmm1
  unsigned __int64 v26; // xmm0_8
  signed int result; // eax
  signed int v28; // eax
  signed int v29; // eax
  int v30; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v32; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 *v33; // [rsp+40h] [rbp-C0h]
  __int128 v34; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-A8h]
  __int128 ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v37; // [rsp+70h] [rbp-90h]
  unsigned __int64 v38; // [rsp+80h] [rbp-80h]
  __int128 v39; // [rsp+88h] [rbp-78h] BYREF
  __int128 v40; // [rsp+98h] [rbp-68h]
  _OWORD SystemInformation[4]; // [rsp+B0h] [rbp-50h] BYREF

  v33 = a2;
  v6 = a2;
  v32 = 0;
  v38 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v39 = 0;
  v40 = 0;
  ProcessInformation = 0;
  v37 = 0;
  v7 = NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBasePriority|0x40, &ProcessInformation, 0x28u, 0);
  if ( v7 < 0 )
  {
    result = RtlNtStatusToDosError(v7);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  RtlAcquireSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
  if ( Windows::System::CMemoryManager::s_pProxy )
  {
    RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
    goto LABEL_7;
  }
  v8 = (ModernResourceManagerProxy *)operator new(0x70u);
  if ( !v8 || (v9 = ModernResourceManagerProxy::ModernResourceManagerProxy(v8)) == 0 )
  {
    RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
    goto LABEL_17;
  }
  v10 = CempRpcBindToServer(qword_18001D170);
  v13 = v10 | 0x10000000;
  if ( v10 < 0 || (v13 = ModernResourceManagerProxy::RegisterCommitMemoryCallback(v9, v11, v12), v13 < 0) )
  {
    RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
    (*(void (__fastcall **)(ModernResourceManagerProxy *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v13 >= 0 )
      goto LABEL_7;
LABEL_17:
    v15 = v38;
    v18 = v38;
    goto LABEL_18;
  }
  if ( Windows::System::CMemoryManager::s_pProxy )
    (*(void (__fastcall **)(ModernResourceManagerProxy *))(*(_QWORD *)Windows::System::CMemoryManager::s_pProxy + 16LL))(Windows::System::CMemoryManager::s_pProxy);
  Windows::System::CMemoryManager::s_pProxy = v9;
  RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
LABEL_7:
  v14 = Windows::System::CMemoryManager::s_pProxy;
  v31 = 0;
  v15 = 0;
  v30 = 0;
  v34 = 0;
  v35 = 0;
  RtlAcquireSRWLockExclusive((char *)Windows::System::CMemoryManager::s_pProxy + 96);
  *((_DWORD *)v14 + 26) = GetCurrentThreadId();
  v16 = ModernResourceManagerProxy::RegisterWithServer(v14);
  if ( v16 >= 0 )
  {
    v30 = 24;
    v17 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, int *, __int128 *, int *))NtQueryWnfStateData)(
            (char *)v14 + 48,
            0,
            0,
            &v31,
            &v34,
            &v30);
    if ( v17 >= 0 )
    {
      v15 = *((_QWORD *)&v34 + 1);
      *((_DWORD *)v14 + 26) = 0;
      RtlReleaseSRWLockExclusive((char *)v14 + 96);
      goto LABEL_10;
    }
    v29 = RtlNtStatusToDosError(v17);
    v16 = v29;
    if ( v29 > 0 )
      v16 = (unsigned __int16)v29 | 0x80070000;
  }
  *((_DWORD *)v14 + 26) = 0;
  RtlReleaseSRWLockExclusive((char *)v14 + 96);
  if ( v16 < 0 )
    return v16;
LABEL_10:
  v18 = 0;
  v19 = Windows::System::CMemoryManager::s_pProxy;
  v31 = 0;
  v30 = 0;
  v34 = 0;
  v20 = (char *)Windows::System::CMemoryManager::s_pProxy + 96;
  v35 = 0;
  RtlAcquireSRWLockExclusive((char *)Windows::System::CMemoryManager::s_pProxy + 96);
  *((_DWORD *)v20 + 2) = GetCurrentThreadId();
  v21 = ModernResourceManagerProxy::RegisterWithServer(v19);
  if ( v21 < 0 )
    goto LABEL_32;
  v30 = 24;
  v22 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, int *, __int128 *, int *))NtQueryWnfStateData)(
          (char *)v19 + 48,
          0,
          0,
          &v31,
          &v34,
          &v30);
  if ( v22 < 0 )
  {
    v28 = RtlNtStatusToDosError(v22);
    v21 = v28;
    if ( v28 > 0 )
      v21 = (unsigned __int16)v28 | 0x80070000;
LABEL_32:
    *((_DWORD *)v20 + 2) = 0;
    RtlReleaseSRWLockExclusive(v20);
    if ( v21 < 0 )
      return v21;
    goto LABEL_15;
  }
  v18 = v35;
  if ( !v35 )
    v18 = *((_QWORD *)&v34 + 1);
  *((_DWORD *)v20 + 2) = 0;
  RtlReleaseSRWLockExclusive(v20);
LABEL_15:
  v6 = v33;
LABEL_18:
  if ( ((v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_21:
    if ( v6 )
      *v6 = v15;
    if ( a3 )
      *a3 = v18;
    if ( a4 )
    {
      v25 = v37;
      *(_OWORD *)a4 = ProcessInformation;
      v26 = v38;
      *((_OWORD *)a4 + 1) = v25;
      *((_QWORD *)a4 + 4) = v26;
    }
    return 0;
  }
  NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  v23 = DWORD2(SystemInformation[0]);
  v24 = NtQuerySystemInformation(MaxSystemInfoClass|SystemFullMemoryInformation, &v39, 0x20u, &v32);
  if ( v24 >= 0 )
  {
    v15 = v40 * v23;
    goto LABEL_21;
  }
  result = RtlNtStatusToDosError(v24);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002860  push    rbp
0x180002862  push    rsi
0x180002863  push    r12
0x180002865  push    r13
0x180002867  push    r14
0x180002869  lea     rbp, [rsp-10h]
0x18000286e  sub     rsp, 110h
0x180002875  mov     rax, cs:__security_cookie
0x18000287c  xor     rax, rsp
0x18000287f  mov     [rbp+30h+var_40], rax
0x180002883  xorps   xmm0, xmm0
0x180002886  mov     [rsp+130h+var_F0], rdx
0x18000288b  xorps   xmm1, xmm1
0x18000288e  mov     rsi, r9
0x180002891  mov     r12, r8
0x180002894  mov     r14, rdx
0x180002897  xor     r13d, r13d
0x18000289a  lea     r8, [rsp+130h+ProcessInformation]; ProcessInformation
0x18000289f  xor     eax, eax
0x1800028a1  mov     [rsp+130h+var_F8], r13d
0x1800028a6  mov     r9d, 28h ; '('; ProcessInformationLength
0x1800028ac  mov     [rbp+30h+var_B0], rax
0x1800028b0  mov     edx, 45h ; 'E'; ProcessInformationClass
0x1800028b5  mov     [rsp+130h+ReturnLength], r13; ReturnLength
0x1800028ba  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800028c1  movups  [rbp+30h+SystemInformation], xmm0
0x1800028c5  movups  [rbp+30h+var_70], xmm0
0x1800028c9  movups  [rbp+30h+var_60], xmm0
0x1800028cd  movups  [rbp+30h+var_50], xmm0
0x1800028d1  movups  [rbp+30h+var_A8], xmm0
0x1800028d5  movups  [rbp+30h+var_98], xmm0
0x1800028d9  movups  [rsp+130h+ProcessInformation], xmm1
0x1800028de  movups  [rsp+130h+var_C0], xmm1
0x1800028e3  call    cs:__imp_NtQueryInformationProcess
0x1800028e9  test    eax, eax
0x1800028eb  js      loc_180002C57
0x1800028f1  mov     [rsp+130h+arg_0], rbx
0x1800028f9  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x180002900  mov     [rsp+130h+var_28], rdi
0x180002908  mov     [rsp+130h+var_30], r15
0x180002910  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002916  cmp     cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A, r13; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x18000291d  jnz     loc_180002B91
0x180002923  mov     ecx, 70h ; 'p'; Size
0x180002928  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000292d  test    rax, rax
0x180002930  jz      loc_180002ACA
0x180002936  mov     rcx, rax; this
0x180002939  call    ??0ModernResourceManagerProxy@@QEAA@XZ; ModernResourceManagerProxy::ModernResourceManagerProxy(void)
0x18000293e  mov     rbx, rax
0x180002941  test    rax, rax
0x180002944  jz      loc_180002ACA
0x18000294a  lea     rdx, [rax+10h]
0x18000294e  lea     rcx, qword_18001D170; IfSpec
0x180002955  call    CempRpcBindToServer
0x18000295a  mov     edi, eax
0x18000295c  or      edi, 10000000h
0x180002962  jge     loc_180002BD1
0x180002968  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x18000296f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002975  mov     rax, [rbx]
0x180002978  mov     rcx, rbx
0x18000297b  mov     rax, [rax+10h]
0x18000297f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002984  test    edi, edi
0x180002986  js      loc_180002AD7
0x18000298c  mov     r15, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002993  xorps   xmm0, xmm0
0x180002996  xor     eax, eax
0x180002998  mov     [rsp+130h+var_FC], r13d
0x18000299d  mov     rbx, r13
0x1800029a0  mov     [rsp+130h+var_100], r13d
0x1800029a5  movups  [rsp+130h+var_E8], xmm0
0x1800029aa  lea     rcx, [r15+60h]
0x1800029ae  mov     [rsp+130h+var_D8], rax
0x1800029b3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800029b9  call    cs:__imp_GetCurrentThreadId
0x1800029bf  mov     rcx, r15; this
0x1800029c2  mov     [r15+68h], eax
0x1800029c6  call    ?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ; ModernResourceManagerProxy::RegisterWithServer(void)
0x1800029cb  mov     r14d, eax
0x1800029ce  test    eax, eax
0x1800029d0  js      loc_180002C38
0x1800029d6  lea     rax, [rsp+130h+var_100]
0x1800029db  mov     [rsp+130h+var_100], 18h
0x1800029e3  mov     [rsp+130h+var_108], rax
0x1800029e8  lea     rcx, [r15+30h]
0x1800029ec  lea     rax, [rsp+130h+var_E8]
0x1800029f1  xor     r8d, r8d
0x1800029f4  lea     r9, [rsp+130h+var_FC]
0x1800029f9  mov     [rsp+130h+ReturnLength], rax
0x1800029fe  xor     edx, edx
0x180002a00  call    cs:__imp_NtQueryWnfStateData
0x180002a06  test    eax, eax
0x180002a08  js      loc_180002C29
0x180002a0e  mov     rbx, qword ptr [rsp+130h+var_E8+8]
0x180002a13  lea     rcx, [r15+60h]
0x180002a17  mov     [r15+68h], r13d
0x180002a1b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002a21  mov     r15, r13
0x180002a24  xorps   xmm0, xmm0
0x180002a27  mov     r13, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002a2e  xor     eax, eax
0x180002a30  mov     [rsp+130h+var_FC], r15d
0x180002a35  mov     [rsp+130h+var_100], r15d
0x180002a3a  movups  [rsp+130h+var_E8], xmm0
0x180002a3f  lea     r14, [r13+60h]
0x180002a43  mov     [rsp+130h+var_D8], rax
0x180002a48  mov     rcx, r14
0x180002a4b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002a51  call    cs:__imp_GetCurrentThreadId
0x180002a57  mov     rcx, r13; this
0x180002a5a  mov     [r14+8], eax
0x180002a5e  call    ?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ; ModernResourceManagerProxy::RegisterWithServer(void)
0x180002a63  mov     edi, eax
0x180002a65  test    eax, eax
0x180002a67  js      loc_180002BB5
0x180002a6d  lea     rax, [rsp+130h+var_100]
0x180002a72  mov     [rsp+130h+var_100], 18h
0x180002a7a  mov     [rsp+130h+var_108], rax
0x180002a7f  lea     rcx, [r13+30h]
0x180002a83  lea     rax, [rsp+130h+var_E8]
0x180002a88  xor     r8d, r8d
0x180002a8b  lea     r9, [rsp+130h+var_FC]
0x180002a90  mov     [rsp+130h+ReturnLength], rax
0x180002a95  xor     edx, edx
0x180002a97  call    cs:__imp_NtQueryWnfStateData
0x180002a9d  test    eax, eax
0x180002a9f  js      loc_180002BA3
0x180002aa5  mov     r15, [rsp+130h+var_D8]
0x180002aaa  mov     rcx, r14
0x180002aad  test    r15, r15
0x180002ab0  cmovz   r15, qword ptr [rsp+130h+var_E8+8]
0x180002ab6  xor     r13d, r13d
0x180002ab9  mov     [r14+8], r13d
0x180002abd  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002ac3  mov     r14, [rsp+130h+var_F0]
0x180002ac8  jmp     short loc_180002ADE
0x180002aca  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x180002ad1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002ad7  mov     rbx, [rbp+30h+var_B0]
0x180002adb  mov     r15, rbx
0x180002ade  lea     rax, [rbx+1]
0x180002ae2  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002ae8  jnz     short loc_180002B29
0x180002aea  xor     r9d, r9d; ReturnLength
0x180002aed  lea     rdx, [rbp+30h+SystemInformation]; SystemInformation
0x180002af1  mov     r8d, 40h ; '@'; SystemInformationLength
0x180002af7  xor     ecx, ecx; SystemInformationClass
0x180002af9  call    cs:__imp_NtQuerySystemInformation
0x180002aff  mov     ebx, dword ptr [rbp+30h+SystemInformation+8]
0x180002b02  lea     r9, [rsp+130h+var_F8]; ReturnLength
0x180002b07  mov     r8d, 20h ; ' '; SystemInformationLength
0x180002b0d  lea     rdx, [rbp+30h+var_A8]; SystemInformation
0x180002b11  mov     ecx, 7Bh ; '{'; SystemInformationClass
0x180002b16  call    cs:__imp_NtQuerySystemInformation
0x180002b1c  test    eax, eax
0x180002b1e  js      loc_180002C0C
0x180002b24  imul    rbx, qword ptr [rbp+30h+var_98]
0x180002b29  test    r14, r14
0x180002b2c  jz      short loc_180002B31
0x180002b2e  mov     [r14], rbx
0x180002b31  test    r12, r12
0x180002b34  jz      short loc_180002B3A
0x180002b36  mov     [r12], r15
0x180002b3a  test    rsi, rsi
0x180002b3d  jz      short loc_180002B5A
0x180002b3f  movups  xmm0, [rsp+130h+ProcessInformation]
0x180002b44  movups  xmm1, [rsp+130h+var_C0]
0x180002b49  movups  xmmword ptr [rsi], xmm0
0x180002b4c  movsd   xmm0, [rbp+30h+var_B0]
0x180002b51  movups  xmmword ptr [rsi+10h], xmm1
0x180002b55  movsd   qword ptr [rsi+20h], xmm0
0x180002b5a  mov     eax, r13d
0x180002b5d  mov     rdi, [rsp+130h+var_28]
0x180002b65  mov     rbx, [rsp+130h+arg_0]
0x180002b6d  mov     r15, [rsp+130h+var_30]
0x180002b75  mov     rcx, [rbp+30h+var_40]
0x180002b79  xor     rcx, rsp; StackCookie
0x180002b7c  call    __security_check_cookie
0x180002b81  add     rsp, 110h
0x180002b88  pop     r14
0x180002b8a  pop     r13
0x180002b8c  pop     r12
0x180002b8e  pop     rsi
0x180002b8f  pop     rbp
0x180002b90  retn
0x180002b91  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x180002b98  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002b9e  jmp     loc_18000298C
0x180002ba3  mov     ecx, eax; Status
0x180002ba5  call    cs:__imp_RtlNtStatusToDosError
0x180002bab  mov     edi, eax
0x180002bad  test    eax, eax
0x180002baf  jg      loc_180002C92
0x180002bb5  xor     r13d, r13d
0x180002bb8  mov     rcx, r14
0x180002bbb  mov     [r14+8], r13d
0x180002bbf  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002bc5  test    edi, edi
0x180002bc7  jns     loc_180002AC3
0x180002bcd  mov     eax, edi
0x180002bcf  jmp     short loc_180002B5D
0x180002bd1  mov     rcx, rbx; this
0x180002bd4  call    ?RegisterCommitMemoryCallback@ModernResourceManagerProxy@@QEAAJP6AXPEAU_RM_COMMIT_LEVEL_CHANGE_PAYLOAD@@@ZP6AX_K2@Z@Z; ModernResourceManagerProxy::RegisterCommitMemoryCallback(void (*)(_RM_COMMIT_LEVEL_CHANGE_PAYLOAD *),void (*)(unsigned __int64,unsigned __int64))
0x180002bd9  mov     edi, eax
0x180002bdb  test    eax, eax
0x180002bdd  js      loc_180002968
0x180002be3  mov     rcx, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002bea  test    rcx, rcx
0x180002bed  jnz     loc_180002C74
0x180002bf3  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x180002bfa  mov     cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A, rbx; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002c01  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002c07  jmp     loc_18000298C
0x180002c0c  mov     ecx, eax; Status
0x180002c0e  call    cs:__imp_RtlNtStatusToDosError
0x180002c14  test    eax, eax
0x180002c16  jle     loc_180002B5D
0x180002c1c  movzx   eax, ax
0x180002c1f  or      eax, 80070000h
0x180002c24  jmp     loc_180002B5D
0x180002c29  mov     ecx, eax; Status
0x180002c2b  call    cs:__imp_RtlNtStatusToDosError
0x180002c31  mov     r14d, eax
0x180002c34  test    eax, eax
0x180002c36  jg      short loc_180002C85
0x180002c38  lea     rcx, [r15+60h]
0x180002c3c  mov     [r15+68h], r13d
0x180002c40  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002c46  test    r14d, r14d
0x180002c49  jns     loc_180002A21
0x180002c4f  mov     eax, r14d
0x180002c52  jmp     loc_180002B5D
0x180002c57  mov     ecx, eax; Status
0x180002c59  call    cs:__imp_RtlNtStatusToDosError
0x180002c5f  test    eax, eax
0x180002c61  jle     loc_180002B75
0x180002c67  movzx   eax, ax
0x180002c6a  or      eax, 80070000h
0x180002c6f  jmp     loc_180002B75
0x180002c74  mov     rax, [rcx]
0x180002c77  mov     rax, [rax+10h]
0x180002c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c80  jmp     loc_180002BF3
0x180002c85  movzx   r14d, ax
0x180002c89  or      r14d, 80070000h
0x180002c90  jmp     short loc_180002C38
0x180002c92  movzx   edi, ax
0x180002c95  or      edi, 80070000h
0x180002c9b  jmp     loc_180002BB5
```

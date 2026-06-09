# Windows::System::CMemoryManager::GetAppMemoryReport(Windows::System::IAppMemoryReport * *)

- ea: `0x180002320`
- end: `0x180002749`
- name: `?GetAppMemoryReport@CMemoryManager@System@Windows@@UEAAJPEAPEAUIAppMemoryReport@23@@Z`
- size: `1065`
- prototype: `__int64 __fastcall(Windows::System::CMemoryManager *__hidden this, struct Windows::System::IAppMemoryReport **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002320`
- `0x180002750`
- `0x180002cb0`
- `0x180002e10`
- `0x180002ec4`
- `0x180013ce8`
- `0x18001aec0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002409`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000249d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002409`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000249d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000246a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002507`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026ad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026d2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000246a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002507`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026ad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026d2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002403`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002497`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002403`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002497`
- `ntdll!NtQueryInformationProcess` at `0x1800023c1`
- `ntdll!NtQueryInformationProcess` at `0x1800023c1`
- `ntdll!RtlNtStatusToDosError` at `0x180002619`
- `ntdll!RtlNtStatusToDosError` at `0x180002699`
- `ntdll!RtlNtStatusToDosError` at `0x1800026be`
- `ntdll!RtlNtStatusToDosError` at `0x1800026e7`
- `ntdll!RtlNtStatusToDosError` at `0x180002619`
- `ntdll!RtlNtStatusToDosError` at `0x180002699`
- `ntdll!RtlNtStatusToDosError` at `0x1800026be`
- `ntdll!RtlNtStatusToDosError` at `0x1800026e7`
- `ntdll!NtQueryWnfStateData` at `0x18000244f`
- `ntdll!NtQueryWnfStateData` at `0x1800024e3`
- `ntdll!NtQueryWnfStateData` at `0x18000244f`
- `ntdll!NtQueryWnfStateData` at `0x1800024e3`
- `ntdll!NtQuerySystemInformation` at `0x180002531`
- `ntdll!NtQuerySystemInformation` at `0x18000254e`
- `ntdll!NtQuerySystemInformation` at `0x180002531`
- `ntdll!NtQuerySystemInformation` at `0x18000254e`

## pseudocode

```c
__int64 __fastcall Windows::System::CMemoryManager::GetAppMemoryReport(
        Windows::System::CMemoryManager *this,
        struct Windows::System::IAppMemoryReport **a2)
{
  __int64 v3; // xmm7_8
  __m128i v4; // xmm6
  int InformationProcess; // eax
  ModernResourceManagerProxy *v6; // r14
  __int64 v7; // rdi
  signed int v8; // ebx
  NTSTATUS v9; // eax
  ModernResourceManagerProxy *v10; // r15
  __int64 v11; // r14
  NTSTATUS v12; // eax
  bool v13; // zf
  __int64 v14; // rdi
  int v15; // eax
  Windows::System::CAppMemoryReport *v16; // rax
  __int64 v17; // rsi
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  signed int v20; // eax
  struct Windows::System::IAppMemoryReport *v21; // rcx
  signed int v23; // eax
  signed int v24; // eax
  __int64 v25; // [rsp+48h] [rbp-C0h] BYREF
  struct Windows::System::IAppMemoryReport *v26; // [rsp+50h] [rbp-B8h] BYREF
  ULONG v27; // [rsp+58h] [rbp-B0h] BYREF
  ULONG v28[4]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD ProcessInformation[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v30; // [rsp+88h] [rbp-80h]
  __int64 v31; // [rsp+98h] [rbp-70h]
  __int128 v32; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-58h]
  _OWORD SystemInformation[4]; // [rsp+C8h] [rbp-40h] BYREF

  v26 = 0;
  v3 = 0;
  v27 = 0;
  v4 = 0;
  v31 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v32 = 0;
  v33 = 0;
  *(_OWORD *)&ProcessInformation[1] = 0;
  v30 = 0;
  InformationProcess = NtQueryInformationProcess(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         ProcessBasePriority|0x40,
                         &ProcessInformation[1],
                         0x28u,
                         0);
  if ( InformationProcess < 0 )
  {
    v20 = RtlNtStatusToDosError(InformationProcess);
    v8 = v20;
    if ( v20 <= 0 )
      goto LABEL_21;
    goto LABEL_34;
  }
  if ( (int)Windows::System::CMemoryManager::Init() < 0 )
  {
    v7 = v31;
    v11 = v31;
    goto LABEL_12;
  }
  v6 = Windows::System::CMemoryManager::s_pProxy;
  v7 = 0;
  v25 = 0;
  *(_OWORD *)v28 = 0;
  ProcessInformation[0] = 0;
  RtlAcquireSRWLockExclusive((char *)Windows::System::CMemoryManager::s_pProxy + 96);
  *((_DWORD *)v6 + 26) = GetCurrentThreadId();
  v8 = ModernResourceManagerProxy::RegisterWithServer(v6);
  if ( v8 >= 0 )
  {
    LODWORD(v25) = 24;
    v9 = NtQueryWnfStateData((char *)v6 + 48, 0, 0, (char *)&v25 + 4, v28, &v25);
    if ( v9 >= 0 )
    {
      v7 = *(_QWORD *)&v28[2];
      *((_DWORD *)v6 + 26) = 0;
      RtlReleaseSRWLockExclusive((char *)v6 + 96);
      goto LABEL_6;
    }
    v24 = RtlNtStatusToDosError(v9);
    v8 = v24;
    if ( v24 > 0 )
      v8 = (unsigned __int16)v24 | 0x80070000;
  }
  *((_DWORD *)v6 + 26) = 0;
  RtlReleaseSRWLockExclusive((char *)v6 + 96);
  if ( v8 < 0 )
    goto LABEL_22;
LABEL_6:
  v10 = Windows::System::CMemoryManager::s_pProxy;
  v11 = 0;
  v25 = 0;
  *(_OWORD *)v28 = 0;
  ProcessInformation[0] = 0;
  RtlAcquireSRWLockExclusive((char *)Windows::System::CMemoryManager::s_pProxy + 96);
  *((_DWORD *)v10 + 26) = GetCurrentThreadId();
  v8 = ModernResourceManagerProxy::RegisterWithServer(v10);
  if ( v8 >= 0 )
  {
    LODWORD(v25) = 24;
    v12 = NtQueryWnfStateData((char *)v10 + 48, 0, 0, (char *)&v25 + 4, v28, &v25);
    if ( v12 >= 0 )
    {
      v11 = ProcessInformation[0];
      v13 = ProcessInformation[0] == 0;
      *((_DWORD *)v10 + 26) = 0;
      if ( v13 )
        v11 = *(_QWORD *)&v28[2];
      RtlReleaseSRWLockExclusive((char *)v10 + 96);
      goto LABEL_12;
    }
    v23 = RtlNtStatusToDosError(v12);
    v8 = v23;
    if ( v23 > 0 )
      v8 = (unsigned __int16)v23 | 0x80070000;
  }
  *((_DWORD *)v10 + 26) = 0;
  RtlReleaseSRWLockExclusive((char *)v10 + 96);
  if ( v8 < 0 )
    goto LABEL_22;
LABEL_12:
  if ( ((v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
    v14 = DWORD2(SystemInformation[0]);
    v15 = NtQuerySystemInformation(MaxSystemInfoClass|SystemFullMemoryInformation, &v32, 0x20u, &v27);
    if ( v15 >= 0 )
    {
      v7 = v33 * v14;
      goto LABEL_15;
    }
    v20 = RtlNtStatusToDosError(v15);
    v8 = v20;
    if ( v20 <= 0 )
    {
LABEL_21:
      v7 = 0;
      v11 = 0;
      if ( v8 < 0 )
        goto LABEL_22;
      goto LABEL_16;
    }
LABEL_34:
    v8 = (unsigned __int16)v20 | 0x80070000;
    goto LABEL_21;
  }
LABEL_15:
  v4 = *(__m128i *)&ProcessInformation[1];
  v3 = v30;
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::System::IAppMemoryReport>::InternalRelease(&v26);
  v26 = 0;
  v16 = (Windows::System::CAppMemoryReport *)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  if ( v16 )
  {
    v17 = Windows::System::CAppMemoryReport::CAppMemoryReport(v16);
    v18 = _mm_srli_si128(v4, 8).m128i_u64[0];
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, unsigned __int64, __int64, __int64))(*(_QWORD *)v17 + 88LL))(
           v17,
           v18,
           v3,
           v18 + v4.m128i_i64[0],
           v7,
           v11);
    v19 = *(_QWORD *)v17;
    if ( v8 < 0 )
    {
      (*(void (__fastcall **)(__int64))(v19 + 16))(v17);
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(__int64, GUID *, struct Windows::System::IAppMemoryReport **))v19)(
             v17,
             &GUID_6d65339b_4d6f_45bc_9c5e_e49b3ff2758d,
             &v26);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v8 >= 0 )
      {
        *a2 = v26;
        v26 = 0;
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_22:
  v21 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(struct Windows::System::IAppMemoryReport *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002320  mov     r11, rsp
0x180002323  push    rbp
0x180002324  push    rbx
0x180002325  push    r13
0x180002327  lea     rbp, [r11-58h]
0x18000232b  sub     rsp, 140h
0x180002332  mov     rax, cs:__security_cookie
0x180002339  xor     rax, rsp
0x18000233c  mov     [rbp+50h+var_50], rax
0x180002340  mov     [r11+8], rsi
0x180002344  lea     r8, [rsp+150h+ProcessInformation+8]; ProcessInformation
0x180002349  xorps   xmm0, xmm0
0x18000234c  mov     [r11+18h], rdi
0x180002350  mov     [r11+20h], r12
0x180002354  xor     eax, eax
0x180002356  mov     [r11-20h], r14
0x18000235a  xor     r13d, r13d
0x18000235d  mov     [r11-28h], r15
0x180002361  xorps   xmm1, xmm1
0x180002364  movaps  xmmword ptr [r11-38h], xmm6
0x180002369  mov     r12, rdx
0x18000236c  movaps  xmmword ptr [r11-48h], xmm7
0x180002371  mov     r9d, 28h ; '('; ProcessInformationLength
0x180002377  mov     [rbp+50h+var_C0], rax
0x18000237b  mov     edx, 45h ; 'E'; ProcessInformationClass
0x180002380  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180002387  mov     [rsp+150h+var_108], r13
0x18000238c  xorps   xmm7, xmm7
0x18000238f  mov     [rsp+150h+var_100], r13d
0x180002394  xorps   xmm6, xmm6
0x180002397  mov     [rbp+50h+var_C0], rax
0x18000239b  movups  [rbp+50h+SystemInformation], xmm0
0x18000239f  mov     [rsp+150h+ReturnLength], r13; ReturnLength
0x1800023a4  movups  [rbp+50h+var_80], xmm0
0x1800023a8  movups  [rbp+50h+var_70], xmm0
0x1800023ac  movups  [rbp+50h+var_60], xmm0
0x1800023b0  movups  [rbp+50h+var_B8], xmm0
0x1800023b4  movups  [rbp+50h+var_A8], xmm0
0x1800023b8  movups  xmmword ptr [rsp+150h+ProcessInformation+8], xmm1
0x1800023bd  movups  [rbp+50h+var_D0], xmm1
0x1800023c1  call    cs:__imp_NtQueryInformationProcess
0x1800023c7  test    eax, eax
0x1800023c9  js      loc_1800026E5
0x1800023cf  call    ?Init@CMemoryManager@System@Windows@@CAJXZ; Windows::System::CMemoryManager::Init(void)
0x1800023d4  test    eax, eax
0x1800023d6  js      loc_18000250F
0x1800023dc  mov     r14, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x1800023e3  xorps   xmm0, xmm0
0x1800023e6  xor     eax, eax
0x1800023e8  mov     dword ptr [rsp+150h+var_110+4], r13d
0x1800023ed  mov     edi, r13d
0x1800023f0  mov     dword ptr [rsp+150h+var_110], r13d
0x1800023f5  movups  xmmword ptr [rsp+150h+var_100+8], xmm0
0x1800023fa  lea     rcx, [r14+60h]
0x1800023fe  mov     qword ptr [rsp+150h+ProcessInformation], rax
0x180002403  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002409  call    cs:__imp_GetCurrentThreadId
0x18000240f  mov     rcx, r14; this
0x180002412  mov     [r14+68h], eax
0x180002416  call    ?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ; ModernResourceManagerProxy::RegisterWithServer(void)
0x18000241b  mov     ebx, eax
0x18000241d  test    eax, eax
0x18000241f  js      loc_1800026CA
0x180002425  lea     rax, [rsp+150h+var_110]
0x18000242a  mov     dword ptr [rsp+150h+var_110], 18h
0x180002432  mov     [rsp+28h], rax
0x180002437  lea     rcx, [r14+30h]
0x18000243b  lea     rax, [rsp+150h+var_100+8]
0x180002440  xor     r8d, r8d
0x180002443  lea     r9, [rsp+150h+var_110+4]
0x180002448  mov     [rsp+150h+ReturnLength], rax
0x18000244d  xor     edx, edx
0x18000244f  call    cs:__imp_NtQueryWnfStateData
0x180002455  test    eax, eax
0x180002457  js      loc_1800026BC
0x18000245d  mov     rdi, [rsp+150h+var_F0]
0x180002462  lea     rcx, [r14+60h]
0x180002466  mov     [r14+68h], r13d
0x18000246a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002470  mov     r15, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002477  xorps   xmm0, xmm0
0x18000247a  xor     eax, eax
0x18000247c  mov     dword ptr [rsp+150h+var_110+4], r13d
0x180002481  mov     r14, r13
0x180002484  mov     dword ptr [rsp+150h+var_110], r13d
0x180002489  movups  xmmword ptr [rsp+150h+var_100+8], xmm0
0x18000248e  lea     rcx, [r15+60h]
0x180002492  mov     qword ptr [rsp+150h+ProcessInformation], rax
0x180002497  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000249d  call    cs:__imp_GetCurrentThreadId
0x1800024a3  mov     rcx, r15; this
0x1800024a6  mov     [r15+68h], eax
0x1800024aa  call    ?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ; ModernResourceManagerProxy::RegisterWithServer(void)
0x1800024af  mov     ebx, eax
0x1800024b1  test    eax, eax
0x1800024b3  js      loc_1800026A5
0x1800024b9  lea     rax, [rsp+150h+var_110]
0x1800024be  mov     dword ptr [rsp+150h+var_110], 18h
0x1800024c6  mov     [rsp+28h], rax
0x1800024cb  lea     rcx, [r15+30h]
0x1800024cf  lea     rax, [rsp+150h+var_100+8]
0x1800024d4  xor     r8d, r8d
0x1800024d7  lea     r9, [rsp+150h+var_110+4]
0x1800024dc  mov     [rsp+150h+ReturnLength], rax
0x1800024e1  xor     edx, edx
0x1800024e3  call    cs:__imp_NtQueryWnfStateData
0x1800024e9  test    eax, eax
0x1800024eb  js      loc_180002697
0x1800024f1  mov     r14, qword ptr [rsp+150h+ProcessInformation]
0x1800024f6  lea     rcx, [r15+60h]
0x1800024fa  test    r14, r14
0x1800024fd  mov     [r15+68h], r13d
0x180002501  cmovz   r14, [rsp+150h+var_F0]
0x180002507  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000250d  jmp     short loc_180002516
0x18000250f  mov     rdi, [rbp+50h+var_C0]
0x180002513  mov     r14, rdi
0x180002516  lea     rax, [rdi+1]
0x18000251a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002520  jnz     short loc_180002561
0x180002522  xor     r9d, r9d; ReturnLength
0x180002525  lea     rdx, [rbp+50h+SystemInformation]; SystemInformation
0x180002529  mov     r8d, 40h ; '@'; SystemInformationLength
0x18000252f  xor     ecx, ecx; SystemInformationClass
0x180002531  call    cs:__imp_NtQuerySystemInformation
0x180002537  mov     edi, dword ptr [rbp+50h+SystemInformation+8]
0x18000253a  lea     r9, [rsp+150h+var_100]; ReturnLength
0x18000253f  mov     r8d, 20h ; ' '; SystemInformationLength
0x180002545  lea     rdx, [rbp+50h+var_B8]; SystemInformation
0x180002549  mov     ecx, 7Bh ; '{'; SystemInformationClass
0x18000254e  call    cs:__imp_NtQuerySystemInformation
0x180002554  test    eax, eax
0x180002556  js      loc_180002617
0x18000255c  imul    rdi, qword ptr [rbp+50h+var_A8]
0x180002561  movups  xmm6, xmmword ptr [rsp+150h+ProcessInformation+8]
0x180002566  movups  xmm7, [rbp+50h+var_D0]
0x18000256a  lea     rcx, [rsp+150h+var_108]
0x18000256f  call    ?InternalRelease@?$ComPtr@UIAppMemoryReport@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IAppMemoryReport>::InternalRelease(void)
0x180002574  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000257b  mov     [rsp+150h+var_108], r13
0x180002580  mov     ecx, 58h ; 'X'; unsigned __int64
0x180002585  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000258a  test    rax, rax
0x18000258d  jz      loc_18000271B
0x180002593  mov     rcx, rax; this
0x180002596  call    ??0CAppMemoryReport@System@Windows@@QEAA@XZ; Windows::System::CAppMemoryReport::CAppMemoryReport(void)
0x18000259b  movq    r9, xmm6
0x1800025a0  mov     [rsp+28h], r14
0x1800025a5  mov     rsi, rax
0x1800025a8  psrldq  xmm6, 8
0x1800025ad  movq    rdx, xmm6
0x1800025b2  mov     [rsp+150h+ReturnLength], rdi
0x1800025b7  mov     r8, [rax]
0x1800025ba  add     r9, rdx
0x1800025bd  mov     rcx, rsi
0x1800025c0  mov     rax, [r8+58h]
0x1800025c4  movq    r8, xmm7
0x1800025c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ce  mov     ebx, eax
0x1800025d0  mov     rcx, rsi
0x1800025d3  mov     rax, [rsi]
0x1800025d6  test    ebx, ebx
0x1800025d8  js      loc_180002725
0x1800025de  mov     rax, [rax]
0x1800025e1  lea     r8, [rsp+150h+var_108]
0x1800025e6  lea     rdx, _GUID_6d65339b_4d6f_45bc_9c5e_e49b3ff2758d
0x1800025ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025f2  mov     ebx, eax
0x1800025f4  mov     rcx, rsi
0x1800025f7  mov     rax, [rsi]
0x1800025fa  mov     rax, [rax+10h]
0x1800025fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002603  test    ebx, ebx
0x180002605  js      short loc_180002637
0x180002607  mov     rax, [rsp+150h+var_108]
0x18000260c  mov     [r12], rax
0x180002610  mov     [rsp+150h+var_108], r13
0x180002615  jmp     short loc_180002637
0x180002617  mov     ecx, eax; Status
0x180002619  call    cs:__imp_RtlNtStatusToDosError
0x18000261f  mov     ebx, eax
0x180002621  test    eax, eax
0x180002623  jg      loc_1800026F7
0x180002629  mov     rdi, r13
0x18000262c  mov     r14, r13
0x18000262f  test    ebx, ebx
0x180002631  jns     loc_18000256A
0x180002637  mov     rcx, [rsp+150h+var_108]
0x18000263c  movaps  xmm7, [rsp+150h+var_48+8]
0x180002644  movaps  xmm6, [rsp+150h+var_38+8]
0x18000264c  mov     r15, [rsp+150h+var_20]
0x180002654  mov     r14, [rsp+138h]
0x18000265c  mov     r12, [rsp+150h+arg_18]
0x180002664  mov     rdi, [rsp+150h+arg_10]
0x18000266c  mov     rsi, [rsp+150h+arg_0]
0x180002674  test    rcx, rcx
0x180002677  jnz     loc_180002733
0x18000267d  mov     eax, ebx
0x18000267f  mov     rcx, [rbp+50h+var_50]
0x180002683  xor     rcx, rsp; StackCookie
0x180002686  call    __security_check_cookie
0x18000268b  add     rsp, 140h
0x180002692  pop     r13
0x180002694  pop     rbx
0x180002695  pop     rbp
0x180002696  retn
0x180002697  mov     ecx, eax; Status
0x180002699  call    cs:__imp_RtlNtStatusToDosError
0x18000269f  mov     ebx, eax
0x1800026a1  test    eax, eax
0x1800026a3  jg      short loc_180002710
0x1800026a5  lea     rcx, [r15+60h]
0x1800026a9  mov     [r15+68h], r13d
0x1800026ad  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800026b3  test    ebx, ebx
0x1800026b5  js      short loc_180002637
0x1800026b7  jmp     loc_180002516
0x1800026bc  mov     ecx, eax; Status
0x1800026be  call    cs:__imp_RtlNtStatusToDosError
0x1800026c4  mov     ebx, eax
0x1800026c6  test    eax, eax
0x1800026c8  jg      short loc_180002705
0x1800026ca  lea     rcx, [r14+60h]
0x1800026ce  mov     [r14+68h], r13d
0x1800026d2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800026d8  test    ebx, ebx
0x1800026da  js      loc_180002637
0x1800026e0  jmp     loc_180002470
0x1800026e5  mov     ecx, eax; Status
0x1800026e7  call    cs:__imp_RtlNtStatusToDosError
0x1800026ed  mov     ebx, eax
0x1800026ef  test    eax, eax
0x1800026f1  jle     loc_180002629
0x1800026f7  movzx   ebx, ax
0x1800026fa  or      ebx, 80070000h
0x180002700  jmp     loc_180002629
0x180002705  movzx   ebx, ax
0x180002708  or      ebx, 80070000h
0x18000270e  jmp     short loc_1800026CA
0x180002710  movzx   ebx, ax
0x180002713  or      ebx, 80070000h
0x180002719  jmp     short loc_1800026A5
0x18000271b  mov     ebx, 8007000Eh
0x180002720  jmp     loc_180002637
0x180002725  mov     rax, [rax+10h]
0x180002729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000272e  jmp     loc_180002637
0x180002733  mov     [rsp+150h+var_108], r13
0x180002738  mov     rax, [rcx]
0x18000273b  mov     rax, [rax+10h]
0x18000273f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002744  jmp     loc_18000267D
```

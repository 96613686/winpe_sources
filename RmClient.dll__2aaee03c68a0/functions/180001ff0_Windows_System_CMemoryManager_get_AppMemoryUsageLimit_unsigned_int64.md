# Windows::System::CMemoryManager::get_AppMemoryUsageLimit(unsigned __int64 *)

- ea: `0x180001ff0`
- end: `0x180002310`
- name: `?get_AppMemoryUsageLimit@CMemoryManager@System@Windows@@UEAAJPEA_K@Z`
- size: `800`
- prototype: `__int64 __fastcall(Windows::System::CMemoryManager *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001ff0`
- `0x180002750`
- `0x180002cb0`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800020ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000215b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800020ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000215b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000212b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800021b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000228a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800022b5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000212b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800021b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000228a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800022b5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800020c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002155`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800020c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002155`
- `ntdll!NtQueryInformationProcess` at `0x180002082`
- `ntdll!NtQueryInformationProcess` at `0x180002082`
- `ntdll!RtlNtStatusToDosError` at `0x180002210`
- `ntdll!RtlNtStatusToDosError` at `0x180002272`
- `ntdll!RtlNtStatusToDosError` at `0x1800022a1`
- `ntdll!RtlNtStatusToDosError` at `0x1800022cf`
- `ntdll!RtlNtStatusToDosError` at `0x180002210`
- `ntdll!RtlNtStatusToDosError` at `0x180002272`
- `ntdll!RtlNtStatusToDosError` at `0x1800022a1`
- `ntdll!RtlNtStatusToDosError` at `0x1800022cf`
- `ntdll!NtQueryWnfStateData` at `0x180002110`
- `ntdll!NtQueryWnfStateData` at `0x1800021a1`
- `ntdll!NtQueryWnfStateData` at `0x180002110`
- `ntdll!NtQueryWnfStateData` at `0x1800021a1`
- `ntdll!NtQuerySystemInformation` at `0x1800021de`
- `ntdll!NtQuerySystemInformation` at `0x1800021fc`
- `ntdll!NtQuerySystemInformation` at `0x1800021de`
- `ntdll!NtQuerySystemInformation` at `0x1800021fc`

## pseudocode

```c
__int64 __fastcall Windows::System::CMemoryManager::get_AppMemoryUsageLimit(
        Windows::System::CMemoryManager *this,
        unsigned __int64 *a2)
{
  int InformationProcess; // eax
  ModernResourceManagerProxy *v4; // r15
  unsigned __int64 v5; // rbx
  signed int v6; // edi
  NTSTATUS v7; // eax
  ModernResourceManagerProxy *v8; // r15
  signed int v9; // edi
  NTSTATUS v10; // eax
  __int64 v11; // rbx
  int v12; // eax
  signed int v13; // eax
  signed int v15; // eax
  signed int v16; // eax
  int v17; // [rsp+38h] [rbp-D0h] BYREF
  int v18; // [rsp+3Ch] [rbp-CCh] BYREF
  ULONG v19; // [rsp+40h] [rbp-C8h] BYREF
  ULONG v20[4]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+70h] [rbp-98h]
  _OWORD ProcessInformation_8[2]; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 v25; // [rsp+A0h] [rbp-68h]
  _OWORD SystemInformation[4]; // [rsp+A8h] [rbp-60h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v19 = 0;
  v25 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v22 = 0;
  v23 = 0;
  memset(ProcessInformation_8, 0, sizeof(ProcessInformation_8));
  InformationProcess = NtQueryInformationProcess(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         ProcessBasePriority|0x40,
                         ProcessInformation_8,
                         0x28u,
                         0);
  if ( InformationProcess < 0 )
  {
    v13 = RtlNtStatusToDosError(InformationProcess);
    v6 = v13;
    if ( v13 <= 0 )
      goto LABEL_15;
    goto LABEL_27;
  }
  if ( (int)Windows::System::CMemoryManager::Init() < 0 )
  {
    v5 = v25;
    goto LABEL_11;
  }
  v4 = Windows::System::CMemoryManager::s_pProxy;
  v18 = 0;
  v5 = 0;
  v17 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  RtlAcquireSRWLockExclusive((char *)Windows::System::CMemoryManager::s_pProxy + 96);
  *((_DWORD *)v4 + 26) = GetCurrentThreadId();
  v6 = ModernResourceManagerProxy::RegisterWithServer(v4);
  if ( v6 < 0 )
    goto LABEL_24;
  v17 = 24;
  v7 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, int *, ULONG *, int *))NtQueryWnfStateData)(
         (char *)v4 + 48,
         0,
         0,
         &v18,
         v20,
         &v17);
  if ( v7 < 0 )
  {
    v16 = RtlNtStatusToDosError(v7);
    v6 = v16;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
LABEL_24:
    *((_DWORD *)v4 + 26) = 0;
    RtlReleaseSRWLockExclusive((char *)v4 + 96);
    if ( v6 < 0 )
      goto LABEL_25;
    goto LABEL_7;
  }
  v5 = *(_QWORD *)&v20[2];
  *((_DWORD *)v4 + 26) = 0;
  RtlReleaseSRWLockExclusive((char *)v4 + 96);
LABEL_7:
  v8 = Windows::System::CMemoryManager::s_pProxy;
  v18 = 0;
  v17 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  RtlAcquireSRWLockExclusive((char *)Windows::System::CMemoryManager::s_pProxy + 96);
  *((_DWORD *)v8 + 26) = GetCurrentThreadId();
  v9 = ModernResourceManagerProxy::RegisterWithServer(v8);
  if ( v9 >= 0 )
  {
    v17 = 24;
    v10 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, int *, ULONG *, int *))NtQueryWnfStateData)(
            (char *)v8 + 48,
            0,
            0,
            &v18,
            v20,
            &v17);
    if ( v10 >= 0 )
    {
      *((_DWORD *)v8 + 26) = 0;
      RtlReleaseSRWLockExclusive((char *)v8 + 96);
      goto LABEL_11;
    }
    v15 = RtlNtStatusToDosError(v10);
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
  }
  *((_DWORD *)v8 + 26) = 0;
  RtlReleaseSRWLockExclusive((char *)v8 + 96);
  if ( v9 < 0 )
  {
    *a2 = 0;
    return (unsigned int)v9;
  }
LABEL_11:
  if ( ((v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
    v11 = DWORD2(SystemInformation[0]);
    v12 = NtQuerySystemInformation(MaxSystemInfoClass|SystemFullMemoryInformation, &v22, 0x20u, &v19);
    if ( v12 >= 0 )
    {
      v5 = v23 * v11;
      goto LABEL_16;
    }
    v13 = RtlNtStatusToDosError(v12);
    v6 = v13;
    if ( v13 <= 0 )
      goto LABEL_15;
LABEL_27:
    v6 = (unsigned __int16)v13 | 0x80070000;
LABEL_15:
    v5 = 0;
    if ( v6 >= 0 )
      goto LABEL_16;
LABEL_25:
    *a2 = 0;
    return (unsigned int)v6;
  }
LABEL_16:
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180001ff0  mov     r11, rsp
0x180001ff3  push    rbp
0x180001ff4  push    r14
0x180001ff6  lea     rbp, [r11-18h]
0x180001ffa  sub     rsp, 108h
0x180002001  mov     rax, cs:__security_cookie
0x180002008  xor     rax, rsp
0x18000200b  mov     [rbp+10h+var_30], rax
0x18000200f  mov     r14, rdx
0x180002012  test    rdx, rdx
0x180002015  jz      loc_1800022ED
0x18000201b  xorps   xmm0, xmm0
0x18000201e  mov     [r11+8], rbx
0x180002022  mov     [r11+18h], rsi
0x180002026  lea     r8, [rsp+110h+ProcessInformation+8]; ProcessInformation
0x18000202b  mov     [r11-18h], rdi
0x18000202f  xorps   xmm1, xmm1
0x180002032  mov     [r11-20h], r12
0x180002036  xor     eax, eax
0x180002038  xor     r12d, r12d
0x18000203b  mov     [r11-28h], r15
0x18000203f  mov     r9d, 28h ; '('; ProcessInformationLength
0x180002045  mov     [rsp+110h+var_D8], r12d
0x18000204a  mov     edx, 45h ; 'E'; ProcessInformationClass
0x18000204f  mov     [rsp+110h+ReturnLength], r12; ReturnLength
0x180002054  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000205b  mov     [rbp+10h+var_78], rax
0x18000205f  movups  [rbp+10h+SystemInformation], xmm0
0x180002063  movups  [rbp+10h+var_60], xmm0
0x180002067  movups  [rbp+10h+var_50], xmm0
0x18000206b  movups  [rbp+10h+var_40], xmm0
0x18000206f  movups  [rsp+110h+var_C0+8], xmm0
0x180002074  movups  [rsp+110h+var_B0+8], xmm0
0x180002079  movups  [rsp+110h+ProcessInformation+8], xmm1
0x18000207e  movups  [rbp+10h+var_88], xmm1
0x180002082  call    cs:__imp_NtQueryInformationProcess
0x180002088  test    eax, eax
0x18000208a  js      loc_1800022CD
0x180002090  call    ?Init@CMemoryManager@System@Windows@@CAJXZ; Windows::System::CMemoryManager::Init(void)
0x180002095  test    eax, eax
0x180002097  js      loc_1800021BF
0x18000209d  mov     r15, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x1800020a4  xorps   xmm0, xmm0
0x1800020a7  xor     eax, eax
0x1800020a9  mov     [rsp+110h+var_DC], r12d
0x1800020ae  mov     ebx, r12d
0x1800020b1  mov     [rsp+110h+var_E0], r12d
0x1800020b6  movups  xmmword ptr [rsp+110h+var_D8+8], xmm0
0x1800020bb  lea     rcx, [r15+60h]
0x1800020bf  mov     qword ptr [rsp+110h+var_C0], rax
0x1800020c4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800020ca  call    cs:__imp_GetCurrentThreadId
0x1800020d0  mov     rcx, r15; this
0x1800020d3  mov     [r15+68h], eax
0x1800020d7  call    ?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ; ModernResourceManagerProxy::RegisterWithServer(void)
0x1800020dc  mov     edi, eax
0x1800020de  test    eax, eax
0x1800020e0  js      loc_1800022AD
0x1800020e6  lea     rax, [rsp+110h+var_E0]
0x1800020eb  mov     [rsp+110h+var_E0], 18h
0x1800020f3  mov     qword ptr [rsp+110h+var_E8], rax
0x1800020f8  lea     rcx, [r15+30h]
0x1800020fc  lea     rax, [rsp+110h+var_D8+8]
0x180002101  xor     r8d, r8d
0x180002104  lea     r9, [rsp+110h+var_DC]
0x180002109  mov     [rsp+110h+ReturnLength], rax
0x18000210e  xor     edx, edx
0x180002110  call    cs:__imp_NtQueryWnfStateData
0x180002116  test    eax, eax
0x180002118  js      loc_18000229F
0x18000211e  mov     rbx, [rsp+110h+var_C8]
0x180002123  lea     rcx, [r15+60h]
0x180002127  mov     [r15+68h], r12d
0x18000212b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002131  mov     r15, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002138  xorps   xmm0, xmm0
0x18000213b  xor     eax, eax
0x18000213d  mov     [rsp+110h+var_DC], r12d
0x180002142  mov     [rsp+110h+var_E0], r12d
0x180002147  movups  xmmword ptr [rsp+110h+var_D8+8], xmm0
0x18000214c  lea     rcx, [r15+60h]
0x180002150  mov     qword ptr [rsp+110h+var_C0], rax
0x180002155  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000215b  call    cs:__imp_GetCurrentThreadId
0x180002161  mov     rcx, r15; this
0x180002164  mov     [r15+68h], eax
0x180002168  call    ?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ; ModernResourceManagerProxy::RegisterWithServer(void)
0x18000216d  mov     edi, eax
0x18000216f  test    eax, eax
0x180002171  js      loc_180002282
0x180002177  lea     rax, [rsp+110h+var_E0]
0x18000217c  mov     [rsp+110h+var_E0], 18h
0x180002184  mov     qword ptr [rsp+110h+var_E8], rax
0x180002189  lea     rcx, [r15+30h]
0x18000218d  lea     rax, [rsp+110h+var_D8+8]
0x180002192  xor     r8d, r8d
0x180002195  lea     r9, [rsp+110h+var_DC]
0x18000219a  mov     [rsp+110h+ReturnLength], rax
0x18000219f  xor     edx, edx
0x1800021a1  call    cs:__imp_NtQueryWnfStateData
0x1800021a7  test    eax, eax
0x1800021a9  js      loc_180002270
0x1800021af  lea     rcx, [r15+60h]
0x1800021b3  mov     [r15+68h], r12d
0x1800021b7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800021bd  jmp     short loc_1800021C3
0x1800021bf  mov     rbx, [rbp+10h+var_78]
0x1800021c3  lea     rax, [rbx+1]
0x1800021c7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800021cd  jnz     short loc_18000222B
0x1800021cf  xor     r9d, r9d; ReturnLength
0x1800021d2  lea     rdx, [rbp+10h+SystemInformation]; SystemInformation
0x1800021d6  mov     r8d, 40h ; '@'; SystemInformationLength
0x1800021dc  xor     ecx, ecx; SystemInformationClass
0x1800021de  call    cs:__imp_NtQuerySystemInformation
0x1800021e4  mov     ebx, dword ptr [rbp+10h+SystemInformation+8]
0x1800021e7  lea     r9, [rsp+110h+var_D8]; ReturnLength
0x1800021ec  mov     r8d, 20h ; ' '; SystemInformationLength
0x1800021f2  lea     rdx, [rsp+110h+var_C0+8]; SystemInformation
0x1800021f7  mov     ecx, 7Bh ; '{'; SystemInformationClass
0x1800021fc  call    cs:__imp_NtQuerySystemInformation
0x180002202  test    eax, eax
0x180002204  js      short loc_18000220E
0x180002206  imul    rbx, qword ptr [rsp+110h+var_B0+8]
0x18000220c  jmp     short loc_18000222B
0x18000220e  mov     ecx, eax; Status
0x180002210  call    cs:__imp_RtlNtStatusToDosError
0x180002216  mov     edi, eax
0x180002218  test    eax, eax
0x18000221a  jg      loc_1800022DF
0x180002220  mov     rbx, r12
0x180002223  test    edi, edi
0x180002225  js      loc_1800022C3
0x18000222b  mov     [r14], rbx
0x18000222e  mov     eax, r12d
0x180002231  mov     r12, [rsp+110h+var_18]
0x180002239  mov     rdi, [rsp+100h]
0x180002241  mov     rsi, [rsp+110h+arg_10]
0x180002249  mov     rbx, [rsp+110h+arg_0]
0x180002251  mov     r15, [rsp+110h+var_20]
0x180002259  mov     rcx, [rbp+10h+var_30]
0x18000225d  xor     rcx, rsp; StackCookie
0x180002260  call    __security_check_cookie
0x180002265  add     rsp, 108h
0x18000226c  pop     r14
0x18000226e  pop     rbp
0x18000226f  retn
0x180002270  mov     ecx, eax; Status
0x180002272  call    cs:__imp_RtlNtStatusToDosError
0x180002278  mov     edi, eax
0x18000227a  test    eax, eax
0x18000227c  jg      loc_180002302
0x180002282  lea     rcx, [r15+60h]
0x180002286  mov     [r15+68h], r12d
0x18000228a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002290  test    edi, edi
0x180002292  jns     loc_1800021C3
0x180002298  mov     [r14], r12
0x18000229b  mov     eax, edi
0x18000229d  jmp     short loc_180002231
0x18000229f  mov     ecx, eax; Status
0x1800022a1  call    cs:__imp_RtlNtStatusToDosError
0x1800022a7  mov     edi, eax
0x1800022a9  test    eax, eax
0x1800022ab  jg      short loc_1800022F7
0x1800022ad  lea     rcx, [r15+60h]
0x1800022b1  mov     [r15+68h], r12d
0x1800022b5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800022bb  test    edi, edi
0x1800022bd  jns     loc_180002131
0x1800022c3  mov     [r14], r12
0x1800022c6  mov     eax, edi
0x1800022c8  jmp     loc_180002231
0x1800022cd  mov     ecx, eax; Status
0x1800022cf  call    cs:__imp_RtlNtStatusToDosError
0x1800022d5  mov     edi, eax
0x1800022d7  test    eax, eax
0x1800022d9  jle     loc_180002220
0x1800022df  movzx   edi, ax
0x1800022e2  or      edi, 80070000h
0x1800022e8  jmp     loc_180002220
0x1800022ed  mov     eax, 80070057h
0x1800022f2  jmp     loc_180002259
0x1800022f7  movzx   edi, ax
0x1800022fa  or      edi, 80070000h
0x180002300  jmp     short loc_1800022AD
0x180002302  movzx   edi, ax
0x180002305  or      edi, 80070000h
0x18000230b  jmp     loc_180002282
```

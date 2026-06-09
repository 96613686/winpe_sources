# DpsProcessScenarioEvent

- ea: `0x180001830`
- end: `0x180001e82`
- name: `DpsProcessScenarioEvent`
- size: `1618`
- prototype: `__int64 __fastcall(void *Source)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b3e0`

## callees

- `0x1800013a0`
- `0x180001830`
- `0x180002090`
- `0x180005ec0`
- `0x180006e10`
- `0x1800086d0`
- `0x180008dc0`
- `0x180008ed0`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x18000c93c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800018cd`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800018cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001978`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000198f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001978`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000198f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001c9e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001c9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001cc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001cc0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180001c77`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180001c77`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180001a30`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180001a30`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001c87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001c87`
- `RPCRT4!UuidCreate` at `0x180001a99`
- `RPCRT4!UuidCreate` at `0x180001a99`

## pseudocode

```c
__int64 __fastcall DpsProcessScenarioEvent(char *Source)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  _DWORD *v5; // r12
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // r15
  __int64 v9; // rcx
  __int64 v10; // r9
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r15
  unsigned __int64 v18; // rbx
  char *v19; // rax
  __int64 v20; // rcx
  char *v21; // rbx
  unsigned int v22; // edx
  bool i; // cf
  int v24; // eax
  int v25; // eax
  int v26; // r8d
  int v27; // r8d
  __int64 Args; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+30h] [rbp-D0h]
  char *v31; // [rsp+30h] [rbp-D0h]
  unsigned int v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+38h] [rbp-C8h]
  __int64 v34; // [rsp+40h] [rbp-C0h]
  __int64 v35; // [rsp+48h] [rbp-B8h]
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v37[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v38[30]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v39[25]; // [rsp+AEh] [rbp-52h] BYREF
  _OWORD v40[3]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v41[30]; // [rsp+110h] [rbp+10h]
  int v42; // [rsp+12Eh] [rbp+2Eh]

  memset_0(v40, 0, 0x80u);
  _InterlockedIncrement(&g_ulTotalEvents);
  v2 = WdipGuidToString(Source + 24, v37, 64);
  v3 = v2;
  if ( v2 < 0 )
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (__int64)L"DpsProcessScenarioEvent",
      4283,
      (const wchar_t *)L"Error = %d",
      (unsigned __int16)v2);
    return v3;
  }
  v4 = *((unsigned __int16 *)Source + 20);
  strcpy(&v38[28], ";");
  if ( (unsigned int)_o__ultow_s(v4, v39, 25, 10) )
    return (unsigned int)-2147024809;
  v5 = g_pScenarioHead;
  v40[0] = v37[0];
  v40[2] = v37[2];
  v40[1] = v37[1];
  *(_OWORD *)v41 = *(_OWORD *)v38;
  v42 = 42;
  *(_OWORD *)&v41[14] = *(_OWORD *)&v38[14];
  if ( !g_pScenarioHead )
    return v3;
  while ( 1 )
  {
    if ( !(unsigned int)DpspGetScenarioExecutionLevel(v5) )
      goto LABEL_36;
    v6 = 0;
    v30 = 0;
    if ( !v5[5] )
      goto LABEL_36;
    while ( 1 )
    {
      v7 = *((_QWORD *)v5 + 6);
      v8 = 2 * v6;
      v9 = *(_QWORD *)(v7 + 8 * v8);
      if ( v9 )
      {
        if ( !*(_DWORD *)(v7 + 8 * v8 + 8)
          && (!(unsigned int)_o__wcsicmp(v9, v37)
           || !(unsigned int)_o__wcsicmp(*(_QWORD *)(*((_QWORD *)v5 + 6) + 8 * v8), v40)) )
        {
          if ( (unsigned int)DpspIsCoordinationPolicySatisfied(v5) )
            break;
        }
      }
      v6 = (unsigned int)(v30 + 1);
      v30 = v6;
      if ( (unsigned int)v6 >= v5[5] )
        goto LABEL_36;
    }
    if ( !Source )
    {
      LODWORD(Args) = 87;
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
        (__int64)L"DpspGetEventSize",
        1169,
        (const wchar_t *)L"Error = %d",
        Args);
      v3 = -2147024809;
LABEL_53:
      v27 = 4332;
      LODWORD(Args) = (unsigned __int16)v3;
LABEL_54:
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (__int64)L"DpsProcessScenarioEvent",
        v27,
        (const wchar_t *)L"Error = %d",
        Args);
      return v3;
    }
    v10 = *((unsigned __int16 *)Source + 42);
    v11 = ((*((unsigned __int16 *)Source + 43) + 7LL) & 0xFFFFFFF8LL) + 16 * (v10 + 7);
    if ( *((_WORD *)Source + 42) )
    {
      v12 = 0;
      do
      {
        v13 = v12++;
        v11 += ((*(unsigned __int16 *)(*((_QWORD *)Source + 11) + 16 * v13 + 6) + 7LL) & 0xFFFFFFF8LL)
             + *(unsigned __int16 *)(*((_QWORD *)Source + 11) + 16 * v13);
      }
      while ( v12 < (unsigned int)v10 );
    }
    if ( v11 > 0xFFFF )
    {
      v3 = -2147024362;
      goto LABEL_53;
    }
    v14 = (unsigned __int16)v11;
    v34 = (unsigned __int16)v11;
    if ( (unsigned __int16)v11 > (unsigned __int64)(AlpcMaxAllowedMessageLength() - 132) )
    {
      v3 = -2147467259;
      LODWORD(Args) = 16389;
      v27 = 4340;
      goto LABEL_54;
    }
    v15 = (unsigned int)(v14 + 1264);
    if ( (unsigned int)v15 < (int)v14 + 1248 )
    {
      v3 = -2147024362;
      LODWORD(Args) = 534;
      v27 = 4355;
      goto LABEL_54;
    }
    v16 = WdipAlloc(v15);
    v36 = v16;
    v17 = v16;
    if ( !v16 )
      break;
    *(_QWORD *)(v16 + 1240) = v16 + 1248;
    *(_QWORD *)(v16 + 1224) = v14 + v16 + 1248;
    UuidCreate((UUID *)(v16 + 24));
    *(_QWORD *)(v17 + 1216) = v5;
    *(_QWORD *)(v17 + 8LL * *(unsigned int *)(v17 + 116) + 816) = *((_QWORD *)v5 + 12);
    *(_QWORD *)(v17 + 808) = *((_QWORD *)v5 + 12);
    v33 = *(_QWORD *)(v17 + 1240);
    if ( memcpy_s((void *const)v33, (unsigned int)v14, Source, 0x70u) )
    {
      v3 = -2147024362;
      v25 = 534;
      v26 = 4386;
      goto LABEL_47;
    }
    v18 = v33 + v14;
    if ( v33 + 112 > v18 )
    {
      v3 = -2147024362;
      v25 = 534;
      v26 = 4392;
      goto LABEL_47;
    }
    if ( memcpy_s(
           (void *const)(v33 + 112),
           v18 - (v33 + 112),
           *((const void *const *)Source + 12),
           *((unsigned __int16 *)Source + 43)) )
    {
      v3 = -2147024362;
      v25 = 534;
      v26 = 4397;
      goto LABEL_47;
    }
    v19 = (char *)(v33 + 112 + ((*((unsigned __int16 *)Source + 43) + 7LL) & 0xFFFFFFF8LL));
    v31 = v19;
    if ( (unsigned __int64)v19 > v18 )
    {
      v3 = -2147024362;
      v25 = 534;
      v26 = 4403;
      goto LABEL_47;
    }
    if ( memcpy_s(
           v19,
           v18 - (_QWORD)v19,
           *((const void *const *)Source + 11),
           16LL * *((unsigned __int16 *)Source + 42)) )
    {
      v3 = -2147024362;
      v25 = 534;
      v26 = 4411;
      goto LABEL_47;
    }
    v20 = v34 + v33;
    v21 = &v31[16 * *((unsigned __int16 *)Source + 42)];
    if ( (unsigned __int64)v21 > v34 + v33 )
    {
      v3 = -2147024362;
      v25 = 534;
      v26 = 4417;
      goto LABEL_47;
    }
    v22 = 0;
    for ( i = *((_WORD *)Source + 42) != 0; ; i = v32 + 1 < *((unsigned __int16 *)Source + 42) )
    {
      v32 = v22;
      if ( !i )
        break;
      v35 = 16LL * v22;
      if ( memcpy_s(
             v21,
             v20 - (_QWORD)v21,
             *(const void *const *)(*((_QWORD *)Source + 11) + v35 + 8),
             *(unsigned __int16 *)(*((_QWORD *)Source + 11) + v35 + 6)) )
      {
        v3 = -2147024362;
        v25 = 534;
        v26 = 4427;
        goto LABEL_47;
      }
      v21 += (*(unsigned __int16 *)(*((_QWORD *)Source + 11) + v35 + 6) + 7LL) & 0xFFFFFFF8LL;
      v20 = v34 + v33;
      if ( (unsigned __int64)v21 > v34 + v33 )
      {
        v3 = -2147024362;
        v25 = 534;
        v26 = 4433;
        goto LABEL_47;
      }
      v22 = v32 + 1;
    }
    *(_WORD *)(v17 + 82) = v34;
    *(_DWORD *)(v17 + 84) = 1;
    *(_QWORD *)(v17 + 200) = 0;
    *(_QWORD *)(v17 + 784) = 0;
    *(_QWORD *)(v17 + 768) = 0;
    *(_QWORD *)(v17 + 776) = 0;
    *(_DWORD *)(v17 + 72) = 1;
    *(_DWORD *)(v17 + 208) = 0;
    *(_QWORD *)(v17 + 212) = 1000;
    *(_DWORD *)(v17 + 220) = 250;
    WdipCopyGuid(v17 + 56, Source + 64);
    InitializeSRWLock((PSRWLOCK)(v17 + 16));
    GetSystemTimeAsFileTime((LPFILETIME)(v17 + 136));
    *(_QWORD *)(v17 + 144) = *(_QWORD *)(v17 + 136);
    AcquireSRWLockExclusive(&g_SRWInstanceList);
    *(_QWORD *)(v17 + 1232) = g_pInstanceHead;
    g_pInstanceHead = v17;
    ReleaseSRWLockExclusive(&g_SRWInstanceList);
    v24 = DpspAttemptScenarioCompletionEx((struct INSTANCEINFO *)v17);
    v3 = v24;
    if ( v24 < 0 )
    {
      LODWORD(Args) = (unsigned __int16)v24;
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (__int64)L"DpsProcessScenarioEvent",
        4476,
        (const wchar_t *)L"Error = %d",
        Args);
      v3 = 0;
    }
LABEL_36:
    v5 = (_DWORD *)*((_QWORD *)v5 + 62);
    if ( !v5 )
      return v3;
  }
  v3 = -2147024882;
  v25 = 14;
  v26 = 4361;
LABEL_47:
  LODWORD(Args) = v25;
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
    (__int64)L"DpsProcessScenarioEvent",
    v26,
    (const wchar_t *)L"Error = %d",
    Args);
  if ( v17 )
    DpspFreeSpecificInstanceInfo(&v36);
  return v3;
}

```

## disassembly

```asm
0x180001830  push    rbp
0x180001832  push    rbx
0x180001833  push    rsi
0x180001834  push    rdi
0x180001835  push    r12
0x180001837  push    r13
0x180001839  push    r14
0x18000183b  push    r15
0x18000183d  lea     rbp, [rsp-78h]
0x180001842  sub     rsp, 178h
0x180001849  mov     rax, cs:__security_cookie
0x180001850  xor     rax, rsp
0x180001853  mov     [rbp+0B0h+var_50], rax
0x180001857  mov     r13, rcx
0x18000185a  xor     edx, edx; Val
0x18000185c  lea     rcx, [rbp+0B0h+var_D0]; void *
0x180001860  mov     r8d, 80h; Size
0x180001866  call    memset_0
0x18000186b  lock inc cs:g_ulTotalEvents
0x180001872  lea     rcx, [r13+18h]
0x180001876  mov     r8d, 40h ; '@'
0x18000187c  lea     rdx, [rsp+1B0h+var_150]
0x180001881  call    WdipGuidToString
0x180001886  mov     ebx, eax
0x180001888  test    eax, eax
0x18000188a  jns     short loc_1800018B3
0x18000188c  movzx   ecx, ax
0x18000188f  lea     r9, aErrorD; "Error = %d"
0x180001896  mov     dword ptr [rsp+1B0h+Args], ecx
0x18000189a  lea     rdx, aDpsprocessscen; "DpsProcessScenarioEvent"
0x1800018a1  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800018a8  mov     r8d, 10BBh
0x1800018ae  jmp     loc_180001E5B
0x1800018b3  movzx   ecx, word ptr [r13+28h]
0x1800018b8  lea     rdx, [rbp+0B0h+var_104+2]
0x1800018bc  mov     eax, 3Bh ; ';'
0x1800018c1  mov     [rbp+0B0h+var_104], ax
0x1800018c5  lea     r9d, [rax-31h]
0x1800018c9  lea     r8d, [rax-22h]
0x1800018cd  call    cs:__imp__o__ultow_s
0x1800018d3  test    eax, eax
0x1800018d5  jz      short loc_1800018E1
0x1800018d7  mov     ebx, 80070057h
0x1800018dc  jmp     loc_180001E60
0x1800018e1  movaps  xmm0, [rsp+1B0h+var_150]
0x1800018e6  movaps  xmm1, [rsp+1B0h+var_140]
0x1800018eb  mov     r12, cs:g_pScenarioHead
0x1800018f2  movaps  [rbp+0B0h+var_D0], xmm0
0x1800018f6  movaps  xmm0, [rbp+0B0h+var_130]
0x1800018fa  movaps  [rbp+0B0h+var_B0], xmm0
0x1800018fe  movaps  [rbp+0B0h+var_C0], xmm1
0x180001902  movaps  xmm1, [rbp+0B0h+var_120]
0x180001906  movaps  xmmword ptr [rbp+0B0h+var_A0], xmm1
0x18000190a  mov     [rbp+0B0h+var_82], 2Ah ; '*'
0x180001911  movups  xmm0, [rbp+0B0h+var_120+0Eh]
0x180001915  movups  xmmword ptr [rbp+0B0h+var_A0+0Eh], xmm0
0x180001919  test    r12, r12
0x18000191c  jz      loc_180001E60
0x180001922  lea     rdi, aErrorD; "Error = %d"
0x180001929  lea     r14, aDpsprocessscen; "DpsProcessScenarioEvent"
0x180001930  lea     rsi, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001937  mov     rcx, r12
0x18000193a  call    DpspGetScenarioExecutionLevel
0x18000193f  test    eax, eax
0x180001941  jz      loc_180001CF3
0x180001947  xor     r15d, r15d
0x18000194a  mov     dword ptr [rsp+1B0h+var_180], r15d
0x18000194f  cmp     [r12+14h], r15d
0x180001954  jbe     loc_180001CF3
0x18000195a  mov     rax, [r12+30h]
0x18000195f  add     r15, r15
0x180001962  mov     rcx, [rax+r15*8]
0x180001966  test    rcx, rcx
0x180001969  jz      short loc_1800019A5
0x18000196b  cmp     dword ptr [rax+r15*8+8], 0
0x180001971  jnz     short loc_1800019A5
0x180001973  lea     rdx, [rsp+1B0h+var_150]
0x180001978  call    cs:__imp__o__wcsicmp
0x18000197e  test    eax, eax
0x180001980  jz      short loc_180001999
0x180001982  mov     rcx, [r12+30h]
0x180001987  lea     rdx, [rbp+0B0h+var_D0]
0x18000198b  mov     rcx, [rcx+r15*8]
0x18000198f  call    cs:__imp__o__wcsicmp
0x180001995  test    eax, eax
0x180001997  jnz     short loc_1800019A5
0x180001999  mov     rcx, r12
0x18000199c  call    DpspIsCoordinationPolicySatisfied
0x1800019a1  test    eax, eax
0x1800019a3  jnz     short loc_1800019BE
0x1800019a5  mov     r15d, dword ptr [rsp+1B0h+var_180]
0x1800019aa  inc     r15d
0x1800019ad  mov     dword ptr [rsp+1B0h+var_180], r15d
0x1800019b2  cmp     r15d, [r12+14h]
0x1800019b7  jb      short loc_18000195A
0x1800019b9  jmp     loc_180001CF3
0x1800019be  test    r13, r13
0x1800019c1  jz      loc_180001E1C
0x1800019c7  movzx   r9d, word ptr [r13+54h]
0x1800019cc  mov     r11d, 0FFFFFFF8h
0x1800019d2  movzx   eax, word ptr [r13+56h]
0x1800019d7  add     rax, 7
0x1800019db  and     rax, r11
0x1800019de  lea     rdx, [r9+7]
0x1800019e2  shl     rdx, 4
0x1800019e6  add     rdx, rax
0x1800019e9  test    r9d, r9d
0x1800019ec  jz      short loc_180001A1B
0x1800019ee  mov     r10, [r13+58h]
0x1800019f2  xor     r8d, r8d
0x1800019f5  mov     eax, r8d
0x1800019f8  inc     r8d
0x1800019fb  add     rax, rax
0x1800019fe  movzx   ecx, word ptr [r10+rax*8+6]
0x180001a04  movzx   eax, word ptr [r10+rax*8]
0x180001a09  add     rcx, 7
0x180001a0d  and     rcx, r11
0x180001a10  add     rdx, rax
0x180001a13  add     rdx, rcx
0x180001a16  cmp     r8d, r9d
0x180001a19  jb      short loc_1800019F5
0x180001a1b  cmp     rdx, 0FFFFh
0x180001a22  ja      loc_180001E15
0x180001a28  movzx   ebx, dx
0x180001a2b  mov     [rsp+1B0h+var_170], rbx
0x180001a30  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180001a36  sub     rax, 84h
0x180001a3c  cmp     rbx, rax
0x180001a3f  ja      loc_180001E00
0x180001a45  lea     eax, [rbx+4E0h]
0x180001a4b  cmp     eax, 4E0h
0x180001a50  jb      loc_180001DEB
0x180001a56  lea     ecx, [rax+10h]
0x180001a59  cmp     ecx, eax
0x180001a5b  jb      loc_180001DD6
0x180001a61  call    WdipAlloc
0x180001a66  mov     [rsp+1B0h+var_160], rax
0x180001a6b  mov     r15, rax
0x180001a6e  test    rax, rax
0x180001a71  jz      loc_180001D9C
0x180001a77  add     rax, 4E0h
0x180001a7d  lea     rcx, [r15+18h]; Uuid
0x180001a81  mov     [r15+4D8h], rax
0x180001a88  lea     rax, [r15+4E0h]
0x180001a8f  add     rax, rbx
0x180001a92  mov     [r15+4C8h], rax
0x180001a99  call    cs:__imp_UuidCreate
0x180001a9f  mov     [r15+4C0h], r12
0x180001aa6  mov     r9d, 70h ; 'p'; SourceSize
0x180001aac  mov     ecx, [r15+74h]
0x180001ab0  mov     r8, r13; Source
0x180001ab3  mov     rax, [r12+60h]
0x180001ab8  mov     edx, ebx; DestinationSize
0x180001aba  mov     [r15+rcx*8+330h], rax
0x180001ac2  mov     rax, [r12+60h]
0x180001ac7  mov     [r15+328h], rax
0x180001ace  mov     rax, [r15+4D8h]
0x180001ad5  mov     rcx, rax; Destination
0x180001ad8  mov     [rsp+1B0h+var_178], rax
0x180001add  call    memcpy_s
0x180001ae2  test    eax, eax
0x180001ae4  jnz     loc_180001D8A
0x180001aea  mov     rax, [rsp+1B0h+var_178]
0x180001aef  add     rbx, rax
0x180001af2  add     rax, 70h ; 'p'
0x180001af6  cmp     rax, rbx
0x180001af9  ja      loc_180001D78
0x180001aff  movzx   r9d, word ptr [r13+56h]; SourceSize
0x180001b04  mov     rdx, rbx
0x180001b07  mov     r8, [r13+60h]; Source
0x180001b0b  sub     rdx, rax; DestinationSize
0x180001b0e  mov     rcx, rax; Destination
0x180001b11  call    memcpy_s
0x180001b16  test    eax, eax
0x180001b18  jnz     loc_180001D66
0x180001b1e  movzx   eax, word ptr [r13+56h]
0x180001b23  mov     ecx, 0FFFFFFF8h
0x180001b28  add     rax, 7
0x180001b2c  and     rax, rcx
0x180001b2f  mov     rcx, [rsp+1B0h+var_178]
0x180001b34  add     rcx, 70h ; 'p'
0x180001b38  add     rax, rcx
0x180001b3b  mov     [rsp+1B0h+var_180], rax
0x180001b40  cmp     rax, rbx
0x180001b43  ja      loc_180001D54
0x180001b49  movzx   r9d, word ptr [r13+54h]
0x180001b4e  mov     rdx, rbx
0x180001b51  mov     r8, [r13+58h]; Source
0x180001b55  sub     rdx, rax; DestinationSize
0x180001b58  shl     r9, 4; SourceSize
0x180001b5c  mov     rcx, rax; Destination
0x180001b5f  call    memcpy_s
0x180001b64  xor     r9d, r9d
0x180001b67  test    eax, eax
0x180001b69  jnz     loc_180001D42
0x180001b6f  movzx   r8d, word ptr [r13+54h]
0x180001b74  mov     rcx, [rsp+1B0h+var_178]
0x180001b79  mov     ebx, r8d
0x180001b7c  add     rcx, [rsp+1B0h+var_170]
0x180001b81  shl     rbx, 4
0x180001b85  add     rbx, [rsp+1B0h+var_180]
0x180001b8a  cmp     rbx, rcx
0x180001b8d  ja      loc_180001D30
0x180001b93  mov     edx, r9d
0x180001b96  cmp     r9w, r8w
0x180001b9a  jmp     short loc_180001C0C
0x180001b9c  mov     r8, [r13+58h]
0x180001ba0  mov     eax, edx
0x180001ba2  mov     rdx, rcx
0x180001ba5  shl     rax, 4
0x180001ba9  sub     rdx, rbx; DestinationSize
0x180001bac  mov     rcx, rbx; Destination
0x180001baf  mov     [rsp+1B0h+var_168], rax
0x180001bb4  movzx   r9d, word ptr [r8+rax+6]; SourceSize
0x180001bba  mov     r8, [r8+rax+8]; Source
0x180001bbf  call    memcpy_s
0x180001bc4  xor     r9d, r9d
0x180001bc7  test    eax, eax
0x180001bc9  jnz     loc_180001D1E
0x180001bcf  mov     rax, [r13+58h]
0x180001bd3  mov     rcx, [rsp+1B0h+var_168]
0x180001bd8  movzx   ecx, word ptr [rax+rcx+6]
0x180001bdd  mov     eax, 0FFFFFFF8h
0x180001be2  add     rcx, 7
0x180001be6  and     rcx, rax
0x180001be9  add     rbx, rcx
0x180001bec  mov     rcx, [rsp+1B0h+var_178]
0x180001bf1  add     rcx, [rsp+1B0h+var_170]
0x180001bf6  cmp     rbx, rcx
0x180001bf9  ja      loc_180001D09
0x180001bff  mov     edx, dword ptr [rsp+1B0h+var_180]
0x180001c03  movzx   eax, word ptr [r13+54h]
0x180001c08  inc     edx
0x180001c0a  cmp     edx, eax
0x180001c0c  mov     dword ptr [rsp+1B0h+var_180], edx
0x180001c10  jb      short loc_180001B9C
0x180001c12  mov     rax, [rsp+1B0h+var_170]
0x180001c17  lea     rdx, [r13+40h]
0x180001c1b  mov     [r15+52h], ax
0x180001c20  lea     rcx, [r15+38h]
0x180001c24  mov     eax, 1
0x180001c29  mov     [r15+54h], eax
0x180001c2d  mov     qword ptr [r15+0C8h], 0
0x180001c38  mov     [r15+310h], r9
0x180001c3f  mov     [r15+300h], r9
0x180001c46  mov     [r15+308h], r9
0x180001c4d  mov     [r15+48h], eax
0x180001c51  mov     [r15+0D0h], r9d
0x180001c58  mov     qword ptr [r15+0D4h], 3E8h
0x180001c63  mov     dword ptr [r15+0DCh], 0FAh
0x180001c6e  call    WdipCopyGuid
0x180001c73  lea     rcx, [r15+10h]; SRWLock
0x180001c77  call    cs:__imp_InitializeSRWLock
0x180001c7d  lea     rbx, [r15+88h]
0x180001c84  mov     rcx, rbx; lpSystemTimeAsFileTime
0x180001c87  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c8d  mov     rax, [rbx]
0x180001c90  lea     rcx, g_SRWInstanceList; SRWLock
0x180001c97  mov     [r15+90h], rax
0x180001c9e  call    cs:__imp_AcquireSRWLockExclusive
0x180001ca4  mov     rax, cs:g_pInstanceHead
0x180001cab  lea     rcx, g_SRWInstanceList; SRWLock
0x180001cb2  mov     [r15+4D0h], rax
0x180001cb9  mov     cs:g_pInstanceHead, r15
0x180001cc0  call    cs:__imp_ReleaseSRWLockExclusive
0x180001cc6  xor     edx, edx
0x180001cc8  mov     rcx, r15; struct INSTANCEINFO *
0x180001ccb  call    DpspAttemptScenarioCompletionEx
0x180001cd0  mov     ebx, eax
0x180001cd2  test    eax, eax
0x180001cd4  jns     short loc_180001CF3
0x180001cd6  movzx   eax, ax
0x180001cd9  mov     r9, rdi; int
0x180001cdc  mov     r8d, 117Ch; int
0x180001ce2  mov     dword ptr [rsp+1B0h+Args], eax; Args
0x180001ce6  mov     rdx, r14; int
0x180001ce9  mov     rcx, rsi; int
0x180001cec  call    WdipTraceError
0x180001cf1  xor     ebx, ebx
0x180001cf3  mov     r12, [r12+1F0h]
0x180001cfb  test    r12, r12
0x180001cfe  jnz     loc_180001937
0x180001d04  jmp     loc_180001E60
0x180001d09  mov     ebx, 80070216h
0x180001d0e  mov     eax, 216h
0x180001d13  mov     r8d, 1151h
0x180001d19  jmp     loc_180001DAC
0x180001d1e  mov     ebx, 80070216h
0x180001d23  mov     eax, 216h
0x180001d28  mov     r8d, 114Bh
0x180001d2e  jmp     short loc_180001DAC
0x180001d30  mov     ebx, 80070216h
0x180001d35  mov     eax, 216h
0x180001d3a  mov     r8d, 1141h
0x180001d40  jmp     short loc_180001DAC
0x180001d42  mov     ebx, 80070216h
0x180001d47  mov     eax, 216h
0x180001d4c  mov     r8d, 113Bh
0x180001d52  jmp     short loc_180001DAC
0x180001d54  mov     ebx, 80070216h
  ... truncated ...
```

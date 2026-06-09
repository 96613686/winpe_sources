# BampStartThrottledProcessInformation

- ea: `0x14001474c`
- end: `0x140014d0c`
- name: `BampStartThrottledProcessInformation`
- size: `1472`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140012530`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x14000b20c`
- `0x14000b238`
- `0x14000c0c8`
- `0x140010684`
- `0x140010760`
- `0x1400107a0`
- `0x1400107f0`
- `0x140010880`
- `0x140011160`
- `0x1400113a0`
- `0x1400113f0`
- `0x140011930`
- `0x140011c68`
- `0x140012368`
- `0x140012c1c`
- `0x140012c50`
- `0x140012c84`
- `0x14001474c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140014ccc`
- `ntoskrnl!ObfDereferenceObject` at `0x140014ccc`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140014881`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140014881`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14001499f`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14001499f`

## pseudocode

```c
__int64 __fastcall BampStartThrottledProcessInformation(__int64 a1, void *a2, unsigned int a3, __int64 a4, __int64 *a5)
{
  __int64 v5; // r13
  __int64 v6; // rsi
  __int64 v7; // r14
  __int64 ThrottledProcessInformation; // rax
  int ProcessUserSidString; // edi
  int v10; // r8d
  char v11; // r12
  _DWORD *v12; // r11
  __int64 v13; // rax
  __int128 v14; // xmm7
  __int64 v15; // xmm6_8
  _QWORD *v16; // rdx
  int v17; // eax
  __int64 v18; // xmm1_8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rbx
  char *v22; // r8
  char v23; // cl
  __int64 v24; // r9
  char v25; // dl
  __int64 v26; // rdi
  __int64 v27; // r15
  _QWORD *v28; // r11
  _QWORD *v29; // r9
  __int64 v30; // rdx
  PVOID v31; // rcx
  char v33; // [rsp+38h] [rbp-B1h]
  HANDLE ProcessId; // [rsp+40h] [rbp-A9h] BYREF
  __int64 v35; // [rsp+48h] [rbp-A1h] BYREF
  PEPROCESS Process; // [rsp+50h] [rbp-99h] BYREF
  __int64 v37; // [rsp+58h] [rbp-91h]
  __int64 *v38; // [rsp+60h] [rbp-89h]
  struct _UNICODE_STRING v39[2]; // [rsp+68h] [rbp-81h] BYREF
  __int64 v40; // [rsp+88h] [rbp-61h]
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+98h] [rbp-51h] BYREF
  __int64 *v42; // [rsp+B8h] [rbp-31h]
  __int64 v43; // [rsp+C0h] [rbp-29h]
  HANDLE *p_ProcessId; // [rsp+C8h] [rbp-21h]
  __int64 v45; // [rsp+D0h] [rbp-19h]

  v5 = *(_QWORD *)(a1 + 8);
  v6 = a1;
  v37 = a1;
  v7 = 0;
  v38 = a5;
  v39[0] = 0;
  ProcessId = a2;
  Process = 0;
  v33 = BampTempBoostCheck(a3);
  BampAcquireThrottlingLockExclusive();
  ThrottledProcessInformation = BampFindThrottledProcessInformation(v5);
  if ( ThrottledProcessInformation )
  {
    *a5 = ThrottledProcessInformation;
    ProcessUserSidString = 0;
LABEL_47:
    BampReleaseThrottlingLockExclusive();
    goto LABEL_48;
  }
  *(_WORD *)(v6 + 394) = 376;
  *(_QWORD *)(v6 + 400) = v6 + 408;
  *(_WORD *)(v6 + 392) = 0;
  ProcessUserSidString = BampQueryProcessUserSidString((struct _KPROCESS *)v5, (struct _UNICODE_STRING *)(v6 + 392));
  if ( ProcessUserSidString < 0 )
    goto LABEL_47;
  LOBYTE(v10) = 1;
  *(_DWORD *)(v6 + 300) = 0;
  v11 = 0;
  BamUserSettingsGet(v6 + 392, v6 + 88, v10, v6 + 300, 0);
  *(_DWORD *)(v6 + 376) = 0;
  *(_QWORD *)(v6 + 380) = 0;
  *(_DWORD *)(v6 + 388) = 0;
  BampGetShortNameFromIdentifier(v6 + 88, v39);
  BampReadProcessThrottlingSettings(v39, v12, v6 + 380);
  if ( ProcessId )
  {
    if ( PsLookupProcessByProcessId(ProcessId, &Process) >= 0 )
    {
      v13 = BampFindThrottledProcessInformation(Process);
      v7 = v13;
      if ( v13 )
      {
        v11 = 1;
        BampAcquireThrottledProcessLock(v13);
        if ( (*(_BYTE *)(v7 + 276) & 4) != 0 )
        {
          BampReleaseThrottledProcessLock(v7);
          v11 = 0;
          BampDereferenceThrottledProcessInformation((PVOID)v7);
          v7 = 0;
          if ( (unsigned int)dword_140007010 > 5 )
          {
            LODWORD(v35) = *(_DWORD *)(v5 + 464);
            v43 = 4;
            v42 = &v35;
            p_ProcessId = &ProcessId;
            v45 = 4;
            tlgWriteTransfer_EtwWriteTransfer(
              (__int64)&dword_140007010,
              (unsigned __int8 *)&word_140005766,
              0,
              0,
              4u,
              &v41);
          }
        }
      }
    }
  }
  v14 = 0;
  v40 = 0;
  if ( v7 )
  {
    if ( (*(_DWORD *)(v7 + 304) & 1) != 0 )
    {
      v14 = *(_OWORD *)(v7 + 304);
      v15 = *(_QWORD *)(v7 + 320);
    }
    else
    {
      v14 = *(_OWORD *)(v7 + 328);
      v15 = *(_QWORD *)(v7 + 344);
    }
  }
  else
  {
    v15 = v40;
  }
  BampAcquireThrottledProcessLock(v6);
  ProcessUserSidString = ExSubscribeWnfStateChange(
                           v6 + 112,
                           v6 + 120,
                           1,
                           0,
                           BampThrottledProcessWakeNotificationCallback,
                           v6);
  if ( ProcessUserSidString < 0 )
  {
    BampReleaseThrottledProcessLock(v6);
    if ( v11 )
      BampReleaseThrottledProcessLock(v7);
    goto LABEL_47;
  }
  *(_QWORD *)(v6 + 64) = v7;
  *(_OWORD *)(v6 + 328) = v14;
  *(_QWORD *)(v6 + 344) = v15;
  if ( v7 )
  {
    v16 = *(_QWORD **)(v7 + 40);
    if ( *v16 != v7 + 32 )
      __fastfail(3u);
    *(_QWORD *)(v6 + 48) = v7 + 32;
    *(_QWORD *)(v6 + 56) = v16;
    *v16 = v6 + 48;
    *(_QWORD *)(v7 + 40) = v6 + 48;
  }
  v17 = *(_DWORD *)(v6 + 280);
  *(_WORD *)(v6 + 276) |= 1u;
  *(_DWORD *)(v6 + 280) = v17 & 0xFFFFFFEF | (v33 != 0 ? 0x10 : 0);
  v18 = *(_QWORD *)(v6 + 296);
  *(_OWORD *)(v6 + 304) = *(_OWORD *)(v6 + 280);
  *(_QWORD *)(v6 + 320) = v18;
  BampReferenceThrottledProcessInformation(v6);
  ProcessId = (HANDLE)(*(_QWORD *)(v6 + 8) & (-1LL << (BYTE4(BampThrottledProcessTable) & 0x1F)));
  v19 = P;
  v20 = ((HIDWORD(BampThrottledProcessTable) >> 5) - 1)
      & (HIBYTE(ProcessId)
       + 37
       * (BYTE6(ProcessId)
        + 37
        * (BYTE5(ProcessId)
         + 37
         * (BYTE4(ProcessId)
          + 37
          * (BYTE3(ProcessId)
           + 37 * (BYTE2(ProcessId) + 37 * (BYTE1(ProcessId) + 37 * ((unsigned __int8)ProcessId + 11623883))))))));
  *(_QWORD *)v6 = *((_QWORD *)P + v20);
  v19[v20] = v6;
  v21 = (unsigned int)(2 * (HIDWORD(BampThrottledProcessTable) >> 5));
  LODWORD(BampThrottledProcessTable) = BampThrottledProcessTable + 1;
  if ( (unsigned int)BampThrottledProcessTable >= (unsigned int)v21 )
  {
    if ( (unsigned int)v21 < 4 )
      v21 = 4;
    v22 = (char *)BampAllocateForHashTable(8LL * (unsigned int)v21, 0);
    if ( v22 )
    {
      if ( (((_DWORD)v21 - 1) & (unsigned int)v21) != 0 )
      {
        v23 = -1;
        do
        {
          ++v23;
          LODWORD(v21) = (unsigned int)v21 >> 1;
        }
        while ( (_DWORD)v21 );
        v21 = (unsigned int)(1 << v23);
      }
      if ( (unsigned int)v21 > 0x4000000 )
        v21 = 0x4000000;
      v24 = (unsigned int)v21;
      if ( v22 > &v22[8 * v21] )
        v24 = 0;
      if ( v24 )
        memset64(v22, (unsigned __int64)&BampThrottledProcessTable + 1, (unsigned int)v24);
      v25 = BYTE4(BampThrottledProcessTable);
      v26 = 0;
      v27 = -1LL << (BYTE4(BampThrottledProcessTable) & 0x1F);
      if ( (BampThrottledProcessTable & 0xFFFFFFE000000000uLL) != 0 )
      {
        do
        {
          v28 = P;
          while ( 1 )
          {
            v29 = (_QWORD *)v28[v26];
            if ( ((unsigned __int8)v29 & 1) != 0 )
              break;
            v28[v26] = *v29;
            ProcessId = (HANDLE)(v27 & v29[1]);
            v30 = ((_DWORD)v21 - 1)
                & (HIBYTE(ProcessId)
                 + 37
                 * (BYTE6(ProcessId)
                  + 37
                  * (BYTE5(ProcessId)
                   + 37
                   * (BYTE4(ProcessId)
                    + 37
                    * (BYTE3(ProcessId)
                     + 37
                     * (BYTE2(ProcessId)
                      + 37 * (BYTE1(ProcessId) + 37 * ((unsigned int)(unsigned __int8)ProcessId + 11623883))))))));
            *v29 = *(_QWORD *)&v22[8 * v30];
            *(_QWORD *)&v22[8 * v30] = v29;
          }
          v25 = BYTE4(BampThrottledProcessTable);
          v26 = (unsigned int)(v26 + 1);
        }
        while ( (unsigned int)v26 < HIDWORD(BampThrottledProcessTable) >> 5 );
        v6 = v37;
      }
      v31 = P;
      P = v22;
      HIDWORD(BampThrottledProcessTable) = v25 & 0x1F | (32 * v21);
      if ( v31 )
        BampFreeForHashTable(v31, 0);
    }
  }
  BampAcquireThrottlingWorkerLock();
  BampQueueThrottledProcessActionItem(v6, 1, 0, 0);
  BampReleaseThrottlingWorkerLock();
  BampReleaseThrottledProcessLock(v6);
  if ( v11 )
    BampReleaseThrottledProcessLock(v7);
  BampReleaseThrottlingLockExclusive();
  BampReferenceThrottledProcessInformation(v6);
  ProcessUserSidString = 0;
  *v38 = v6;
LABEL_48:
  if ( v7 )
    BampDereferenceThrottledProcessInformation((PVOID)v7);
  if ( Process )
    ObfDereferenceObject(Process);
  return (unsigned int)ProcessUserSidString;
}

```

## disassembly

```asm
0x14001474c  mov     rax, rsp
0x14001474f  mov     [rax+18h], rbx
0x140014753  push    rbp
0x140014754  push    rsi
0x140014755  push    rdi
0x140014756  push    r12
0x140014758  push    r13
0x14001475a  push    r14
0x14001475c  push    r15
0x14001475e  lea     rbp, [rax-57h]
0x140014762  sub     rsp, 100h
0x140014769  movaps  xmmword ptr [rax-48h], xmm6
0x14001476d  movaps  xmmword ptr [rax-58h], xmm7
0x140014771  mov     rax, cs:__security_cookie
0x140014778  xor     rax, rsp
0x14001477b  mov     [rbp+4Fh+var_60], rax
0x14001477f  mov     r13, [rcx+8]
0x140014783  mov     rsi, rcx
0x140014786  mov     rdi, [rbp+4Fh+arg_20]
0x14001478a  xorps   xmm0, xmm0
0x14001478d  mov     [rsp+130h+var_E0], rcx
0x140014792  xor     r14d, r14d
0x140014795  mov     ecx, r8d
0x140014798  mov     qword ptr [rsp+130h+var_D8], rdi
0x14001479d  movups  [rsp+130h+var_D8+8], xmm0
0x1400147a2  mov     [rsp+130h+ProcessId], rdx
0x1400147a7  mov     [rsp+130h+Process], 0
0x1400147b0  call    BampTempBoostCheck
0x1400147b5  mov     byte ptr [rsp+130h+var_100], al
0x1400147b9  call    BampAcquireThrottlingLockExclusive
0x1400147be  mov     rcx, r13
0x1400147c1  call    BampFindThrottledProcessInformation
0x1400147c6  test    rax, rax
0x1400147c9  jz      short loc_1400147D5
0x1400147cb  mov     [rdi], rax
0x1400147ce  xor     edi, edi
0x1400147d0  jmp     loc_140014CB0
0x1400147d5  lea     rax, [rsi+198h]
0x1400147dc  mov     word ptr [rsi+18Ah], 178h
0x1400147e5  mov     [rsi+190h], rax
0x1400147ec  lea     r15, [rsi+188h]
0x1400147f3  xor     eax, eax
0x1400147f5  mov     rdx, r15
0x1400147f8  mov     rcx, r13
0x1400147fb  mov     [r15], ax
0x1400147ff  call    BampQueryProcessUserSidString
0x140014804  mov     edi, eax
0x140014806  test    eax, eax
0x140014808  js      loc_140014CB0
0x14001480e  lea     r9, [rsi+12Ch]
0x140014815  mov     [rsp+130h+var_110], r14
0x14001481a  mov     r8b, 1
0x14001481d  mov     [r9], r14d
0x140014820  lea     rdx, [rsi+58h]
0x140014824  mov     rcx, r15
0x140014827  xor     r12b, r12b
0x14001482a  call    BamUserSettingsGet
0x14001482f  xor     eax, eax
0x140014831  lea     rdi, [rsi+17Ch]
0x140014838  lea     r11, [rsi+178h]
0x14001483f  mov     [r11], eax
0x140014842  lea     rdx, [rsp+130h+var_D8+8]
0x140014847  mov     [rdi], rax
0x14001484a  lea     rcx, [rsi+58h]
0x14001484e  mov     [rdi+8], eax
0x140014851  call    BampGetShortNameFromIdentifier
0x140014856  mov     r8, rdi
0x140014859  lea     rcx, [rsp+130h+var_D8+8]
0x14001485e  mov     rdx, r11
0x140014861  call    BampReadProcessThrottlingSettings
0x140014866  mov     rdi, [rsp+130h+ProcessId]
0x14001486b  mov     ebx, 4
0x140014870  test    rdi, rdi
0x140014873  jz      loc_14001492F
0x140014879  lea     rdx, [rsp+130h+Process]; Process
0x14001487e  mov     rcx, rdi; ProcessId
0x140014881  call    cs:__imp_PsLookupProcessByProcessId
0x140014888  nop     dword ptr [rax+rax+00h]
0x14001488d  test    eax, eax
0x14001488f  js      loc_14001492F
0x140014895  mov     rcx, [rsp+130h+Process]
0x14001489a  call    BampFindThrottledProcessInformation
0x14001489f  mov     r14, rax
0x1400148a2  test    rax, rax
0x1400148a5  jz      loc_14001492F
0x1400148ab  mov     rcx, rax
0x1400148ae  mov     r12b, 1
0x1400148b1  call    BampAcquireThrottledProcessLock
0x1400148b6  test    [r14+114h], bl
0x1400148bd  jz      short loc_14001492F
0x1400148bf  mov     rcx, r14
0x1400148c2  call    BampReleaseThrottledProcessLock
0x1400148c7  mov     rcx, r14; P
0x1400148ca  xor     r12b, r12b
0x1400148cd  call    BampDereferenceThrottledProcessInformation
0x1400148d2  mov     eax, cs:dword_140007010
0x1400148d8  xor     r14d, r14d
0x1400148db  cmp     eax, 5
0x1400148de  jbe     short loc_14001492F
0x1400148e0  mov     eax, [r13+1D0h]
0x1400148e7  lea     rdx, word_140005766
0x1400148ee  mov     dword ptr [rsp+130h+var_F0], eax
0x1400148f2  lea     rcx, dword_140007010
0x1400148f9  lea     rax, [rsp+130h+var_F0]
0x1400148fe  mov     [rbp+4Fh+var_78], rbx
0x140014902  mov     [rbp+4Fh+var_80], rax
0x140014906  xor     r9d, r9d
0x140014909  lea     rax, [rsp+130h+ProcessId]
0x14001490e  mov     dword ptr [rsp+130h+ProcessId], edi
0x140014912  mov     [rbp+4Fh+var_70], rax
0x140014916  xor     r8d, r8d
0x140014919  lea     rax, [rbp+4Fh+var_A0]
0x14001491d  mov     [rbp+4Fh+var_68], rbx
0x140014921  mov     qword ptr [rsp+130h+var_108], rax
0x140014926  mov     dword ptr [rsp+130h+var_110], ebx
0x14001492a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001492f  xor     eax, eax
0x140014931  xorps   xmm7, xmm7
0x140014934  mov     [rbp+4Fh+var_B0], rax
0x140014938  lea     r13d, [rax+1]
0x14001493c  test    r14, r14
0x14001493f  jz      short loc_140014973
0x140014941  mov     eax, [r14+130h]
0x140014948  test    r13b, al
0x14001494b  jz      short loc_140014960
0x14001494d  movups  xmm7, xmmword ptr [r14+130h]
0x140014955  movsd   xmm6, qword ptr [r14+140h]
0x14001495e  jmp     short loc_140014978
0x140014960  movups  xmm7, xmmword ptr [r14+148h]
0x140014968  movsd   xmm6, qword ptr [r14+158h]
0x140014971  jmp     short loc_140014978
0x140014973  movsd   xmm6, [rbp+4Fh+var_B0]
0x140014978  mov     rcx, rsi
0x14001497b  call    BampAcquireThrottledProcessLock
0x140014980  lea     rax, BampThrottledProcessWakeNotificationCallback
0x140014987  mov     qword ptr [rsp+130h+var_108], rsi
0x14001498c  lea     rdx, [rsi+78h]
0x140014990  mov     [rsp+130h+var_110], rax
0x140014995  lea     rcx, [rsi+70h]
0x140014999  xor     r9d, r9d
0x14001499c  mov     r8d, r13d
0x14001499f  call    cs:__imp_ExSubscribeWnfStateChange
0x1400149a6  nop     dword ptr [rax+rax+00h]
0x1400149ab  mov     edi, eax
0x1400149ad  test    eax, eax
0x1400149af  js      loc_140014C9B
0x1400149b5  mov     [rsi+40h], r14
0x1400149b9  movups  xmmword ptr [rsi+148h], xmm7
0x1400149c0  movsd   qword ptr [rsi+158h], xmm6
0x1400149c8  test    r14, r14
0x1400149cb  jz      short loc_1400149F3
0x1400149cd  lea     rcx, [r14+20h]
0x1400149d1  mov     rdx, [rcx+8]
0x1400149d5  cmp     [rdx], rcx
0x1400149d8  jz      short loc_1400149E1
0x1400149da  mov     ecx, 3
0x1400149df  int     29h; Win8: RtlFailFast(ecx)
0x1400149e1  lea     rax, [rsi+30h]
0x1400149e5  mov     [rax], rcx
0x1400149e8  mov     [rax+8], rdx
0x1400149ec  mov     [rdx], rax
0x1400149ef  mov     [rcx+8], rax
0x1400149f3  mov     eax, [rsi+118h]
0x1400149f9  neg     byte ptr [rsp+130h+var_100]
0x1400149fd  sbb     ecx, ecx
0x1400149ff  or      [rsi+114h], r13w
0x140014a07  and     ecx, 10h
0x140014a0a  and     eax, 0FFFFFFEFh
0x140014a0d  or      ecx, eax
0x140014a0f  mov     [rsi+118h], ecx
0x140014a15  mov     rcx, rsi
0x140014a18  movups  xmm0, xmmword ptr [rsi+118h]
0x140014a1f  movsd   xmm1, qword ptr [rsi+128h]
0x140014a27  movups  xmmword ptr [rsi+130h], xmm0
0x140014a2e  movsd   qword ptr [rsi+140h], xmm1
0x140014a36  call    BampReferenceThrottledProcessInformation
0x140014a3b  mov     edi, dword ptr cs:BampThrottledProcessTable+4
0x140014a41  lea     r8, [rsp+130h+ProcessId]
0x140014a46  mov     ecx, edi
0x140014a48  or      r15, 0FFFFFFFFFFFFFFFFh
0x140014a4c  and     ecx, 1Fh
0x140014a4f  shr     edi, 5
0x140014a52  mov     rax, r15
0x140014a55  sub     edi, r13d
0x140014a58  shl     rax, cl
0x140014a5b  and     rax, [rsi+8]
0x140014a5f  mov     [rsp+130h+ProcessId], rax
0x140014a64  movzx   eax, byte ptr [r8]
0x140014a68  add     eax, 0B15DCBh
0x140014a6d  imul    ecx, eax, 25h ; '%'
0x140014a70  movzx   eax, byte ptr [r8+1]
0x140014a75  add     ecx, eax
0x140014a77  movzx   eax, byte ptr [r8+2]
0x140014a7c  imul    edx, ecx, 25h ; '%'
0x140014a7f  add     edx, eax
0x140014a81  movzx   eax, byte ptr [r8+3]
0x140014a86  imul    ecx, edx, 25h ; '%'
0x140014a89  add     ecx, eax
0x140014a8b  movzx   eax, byte ptr [r8+4]
0x140014a90  imul    edx, ecx, 25h ; '%'
0x140014a93  add     edx, eax
0x140014a95  movzx   eax, byte ptr [r8+5]
0x140014a9a  imul    ecx, edx, 25h ; '%'
0x140014a9d  add     ecx, eax
0x140014a9f  movzx   eax, byte ptr [r8+6]
0x140014aa4  imul    edx, ecx, 25h ; '%'
0x140014aa7  mov     rcx, cs:P
0x140014aae  add     edx, eax
0x140014ab0  movzx   eax, byte ptr [r8+7]
0x140014ab5  imul    edx, 25h ; '%'
0x140014ab8  add     edx, eax
0x140014aba  mov     eax, edi
0x140014abc  and     rdx, rax
0x140014abf  mov     rax, [rcx+rdx*8]
0x140014ac3  mov     [rsi], rax
0x140014ac6  mov     [rcx+rdx*8], rsi
0x140014aca  mov     eax, dword ptr cs:BampThrottledProcessTable
0x140014ad0  mov     ebx, dword ptr cs:BampThrottledProcessTable+4
0x140014ad6  inc     eax
0x140014ad8  shr     ebx, 5
0x140014adb  add     ebx, ebx
0x140014add  mov     dword ptr cs:BampThrottledProcessTable, eax
0x140014ae3  cmp     dword ptr cs:BampThrottledProcessTable, ebx
0x140014ae9  jb      loc_140014C52
0x140014aef  lea     eax, [r15+5]
0x140014af3  cmp     ebx, eax
0x140014af5  cmovb   ebx, eax
0x140014af8  xor     edx, edx
0x140014afa  mov     ecx, ebx
0x140014afc  shl     rcx, 3
0x140014b00  call    BampAllocateForHashTable
0x140014b05  mov     r8, rax
0x140014b08  test    rax, rax
0x140014b0b  jz      loc_140014C52
0x140014b11  lea     ecx, [rbx-1]
0x140014b14  test    ebx, ecx
0x140014b16  jz      short loc_140014B2B
0x140014b18  or      ecx, 0FFFFFFFFh
0x140014b1b  test    ebx, ebx
0x140014b1d  jz      short loc_140014B26
0x140014b1f  add     ecx, r13d
0x140014b22  shr     ebx, 1
0x140014b24  jnz     short loc_140014B1F
0x140014b26  mov     ebx, r13d
0x140014b29  shl     ebx, cl
0x140014b2b  mov     eax, 4000000h
0x140014b30  cmp     ebx, eax
0x140014b32  cmova   ebx, eax
0x140014b35  xor     ecx, ecx
0x140014b37  lea     rax, BampThrottledProcessTable
0x140014b3e  mov     r9d, ebx
0x140014b41  or      rax, r13
0x140014b44  lea     rdx, [r8+rbx*8]
0x140014b48  cmp     r8, rdx
0x140014b4b  cmova   r9d, ecx
0x140014b4f  test    r9, r9
0x140014b52  jz      short loc_140014B5D
0x140014b54  mov     rdi, r8
0x140014b57  mov     ecx, r9d
0x140014b5a  rep stosq
0x140014b5d  mov     edx, dword ptr cs:BampThrottledProcessTable+4
0x140014b63  xor     edi, edi
0x140014b65  mov     ecx, edx
0x140014b67  and     ecx, 1Fh
0x140014b6a  shl     r15, cl
0x140014b6d  test    edx, 0FFFFFFE0h
0x140014b73  jbe     loc_140014C2A
0x140014b79  lea     esi, [rdi+1]
0x140014b7c  mov     r11, cs:P
0x140014b83  mov     r9, [r11+rdi*8]
0x140014b87  test    sil, r9b
0x140014b8a  jnz     short loc_140014C0A
0x140014b8c  mov     rax, [r9]
0x140014b8f  lea     r13, [rsp+130h+ProcessId]
0x140014b94  mov     [r11+rdi*8], rax
0x140014b98  mov     rax, [r9+8]
0x140014b9c  and     rax, r15
0x140014b9f  mov     [rsp+130h+ProcessId], rax
0x140014ba4  movzx   eax, byte ptr [r13+0]
0x140014ba9  add     eax, 0B15DCBh
0x140014bae  imul    ecx, eax, 25h ; '%'
0x140014bb1  movzx   eax, byte ptr [r13+1]
0x140014bb6  add     ecx, eax
0x140014bb8  movzx   eax, byte ptr [r13+2]
0x140014bbd  imul    edx, ecx, 25h ; '%'
0x140014bc0  add     edx, eax
0x140014bc2  movzx   eax, byte ptr [r13+3]
0x140014bc7  imul    ecx, edx, 25h ; '%'
0x140014bca  add     ecx, eax
0x140014bcc  movzx   eax, byte ptr [r13+4]
0x140014bd1  imul    edx, ecx, 25h ; '%'
0x140014bd4  add     edx, eax
0x140014bd6  movzx   eax, byte ptr [r13+5]
0x140014bdb  imul    ecx, edx, 25h ; '%'
0x140014bde  add     ecx, eax
0x140014be0  movzx   eax, byte ptr [r13+6]
0x140014be5  imul    edx, ecx, 25h ; '%'
0x140014be8  lea     ecx, [rbx-1]
0x140014beb  add     edx, eax
0x140014bed  movzx   eax, byte ptr [r13+7]
  ... truncated ...
```

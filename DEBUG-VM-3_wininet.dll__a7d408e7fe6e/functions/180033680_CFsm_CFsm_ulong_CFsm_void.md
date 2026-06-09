# CFsm::CFsm(ulong (*)(CFsm *),void *)

- ea: `0x180033680`
- end: `0x1800339a1`
- name: `??0CFsm@@QEAA@P6AKPEAV0@@ZPEAX@Z`
- size: `801`
- prototype: `CFsm *__fastcall(CFsm *__hidden this, unsigned int (*)(struct CFsm *), void *)`
- caller_count: `57`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180031150`
- `0x180034250`
- `0x180037ff0`
- `0x180038bc4`
- `0x180039228`
- `0x180039bdc`
- `0x18003a8f0`
- `0x18004c490`
- `0x18004e73c`
- `0x180053934`
- `0x18005a608`
- `0x18005cb00`
- `0x18007a218`
- `0x18008cce8`
- `0x1800bae30`
- `0x1800bbc70`
- `0x1800cc948`
- `0x1800faa40`
- `0x1800faed4`
- `0x1800fb250`
- `0x1800ffdd0`
- `0x180105580`
- `0x180107a30`
- `0x18010aeb0`
- `0x18010d6f0`
- `0x180116114`
- `0x180122ca4`
- `0x18012b148`
- `0x180135a1c`
- `0x1801396d0`
- `0x18016390c`
- `0x180163d10`
- `0x180165758`
- `0x1801657e4`
- `0x180165870`
- `0x18016e4e4`
- `0x18016e5a0`
- `0x18016e6c8`
- `0x18016e768`
- `0x18016e808`
- `0x18016e8ac`
- `0x18016e958`
- `0x18016e9f8`
- `0x18016eac4`
- `0x1801719cc`
- `0x180172b34`
- `0x1801730cc`
- `0x1801731c4`
- `0x180181298`
- `0x180181990`

## callees

- `0x180033680`
- `0x1800d2e04`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801e7088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033750`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003388d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033750`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003388d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003371d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003371d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003381e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003381e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800338ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033944`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800338ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033944`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003373c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003373c`
- `ntdll!RtlGetLastNtStatus` at `0x18003382f`
- `ntdll!RtlGetLastNtStatus` at `0x18003382f`

## pseudocode

```c
CFsm *__fastcall CFsm::CFsm(CFsm *this, unsigned int (*a2)(struct CFsm *), void *a3)
{
  DWORD LastError; // eax
  DWORD v7; // esi
  _QWORD *Value; // rdi
  __int64 v9; // rcx
  __int64 v11; // rdi
  DWORD v12; // eax
  DWORD CurrentThreadId; // eax

  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &CFsm::`vftable';
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_q(1032, 13, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, this);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 10) = 12004;
  *((_DWORD *)this + 20) = 12004;
  *(_QWORD *)((char *)this + 84) = -1;
  *((_DWORD *)this + 23) = -1;
  *((_QWORD *)this + 12) = a2;
  *((_QWORD *)this + 13) = a3;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = -1;
  *(_QWORD *)((char *)this + 132) = 0;
  *(_QWORD *)((char *)this + 140) = 0;
  *(_QWORD *)((char *)this + 148) = 0;
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 20) = 0;
  *(_QWORD *)((char *)this + 188) = 0;
  LastError = GetLastError();
  v7 = LastError;
  if ( qword_180269EA8 && LastError && LastError != 997 && LastError != 12150 && LastError != 12028 && LastError != 122 )
  {
    v11 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
    GetSystemTimeAsFileTime((LPFILETIME)(v11 + qword_180269EA8));
    *(_DWORD *)(v11 + qword_180269EA8 + 8) = v7;
    *(_DWORD *)(v11 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  Value = TlsGetValue(InternetTlsIndex);
  if ( !Value )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(1037, 22, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, CurrentThreadId);
    }
    Value = (_QWORD *)InternetCreateThreadInfo(1);
    if ( !Value && (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      WPP_SF_(1037, 23, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids);
      SetLastError(v7);
      *((_QWORD *)this + 6) = 0;
      goto LABEL_23;
    }
  }
  SetLastError(v7);
  *((_QWORD *)this + 6) = Value;
  if ( !Value )
  {
LABEL_23:
    *((_DWORD *)this + 10) = 12004;
    goto LABEL_10;
  }
  *((_QWORD *)this + 7) = Value[5];
  *((_QWORD *)this + 8) = Value[6];
  *((_QWORD *)this + 9) = Value[7];
  *((_QWORD *)this + 10) = *((unsigned int *)Value + 19);
  *((_DWORD *)this + 22) = 4;
  *((_DWORD *)this + 10) = 0;
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    WPP_SF_qss(
      1033,
      17,
      (unsigned int)&WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids,
      (_DWORD)this,
      (__int64)word_180222338,
      (__int64)word_180222338);
  v9 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 4) = *(_QWORD *)(v9 + 80);
  *(_QWORD *)(v9 + 80) = this;
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
  {
    WPP_SF_q(1033, 18, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, *((_QWORD *)this + 4));
    if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    {
      v12 = GetCurrentThreadId();
      WPP_SF_qD(1033, 19, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, this, v12);
      if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
        WPP_SF_(1033, 20, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
    }
  }
LABEL_10:
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 14, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
  return this;
}

```

## disassembly

```asm
0x180033680  push    rbx
0x180033682  push    rbp
0x180033683  push    rsi
0x180033684  push    rdi
0x180033685  sub     rsp, 38h
0x180033689  xor     ebp, ebp
0x18003368b  lea     rax, ??_7CFsm@@6B@; const CFsm::`vftable'
0x180033692  mov     [rcx+18h], ebp
0x180033695  mov     rdi, r8
0x180033698  mov     [rcx], rax
0x18003369b  mov     rsi, rdx
0x18003369e  mov     rbx, rcx
0x1800336a1  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800336a8  jnz     loc_180033983
0x1800336ae  mov     [rbx+20h], rbp
0x1800336b2  mov     [rbx+38h], rbp
0x1800336b6  mov     [rbx+40h], rbp
0x1800336ba  mov     [rbx+48h], rbp
0x1800336be  mov     dword ptr [rbx+28h], 2EE4h
0x1800336c5  mov     dword ptr [rbx+50h], 2EE4h
0x1800336cc  mov     qword ptr [rbx+54h], 0FFFFFFFFFFFFFFFFh
0x1800336d4  mov     dword ptr [rbx+5Ch], 0FFFFFFFFh
0x1800336db  mov     [rbx+60h], rsi
0x1800336df  mov     [rbx+68h], rdi
0x1800336e3  mov     [rbx+70h], ebp
0x1800336e6  mov     [rbx+78h], rbp
0x1800336ea  mov     dword ptr [rbx+80h], 0FFFFFFFFh
0x1800336f4  mov     [rbx+84h], rbp
0x1800336fb  mov     [rbx+8Ch], rbp
0x180033702  mov     [rbx+94h], rbp
0x180033709  mov     [rbx+0A8h], ebp
0x18003370f  mov     [rbx+0A0h], rbp
0x180033716  mov     [rbx+0BCh], rbp
0x18003371d  call    cs:__imp_GetLastError
0x180033723  cmp     cs:qword_180269EA8, rbp
0x18003372a  mov     esi, eax
0x18003372c  jz      short loc_180033736
0x18003372e  test    eax, eax
0x180033730  jnz     loc_1800337D1
0x180033736  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x18003373c  call    cs:__imp_TlsGetValue
0x180033742  mov     rdi, rax
0x180033745  test    rax, rax
0x180033748  jz      loc_180033845
0x18003374e  mov     ecx, esi; dwErrCode
0x180033750  call    cs:__imp_SetLastError
0x180033756  mov     [rbx+30h], rdi
0x18003375a  test    rdi, rdi
0x18003375d  jz      loc_180033897
0x180033763  mov     rax, [rdi+28h]
0x180033767  mov     [rbx+38h], rax
0x18003376b  mov     rax, [rdi+30h]
0x18003376f  mov     [rbx+40h], rax
0x180033773  mov     rax, [rdi+38h]
0x180033777  mov     [rbx+48h], rax
0x18003377b  mov     eax, [rdi+4Ch]
0x18003377e  mov     [rbx+50h], eax
0x180033781  mov     [rbx+54h], ebp
0x180033784  mov     dword ptr [rbx+58h], 4
0x18003378b  mov     [rbx+28h], ebp
0x18003378e  test    byte ptr cs:xmmword_180266B60+1, 2
0x180033795  jnz     loc_180033915
0x18003379b  mov     rcx, [rbx+30h]
0x18003379f  mov     rax, [rcx+50h]
0x1800337a3  mov     [rbx+20h], rax
0x1800337a7  mov     [rcx+50h], rbx
0x1800337ab  test    byte ptr cs:xmmword_180266B60+1, 2
0x1800337b2  jnz     loc_1800338A3
0x1800337b8  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800337bf  jnz     loc_180033968
0x1800337c5  mov     rax, rbx
0x1800337c8  add     rsp, 38h
0x1800337cc  pop     rdi
0x1800337cd  pop     rsi
0x1800337ce  pop     rbp
0x1800337cf  pop     rbx
0x1800337d0  retn
0x1800337d1  cmp     esi, 3E5h
0x1800337d7  jz      loc_180033736
0x1800337dd  cmp     esi, 2F76h
0x1800337e3  jz      loc_180033736
0x1800337e9  cmp     esi, 2EFCh
0x1800337ef  jz      loc_180033736
0x1800337f5  cmp     esi, 7Ah ; 'z'
0x1800337f8  jz      loc_180033736
0x1800337fe  mov     eax, 1
0x180033803  lock xadd cs:dword_180269EA4, eax
0x18003380b  mov     rcx, cs:qword_180269EA8
0x180033812  inc     eax
0x180033814  movzx   edi, al
0x180033817  shl     rdi, 4
0x18003381b  add     rcx, rdi; lpSystemTimeAsFileTime
0x18003381e  call    cs:__imp_GetSystemTimeAsFileTime
0x180033824  mov     rax, cs:qword_180269EA8
0x18003382b  mov     [rdi+rax+8], esi
0x18003382f  call    cs:__imp_RtlGetLastNtStatus
0x180033835  mov     rcx, cs:qword_180269EA8
0x18003383c  mov     [rdi+rcx+0Ch], eax
0x180033840  jmp     loc_180033736
0x180033845  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18003384c  jnz     loc_180033944
0x180033852  mov     ecx, 1
0x180033857  call    InternetCreateThreadInfo
0x18003385c  mov     rdi, rax
0x18003385f  test    rax, rax
0x180033862  jnz     loc_18003374E
0x180033868  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18003386f  jz      loc_18003374E
0x180033875  mov     edx, 17h
0x18003387a  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x180033881  mov     ecx, 40Dh
0x180033886  call    WPP_SF_
0x18003388b  mov     ecx, esi; dwErrCode
0x18003388d  call    cs:__imp_SetLastError
0x180033893  mov     [rbx+30h], rdi
0x180033897  mov     dword ptr [rbx+28h], 2EE4h
0x18003389e  jmp     loc_1800337B8
0x1800338a3  mov     r9, [rbx+20h]
0x1800338a7  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800338ae  mov     edx, 12h
0x1800338b3  mov     ecx, 409h
0x1800338b8  call    WPP_SF_q
0x1800338bd  test    byte ptr cs:xmmword_180266B60+1, 2
0x1800338c4  jz      loc_1800337B8
0x1800338ca  call    cs:__imp_GetCurrentThreadId
0x1800338d0  mov     edx, 13h
0x1800338d5  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800338dc  mov     ecx, 409h
0x1800338e1  mov     dword ptr [rsp+58h+var_38], eax
0x1800338e5  mov     r9, rbx
0x1800338e8  call    WPP_SF_qD
0x1800338ed  test    byte ptr cs:xmmword_180266B60+1, 2
0x1800338f4  jz      loc_1800337B8
0x1800338fa  mov     edx, 14h
0x1800338ff  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x180033906  mov     ecx, 409h
0x18003390b  call    WPP_SF_
0x180033910  jmp     loc_1800337B8
0x180033915  lea     rax, word_180222338
0x18003391c  mov     edx, 11h
0x180033921  mov     [rsp+58h+var_30], rax
0x180033926  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18003392d  mov     ecx, 409h
0x180033932  mov     [rsp+58h+var_38], rax
0x180033937  mov     r9, rbx
0x18003393a  call    WPP_SF_qss
0x18003393f  jmp     loc_18003379B
0x180033944  call    cs:__imp_GetCurrentThreadId
0x18003394a  mov     edx, 16h
0x18003394f  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x180033956  mov     r9d, eax
0x180033959  mov     ecx, 40Dh
0x18003395e  call    WPP_SF_d
0x180033963  jmp     loc_180033852
0x180033968  mov     edx, 0Eh
0x18003396d  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x180033974  mov     ecx, 408h
0x180033979  call    WPP_SF_
0x18003397e  jmp     loc_1800337C5
0x180033983  mov     edx, 0Dh
0x180033988  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18003398f  mov     ecx, 408h
0x180033994  mov     r9, rbx
0x180033997  call    WPP_SF_q
0x18003399c  jmp     loc_1800336AE
```

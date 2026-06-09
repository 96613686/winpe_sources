# CReader::InitializeThreadpool(void)

- ea: `0x180017c60`
- end: `0x180017da7`
- name: `?InitializeThreadpool@CReader@@IEAAKXZ`
- size: `327`
- prototype: `__int64 __fastcall(CReader *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002d870`

## callees

- `0x1800044e0`
- `0x18000d7a0`
- `0x180017c60`
- `0x18002d62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ce3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017d0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017d2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017d0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017d2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180017cd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180017cd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CReader::InitializeThreadpool(CReader *this)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD LastError; // edi
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_TIMER v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  char v9; // [rsp+30h] [rbp+8h] BYREF

  CLockWrite::CLockWrite((CLockWrite *)&v9, (CReader *)((char *)this + 56));
  *((_DWORD *)this + 171) = 1;
  *((_DWORD *)this + 156) = 3;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_DWORD *)this + 170) = 0;
  *((_DWORD *)this + 172) = 72;
  *((_DWORD *)this + 11) = 1;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 87) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup
    && (*((_QWORD *)this + 80) = ThreadpoolCleanupGroup,
        *((_QWORD *)this + 81) = 0,
        ThreadpoolTimer = CreateThreadpoolTimer(
                            CReader::PowerDownTimeoutCallback,
                            this,
                            (PTP_CALLBACK_ENVIRON)((char *)this + 624)),
        (*((_QWORD *)this + 88) = ThreadpoolTimer) != 0)
    && (v5 = CreateThreadpoolTimer(
               CReader::TransactionTimeoutCallback,
               this,
               (PTP_CALLBACK_ENVIRON)((char *)this + 624)),
        (*((_QWORD *)this + 89) = v5) != 0) )
  {
    LastError = 0;
    v6 = -10000000LL * (int)g_dwCardDisconnectPowerDownDelay;
    *((_DWORD *)this + 180) = v6;
    v7 = -10000000LL * (int)g_dwTransactionTimeoutDelay;
    *((_DWORD *)this + 181) = HIDWORD(v6);
    *((_QWORD *)this + 91) = v7;
  }
  else
  {
    LastError = GetLastError();
  }
  CLockWrite::~CLockWrite((CLockWrite *)&v9);
  if ( LastError )
    CReader::CloseThreadpool((PTP_CLEANUP_GROUP *)this);
  return LastError;
}

```

## disassembly

```asm
0x180017c60  mov     [rsp+arg_8], rbx
0x180017c65  push    rdi
0x180017c66  sub     rsp, 20h
0x180017c6a  mov     rbx, rcx
0x180017c6d  lea     rdx, [rcx+38h]; struct CAccessLock *
0x180017c71  lea     rcx, [rsp+28h+arg_0]; this
0x180017c76  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180017c7b  lea     rdi, [rbx+270h]
0x180017c82  mov     eax, 1
0x180017c87  mov     [rdi+3Ch], eax
0x180017c8a  mov     dword ptr [rdi], 3
0x180017c90  mov     qword ptr [rdi+8], 0
0x180017c98  mov     qword ptr [rdi+10h], 0
0x180017ca0  mov     qword ptr [rdi+18h], 0
0x180017ca8  mov     qword ptr [rdi+20h], 0
0x180017cb0  mov     qword ptr [rdi+28h], 0
0x180017cb8  mov     qword ptr [rdi+30h], 0
0x180017cc0  mov     dword ptr [rdi+38h], 0
0x180017cc7  mov     dword ptr [rdi+40h], 48h ; 'H'
0x180017cce  mov     [rbx+2Ch], eax
0x180017cd1  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180017cd7  mov     [rbx+2B8h], rax
0x180017cde  test    rax, rax
0x180017ce1  jnz     short loc_180017CF0
0x180017ce3  call    cs:__imp_GetLastError
0x180017ce9  mov     edi, eax
0x180017ceb  jmp     loc_180017D84
0x180017cf0  mov     r8, rdi; pcbe
0x180017cf3  mov     [rbx+280h], rax
0x180017cfa  mov     rdx, rbx; pv
0x180017cfd  mov     qword ptr [rbx+288h], 0
0x180017d08  lea     rcx, ?PowerDownTimeoutCallback@CReader@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017d0f  call    cs:__imp_CreateThreadpoolTimer
0x180017d15  mov     [rbx+2C0h], rax
0x180017d1c  test    rax, rax
0x180017d1f  jz      short loc_180017CE3
0x180017d21  mov     r8, rdi; pcbe
0x180017d24  lea     rcx, ?TransactionTimeoutCallback@CReader@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017d2b  mov     rdx, rbx; pv
0x180017d2e  call    cs:__imp_CreateThreadpoolTimer
0x180017d34  mov     [rbx+2C8h], rax
0x180017d3b  test    rax, rax
0x180017d3e  jz      short loc_180017CE3
0x180017d40  movsxd  rax, cs:?g_dwCardDisconnectPowerDownDelay@@3KA; ulong g_dwCardDisconnectPowerDownDelay
0x180017d47  xor     edi, edi
0x180017d49  imul    rax, 0FFFFFFFFFF676980h
0x180017d50  mov     rcx, rax
0x180017d53  mov     [rbx+2D0h], eax
0x180017d59  movsxd  rax, cs:?g_dwTransactionTimeoutDelay@@3KA; ulong g_dwTransactionTimeoutDelay
0x180017d60  imul    rax, 0FFFFFFFFFF676980h
0x180017d67  shr     rcx, 20h
0x180017d6b  mov     [rbx+2D4h], ecx
0x180017d71  mov     rcx, rax
0x180017d74  shr     rcx, 20h
0x180017d78  mov     [rbx+2DCh], ecx
0x180017d7e  mov     [rbx+2D8h], eax
0x180017d84  lea     rcx, [rsp+28h+arg_0]; this
0x180017d89  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180017d8e  test    edi, edi
0x180017d90  jz      short loc_180017D9A
0x180017d92  mov     rcx, rbx; this
0x180017d95  call    ?CloseThreadpool@CReader@@IEAAXXZ; CReader::CloseThreadpool(void)
0x180017d9a  mov     rbx, [rsp+28h+arg_8]
0x180017d9f  mov     eax, edi
0x180017da1  add     rsp, 20h
0x180017da5  pop     rdi
0x180017da6  retn
```

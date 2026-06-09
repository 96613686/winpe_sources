# UbpmHardeningListRemove

- ea: `0x18002702c`
- end: `0x180027193`
- name: `UbpmHardeningListRemove`
- size: `359`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180001f40`
- `0x180012b70`

## callees

- `0x18000fbf0`
- `0x18002702c`
- `0x18002719c`
- `0x180035184`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180027096`
- `msvcrt!_wcsicmp` at `0x180027096`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027055`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027055`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800270d2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027120`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800270d2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027120`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027061`

## pseudocode

```c
void __fastcall UbpmHardeningListRemove(wchar_t *String2, __int64 a2)
{
  DWORD CurrentThreadId; // eax
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v6; // r14
  unsigned __int8 v7; // si
  int v8; // eax
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *Blink; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9

  if ( String2 && a2 )
  {
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    CurrentThreadId = GetCurrentThreadId();
    Flink = g_leTaskHostHardeningListHead.Flink;
    v6 = &g_leTaskHostHardeningListHead;
    dword_180050018 = CurrentThreadId;
    v7 = 0;
LABEL_4:
    if ( v7 >= 2u )
    {
      dword_180050018 = 0;
      RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    }
    else
    {
      while ( 1 )
      {
        if ( Flink == v6 )
        {
          Flink = g_leNonHostHardeningListHead.Flink;
          v6 = &g_leNonHostHardeningListHead;
          ++v7;
          goto LABEL_4;
        }
        v8 = _wcsicmp((const wchar_t *)Flink[1].Flink, String2);
        v9 = Flink->Flink;
        if ( !v8 )
          break;
        Flink = Flink->Flink;
      }
      if ( v9->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
        __fastfail(3u);
      Blink->Flink = v9;
      v9->Blink = Blink;
      Flink->Blink = Flink;
      Flink->Flink = Flink;
      dword_180050018 = 0;
      RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
      UBPM_MIDL_user_free(Flink, v11, v12, v13);
      if ( *(_BYTE *)(a2 + 49) )
        UbpmUpdateConsumerSidCache(*(PCWSTR *)(a2 + 56), *(const WCHAR **)(a2 + 64), *(unsigned int *)(a2 + 72), 0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, String2);
    }
  }
}

```

## disassembly

```asm
0x18002702c  test    rcx, rcx
0x18002702f  jz      locret_1800270E8
0x180027035  push    rbx
0x180027036  push    rbp
0x180027037  push    rsi
0x180027038  push    rdi
0x180027039  push    r14
0x18002703b  sub     rsp, 20h
0x18002703f  mov     rdi, rdx
0x180027042  mov     rbp, rcx
0x180027045  test    rdx, rdx
0x180027048  jz      loc_1800270DE
0x18002704e  lea     rcx, g_TaskHostContextListLock
0x180027055  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002705c  nop     dword ptr [rax+rax+00h]
0x180027061  call    cs:__imp_GetCurrentThreadId
0x180027068  nop     dword ptr [rax+rax+00h]
0x18002706d  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180027074  lea     r14, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18002707b  mov     cs:dword_180050018, eax
0x180027081  xor     sil, sil
0x180027084  cmp     sil, 2
0x180027088  jnb     short loc_1800270C1
0x18002708a  cmp     rbx, r14
0x18002708d  jz      short loc_1800270AE
0x18002708f  mov     rcx, [rbx+10h]; String1
0x180027093  mov     rdx, rbp; String2
0x180027096  call    cs:__imp__wcsicmp
0x18002709d  nop     dword ptr [rax+rax+00h]
0x1800270a2  mov     rcx, [rbx]
0x1800270a5  test    eax, eax
0x1800270a7  jz      short loc_1800270EA
0x1800270a9  mov     rbx, rcx
0x1800270ac  jmp     short loc_18002708A
0x1800270ae  mov     rbx, cs:?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x1800270b5  lea     r14, ?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x1800270bc  inc     sil
0x1800270bf  jmp     short loc_180027084
0x1800270c1  lea     rcx, g_TaskHostContextListLock
0x1800270c8  mov     cs:dword_180050018, 0
0x1800270d2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800270d9  nop     dword ptr [rax+rax+00h]
0x1800270de  add     rsp, 20h
0x1800270e2  pop     r14
0x1800270e4  pop     rdi
0x1800270e5  pop     rsi
0x1800270e6  pop     rbp
0x1800270e7  pop     rbx
0x1800270e8  retn
0x1800270ea  cmp     [rcx+8], rbx
0x1800270ee  jnz     loc_18002718C
0x1800270f4  mov     rax, [rbx+8]
0x1800270f8  cmp     [rax], rbx
0x1800270fb  jnz     loc_18002718C
0x180027101  mov     [rax], rcx
0x180027104  mov     [rcx+8], rax
0x180027108  lea     rcx, g_TaskHostContextListLock
0x18002710f  mov     [rbx+8], rbx
0x180027113  mov     [rbx], rbx
0x180027116  mov     cs:dword_180050018, 0
0x180027120  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180027127  nop     dword ptr [rax+rax+00h]
0x18002712c  mov     rcx, rbx
0x18002712f  call    UBPM_MIDL_user_free
0x180027134  cmp     byte ptr [rdi+31h], 0
0x180027138  jz      short loc_18002714E
0x18002713a  mov     r8d, [rdi+48h]
0x18002713e  xor     r9d, r9d
0x180027141  mov     rdx, [rdi+40h]
0x180027145  mov     rcx, [rdi+38h]; SourceString
0x180027149  call    UbpmUpdateConsumerSidCache
0x18002714e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027155  lea     rax, WPP_GLOBAL_Control
0x18002715c  cmp     rcx, rax
0x18002715f  jz      loc_1800270DE
0x180027165  test    byte ptr [rcx+1Ch], 80h
0x180027169  jz      loc_1800270DE
0x18002716f  mov     rcx, [rcx+10h]
0x180027173  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002717a  mov     edx, 40h ; '@'
0x18002717f  mov     r9, rbp
0x180027182  call    WPP_SF_S
0x180027187  jmp     loc_1800270DE
0x18002718c  mov     ecx, 3
0x180027191  int     29h; Win8: RtlFailFast(ecx)
```

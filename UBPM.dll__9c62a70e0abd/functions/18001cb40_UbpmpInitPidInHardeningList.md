# UbpmpInitPidInHardeningList

- ea: `0x18001cb40`
- end: `0x18001cbd3`
- name: `UbpmpInitPidInHardeningList`
- size: `147`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001da20`

## callees

- `0x1800103c0`
- `0x18001cb40`
- `0x18001d1d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001cbb8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001cbb8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001cba3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001cba3`

## pseudocode

```c
void __fastcall UbpmpInitPidInHardeningList(PSID pSid1, int a2)
{
  struct _LIST_ENTRY *i; // rbx

  if ( pSid1 && UbpmUtilsSidSupportsHardening(pSid1) )
  {
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_TaskHostContextListLock);
    for ( i = g_leTaskHostHardeningListHead.Flink; i != &g_leTaskHostHardeningListHead; i = i->Flink )
    {
      if ( !i[3].Flink && EqualSid(pSid1, i[1].Blink) && !LODWORD(i[3].Blink) )
        LODWORD(i[3].Blink) = a2;
    }
    dword_180050018 = 0;
    RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  }
}

```

## disassembly

```asm
0x18001cb40  test    rcx, rcx
0x18001cb43  jz      short locret_18001CB65
0x18001cb45  push    rbx
0x18001cb46  push    rsi
0x18001cb47  push    rdi
0x18001cb48  push    r14
0x18001cb4a  sub     rsp, 28h
0x18001cb4e  mov     esi, edx
0x18001cb50  mov     rdi, rcx
0x18001cb53  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x18001cb58  test    al, al
0x18001cb5a  jnz     short loc_18001CB67
0x18001cb5c  add     rsp, 28h
0x18001cb60  pop     r14
0x18001cb62  pop     rdi
0x18001cb63  pop     rsi
0x18001cb64  pop     rbx
0x18001cb65  retn
0x18001cb67  lea     rcx, g_TaskHostContextListLock; struct _UBPM_SRWLOCK *
0x18001cb6e  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18001cb73  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18001cb7a  lea     r14, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18001cb81  cmp     rbx, r14
0x18001cb84  jz      short loc_18001CB92
0x18001cb86  cmp     qword ptr [rbx+30h], 0
0x18001cb8b  jz      short loc_18001CBB1
0x18001cb8d  mov     rbx, [rbx]
0x18001cb90  jmp     short loc_18001CB81
0x18001cb92  lea     rcx, g_TaskHostContextListLock
0x18001cb99  mov     cs:dword_180050018, 0
0x18001cba3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001cbaa  nop     dword ptr [rax+rax+00h]
0x18001cbaf  jmp     short loc_18001CB5C
0x18001cbb1  mov     rdx, [rbx+18h]; pSid2
0x18001cbb5  mov     rcx, rdi; pSid1
0x18001cbb8  call    cs:__imp_EqualSid
0x18001cbbf  nop     dword ptr [rax+rax+00h]
0x18001cbc4  test    eax, eax
0x18001cbc6  jz      short loc_18001CB8D
0x18001cbc8  cmp     dword ptr [rbx+38h], 0
0x18001cbcc  jnz     short loc_18001CB8D
0x18001cbce  mov     [rbx+38h], esi
0x18001cbd1  jmp     short loc_18001CB8D
```

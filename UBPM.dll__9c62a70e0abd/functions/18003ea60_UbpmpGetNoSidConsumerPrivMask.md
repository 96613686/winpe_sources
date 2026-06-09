# UbpmpGetNoSidConsumerPrivMask

- ea: `0x18003ea60`
- end: `0x18003eb25`
- name: `UbpmpGetNoSidConsumerPrivMask`
- size: `197`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f284`

## callees

- `0x1800103c0`
- `0x18003ea60`
- `0x18003eff0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ea9a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ea9a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003eb19`

## pseudocode

```c
__int64 __fastcall UbpmpGetNoSidConsumerPrivMask(PSID pSid1, _QWORD *a2)
{
  struct _LIST_ENTRY *i; // rbx
  int v5; // r8d

  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_TaskHostContextListLock);
  for ( i = g_leTaskHostHardeningListHead.Flink; i != &g_leTaskHostHardeningListHead; i = i->Flink )
  {
    if ( !i[3].Flink )
    {
      if ( EqualSid(pSid1, i[1].Blink) )
      {
        if ( ((LODWORD(i[3].Blink) + 1) & 0xFFFFFFFE) == 0 )
        {
          *a2 |= (unsigned __int64)i[2].Flink;
          LODWORD(i[3].Blink) = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_Si(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, v5, i[1].Flink, *a2);
        }
      }
    }
  }
  dword_180050018 = 0;
  return RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
}

```

## disassembly

```asm
0x18003ea60  push    rbx
0x18003ea62  push    rsi
0x18003ea63  push    rdi
0x18003ea64  push    r14
0x18003ea66  sub     rsp, 38h
0x18003ea6a  mov     rsi, rcx
0x18003ea6d  mov     rdi, rdx
0x18003ea70  lea     rcx, g_TaskHostContextListLock; struct _UBPM_SRWLOCK *
0x18003ea77  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18003ea7c  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18003ea83  lea     r14, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18003ea8a  jmp     short loc_18003EAFA
0x18003ea8c  cmp     qword ptr [rbx+30h], 0
0x18003ea91  jnz     short loc_18003EAF7
0x18003ea93  mov     rdx, [rbx+18h]; pSid2
0x18003ea97  mov     rcx, rsi; pSid1
0x18003ea9a  call    cs:__imp_EqualSid
0x18003eaa1  nop     dword ptr [rax+rax+00h]
0x18003eaa6  test    eax, eax
0x18003eaa8  jz      short loc_18003EAF7
0x18003eaaa  mov     eax, [rbx+38h]
0x18003eaad  inc     eax
0x18003eaaf  test    eax, 0FFFFFFFEh
0x18003eab4  jnz     short loc_18003EAF7
0x18003eab6  mov     rax, [rbx+20h]
0x18003eaba  or      [rdi], rax
0x18003eabd  mov     dword ptr [rbx+38h], 0
0x18003eac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eacb  lea     rax, WPP_GLOBAL_Control
0x18003ead2  cmp     rcx, rax
0x18003ead5  jz      short loc_18003EAF7
0x18003ead7  test    byte ptr [rcx+1Ch], 80h
0x18003eadb  jz      short loc_18003EAF7
0x18003eadd  mov     rax, [rdi]
0x18003eae0  mov     edx, 0E2h
0x18003eae5  mov     r9, [rbx+10h]
0x18003eae9  mov     rcx, [rcx+10h]
0x18003eaed  mov     [rsp+58h+var_38], rax
0x18003eaf2  call    WPP_SF_Si
0x18003eaf7  mov     rbx, [rbx]
0x18003eafa  cmp     rbx, r14
0x18003eafd  jnz     short loc_18003EA8C
0x18003eaff  lea     rcx, g_TaskHostContextListLock
0x18003eb06  mov     cs:dword_180050018, 0
0x18003eb10  add     rsp, 38h
0x18003eb14  pop     r14
0x18003eb16  pop     rdi
0x18003eb17  pop     rsi
0x18003eb18  pop     rbx
0x18003eb19  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```

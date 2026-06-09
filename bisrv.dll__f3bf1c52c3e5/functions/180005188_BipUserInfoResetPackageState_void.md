# BipUserInfoResetPackageState(void *)

- ea: `0x180005188`
- end: `0x180005277`
- name: `?BipUserInfoResetPackageState@@YAXPEAX@Z`
- size: `239`
- prototype: `void __fastcall(PSID Sid1)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007014`

## callees

- `0x1800048ec`
- `0x180005188`
- `0x180005360`
- `0x1800053a0`
- `0x1800058b4`
- `0x18000d7c0`
- `0x18000da50`
- `0x1800121b0`

## import_xrefs

- `ntdll!RtlEnumerateEntryHashTable` at `0x180005235`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180005235`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800051d7`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800051d7`
- `ntdll!RtlEqualSid` at `0x1800051fe`
- `ntdll!RtlEqualSid` at `0x1800051fe`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000524e`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000524e`

## pseudocode

```c
void __fastcall BipUserInfoResetPackageState(PSID Sid1)
{
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdx
  _OWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v6; // [rsp+40h] [rbp-10h]
  __int64 v7; // [rsp+68h] [rbp+18h] BYREF

  v7 = 0;
  BipAcquireGlobalLock();
  memset(v5, 0, sizeof(v5));
  v6 = 0;
  if ( (unsigned __int8)RtlInitEnumerationHashTable(qword_1800C4380, v5) )
  {
    BipPackageGetNext(&v7, v5);
    v3 = v7;
    if ( v7 )
    {
      do
      {
        if ( RtlEqualSid(Sid1, *(PSID *)(v3 + 24)) )
        {
          BipPackageBackgroundAccessQueueQueryState(v3);
          *(_DWORD *)(v3 + 572) = 0;
          BipResetPackageStateFlags(v3);
          BipConditionallyDeletePackage(v3);
        }
        v3 = RtlEnumerateEntryHashTable(qword_1800C4380, v5);
      }
      while ( v3 );
      RtlEndEnumerationHashTable(qword_1800C4380, v5);
    }
  }
  BipLockWatchdogContextDisarmWatchdog(v2);
  LOBYTE(v4) = 1;
  BipSyncReleaseLock(&BipGlobalLock, v4);
}

```

## disassembly

```asm
0x180005188  mov     [rsp-8+arg_0], rbx
0x18000518d  mov     [rsp-8+arg_10], rdi
0x180005192  push    rbp
0x180005193  mov     rbp, rsp
0x180005196  sub     rsp, 50h
0x18000519a  xorps   xmm0, xmm0
0x18000519d  mov     [rbp+arg_8], 0
0x1800051a5  xor     eax, eax
0x1800051a7  mov     rdi, rcx
0x1800051aa  movups  [rbp+var_30], xmm0
0x1800051ae  mov     [rbp+var_10], rax
0x1800051b2  movups  [rbp+var_20], xmm0
0x1800051b6  call    BipAcquireGlobalLock
0x1800051bb  mov     rcx, cs:qword_1800C4380
0x1800051c2  lea     rdx, [rbp+var_30]
0x1800051c6  xorps   xmm0, xmm0
0x1800051c9  xor     eax, eax
0x1800051cb  movups  [rbp+var_30], xmm0
0x1800051cf  mov     [rbp+var_10], rax
0x1800051d3  movups  [rbp+var_20], xmm0
0x1800051d7  call    cs:__imp_RtlInitEnumerationHashTable
0x1800051dd  test    al, al
0x1800051df  jz      short loc_180005254
0x1800051e1  lea     rdx, [rbp+var_30]
0x1800051e5  lea     rcx, [rbp+arg_8]
0x1800051e9  call    BipPackageGetNext
0x1800051ee  mov     rbx, [rbp+arg_8]
0x1800051f2  test    rbx, rbx
0x1800051f5  jz      short loc_180005254
0x1800051f7  mov     rdx, [rbx+18h]; Sid2
0x1800051fb  mov     rcx, rdi; Sid1
0x1800051fe  call    cs:__imp_RtlEqualSid
0x180005204  test    al, al
0x180005206  jz      short loc_18000522A
0x180005208  mov     rcx, rbx
0x18000520b  call    BipPackageBackgroundAccessQueueQueryState
0x180005210  mov     rcx, rbx
0x180005213  mov     dword ptr [rbx+23Ch], 0
0x18000521d  call    BipResetPackageStateFlags
0x180005222  mov     rcx, rbx
0x180005225  call    BipConditionallyDeletePackage
0x18000522a  mov     rcx, cs:qword_1800C4380
0x180005231  lea     rdx, [rbp+var_30]
0x180005235  call    cs:__imp_RtlEnumerateEntryHashTable
0x18000523b  mov     rbx, rax
0x18000523e  test    rax, rax
0x180005241  jnz     short loc_1800051F7
0x180005243  mov     rcx, cs:qword_1800C4380
0x18000524a  lea     rdx, [rbp+var_30]
0x18000524e  call    cs:__imp_RtlEndEnumerationHashTable
0x180005254  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180005259  mov     dl, 1
0x18000525b  lea     rcx, BipGlobalLock
0x180005262  call    BipSyncReleaseLock
0x180005267  mov     rbx, [rsp+50h+arg_0]
0x18000526c  mov     rdi, [rsp+50h+arg_10]
0x180005271  add     rsp, 50h
0x180005275  pop     rbp
0x180005276  retn
```

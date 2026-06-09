# BiSrvQueryWorkItemStatusStateName

- ea: `0x180039d14`
- end: `0x180039f10`
- name: `BiSrvQueryWorkItemStatusStateName`
- size: `508`
- prototype: `__int64 __fastcall(void *Source2)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039d00`
- `0x180065324`
- `0x18007e2ac`

## callees

- `0x18000d50c`
- `0x18000d7c0`
- `0x18000da50`
- `0x1800121b0`
- `0x180039d14`
- `0x18004df58`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180039ded`
- `ntdll!RtlReleaseSRWLockShared` at `0x180039ded`
- `ntdll!RtlAcquireSRWLockShared` at `0x180039d7e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180039d7e`
- `ntdll!RtlGetNextEntryHashTable` at `0x180039dd8`
- `ntdll!RtlGetNextEntryHashTable` at `0x180039dd8`
- `ntdll!RtlLookupEntryHashTable` at `0x180039d9c`
- `ntdll!RtlLookupEntryHashTable` at `0x180039d9c`
- `ntdll!RtlWaitOnAddress` at `0x180039eae`
- `ntdll!RtlWaitOnAddress` at `0x180039eae`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180039dc1`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180039e66`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180039dc1`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180039e66`

## pseudocode

```c
__int64 __fastcall BiSrvQueryWorkItemStatusStateName(unsigned __int8 *Source2, _QWORD *a2)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  unsigned __int8 *v6; // rcx
  int v7; // edx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 i; // rax
  __int64 v11; // rsi
  int v12; // edi
  int v13; // ecx
  char v15; // si
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v16; // rcx
  __int64 *j; // rbx
  __int64 v18; // rdx
  __int128 v19; // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+30h] [rbp-38h]
  int v21; // [rsp+70h] [rbp+8h] BYREF

  while ( 1 )
  {
    v21 = dword_1800C4340;
    if ( (unsigned int)dword_1800C4340 > 1 )
      break;
    RtlWaitOnAddress(&dword_1800C4340, &v21, 4, 0);
  }
  v4 = qword_1800C4148;
  v5 = 0;
  v19 = 0;
  v20 = 0;
  v6 = Source2;
  v7 = 16;
  do
  {
    v8 = *v6++;
    v4 = v8 + 39 * v4;
    --v7;
  }
  while ( v7 );
  RtlAcquireSRWLockShared(&qword_1800C4390);
  v9 = 1;
  if ( v4 )
    v9 = v4;
  for ( i = RtlLookupEntryHashTable(qword_1800C4388, v9, &v19); ; i = RtlGetNextEntryHashTable(qword_1800C4388, &v19) )
  {
    v11 = i;
    if ( !i )
      break;
    v5 = i;
    if ( RtlCompareMemory(Source2, (const void *)(i + 32), 0x10u) == 16 )
    {
      v12 = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 28));
      goto LABEL_11;
    }
  }
  v12 = -1073741275;
LABEL_11:
  RtlReleaseSRWLockShared(&qword_1800C4390);
  if ( v12 < 0 )
  {
    v15 = 0;
    BipAcquireGlobalLock();
    for ( j = (__int64 *)qword_1800C43A0; j != &qword_1800C43A0; j = (__int64 *)*j )
    {
      if ( RtlCompareMemory(j + 2, Source2, 0x10u) == 16 )
      {
        v15 = 1;
        *a2 = j[4];
        break;
      }
    }
    BipLockWatchdogContextDisarmWatchdog(v16);
    LOBYTE(v18) = 1;
    BipSyncReleaseLock(&BipGlobalLock, v18);
    if ( !v15 )
      return (unsigned int)-1073741275;
  }
  else
  {
    v13 = *(_DWORD *)(v5 + 400);
    if ( v13 && v13 != 2 )
    {
      v12 = -1073741811;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
    }
    else
    {
      *a2 = *(_QWORD *)(v5 + 592);
    }
    if ( v5 )
      BipWorkItemDereference(v5);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180039d14  mov     [rsp+arg_8], rbx
0x180039d19  mov     [rsp+arg_10], rbp
0x180039d1e  push    rsi
0x180039d1f  push    rdi
0x180039d20  push    r12
0x180039d22  push    r13
0x180039d24  push    r14
0x180039d26  sub     rsp, 40h
0x180039d2a  mov     r14, rdx
0x180039d2d  mov     rbp, rcx
0x180039d30  mov     eax, cs:dword_1800C4340
0x180039d36  mov     [rsp+68h+arg_0], eax
0x180039d3a  cmp     eax, 1
0x180039d3d  jbe     loc_180039E9B
0x180039d43  mov     rdi, cs:qword_1800C4148
0x180039d4a  xor     ebx, ebx
0x180039d4c  xorps   xmm0, xmm0
0x180039d4f  xor     eax, eax
0x180039d51  movups  [rsp+68h+var_48], xmm0
0x180039d56  mov     [rsp+68h+var_38], rax
0x180039d5b  mov     rcx, rbp
0x180039d5e  lea     r12d, [rbx+10h]
0x180039d62  mov     edx, r12d
0x180039d65  movzx   eax, byte ptr [rcx]
0x180039d68  inc     rcx
0x180039d6b  imul    rdi, 27h ; '''
0x180039d6f  add     rdi, rax
0x180039d72  add     edx, 0FFFFFFFFh
0x180039d75  jnz     short loc_180039D65
0x180039d77  lea     rcx, qword_1800C4390
0x180039d7e  call    cs:__imp_RtlAcquireSRWLockShared
0x180039d84  mov     rcx, cs:qword_1800C4388
0x180039d8b  lea     r8, [rsp+68h+var_48]
0x180039d90  test    rdi, rdi
0x180039d93  mov     edx, 1
0x180039d98  cmovnz  rdx, rdi
0x180039d9c  call    cs:__imp_RtlLookupEntryHashTable
0x180039da2  mov     rsi, rax
0x180039da5  mov     r13d, 0C0000225h
0x180039dab  test    rax, rax
0x180039dae  jz      loc_180039EC6
0x180039db4  lea     rdx, [rax+20h]; Source2
0x180039db8  mov     r8, r12; Length
0x180039dbb  mov     rcx, rbp; Source1
0x180039dbe  mov     rbx, rax
0x180039dc1  call    cs:__imp_RtlCompareMemory
0x180039dc7  cmp     rax, r12
0x180039dca  jz      short loc_180039DE0
0x180039dcc  mov     rcx, cs:qword_1800C4388
0x180039dd3  lea     rdx, [rsp+68h+var_48]
0x180039dd8  call    cs:__imp_RtlGetNextEntryHashTable
0x180039dde  jmp     short loc_180039DA2
0x180039de0  xor     edi, edi
0x180039de2  lock inc dword ptr [rsi+1Ch]
0x180039de6  lea     rcx, qword_1800C4390
0x180039ded  call    cs:__imp_RtlReleaseSRWLockShared
0x180039df3  test    edi, edi
0x180039df5  js      short loc_180039E41
0x180039df7  mov     ecx, [rbx+190h]
0x180039dfd  test    ecx, ecx
0x180039dff  jz      short loc_180039E13
0x180039e01  sub     ecx, 1
0x180039e04  jz      loc_180039ECE
0x180039e0a  cmp     ecx, 1
0x180039e0d  jnz     loc_180039ECE
0x180039e13  mov     rax, [rbx+250h]
0x180039e1a  mov     [r14], rax
0x180039e1d  test    rbx, rbx
0x180039e20  jnz     loc_180039EB9
0x180039e26  lea     r11, [rsp+68h+var_28]
0x180039e2b  mov     eax, edi
0x180039e2d  mov     rbx, [r11+38h]
0x180039e31  mov     rbp, [r11+40h]
0x180039e35  mov     rsp, r11
0x180039e38  pop     r14
0x180039e3a  pop     r13
0x180039e3c  pop     r12
0x180039e3e  pop     rdi
0x180039e3f  pop     rsi
0x180039e40  retn
0x180039e41  xor     sil, sil
0x180039e44  call    BipAcquireGlobalLock
0x180039e49  mov     rbx, cs:qword_1800C43A0
0x180039e50  lea     rax, qword_1800C43A0
0x180039e57  cmp     rbx, rax
0x180039e5a  jz      short loc_180039E7F
0x180039e5c  lea     rcx, [rbx+10h]; Source1
0x180039e60  mov     r8, r12; Length
0x180039e63  mov     rdx, rbp; Source2
0x180039e66  call    cs:__imp_RtlCompareMemory
0x180039e6c  cmp     rax, r12
0x180039e6f  jnz     loc_180039F08
0x180039e75  mov     rax, [rbx+20h]
0x180039e79  mov     sil, 1
0x180039e7c  mov     [r14], rax
0x180039e7f  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180039e84  mov     dl, 1
0x180039e86  lea     rcx, BipGlobalLock
0x180039e8d  call    BipSyncReleaseLock
0x180039e92  test    sil, sil
0x180039e95  cmovz   edi, r13d
0x180039e99  jmp     short loc_180039E26
0x180039e9b  xor     r9d, r9d
0x180039e9e  lea     rdx, [rsp+68h+arg_0]
0x180039ea3  lea     rcx, dword_1800C4340
0x180039eaa  lea     r8d, [r9+4]
0x180039eae  call    cs:__imp_RtlWaitOnAddress
0x180039eb4  jmp     loc_180039D30
0x180039eb9  mov     rcx, rbx
0x180039ebc  call    BipWorkItemDereference
0x180039ec1  jmp     loc_180039E26
0x180039ec6  mov     edi, r13d
0x180039ec9  jmp     loc_180039DE6
0x180039ece  mov     edi, 0C000000Dh
0x180039ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180039eda  test    byte ptr [rcx+1Ch], 40h
0x180039ede  jz      loc_180039E1D
0x180039ee4  cmp     byte ptr [rcx+19h], 2
0x180039ee8  jb      loc_180039E1D
0x180039eee  mov     rcx, [rcx+10h]
0x180039ef2  lea     r8, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids
0x180039ef9  mov     edx, 3Ah ; ':'
0x180039efe  call    WPP_SF_
0x180039f03  jmp     loc_180039E1D
0x180039f08  mov     rbx, [rbx]
0x180039f0b  jmp     loc_180039E50
```

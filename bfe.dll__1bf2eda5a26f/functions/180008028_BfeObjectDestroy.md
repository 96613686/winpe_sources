# BfeObjectDestroy

- ea: `0x180008028`
- end: `0x180008235`
- name: `BfeObjectDestroy`
- size: `525`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005f80`
- `0x180038580`

## callees

- `0x180007f6c`
- `0x180008028`
- `0x180008240`
- `0x1800082a4`
- `0x180008320`
- `0x1800083c0`
- `0x1800084e0`
- `0x18000e000`
- `0x18002aaa0`
- `0x1800540ec`
- `0x1800542bc`
- `0x1800575c4`
- `0x18008b010`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180008196`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800081cb`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008196`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800081cb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008180`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008180`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800081ad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800081ad`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180008221`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180008221`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008150`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008150`

## pseudocode

```c
__int64 __fastcall BfeObjectDestroy(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rcx
  _QWORD *v4; // rdx
  _QWORD *v5; // rdi
  _QWORD *v6; // rsi
  _QWORD *v7; // rdi
  bool v8; // zf
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    if ( !*(_QWORD *)v1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (*(_BYTE *)(v1 + 8) & 0x10) != 0 )
    {
      if ( !*(_QWORD *)v1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 96LL))(v1 + 144);
    }
    if ( (*(_BYTE *)(v1 + 8) & 0xC) != 0 )
    {
      v3 = *(_QWORD *)(v1 + 128);
      if ( *(_QWORD *)(v3 + 8) != v1 + 128 || (v4 = *(_QWORD **)(v1 + 136), *v4 != v1 + 128) )
LABEL_32:
        __fastfail(3u);
      *v4 = v3;
      *(_QWORD *)(v3 + 8) = v4;
    }
    BfeSessionRundownDestroy(v1 + 120);
    BfeObjectSecurityDestroy(v1 + 112);
    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage();
    BfeIterateAssociationEnterLock();
    v5 = (_QWORD *)(v1 + 96);
    while ( (_QWORD *)*v5 != v5 )
    {
      v15 = *v5 - 32LL;
      BfeObjectAssocDestroy(&v15);
    }
    v6 = (_QWORD *)(v1 + 80);
    while ( 1 )
    {
      v7 = (_QWORD *)*v6;
      if ( (_QWORD *)*v6 == v6 )
        break;
      v8 = v7 == (_QWORD *)8;
      v9 = v7 - 1;
      v15 = (__int64)v9;
      if ( !v8 )
      {
        v10 = v9[1];
        if ( *(_QWORD **)(v10 + 8) != v9 + 1 )
          goto LABEL_32;
        v11 = (_QWORD *)v9[2];
        if ( (_QWORD *)*v11 != v9 + 1 )
          goto LABEL_32;
        *v11 = v10;
        *(_QWORD *)(v10 + 8) = v11;
        v12 = v9[4];
        if ( *(_QWORD **)(v12 + 8) != v9 + 4 )
          goto LABEL_32;
        v13 = (_QWORD *)v9[5];
        if ( (_QWORD *)*v13 != v9 + 4 )
          goto LABEL_32;
        *v13 = v12;
        *(_QWORD *)(v12 + 8) = v13;
      }
      if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
      {
        WfpMemFree25B(&v15);
      }
      else
      {
        if ( gWfpTrackHeapBytes )
        {
          if ( v9 )
            _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v9));
        }
        HeapFree(gWfpHeap, 0, v9);
      }
    }
    BfeIterateAssociationLeaveLock();
    if ( (*(_BYTE *)(v1 + 8) & 0x40) != 0 )
    {
      RtlAcquireSRWLockExclusive(*(_QWORD *)v1 + 328LL);
      RtlRemoveEntryHashTable(*(_QWORD *)v1 + 288LL, v1 + 40, 0);
      WfpRestructureHashtable(*(_QWORD *)v1 + 288LL);
      RtlReleaseSRWLockExclusive(*(_QWORD *)v1 + 328LL);
    }
    if ( (*(_BYTE *)(v1 + 8) & 0x20) != 0 )
    {
      RtlRemoveEntryHashTable(*(_QWORD *)v1 + 240LL, v1 + 16, 0);
      WfpRestructureHashtable(*(_QWORD *)v1 + 240LL);
    }
  }
  return WfpMemFree(a1);
}

```

## disassembly

```asm
0x180008028  push    rbx
0x18000802a  push    rsi
0x18000802b  push    rdi
0x18000802c  push    r14
0x18000802e  sub     rsp, 28h
0x180008032  mov     rbx, [rcx]
0x180008035  mov     r14, rcx
0x180008038  test    rbx, rbx
0x18000803b  jz      loc_1800081DC
0x180008041  cmp     qword ptr [rbx], 0
0x180008045  jnz     short loc_18000804C
0x180008047  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000804c  test    byte ptr [rbx+8], 10h
0x180008050  jz      short loc_180008070
0x180008052  cmp     qword ptr [rbx], 0
0x180008056  jnz     short loc_18000805D
0x180008058  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000805d  mov     rax, [rbx]
0x180008060  lea     rcx, [rbx+90h]
0x180008067  mov     rax, [rax+60h]
0x18000806b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008070  test    byte ptr [rbx+8], 0Ch
0x180008074  jz      short loc_18000809E
0x180008076  lea     rax, [rbx+80h]
0x18000807d  mov     rcx, [rax]
0x180008080  cmp     [rcx+8], rax
0x180008084  jnz     loc_180008205
0x18000808a  mov     rdx, [rax+8]
0x18000808e  cmp     [rdx], rax
0x180008091  jnz     loc_180008205
0x180008097  mov     [rdx], rcx
0x18000809a  mov     [rcx+8], rdx
0x18000809e  lea     rcx, [rbx+78h]
0x1800080a2  call    BfeSessionRundownDestroy
0x1800080a7  lea     rcx, [rbx+70h]
0x1800080ab  call    BfeObjectSecurityDestroy
0x1800080b0  call    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage
0x1800080b5  call    BfeIterateAssociationEnterLock
0x1800080ba  lea     rdi, [rbx+60h]
0x1800080be  mov     rax, [rdi]
0x1800080c1  cmp     rax, rdi
0x1800080c4  jnz     loc_1800081ED
0x1800080ca  lea     rsi, [rbx+50h]
0x1800080ce  mov     rdi, [rsi]
0x1800080d1  cmp     rdi, rsi
0x1800080d4  jz      loc_18000816A
0x1800080da  add     rdi, 0FFFFFFFFFFFFFFF8h
0x1800080de  mov     [rsp+48h+arg_0], rdi
0x1800080e3  jz      short loc_18000812F
0x1800080e5  lea     rax, [rdi+8]
0x1800080e9  mov     rcx, [rax]
0x1800080ec  cmp     [rcx+8], rax
0x1800080f0  jnz     loc_180008205
0x1800080f6  mov     rdx, [rax+8]
0x1800080fa  cmp     [rdx], rax
0x1800080fd  jnz     loc_180008205
0x180008103  mov     [rdx], rcx
0x180008106  mov     [rcx+8], rdx
0x18000810a  lea     rcx, [rdi+20h]
0x18000810e  mov     rdx, [rcx]
0x180008111  cmp     [rdx+8], rcx
0x180008115  jnz     loc_180008205
0x18000811b  mov     rax, [rcx+8]
0x18000811f  cmp     [rax], rcx
0x180008122  jnz     loc_180008205
0x180008128  mov     [rax], rdx
0x18000812b  mov     [rdx+8], rax
0x18000812f  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180008134  test    eax, eax
0x180008136  jnz     short loc_18000815B
0x180008138  cmp     cs:gWfpTrackHeapBytes, eax
0x18000813e  jnz     loc_18000820C
0x180008144  mov     rcx, cs:gWfpHeap; hHeap
0x18000814b  mov     r8, rdi; lpMem
0x18000814e  xor     edx, edx; dwFlags
0x180008150  call    cs:__imp_HeapFree
0x180008156  jmp     loc_1800080CE
0x18000815b  lea     rcx, [rsp+48h+arg_0]
0x180008160  call    WfpMemFree25B
0x180008165  jmp     loc_1800080CE
0x18000816a  call    BfeIterateAssociationLeaveLock
0x18000816f  test    byte ptr [rbx+8], 40h
0x180008173  jz      short loc_1800081B3
0x180008175  mov     rcx, [rbx]
0x180008178  mov     esi, 148h
0x18000817d  add     rcx, rsi
0x180008180  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008186  mov     rcx, [rbx]
0x180008189  lea     edi, [rsi-28h]
0x18000818c  add     rcx, rdi
0x18000818f  lea     rdx, [rbx+28h]
0x180008193  xor     r8d, r8d
0x180008196  call    cs:__imp_RtlRemoveEntryHashTable
0x18000819c  mov     rcx, [rbx]
0x18000819f  add     rcx, rdi
0x1800081a2  call    WfpRestructureHashtable
0x1800081a7  mov     rcx, [rbx]
0x1800081aa  add     rcx, rsi
0x1800081ad  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800081b3  test    byte ptr [rbx+8], 20h
0x1800081b7  jz      short loc_1800081DC
0x1800081b9  mov     rcx, [rbx]
0x1800081bc  lea     rdx, [rbx+10h]
0x1800081c0  mov     edi, 0F0h
0x1800081c5  xor     r8d, r8d
0x1800081c8  add     rcx, rdi
0x1800081cb  call    cs:__imp_RtlRemoveEntryHashTable
0x1800081d1  mov     rcx, [rbx]
0x1800081d4  add     rcx, rdi
0x1800081d7  call    WfpRestructureHashtable
0x1800081dc  mov     rcx, r14
0x1800081df  add     rsp, 28h
0x1800081e3  pop     r14
0x1800081e5  pop     rdi
0x1800081e6  pop     rsi
0x1800081e7  pop     rbx
0x1800081e8  jmp     WfpMemFree
0x1800081ed  add     rax, 0FFFFFFFFFFFFFFE0h
0x1800081f1  lea     rcx, [rsp+48h+arg_0]
0x1800081f6  mov     [rsp+48h+arg_0], rax
0x1800081fb  call    BfeObjectAssocDestroy
0x180008200  jmp     loc_1800080BE
0x180008205  mov     ecx, 3
0x18000820a  int     29h; Win8: RtlFailFast(ecx)
0x18000820c  test    rdi, rdi
0x18000820f  jz      loc_180008144
0x180008215  mov     rcx, cs:gWfpHeap; hHeap
0x18000821c  mov     r8, rdi; lpMem
0x18000821f  xor     edx, edx; dwFlags
0x180008221  call    cs:__imp_HeapSize
0x180008227  neg     eax
0x180008229  lock add cs:gWfpHeapBytesAllocated, eax
0x180008230  jmp     loc_180008144
```

# BfeObjectDestroy

- ea: `0x1800085b8`
- end: `0x1800087e9`
- name: `BfeObjectDestroy`
- size: `561`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800367b0`
- `0x180037070`

## callees

- `0x1800084ec`
- `0x1800085b8`
- `0x1800087f0`
- `0x180008868`
- `0x1800088f0`
- `0x1800089a0`
- `0x180008adc`
- `0x18000e7e0`
- `0x18002c1e0`
- `0x180055f04`
- `0x1800560f8`
- `0x1800592f4`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180008732`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008773`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008732`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008773`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008716`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008716`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000874f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000874f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800087cf`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800087cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086e0`

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
0x1800085b8  push    rbx
0x1800085ba  push    rsi
0x1800085bb  push    rdi
0x1800085bc  push    r14
0x1800085be  sub     rsp, 28h
0x1800085c2  mov     rbx, [rcx]
0x1800085c5  mov     r14, rcx
0x1800085c8  test    rbx, rbx
0x1800085cb  jz      loc_18000878A
0x1800085d1  cmp     qword ptr [rbx], 0
0x1800085d5  jnz     short loc_1800085DC
0x1800085d7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x1800085dc  test    byte ptr [rbx+8], 10h
0x1800085e0  jz      short loc_180008600
0x1800085e2  cmp     qword ptr [rbx], 0
0x1800085e6  jnz     short loc_1800085ED
0x1800085e8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x1800085ed  mov     rax, [rbx]
0x1800085f0  lea     rcx, [rbx+90h]
0x1800085f7  mov     rax, [rax+60h]
0x1800085fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008600  test    byte ptr [rbx+8], 0Ch
0x180008604  jz      short loc_18000862E
0x180008606  lea     rax, [rbx+80h]
0x18000860d  mov     rcx, [rax]
0x180008610  cmp     [rcx+8], rax
0x180008614  jnz     loc_1800087B3
0x18000861a  mov     rdx, [rax+8]
0x18000861e  cmp     [rdx], rax
0x180008621  jnz     loc_1800087B3
0x180008627  mov     [rdx], rcx
0x18000862a  mov     [rcx+8], rdx
0x18000862e  lea     rcx, [rbx+78h]
0x180008632  call    BfeSessionRundownDestroy
0x180008637  lea     rcx, [rbx+70h]
0x18000863b  call    BfeObjectSecurityDestroy
0x180008640  call    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage
0x180008645  call    BfeIterateAssociationEnterLock
0x18000864a  lea     rdi, [rbx+60h]
0x18000864e  mov     rax, [rdi]
0x180008651  cmp     rax, rdi
0x180008654  jnz     loc_18000879B
0x18000865a  lea     rsi, [rbx+50h]
0x18000865e  mov     rdi, [rsi]
0x180008661  cmp     rdi, rsi
0x180008664  jz      loc_180008700
0x18000866a  add     rdi, 0FFFFFFFFFFFFFFF8h
0x18000866e  mov     [rsp+48h+arg_0], rdi
0x180008673  jz      short loc_1800086BF
0x180008675  lea     rax, [rdi+8]
0x180008679  mov     rcx, [rax]
0x18000867c  cmp     [rcx+8], rax
0x180008680  jnz     loc_1800087B3
0x180008686  mov     rdx, [rax+8]
0x18000868a  cmp     [rdx], rax
0x18000868d  jnz     loc_1800087B3
0x180008693  mov     [rdx], rcx
0x180008696  mov     [rcx+8], rdx
0x18000869a  lea     rcx, [rdi+20h]
0x18000869e  mov     rdx, [rcx]
0x1800086a1  cmp     [rdx+8], rcx
0x1800086a5  jnz     loc_1800087B3
0x1800086ab  mov     rax, [rcx+8]
0x1800086af  cmp     [rax], rcx
0x1800086b2  jnz     loc_1800087B3
0x1800086b8  mov     [rax], rdx
0x1800086bb  mov     [rdx+8], rax
0x1800086bf  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x1800086c4  test    eax, eax
0x1800086c6  jnz     short loc_1800086F1
0x1800086c8  cmp     cs:gWfpTrackHeapBytes, eax
0x1800086ce  jnz     loc_1800087BA
0x1800086d4  mov     rcx, cs:gWfpHeap; hHeap
0x1800086db  mov     r8, rdi; lpMem
0x1800086de  xor     edx, edx; dwFlags
0x1800086e0  call    cs:__imp_HeapFree
0x1800086e7  nop     dword ptr [rax+rax+00h]
0x1800086ec  jmp     loc_18000865E
0x1800086f1  lea     rcx, [rsp+48h+arg_0]
0x1800086f6  call    WfpMemFree25B
0x1800086fb  jmp     loc_18000865E
0x180008700  call    BfeIterateAssociationLeaveLock
0x180008705  test    byte ptr [rbx+8], 40h
0x180008709  jz      short loc_18000875B
0x18000870b  mov     rcx, [rbx]
0x18000870e  mov     esi, 148h
0x180008713  add     rcx, rsi
0x180008716  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000871d  nop     dword ptr [rax+rax+00h]
0x180008722  mov     rcx, [rbx]
0x180008725  lea     edi, [rsi-28h]
0x180008728  add     rcx, rdi
0x18000872b  lea     rdx, [rbx+28h]
0x18000872f  xor     r8d, r8d
0x180008732  call    cs:__imp_RtlRemoveEntryHashTable
0x180008739  nop     dword ptr [rax+rax+00h]
0x18000873e  mov     rcx, [rbx]
0x180008741  add     rcx, rdi
0x180008744  call    WfpRestructureHashtable
0x180008749  mov     rcx, [rbx]
0x18000874c  add     rcx, rsi
0x18000874f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008756  nop     dword ptr [rax+rax+00h]
0x18000875b  test    byte ptr [rbx+8], 20h
0x18000875f  jz      short loc_18000878A
0x180008761  mov     rcx, [rbx]
0x180008764  lea     rdx, [rbx+10h]
0x180008768  mov     edi, 0F0h
0x18000876d  xor     r8d, r8d
0x180008770  add     rcx, rdi
0x180008773  call    cs:__imp_RtlRemoveEntryHashTable
0x18000877a  nop     dword ptr [rax+rax+00h]
0x18000877f  mov     rcx, [rbx]
0x180008782  add     rcx, rdi
0x180008785  call    WfpRestructureHashtable
0x18000878a  mov     rcx, r14
0x18000878d  add     rsp, 28h
0x180008791  pop     r14
0x180008793  pop     rdi
0x180008794  pop     rsi
0x180008795  pop     rbx
0x180008796  jmp     WfpMemFree
0x18000879b  add     rax, 0FFFFFFFFFFFFFFE0h
0x18000879f  lea     rcx, [rsp+48h+arg_0]
0x1800087a4  mov     [rsp+48h+arg_0], rax
0x1800087a9  call    BfeObjectAssocDestroy
0x1800087ae  jmp     loc_18000864E
0x1800087b3  mov     ecx, 3
0x1800087b8  int     29h; Win8: RtlFailFast(ecx)
0x1800087ba  test    rdi, rdi
0x1800087bd  jz      loc_1800086D4
0x1800087c3  mov     rcx, cs:gWfpHeap; hHeap
0x1800087ca  mov     r8, rdi; lpMem
0x1800087cd  xor     edx, edx; dwFlags
0x1800087cf  call    cs:__imp_HeapSize
0x1800087d6  nop     dword ptr [rax+rax+00h]
0x1800087db  neg     eax
0x1800087dd  lock add cs:gWfpHeapBytesAllocated, eax
0x1800087e4  jmp     loc_1800086D4
```

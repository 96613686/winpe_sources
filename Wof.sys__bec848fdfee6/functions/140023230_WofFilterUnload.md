# WofFilterUnload

- ea: `0x140023230`
- end: `0x14002337e`
- name: `WofFilterUnload`
- size: `334`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140011640`
- `0x140023230`
- `0x1400251f0`
- `0x140025310`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002333d`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002333d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002332c`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002332c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023268`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023285`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023355`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023268`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023285`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023355`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400232e3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400232e3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023250`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002330f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023250`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002330f`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400232fc`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400232fc`
- `FLTMGR!FltUnregisterFilter` at `0x1400232c5`
- `FLTMGR!FltUnregisterFilter` at `0x1400232c5`

## pseudocode

```c
__int64 WofFilterUnload()
{
  struct _FLT_FILTER *v0; // rdi
  __int64 i; // rbx
  void (*v3)(void); // rax
  BOOLEAN j; // dl
  PVOID v5; // rax

  v0 = WofGlobal;
  ExAcquireFastMutexUnsafe(&FastMutex);
  if ( dword_140018468 )
  {
    ExReleaseFastMutexUnsafe(&FastMutex);
    return 3221225659LL;
  }
  else
  {
    byte_140018464 = 1;
    ExReleaseFastMutexUnsafe(&FastMutex);
    for ( i = 0; i != 4; ++i )
    {
      if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * i) )
      {
        v3 = (void (*)(void))*((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * i + 52);
        if ( v3 )
          v3();
      }
    }
    FltUnregisterFilter(v0);
    WofGlobal = 0;
    ExDeletePagedLookasideList(&Lookaside);
    FltDeleteExtraCreateParameterLookasideList(v0, qword_140018340, 0);
    ExAcquireFastMutexUnsafe(&stru_140018628);
    for ( j = 1; ; j = 0 )
    {
      v5 = RtlEnumerateGenericTableAvl(&Table, j);
      if ( !v5 )
        break;
      RtlDeleteElementGenericTableAvl(&Table, v5);
    }
    ExReleaseFastMutexUnsafe(&stru_140018628);
    WofUnregisterTelemetry();
    WppCleanupKm();
    return 0;
  }
}

```

## disassembly

```asm
0x140023230  mov     [rsp+arg_0], rbx
0x140023235  mov     [rsp+arg_8], rbp
0x14002323a  push    rdi
0x14002323b  sub     rsp, 20h
0x14002323f  mov     rdi, cs:WofGlobal
0x140023246  lea     rbx, FastMutex
0x14002324d  mov     rcx, rbx; FastMutex
0x140023250  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140023257  nop     dword ptr [rax+rax+00h]
0x14002325c  cmp     cs:dword_140018468, 0
0x140023263  mov     rcx, rbx; FastMutex
0x140023266  jz      short loc_14002327E
0x140023268  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002326f  nop     dword ptr [rax+rax+00h]
0x140023274  mov     eax, 0C00000BBh
0x140023279  jmp     loc_14002336D
0x14002327e  mov     cs:byte_140018464, 1
0x140023285  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002328c  nop     dword ptr [rax+rax+00h]
0x140023291  xor     ebx, ebx
0x140023293  lea     rbp, WPP_MAIN_CB.Queue+10h
0x14002329a  imul    rax, rbx, 1A8h
0x1400232a1  cmp     byte ptr [rax+rbp], 0
0x1400232a5  jz      short loc_1400232B9
0x1400232a7  mov     rax, [rax+rbp+1A0h]
0x1400232af  test    rax, rax
0x1400232b2  jz      short loc_1400232B9
0x1400232b4  call    _guard_dispatch_icall
0x1400232b9  inc     rbx
0x1400232bc  cmp     rbx, 4
0x1400232c0  jnz     short loc_14002329A
0x1400232c2  mov     rcx, rdi; Filter
0x1400232c5  call    cs:__imp_FltUnregisterFilter
0x1400232cc  nop     dword ptr [rax+rax+00h]
0x1400232d1  lea     rcx, Lookaside; Lookaside
0x1400232d8  mov     cs:WofGlobal, 0
0x1400232e3  call    cs:__imp_ExDeletePagedLookasideList
0x1400232ea  nop     dword ptr [rax+rax+00h]
0x1400232ef  xor     r8d, r8d; Flags
0x1400232f2  lea     rdx, qword_140018340; Lookaside
0x1400232f9  mov     rcx, rdi; Filter
0x1400232fc  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x140023303  nop     dword ptr [rax+rax+00h]
0x140023308  lea     rcx, stru_140018628; FastMutex
0x14002330f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140023316  nop     dword ptr [rax+rax+00h]
0x14002331b  mov     dl, 1
0x14002331d  lea     rbx, Table
0x140023324  jmp     short loc_14002333A
0x140023326  mov     rdx, rax; Buffer
0x140023329  mov     rcx, rbx; Table
0x14002332c  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140023333  nop     dword ptr [rax+rax+00h]
0x140023338  xor     edx, edx; Restart
0x14002333a  mov     rcx, rbx; Table
0x14002333d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140023344  nop     dword ptr [rax+rax+00h]
0x140023349  test    rax, rax
0x14002334c  jnz     short loc_140023326
0x14002334e  lea     rcx, stru_140018628; FastMutex
0x140023355  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002335c  nop     dword ptr [rax+rax+00h]
0x140023361  call    WofUnregisterTelemetry
0x140023366  call    WppCleanupKm
0x14002336b  xor     eax, eax
0x14002336d  mov     rbx, [rsp+28h+arg_0]
0x140023372  mov     rbp, [rsp+28h+arg_8]
0x140023377  add     rsp, 20h
0x14002337b  pop     rdi
0x14002337c  retn
```

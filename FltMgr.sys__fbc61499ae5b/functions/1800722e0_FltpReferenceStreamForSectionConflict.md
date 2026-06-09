# FltpReferenceStreamForSectionConflict

- ea: `0x1800722e0`
- end: `0x180072359`
- name: `FltpReferenceStreamForSectionConflict`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180071ac0`

## callees

- `0x1800722e0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180072330`
- `ntoskrnl!KeDelayExecutionThread` at `0x180072330`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x18007230e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x180072347`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x18007230e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x180072347`

## pseudocode

```c
__int64 __fastcall FltpReferenceStreamForSectionConflict(__int64 a1)
{
  __int64 v2; // rcx
  LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  Interval.QuadPart = -10000;
  v2 = *(_QWORD *)(a1 + 360);
  if ( !v2 )
    return 3221226021LL;
  if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 8)) )
  {
    do
      KeDelayExecutionThread(0, 0, &Interval);
    while ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(a1 + 360) + 8LL)) );
  }
  return 0;
}

```

## disassembly

```asm
0x1800722e0  push    rbx
0x1800722e2  sub     rsp, 20h
0x1800722e6  mov     rbx, rcx
0x1800722e9  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x1800722f2  mov     rcx, [rcx+168h]
0x1800722f9  test    rcx, rcx
0x1800722fc  jnz     short loc_18007230A
0x1800722fe  mov     eax, 0C0000225h
0x180072303  add     rsp, 20h
0x180072307  pop     rbx
0x180072308  retn
0x18007230a  mov     rcx, [rcx+8]; RunRefCacheAware
0x18007230e  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x180072315  nop     dword ptr [rax+rax+00h]
0x18007231a  test    al, al
0x18007231c  jz      short loc_180072327
0x18007231e  xor     eax, eax
0x180072320  add     rsp, 20h
0x180072324  pop     rbx
0x180072325  retn
0x180072327  lea     r8, [rsp+28h+Interval]; Interval
0x18007232c  xor     edx, edx; Alertable
0x18007232e  xor     ecx, ecx; WaitMode
0x180072330  call    cs:__imp_KeDelayExecutionThread
0x180072337  nop     dword ptr [rax+rax+00h]
0x18007233c  mov     rcx, [rbx+168h]
0x180072343  mov     rcx, [rcx+8]; RunRefCacheAware
0x180072347  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x18007234e  nop     dword ptr [rax+rax+00h]
0x180072353  test    al, al
0x180072355  jnz     short loc_18007231E
0x180072357  jmp     short loc_180072327
```

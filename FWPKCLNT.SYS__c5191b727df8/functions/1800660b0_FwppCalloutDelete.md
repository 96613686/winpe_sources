# FwppCalloutDelete

- ea: `0x1800660b0`
- end: `0x180066136`
- name: `FwppCalloutDelete`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180065bd0`

## callees

- `0x1800660b0`
- `0x180066424`
- `0x180066450`

## import_xrefs

- `ntoskrnl!KeReleaseGuardedMutex` at `0x1800660e3`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x180066123`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1800660e3`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x180066123`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1800660c0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x180066105`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1800660c0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x180066105`
- `NETIO!KfdDeleteCalloutEntry` at `0x1800660f2`
- `NETIO!KfdDeleteCalloutEntry` at `0x1800660f2`

## pseudocode

```c
void __fastcall FwppCalloutDelete(__int64 a1)
{
  __int64 v2; // rbx

  KeAcquireGuardedMutex(&gFwppCallouts);
  v2 = FwppCalloutFindByKey(a1);
  if ( v2 )
  {
    KeReleaseGuardedMutex(&gFwppCallouts);
    KfdDeleteCalloutEntry(*(unsigned int *)(v2 + 16));
    KeAcquireGuardedMutex(&gFwppCallouts);
    --*(_DWORD *)(v2 + 24);
    FwppCalloutReleaseIfIdle(v2);
  }
  KeReleaseGuardedMutex(&gFwppCallouts);
}

```

## disassembly

```asm
0x1800660b0  push    rbx
0x1800660b2  sub     rsp, 20h
0x1800660b6  mov     rbx, rcx
0x1800660b9  lea     rcx, gFwppCallouts; Mutex
0x1800660c0  call    cs:__imp_KeAcquireGuardedMutex
0x1800660c7  nop     dword ptr [rax+rax+00h]
0x1800660cc  mov     rcx, rbx
0x1800660cf  call    FwppCalloutFindByKey
0x1800660d4  mov     rbx, rax
0x1800660d7  test    rax, rax
0x1800660da  jz      short loc_18006611C
0x1800660dc  lea     rcx, gFwppCallouts; Mutex
0x1800660e3  call    cs:__imp_KeReleaseGuardedMutex
0x1800660ea  nop     dword ptr [rax+rax+00h]
0x1800660ef  mov     ecx, [rbx+10h]
0x1800660f2  call    cs:__imp_KfdDeleteCalloutEntry
0x1800660f9  nop     dword ptr [rax+rax+00h]
0x1800660fe  lea     rcx, gFwppCallouts; Mutex
0x180066105  call    cs:__imp_KeAcquireGuardedMutex
0x18006610c  nop     dword ptr [rax+rax+00h]
0x180066111  dec     dword ptr [rbx+18h]
0x180066114  mov     rcx, rbx
0x180066117  call    FwppCalloutReleaseIfIdle
0x18006611c  lea     rcx, gFwppCallouts; Mutex
0x180066123  call    cs:__imp_KeReleaseGuardedMutex
0x18006612a  nop     dword ptr [rax+rax+00h]
0x18006612f  add     rsp, 20h
0x180066133  pop     rbx
0x180066134  retn
```

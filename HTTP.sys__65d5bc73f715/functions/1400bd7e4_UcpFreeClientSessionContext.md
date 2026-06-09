# UcpFreeClientSessionContext

- ea: `0x1400bd7e4`
- end: `0x1400bd8fc`
- name: `UcpFreeClientSessionContext`
- size: `280`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400bcdc4`
- `0x14015bb74`

## callees

- `0x14000a350`
- `0x1400bd7e4`
- `0x1400bd904`
- `0x14015beb8`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd858`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd858`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd8ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd8ad`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd830`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd830`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd864`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd864`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd8c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd8c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd820`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd820`

## pseudocode

```c
void __fastcall UcpFreeClientSessionContext(PVOID P)
{
  __int64 v2; // rdi
  ULONG_PTR v3; // rdi
  int v4; // eax

  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_q(1053, 40, WPP_3de096d7bee33433074a41eaae020079_Traceguids, P);
  v2 = *((_QWORD *)P + 1);
  if ( v2 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v2 + 64));
    UcpRemoveSessionContextFromSessionList(P, *((_QWORD *)P + 1));
    v3 = *((_QWORD *)P + 1);
    *((_QWORD *)P + 1) = 0;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v3 + 64));
    KeLeaveCriticalRegion();
    v4 = _InterlockedDecrement((volatile signed __int32 *)v3);
    if ( UxDebugCheckRefcount && v4 <= -1 )
      UlBugCheckEx(3u, v3, 0x41u, v4);
    if ( !v4 )
      UcFreeClientSession((PVOID)v3);
  }
  ObfDereferenceObject(*((PVOID *)P + 7));
  *((_DWORD *)P + 4) = 1668498293;
  ExFreePoolWithTag(P, 0);
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_(1053, 41, WPP_3de096d7bee33433074a41eaae020079_Traceguids);
}

```

## disassembly

```asm
0x1400bd7e4  mov     [rsp+arg_0], rbx
0x1400bd7e9  push    rdi
0x1400bd7ea  sub     rsp, 20h
0x1400bd7ee  mov     rbx, rcx
0x1400bd7f1  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd7f8  jz      short loc_1400BD813
0x1400bd7fa  mov     edx, 28h ; '('
0x1400bd7ff  lea     r8, WPP_3de096d7bee33433074a41eaae020079_Traceguids
0x1400bd806  mov     ecx, 41Dh
0x1400bd80b  mov     r9, rbx
0x1400bd80e  call    WPP_SF_q
0x1400bd813  mov     rdi, [rbx+8]
0x1400bd817  test    rdi, rdi
0x1400bd81a  jz      loc_1400BD8A9
0x1400bd820  call    cs:__imp_KeEnterCriticalRegion
0x1400bd827  nop     dword ptr [rax+rax+00h]
0x1400bd82c  mov     rcx, [rdi+40h]
0x1400bd830  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bd837  nop     dword ptr [rax+rax+00h]
0x1400bd83c  mov     rdx, [rbx+8]
0x1400bd840  mov     rcx, rbx
0x1400bd843  call    UcpRemoveSessionContextFromSessionList
0x1400bd848  mov     rdi, [rbx+8]
0x1400bd84c  mov     qword ptr [rbx+8], 0
0x1400bd854  mov     rcx, [rdi+40h]
0x1400bd858  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bd85f  nop     dword ptr [rax+rax+00h]
0x1400bd864  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd86b  nop     dword ptr [rax+rax+00h]
0x1400bd870  or      eax, 0FFFFFFFFh
0x1400bd873  lock xadd [rdi], eax
0x1400bd877  dec     eax
0x1400bd879  cmp     cs:UxDebugCheckRefcount, 0
0x1400bd880  jz      short loc_1400BD89D
0x1400bd882  cmp     eax, 0FFFFFFFFh
0x1400bd885  jg      short loc_1400BD89D
0x1400bd887  mov     r8d, 41h ; 'A'; BugCheckParameter3
0x1400bd88d  movsxd  r9, eax; BugCheckParameter4
0x1400bd890  mov     rdx, rdi; BugCheckParameter2
0x1400bd893  lea     ecx, [r8-3Eh]; BugCheckParameter1
0x1400bd897  call    UlBugCheckEx
0x1400bd89d  test    eax, eax
0x1400bd89f  jnz     short loc_1400BD8A9
0x1400bd8a1  mov     rcx, rdi; P
0x1400bd8a4  call    UcFreeClientSession
0x1400bd8a9  mov     rcx, [rbx+38h]; Object
0x1400bd8ad  call    cs:__imp_ObfDereferenceObject
0x1400bd8b4  nop     dword ptr [rax+rax+00h]
0x1400bd8b9  xor     edx, edx; Tag
0x1400bd8bb  mov     dword ptr [rbx+10h], 63734375h
0x1400bd8c2  mov     rcx, rbx; P
0x1400bd8c5  call    cs:__imp_ExFreePoolWithTag
0x1400bd8cc  nop     dword ptr [rax+rax+00h]
0x1400bd8d1  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd8d8  jz      short loc_1400BD8F0
0x1400bd8da  mov     edx, 29h ; ')'
0x1400bd8df  lea     r8, WPP_3de096d7bee33433074a41eaae020079_Traceguids
0x1400bd8e6  mov     ecx, 41Dh
0x1400bd8eb  call    WPP_SF_
0x1400bd8f0  mov     rbx, [rsp+28h+arg_0]
0x1400bd8f5  add     rsp, 20h
0x1400bd8f9  pop     rdi
0x1400bd8fa  retn
```

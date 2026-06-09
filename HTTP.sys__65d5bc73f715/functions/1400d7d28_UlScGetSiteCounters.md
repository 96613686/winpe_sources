# UlScGetSiteCounters

- ea: `0x1400d7d28`
- end: `0x1400d7f46`
- name: `UlScGetSiteCounters`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140016960`

## callees

- `0x14000a350`
- `0x1400b1c18`
- `0x1400d737c`
- `0x1400d7d28`
- `0x1400d8378`
- `0x1400d8460`
- `0x1401d9dd8`
- `0x1401da4fc`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7dac`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7dac`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7e8c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7e8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7e7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7e98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7e7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7e98`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d7df1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d7df1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d7e6f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d7e6f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7d97`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7dd8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7d97`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7dd8`

## pseudocode

```c
__int64 __fastcall UlScGetSiteCounters(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v5; // ebp
  __int64 v9; // rsi
  unsigned int *v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rbx
  int ServerSessionFromId; // edi
  unsigned int v14; // eax
  char *v15; // rax
  char *v16; // r12
  char *v17; // rdx
  int v18; // eax
  PVOID P; // [rsp+90h] [rbp+8h] BYREF

  v5 = a4;
  P = 0;
  v9 = a3;
  v10 = a5;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqqdq(1049, 27, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids, a1, a2, a3, a4, a5);
  *v10 = 0;
  v11 = *(_QWORD *)(a1 + 56);
  KeEnterCriticalRegion();
  v12 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v11 + 1368), 0);
  ServerSessionFromId = UlGetServerSessionFromId(a1, a2, &P);
  if ( ServerSessionFromId >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(*(_QWORD *)(a1 + 56) + 1408LL, 0);
    v14 = 72 * *((_DWORD *)P + 22);
    if ( a3 && v14 <= v5 )
    {
      v15 = (char *)P + 72;
      v16 = (char *)*((_QWORD *)P + 9);
      while ( v16 != v15 && v5 >= 0x48 )
      {
        UlpCopyUrlGroupCounters(v16 + 16, v9);
        UlpScResetSiteCounters(v16 - 8);
        v9 += 72;
        v16 = *(char **)v16;
        v5 -= 72;
        v15 = (char *)P + 72;
      }
    }
    else
    {
      *v10 = v14;
      ServerSessionFromId = -2147483643;
    }
    ExReleasePushLockSharedEx(*(_QWORD *)(a1 + 56) + 1408LL, 0);
    KeLeaveCriticalRegion();
  }
  ExReleaseCacheAwarePushLockSharedEx(v12, 0);
  KeLeaveCriticalRegion();
  if ( P )
  {
    v17 = (char *)P + 4;
    v18 = _InterlockedDecrement((volatile signed __int32 *)P + 1);
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v17, 0xBu, v18);
    if ( !v18 )
      UlFreeServerSession(P);
    P = 0;
  }
  if ( ServerSessionFromId >= 0 )
    *v10 = v9 - a3;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLd(1049, 28, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids, a3, *v10, ServerSessionFromId);
  return (unsigned int)ServerSessionFromId;
}

```

## disassembly

```asm
0x1400d7d28  mov     rax, rsp
0x1400d7d2b  push    rbx
0x1400d7d2c  push    rbp
0x1400d7d2d  push    rsi
0x1400d7d2e  push    rdi
0x1400d7d2f  push    r12
0x1400d7d31  push    r13
0x1400d7d33  push    r14
0x1400d7d35  push    r15
0x1400d7d37  sub     rsp, 48h
0x1400d7d3b  mov     ebp, r9d
0x1400d7d3e  mov     qword ptr [rax+8], 0
0x1400d7d46  mov     r15, r8
0x1400d7d49  mov     rdi, rdx
0x1400d7d4c  mov     r13, rcx
0x1400d7d4f  mov     rsi, r8
0x1400d7d52  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x1400d7d59  mov     r14, [rsp+88h+arg_20]
0x1400d7d61  jz      short loc_1400D7D8C
0x1400d7d63  mov     [rax-50h], r14
0x1400d7d67  mov     edx, 1Bh
0x1400d7d6c  mov     [rax-58h], r9d
0x1400d7d70  mov     ecx, 419h
0x1400d7d75  mov     [rax-60h], r8
0x1400d7d79  mov     r9, r13
0x1400d7d7c  lea     r8, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids
0x1400d7d83  mov     [rax-68h], rdi
0x1400d7d87  call    WPP_SF_qqqdq
0x1400d7d8c  mov     dword ptr [r14], 0
0x1400d7d93  mov     rbx, [r13+38h]
0x1400d7d97  call    cs:__imp_KeEnterCriticalRegion
0x1400d7d9e  nop     dword ptr [rax+rax+00h]
0x1400d7da3  mov     rcx, [rbx+558h]
0x1400d7daa  xor     edx, edx
0x1400d7dac  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d7db3  nop     dword ptr [rax+rax+00h]
0x1400d7db8  lea     r8, [rsp+88h+P]
0x1400d7dc0  mov     rdx, rdi
0x1400d7dc3  mov     rcx, r13
0x1400d7dc6  mov     rbx, rax
0x1400d7dc9  call    UlGetServerSessionFromId
0x1400d7dce  mov     edi, eax
0x1400d7dd0  test    eax, eax
0x1400d7dd2  js      loc_1400D7E87
0x1400d7dd8  call    cs:__imp_KeEnterCriticalRegion
0x1400d7ddf  nop     dword ptr [rax+rax+00h]
0x1400d7de4  mov     rcx, [r13+38h]
0x1400d7de8  xor     edx, edx
0x1400d7dea  add     rcx, 580h
0x1400d7df1  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400d7df8  nop     dword ptr [rax+rax+00h]
0x1400d7dfd  mov     rdx, [rsp+88h+P]
0x1400d7e05  mov     ecx, [rdx+58h]
0x1400d7e08  lea     eax, [rcx+rcx*8]
0x1400d7e0b  shl     eax, 3
0x1400d7e0e  test    r15, r15
0x1400d7e11  jz      short loc_1400D7E5A
0x1400d7e13  cmp     eax, ebp
0x1400d7e15  ja      short loc_1400D7E5A
0x1400d7e17  lea     rax, [rdx+48h]
0x1400d7e1b  mov     r12, [rax]
0x1400d7e1e  jmp     short loc_1400D7E53
0x1400d7e20  cmp     ebp, 48h ; 'H'
0x1400d7e23  jb      short loc_1400D7E62
0x1400d7e25  lea     rcx, [r12+10h]
0x1400d7e2a  mov     rdx, rsi
0x1400d7e2d  call    UlpCopyUrlGroupCounters
0x1400d7e32  lea     rcx, [r12-8]
0x1400d7e37  call    UlpScResetSiteCounters
0x1400d7e3c  mov     rax, [rsp+88h+P]
0x1400d7e44  add     rsi, 48h ; 'H'
0x1400d7e48  mov     r12, [r12]
0x1400d7e4c  add     ebp, 0FFFFFFB8h
0x1400d7e4f  add     rax, 48h ; 'H'
0x1400d7e53  cmp     r12, rax
0x1400d7e56  jnz     short loc_1400D7E20
0x1400d7e58  jmp     short loc_1400D7E62
0x1400d7e5a  mov     [r14], eax
0x1400d7e5d  mov     edi, 80000005h
0x1400d7e62  mov     rcx, [r13+38h]
0x1400d7e66  xor     edx, edx
0x1400d7e68  add     rcx, 580h
0x1400d7e6f  call    cs:__imp_ExReleasePushLockSharedEx
0x1400d7e76  nop     dword ptr [rax+rax+00h]
0x1400d7e7b  call    cs:__imp_KeLeaveCriticalRegion
0x1400d7e82  nop     dword ptr [rax+rax+00h]
0x1400d7e87  xor     edx, edx
0x1400d7e89  mov     rcx, rbx
0x1400d7e8c  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d7e93  nop     dword ptr [rax+rax+00h]
0x1400d7e98  call    cs:__imp_KeLeaveCriticalRegion
0x1400d7e9f  nop     dword ptr [rax+rax+00h]
0x1400d7ea4  mov     rdx, [rsp+88h+P]
0x1400d7eac  test    rdx, rdx
0x1400d7eaf  jz      short loc_1400D7EFB
0x1400d7eb1  add     rdx, 4; BugCheckParameter2
0x1400d7eb5  or      eax, 0FFFFFFFFh
0x1400d7eb8  lock xadd [rdx], eax
0x1400d7ebc  dec     eax
0x1400d7ebe  cmp     cs:UxDebugCheckRefcount, 0
0x1400d7ec5  jz      short loc_1400D7EDE
0x1400d7ec7  cmp     eax, 0FFFFFFFFh
0x1400d7eca  jg      short loc_1400D7EDE
0x1400d7ecc  mov     ecx, 3; BugCheckParameter1
0x1400d7ed1  movsxd  r9, eax; BugCheckParameter4
0x1400d7ed4  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d7ed8  call    UlBugCheckEx
0x1400d7ede  test    eax, eax
0x1400d7ee0  jnz     short loc_1400D7EEF
0x1400d7ee2  mov     rcx, [rsp+88h+P]; P
0x1400d7eea  call    UlFreeServerSession
0x1400d7eef  mov     [rsp+88h+P], 0
0x1400d7efb  test    edi, edi
0x1400d7efd  js      short loc_1400D7F05
0x1400d7eff  sub     esi, r15d
0x1400d7f02  mov     [r14], esi
0x1400d7f05  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x1400d7f0c  jz      short loc_1400D7F32
0x1400d7f0e  mov     eax, [r14]
0x1400d7f11  lea     r8, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids
0x1400d7f18  mov     edx, 1Ch
0x1400d7f1d  mov     [rsp+88h+var_60], edi
0x1400d7f21  mov     ecx, 419h
0x1400d7f26  mov     [rsp+88h+var_68], eax
0x1400d7f2a  mov     r9, r15
0x1400d7f2d  call    WPP_SF_qLd
0x1400d7f32  mov     eax, edi
0x1400d7f34  add     rsp, 48h
0x1400d7f38  pop     r15
0x1400d7f3a  pop     r14
0x1400d7f3c  pop     r13
0x1400d7f3e  pop     r12
0x1400d7f40  pop     rdi
0x1400d7f41  pop     rsi
0x1400d7f42  pop     rbp
0x1400d7f43  pop     rbx
0x1400d7f44  retn
```

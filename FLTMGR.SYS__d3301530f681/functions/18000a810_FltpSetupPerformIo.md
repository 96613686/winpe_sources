# FltpSetupPerformIo

- ea: `0x18000a810`
- end: `0x18000ad8c`
- name: `FltpSetupPerformIo`
- size: `1404`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18006fc70`

## callees

- `0x180005a50`
- `0x180009f20`
- `0x18000a810`
- `0x18000bfa0`
- `0x180024800`
- `0x180024c40`
- `0x180074e60`

## import_xrefs

- `ntoskrnl!IoAllocateIrpEx` at `0x18000a9fb`
- `ntoskrnl!IoAllocateIrpEx` at `0x18000a9fb`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18000a8d1`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18000a8d1`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18000a926`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18000a926`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a908`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a908`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a978`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a978`
- `ntoskrnl!ExReleaseFastResource` at `0x18000a96c`
- `ntoskrnl!ExReleaseFastResource` at `0x18000a96c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x18000a8f9`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x18000a8f9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000a8e8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000a8e8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000aaf5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000acba`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000aaf5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000acba`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000a995`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000a995`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18000a989`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18000a989`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18000ac05`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18000ac05`
- `ntoskrnl!IoSetIoPriorityHint` at `0x18000ac37`
- `ntoskrnl!IoSetIoPriorityHint` at `0x18000ac37`

## pseudocode

```c
__int64 __fastcall FltpSetupPerformIo(
        __int64 a1,
        __int64 a2,
        char a3,
        struct _KTHREAD *CurrentThread,
        __int64 a5,
        _QWORD *a6)
{
  _QWORD *v6; // rbx
  __int64 v8; // r13
  __int64 v9; // rcx
  unsigned __int8 v10; // cl
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // r12
  __int64 v16; // r15
  __int64 v17; // r8
  __int64 *v18; // rbx
  __int64 *i; // rdi
  __int64 v20; // rdx
  __int64 Irp; // rax
  _DWORD *v22; // r8
  __int64 v23; // r9
  int v24; // eax
  __int64 v25; // r10
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // ebx
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  struct _FILE_OBJECT *v33; // rdx
  unsigned int v34; // eax
  bool v36; // zf
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  _BYTE v41[80]; // [rsp+30h] [rbp-98h] BYREF
  struct _IO_PRIORITY_INFO PriorityInfo; // [rsp+80h] [rbp-48h] BYREF

  v6 = a6;
  v8 = *(_QWORD *)(a1 + 72);
  v9 = *(_QWORD *)(a1 + 248);
  *(_BYTE *)(a1 + 12) = *(_BYTE *)(v9 + 4);
  if ( !CurrentThread )
    CurrentThread = KeGetCurrentThread();
  *(_QWORD *)(a1 + 240) = CurrentThread;
  v10 = *(_BYTE *)(v9 + 4) + 22;
  *a6 = 0;
  v11 = v10;
  if ( (*(_DWORD *)(a1 + 4) & 0x200) != 0 )
  {
    v12 = *(_QWORD *)(v8 + 8LL * v10 + 304);
    if ( v12
      && (*(_DWORD *)(v8 + 80) & 6) == 0
      && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v8 + 56), 1u) )
    {
      goto LABEL_9;
    }
    *a6 = 0;
  }
  *(_QWORD *)&PriorityInfo.Size = a6;
  v12 = 0;
  memset(v41, 0, 0x48u);
  ExInitializeFastOwnerEntry(v41);
  v13 = *(_QWORD *)(v8 + 64);
  v14 = qword_18003EF20;
  KeEnterGuardedRegion();
  v15 = ExAcquireCacheAwarePushLockSharedEx(v14, 0);
  KeEnterCriticalRegion();
  v16 = v13 + 192;
  LOBYTE(v17) = 1;
  ExAcquireFastResourceShared(v13 + 192, v41, v17);
  v18 = *(__int64 **)(v8 + 16);
  for ( i = (__int64 *)(v13 + 296); v18 != i; v12 = 0 )
  {
    if ( (v18[8] & 6) == 0 )
    {
      v12 = v18[v11 + 36];
      if ( v12 )
      {
        if ( ExAcquireRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)v18[5], 1u) )
          break;
      }
    }
    v18 = (__int64 *)*v18;
  }
  ExReleaseFastResource(v16, v41);
  KeLeaveCriticalRegion();
  ExReleaseCacheAwarePushLockSharedEx(v15, 0);
  KeLeaveGuardedRegion();
  v6 = *(_QWORD **)&PriorityInfo.Size;
LABEL_9:
  *v6 = v12;
  if ( !a3 )
  {
    v20 = *(_QWORD *)(a1 + 48);
    if ( !v20 )
    {
      Irp = IoAllocateIrpEx(*(_QWORD *)(a1 + 104), *(unsigned __int8 *)(*(_QWORD *)(a1 + 104) + 76LL), 0);
      v20 = Irp;
      if ( !Irp )
        return 3221225626LL;
      *(_DWORD *)(a1 + 4) |= 0x1000000u;
      *(_QWORD *)(a1 + 48) = Irp;
    }
    v22 = (_DWORD *)(a1 + 232);
    v23 = *(_QWORD *)(a1 + 248);
    v24 = *(unsigned __int8 *)(v23 + 4);
    if ( v24 == 27 )
    {
LABEL_24:
      v29 = FltpBuildRequest(a1 + 232, 0);
LABEL_25:
      v28 = v29;
      goto LABEL_26;
    }
    if ( v24 != 15 )
    {
      switch ( *(_BYTE *)(v23 + 4) )
      {
        case 0:
        case 1:
        case 0x13:
        case 0x17:
          v28 = -1073741822;
          goto LABEL_26;
        case 2:
        case 0x12:
          v29 = FltpBuildCleanupRequest(a1 + 232);
          goto LABEL_25;
        case 3:
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
        case 0xA:
        case 0xB:
        case 0xC:
        case 0x10:
        case 0x11:
        case 0x14:
        case 0x15:
        case 0x16:
        case 0x19:
        case 0x1A:
          goto LABEL_24;
        case 0xD:
          v37 = *(unsigned __int8 *)(v23 + 5);
          if ( v37 == 4 || !*(_BYTE *)(v23 + 5) )
            goto LABEL_49;
          v38 = v37 - 1;
          if ( v38 && (v39 = v38 - 1) != 0 )
          {
            if ( v39 == 1 )
            {
LABEL_49:
              v29 = FltpBuildDeviceControlRequest(a1 + 232);
              goto LABEL_25;
            }
LABEL_57:
            v28 = -1073741811;
          }
          else
          {
            v28 = -1073741823;
          }
          break;
        case 0xE:
          goto LABEL_15;
        default:
          goto LABEL_57;
      }
      goto LABEL_26;
    }
LABEL_15:
    v25 = *(_QWORD *)(v20 + 184);
    *(_QWORD *)(v20 + 152) = KeGetCurrentThread();
    *(_BYTE *)(v20 + 64) = 0;
    *(_QWORD *)(v20 + 72) = 0;
    *(_DWORD *)(v20 + 16) |= **(_DWORD **)(a1 + 248);
    *(_BYTE *)(v25 - 72) = *(_BYTE *)(*(_QWORD *)(a1 + 248) + 4LL);
    *(_BYTE *)(v25 - 71) = *(_BYTE *)(*(_QWORD *)(a1 + 248) + 5LL);
    *(_BYTE *)(v25 - 70) = *(_BYTE *)(*(_QWORD *)(a1 + 248) + 6LL);
    *(_OWORD *)(v25 - 64) = *(_OWORD *)(v23 + 24);
    *(_QWORD *)(v25 - 48) = *(_QWORD *)(v23 + 40);
    *(_BYTE *)(v25 - 69) = 0;
    v26 = *(_QWORD *)(*(_QWORD *)(a1 + 248) + 8LL);
    if ( !v26 )
      v26 = *(_QWORD *)(a1 + 112);
    *(_QWORD *)(v25 - 24) = v26;
    *(_QWORD *)(v25 - 32) = *(_QWORD *)(a1 + 104);
    v27 = *(_DWORD *)(v23 + 40) & 3;
    if ( v27 == 3 )
    {
      *(_QWORD *)(v20 + 112) = *(_QWORD *)(v23 + 56);
      *(_QWORD *)(v25 - 40) = *(_QWORD *)(v23 + 48);
    }
    else if ( v27 )
    {
      if ( (unsigned int)(v27 - 1) <= 1 )
      {
        *(_QWORD *)(v20 + 24) = *(_QWORD *)(v23 + 48);
        *(_QWORD *)(v25 - 40) = 0;
        *(_QWORD *)(v20 + 8) = *(_QWORD *)(v23 + 64);
        if ( *(_DWORD *)(v25 - 56) )
        {
          *v22 |= 8u;
          *(_DWORD *)(v20 + 16) |= 0x10u;
        }
      }
    }
    else
    {
      *(_QWORD *)(v20 + 24) = *(_QWORD *)(v23 + 48);
      v36 = *(_DWORD *)(v25 - 56) == 0;
      *(_QWORD *)(v25 - 40) = 0;
      if ( !v36 || *(_DWORD *)(v25 - 64) )
      {
        *v22 |= 8u;
        *(_DWORD *)(v20 + 16) |= 0x10u;
        v28 = 0;
        goto LABEL_26;
      }
    }
    v28 = 0;
LABEL_26:
    if ( (int)FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 1220, 0) >= 0 )
    {
      v30 = *(_QWORD *)(a1 + 48);
      v31 = *(_QWORD *)(v30 + 184);
      *(_QWORD *)(v31 - 16) = 0;
      *(_QWORD *)(v31 - 8) = 0;
      *(_BYTE *)(v31 - 69) = 0;
      --*(_BYTE *)(v30 + 67);
      *(_QWORD *)(v30 + 184) -= 72LL;
      **(_DWORD **)(a1 + 248) = *(_DWORD *)(v30 + 16);
      *(_BYTE *)(a1 + 312) = *(_BYTE *)(v30 + 64);
    }
    FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 667, 0);
    goto LABEL_29;
  }
  v28 = 0;
LABEL_29:
  if ( (*(_DWORD *)(a1 + 232) & 1) != 0 )
  {
    v32 = *(_QWORD *)(a1 + 248);
    PriorityInfo.Size = 16;
    *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
    PriorityInfo.IoPriority = IoPriorityNormal;
    v33 = *(struct _FILE_OBJECT **)(v32 + 8);
    if ( !v33 )
      v33 = *(struct _FILE_OBJECT **)(a1 + 112);
    v34 = IoRetrievePriorityInfo(*(PIRP *)(a1 + 48), v33, KeGetCurrentThread(), &PriorityInfo);
    if ( (int)FltpDbgStatus(v34, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 10024, 0) >= 0 )
      IoSetIoPriorityHint(*(PIRP *)(a1 + 48), PriorityInfo.IoPriority);
  }
  return v28;
}

```

## disassembly

```asm
0x18000a810  mov     r11, rsp
0x18000a813  push    rbx
0x18000a814  push    rbp
0x18000a815  sub     rsp, 0B8h
0x18000a81c  mov     rax, cs:__security_cookie
0x18000a823  xor     rax, rsp
0x18000a826  mov     [rsp+0C8h+var_38], rax
0x18000a82e  mov     rbx, [rsp+0C8h+arg_28]
0x18000a836  mov     rbp, rcx
0x18000a839  mov     [r11+10h], rsi
0x18000a83d  mov     [r11-18h], r13
0x18000a841  mov     r13, [rcx+48h]
0x18000a845  mov     rcx, [rcx+0F8h]
0x18000a84c  mov     [r11-20h], r14
0x18000a850  mov     [rsp+0C8h+var_A8], r8b
0x18000a855  mov     [rsp+0C8h+var_A4], 0
0x18000a85d  movzx   eax, byte ptr [rcx+4]
0x18000a861  mov     [rbp+0Ch], al
0x18000a864  test    r9, r9
0x18000a867  jnz     short loc_18000A872
0x18000a869  mov     r9, gs:188h
0x18000a872  mov     [rbp+0F0h], r9
0x18000a879  movzx   ecx, byte ptr [rcx+4]
0x18000a87d  add     cl, 16h
0x18000a880  mov     qword ptr [rbx], 0
0x18000a887  test    dword ptr [rbp+4], 200h
0x18000a88e  movzx   r14d, cl
0x18000a892  jnz     loc_18000AB0E
0x18000a898  mov     [rsp+0C8h+arg_10], rdi
0x18000a8a0  lea     rcx, [rsp+0C8h+var_98]; void *
0x18000a8a5  mov     [rsp+0C8h+arg_18], r12
0x18000a8ad  xor     edx, edx; Val
0x18000a8af  mov     r8d, 48h ; 'H'; Size
0x18000a8b5  mov     [rsp+0C8h+var_28], r15
0x18000a8bd  mov     qword ptr [rsp+0C8h+PriorityInfo.Size], rbx
0x18000a8c5  xor     esi, esi
0x18000a8c7  call    memset
0x18000a8cc  lea     rcx, [rsp+0C8h+var_98]
0x18000a8d1  call    cs:__imp_ExInitializeFastOwnerEntry
0x18000a8d8  nop     dword ptr [rax+rax+00h]
0x18000a8dd  mov     rdi, [r13+40h]
0x18000a8e1  mov     rbx, cs:qword_18003EF20
0x18000a8e8  call    cs:__imp_KeEnterGuardedRegion
0x18000a8ef  nop     dword ptr [rax+rax+00h]
0x18000a8f4  xor     edx, edx
0x18000a8f6  mov     rcx, rbx
0x18000a8f9  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x18000a900  nop     dword ptr [rax+rax+00h]
0x18000a905  mov     r12, rax
0x18000a908  call    cs:__imp_KeEnterCriticalRegion
0x18000a90f  nop     dword ptr [rax+rax+00h]
0x18000a914  lea     r15, [rdi+0C0h]
0x18000a91b  mov     r8b, 1
0x18000a91e  mov     rcx, r15
0x18000a921  lea     rdx, [rsp+0C8h+var_98]
0x18000a926  call    cs:__imp_ExAcquireFastResourceShared
0x18000a92d  nop     dword ptr [rax+rax+00h]
0x18000a932  mov     rbx, [r13+10h]
0x18000a936  add     rdi, 128h
0x18000a93d  cmp     rbx, rdi
0x18000a940  jz      short loc_18000A964
0x18000a942  mov     eax, [rbx+40h]
0x18000a945  test    al, 6
0x18000a947  jnz     short loc_18000A95A
0x18000a949  mov     rsi, [rbx+r14*8+120h]
0x18000a951  test    rsi, rsi
0x18000a954  jnz     loc_18000AAEC
0x18000a95a  mov     rbx, [rbx]
0x18000a95d  xor     esi, esi
0x18000a95f  cmp     rbx, rdi
0x18000a962  jnz     short loc_18000A942
0x18000a964  lea     rdx, [rsp+0C8h+var_98]
0x18000a969  mov     rcx, r15
0x18000a96c  call    cs:__imp_ExReleaseFastResource
0x18000a973  nop     dword ptr [rax+rax+00h]
0x18000a978  call    cs:__imp_KeLeaveCriticalRegion
0x18000a97f  nop     dword ptr [rax+rax+00h]
0x18000a984  xor     edx, edx
0x18000a986  mov     rcx, r12
0x18000a989  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x18000a990  nop     dword ptr [rax+rax+00h]
0x18000a995  call    cs:__imp_KeLeaveGuardedRegion
0x18000a99c  nop     dword ptr [rax+rax+00h]
0x18000a9a1  mov     rbx, qword ptr [rsp+0C8h+PriorityInfo.Size]
0x18000a9a9  mov     r15, [rsp+0C8h+var_28]
0x18000a9b1  mov     r12, [rsp+0C8h+arg_18]
0x18000a9b9  mov     rdi, [rsp+0C8h+arg_10]
0x18000a9c1  cmp     [rsp+0C8h+var_A8], 0
0x18000a9c6  mov     [rbx], rsi
0x18000a9c9  mov     r14, [rsp+0C8h+var_20]
0x18000a9d1  mov     r13, [rsp+0C8h+var_18]
0x18000a9d9  mov     rsi, [rsp+0C8h+arg_8]
0x18000a9e1  jnz     loc_18000AC60
0x18000a9e7  mov     rdx, [rbp+30h]
0x18000a9eb  test    rdx, rdx
0x18000a9ee  jnz     short loc_18000AA1E
0x18000a9f0  mov     rcx, [rbp+68h]
0x18000a9f4  xor     r8d, r8d
0x18000a9f7  movzx   edx, byte ptr [rcx+4Ch]
0x18000a9fb  call    cs:__imp_IoAllocateIrpEx
0x18000aa02  nop     dword ptr [rax+rax+00h]
0x18000aa07  mov     rdx, rax
0x18000aa0a  test    rax, rax
0x18000aa0d  jz      loc_18000AC9E
0x18000aa13  or      dword ptr [rbp+4], 1000000h
0x18000aa1a  mov     [rbp+30h], rax
0x18000aa1e  lea     r8, [rbp+0E8h]
0x18000aa25  mov     r9, [r8+10h]
0x18000aa29  movzx   eax, byte ptr [r9+4]
0x18000aa2e  cmp     eax, 1Bh
0x18000aa31  jz      loc_18000AB2E; jumptable 000000018000AD31 cases 3-12,16,17,20-22,25,26
0x18000aa37  cmp     eax, 0Fh
0x18000aa3a  jnz     loc_18000AD11
0x18000aa40  mov     rax, gs:188h; jumptable 000000018000AD31 case 14
0x18000aa49  mov     r10, [rdx+0B8h]
0x18000aa50  mov     [rdx+98h], rax
0x18000aa57  mov     byte ptr [rdx+40h], 0
0x18000aa5b  mov     qword ptr [rdx+48h], 0
0x18000aa63  mov     rax, [r8+10h]
0x18000aa67  mov     ecx, [rax]
0x18000aa69  or      [rdx+10h], ecx
0x18000aa6c  mov     rax, [r8+10h]
0x18000aa70  movzx   ecx, byte ptr [rax+4]
0x18000aa74  mov     [r10-48h], cl
0x18000aa78  mov     rax, [r8+10h]
0x18000aa7c  movzx   ecx, byte ptr [rax+5]
0x18000aa80  mov     [r10-47h], cl
0x18000aa84  mov     rax, [r8+10h]
0x18000aa88  movzx   ecx, byte ptr [rax+6]
0x18000aa8c  mov     [r10-46h], cl
0x18000aa90  movups  xmm0, xmmword ptr [r9+18h]
0x18000aa95  movups  xmmword ptr [r10-40h], xmm0
0x18000aa9a  movsd   xmm1, qword ptr [r9+28h]
0x18000aaa0  movsd   qword ptr [r10-30h], xmm1
0x18000aaa6  mov     byte ptr [r10-45h], 0
0x18000aaab  mov     rax, [r8+10h]
0x18000aaaf  mov     rcx, [rax+8]
0x18000aab3  test    rcx, rcx
0x18000aab6  jnz     short loc_18000AABC
0x18000aab8  mov     rcx, [r8-78h]
0x18000aabc  mov     [r10-18h], rcx
0x18000aac0  mov     rax, [r8-80h]
0x18000aac4  mov     [r10-20h], rax
0x18000aac8  mov     eax, [r9+28h]
0x18000aacc  and     eax, 3
0x18000aacf  cmp     eax, 3
0x18000aad2  jnz     loc_18000AC69
0x18000aad8  mov     rax, [r9+38h]
0x18000aadc  mov     [rdx+70h], rax
0x18000aae0  mov     rax, [r9+30h]
0x18000aae4  mov     [r10-28h], rax
0x18000aae8  xor     ebx, ebx
0x18000aaea  jmp     short loc_18000AB3A
0x18000aaec  mov     rcx, [rbx+28h]; RunRefCacheAware
0x18000aaf0  mov     edx, 1; Count
0x18000aaf5  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18000aafc  nop     dword ptr [rax+rax+00h]
0x18000ab01  test    al, al
0x18000ab03  jz      loc_18000A95A
0x18000ab09  jmp     loc_18000A964
0x18000ab0e  movzx   eax, cl
0x18000ab11  mov     rsi, [r13+rax*8+130h]
0x18000ab19  test    rsi, rsi
0x18000ab1c  jnz     loc_18000ACA5
0x18000ab22  mov     qword ptr [rbx], 0
0x18000ab29  jmp     loc_18000A898
0x18000ab2e  xor     edx, edx; jumptable 000000018000AD31 cases 3-12,16,17,20-22,25,26
0x18000ab30  mov     rcx, r8
0x18000ab33  call    FltpBuildRequest
0x18000ab38  mov     ebx, eax
0x18000ab3a  mov     r8d, 4C4h
0x18000ab40  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18000ab47  xor     r9d, r9d
0x18000ab4a  mov     ecx, ebx
0x18000ab4c  call    FltpDbgStatus
0x18000ab51  test    eax, eax
0x18000ab53  js      short loc_18000AB95
0x18000ab55  mov     rdx, [rbp+30h]
0x18000ab59  mov     rax, [rdx+0B8h]
0x18000ab60  mov     qword ptr [rax-10h], 0
0x18000ab68  mov     qword ptr [rax-8], 0
0x18000ab70  mov     byte ptr [rax-45h], 0
0x18000ab74  dec     byte ptr [rdx+43h]
0x18000ab77  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x18000ab7f  mov     eax, [rdx+10h]
0x18000ab82  mov     rcx, [rbp+0F8h]
0x18000ab89  mov     [rcx], eax
0x18000ab8b  movzx   eax, byte ptr [rdx+40h]
0x18000ab8f  mov     [rbp+138h], al
0x18000ab95  mov     r8d, 29Bh
0x18000ab9b  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18000aba2  xor     r9d, r9d
0x18000aba5  mov     ecx, ebx
0x18000aba7  call    FltpDbgStatus
0x18000abac  mov     eax, [rbp+0E8h]
0x18000abb2  test    al, 1
0x18000abb4  jz      loc_18000AC43
0x18000abba  mov     rax, [rbp+0F8h]
0x18000abc1  mov     [rsp+0C8h+PriorityInfo.Size], 10h
0x18000abcc  mov     qword ptr [rsp+0C8h+PriorityInfo.ThreadPriority], 0FFFFh
0x18000abd8  mov     [rsp+0C8h+PriorityInfo.IoPriority], 2
0x18000abe3  mov     rdx, [rax+8]
0x18000abe7  test    rdx, rdx
0x18000abea  jnz     short loc_18000ABF0
0x18000abec  mov     rdx, [rbp+70h]; FileObject
0x18000abf0  mov     r8, gs:188h; Thread
0x18000abf9  lea     r9, [rsp+0C8h+PriorityInfo]; PriorityInfo
0x18000ac01  mov     rcx, [rbp+30h]; Irp
0x18000ac05  call    cs:__imp_IoRetrievePriorityInfo
0x18000ac0c  nop     dword ptr [rax+rax+00h]
0x18000ac11  mov     r8d, 2728h
0x18000ac17  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18000ac1e  mov     ecx, eax
0x18000ac20  xor     r9d, r9d
0x18000ac23  call    FltpDbgStatus
0x18000ac28  test    eax, eax
0x18000ac2a  js      short loc_18000AC43
0x18000ac2c  mov     edx, [rsp+0C8h+PriorityInfo.IoPriority]; PriorityHint
0x18000ac33  mov     rcx, [rbp+30h]; Irp
0x18000ac37  call    cs:__imp_IoSetIoPriorityHint
0x18000ac3e  nop     dword ptr [rax+rax+00h]
0x18000ac43  mov     eax, ebx
0x18000ac45  mov     rcx, [rsp+0C8h+var_38]
0x18000ac4d  xor     rcx, rsp; StackCookie
0x18000ac50  call    __security_check_cookie
0x18000ac55  add     rsp, 0B8h
0x18000ac5c  pop     rbp
0x18000ac5d  pop     rbx
0x18000ac5e  retn
0x18000ac60  mov     ebx, [rsp+0C8h+var_A4]
0x18000ac64  jmp     loc_18000ABAC
0x18000ac69  test    eax, eax
0x18000ac6b  jnz     short loc_18000ACD3
0x18000ac6d  mov     rax, [r9+30h]
0x18000ac71  mov     [rdx+18h], rax
0x18000ac75  cmp     dword ptr [r10-38h], 0
0x18000ac7a  mov     qword ptr [r10-28h], 0
0x18000ac82  jnz     short loc_18000AC8F
0x18000ac84  cmp     dword ptr [r10-40h], 0
0x18000ac89  jz      loc_18000AAE8
0x18000ac8f  or      dword ptr [r8], 8
0x18000ac93  or      dword ptr [rdx+10h], 10h
0x18000ac97  xor     ebx, ebx
0x18000ac99  jmp     loc_18000AB3A
0x18000ac9e  mov     eax, 0C000009Ah
0x18000aca3  jmp     short loc_18000AC45
0x18000aca5  mov     eax, [r13+50h]
0x18000aca9  test    al, 6
0x18000acab  jnz     loc_18000AB22
0x18000acb1  mov     rcx, [r13+38h]; RunRefCacheAware
0x18000acb5  mov     edx, 1; Count
0x18000acba  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18000acc1  nop     dword ptr [rax+rax+00h]
0x18000acc6  test    al, al
0x18000acc8  jnz     loc_18000A9C1
0x18000acce  jmp     loc_18000AB22
0x18000acd3  sub     eax, 1
0x18000acd6  jz      short loc_18000ACE1
0x18000acd8  cmp     eax, 1
0x18000acdb  jnz     loc_18000AAE8
0x18000ace1  mov     rax, [r9+30h]
0x18000ace5  mov     [rdx+18h], rax
0x18000ace9  mov     qword ptr [r10-28h], 0
0x18000acf1  mov     rax, [r9+40h]
0x18000acf5  mov     [rdx+8], rax
0x18000acf9  cmp     dword ptr [r10-38h], 0
0x18000acfe  jz      loc_18000AAE8
0x18000ad04  or      dword ptr [r8], 8
0x18000ad08  or      dword ptr [rdx+10h], 10h
0x18000ad0c  jmp     loc_18000AAE8
0x18000ad11  cmp     eax, 1Ah; switch 27 cases
0x18000ad14  ja      short def_18000AD31; jumptable 000000018000AD31 default case, cases 15,24
0x18000ad16  lea     r10, cs:180000000h
0x18000ad1d  movzx   eax, ds:(byte_180031C90 - 180000000h)[r10+rax]
0x18000ad26  mov     ecx, ds:(jpt_18000AD31 - 180000000h)[r10+rax*4]
0x18000ad2e  add     rcx, r10
0x18000ad31  jmp     rcx; switch jump
0x18000ad37  movzx   ecx, byte ptr [r9+5]; jumptable 000000018000AD31 case 13
0x18000ad3c  cmp     ecx, 4
0x18000ad3f  jnz     short loc_18000AD4E
0x18000ad41  mov     rcx, r8
0x18000ad44  call    FltpBuildDeviceControlRequest
0x18000ad49  jmp     loc_18000AB38
0x18000ad4e  test    ecx, ecx
0x18000ad50  jz      short loc_18000AD41
0x18000ad52  sub     ecx, 1
0x18000ad55  jz      short loc_18000AD5C
0x18000ad57  sub     ecx, 1
0x18000ad5a  jnz     short loc_18000AD7D
0x18000ad5c  mov     ebx, 0C0000001h
0x18000ad61  jmp     loc_18000AB3A
0x18000ad66  mov     rcx, r8; jumptable 000000018000AD31 cases 2,18
0x18000ad69  call    FltpBuildCleanupRequest
0x18000ad6e  jmp     loc_18000AB38
0x18000ad73  mov     ebx, 0C0000002h; jumptable 000000018000AD31 cases 0,1,19,23
0x18000ad78  jmp     loc_18000AB3A
0x18000ad7d  cmp     ecx, 1
0x18000ad80  jz      short loc_18000AD41
0x18000ad82  mov     ebx, 0C000000Dh; jumptable 000000018000AD31 default case, cases 15,24
0x18000ad87  jmp     loc_18000AB3A
  ... truncated ...
```

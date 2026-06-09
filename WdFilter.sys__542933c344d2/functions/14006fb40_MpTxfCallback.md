# MpTxfCallback

- ea: `0x14006fb40`
- end: `0x14006ff26`
- name: `MpTxfCallback`
- size: `998`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400018a4`
- `0x140003460`
- `0x1400049dc`
- `0x1400118d0`
- `0x14006cb28`
- `0x14006fb40`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14006fd0d`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14006fd0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006fdda`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006fdf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006fe1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006fdda`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006fdf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006fe1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006fdce`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006fdea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006fe10`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006fdce`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006fdea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006fe10`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fc0a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fc28`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fc50`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fc0a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fc28`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fc50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fbf5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fc16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fc3b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fbf5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fc16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fc3b`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14006fd3d`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14006fd3d`
- `ntoskrnl!KeBugCheck` at `0x14006fdb3`
- `ntoskrnl!KeBugCheck` at `0x14006fdb3`
- `FLTMGR!FltReleaseContext` at `0x14006fe7d`
- `FLTMGR!FltReleaseContext` at `0x14006fe7d`
- `FLTMGR!FltReleasePushLock` at `0x14006fd78`
- `FLTMGR!FltReleasePushLock` at `0x14006fd78`
- `FLTMGR!FltDeleteContext` at `0x14006fe6d`
- `FLTMGR!FltDeleteContext` at `0x14006fe6d`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14006fcef`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14006fcef`

## pseudocode

```c
__int64 __fastcall MpTxfCallback(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v7; // rbx
  char *v8; // rbx
  void **v9; // r15
  void *v10; // rdi
  void **v11; // rax
  __int64 v12; // rbx
  void *v13; // rcx
  _QWORD *v14; // rax
  PFLT_CONTEXT *v15; // rbx
  __int64 v16; // rax
  PFLT_CONTEXT v17; // rcx
  PVOID Entry[2]; // [rsp+20h] [rbp-20h] BYREF

  if ( !MpTxfData )
    return 3221225659LL;
  if ( a1 && a2 )
  {
    if ( ((a3 - 4) & 0xFFFFFFFB) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids, a3);
    }
    else
    {
      v7 = *(_QWORD *)(a2 + 128);
      Entry[1] = Entry;
      Entry[0] = Entry;
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)(v7 + 288), 1u);
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 8), 1u);
      v8 = (char *)MpTxfData;
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)(v8 + 192), 1u);
      v9 = (void **)(a2 + 136);
      while ( 1 )
      {
        v10 = *v9;
        if ( *v9 == v9 )
          break;
        if ( *((void ***)v10 + 1) != v9 )
          goto LABEL_42;
        v11 = *(void ***)v10;
        if ( *(void **)(*(_QWORD *)v10 + 8LL) != v10 )
          goto LABEL_42;
        *v9 = v11;
        v11[1] = v9;
        v12 = *((_QWORD *)v10 + 8);
        if ( a3 == 4 && (*(_DWORD *)(a2 + 168) & 1) == 0 )
        {
          *(_DWORD *)(v12 + 32) = 0;
          _InterlockedAnd((volatile signed __int32 *)(v12 + 48), 0xFFFFBFFF);
          _InterlockedExchange64((volatile __int64 *)(v12 + 176), *((_QWORD *)v10 + 4));
          _InterlockedExchange64((volatile __int64 *)(v12 + 40), 0);
          if ( (*((_DWORD *)v10 + 12) & 2) != 0 )
            _InterlockedOr((volatile signed __int32 *)(v12 + 48), 2u);
          else
            _InterlockedAnd((volatile signed __int32 *)(v12 + 48), 0xFFFFFFFD);
          if ( (*((_DWORD *)v10 + 12) & 4) != 0 )
            _InterlockedOr((volatile signed __int32 *)(v12 + 48), 4u);
          _InterlockedAnd((volatile signed __int32 *)(v12 + 48), 0xFFFFFFEF);
        }
        FltAcquirePushLockExclusive((PULONG_PTR)(v12 + 192));
        v13 = *(void **)(v12 + 200);
        if ( v13 && v13 == *(void **)(a1 + 40) )
        {
          ObDereferenceObjectDeferDelete(v13);
          if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
          {
            if ( KdRefreshDebuggerNotPresent() )
              KeBugCheck(1u);
            __debugbreak();
          }
          *(_QWORD *)(v12 + 200) = 0;
          *(_QWORD *)(v12 + 208) = 0;
        }
        else
        {
          *(_DWORD *)(v12 + 32) = 0;
          _InterlockedAnd((volatile signed __int32 *)(v12 + 48), 0xFFFFBFFF);
        }
        FltReleasePushLock((PULONG_PTR)(v12 + 192));
        v14 = Entry[0];
        if ( *((PVOID **)Entry[0] + 1) != Entry )
LABEL_42:
          __fastfail(3u);
        *(PVOID *)v10 = Entry[0];
        *((_QWORD *)v10 + 1) = Entry;
        v14[1] = v10;
        Entry[0] = v10;
      }
      ExReleaseResourceLite((PERESOURCE)((char *)MpTxfData + 192));
      KeLeaveCriticalRegion();
      ExReleaseResourceLite((PERESOURCE)(a2 + 8));
      KeLeaveCriticalRegion();
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a2 + 128) + 288LL));
      KeLeaveCriticalRegion();
      while ( 1 )
      {
        v15 = (PFLT_CONTEXT *)Entry[0];
        if ( Entry[0] == Entry )
          break;
        if ( *((PVOID **)Entry[0] + 1) != Entry )
          goto LABEL_42;
        v16 = *(_QWORD *)Entry[0];
        if ( *(PVOID *)(*(_QWORD *)Entry[0] + 8LL) != Entry[0] )
          goto LABEL_42;
        Entry[0] = *(PVOID *)Entry[0];
        *(_QWORD *)(v16 + 8) = Entry;
        v17 = v15[8];
        if ( v17 )
        {
          if ( (*(_DWORD *)(a2 + 168) & 1) != 0 && a3 == 4 )
            FltDeleteContext(v17);
          FltReleaseContext(v15[8]);
          v15[8] = 0;
        }
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpTxfData + 64), v15);
      }
      if ( (*(_DWORD *)(a2 + 168) & 1) != 0 && ((a3 - 4) & 0xFFFFFFFB) == 0 )
        MpPurgeInstanceScannedFileCache(*(_QWORD *)(a2 + 128));
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14006fb40  mov     [rsp-38h+arg_0], rbx
0x14006fb45  push    rbp
0x14006fb46  push    rsi
0x14006fb47  push    rdi
0x14006fb48  push    r12
0x14006fb4a  push    r13
0x14006fb4c  push    r14
0x14006fb4e  push    r15
0x14006fb50  mov     rbp, rsp
0x14006fb53  sub     rsp, 40h
0x14006fb57  mov     rax, cs:__security_cookie
0x14006fb5e  xor     rax, rsp
0x14006fb61  mov     [rbp+var_10], rax
0x14006fb65  cmp     cs:MpTxfData, 0
0x14006fb6d  mov     r14d, r8d
0x14006fb70  mov     rsi, rdx
0x14006fb73  mov     r13, rcx
0x14006fb76  jnz     short loc_14006FB82
0x14006fb78  mov     eax, 0C00000BBh
0x14006fb7d  jmp     loc_14006FF01
0x14006fb82  test    r13, r13
0x14006fb85  jz      loc_14006FED0
0x14006fb8b  test    rsi, rsi
0x14006fb8e  jz      loc_14006FED0
0x14006fb94  lea     eax, [r8-4]
0x14006fb98  test    eax, 0FFFFFFFBh
0x14006fb9d  jz      short loc_14006FBDE
0x14006fb9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fba6  lea     rax, WPP_GLOBAL_Control
0x14006fbad  cmp     rcx, rax
0x14006fbb0  jz      loc_14006FEFF
0x14006fbb6  mov     eax, [rcx+2Ch]
0x14006fbb9  test    al, 1
0x14006fbbb  jz      loc_14006FEFF
0x14006fbc1  mov     rcx, [rcx+18h]
0x14006fbc5  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x14006fbcc  mov     edx, 17h
0x14006fbd1  mov     r9d, r14d
0x14006fbd4  call    WPP_SF_d
0x14006fbd9  jmp     loc_14006FEFF
0x14006fbde  mov     rbx, [rdx+80h]
0x14006fbe5  lea     rax, [rbp+Entry]
0x14006fbe9  mov     [rbp+var_18], rax
0x14006fbed  lea     rax, [rbp+Entry]
0x14006fbf1  mov     [rbp+Entry], rax
0x14006fbf5  call    cs:__imp_KeEnterCriticalRegion
0x14006fbfc  nop     dword ptr [rax+rax+00h]
0x14006fc01  mov     dl, 1; Wait
0x14006fc03  lea     rcx, [rbx+120h]; Resource
0x14006fc0a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006fc11  nop     dword ptr [rax+rax+00h]
0x14006fc16  call    cs:__imp_KeEnterCriticalRegion
0x14006fc1d  nop     dword ptr [rax+rax+00h]
0x14006fc22  lea     rcx, [rsi+8]; Resource
0x14006fc26  mov     dl, 1; Wait
0x14006fc28  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006fc2f  nop     dword ptr [rax+rax+00h]
0x14006fc34  mov     rbx, cs:MpTxfData
0x14006fc3b  call    cs:__imp_KeEnterCriticalRegion
0x14006fc42  nop     dword ptr [rax+rax+00h]
0x14006fc47  mov     dl, 1; Wait
0x14006fc49  lea     rcx, [rbx+0C0h]; Resource
0x14006fc50  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006fc57  nop     dword ptr [rax+rax+00h]
0x14006fc5c  lea     r15, [rsi+88h]
0x14006fc63  mov     rdi, [r15]
0x14006fc66  cmp     rdi, r15
0x14006fc69  jz      loc_14006FDC0
0x14006fc6f  cmp     [rdi+8], r15
0x14006fc73  jnz     loc_14006FEA6
0x14006fc79  mov     rax, [rdi]
0x14006fc7c  cmp     [rax+8], rdi
0x14006fc80  jnz     loc_14006FEA6
0x14006fc86  mov     [r15], rax
0x14006fc89  mov     [rax+8], r15
0x14006fc8d  mov     rbx, [rdi+40h]
0x14006fc91  cmp     r14d, 4
0x14006fc95  jnz     short loc_14006FCE5
0x14006fc97  mov     eax, [rsi+0A8h]
0x14006fc9d  test    al, 1
0x14006fc9f  jnz     short loc_14006FCE5
0x14006fca1  mov     dword ptr [rbx+20h], 0
0x14006fca8  lock and dword ptr [rbx+30h], 0FFFFBFFFh
0x14006fcb0  mov     rax, [rdi+20h]
0x14006fcb4  xchg    rax, [rbx+0B0h]
0x14006fcbb  xor     eax, eax
0x14006fcbd  xchg    rax, [rbx+28h]
0x14006fcc1  mov     eax, [rdi+30h]
0x14006fcc4  test    al, 2
0x14006fcc6  jz      short loc_14006FCCF
0x14006fcc8  lock or dword ptr [rbx+30h], 2
0x14006fccd  jmp     short loc_14006FCD4
0x14006fccf  lock and dword ptr [rbx+30h], 0FFFFFFFDh
0x14006fcd4  mov     eax, [rdi+30h]
0x14006fcd7  test    al, 4
0x14006fcd9  jz      short loc_14006FCE0
0x14006fcdb  lock or dword ptr [rbx+30h], 4
0x14006fce0  lock and dword ptr [rbx+30h], 0FFFFFFEFh
0x14006fce5  lea     r12, [rbx+0C0h]
0x14006fcec  mov     rcx, r12; PushLock
0x14006fcef  call    cs:__imp_FltAcquirePushLockExclusive
0x14006fcf6  nop     dword ptr [rax+rax+00h]
0x14006fcfb  mov     rcx, [rbx+0C8h]; Object
0x14006fd02  test    rcx, rcx
0x14006fd05  jz      short loc_14006FD66
0x14006fd07  cmp     rcx, [r13+28h]
0x14006fd0b  jnz     short loc_14006FD66
0x14006fd0d  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14006fd14  nop     dword ptr [rax+rax+00h]
0x14006fd19  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006fd1d  lock xadd cs:ObTotalReferences, rax
0x14006fd26  cmp     rax, 1
0x14006fd2a  jns     short loc_14006FD4E
0x14006fd2c  mov     rax, cs:MpData
0x14006fd33  mov     ecx, [rax+364h]
0x14006fd39  test    ecx, ecx
0x14006fd3b  jns     short loc_14006FD4E
0x14006fd3d  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14006fd44  nop     dword ptr [rax+rax+00h]
0x14006fd49  test    al, al
0x14006fd4b  jnz     short loc_14006FDAE
0x14006fd4d  int     3; Trap to Debugger
0x14006fd4e  mov     qword ptr [rbx+0C8h], 0
0x14006fd59  mov     qword ptr [rbx+0D0h], 0
0x14006fd64  jmp     short loc_14006FD75
0x14006fd66  mov     dword ptr [rbx+20h], 0
0x14006fd6d  lock and dword ptr [rbx+30h], 0FFFFBFFFh
0x14006fd75  mov     rcx, r12; PushLock
0x14006fd78  call    cs:__imp_FltReleasePushLock
0x14006fd7f  nop     dword ptr [rax+rax+00h]
0x14006fd84  mov     rax, [rbp+Entry]
0x14006fd88  lea     rcx, [rbp+Entry]
0x14006fd8c  cmp     [rax+8], rcx
0x14006fd90  jnz     loc_14006FEA6
0x14006fd96  mov     [rdi], rax
0x14006fd99  lea     rcx, [rbp+Entry]
0x14006fd9d  mov     [rdi+8], rcx
0x14006fda1  mov     [rax+8], rdi
0x14006fda5  mov     [rbp+Entry], rdi
0x14006fda9  jmp     loc_14006FC63
0x14006fdae  mov     ecx, 1; BugCheckCode
0x14006fdb3  call    cs:__imp_KeBugCheck
0x14006fdc0  mov     rcx, cs:MpTxfData
0x14006fdc7  add     rcx, 0C0h; Resource
0x14006fdce  call    cs:__imp_ExReleaseResourceLite
0x14006fdd5  nop     dword ptr [rax+rax+00h]
0x14006fdda  call    cs:__imp_KeLeaveCriticalRegion
0x14006fde1  nop     dword ptr [rax+rax+00h]
0x14006fde6  lea     rcx, [rsi+8]; Resource
0x14006fdea  call    cs:__imp_ExReleaseResourceLite
0x14006fdf1  nop     dword ptr [rax+rax+00h]
0x14006fdf6  call    cs:__imp_KeLeaveCriticalRegion
0x14006fdfd  nop     dword ptr [rax+rax+00h]
0x14006fe02  mov     rcx, [rsi+80h]
0x14006fe09  add     rcx, 120h; Resource
0x14006fe10  call    cs:__imp_ExReleaseResourceLite
0x14006fe17  nop     dword ptr [rax+rax+00h]
0x14006fe1c  call    cs:__imp_KeLeaveCriticalRegion
0x14006fe23  nop     dword ptr [rax+rax+00h]
0x14006fe28  mov     rbx, [rbp+Entry]
0x14006fe2c  lea     rax, [rbp+Entry]
0x14006fe30  cmp     rbx, rax
0x14006fe33  jz      short loc_14006FEAD
0x14006fe35  lea     rax, [rbp+Entry]
0x14006fe39  cmp     [rbx+8], rax
0x14006fe3d  jnz     short loc_14006FEA6
0x14006fe3f  mov     rax, [rbx]
0x14006fe42  cmp     [rax+8], rbx
0x14006fe46  jnz     short loc_14006FEA6
0x14006fe48  lea     rcx, [rbp+Entry]
0x14006fe4c  mov     [rbp+Entry], rax
0x14006fe50  mov     [rax+8], rcx
0x14006fe54  mov     rcx, [rbx+40h]; Context
0x14006fe58  test    rcx, rcx
0x14006fe5b  jz      short loc_14006FE91
0x14006fe5d  mov     eax, [rsi+0A8h]
0x14006fe63  test    al, 1
0x14006fe65  jz      short loc_14006FE79
0x14006fe67  cmp     r14d, 4
0x14006fe6b  jnz     short loc_14006FE79
0x14006fe6d  call    cs:__imp_FltDeleteContext
0x14006fe74  nop     dword ptr [rax+rax+00h]
0x14006fe79  mov     rcx, [rbx+40h]; Context
0x14006fe7d  call    cs:__imp_FltReleaseContext
0x14006fe84  nop     dword ptr [rax+rax+00h]
0x14006fe89  mov     qword ptr [rbx+40h], 0
0x14006fe91  mov     rcx, cs:MpTxfData
0x14006fe98  mov     rdx, rbx; Entry
0x14006fe9b  add     rcx, 40h ; '@'; Lookaside
0x14006fe9f  call    ExFreeToNPagedLookasideList
0x14006fea4  jmp     short loc_14006FE28
0x14006fea6  mov     ecx, 3
0x14006feab  int     29h; Win8: RtlFailFast(ecx)
0x14006fead  mov     eax, [rsi+0A8h]
0x14006feb3  test    al, 1
0x14006feb5  jz      short loc_14006FEFF
0x14006feb7  lea     eax, [r14-4]
0x14006febb  test    eax, 0FFFFFFFBh
0x14006fec0  jnz     short loc_14006FEFF
0x14006fec2  mov     rcx, [rsi+80h]
0x14006fec9  call    MpPurgeInstanceScannedFileCache
0x14006fece  jmp     short loc_14006FEFF
0x14006fed0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fed7  lea     rax, WPP_GLOBAL_Control
0x14006fede  cmp     rcx, rax
0x14006fee1  jz      short loc_14006FEFF
0x14006fee3  mov     eax, [rcx+2Ch]
0x14006fee6  test    al, 1
0x14006fee8  jz      short loc_14006FEFF
0x14006feea  mov     rcx, [rcx+18h]
0x14006feee  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x14006fef5  mov     edx, 16h
0x14006fefa  call    WPP_SF_
0x14006feff  xor     eax, eax
0x14006ff01  mov     rcx, [rbp+var_10]
0x14006ff05  xor     rcx, rsp; StackCookie
0x14006ff08  call    __security_check_cookie
0x14006ff0d  mov     rbx, [rsp+40h+arg_0]
0x14006ff15  add     rsp, 40h
0x14006ff19  pop     r15
0x14006ff1b  pop     r14
0x14006ff1d  pop     r13
0x14006ff1f  pop     r12
0x14006ff21  pop     rdi
0x14006ff22  pop     rsi
0x14006ff23  pop     rbp
0x14006ff24  retn
```

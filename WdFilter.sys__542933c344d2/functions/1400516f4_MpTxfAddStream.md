# MpTxfAddStream

- ea: `0x1400516f4`
- end: `0x140051aee`
- name: `MpTxfAddStream`
- size: `1018`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140002d40`
- `0x140051af0`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x1400049dc`
- `0x1400052c8`
- `0x140011bc0`
- `0x1400516f4`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400517ab`
- `ntoskrnl!ObfReferenceObject` at `0x1400517ab`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400519b5`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400519b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005199d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005199d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051991`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051991`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005191a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005191a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140051907`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140051907`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005181d`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400519e6`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140051a36`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005181d`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400519e6`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140051a36`
- `ntoskrnl!KeBugCheck` at `0x140051a8b`
- `ntoskrnl!KeBugCheck` at `0x140051a8b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400517eb`
- `ntoskrnl!ObfDereferenceObject` at `0x140051a08`
- `ntoskrnl!ObfDereferenceObject` at `0x1400517eb`
- `ntoskrnl!ObfDereferenceObject` at `0x140051a08`
- `FLTMGR!FltReleaseContext` at `0x140051a55`
- `FLTMGR!FltReleaseContext` at `0x140051a55`
- `FLTMGR!FltAcquirePushLockShared` at `0x140051771`
- `FLTMGR!FltAcquirePushLockShared` at `0x140051771`
- `FLTMGR!FltReleasePushLock` at `0x14005178d`
- `FLTMGR!FltReleasePushLock` at `0x14005179b`
- `FLTMGR!FltReleasePushLock` at `0x140051981`
- `FLTMGR!FltReleasePushLock` at `0x14005178d`
- `FLTMGR!FltReleasePushLock` at `0x14005179b`
- `FLTMGR!FltReleasePushLock` at `0x140051981`
- `FLTMGR!FltReferenceContext` at `0x140051857`
- `FLTMGR!FltReferenceContext` at `0x140051857`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140051929`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140051929`

## pseudocode

```c
__int64 __fastcall MpTxfAddStream(__int64 a1, __int64 a2, __int16 a3, __int64 a4)
{
  void *v7; // r12
  unsigned __int64 *v9; // rdi
  void *v10; // r15
  char *v11; // rax
  char *v12; // rbx
  _OWORD *v13; // rcx
  __int64 v14; // rdx
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  void *v17; // rax
  _QWORD *v18; // rcx

  v7 = 0;
  if ( !MpTxfData )
    return 3221225659LL;
  if ( a2 && a4 && a1 )
  {
    if ( (unsigned __int16)(a3 - 1) <= 0xFFFCu )
      return 0;
    v9 = (unsigned __int64 *)(a4 + 192);
    FltAcquirePushLockShared((PULONG_PTR)(a4 + 192));
    if ( *(_QWORD *)(a4 + 200) == *(_QWORD *)(a1 + 40) )
    {
      FltReleasePushLock(v9);
      return 0;
    }
    FltReleasePushLock(v9);
    ObfReferenceObject(*(PVOID *)(a1 + 40));
    _InterlockedAdd64(&ObTotalReferences, 1u);
    v10 = *(void **)(a1 + 40);
    v11 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpTxfData + 64));
    v12 = v11;
    if ( !v11 )
    {
      _InterlockedOr((volatile signed __int32 *)(a2 + 168), 1u);
      if ( !v10 )
        return 3221225626LL;
      ObfDereferenceObject(v10);
      if ( _InterlockedDecrement64(&ObTotalReferences) >= 0 || *(int *)(MpData + 868) >= 0 )
        return 3221225626LL;
      if ( !KdRefreshDebuggerNotPresent() )
      {
        __debugbreak();
        return 3221225626LL;
      }
LABEL_38:
      KeBugCheck(1u);
    }
    memset(v11 + 16, 0, 0x158u);
    *((_QWORD *)v12 + 1) = v12;
    *(_QWORD *)v12 = v12;
    FltReferenceContext((PFLT_CONTEXT)a4);
    *((_QWORD *)v12 + 8) = a4;
    *((_DWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 4) = _InterlockedCompareExchange64((volatile signed __int64 *)(a4 + 176), 0, 0);
    *((_DWORD *)v12 + 12) = *(_DWORD *)(a4 + 48);
    _InterlockedAnd((volatile signed __int32 *)v12 + 12, 0xFFFFBFFF);
    v13 = (_OWORD *)(a4 + 336);
    *((_QWORD *)v12 + 2) = *(_QWORD *)(a1 + 40);
    v14 = 2;
    *((_QWORD *)v12 + 7) = *(_QWORD *)(a4 + 168);
    v15 = v12 + 72;
    do
    {
      *v15 = *v13;
      v15[1] = v13[1];
      v15[2] = v13[2];
      v15[3] = v13[3];
      v15[4] = v13[4];
      v15[5] = v13[5];
      v15[6] = v13[6];
      v15 += 8;
      v16 = v13[7];
      v13 += 8;
      *(v15 - 1) = v16;
      --v14;
    }
    while ( v14 );
    *v15 = *v13;
    v15[1] = v13[1];
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 8), 1u);
    FltAcquirePushLockExclusive(v9);
    v17 = *(void **)(a4 + 200);
    if ( v17 != *(void **)(a1 + 40) )
    {
      *(_QWORD *)(a4 + 200) = v10;
      *(_QWORD *)(a4 + 208) = v12;
      v7 = v17;
      v10 = 0;
      v18 = *(_QWORD **)(a2 + 144);
      if ( *v18 != a2 + 136 )
        __fastfail(3u);
      *(_QWORD *)v12 = a2 + 136;
      *((_QWORD *)v12 + 1) = v18;
      *v18 = v12;
      *(_QWORD *)(a2 + 144) = v12;
      v12 = 0;
    }
    FltReleasePushLock(v9);
    ExReleaseResourceLite((PERESOURCE)(a2 + 8));
    KeLeaveCriticalRegion();
    if ( v7 )
    {
      ObDereferenceObjectDeferDelete(v7);
      if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
      {
        if ( KdRefreshDebuggerNotPresent() )
          goto LABEL_38;
        __debugbreak();
      }
    }
    if ( v10 )
    {
      ObfDereferenceObject(v10);
      if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
      {
        if ( KdRefreshDebuggerNotPresent() )
          goto LABEL_38;
        __debugbreak();
      }
    }
    if ( v12 )
    {
      if ( *((_QWORD *)v12 + 8) )
        FltReleaseContext((PFLT_CONTEXT)a4);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpTxfData + 64), v12);
    }
    MpSetFileWriteHistoryFlag(a2, *(unsigned __int16 *)(a1 + 2), a4);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400516f4  mov     [rsp+arg_0], rbx
0x1400516f9  mov     [rsp+arg_8], rbp
0x1400516fe  mov     [rsp+arg_10], rsi
0x140051703  push    rdi
0x140051704  push    r12
0x140051706  push    r13
0x140051708  push    r14
0x14005170a  push    r15
0x14005170c  sub     rsp, 30h
0x140051710  xor     eax, eax
0x140051712  mov     rsi, r9
0x140051715  cmp     cs:MpTxfData, rax
0x14005171c  mov     r14, rdx
0x14005171f  mov     r13, rcx
0x140051722  mov     r12d, eax
0x140051725  jnz     short loc_140051731
0x140051727  mov     eax, 0C00000BBh
0x14005172c  jmp     loc_140051AD0
0x140051731  test    r14, r14
0x140051734  jz      loc_140051A98
0x14005173a  test    rsi, rsi
0x14005173d  jz      loc_140051A98
0x140051743  test    r13, r13
0x140051746  jz      loc_140051A98
0x14005174c  mov     ebp, 1
0x140051751  mov     eax, 0FFFCh
0x140051756  sub     r8w, bp
0x14005175a  cmp     r8w, ax
0x14005175e  ja      short loc_140051767
0x140051760  xor     eax, eax
0x140051762  jmp     loc_140051AD0
0x140051767  lea     rdi, [r9+0C0h]
0x14005176e  mov     rcx, rdi; PushLock
0x140051771  call    cs:__imp_FltAcquirePushLockShared
0x140051778  nop     dword ptr [rax+rax+00h]
0x14005177d  mov     rax, [r13+28h]
0x140051781  mov     rcx, rdi; PushLock
0x140051784  cmp     [rsi+0C8h], rax
0x14005178b  jnz     short loc_14005179B
0x14005178d  call    cs:__imp_FltReleasePushLock
0x140051794  nop     dword ptr [rax+rax+00h]
0x140051799  jmp     short loc_140051760
0x14005179b  call    cs:__imp_FltReleasePushLock
0x1400517a2  nop     dword ptr [rax+rax+00h]
0x1400517a7  mov     rcx, [r13+28h]; Object
0x1400517ab  call    cs:__imp_ObfReferenceObject
0x1400517b2  nop     dword ptr [rax+rax+00h]
0x1400517b7  lock add cs:ObTotalReferences, rbp
0x1400517bf  mov     rcx, cs:MpTxfData
0x1400517c6  mov     r15, [r13+28h]
0x1400517ca  add     rcx, 40h ; '@'; Lookaside
0x1400517ce  call    ExAllocateFromPagedLookasideList
0x1400517d3  mov     rbx, rax
0x1400517d6  test    rax, rax
0x1400517d9  jnz     short loc_14005183C
0x1400517db  lock or [r14+0A8h], ebp
0x1400517e3  test    r15, r15
0x1400517e6  jz      short loc_140051832
0x1400517e8  mov     rcx, r15; Object
0x1400517eb  call    cs:__imp_ObfDereferenceObject
0x1400517f2  nop     dword ptr [rax+rax+00h]
0x1400517f7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400517fb  mov     rax, rdi
0x1400517fe  lock xadd cs:ObTotalReferences, rax
0x140051807  add     rax, rdi
0x14005180a  jns     short loc_140051832
0x14005180c  mov     rax, cs:MpData
0x140051813  mov     ecx, [rax+364h]
0x140051819  test    ecx, ecx
0x14005181b  jns     short loc_140051832
0x14005181d  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140051824  nop     dword ptr [rax+rax+00h]
0x140051829  test    al, al
0x14005182b  jnz     loc_140051A89
0x140051831  int     3; Trap to Debugger
0x140051832  mov     eax, 0C000009Ah
0x140051837  jmp     loc_140051AD0
0x14005183c  lea     rcx, [rbx+10h]; void *
0x140051840  xor     edx, edx; Val
0x140051842  mov     r8d, 158h; Size
0x140051848  call    memset
0x14005184d  mov     rcx, rsi; Context
0x140051850  mov     [rbx+8], rbx
0x140051854  mov     [rbx], rbx
0x140051857  call    cs:__imp_FltReferenceContext
0x14005185e  nop     dword ptr [rax+rax+00h]
0x140051863  xor     ecx, ecx
0x140051865  mov     [rbx+40h], rsi
0x140051869  mov     [rbx+18h], ecx
0x14005186c  xor     eax, eax
0x14005186e  lock cmpxchg [rsi+0B0h], rcx
0x140051877  mov     [rbx+20h], rax
0x14005187b  mov     eax, [rsi+30h]
0x14005187e  mov     [rbx+30h], eax
0x140051881  lock and dword ptr [rbx+30h], 0FFFFBFFFh
0x140051889  mov     rax, [r13+28h]
0x14005188d  lea     rcx, [rsi+150h]
0x140051894  mov     [rbx+10h], rax
0x140051898  mov     edx, 2
0x14005189d  mov     rax, [rsi+0A8h]
0x1400518a4  mov     [rbx+38h], rax
0x1400518a8  lea     rax, [rbx+48h]
0x1400518ac  lea     r8d, [rdx+7Eh]
0x1400518b0  movups  xmm0, xmmword ptr [rcx]
0x1400518b3  movups  xmmword ptr [rax], xmm0
0x1400518b6  movups  xmm1, xmmword ptr [rcx+10h]
0x1400518ba  movups  xmmword ptr [rax+10h], xmm1
0x1400518be  movups  xmm0, xmmword ptr [rcx+20h]
0x1400518c2  movups  xmmword ptr [rax+20h], xmm0
0x1400518c6  movups  xmm1, xmmword ptr [rcx+30h]
0x1400518ca  movups  xmmword ptr [rax+30h], xmm1
0x1400518ce  movups  xmm0, xmmword ptr [rcx+40h]
0x1400518d2  movups  xmmword ptr [rax+40h], xmm0
0x1400518d6  movups  xmm1, xmmword ptr [rcx+50h]
0x1400518da  movups  xmmword ptr [rax+50h], xmm1
0x1400518de  movups  xmm0, xmmword ptr [rcx+60h]
0x1400518e2  movups  xmmword ptr [rax+60h], xmm0
0x1400518e6  add     rax, r8
0x1400518e9  movups  xmm1, xmmword ptr [rcx+70h]
0x1400518ed  add     rcx, r8
0x1400518f0  movups  xmmword ptr [rax-10h], xmm1
0x1400518f4  sub     rdx, rbp
0x1400518f7  jnz     short loc_1400518B0
0x1400518f9  movups  xmm0, xmmword ptr [rcx]
0x1400518fc  movups  xmmword ptr [rax], xmm0
0x1400518ff  movups  xmm1, xmmword ptr [rcx+10h]
0x140051903  movups  xmmword ptr [rax+10h], xmm1
0x140051907  call    cs:__imp_KeEnterCriticalRegion
0x14005190e  nop     dword ptr [rax+rax+00h]
0x140051913  lea     rcx, [r14+8]; Resource
0x140051917  mov     dl, bpl; Wait
0x14005191a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140051921  nop     dword ptr [rax+rax+00h]
0x140051926  mov     rcx, rdi; PushLock
0x140051929  call    cs:__imp_FltAcquirePushLockExclusive
0x140051930  nop     dword ptr [rax+rax+00h]
0x140051935  mov     rax, [rsi+0C8h]
0x14005193c  cmp     rax, [r13+28h]
0x140051940  jz      short loc_14005197E
0x140051942  mov     [rsi+0C8h], r15
0x140051949  xor     edx, edx
0x14005194b  mov     [rsi+0D0h], rbx
0x140051952  mov     r12, rax
0x140051955  lea     rax, [r14+88h]
0x14005195c  mov     r15d, edx
0x14005195f  mov     rcx, [rax+8]
0x140051963  cmp     [rcx], rax
0x140051966  jz      short loc_14005196D
0x140051968  lea     ecx, [rdx+3]
0x14005196b  int     29h; Win8: RtlFailFast(ecx)
0x14005196d  mov     [rbx], rax
0x140051970  mov     [rbx+8], rcx
0x140051974  mov     [rcx], rbx
0x140051977  mov     [rax+8], rbx
0x14005197b  mov     rbx, rdx
0x14005197e  mov     rcx, rdi; PushLock
0x140051981  call    cs:__imp_FltReleasePushLock
0x140051988  nop     dword ptr [rax+rax+00h]
0x14005198d  lea     rcx, [r14+8]; Resource
0x140051991  call    cs:__imp_ExReleaseResourceLite
0x140051998  nop     dword ptr [rax+rax+00h]
0x14005199d  call    cs:__imp_KeLeaveCriticalRegion
0x1400519a4  nop     dword ptr [rax+rax+00h]
0x1400519a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400519ad  test    r12, r12
0x1400519b0  jz      short loc_1400519FD
0x1400519b2  mov     rcx, r12; Object
0x1400519b5  call    cs:__imp_ObDereferenceObjectDeferDelete
0x1400519bc  nop     dword ptr [rax+rax+00h]
0x1400519c1  mov     rax, rdi
0x1400519c4  lock xadd cs:ObTotalReferences, rax
0x1400519cd  add     rax, rdi
0x1400519d0  jns     short loc_1400519FD
0x1400519d2  mov     rax, cs:MpData
0x1400519d9  xor     r12d, r12d
0x1400519dc  mov     ecx, [rax+364h]
0x1400519e2  test    ecx, ecx
0x1400519e4  jns     short loc_140051A00
0x1400519e6  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400519ed  nop     dword ptr [rax+rax+00h]
0x1400519f2  test    al, al
0x1400519f4  jnz     loc_140051A89
0x1400519fa  int     3; Trap to Debugger
0x1400519fb  jmp     short loc_140051A00
0x1400519fd  xor     r12d, r12d
0x140051a00  test    r15, r15
0x140051a03  jz      short loc_140051A47
0x140051a05  mov     rcx, r15; Object
0x140051a08  call    cs:__imp_ObfDereferenceObject
0x140051a0f  nop     dword ptr [rax+rax+00h]
0x140051a14  mov     rax, rdi
0x140051a17  lock xadd cs:ObTotalReferences, rax
0x140051a20  add     rax, rdi
0x140051a23  jns     short loc_140051A47
0x140051a25  mov     rax, cs:MpData
0x140051a2c  mov     ecx, [rax+364h]
0x140051a32  test    ecx, ecx
0x140051a34  jns     short loc_140051A47
0x140051a36  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140051a3d  nop     dword ptr [rax+rax+00h]
0x140051a42  test    al, al
0x140051a44  jnz     short loc_140051A89
0x140051a46  int     3; Trap to Debugger
0x140051a47  test    rbx, rbx
0x140051a4a  jz      short loc_140051A74
0x140051a4c  cmp     [rbx+40h], r12
0x140051a50  jz      short loc_140051A61
0x140051a52  mov     rcx, rsi; Context
0x140051a55  call    cs:__imp_FltReleaseContext
0x140051a5c  nop     dword ptr [rax+rax+00h]
0x140051a61  mov     rcx, cs:MpTxfData
0x140051a68  mov     rdx, rbx; Entry
0x140051a6b  add     rcx, 40h ; '@'; Lookaside
0x140051a6f  call    ExFreeToNPagedLookasideList
0x140051a74  movzx   edx, word ptr [r13+2]
0x140051a79  mov     r8, rsi
0x140051a7c  mov     rcx, r14
0x140051a7f  call    MpSetFileWriteHistoryFlag
0x140051a84  jmp     loc_140051760
0x140051a89  mov     ecx, ebp; BugCheckCode
0x140051a8b  call    cs:__imp_KeBugCheck
0x140051a98  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a9f  lea     rax, WPP_GLOBAL_Control
0x140051aa6  cmp     rcx, rax
0x140051aa9  jz      short loc_140051ACB
0x140051aab  mov     eax, [rcx+2Ch]
0x140051aae  mov     ebp, 1
0x140051ab3  test    bpl, al
0x140051ab6  jz      short loc_140051ACB
0x140051ab8  mov     rcx, [rcx+18h]
0x140051abc  lea     edx, [rbp+17h]
0x140051abf  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x140051ac6  call    WPP_SF_
0x140051acb  mov     eax, 0C000000Dh
0x140051ad0  mov     rbx, [rsp+58h+arg_0]
0x140051ad5  mov     rbp, [rsp+58h+arg_8]
0x140051ada  mov     rsi, [rsp+58h+arg_10]
0x140051adf  add     rsp, 30h
0x140051ae3  pop     r15
0x140051ae5  pop     r14
0x140051ae7  pop     r13
0x140051ae9  pop     r12
0x140051aeb  pop     rdi
0x140051aec  retn
```

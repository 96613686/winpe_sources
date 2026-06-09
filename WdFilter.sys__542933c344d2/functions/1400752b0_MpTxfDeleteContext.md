# MpTxfDeleteContext

- ea: `0x1400752b0`
- end: `0x1400756b0`
- name: `MpTxfDeleteContext`
- size: `1024`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400018a4`
- `0x140003460`
- `0x1400049dc`
- `0x1400118d0`
- `0x140050b88`
- `0x1400752b0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140075608`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140075608`
- `ntoskrnl!RtlCompareMemory` at `0x140075441`
- `ntoskrnl!RtlCompareMemory` at `0x140075441`
- `ntoskrnl!ObfReferenceObject` at `0x1400753ea`
- `ntoskrnl!ObfReferenceObject` at `0x1400753ea`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007567b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007567b`
- `ntoskrnl!KeBugCheckEx` at `0x140075324`
- `ntoskrnl!KeBugCheckEx` at `0x140075377`
- `ntoskrnl!KeBugCheckEx` at `0x140075324`
- `ntoskrnl!KeBugCheckEx` at `0x140075377`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14007547a`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400754eb`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14007547a`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400754eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400755d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400755d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400755cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400755cb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007558c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007558c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140075577`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140075577`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075640`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075664`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075640`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075664`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400754aa`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14007551b`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400754aa`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14007551b`
- `ntoskrnl!KeBugCheck` at `0x14007555e`
- `ntoskrnl!KeBugCheck` at `0x14007555e`
- `FLTMGR!FltReleaseContext` at `0x140075535`
- `FLTMGR!FltReleaseContext` at `0x1400755ea`
- `FLTMGR!FltReleaseContext` at `0x140075535`
- `FLTMGR!FltReleaseContext` at `0x1400755ea`
- `FLTMGR!FltAcquirePushLockShared` at `0x1400753cb`
- `FLTMGR!FltAcquirePushLockShared` at `0x1400753cb`
- `FLTMGR!FltReleasePushLock` at `0x140075405`
- `FLTMGR!FltReleasePushLock` at `0x1400754dc`
- `FLTMGR!FltReleasePushLock` at `0x140075405`
- `FLTMGR!FltReleasePushLock` at `0x1400754dc`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14007545e`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14007545e`

## pseudocode

```c
NTSTATUS __fastcall MpTxfDeleteContext(__int64 a1, unsigned __int16 a2)
{
  ULONG_PTR v2; // rbx
  _QWORD **v4; // r14
  _QWORD *v5; // rsi
  _QWORD *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  void *v9; // rbp
  void *v10; // rcx
  void *v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  struct _UNICODE_STRING *v15; // rcx
  void *v16; // rcx
  __int128 Source1; // [rsp+30h] [rbp-48h] BYREF

  v2 = a2;
  if ( a2 != 32 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids, a2);
    KeBugCheckEx(0x108u, v2, 0x20u, 0, 0);
  }
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids);
    KeBugCheckEx(0x108u, 0, 0x20u, 0x20u, 0);
  }
  v4 = (_QWORD **)(a1 + 136);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 )
      goto LABEL_46;
    v6 = (_QWORD *)*v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 )
      goto LABEL_46;
    *v4 = v6;
    v6[1] = v4;
    v7 = v5[8];
    if ( v7 )
    {
      FltAcquirePushLockShared((PULONG_PTR)(v7 + 192));
      v8 = v5[8];
      v9 = *(void **)(v8 + 200);
      if ( v9 )
      {
        ObfReferenceObject(*(PVOID *)(v8 + 200));
        _InterlockedIncrement64(&ObTotalReferences);
      }
      FltReleasePushLock((PULONG_PTR)(v5[8] + 192LL));
      if ( v9 )
      {
        Source1 = 0;
        MpQueryTransactionId(v9, &Source1);
        if ( RtlCompareMemory(&Source1, *(const void **)(a1 + 160), 0x10u) == 16 )
        {
          FltAcquirePushLockExclusive((PULONG_PTR)(v5[8] + 192LL));
          v10 = *(void **)(v5[8] + 200LL);
          if ( v10 == v9 )
          {
            ObDereferenceObjectDeferDelete(v10);
            if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
            {
              if ( KdRefreshDebuggerNotPresent() )
                goto LABEL_34;
              __debugbreak();
            }
            *(_QWORD *)(v5[8] + 200LL) = 0;
            *(_QWORD *)(v5[8] + 208LL) = 0;
          }
          FltReleasePushLock((PULONG_PTR)(v5[8] + 192LL));
        }
        ObDereferenceObjectDeferDelete(v9);
        if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
        {
          if ( KdRefreshDebuggerNotPresent() )
LABEL_34:
            KeBugCheck(1u);
          __debugbreak();
        }
      }
    }
    v11 = (void *)v5[8];
    if ( v11 )
      FltReleaseContext(v11);
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpTxfData + 64), v5);
  }
  v12 = *(_QWORD *)(a1 + 128);
  if ( v12 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v12 + 288), 1u);
    v13 = *(_QWORD *)(a1 + 112);
    if ( *(_QWORD *)(v13 + 8) != a1 + 112 || (v14 = *(_QWORD **)(a1 + 120), *v14 != a1 + 112) )
LABEL_46:
      __fastfail(3u);
    *v14 = v13;
    *(_QWORD *)(v13 + 8) = v14;
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 128) + 288LL));
    KeLeaveCriticalRegion();
    FltReleaseContext(*(PFLT_CONTEXT *)(a1 + 128));
  }
  v15 = *(struct _UNICODE_STRING **)(a1 + 152);
  if ( v15 )
  {
    if ( v15->Buffer )
    {
      RtlFreeUnicodeString(v15);
      *(_QWORD *)(*(_QWORD *)(a1 + 152) + 8LL) = 0;
      **(_WORD **)(a1 + 152) = 0;
      *(_WORD *)(*(_QWORD *)(a1 + 152) + 2LL) = 0;
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 152), 0x6E74504Du);
    *(_QWORD *)(a1 + 152) = 0;
  }
  v16 = *(void **)(a1 + 160);
  if ( v16 )
  {
    ExFreePoolWithTag(v16, 0x6774504Du);
    *(_QWORD *)(a1 + 160) = 0;
  }
  return ExDeleteResourceLite((PERESOURCE)(a1 + 8));
}

```

## disassembly

```asm
0x1400752b0  mov     [rsp+arg_10], rbx
0x1400752b5  push    rbp
0x1400752b6  push    rsi
0x1400752b7  push    rdi
0x1400752b8  push    r12
0x1400752ba  push    r14
0x1400752bc  sub     rsp, 50h
0x1400752c0  mov     rax, cs:__security_cookie
0x1400752c7  xor     rax, rsp
0x1400752ca  mov     [rsp+78h+var_38], rax
0x1400752cf  movzx   ebx, dx
0x1400752d2  mov     esi, 20h ; ' '
0x1400752d7  mov     rdi, rcx
0x1400752da  cmp     si, bx
0x1400752dd  jz      short loc_140075331
0x1400752df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400752e6  lea     rax, WPP_GLOBAL_Control
0x1400752ed  cmp     rcx, rax
0x1400752f0  jz      short loc_14007530F
0x1400752f2  mov     eax, [rcx+2Ch]
0x1400752f5  test    al, 1
0x1400752f7  jz      short loc_14007530F
0x1400752f9  mov     rcx, [rcx+18h]
0x1400752fd  lea     edx, [rsi-0Ch]
0x140075300  mov     r9d, ebx
0x140075303  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x14007530a  call    WPP_SF_d
0x14007530f  mov     rdx, rbx; BugCheckParameter1
0x140075312  xor     r9d, r9d; BugCheckParameter3
0x140075315  xor     ebx, ebx
0x140075317  mov     r8, rsi; BugCheckParameter2
0x14007531a  mov     ecx, 108h; BugCheckCode
0x14007531f  mov     [rsp+78h+BugCheckParameter4], rbx; BugCheckParameter4
0x140075324  call    cs:__imp_KeBugCheckEx
0x140075331  xor     ebx, ebx
0x140075333  test    rdi, rdi
0x140075336  jnz     short loc_140075384
0x140075338  mov     rcx, cs:WPP_GLOBAL_Control
0x14007533f  lea     rax, WPP_GLOBAL_Control
0x140075346  cmp     rcx, rax
0x140075349  jz      short loc_140075365
0x14007534b  mov     eax, [rcx+2Ch]
0x14007534e  test    al, 1
0x140075350  jz      short loc_140075365
0x140075352  mov     rcx, [rcx+18h]
0x140075356  lea     edx, [rbx+15h]
0x140075359  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x140075360  call    WPP_SF_
0x140075365  mov     r9, rsi; BugCheckParameter3
0x140075368  mov     [rsp+78h+BugCheckParameter4], rbx; BugCheckParameter4
0x14007536d  mov     r8, rsi; BugCheckParameter2
0x140075370  xor     edx, edx; BugCheckParameter1
0x140075372  mov     ecx, 108h; BugCheckCode
0x140075377  call    cs:__imp_KeBugCheckEx
0x140075384  lea     r14, [rcx+88h]
0x14007538b  mov     r12d, 0C0h
0x140075391  mov     rsi, [r14]
0x140075394  cmp     rsi, r14
0x140075397  jz      loc_14007556B
0x14007539d  cmp     [rsi+8], r14
0x1400753a1  jnz     loc_1400756A9
0x1400753a7  mov     rax, [rsi]
0x1400753aa  cmp     [rax+8], rsi
0x1400753ae  jnz     loc_1400756A9
0x1400753b4  mov     [r14], rax
0x1400753b7  mov     [rax+8], r14
0x1400753bb  mov     rcx, [rsi+40h]
0x1400753bf  test    rcx, rcx
0x1400753c2  jz      loc_14007552C
0x1400753c8  add     rcx, r12; PushLock
0x1400753cb  call    cs:__imp_FltAcquirePushLockShared
0x1400753d2  nop     dword ptr [rax+rax+00h]
0x1400753d7  mov     rax, [rsi+40h]
0x1400753db  mov     rbp, [rax+0C8h]
0x1400753e2  test    rbp, rbp
0x1400753e5  jz      short loc_1400753FE
0x1400753e7  mov     rcx, rbp; Object
0x1400753ea  call    cs:__imp_ObfReferenceObject
0x1400753f1  nop     dword ptr [rax+rax+00h]
0x1400753f6  lock inc cs:ObTotalReferences
0x1400753fe  mov     rcx, [rsi+40h]
0x140075402  add     rcx, r12; PushLock
0x140075405  call    cs:__imp_FltReleasePushLock
0x14007540c  nop     dword ptr [rax+rax+00h]
0x140075411  test    rbp, rbp
0x140075414  jz      loc_14007552C
0x14007541a  xorps   xmm0, xmm0
0x14007541d  lea     rdx, [rsp+78h+Source1]
0x140075422  mov     rcx, rbp
0x140075425  movups  [rsp+78h+Source1], xmm0
0x14007542a  call    MpQueryTransactionId
0x14007542f  mov     rdx, [rdi+0A0h]; Source2
0x140075436  lea     rcx, [rsp+78h+Source1]; Source1
0x14007543b  mov     r8d, 10h; Length
0x140075441  call    cs:__imp_RtlCompareMemory
0x140075448  nop     dword ptr [rax+rax+00h]
0x14007544d  cmp     rax, 10h
0x140075451  jnz     loc_1400754E8
0x140075457  mov     rcx, [rsi+40h]
0x14007545b  add     rcx, r12; PushLock
0x14007545e  call    cs:__imp_FltAcquirePushLockExclusive
0x140075465  nop     dword ptr [rax+rax+00h]
0x14007546a  mov     rax, [rsi+40h]
0x14007546e  mov     rcx, [rax+0C8h]; Object
0x140075475  cmp     rcx, rbp
0x140075478  jnz     short loc_1400754D5
0x14007547a  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140075481  nop     dword ptr [rax+rax+00h]
0x140075486  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007548a  lock xadd cs:ObTotalReferences, rax
0x140075493  cmp     rax, 1
0x140075497  jns     short loc_1400754BF
0x140075499  mov     rax, cs:MpData
0x1400754a0  mov     ecx, [rax+364h]
0x1400754a6  test    ecx, ecx
0x1400754a8  jns     short loc_1400754BF
0x1400754aa  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400754b1  nop     dword ptr [rax+rax+00h]
0x1400754b6  test    al, al
0x1400754b8  jnz     loc_140075559
0x1400754be  int     3; Trap to Debugger
0x1400754bf  mov     rax, [rsi+40h]
0x1400754c3  mov     [rax+0C8h], rbx
0x1400754ca  mov     rax, [rsi+40h]
0x1400754ce  mov     [rax+0D0h], rbx
0x1400754d5  mov     rcx, [rsi+40h]
0x1400754d9  add     rcx, r12; PushLock
0x1400754dc  call    cs:__imp_FltReleasePushLock
0x1400754e3  nop     dword ptr [rax+rax+00h]
0x1400754e8  mov     rcx, rbp; Object
0x1400754eb  call    cs:__imp_ObDereferenceObjectDeferDelete
0x1400754f2  nop     dword ptr [rax+rax+00h]
0x1400754f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400754fb  lock xadd cs:ObTotalReferences, rax
0x140075504  cmp     rax, 1
0x140075508  jns     short loc_14007552C
0x14007550a  mov     rax, cs:MpData
0x140075511  mov     ecx, [rax+364h]
0x140075517  test    ecx, ecx
0x140075519  jns     short loc_14007552C
0x14007551b  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140075522  nop     dword ptr [rax+rax+00h]
0x140075527  test    al, al
0x140075529  jnz     short loc_140075559
0x14007552b  int     3; Trap to Debugger
0x14007552c  mov     rcx, [rsi+40h]; Context
0x140075530  test    rcx, rcx
0x140075533  jz      short loc_140075541
0x140075535  call    cs:__imp_FltReleaseContext
0x14007553c  nop     dword ptr [rax+rax+00h]
0x140075541  mov     rcx, cs:MpTxfData
0x140075548  mov     rdx, rsi; Entry
0x14007554b  add     rcx, 40h ; '@'; Lookaside
0x14007554f  call    ExFreeToNPagedLookasideList
0x140075554  jmp     loc_140075391
0x140075559  mov     ecx, 1; BugCheckCode
0x14007555e  call    cs:__imp_KeBugCheck
0x14007556b  mov     rsi, [rdi+80h]
0x140075572  test    rsi, rsi
0x140075575  jz      short loc_1400755F6
0x140075577  call    cs:__imp_KeEnterCriticalRegion
0x14007557e  nop     dword ptr [rax+rax+00h]
0x140075583  lea     rcx, [rsi+120h]; Resource
0x14007558a  mov     dl, 1; Wait
0x14007558c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140075593  nop     dword ptr [rax+rax+00h]
0x140075598  lea     rax, [rdi+70h]
0x14007559c  mov     rdx, [rax]
0x14007559f  cmp     [rdx+8], rax
0x1400755a3  jnz     loc_1400756A9
0x1400755a9  mov     rcx, [rax+8]
0x1400755ad  cmp     [rcx], rax
0x1400755b0  jnz     loc_1400756A9
0x1400755b6  mov     [rcx], rdx
0x1400755b9  mov     [rdx+8], rcx
0x1400755bd  mov     rcx, [rdi+80h]
0x1400755c4  add     rcx, 120h; Resource
0x1400755cb  call    cs:__imp_ExReleaseResourceLite
0x1400755d2  nop     dword ptr [rax+rax+00h]
0x1400755d7  call    cs:__imp_KeLeaveCriticalRegion
0x1400755de  nop     dword ptr [rax+rax+00h]
0x1400755e3  mov     rcx, [rdi+80h]; Context
0x1400755ea  call    cs:__imp_FltReleaseContext
0x1400755f1  nop     dword ptr [rax+rax+00h]
0x1400755f6  mov     rcx, [rdi+98h]; UnicodeString
0x1400755fd  test    rcx, rcx
0x140075600  jz      short loc_140075653
0x140075602  cmp     [rcx+8], rbx
0x140075606  jz      short loc_140075634
0x140075608  call    cs:__imp_RtlFreeUnicodeString
0x14007560f  nop     dword ptr [rax+rax+00h]
0x140075614  mov     rax, [rdi+98h]
0x14007561b  mov     [rax+8], rbx
0x14007561f  mov     rax, [rdi+98h]
0x140075626  mov     [rax], bx
0x140075629  mov     rax, [rdi+98h]
0x140075630  mov     [rax+2], bx
0x140075634  mov     rcx, [rdi+98h]; P
0x14007563b  mov     edx, 6E74504Dh; Tag
0x140075640  call    cs:__imp_ExFreePoolWithTag
0x140075647  nop     dword ptr [rax+rax+00h]
0x14007564c  mov     [rdi+98h], rbx
0x140075653  mov     rcx, [rdi+0A0h]; P
0x14007565a  test    rcx, rcx
0x14007565d  jz      short loc_140075677
0x14007565f  mov     edx, 6774504Dh; Tag
0x140075664  call    cs:__imp_ExFreePoolWithTag
0x14007566b  nop     dword ptr [rax+rax+00h]
0x140075670  mov     [rdi+0A0h], rbx
0x140075677  lea     rcx, [rdi+8]; Resource
0x14007567b  call    cs:__imp_ExDeleteResourceLite
0x140075682  nop     dword ptr [rax+rax+00h]
0x140075687  mov     rcx, [rsp+78h+var_38]
0x14007568c  xor     rcx, rsp; StackCookie
0x14007568f  call    __security_check_cookie
0x140075694  mov     rbx, [rsp+78h+arg_10]
0x14007569c  add     rsp, 50h
0x1400756a0  pop     r14
0x1400756a2  pop     r12
0x1400756a4  pop     rdi
0x1400756a5  pop     rsi
0x1400756a6  pop     rbp
0x1400756a7  retn
0x1400756a9  mov     ecx, 3
0x1400756ae  int     29h; Win8: RtlFailFast(ecx)
```

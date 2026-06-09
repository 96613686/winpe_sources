# UxTlDestroyConnectionWorker

- ea: `0x1400897e0`
- end: `0x140089ae7`
- name: `UxTlDestroyConnectionWorker`
- size: `775`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140049d08`
- `0x14005dfd0`
- `0x1400897e0`
- `0x1400cb068`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400899c6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400899c6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140089a07`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140089a07`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140089895`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008992f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140089895`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008992f`
- `ntoskrnl!IoFreeIrp` at `0x140089828`
- `ntoskrnl!IoFreeIrp` at `0x140089828`
- `ntoskrnl!KeSetEvent` at `0x1400899f4`
- `ntoskrnl!KeSetEvent` at `0x1400899f4`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140089918`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14008999f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140089918`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14008999f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400898d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400898d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400898b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400898b6`

## pseudocode

```c
void __fastcall UxTlDestroyConnectionWorker(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v2; // rbx
  IRP *v3; // rcx
  _DWORD *v4; // rsi
  unsigned __int64 v5; // rdi
  __int64 v6; // rdi
  KIRQL v7; // al
  bool v8; // zf
  KIRQL v9; // si
  __int64 v10; // rax
  __int64 v11; // rdi
  USHORT v12; // ax
  __int64 v13; // r9
  int v14; // esi
  __int64 v15; // rdi
  USHORT CurrentNodeNumber; // ax
  ULONG_PTR v17; // rdx
  int v18; // eax
  ULONG_PTR v19; // rdx
  _DWORD v20[24]; // [rsp+40h] [rbp-88h] BYREF

  v1 = *(_QWORD *)(a1 - 224);
  v2 = a1 - 432;
  *(_QWORD *)(a1 - 432 + 208) = 0;
  v3 = *(IRP **)(a1 - 432 + 96);
  if ( v3 )
  {
    IoFreeIrp(v3);
    *(_QWORD *)(v2 + 96) = 0;
  }
  v4 = *(_DWORD **)(v2 + 104);
  if ( v4 )
  {
    memset(v20, 0, sizeof(v20));
    if ( UxDebugDisableLookaside )
    {
      v20[10] = dword_1401A0388;
      ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0398)(v4, v20);
    }
    else if ( UxCompactMode )
    {
      v15 = qword_1401A0370;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v15, v4, CurrentNodeNumber);
    }
    else
    {
      v5 = qword_1401A0370 + ((unsigned __int64)(unsigned int)(*v4 + 1) << 7);
      if ( !*(_BYTE *)(v5 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0370, v5 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v5 + 64), v4);
    }
    *(_QWORD *)(v2 + 104) = 0;
  }
  v6 = *(_QWORD *)(v2 + 480);
  *(_QWORD *)(v2 + 480) = 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6);
  v8 = (*(_DWORD *)(v6 + 12))-- == 1;
  v9 = v7;
  if ( v8 )
  {
    KeAcquireSpinLockAtDpcLevel(&UlPartitionsSpinLock);
    if ( !--UlPartitionsActiveCount )
      KeSetEvent(&UlScavengerRefreshEvent, 0, 0);
    KeReleaseSpinLockFromDpcLevel(&UlPartitionsSpinLock);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)v6, v9);
  v10 = *(_QWORD *)(v2 + 520);
  if ( v10 )
  {
    v17 = v10 + 16;
    v18 = _InterlockedDecrement((volatile signed __int32 *)(v10 + 16));
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, v17, 0xAu, v18);
    if ( !v18 )
      UlAiFreeAddressInformation(*(PVOID *)(v2 + 520));
  }
  *(_DWORD *)(v2 + 56) = 7;
  *(_DWORD *)(v2 + 32) = 1129598069;
  if ( v1 )
  {
    v11 = *(_QWORD *)(*(_QWORD *)(v1 + 200) + 8680LL);
    v12 = KeGetCurrentNodeNumber();
    ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v11 + 8LL * v12 + 8), (PVOID)v2);
    v14 = _InterlockedDecrement((volatile signed __int32 *)(v1 + 8));
    if ( UxDebugCheckRefcount && v14 <= -1 )
      UlBugCheckEx(3u, v1 + 8, 0xFu, v14);
    if ( !v14 )
    {
      v19 = v1 + 48;
      if ( *(_QWORD *)(v1 + 48) || *(_QWORD *)(v1 + 64) || *(_QWORD *)(v1 + 80) )
        UlBugCheckEx(1u, v19, (ULONG_PTR)"minio\\http\\sys\\tl.h", 0x400u);
      LOBYTE(v13) = 1;
      UlThreadPoolEnqueueWorkItem(0, v19, UxTlDestroyListenEndpoint, v13, *(_QWORD *)(v1 + 192), -1);
    }
  }
}

```

## disassembly

```asm
0x1400897e0  mov     [rsp+arg_8], rbx
0x1400897e5  mov     [rsp+arg_10], rbp
0x1400897ea  push    rsi
0x1400897eb  push    rdi
0x1400897ec  push    r14
0x1400897ee  sub     rsp, 0B0h
0x1400897f5  mov     rax, cs:__security_cookie
0x1400897fc  xor     rax, rsp
0x1400897ff  mov     [rsp+0C8h+var_28], rax
0x140089807  mov     rbp, [rcx-0E0h]
0x14008980e  lea     rbx, [rcx-1B0h]
0x140089815  xor     r14d, r14d
0x140089818  mov     [rbx+0D0h], r14
0x14008981f  mov     rcx, [rbx+60h]; Irp
0x140089823  test    rcx, rcx
0x140089826  jz      short loc_140089838
0x140089828  call    cs:__imp_IoFreeIrp
0x14008982f  nop     dword ptr [rax+rax+00h]
0x140089834  mov     [rbx+60h], r14
0x140089838  mov     rsi, [rbx+68h]
0x14008983c  test    rsi, rsi
0x14008983f  jz      short loc_1400898A5
0x140089841  xor     edx, edx; Val
0x140089843  lea     rcx, [rsp+0C8h+var_88]; void *
0x140089848  mov     r8d, 60h ; '`'; Size
0x14008984e  call    memset
0x140089853  cmp     cs:UxDebugDisableLookaside, r14b
0x14008985a  jnz     loc_140089AC4
0x140089860  cmp     cs:UxCompactMode, r14b
0x140089867  jnz     loc_140089998
0x14008986d  mov     edi, [rsi]
0x14008986f  mov     rcx, cs:qword_1401A0370
0x140089876  inc     edi
0x140089878  shl     rdi, 7
0x14008987c  add     rdi, rcx
0x14008987f  movzx   eax, byte ptr [rdi+0B0h]
0x140089886  test    al, al
0x140089888  jz      loc_140089A5E
0x14008988e  mov     rdx, rsi; Entry
0x140089891  lea     rcx, [rdi+40h]; Lookaside
0x140089895  call    cs:__imp_ExFreeToLookasideListEx
0x14008989c  nop     dword ptr [rax+rax+00h]
0x1400898a1  mov     [rbx+68h], r14
0x1400898a5  mov     rdi, [rbx+1E0h]
0x1400898ac  mov     rcx, rdi; SpinLock
0x1400898af  mov     [rbx+1E0h], r14
0x1400898b6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400898bd  nop     dword ptr [rax+rax+00h]
0x1400898c2  add     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x1400898c6  movzx   esi, al
0x1400898c9  jz      loc_1400899BF
0x1400898cf  movzx   edx, sil; NewIrql
0x1400898d3  mov     rcx, rdi; SpinLock
0x1400898d6  call    cs:__imp_KeReleaseSpinLock
0x1400898dd  nop     dword ptr [rax+rax+00h]
0x1400898e2  mov     rax, [rbx+208h]
0x1400898e9  mov     esi, 0FFFFFFFFh
0x1400898ee  test    rax, rax
0x1400898f1  jnz     loc_140089A18
0x1400898f7  mov     dword ptr [rbx+38h], 7
0x1400898fe  mov     dword ptr [rbx+20h], 43544C75h
0x140089905  test    rbp, rbp
0x140089908  jz      short loc_140089956
0x14008990a  mov     rax, [rbp+0C8h]
0x140089911  mov     rdi, [rax+21E8h]
0x140089918  call    cs:__imp_KeGetCurrentNodeNumber
0x14008991f  nop     dword ptr [rax+rax+00h]
0x140089924  movzx   ecx, ax
0x140089927  mov     rdx, rbx; Entry
0x14008992a  mov     rcx, [rdi+rcx*8+8]; Lookaside
0x14008992f  call    cs:__imp_ExFreeToLookasideListEx
0x140089936  nop     dword ptr [rax+rax+00h]
0x14008993b  lea     rdx, [rbp+8]; BugCheckParameter2
0x14008993f  lock xadd [rdx], esi
0x140089943  dec     esi
0x140089945  cmp     cs:UxDebugCheckRefcount, r14b
0x14008994c  jnz     short loc_14008997F
0x14008994e  test    esi, esi
0x140089950  jz      loc_140089A6C
0x140089956  mov     rcx, [rsp+0C8h+var_28]
0x14008995e  xor     rcx, rsp; StackCookie
0x140089961  call    __security_check_cookie
0x140089966  lea     r11, [rsp+0C8h+var_18]
0x14008996e  mov     rbx, [r11+28h]
0x140089972  mov     rbp, [r11+30h]
0x140089976  mov     rsp, r11
0x140089979  pop     r14
0x14008997b  pop     rdi
0x14008997c  pop     rsi
0x14008997d  retn
0x14008997f  cmp     esi, 0FFFFFFFFh
0x140089982  jg      short loc_14008994E
0x140089984  movsxd  r9, esi; BugCheckParameter4
0x140089987  mov     ecx, 3; BugCheckParameter1
0x14008998c  mov     r8d, 0Fh; BugCheckParameter3
0x140089992  call    UlBugCheckEx
0x140089998  mov     rdi, cs:qword_1401A0370
0x14008999f  call    cs:__imp_KeGetCurrentNodeNumber
0x1400899a6  nop     dword ptr [rax+rax+00h]
0x1400899ab  movzx   r8d, ax
0x1400899af  mov     rdx, rsi
0x1400899b2  mov     rcx, rdi
0x1400899b5  call    PplFreeToLookasideListProcessor
0x1400899ba  jmp     loc_1400898A1
0x1400899bf  lea     rcx, UlPartitionsSpinLock; SpinLock
0x1400899c6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400899cd  nop     dword ptr [rax+rax+00h]
0x1400899d2  mov     edx, cs:UlPartitionsActiveCount
0x1400899d8  dec     edx
0x1400899da  mov     cs:UlPartitionsActiveCount, edx
0x1400899e0  mov     edx, cs:UlPartitionsActiveCount; Increment
0x1400899e6  test    edx, edx
0x1400899e8  jnz     short loc_140089A00
0x1400899ea  xor     r8d, r8d; Wait
0x1400899ed  lea     rcx, UlScavengerRefreshEvent; Event
0x1400899f4  call    cs:__imp_KeSetEvent
0x1400899fb  nop     dword ptr [rax+rax+00h]
0x140089a00  lea     rcx, UlPartitionsSpinLock; SpinLock
0x140089a07  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140089a0e  nop     dword ptr [rax+rax+00h]
0x140089a13  jmp     loc_1400898CF
0x140089a18  lea     rdx, [rax+10h]; BugCheckParameter2
0x140089a1c  mov     eax, esi
0x140089a1e  lock xadd [rdx], eax
0x140089a22  dec     eax
0x140089a24  cmp     cs:UxDebugCheckRefcount, r14b
0x140089a2b  jnz     short loc_140089A46
0x140089a2d  test    eax, eax
0x140089a2f  jnz     loc_1400898F7
0x140089a35  mov     rcx, [rbx+208h]; P
0x140089a3c  call    UlAiFreeAddressInformation
0x140089a41  jmp     loc_1400898F7
0x140089a46  cmp     eax, esi
0x140089a48  jg      short loc_140089A2D
0x140089a4a  movsxd  r9, eax; BugCheckParameter4
0x140089a4d  mov     ecx, 3; BugCheckParameter1
0x140089a52  mov     r8d, 0Ah; BugCheckParameter3
0x140089a58  call    UlBugCheckEx
0x140089a5e  lea     rdx, [rdi+40h]
0x140089a62  call    PplpLazyInitializeLookasideList
0x140089a67  jmp     loc_14008988E
0x140089a6c  cmp     [rbp+30h], r14
0x140089a70  lea     rdx, [rbp+30h]; BugCheckParameter2
0x140089a74  jnz     short loc_140089A7C
0x140089a76  cmp     [rdx+10h], r14
0x140089a7a  jz      short loc_140089A94
0x140089a7c  mov     r9d, 400h; BugCheckParameter4
0x140089a82  lea     r8, aMinioHttpSysTl; "minio\\http\\sys\\tl.h"
0x140089a89  mov     ecx, 1; BugCheckParameter1
0x140089a8e  call    UlBugCheckEx
0x140089a94  cmp     [rdx+20h], r14
0x140089a98  jnz     short loc_140089A7C
0x140089a9a  mov     rax, [rbp+0C0h]
0x140089aa1  lea     r8, UxTlDestroyListenEndpoint
0x140089aa8  mov     [rsp+0C8h+var_A0], 0FFFFFFFFh
0x140089ab0  mov     r9b, 1
0x140089ab3  xor     ecx, ecx
0x140089ab5  mov     [rsp+0C8h+var_A8], rax
0x140089aba  call    UlThreadPoolEnqueueWorkItem
0x140089abf  jmp     loc_140089956
0x140089ac4  mov     eax, cs:dword_1401A0388
0x140089aca  lea     rdx, [rsp+0C8h+var_88]
0x140089acf  mov     [rsp+0C8h+var_60], eax
0x140089ad3  mov     rcx, rsi
0x140089ad6  mov     rax, cs:off_1401A0398
0x140089add  call    _guard_dispatch_icall
0x140089ae2  jmp     loc_1400898A1
```

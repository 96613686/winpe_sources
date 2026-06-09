# MbbReqMgrQueueEvent(_MBB_REQUEST_MANAGER *,_MBB_REQUEST_CONTEXT *,MBB_REQUEST_EVENT,void *,ulong)

- ea: `0x14001a9ec`
- end: `0x14001abe6`
- name: `?MbbReqMgrQueueEvent@@YAXPEAU_MBB_REQUEST_MANAGER@@PEAU_MBB_REQUEST_CONTEXT@@W4MBB_REQUEST_EVENT@@PEAXK@Z`
- size: `506`
- prototype: `void __fastcall(__int64, __int64, int, __int64, int)`
- caller_count: `10`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x14000cc8c`
- `0x140012900`
- `0x140012a2c`
- `0x140012c90`
- `0x1400130b8`
- `0x140018ff0`
- `0x14001a8ac`
- `0x14001b348`
- `0x14001b47c`
- `0x14001b760`

## callees

- `0x1400051ac`
- `0x1400090a0`
- `0x140018ce0`
- `0x140018ff0`
- `0x1400191c0`
- `0x140019210`
- `0x140019290`
- `0x140019370`
- `0x140019f78`
- `0x14001a87c`
- `0x14001a9ec`
- `0x14001ba9c`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001aa6a`
- `ntoskrnl!ExAllocatePool2` at `0x14001aa6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ab9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ab9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001aa44`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ab61`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001abc2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001aa44`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ab61`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001abc2`

## pseudocode

```c
void __fastcall MbbReqMgrQueueEvent(__int64 a1, __int64 a2, int a3, __int64 a4, int a5)
{
  __int64 v6; // rbp
  __int64 v9; // rdi
  int v10; // eax
  char v11; // si
  __int64 Pool2; // rax
  __int64 v13; // rbx
  unsigned int v14; // ebp
  __int64 v15; // r14
  int v16; // esi
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rsi
  __int64 v21; // rbx
  int v22; // [rsp+20h] [rbp-68h]

  v6 = a3;
  MbbReqMgrLockManager((struct _MBB_REQUEST_MANAGER *)a1);
  v9 = 48 * v6 + a2 + 136;
  v10 = *(_DWORD *)(v9 + 16);
  if ( (v10 & 1) != 0 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    *(_DWORD *)(v9 + 16) = v10 | 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 176), *(_BYTE *)(a1 + 184));
  if ( !v11 )
    goto LABEL_9;
  Pool2 = ExAllocatePool2(64, 48, 1683505741);
  v9 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 16) |= 2u;
LABEL_9:
    *(_DWORD *)(v9 + 40) = a5;
    *(_DWORD *)(v9 + 20) = v6;
    *(_QWORD *)(v9 + 32) = a4;
    *(_QWORD *)(v9 + 24) = a2;
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 40));
    goto LABEL_10;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DD(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      4u,
      0x28u,
      (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
      *(_DWORD *)(a2 + 16),
      v6);
LABEL_10:
  v13 = *(_QWORD *)(v9 + 24);
  v14 = 0;
  v15 = *(_QWORD *)(v13 + 48);
  v16 = 8;
  MbbReqMgrLockManager((struct _MBB_REQUEST_MANAGER *)v15);
  v17 = *(int *)(v13 + 120);
  if ( (unsigned int)v17 <= 7 )
  {
    v18 = *(int *)(v9 + 20);
    if ( (unsigned int)v18 <= 5 )
    {
      v19 = v18 + 6 * v17;
      v16 = *((_DWORD *)&MbbReqFsmTransitionTable + v19);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_DLLL((__int64)WPP_GLOBAL_Control->DeviceExtension, v19, v18, v17, v22);
      v14 = *(_DWORD *)(v13 + 120);
      *(_DWORD *)(v13 + 120) = v16;
      *(_DWORD *)(v13 + 124) = v14;
      *(_DWORD *)(v13 + 128) = *(_DWORD *)(v9 + 20);
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v15 + 176), *(_BYTE *)(v15 + 184));
  if ( v16 < 8 )
    ((void (__fastcall *)(__int64, _QWORD, __int64))(&MbbReqFsmStateHandlerTable)[v16])(v13, v14, v9);
  v20 = *(_QWORD *)(v9 + 24);
  if ( (*(_DWORD *)(v9 + 16) & 2) != 0 )
  {
    ExFreePoolWithTag((PVOID)v9, 0);
  }
  else
  {
    v21 = *(_QWORD *)(v20 + 48);
    MbbReqMgrLockManager((struct _MBB_REQUEST_MANAGER *)v21);
    *(_DWORD *)(v9 + 16) &= ~1u;
    KeReleaseSpinLock((PKSPIN_LOCK)(v21 + 176), *(_BYTE *)(v21 + 184));
  }
  MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)v20);
}

```

## disassembly

```asm
0x14001a9ec  push    rbx
0x14001a9ee  push    rbp
0x14001a9ef  push    rsi
0x14001a9f0  push    rdi
0x14001a9f1  push    r12
0x14001a9f3  push    r14
0x14001a9f5  push    r15
0x14001a9f7  sub     rsp, 50h
0x14001a9fb  mov     r15, r9
0x14001a9fe  movsxd  rbp, r8d
0x14001aa01  mov     rbx, rdx
0x14001aa04  mov     r14, rcx
0x14001aa07  call    ?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)
0x14001aa0c  lea     r10, ds:0[rbp*2]
0x14001aa14  add     r10, rbp
0x14001aa17  lea     rdi, [rbx+88h]
0x14001aa1e  shl     r10, 4
0x14001aa22  add     rdi, r10
0x14001aa25  mov     eax, [rdi+10h]
0x14001aa28  test    al, 1
0x14001aa2a  jz      short loc_14001AA31
0x14001aa2c  mov     sil, 1
0x14001aa2f  jmp     short loc_14001AA3A
0x14001aa31  xor     sil, sil
0x14001aa34  or      eax, 1
0x14001aa37  mov     [rdi+10h], eax
0x14001aa3a  lea     rcx, [r14+0B0h]; SpinLock
0x14001aa41  mov     dl, [rcx+8]; NewIrql
0x14001aa44  call    cs:__imp_KeReleaseSpinLock
0x14001aa4b  nop     dword ptr [rax+rax+00h]
0x14001aa50  lea     r12, WPP_RECORDER_INITIALIZED
0x14001aa57  test    sil, sil
0x14001aa5a  jz      short loc_14001AABE
0x14001aa5c  mov     edx, 30h ; '0'
0x14001aa61  mov     r8d, 6458424Dh
0x14001aa67  lea     ecx, [rdx+10h]
0x14001aa6a  call    cs:__imp_ExAllocatePool2
0x14001aa71  nop     dword ptr [rax+rax+00h]
0x14001aa76  mov     rdi, rax
0x14001aa79  test    rax, rax
0x14001aa7c  jnz     short loc_14001AABA
0x14001aa7e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001aa85  jz      short loc_14001AAD7
0x14001aa87  mov     ecx, [rbx+10h]
0x14001aa8a  lea     r9d, [rax+28h]
0x14001aa8e  mov     [rsp+88h+var_58], ebp
0x14001aa92  lea     rax, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x14001aa99  mov     [rsp+88h+var_60], ecx
0x14001aa9d  lea     r8d, [rdi+4]
0x14001aaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aaa8  mov     dl, 2
0x14001aaaa  mov     [rsp+88h+var_68], rax
0x14001aaaf  mov     rcx, [rcx+40h]
0x14001aab3  call    WPP_RECORDER_SF_DD
0x14001aab8  jmp     short loc_14001AAD7
0x14001aaba  or      dword ptr [rax+10h], 2
0x14001aabe  mov     eax, [rsp+88h+arg_20]
0x14001aac5  mov     [rdi+28h], eax
0x14001aac8  mov     [rdi+14h], ebp
0x14001aacb  mov     [rdi+20h], r15
0x14001aacf  mov     [rdi+18h], rbx
0x14001aad3  lock inc dword ptr [rbx+28h]
0x14001aad7  mov     rbx, [rdi+18h]
0x14001aadb  xor     ebp, ebp
0x14001aadd  mov     r14, [rbx+30h]
0x14001aae1  lea     esi, [rbp+8]
0x14001aae4  mov     rcx, r14; struct _MBB_REQUEST_MANAGER *
0x14001aae7  call    ?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)
0x14001aaec  movsxd  r9, dword ptr [rbx+78h]
0x14001aaf0  lea     r15, cs:140000000h
0x14001aaf7  cmp     r9d, 7
0x14001aafb  ja      short loc_14001AB57
0x14001aafd  movsxd  r8, dword ptr [rdi+14h]
0x14001ab01  cmp     r8d, 5
0x14001ab05  ja      short loc_14001AB57
0x14001ab07  lea     rcx, [r9+r9*2]
0x14001ab0b  lea     rdx, [r8+rcx*2]
0x14001ab0f  mov     esi, rva ?MbbReqFsmTransitionTable@@3PAY05W4MBB_REQUEST_STATE@@A[r15+rdx*4]; MBB_REQUEST_STATE (near * MbbReqFsmTransitionTable)[6] ...
0x14001ab17  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ab1e  jz      short loc_14001AB45
0x14001ab20  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab27  mov     eax, [rbx+10h]
0x14001ab2a  mov     [rsp+88h+var_48], r8d
0x14001ab2f  mov     [rsp+88h+var_50], esi
0x14001ab33  mov     rcx, [rcx+40h]
0x14001ab37  mov     [rsp+88h+var_58], r9d
0x14001ab3c  mov     [rsp+88h+var_60], eax
0x14001ab40  call    WPP_RECORDER_SF_DLLL
0x14001ab45  mov     ebp, [rbx+78h]
0x14001ab48  mov     [rbx+78h], esi
0x14001ab4b  mov     [rbx+7Ch], ebp
0x14001ab4e  mov     eax, [rdi+14h]
0x14001ab51  mov     [rbx+80h], eax
0x14001ab57  lea     rcx, [r14+0B0h]; SpinLock
0x14001ab5e  mov     dl, [rcx+8]; NewIrql
0x14001ab61  call    cs:__imp_KeReleaseSpinLock
0x14001ab68  nop     dword ptr [rax+rax+00h]
0x14001ab6d  cmp     esi, 8
0x14001ab70  jge     short loc_14001AB8A
0x14001ab72  movsxd  rax, esi
0x14001ab75  mov     r8, rdi
0x14001ab78  mov     edx, ebp
0x14001ab7a  mov     rcx, rbx
0x14001ab7d  mov     rax, ds:(?MbbReqFsmStateHandlerTable@@3PAP6AXPEAU_MBB_REQUEST_CONTEXT@@W4MBB_REQUEST_STATE@@PEAU_MBB_EVENT_ENTRY@@@ZA - 140000000h)[r15+rax*8]; void (*near * MbbReqFsmStateHandlerTable)(_MBB_REQUEST_CONTEXT *,MBB_REQUEST_STATE,_MBB_EVENT_ENTRY *)
0x14001ab85  call    _guard_dispatch_icall; CFxObject<NETADAPTER__ *,MbxAdapter,&GetMbxAdapterFromHandle(NETADAPTER__ *),0>::OnCleanup(void)
0x14001ab8a  mov     eax, [rdi+10h]
0x14001ab8d  mov     rsi, [rdi+18h]
0x14001ab91  test    al, 2
0x14001ab93  jz      short loc_14001ABA8
0x14001ab95  xor     edx, edx; Tag
0x14001ab97  mov     rcx, rdi; P
0x14001ab9a  call    cs:__imp_ExFreePoolWithTag
0x14001aba1  nop     dword ptr [rax+rax+00h]
0x14001aba6  jmp     short loc_14001ABCE
0x14001aba8  mov     rbx, [rsi+30h]
0x14001abac  mov     rcx, rbx; struct _MBB_REQUEST_MANAGER *
0x14001abaf  call    ?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)
0x14001abb4  and     dword ptr [rdi+10h], 0FFFFFFFEh
0x14001abb8  lea     rcx, [rbx+0B0h]; SpinLock
0x14001abbf  mov     dl, [rcx+8]; NewIrql
0x14001abc2  call    cs:__imp_KeReleaseSpinLock
0x14001abc9  nop     dword ptr [rax+rax+00h]
0x14001abce  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x14001abd1  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14001abd6  add     rsp, 50h
0x14001abda  pop     r15
0x14001abdc  pop     r14
0x14001abde  pop     r12
0x14001abe0  pop     rdi
0x14001abe1  pop     rsi
0x14001abe2  pop     rbp
0x14001abe3  pop     rbx
0x14001abe4  retn
```

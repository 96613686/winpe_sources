# BfsDereferencePolicyEntryEx

- ea: `0x140006040`
- end: `0x140006197`
- name: `BfsDereferencePolicyEntryEx`
- size: `343`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `18`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001fb0`
- `0x1400055d8`
- `0x140005c0c`
- `0x140005d4c`
- `0x140007044`
- `0x140007250`
- `0x140007890`
- `0x140007b60`
- `0x140007e5c`
- `0x140008598`
- `0x140009530`
- `0x14000995c`
- `0x140009b9c`
- `0x14000a4bc`
- `0x14000a974`
- `0x14000c658`
- `0x14000dadc`
- `0x14000ebf4`

## callees

- `0x140006040`
- `0x14001064c`
- `0x140012b9c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006069`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006069`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000616c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000616c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006094`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006118`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006132`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006152`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006094`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006118`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006132`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006152`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006054`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006054`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006178`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006178`

## pseudocode

```c
void __fastcall BfsDereferencePolicyEntryEx(char *P, char a2)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  char *v8; // rcx
  __int64 v9; // rax
  char **v10; // rdx
  void *v11; // rcx
  void *v12; // rcx

  if ( !a2 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&gBfsPolicyTable, 0);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 36, 0xFFFFFFFF) == 1 )
  {
    v4 = (void *)*((_QWORD *)P + 3);
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    v5 = (void *)*((_QWORD *)P + 4);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    v6 = (void *)*((_QWORD *)P + 5);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    v7 = (void *)*((_QWORD *)P + 6);
    if ( v7 )
      BfsCloseStorage(v7);
    v8 = P + 64;
    v9 = *((_QWORD *)P + 8);
    if ( v9 && *((_QWORD *)P + 9) )
    {
      if ( *(char **)(v9 + 8) != v8 || (v10 = (char **)*((_QWORD *)P + 9), *v10 != v8) )
        __fastfail(3u);
      *v10 = (char *)v9;
      *(_QWORD *)(v9 + 8) = v10;
    }
    v11 = (void *)*((_QWORD *)P + 15);
    if ( v11 )
      ExFreePoolWithTag(v11, 0);
    v12 = (void *)*((_QWORD *)P + 17);
    if ( v12 )
      ExFreePoolWithTag(v12, 0);
    BfsRemoveEntryHashTable(
      (struct _RTL_DYNAMIC_HASH_TABLE *)qword_140019248,
      (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)P);
    ExFreePoolWithTag(P, 0);
  }
  if ( !a2 )
  {
    ExReleasePushLockExclusiveEx(&gBfsPolicyTable, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140006040  mov     [rsp+arg_0], rbx
0x140006045  push    rdi
0x140006046  sub     rsp, 20h
0x14000604a  mov     dil, dl
0x14000604d  mov     rbx, rcx
0x140006050  test    dl, dl
0x140006052  jnz     short loc_140006075
0x140006054  call    cs:__imp_KeEnterCriticalRegion
0x14000605b  nop     dword ptr [rax+rax+00h]
0x140006060  xor     edx, edx
0x140006062  lea     rcx, gBfsPolicyTable
0x140006069  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140006070  nop     dword ptr [rax+rax+00h]
0x140006075  or      eax, 0FFFFFFFFh
0x140006078  lock xadd [rbx+90h], eax
0x140006080  cmp     eax, 1
0x140006083  jnz     loc_14000615E
0x140006089  mov     rcx, [rbx+18h]; P
0x14000608d  test    rcx, rcx
0x140006090  jz      short loc_1400060A0
0x140006092  xor     edx, edx; Tag
0x140006094  call    cs:__imp_ExFreePoolWithTag
0x14000609b  nop     dword ptr [rax+rax+00h]
0x1400060a0  mov     rcx, [rbx+20h]; P
0x1400060a4  test    rcx, rcx
0x1400060a7  jz      short loc_1400060B7
0x1400060a9  xor     edx, edx; Tag
0x1400060ab  call    cs:__imp_ExFreePoolWithTag
0x1400060b2  nop     dword ptr [rax+rax+00h]
0x1400060b7  mov     rcx, [rbx+28h]; P
0x1400060bb  test    rcx, rcx
0x1400060be  jz      short loc_1400060CE
0x1400060c0  xor     edx, edx; Tag
0x1400060c2  call    cs:__imp_ExFreePoolWithTag
0x1400060c9  nop     dword ptr [rax+rax+00h]
0x1400060ce  mov     rcx, [rbx+30h]; P
0x1400060d2  test    rcx, rcx
0x1400060d5  jz      short loc_1400060DC
0x1400060d7  call    BfsCloseStorage
0x1400060dc  lea     rcx, [rbx+40h]
0x1400060e0  mov     rax, [rcx]
0x1400060e3  test    rax, rax
0x1400060e6  jz      short loc_14000610D
0x1400060e8  cmp     qword ptr [rbx+48h], 0
0x1400060ed  jz      short loc_14000610D
0x1400060ef  cmp     [rax+8], rcx
0x1400060f3  jnz     loc_140006190
0x1400060f9  mov     rdx, [rcx+8]
0x1400060fd  cmp     [rdx], rcx
0x140006100  jnz     loc_140006190
0x140006106  mov     [rdx], rax
0x140006109  mov     [rax+8], rdx
0x14000610d  mov     rcx, [rbx+78h]; P
0x140006111  test    rcx, rcx
0x140006114  jz      short loc_140006124
0x140006116  xor     edx, edx; Tag
0x140006118  call    cs:__imp_ExFreePoolWithTag
0x14000611f  nop     dword ptr [rax+rax+00h]
0x140006124  mov     rcx, [rbx+88h]; P
0x14000612b  test    rcx, rcx
0x14000612e  jz      short loc_14000613E
0x140006130  xor     edx, edx; Tag
0x140006132  call    cs:__imp_ExFreePoolWithTag
0x140006139  nop     dword ptr [rax+rax+00h]
0x14000613e  mov     rcx, cs:qword_140019248
0x140006145  mov     rdx, rbx
0x140006148  call    BfsRemoveEntryHashTable
0x14000614d  xor     edx, edx; Tag
0x14000614f  mov     rcx, rbx; P
0x140006152  call    cs:__imp_ExFreePoolWithTag
0x140006159  nop     dword ptr [rax+rax+00h]
0x14000615e  test    dil, dil
0x140006161  jnz     short loc_140006184
0x140006163  xor     edx, edx
0x140006165  lea     rcx, gBfsPolicyTable
0x14000616c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140006173  nop     dword ptr [rax+rax+00h]
0x140006178  call    cs:__imp_KeLeaveCriticalRegion
0x14000617f  nop     dword ptr [rax+rax+00h]
0x140006184  mov     rbx, [rsp+28h+arg_0]
0x140006189  add     rsp, 20h
0x14000618d  pop     rdi
0x14000618e  retn
0x140006190  mov     ecx, 3
0x140006195  int     29h; Win8: RtlFailFast(ecx)
```

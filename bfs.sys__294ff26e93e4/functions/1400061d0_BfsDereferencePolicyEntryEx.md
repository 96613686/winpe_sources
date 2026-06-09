# BfsDereferencePolicyEntryEx

- ea: `0x1400061d0`
- end: `0x140006327`
- name: `BfsDereferencePolicyEntryEx`
- size: `343`
- prototype: `void __fastcall(char *P, char)`
- caller_count: `18`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140001ba0`
- `0x140005768`
- `0x140005d9c`
- `0x140005edc`
- `0x1400071d4`
- `0x1400073e0`
- `0x140007a20`
- `0x140007cf0`
- `0x140007fec`
- `0x140008728`
- `0x1400096c0`
- `0x140009aec`
- `0x140009d2c`
- `0x14000a64c`
- `0x14000ab04`
- `0x14000c7e8`
- `0x14000dc70`
- `0x14000ed84`

## callees

- `0x1400061d0`
- `0x1400107ec`
- `0x140012cd4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400061f9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400061f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400062fc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400062fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006224`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000623b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006252`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400062a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400062c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400062e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006224`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000623b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006252`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400062a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400062c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400062e2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400061e4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400061e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006308`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006308`

## pseudocode

```c
void __fastcall BfsDereferencePolicyEntryEx(char *P, char a2)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  _QWORD *v7; // rcx
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
    v7 = (_QWORD *)*((_QWORD *)P + 6);
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
    BfsRemoveEntryHashTable(qword_140019238, P);
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
0x1400061d0  mov     [rsp+arg_0], rbx
0x1400061d5  push    rdi
0x1400061d6  sub     rsp, 20h
0x1400061da  mov     dil, dl
0x1400061dd  mov     rbx, rcx
0x1400061e0  test    dl, dl
0x1400061e2  jnz     short loc_140006205
0x1400061e4  call    cs:__imp_KeEnterCriticalRegion
0x1400061eb  nop     dword ptr [rax+rax+00h]
0x1400061f0  xor     edx, edx
0x1400061f2  lea     rcx, gBfsPolicyTable
0x1400061f9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140006200  nop     dword ptr [rax+rax+00h]
0x140006205  or      eax, 0FFFFFFFFh
0x140006208  lock xadd [rbx+90h], eax
0x140006210  cmp     eax, 1
0x140006213  jnz     loc_1400062EE
0x140006219  mov     rcx, [rbx+18h]; P
0x14000621d  test    rcx, rcx
0x140006220  jz      short loc_140006230
0x140006222  xor     edx, edx; Tag
0x140006224  call    cs:__imp_ExFreePoolWithTag
0x14000622b  nop     dword ptr [rax+rax+00h]
0x140006230  mov     rcx, [rbx+20h]; P
0x140006234  test    rcx, rcx
0x140006237  jz      short loc_140006247
0x140006239  xor     edx, edx; Tag
0x14000623b  call    cs:__imp_ExFreePoolWithTag
0x140006242  nop     dword ptr [rax+rax+00h]
0x140006247  mov     rcx, [rbx+28h]; P
0x14000624b  test    rcx, rcx
0x14000624e  jz      short loc_14000625E
0x140006250  xor     edx, edx; Tag
0x140006252  call    cs:__imp_ExFreePoolWithTag
0x140006259  nop     dword ptr [rax+rax+00h]
0x14000625e  mov     rcx, [rbx+30h]; P
0x140006262  test    rcx, rcx
0x140006265  jz      short loc_14000626C
0x140006267  call    BfsCloseStorage
0x14000626c  lea     rcx, [rbx+40h]
0x140006270  mov     rax, [rcx]
0x140006273  test    rax, rax
0x140006276  jz      short loc_14000629D
0x140006278  cmp     qword ptr [rbx+48h], 0
0x14000627d  jz      short loc_14000629D
0x14000627f  cmp     [rax+8], rcx
0x140006283  jnz     loc_140006320
0x140006289  mov     rdx, [rcx+8]
0x14000628d  cmp     [rdx], rcx
0x140006290  jnz     loc_140006320
0x140006296  mov     [rdx], rax
0x140006299  mov     [rax+8], rdx
0x14000629d  mov     rcx, [rbx+78h]; P
0x1400062a1  test    rcx, rcx
0x1400062a4  jz      short loc_1400062B4
0x1400062a6  xor     edx, edx; Tag
0x1400062a8  call    cs:__imp_ExFreePoolWithTag
0x1400062af  nop     dword ptr [rax+rax+00h]
0x1400062b4  mov     rcx, [rbx+88h]; P
0x1400062bb  test    rcx, rcx
0x1400062be  jz      short loc_1400062CE
0x1400062c0  xor     edx, edx; Tag
0x1400062c2  call    cs:__imp_ExFreePoolWithTag
0x1400062c9  nop     dword ptr [rax+rax+00h]
0x1400062ce  mov     rcx, cs:qword_140019238
0x1400062d5  mov     rdx, rbx
0x1400062d8  call    BfsRemoveEntryHashTable
0x1400062dd  xor     edx, edx; Tag
0x1400062df  mov     rcx, rbx; P
0x1400062e2  call    cs:__imp_ExFreePoolWithTag
0x1400062e9  nop     dword ptr [rax+rax+00h]
0x1400062ee  test    dil, dil
0x1400062f1  jnz     short loc_140006314
0x1400062f3  xor     edx, edx
0x1400062f5  lea     rcx, gBfsPolicyTable
0x1400062fc  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140006303  nop     dword ptr [rax+rax+00h]
0x140006308  call    cs:__imp_KeLeaveCriticalRegion
0x14000630f  nop     dword ptr [rax+rax+00h]
0x140006314  mov     rbx, [rsp+28h+arg_0]
0x140006319  add     rsp, 20h
0x14000631d  pop     rdi
0x14000631e  retn
0x140006320  mov     ecx, 3
0x140006325  int     29h; Win8: RtlFailFast(ecx)
```

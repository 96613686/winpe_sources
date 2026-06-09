# BfsInitializePolicyTable

- ea: `0x140007790`
- end: `0x14000788a`
- name: `BfsInitializePolicyTable`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140007790`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x1400077aa`
- `ntoskrnl!ExInitializePushLock` at `0x1400077aa`
- `ntoskrnl!RtlCreateHashTable` at `0x1400077f0`
- `ntoskrnl!RtlCreateHashTable` at `0x1400077f0`
- `ntoskrnl!ExAllocateTimer` at `0x140007830`
- `ntoskrnl!ExAllocateTimer` at `0x140007830`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000784d`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000784d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007865`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007865`
- `ntoskrnl!ExAllocatePool2` at `0x1400077c6`
- `ntoskrnl!ExAllocatePool2` at `0x1400077c6`

## pseudocode

```c
__int64 BfsInitializePolicyTable()
{
  unsigned int v1; // ebx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+30h] [rbp+8h] BYREF

  HashTable = 0;
  ExInitializePushLock(&gBfsPolicyTable);
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)ExAllocatePool2(256, 40, 1416848962);
  if ( !HashTable )
    return 3221225495LL;
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    v1 = -1073741823;
LABEL_7:
    ExFreePoolWithTag(HashTable, 0);
    return v1;
  }
  qword_140019258 = (__int64)&qword_140019250;
  qword_140019250 = (__int64)&qword_140019250;
  qword_140019260 = ExAllocateTimer(&BfsIdleCheckTimerCallback, &gBfsPolicyTable, 8);
  if ( !qword_140019260 )
  {
    RtlDeleteHashTable(HashTable);
    v1 = -1073741801;
    goto LABEL_7;
  }
  qword_140019248 = (__int64)HashTable;
  return 0;
}

```

## disassembly

```asm
0x140007790  mov     [rsp+HashTable], rcx
0x140007795  push    rbx
0x140007796  sub     rsp, 20h
0x14000779a  lea     rcx, gBfsPolicyTable; PushLock
0x1400077a1  mov     [rsp+28h+HashTable], 0
0x1400077aa  call    cs:__imp_ExInitializePushLock
0x1400077b1  nop     dword ptr [rax+rax+00h]
0x1400077b6  mov     edx, 28h ; '('
0x1400077bb  mov     ecx, 100h
0x1400077c0  mov     r8d, 54736642h
0x1400077c6  call    cs:__imp_ExAllocatePool2
0x1400077cd  nop     dword ptr [rax+rax+00h]
0x1400077d2  mov     [rsp+28h+HashTable], rax
0x1400077d7  test    rax, rax
0x1400077da  jnz     short loc_1400077E6
0x1400077dc  mov     eax, 0C0000017h
0x1400077e1  jmp     loc_140007883
0x1400077e6  xor     r8d, r8d; Flags
0x1400077e9  lea     rcx, [rsp+28h+HashTable]; HashTable
0x1400077ee  xor     edx, edx; Shift
0x1400077f0  call    cs:__imp_RtlCreateHashTable
0x1400077f7  nop     dword ptr [rax+rax+00h]
0x1400077fc  test    al, al
0x1400077fe  jnz     short loc_140007807
0x140007800  mov     ebx, 0C0000001h
0x140007805  jmp     short loc_14000785E
0x140007807  lea     rax, qword_140019250
0x14000780e  mov     r8d, 8
0x140007814  lea     rdx, gBfsPolicyTable
0x14000781b  mov     cs:qword_140019258, rax
0x140007822  lea     rcx, BfsIdleCheckTimerCallback
0x140007829  mov     cs:qword_140019250, rax
0x140007830  call    cs:__imp_ExAllocateTimer
0x140007837  nop     dword ptr [rax+rax+00h]
0x14000783c  mov     cs:qword_140019260, rax
0x140007843  test    rax, rax
0x140007846  jnz     short loc_140007875
0x140007848  mov     rcx, [rsp+28h+HashTable]; HashTable
0x14000784d  call    cs:__imp_RtlDeleteHashTable
0x140007854  nop     dword ptr [rax+rax+00h]
0x140007859  mov     ebx, 0C0000017h
0x14000785e  mov     rcx, [rsp+28h+HashTable]; P
0x140007863  xor     edx, edx; Tag
0x140007865  call    cs:__imp_ExFreePoolWithTag
0x14000786c  nop     dword ptr [rax+rax+00h]
0x140007871  mov     eax, ebx
0x140007873  jmp     short loc_140007883
0x140007875  mov     rax, [rsp+28h+HashTable]
0x14000787a  mov     cs:qword_140019248, rax
0x140007881  xor     eax, eax
0x140007883  add     rsp, 20h
0x140007887  pop     rbx
0x140007888  retn
```

# BfsInitializePolicyTable

- ea: `0x140007920`
- end: `0x140007a1a`
- name: `BfsInitializePolicyTable`
- size: `250`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140007920`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x14000793a`
- `ntoskrnl!ExInitializePushLock` at `0x14000793a`
- `ntoskrnl!RtlCreateHashTable` at `0x140007980`
- `ntoskrnl!RtlCreateHashTable` at `0x140007980`
- `ntoskrnl!ExAllocateTimer` at `0x1400079c0`
- `ntoskrnl!ExAllocateTimer` at `0x1400079c0`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400079dd`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400079dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079f5`
- `ntoskrnl!ExAllocatePool2` at `0x140007956`
- `ntoskrnl!ExAllocatePool2` at `0x140007956`

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
  qword_140019248 = (__int64)&qword_140019240;
  qword_140019240 = (__int64)&qword_140019240;
  qword_140019250 = ExAllocateTimer(&BfsIdleCheckTimerCallback, &gBfsPolicyTable, 8);
  if ( !qword_140019250 )
  {
    RtlDeleteHashTable(HashTable);
    v1 = -1073741801;
    goto LABEL_7;
  }
  qword_140019238 = (__int64)HashTable;
  return 0;
}

```

## disassembly

```asm
0x140007920  mov     [rsp+HashTable], rcx
0x140007925  push    rbx
0x140007926  sub     rsp, 20h
0x14000792a  lea     rcx, gBfsPolicyTable; PushLock
0x140007931  mov     [rsp+28h+HashTable], 0
0x14000793a  call    cs:__imp_ExInitializePushLock
0x140007941  nop     dword ptr [rax+rax+00h]
0x140007946  mov     edx, 28h ; '('
0x14000794b  mov     ecx, 100h
0x140007950  mov     r8d, 54736642h
0x140007956  call    cs:__imp_ExAllocatePool2
0x14000795d  nop     dword ptr [rax+rax+00h]
0x140007962  mov     [rsp+28h+HashTable], rax
0x140007967  test    rax, rax
0x14000796a  jnz     short loc_140007976
0x14000796c  mov     eax, 0C0000017h
0x140007971  jmp     loc_140007A13
0x140007976  xor     r8d, r8d; Flags
0x140007979  lea     rcx, [rsp+28h+HashTable]; HashTable
0x14000797e  xor     edx, edx; Shift
0x140007980  call    cs:__imp_RtlCreateHashTable
0x140007987  nop     dword ptr [rax+rax+00h]
0x14000798c  test    al, al
0x14000798e  jnz     short loc_140007997
0x140007990  mov     ebx, 0C0000001h
0x140007995  jmp     short loc_1400079EE
0x140007997  lea     rax, qword_140019240
0x14000799e  mov     r8d, 8
0x1400079a4  lea     rdx, gBfsPolicyTable
0x1400079ab  mov     cs:qword_140019248, rax
0x1400079b2  lea     rcx, BfsIdleCheckTimerCallback
0x1400079b9  mov     cs:qword_140019240, rax
0x1400079c0  call    cs:__imp_ExAllocateTimer
0x1400079c7  nop     dword ptr [rax+rax+00h]
0x1400079cc  mov     cs:qword_140019250, rax
0x1400079d3  test    rax, rax
0x1400079d6  jnz     short loc_140007A05
0x1400079d8  mov     rcx, [rsp+28h+HashTable]; HashTable
0x1400079dd  call    cs:__imp_RtlDeleteHashTable
0x1400079e4  nop     dword ptr [rax+rax+00h]
0x1400079e9  mov     ebx, 0C0000017h
0x1400079ee  mov     rcx, [rsp+28h+HashTable]; P
0x1400079f3  xor     edx, edx; Tag
0x1400079f5  call    cs:__imp_ExFreePoolWithTag
0x1400079fc  nop     dword ptr [rax+rax+00h]
0x140007a01  mov     eax, ebx
0x140007a03  jmp     short loc_140007A13
0x140007a05  mov     rax, [rsp+28h+HashTable]
0x140007a0a  mov     cs:qword_140019238, rax
0x140007a11  xor     eax, eax
0x140007a13  add     rsp, 20h
0x140007a17  pop     rbx
0x140007a18  retn
```

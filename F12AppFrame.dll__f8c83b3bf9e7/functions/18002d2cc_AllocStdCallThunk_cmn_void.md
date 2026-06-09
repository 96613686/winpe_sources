# __AllocStdCallThunk_cmn(void)

- ea: `0x18002d2cc`
- end: `0x18002d386`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `PSLIST_ENTRY(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d408`

## callees

- `0x18002d2cc`
- `0x18002d38c`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x18002d34d`
- `KERNEL32!VirtualFree` at `0x18002d34d`
- `KERNEL32!VirtualAlloc` at `0x18002d319`
- `KERNEL32!VirtualAlloc` at `0x18002d319`
- `KERNEL32!InterlockedPushEntrySList` at `0x18002d369`
- `KERNEL32!InterlockedPushEntrySList` at `0x18002d369`
- `KERNEL32!InterlockedPopEntrySList` at `0x18002d2f2`
- `KERNEL32!InterlockedPopEntrySList` at `0x18002d334`
- `KERNEL32!InterlockedPopEntrySList` at `0x18002d2f2`
- `KERNEL32!InterlockedPopEntrySList` at `0x18002d334`

## pseudocode

```c
PSLIST_ENTRY __AllocStdCallThunk_cmn(void)
{
  union _SLIST_HEADER *v0; // rcx
  PSLIST_ENTRY result; // rax
  struct _SLIST_ENTRY *v2; // rbx
  PSLIST_ENTRY v3; // rdi
  struct _SLIST_ENTRY *v4; // rdi

  v0 = __AtlThunkPool;
  if ( !__AtlThunkPool )
  {
    if ( !(unsigned int)_InitializeThunkPool() )
      return 0;
    v0 = __AtlThunkPool;
  }
  result = InterlockedPopEntrySList(v0);
  if ( result )
  {
    *result = 0;
    *(struct _SLIST_ENTRY **)((char *)&result->Next + 14) = 0;
    return result;
  }
  v2 = (struct _SLIST_ENTRY *)VirtualAlloc(0, 0x1000u, 0x1000u, 0x40u);
  if ( !v2 )
    return 0;
  v3 = InterlockedPopEntrySList(__AtlThunkPool);
  if ( v3 )
  {
    VirtualFree(v2, 0, 0x8000u);
    return v3;
  }
  else
  {
    v4 = v2 + 254;
    do
    {
      InterlockedPushEntrySList(__AtlThunkPool, v2);
      v2 += 2;
    }
    while ( v2 < v4 );
    return v2;
  }
}

```

## disassembly

```asm
0x18002d2cc  mov     [rsp+arg_0], rbx
0x18002d2d1  push    rdi
0x18002d2d2  sub     rsp, 20h
0x18002d2d6  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x18002d2dd  test    rcx, rcx
0x18002d2e0  jnz     short loc_18002D2F2
0x18002d2e2  call    __InitializeThunkPool
0x18002d2e7  test    eax, eax
0x18002d2e9  jz      short loc_18002D327
0x18002d2eb  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18002d2f2  call    cs:__imp_InterlockedPopEntrySList
0x18002d2f8  xor     ecx, ecx; lpAddress
0x18002d2fa  test    rax, rax
0x18002d2fd  jz      short loc_18002D30B
0x18002d2ff  xorps   xmm0, xmm0
0x18002d302  movups  xmmword ptr [rax], xmm0
0x18002d305  mov     [rax+0Eh], rcx
0x18002d309  jmp     short loc_18002D37B
0x18002d30b  mov     edx, 1000h; dwSize
0x18002d310  mov     r9d, 40h ; '@'; flProtect
0x18002d316  mov     r8d, edx; flAllocationType
0x18002d319  call    cs:__imp_VirtualAlloc
0x18002d31f  mov     rbx, rax
0x18002d322  test    rax, rax
0x18002d325  jnz     short loc_18002D32B
0x18002d327  xor     eax, eax
0x18002d329  jmp     short loc_18002D37B
0x18002d32b  mov     eax, [rax]
0x18002d32d  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18002d334  call    cs:__imp_InterlockedPopEntrySList
0x18002d33a  mov     rdi, rax
0x18002d33d  test    rax, rax
0x18002d340  jz      short loc_18002D358
0x18002d342  xor     edx, edx; dwSize
0x18002d344  mov     r8d, 8000h; dwFreeType
0x18002d34a  mov     rcx, rbx; lpAddress
0x18002d34d  call    cs:__imp_VirtualFree
0x18002d353  mov     rax, rdi
0x18002d356  jmp     short loc_18002D37B
0x18002d358  lea     rdi, [rbx+0FE0h]
0x18002d35f  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18002d366  mov     rdx, rbx; ListEntry
0x18002d369  call    cs:__imp_InterlockedPushEntrySList
0x18002d36f  add     rbx, 20h ; ' '
0x18002d373  cmp     rbx, rdi
0x18002d376  jb      short loc_18002D35F
0x18002d378  mov     rax, rbx
0x18002d37b  mov     rbx, [rsp+28h+arg_0]
0x18002d380  add     rsp, 20h
0x18002d384  pop     rdi
0x18002d385  retn
```

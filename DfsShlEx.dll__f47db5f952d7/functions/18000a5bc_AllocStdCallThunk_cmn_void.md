# __AllocStdCallThunk_cmn(void)

- ea: `0x18000a5bc`
- end: `0x18000a676`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a6f8`

## callees

- `0x18000a5bc`
- `0x18000a67c`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18000a5e2`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000a624`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000a5e2`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000a624`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000a659`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000a659`
- `KERNEL32!VirtualAlloc` at `0x18000a609`
- `KERNEL32!VirtualAlloc` at `0x18000a609`
- `KERNEL32!VirtualFree` at `0x18000a63d`
- `KERNEL32!VirtualFree` at `0x18000a63d`

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
0x18000a5bc  mov     [rsp+arg_0], rbx
0x18000a5c1  push    rdi
0x18000a5c2  sub     rsp, 20h
0x18000a5c6  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x18000a5cd  test    rcx, rcx
0x18000a5d0  jnz     short loc_18000A5E2
0x18000a5d2  call    __InitializeThunkPool
0x18000a5d7  test    eax, eax
0x18000a5d9  jz      short loc_18000A617
0x18000a5db  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18000a5e2  call    cs:__imp_InterlockedPopEntrySList
0x18000a5e8  xor     ecx, ecx; lpAddress
0x18000a5ea  test    rax, rax
0x18000a5ed  jz      short loc_18000A5FB
0x18000a5ef  xorps   xmm0, xmm0
0x18000a5f2  movups  xmmword ptr [rax], xmm0
0x18000a5f5  mov     [rax+0Eh], rcx
0x18000a5f9  jmp     short loc_18000A66B
0x18000a5fb  mov     edx, 1000h; dwSize
0x18000a600  mov     r9d, 40h ; '@'; flProtect
0x18000a606  mov     r8d, edx; flAllocationType
0x18000a609  call    cs:__imp_VirtualAlloc
0x18000a60f  mov     rbx, rax
0x18000a612  test    rax, rax
0x18000a615  jnz     short loc_18000A61B
0x18000a617  xor     eax, eax
0x18000a619  jmp     short loc_18000A66B
0x18000a61b  mov     eax, [rax]
0x18000a61d  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18000a624  call    cs:__imp_InterlockedPopEntrySList
0x18000a62a  mov     rdi, rax
0x18000a62d  test    rax, rax
0x18000a630  jz      short loc_18000A648
0x18000a632  xor     edx, edx; dwSize
0x18000a634  mov     r8d, 8000h; dwFreeType
0x18000a63a  mov     rcx, rbx; lpAddress
0x18000a63d  call    cs:__imp_VirtualFree
0x18000a643  mov     rax, rdi
0x18000a646  jmp     short loc_18000A66B
0x18000a648  lea     rdi, [rbx+0FE0h]
0x18000a64f  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18000a656  mov     rdx, rbx; ListEntry
0x18000a659  call    cs:__imp_InterlockedPushEntrySList
0x18000a65f  add     rbx, 20h ; ' '
0x18000a663  cmp     rbx, rdi
0x18000a666  jb      short loc_18000A64F
0x18000a668  mov     rax, rbx
0x18000a66b  mov     rbx, [rsp+28h+arg_0]
0x18000a670  add     rsp, 20h
0x18000a674  pop     rdi
0x18000a675  retn
```

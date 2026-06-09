# __AllocStdCallThunk_cmn(void)

- ea: `0x180077c34`
- end: `0x180077cee`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035b90`

## callees

- `0x180077c34`
- `0x180077d18`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x180077cb5`
- `KERNEL32!VirtualFree` at `0x180077cb5`
- `KERNEL32!VirtualAlloc` at `0x180077c81`
- `KERNEL32!VirtualAlloc` at `0x180077c81`
- `KERNEL32!InterlockedPushEntrySList` at `0x180077cd1`
- `KERNEL32!InterlockedPushEntrySList` at `0x180077cd1`
- `KERNEL32!InterlockedPopEntrySList` at `0x180077c5a`
- `KERNEL32!InterlockedPopEntrySList` at `0x180077c9c`
- `KERNEL32!InterlockedPopEntrySList` at `0x180077c5a`
- `KERNEL32!InterlockedPopEntrySList` at `0x180077c9c`

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
0x180077c34  mov     [rsp+arg_0], rbx
0x180077c39  push    rdi
0x180077c3a  sub     rsp, 20h
0x180077c3e  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x180077c45  test    rcx, rcx
0x180077c48  jnz     short loc_180077C5A
0x180077c4a  call    __InitializeThunkPool
0x180077c4f  test    eax, eax
0x180077c51  jz      short loc_180077C8F
0x180077c53  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180077c5a  call    cs:__imp_InterlockedPopEntrySList
0x180077c60  xor     ecx, ecx; lpAddress
0x180077c62  test    rax, rax
0x180077c65  jz      short loc_180077C73
0x180077c67  xorps   xmm0, xmm0
0x180077c6a  movups  xmmword ptr [rax], xmm0
0x180077c6d  mov     [rax+0Eh], rcx
0x180077c71  jmp     short loc_180077CE3
0x180077c73  mov     edx, 1000h; dwSize
0x180077c78  mov     r9d, 40h ; '@'; flProtect
0x180077c7e  mov     r8d, edx; flAllocationType
0x180077c81  call    cs:__imp_VirtualAlloc
0x180077c87  mov     rbx, rax
0x180077c8a  test    rax, rax
0x180077c8d  jnz     short loc_180077C93
0x180077c8f  xor     eax, eax
0x180077c91  jmp     short loc_180077CE3
0x180077c93  mov     eax, [rax]
0x180077c95  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180077c9c  call    cs:__imp_InterlockedPopEntrySList
0x180077ca2  mov     rdi, rax
0x180077ca5  test    rax, rax
0x180077ca8  jz      short loc_180077CC0
0x180077caa  xor     edx, edx; dwSize
0x180077cac  mov     r8d, 8000h; dwFreeType
0x180077cb2  mov     rcx, rbx; lpAddress
0x180077cb5  call    cs:__imp_VirtualFree
0x180077cbb  mov     rax, rdi
0x180077cbe  jmp     short loc_180077CE3
0x180077cc0  lea     rdi, [rbx+0FE0h]
0x180077cc7  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180077cce  mov     rdx, rbx; ListEntry
0x180077cd1  call    cs:__imp_InterlockedPushEntrySList
0x180077cd7  add     rbx, 20h ; ' '
0x180077cdb  cmp     rbx, rdi
0x180077cde  jb      short loc_180077CC7
0x180077ce0  mov     rax, rbx
0x180077ce3  mov     rbx, [rsp+28h+arg_0]
0x180077ce8  add     rsp, 20h
0x180077cec  pop     rdi
0x180077ced  retn
```

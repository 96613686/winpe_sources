# __AllocStdCallThunk_cmn(void)

- ea: `0x180050980`
- end: `0x180050a3a`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180050ae0`

## callees

- `0x180050980`
- `0x180050a64`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800509cd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800509cd`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180050a01`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180050a01`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800509a6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800509e8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800509a6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800509e8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180050a1d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180050a1d`

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
0x180050980  mov     [rsp+arg_0], rbx
0x180050985  push    rdi
0x180050986  sub     rsp, 20h
0x18005098a  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x180050991  test    rcx, rcx
0x180050994  jnz     short loc_1800509A6
0x180050996  call    __InitializeThunkPool
0x18005099b  test    eax, eax
0x18005099d  jz      short loc_1800509DB
0x18005099f  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800509a6  call    cs:__imp_InterlockedPopEntrySList
0x1800509ac  xor     ecx, ecx; lpAddress
0x1800509ae  test    rax, rax
0x1800509b1  jz      short loc_1800509BF
0x1800509b3  xorps   xmm0, xmm0
0x1800509b6  movups  xmmword ptr [rax], xmm0
0x1800509b9  mov     [rax+0Eh], rcx
0x1800509bd  jmp     short loc_180050A2F
0x1800509bf  mov     edx, 1000h; dwSize
0x1800509c4  mov     r9d, 40h ; '@'; flProtect
0x1800509ca  mov     r8d, edx; flAllocationType
0x1800509cd  call    cs:__imp_VirtualAlloc
0x1800509d3  mov     rbx, rax
0x1800509d6  test    rax, rax
0x1800509d9  jnz     short loc_1800509DF
0x1800509db  xor     eax, eax
0x1800509dd  jmp     short loc_180050A2F
0x1800509df  mov     eax, [rax]
0x1800509e1  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800509e8  call    cs:__imp_InterlockedPopEntrySList
0x1800509ee  mov     rdi, rax
0x1800509f1  test    rax, rax
0x1800509f4  jz      short loc_180050A0C
0x1800509f6  xor     edx, edx; dwSize
0x1800509f8  mov     r8d, 8000h; dwFreeType
0x1800509fe  mov     rcx, rbx; lpAddress
0x180050a01  call    cs:__imp_VirtualFree
0x180050a07  mov     rax, rdi
0x180050a0a  jmp     short loc_180050A2F
0x180050a0c  lea     rdi, [rbx+0FE0h]
0x180050a13  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180050a1a  mov     rdx, rbx; ListEntry
0x180050a1d  call    cs:__imp_InterlockedPushEntrySList
0x180050a23  add     rbx, 20h ; ' '
0x180050a27  cmp     rbx, rdi
0x180050a2a  jb      short loc_180050A13
0x180050a2c  mov     rax, rbx
0x180050a2f  mov     rbx, [rsp+28h+arg_0]
0x180050a34  add     rsp, 20h
0x180050a38  pop     rdi
0x180050a39  retn
```

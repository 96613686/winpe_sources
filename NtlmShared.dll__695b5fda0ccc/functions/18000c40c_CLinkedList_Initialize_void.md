# CLinkedList::Initialize(void)

- ea: `0x18000c40c`
- end: `0x18000c445`
- name: `?Initialize@CLinkedList@@QEAAHXZ`
- size: `57`
- prototype: `__int64 __fastcall(CLinkedList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000beb0`

## callees

- `0x18000c40c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c428`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c428`

## pseudocode

```c
__int64 __fastcall CLinkedList::Initialize(CLinkedList *this)
{
  CLinkedList *v1; // rbx

  v1 = g_pBCProvList;
  if ( !*((_DWORD *)g_pBCProvList + 2) )
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)g_pBCProvList + 16));
  *((_DWORD *)v1 + 2) = 1;
  return *((unsigned int *)v1 + 2);
}

```

## disassembly

```asm
0x18000c40c  push    rbx
0x18000c40e  sub     rsp, 30h
0x18000c412  mov     rbx, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x18000c419  mov     [rsp+38h+var_18], rbx
0x18000c41e  cmp     dword ptr [rbx+8], 0
0x18000c422  jnz     short loc_18000C42E
0x18000c424  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000c428  call    cs:__imp_InitializeCriticalSection
0x18000c42e  mov     dword ptr [rbx+8], 1
0x18000c435  jmp     short loc_18000C43C
0x18000c437  mov     rbx, [rsp+38h+var_18]
0x18000c43c  mov     eax, [rbx+8]
0x18000c43f  add     rsp, 30h
0x18000c443  pop     rbx
0x18000c444  retn
```

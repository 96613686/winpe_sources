# winMutexEnd

- ea: `0x18005a6d0`
- end: `0x18005a725`
- name: `winMutexEnd`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18005a6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005a70a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005a70a`

## pseudocode

```c
__int64 winMutexEnd()
{
  __int64 i; // rbx

  if ( _InterlockedCompareExchange(&dword_1800B5BE0, 0, 1) == 1 && dword_1800B5BF8 == 1 )
  {
    for ( i = 0; i != 12; ++i )
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)&unk_1800B57F0 + 48 * i));
    dword_1800B5BF8 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18005a6d0  push    rbx
0x18005a6d2  sub     rsp, 20h
0x18005a6d6  xor     ecx, ecx
0x18005a6d8  lea     eax, [rcx+1]
0x18005a6db  lock cmpxchg cs:dword_1800B5BE0, ecx
0x18005a6e3  jz      short loc_18005A6ED
0x18005a6e5  xor     eax, eax
0x18005a6e7  add     rsp, 20h
0x18005a6eb  pop     rbx
0x18005a6ec  retn
0x18005a6ed  cmp     cs:dword_1800B5BF8, 1
0x18005a6f4  jnz     short loc_18005A6E5
0x18005a6f6  xor     ebx, ebx
0x18005a6f8  lea     rax, unk_1800B57F0
0x18005a6ff  lea     rcx, [rbx+rbx*2]
0x18005a703  shl     rcx, 4
0x18005a707  add     rcx, rax; lpCriticalSection
0x18005a70a  call    cs:__imp_DeleteCriticalSection
0x18005a710  inc     rbx
0x18005a713  cmp     rbx, 0Ch
0x18005a717  jnz     short loc_18005A6F8
0x18005a719  mov     cs:dword_1800B5BF8, 0
0x18005a723  jmp     short loc_18005A6E5
```

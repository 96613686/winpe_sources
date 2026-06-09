# winMutexEnd

- ea: `0x1800a4e60`
- end: `0x1800a4eb3`
- name: `winMutexEnd`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800a4e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a4e92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a4e92`

## pseudocode

```c
__int64 winMutexEnd()
{
  __int64 i; // rbx

  if ( _InterlockedCompareExchange(&dword_1800D0E90, 0, 1) == 1 && dword_1800D0EA8 == 1 )
  {
    for ( i = 0; i != 12; ++i )
      DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800D0A30[6 * i]);
    dword_1800D0EA8 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a4e60  push    rbx
0x1800a4e62  sub     rsp, 20h
0x1800a4e66  xor     ecx, ecx
0x1800a4e68  lea     eax, [rcx+1]
0x1800a4e6b  lock cmpxchg cs:dword_1800D0E90, ecx
0x1800a4e73  jnz     short loc_1800A4EAB
0x1800a4e75  cmp     cs:dword_1800D0EA8, 1
0x1800a4e7c  jnz     short loc_1800A4EAB
0x1800a4e7e  xor     ebx, ebx
0x1800a4e80  lea     rax, qword_1800D0A30
0x1800a4e87  lea     rcx, [rbx+rbx*2]
0x1800a4e8b  shl     rcx, 4
0x1800a4e8f  add     rcx, rax; lpCriticalSection
0x1800a4e92  call    cs:__imp_DeleteCriticalSection
0x1800a4e98  inc     rbx
0x1800a4e9b  cmp     rbx, 0Ch
0x1800a4e9f  jnz     short loc_1800A4E80
0x1800a4ea1  mov     cs:dword_1800D0EA8, 0
0x1800a4eab  xor     eax, eax
0x1800a4ead  add     rsp, 20h
0x1800a4eb1  pop     rbx
0x1800a4eb2  retn
```

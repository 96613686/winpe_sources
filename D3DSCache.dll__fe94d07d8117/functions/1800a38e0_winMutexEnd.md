# winMutexEnd

- ea: `0x1800a38e0`
- end: `0x1800a3933`
- name: `winMutexEnd`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800a38e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a3912`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a3912`

## pseudocode

```c
__int64 winMutexEnd()
{
  __int64 i; // rbx

  if ( _InterlockedCompareExchange(&dword_1800C79B0, 0, 1) == 1 && dword_1800C79C8 == 1 )
  {
    for ( i = 0; i != 12; ++i )
      DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800C6B30[6 * i]);
    dword_1800C79C8 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a38e0  push    rbx
0x1800a38e2  sub     rsp, 20h
0x1800a38e6  xor     ecx, ecx
0x1800a38e8  lea     eax, [rcx+1]
0x1800a38eb  lock cmpxchg cs:dword_1800C79B0, ecx
0x1800a38f3  jnz     short loc_1800A392B
0x1800a38f5  cmp     cs:dword_1800C79C8, 1
0x1800a38fc  jnz     short loc_1800A392B
0x1800a38fe  xor     ebx, ebx
0x1800a3900  lea     rax, qword_1800C6B30
0x1800a3907  lea     rcx, [rbx+rbx*2]
0x1800a390b  shl     rcx, 4
0x1800a390f  add     rcx, rax; lpCriticalSection
0x1800a3912  call    cs:__imp_DeleteCriticalSection
0x1800a3918  inc     rbx
0x1800a391b  cmp     rbx, 0Ch
0x1800a391f  jnz     short loc_1800A3900
0x1800a3921  mov     cs:dword_1800C79C8, 0
0x1800a392b  xor     eax, eax
0x1800a392d  add     rsp, 20h
0x1800a3931  pop     rbx
0x1800a3932  retn
```

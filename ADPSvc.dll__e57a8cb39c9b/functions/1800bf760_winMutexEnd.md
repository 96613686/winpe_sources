# winMutexEnd

- ea: `0x1800bf760`
- end: `0x1800bf7b3`
- name: `winMutexEnd`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800bf760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bf792`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bf792`

## pseudocode

```c
__int64 winMutexEnd()
{
  __int64 i; // rbx

  if ( _InterlockedCompareExchange(&dword_18010F950, 0, 1) == 1 && dword_18010F968 == 1 )
  {
    for ( i = 0; i != 12; ++i )
      DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18010F010[6 * i]);
    dword_18010F968 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800bf760  push    rbx
0x1800bf762  sub     rsp, 20h
0x1800bf766  xor     ecx, ecx
0x1800bf768  lea     eax, [rcx+1]
0x1800bf76b  lock cmpxchg cs:dword_18010F950, ecx
0x1800bf773  jnz     short loc_1800BF7AB
0x1800bf775  cmp     cs:dword_18010F968, 1
0x1800bf77c  jnz     short loc_1800BF7AB
0x1800bf77e  xor     ebx, ebx
0x1800bf780  lea     rax, qword_18010F010
0x1800bf787  lea     rcx, [rbx+rbx*2]
0x1800bf78b  shl     rcx, 4
0x1800bf78f  add     rcx, rax; lpCriticalSection
0x1800bf792  call    cs:__imp_DeleteCriticalSection
0x1800bf798  inc     rbx
0x1800bf79b  cmp     rbx, 0Ch
0x1800bf79f  jnz     short loc_1800BF780
0x1800bf7a1  mov     cs:dword_18010F968, 0
0x1800bf7ab  xor     eax, eax
0x1800bf7ad  add     rsp, 20h
0x1800bf7b1  pop     rbx
0x1800bf7b2  retn
```

# winMutexEnd

- ea: `0x14009fd40`
- end: `0x14009fd93`
- name: `winMutexEnd`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14009fd40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14009fd72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14009fd72`

## pseudocode

```c
__int64 winMutexEnd()
{
  __int64 i; // rbx

  if ( _InterlockedCompareExchange(&dword_1400C9220, 0, 1) == 1 && dword_1400C9238 == 1 )
  {
    for ( i = 0; i != 12; ++i )
      DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1400C8670[6 * i]);
    dword_1400C9238 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14009fd40  push    rbx
0x14009fd42  sub     rsp, 20h
0x14009fd46  xor     ecx, ecx
0x14009fd48  lea     eax, [rcx+1]
0x14009fd4b  lock cmpxchg cs:dword_1400C9220, ecx
0x14009fd53  jnz     short loc_14009FD8B
0x14009fd55  cmp     cs:dword_1400C9238, 1
0x14009fd5c  jnz     short loc_14009FD8B
0x14009fd5e  xor     ebx, ebx
0x14009fd60  lea     rax, qword_1400C8670
0x14009fd67  lea     rcx, [rbx+rbx*2]
0x14009fd6b  shl     rcx, 4
0x14009fd6f  add     rcx, rax; lpCriticalSection
0x14009fd72  call    cs:__imp_DeleteCriticalSection
0x14009fd78  inc     rbx
0x14009fd7b  cmp     rbx, 0Ch
0x14009fd7f  jnz     short loc_14009FD60
0x14009fd81  mov     cs:dword_1400C9238, 0
0x14009fd8b  xor     eax, eax
0x14009fd8d  add     rsp, 20h
0x14009fd91  pop     rbx
0x14009fd92  retn
```

# winMutexEnd

- ea: `0x180021910`
- end: `0x180021976`
- name: `winMutexEnd`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180021910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002194c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002194c`

## pseudocode

```c
__int64 winMutexEnd()
{
  __int64 i; // rbx

  if ( _InterlockedCompareExchange(&dword_18013FC5C, 0, 1) == 1 && dword_18013FC58 == 1 )
  {
    for ( i = 0; i != 12; ++i )
      DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18013C690[6 * i]);
    dword_18013FC58 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180021910  sub     rsp, 28h
0x180021914  xor     ecx, ecx
0x180021916  mov     eax, 1
0x18002191b  lock cmpxchg cs:dword_18013FC5C, ecx
0x180021923  jnz     short loc_18002196F
0x180021925  cmp     cs:dword_18013FC58, 1
0x18002192c  jnz     short loc_18002196F
0x18002192e  mov     [rsp+28h+arg_0], rbx
0x180021933  xor     ebx, ebx
0x180021935  mov     [rsp+28h+var_8], rdi
0x18002193a  lea     rdi, qword_18013C690
0x180021941  lea     rcx, [rbx+rbx*2]
0x180021945  shl     rcx, 4
0x180021949  add     rcx, rdi; lpCriticalSection
0x18002194c  call    cs:__imp_DeleteCriticalSection
0x180021952  inc     rbx
0x180021955  cmp     rbx, 0Ch
0x180021959  jnz     short loc_180021941
0x18002195b  mov     rdi, [rsp+28h+var_8]
0x180021960  mov     rbx, [rsp+28h+arg_0]
0x180021965  mov     cs:dword_18013FC58, 0
0x18002196f  xor     eax, eax
0x180021971  add     rsp, 28h
0x180021975  retn
```

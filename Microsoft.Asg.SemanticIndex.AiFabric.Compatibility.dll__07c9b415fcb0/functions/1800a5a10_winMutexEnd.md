# winMutexEnd

- ea: `0x1800a5a10`
- end: `0x1800a5a71`
- name: `winMutexEnd`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800a5a10`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800a5a49`
- `KERNEL32!DeleteCriticalSection` at `0x1800a5a49`

## pseudocode

```c
__int64 winMutexEnd()
{
  struct _RTL_CRITICAL_SECTION *v0; // rbx
  __int64 v1; // rdi

  if ( _InterlockedCompareExchange(&dword_1803DC8CC, 0, 1) == 1 && dword_1803DC8C8 == 1 )
  {
    v0 = &CriticalSection;
    v1 = 12;
    do
    {
      DeleteCriticalSection(v0);
      v0 = (struct _RTL_CRITICAL_SECTION *)((char *)v0 + 48);
      --v1;
    }
    while ( v1 );
    dword_1803DC8C8 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a5a10  push    rsi
0x1800a5a12  sub     rsp, 20h
0x1800a5a16  xor     esi, esi
0x1800a5a18  mov     eax, 1
0x1800a5a1d  lock cmpxchg cs:dword_1803DC8CC, esi
0x1800a5a25  jnz     short loc_1800A5A69
0x1800a5a27  cmp     cs:dword_1803DC8C8, 1
0x1800a5a2e  jnz     short loc_1800A5A69
0x1800a5a30  mov     [rsp+28h+arg_0], rbx
0x1800a5a35  lea     rbx, CriticalSection
0x1800a5a3c  mov     [rsp+28h+arg_8], rdi
0x1800a5a41  mov     edi, 0Ch
0x1800a5a46  mov     rcx, rbx; lpCriticalSection
0x1800a5a49  call    cs:__imp_DeleteCriticalSection
0x1800a5a4f  add     rbx, 30h ; '0'
0x1800a5a53  sub     rdi, 1
0x1800a5a57  jnz     short loc_1800A5A46
0x1800a5a59  mov     rdi, [rsp+28h+arg_8]
0x1800a5a5e  mov     rbx, [rsp+28h+arg_0]
0x1800a5a63  mov     cs:dword_1803DC8C8, esi
0x1800a5a69  xor     eax, eax
0x1800a5a6b  add     rsp, 20h
0x1800a5a6f  pop     rsi
0x1800a5a70  retn
```

# CTaskCounter::Instance(void)

- ea: `0x180008070`
- end: `0x1800080d6`
- name: `?Instance@CTaskCounter@@SAAEAV1@XZ`
- size: `102`
- prototype: `struct CTaskCounter *(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007af0`
- `0x180007b18`
- `0x180007b54`
- `0x180007bb4`
- `0x180007d34`
- `0x180007ec0`

## callees

- `0x180001c44`
- `0x180002278`
- `0x1800022e8`
- `0x18000754c`
- `0x180008070`

## pseudocode

```c
struct CTaskCounter *CTaskCounter::Instance(void)
{
  CTaskCounter *v0; // rcx

  if ( __TSS0__1__Instance_CTaskCounter__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                      + (unsigned int)tls_index)
                                                                    + 4LL) )
  {
    Init_thread_header(&__TSS0__1__Instance_CTaskCounter__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__Instance_CTaskCounter__SAAEAV2_XZ_4HA == -1 )
    {
      CTaskCounter::CTaskCounter(v0);
      atexit(`CTaskCounter::Instance'::`2'::`dynamic atexit destructor for 'theTaskCounter'');
      Init_thread_footer(&__TSS0__1__Instance_CTaskCounter__SAAEAV2_XZ_4HA);
    }
  }
  return (struct CTaskCounter *)&`CTaskCounter::Instance'::`2'::theTaskCounter;
}

```

## disassembly

```asm
0x180008070  sub     rsp, 28h
0x180008074  mov     ecx, cs:_tls_index
0x18000807a  mov     rax, gs:58h
0x180008083  mov     edx, 4
0x180008088  mov     rax, [rax+rcx*8]
0x18000808c  mov     eax, [rdx+rax]
0x18000808f  cmp     cs:?$TSS0@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4HA, eax
0x180008095  jle     short loc_1800080CA
0x180008097  lea     rcx, ?$TSS0@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4HA
0x18000809e  call    _Init_thread_header
0x1800080a3  cmp     cs:?$TSS0@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x1800080aa  jnz     short loc_1800080CA
0x1800080ac  call    ??0CTaskCounter@@QEAA@XZ; CTaskCounter::CTaskCounter(void)
0x1800080b1  lea     rcx, ??__FtheTaskCounter@?1??Instance@CTaskCounter@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x1800080b8  call    atexit
0x1800080bd  nop
0x1800080be  lea     rcx, ?$TSS0@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4HA
0x1800080c5  call    _Init_thread_footer
0x1800080ca  lea     rax, ?theTaskCounter@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4V2@A; CTaskCounter `CTaskCounter::Instance(void)'::`2'::theTaskCounter
0x1800080d1  add     rsp, 28h
0x1800080d5  retn
```

# CEnrollmentLogger::GetLogger(void)

- ea: `0x1400177b0`
- end: `0x140017802`
- name: `?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ`
- size: `82`
- prototype: `struct CEnrollmentLogger *(void)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x140007f34`
- `0x140009bfc`
- `0x14000d0fc`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e6e8`
- `0x14000eaa8`
- `0x14000ef04`
- `0x14000f56c`
- `0x140010000`
- `0x1400104c0`
- `0x140010a68`

## callees

- `0x1400036a0`
- `0x140003708`
- `0x1400177b0`
- `0x140018060`

## pseudocode

```c
struct CEnrollmentLogger *CEnrollmentLogger::GetLogger(void)
{
  char *v0; // rdx
  const unsigned __int16 *v1; // rcx

  if ( dword_140024954 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_140024954);
    if ( dword_140024954 == -1 )
    {
      GetCorrelationVectorForEnrollmentSession(v1, v0);
      Init_thread_footer(&dword_140024954);
    }
  }
  return (struct CEnrollmentLogger *)&byte_1400248D0;
}

```

## disassembly

```asm
0x1400177b0  sub     rsp, 28h
0x1400177b4  mov     rax, gs:58h
0x1400177bd  mov     ecx, 4
0x1400177c2  mov     rax, [rax]
0x1400177c5  mov     eax, [rcx+rax]
0x1400177c8  cmp     cs:dword_140024954, eax
0x1400177ce  jle     short loc_1400177F6
0x1400177d0  lea     rcx, dword_140024954
0x1400177d7  call    _Init_thread_header
0x1400177dc  cmp     cs:dword_140024954, 0FFFFFFFFh
0x1400177e3  jnz     short loc_1400177F6
0x1400177e5  call    ?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForEnrollmentSession(ushort const *,char *)
0x1400177ea  lea     rcx, dword_140024954
0x1400177f1  call    _Init_thread_footer
0x1400177f6  lea     rax, byte_1400248D0
0x1400177fd  add     rsp, 28h
0x140017801  retn
```

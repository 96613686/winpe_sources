# CEnrollmentLogger::GetLogger(void)

- ea: `0x14001848c`
- end: `0x1400184df`
- name: `?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ`
- size: `83`
- prototype: `struct CEnrollmentLogger *(void)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x14000829c`
- `0x14000a03c`
- `0x14000d780`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`
- `0x140010818`
- `0x140010cf0`
- `0x1400112b0`

## callees

- `0x140003740`
- `0x1400037a8`
- `0x14001848c`
- `0x140018d74`

## pseudocode

```c
struct CEnrollmentLogger *CEnrollmentLogger::GetLogger(void)
{
  char *v0; // rdx
  const unsigned __int16 *v1; // rcx

  if ( dword_140025954 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_140025954);
    if ( dword_140025954 == -1 )
    {
      GetCorrelationVectorForEnrollmentSession(v1, v0);
      Init_thread_footer(&dword_140025954);
    }
  }
  return (struct CEnrollmentLogger *)&byte_1400258D0;
}

```

## disassembly

```asm
0x14001848c  sub     rsp, 28h
0x140018490  mov     rax, gs:58h
0x140018499  mov     ecx, 4
0x14001849e  mov     rax, [rax]
0x1400184a1  mov     eax, [rcx+rax]
0x1400184a4  cmp     cs:dword_140025954, eax
0x1400184aa  jle     short loc_1400184D2
0x1400184ac  lea     rcx, dword_140025954
0x1400184b3  call    _Init_thread_header
0x1400184b8  cmp     cs:dword_140025954, 0FFFFFFFFh
0x1400184bf  jnz     short loc_1400184D2
0x1400184c1  call    ?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForEnrollmentSession(ushort const *,char *)
0x1400184c6  lea     rcx, dword_140025954
0x1400184cd  call    _Init_thread_footer
0x1400184d2  lea     rax, byte_1400258D0
0x1400184d9  add     rsp, 28h
0x1400184dd  retn
```

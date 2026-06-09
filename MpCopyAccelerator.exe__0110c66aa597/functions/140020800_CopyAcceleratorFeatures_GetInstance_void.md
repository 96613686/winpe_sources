# CopyAcceleratorFeatures::GetInstance(void)

- ea: `0x140020800`
- end: `0x14002085b`
- name: `?GetInstance@CopyAcceleratorFeatures@@SAAEAV1@XZ`
- size: `91`
- prototype: `struct CopyAcceleratorFeatures *(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001d700`
- `0x14001dba4`
- `0x14001fce0`
- `0x14001fe40`
- `0x140020730`

## callees

- `0x140005cb8`
- `0x140005d24`
- `0x140006010`
- `0x140020800`

## pseudocode

```c
struct CopyAcceleratorFeatures *CopyAcceleratorFeatures::GetInstance(void)
{
  if ( dword_14003DBE8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_14003DBE8);
    if ( dword_14003DBE8 == -1 )
    {
      atexit(CopyAcceleratorFeatures::GetInstance_::_2_::_dynamic_atexit_destructor_for__m_Singleton__);
      Init_thread_footer(&dword_14003DBE8);
    }
  }
  return (struct CopyAcceleratorFeatures *)&qword_14003DBD8;
}

```

## disassembly

```asm
0x140020800  sub     rsp, 28h
0x140020804  mov     rax, gs:58h
0x14002080d  mov     ecx, 4
0x140020812  mov     rax, [rax]
0x140020815  mov     eax, [rcx+rax]
0x140020818  cmp     cs:dword_14003DBE8, eax
0x14002081e  jg      short loc_14002082C
0x140020820  lea     rax, qword_14003DBD8
0x140020827  add     rsp, 28h
0x14002082b  retn
0x14002082c  lea     rcx, dword_14003DBE8
0x140020833  call    _Init_thread_header
0x140020838  cmp     cs:dword_14003DBE8, 0FFFFFFFFh
0x14002083f  jnz     short loc_140020820
0x140020841  lea     rcx, _CopyAcceleratorFeatures__GetInstance____2____dynamic_atexit_destructor_for__m_Singleton__; void (__cdecl *)()
0x140020848  call    atexit
0x14002084d  lea     rcx, dword_14003DBE8
0x140020854  call    _Init_thread_footer
0x140020859  jmp     short loc_140020820
```

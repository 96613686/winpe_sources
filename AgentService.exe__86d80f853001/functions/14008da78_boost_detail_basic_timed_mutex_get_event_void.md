# boost::detail::basic_timed_mutex::get_event(void)

- ea: `0x14008da78`
- end: `0x14008dadb`
- name: `?get_event@basic_timed_mutex@detail@boost@@AEAAPEAXXZ`
- size: `99`
- prototype: `void *__fastcall(boost::detail::basic_timed_mutex *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14008d448`
- `0x14008d6b4`
- `0x14008dae4`

## callees

- `0x140025b78`
- `0x140026518`
- `0x14008da78`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14008dab3`
- `KERNEL32!CloseHandle` at `0x14008dab3`
- `KERNEL32!CreateEventA` at `0x14008da95`
- `KERNEL32!CreateEventA` at `0x14008da95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HANDLE __fastcall boost::detail::basic_timed_mutex::get_event(boost::detail::basic_timed_mutex *this)
{
  HANDLE result; // rax
  signed __int64 v3; // rbx
  boost::thread_resource_error *v4; // rax
  _BYTE v5[56]; // [rsp+20h] [rbp-38h] BYREF

  result = (HANDLE)*((_QWORD *)this + 1);
  if ( !result )
  {
    result = CreateEventA(0, 0, 0, 0);
    if ( !result )
    {
      v4 = boost::thread_resource_error::thread_resource_error((boost::thread_resource_error *)v5);
      boost::throw_exception<boost::thread_resource_error>((__int64)v4);
    }
    v3 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)result, 0);
    if ( v3 )
    {
      CloseHandle(result);
      return (HANDLE)v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14008da78  push    rbx
0x14008da7a  sub     rsp, 50h
0x14008da7e  mov     rbx, rcx
0x14008da81  mov     rax, [rcx+8]
0x14008da85  nop
0x14008da86  test    rax, rax
0x14008da89  jnz     short loc_14008DAC1
0x14008da8b  xor     r9d, r9d; lpName
0x14008da8e  xor     r8d, r8d; bInitialState
0x14008da91  xor     edx, edx; bManualReset
0x14008da93  xor     ecx, ecx; lpEventAttributes
0x14008da95  call    cs:__imp_CreateEventA
0x14008da9b  mov     rdx, rax
0x14008da9e  test    rax, rax
0x14008daa1  jz      short loc_14008DAC7
0x14008daa3  xor     eax, eax
0x14008daa5  lock cmpxchg [rbx+8], rdx
0x14008daab  mov     rbx, rax
0x14008daae  jz      short loc_14008DABE
0x14008dab0  mov     rcx, rdx; hObject
0x14008dab3  call    cs:__imp_CloseHandle
0x14008dab9  mov     rax, rbx
0x14008dabc  jmp     short loc_14008DAC1
0x14008dabe  mov     rax, rdx
0x14008dac1  add     rsp, 50h
0x14008dac5  pop     rbx
0x14008dac6  retn
0x14008dac7  lea     rcx, [rsp+58h+var_38]; this
0x14008dacc  call    ??0thread_resource_error@boost@@QEAA@XZ; boost::thread_resource_error::thread_resource_error(void)
0x14008dad1  nop
0x14008dad2  mov     rcx, rax
0x14008dad5  call    ??$throw_exception@Vthread_resource_error@boost@@@boost@@YAXAEBVthread_resource_error@0@@Z; boost::throw_exception<boost::thread_resource_error>(boost::thread_resource_error const &)
```

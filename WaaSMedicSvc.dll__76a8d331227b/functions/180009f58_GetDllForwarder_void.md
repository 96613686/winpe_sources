# GetDllForwarder(void)

- ea: `0x180009f58`
- end: `0x180009fc1`
- name: `?GetDllForwarder@@YAAEAUDllForwarder@uus@@XZ`
- size: `105`
- prototype: `void ***(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b900`
- `0x18000b9d0`
- `0x18000bac0`

## callees

- `0x1800025b0`
- `0x18000279c`
- `0x180002804`
- `0x180009f58`
- `0x18000aa84`

## pseudocode

```c
void ***GetDllForwarder(void)
{
  const unsigned __int16 *v1; // rdx
  uus::DllForwarder *v2; // rcx
  const unsigned __int16 *v3; // r8

  if ( dword_180013610 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180013610);
    if ( dword_180013610 == -1 )
    {
      uus::DllForwarder::_Init(v2, v1, v3);
      atexit(GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_180013610);
    }
  }
  return &off_180013090;
}

```

## disassembly

```asm
0x180009f58  sub     rsp, 28h
0x180009f5c  mov     ecx, cs:_tls_index
0x180009f62  mov     rax, gs:58h
0x180009f6b  mov     edx, 4
0x180009f70  mov     rax, [rax+rcx*8]
0x180009f74  mov     eax, [rdx+rax]
0x180009f77  cmp     cs:dword_180013610, eax
0x180009f7d  jg      short loc_180009F8B
0x180009f7f  lea     rax, off_180013090
0x180009f86  add     rsp, 28h
0x180009f8a  retn
0x180009f8b  lea     rcx, dword_180013610
0x180009f92  call    _Init_thread_header
0x180009f97  cmp     cs:dword_180013610, 0FFFFFFFFh
0x180009f9e  jnz     short loc_180009F7F
0x180009fa0  call    ?_Init@DllForwarder@uus@@AEAAXPEBG0@Z; uus::DllForwarder::_Init(ushort const *,ushort const *)
0x180009fa5  nop
0x180009fa6  lea     rcx, _GetDllForwarder____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x180009fad  call    atexit
0x180009fb2  nop
0x180009fb3  lea     rcx, dword_180013610
0x180009fba  call    _Init_thread_footer
0x180009fbf  jmp     short loc_180009F7F
```

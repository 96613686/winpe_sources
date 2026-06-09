# dllmain_crt_process_detach

- ea: `0x1800040fc`
- end: `0x18000417e`
- name: `dllmain_crt_process_detach`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180003f80`

## callees

- `0x180003b64`
- `0x180003c90`
- `0x180003cc0`
- `0x180003e88`
- `0x180003eac`
- `0x1800040fc`
- `0x18000467c`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  unsigned int v2; // ebx
  char v4; // di
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = 0;
  if ( dword_1800081A4 <= 0 )
    return 0;
  --dword_1800081A4;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  _scrt_current_native_startup_state = 0;
  _scrt_dllmain_uninitialize_critical();
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  LOBYTE(v2) = (unsigned __int8)_scrt_uninitialize_crt(v6, 0) != 0;
  return v2;
}

```

## disassembly

```asm
0x1800040fc  mov     [rsp+arg_0], rbx
0x180004101  mov     [rsp+arg_10], rsi
0x180004106  push    rdi
0x180004107  sub     rsp, 20h
0x18000410b  mov     sil, cl
0x18000410e  mov     eax, cs:dword_1800081A4
0x180004114  xor     ebx, ebx
0x180004116  test    eax, eax
0x180004118  jg      short loc_18000411E
0x18000411a  xor     eax, eax
0x18000411c  jmp     short loc_18000416E
0x18000411e  dec     eax
0x180004120  mov     cs:dword_1800081A4, eax
0x180004126  call    __scrt_acquire_startup_lock
0x18000412b  mov     dil, al
0x18000412e  mov     [rsp+28h+arg_8], al
0x180004132  cmp     cs:__scrt_current_native_startup_state, 2
0x180004139  jz      short loc_180004145
0x18000413b  mov     ecx, 7
0x180004140  call    __scrt_fastfail
0x180004145  call    __scrt_dllmain_uninitialize_c
0x18000414a  mov     cs:__scrt_current_native_startup_state, ebx
0x180004150  call    __scrt_dllmain_uninitialize_critical
0x180004155  mov     cl, dil
0x180004158  call    __scrt_release_startup_lock
0x18000415d  xor     edx, edx
0x18000415f  mov     cl, sil
0x180004162  call    __scrt_uninitialize_crt
0x180004167  test    al, al
0x180004169  setnz   bl
0x18000416c  mov     eax, ebx
0x18000416e  mov     rbx, [rsp+28h+arg_0]
0x180004173  mov     rsi, [rsp+28h+arg_10]
0x180004178  add     rsp, 20h
0x18000417c  pop     rdi
0x18000417d  retn
0x180004ee8  push    rbp
0x180004eea  sub     rsp, 20h
0x180004eee  mov     rbp, rdx
0x180004ef1  call    __scrt_dllmain_uninitialize_critical
0x180004ef6  mov     cl, [rbp+38h]
0x180004ef9  add     rsp, 20h
0x180004efd  pop     rbp
0x180004efe  jmp     __scrt_release_startup_lock
```

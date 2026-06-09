# __acrt_update_thread_locale_data

- ea: `0x140078b2c`
- end: `0x140078b9a`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14006dc50`
- `0x140072340`
- `0x140072374`

## callees

- `0x14006d034`
- `0x14006fd48`
- `0x14006fda8`
- `0x1400720a8`
- `0x140078b2c`
- `0x140078b9c`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = sub_1400720A8();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & dword_1400BE1D4) == 0 || (v2 = *v1) == 0 )
  {
    _vcrt_lock_0(4);
    v2 = updatetlocinfoEx_nolock(v1, qword_1400C4918);
    _vcrt_unlock_0(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x140078b2c  mov     [rsp+arg_0], rbx
0x140078b31  push    rdi
0x140078b32  sub     rsp, 20h
0x140078b36  call    sub_1400720A8
0x140078b3b  lea     rdi, [rax+90h]
0x140078b42  mov     ecx, [rax+3A8h]
0x140078b48  mov     eax, cs:dword_1400BE1D4
0x140078b4e  test    eax, ecx
0x140078b50  jz      short loc_140078B5A
0x140078b52  mov     rbx, [rdi]
0x140078b55  test    rbx, rbx
0x140078b58  jnz     short loc_140078B86
0x140078b5a  mov     ecx, 4
0x140078b5f  call    __vcrt_lock_0
0x140078b64  nop
0x140078b65  mov     rdx, cs:qword_1400C4918
0x140078b6c  mov     rcx, rdi
0x140078b6f  call    _updatetlocinfoEx_nolock
0x140078b74  mov     rbx, rax
0x140078b77  mov     ecx, 4
0x140078b7c  call    __vcrt_unlock_0
0x140078b81  test    rbx, rbx
0x140078b84  jz      short loc_140078B94
0x140078b86  mov     rax, rbx
0x140078b89  mov     rbx, [rsp+28h+arg_0]
0x140078b8e  add     rsp, 20h
0x140078b92  pop     rdi
0x140078b93  retn
0x140078b94  call    abort
0x1400858c8  push    rbp; Microsoft VisualC 64bit universal runtime
0x1400858ca  sub     rsp, 20h
0x1400858ce  mov     rbp, rdx
0x1400858d1  mov     ecx, 4
0x1400858d6  add     rsp, 20h
0x1400858da  pop     rbp
0x1400858db  jmp     __vcrt_unlock_0
```

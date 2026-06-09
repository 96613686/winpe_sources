# __acrt_errno_map_os_error

- ea: `0x18000bf4c`
- end: `0x18000bf9a`
- name: `__acrt_errno_map_os_error`
- size: `78`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180012144`
- `0x1800122bc`
- `0x180012af4`
- `0x180012c08`
- `0x180018960`
- `0x1800198dc`
- `0x18001a4a0`

## callees

- `0x18000bf04`
- `0x18000bf4c`
- `0x180010420`

## pseudocode

```c
__int64 __fastcall _acrt_errno_map_os_error(unsigned int a1)
{
  __int64 v2; // rax
  int *v3; // rax
  __int64 v4; // rax
  char *v5; // rbx
  __int64 result; // rax

  v2 = _acrt_getptd_noexit();
  if ( v2 )
    v3 = (int *)(v2 + 36);
  else
    v3 = &dword_18003D0C4;
  *v3 = a1;
  v4 = _acrt_getptd_noexit();
  v5 = byte_18003D0C0;
  if ( v4 )
    v5 = (char *)(v4 + 32);
  result = _acrt_errno_from_os_error(a1);
  *(_DWORD *)v5 = result;
  return result;
}

```

## disassembly

```asm
0x18000bf4c  mov     [rsp+arg_0], rbx
0x18000bf51  push    rdi
0x18000bf52  sub     rsp, 20h
0x18000bf56  mov     edi, ecx
0x18000bf58  call    __acrt_getptd_noexit
0x18000bf5d  test    rax, rax
0x18000bf60  jnz     short loc_18000BF6B
0x18000bf62  lea     rax, dword_18003D0C4
0x18000bf69  jmp     short loc_18000BF6F
0x18000bf6b  add     rax, 24h ; '$'
0x18000bf6f  mov     [rax], edi
0x18000bf71  call    __acrt_getptd_noexit
0x18000bf76  lea     rbx, byte_18003D0C0
0x18000bf7d  test    rax, rax
0x18000bf80  jz      short loc_18000BF86
0x18000bf82  lea     rbx, [rax+20h]
0x18000bf86  mov     ecx, edi
0x18000bf88  call    __acrt_errno_from_os_error
0x18000bf8d  mov     [rbx], eax
0x18000bf8f  mov     rbx, [rsp+28h+arg_0]
0x18000bf94  add     rsp, 20h
0x18000bf98  pop     rdi
0x18000bf99  retn
```

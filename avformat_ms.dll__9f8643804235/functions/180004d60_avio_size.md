# avio_size

- ea: `0x180004d60`
- end: `0x180004dfb`
- name: `avio_size`
- size: `155`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800058b0`
- `0x180008910`
- `0x180008b78`
- `0x180008cf4`
- `0x18000bf38`
- `0x18001507c`
- `0x18001a18c`
- `0x18001b08c`

## callees

- `0x180004d60`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall avio_size(_QWORD *a1)
{
  __int64 result; // rax
  __int64 (__fastcall *v3)(_QWORD, _QWORD, __int64); // rax
  __int64 v4; // rdi

  if ( !a1 )
    return -22;
  result = a1[33];
  if ( !result )
  {
    v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64))a1[8];
    if ( !v3 )
      return -40;
    v4 = v3(a1[5], 0, 0x10000);
    if ( v4 < 0 )
    {
      result = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))a1[8])(a1[5], -1, 2);
      if ( result < 0 )
      {
        _mm_lfence();
        return result;
      }
      v4 = result + 1;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))a1[8])(a1[5], a1[9], 0);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180004d60  mov     [rsp+arg_0], rbx
0x180004d65  push    rdi
0x180004d66  sub     rsp, 20h
0x180004d6a  mov     rbx, rcx
0x180004d6d  test    rcx, rcx
0x180004d70  jnz     short loc_180004D78
0x180004d72  lea     rax, [rcx-16h]
0x180004d76  jmp     short loc_180004DF0
0x180004d78  mov     rax, [rcx+108h]
0x180004d7f  test    rax, rax
0x180004d82  jnz     short loc_180004DF0
0x180004d84  mov     rax, [rcx+40h]
0x180004d88  test    rax, rax
0x180004d8b  jnz     short loc_180004D96
0x180004d8d  mov     rax, 0FFFFFFFFFFFFFFD8h
0x180004d94  jmp     short loc_180004DF0
0x180004d96  mov     rcx, [rcx+28h]
0x180004d9a  xor     edx, edx
0x180004d9c  mov     r8d, 10000h
0x180004da2  call    cs:__guard_dispatch_icall_fptr
0x180004da8  mov     rdi, rax
0x180004dab  test    rax, rax
0x180004dae  jns     short loc_180004DED
0x180004db0  mov     rcx, [rbx+28h]
0x180004db4  mov     r8d, 2
0x180004dba  mov     rax, [rbx+40h]
0x180004dbe  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180004dc2  call    cs:__guard_dispatch_icall_fptr
0x180004dc8  mov     rdi, rax
0x180004dcb  test    rax, rax
0x180004dce  jns     short loc_180004DD5
0x180004dd0  lfence
0x180004dd3  jmp     short loc_180004DF0
0x180004dd5  mov     rdx, [rbx+48h]
0x180004dd9  inc     rdi
0x180004ddc  mov     rcx, [rbx+28h]
0x180004de0  xor     r8d, r8d
0x180004de3  mov     rax, [rbx+40h]
0x180004de7  call    cs:__guard_dispatch_icall_fptr
0x180004ded  mov     rax, rdi
0x180004df0  mov     rbx, [rsp+28h+arg_0]
0x180004df5  add     rsp, 20h
0x180004df9  pop     rdi
0x180004dfa  retn
```

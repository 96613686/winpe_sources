# common_flush_and_write_nolock_char_

- ea: `0x18005c8d4`
- end: `0x18005c99f`
- name: `common_flush_and_write_nolock_char_`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000fd80`
- `0x1800150d0`
- `0x18005c8d4`
- `0x18005ca6c`
- `0x18005cc70`
- `0x18005e024`

## pseudocode

```c
__int64 __fastcall common_flush_and_write_nolock_char_(unsigned __int8 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  bool v8; // al

  fileno((FILE *)a2);
  if ( (*(_DWORD *)(a2 + 20) & 6) == 0 )
  {
    *(_DWORD *)(a3 + 44) = 9;
LABEL_3:
    *(_BYTE *)(a3 + 48) = 1;
LABEL_4:
    _InterlockedOr((volatile signed __int32 *)(a2 + 20), 0x10u);
    return 0xFFFFFFFFLL;
  }
  if ( (*(_DWORD *)(a2 + 20) & 0x1000) != 0 )
  {
    *(_DWORD *)(a3 + 44) = 34;
    goto LABEL_3;
  }
  if ( (*(_DWORD *)(a2 + 20) & 1) != 0 )
  {
    v8 = stream_is_at_end_of_file_nolock(a2);
    *(_DWORD *)(a2 + 16) = 0;
    if ( !v8 )
      goto LABEL_4;
    *(_QWORD *)a2 = *(_QWORD *)(a2 + 8);
    _InterlockedAnd((volatile signed __int32 *)(a2 + 20), 0xFFFFFFFE);
  }
  _InterlockedOr((volatile signed __int32 *)(a2 + 20), 2u);
  _InterlockedAnd((volatile signed __int32 *)(a2 + 20), 0xFFFFFFF7);
  *(_DWORD *)(a2 + 16) = 0;
  if ( (*(_DWORD *)(a2 + 20) & 0x4C0) == 0 && !_acrt_should_use_temporary_buffer((FILE *)a2) )
    _acrt_stdio_allocate_buffer_nolock(a2);
  LOBYTE(v6) = a1;
  if ( !(unsigned __int8)write_buffer_nolock_char_(v6, a2, a3) )
    goto LABEL_4;
  return a1;
}

```

## disassembly

```asm
0x18005c8d4  mov     [rsp+arg_0], rbx
0x18005c8d9  mov     [rsp+arg_8], rsi
0x18005c8de  push    rdi
0x18005c8df  sub     rsp, 20h
0x18005c8e3  mov     esi, ecx
0x18005c8e5  mov     rdi, r8
0x18005c8e8  mov     rcx, rdx; Stream
0x18005c8eb  mov     rbx, rdx
0x18005c8ee  call    _fileno
0x18005c8f3  mov     eax, [rbx+14h]
0x18005c8f6  nop
0x18005c8f7  test    al, 6
0x18005c8f9  jnz     short loc_18005C910
0x18005c8fb  mov     dword ptr [rdi+2Ch], 9
0x18005c902  mov     byte ptr [rdi+30h], 1
0x18005c906  lock or dword ptr [rbx+14h], 10h
0x18005c90b  or      eax, 0FFFFFFFFh
0x18005c90e  jmp     short loc_18005C98F
0x18005c910  mov     eax, [rbx+14h]
0x18005c913  nop
0x18005c914  shr     eax, 0Ch
0x18005c917  test    al, 1
0x18005c919  jz      short loc_18005C924
0x18005c91b  mov     dword ptr [rdi+2Ch], 22h ; '"'
0x18005c922  jmp     short loc_18005C902
0x18005c924  mov     eax, [rbx+14h]
0x18005c927  nop
0x18005c928  test    al, 1
0x18005c92a  jz      short loc_18005C948
0x18005c92c  mov     rcx, rbx
0x18005c92f  call    stream_is_at_end_of_file_nolock
0x18005c934  and     dword ptr [rbx+10h], 0
0x18005c938  test    al, al
0x18005c93a  jz      short loc_18005C906
0x18005c93c  mov     rax, [rbx+8]
0x18005c940  mov     [rbx], rax
0x18005c943  lock and dword ptr [rbx+14h], 0FFFFFFFEh
0x18005c948  lock or dword ptr [rbx+14h], 2
0x18005c94d  lock and dword ptr [rbx+14h], 0FFFFFFF7h
0x18005c952  and     dword ptr [rbx+10h], 0
0x18005c956  mov     eax, [rbx+14h]
0x18005c959  nop
0x18005c95a  test    eax, 4C0h
0x18005c95f  jnz     short loc_18005C975
0x18005c961  mov     rcx, rbx; Stream
0x18005c964  call    __acrt_should_use_temporary_buffer
0x18005c969  test    al, al
0x18005c96b  jnz     short loc_18005C975
0x18005c96d  mov     rcx, rbx
0x18005c970  call    __acrt_stdio_allocate_buffer_nolock
0x18005c975  mov     r8, rdi
0x18005c978  mov     rdx, rbx
0x18005c97b  mov     cl, sil
0x18005c97e  call    write_buffer_nolock_char_
0x18005c983  test    al, al
0x18005c985  jz      loc_18005C906
0x18005c98b  movzx   eax, sil
0x18005c98f  mov     rbx, [rsp+28h+arg_0]
0x18005c994  mov     rsi, [rsp+28h+arg_8]
0x18005c999  add     rsp, 20h
0x18005c99d  pop     rdi
0x18005c99e  retn
```

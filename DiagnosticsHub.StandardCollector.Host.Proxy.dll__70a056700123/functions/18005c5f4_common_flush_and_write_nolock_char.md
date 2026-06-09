# common_flush_and_write_nolock_char_

- ea: `0x18005c5f4`
- end: `0x18005c6bf`
- name: `common_flush_and_write_nolock_char_`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000f620`
- `0x180014970`
- `0x18005c5f4`
- `0x18005c78c`
- `0x18005c990`
- `0x18005dd44`

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
0x18005c5f4  mov     [rsp+arg_0], rbx
0x18005c5f9  mov     [rsp+arg_8], rsi
0x18005c5fe  push    rdi
0x18005c5ff  sub     rsp, 20h
0x18005c603  mov     esi, ecx
0x18005c605  mov     rdi, r8
0x18005c608  mov     rcx, rdx; Stream
0x18005c60b  mov     rbx, rdx
0x18005c60e  call    _fileno
0x18005c613  mov     eax, [rbx+14h]
0x18005c616  nop
0x18005c617  test    al, 6
0x18005c619  jnz     short loc_18005C630
0x18005c61b  mov     dword ptr [rdi+2Ch], 9
0x18005c622  mov     byte ptr [rdi+30h], 1
0x18005c626  lock or dword ptr [rbx+14h], 10h
0x18005c62b  or      eax, 0FFFFFFFFh
0x18005c62e  jmp     short loc_18005C6AF
0x18005c630  mov     eax, [rbx+14h]
0x18005c633  nop
0x18005c634  shr     eax, 0Ch
0x18005c637  test    al, 1
0x18005c639  jz      short loc_18005C644
0x18005c63b  mov     dword ptr [rdi+2Ch], 22h ; '"'
0x18005c642  jmp     short loc_18005C622
0x18005c644  mov     eax, [rbx+14h]
0x18005c647  nop
0x18005c648  test    al, 1
0x18005c64a  jz      short loc_18005C668
0x18005c64c  mov     rcx, rbx
0x18005c64f  call    stream_is_at_end_of_file_nolock
0x18005c654  and     dword ptr [rbx+10h], 0
0x18005c658  test    al, al
0x18005c65a  jz      short loc_18005C626
0x18005c65c  mov     rax, [rbx+8]
0x18005c660  mov     [rbx], rax
0x18005c663  lock and dword ptr [rbx+14h], 0FFFFFFFEh
0x18005c668  lock or dword ptr [rbx+14h], 2
0x18005c66d  lock and dword ptr [rbx+14h], 0FFFFFFF7h
0x18005c672  and     dword ptr [rbx+10h], 0
0x18005c676  mov     eax, [rbx+14h]
0x18005c679  nop
0x18005c67a  test    eax, 4C0h
0x18005c67f  jnz     short loc_18005C695
0x18005c681  mov     rcx, rbx; Stream
0x18005c684  call    __acrt_should_use_temporary_buffer
0x18005c689  test    al, al
0x18005c68b  jnz     short loc_18005C695
0x18005c68d  mov     rcx, rbx
0x18005c690  call    __acrt_stdio_allocate_buffer_nolock
0x18005c695  mov     r8, rdi
0x18005c698  mov     rdx, rbx
0x18005c69b  mov     cl, sil
0x18005c69e  call    write_buffer_nolock_char_
0x18005c6a3  test    al, al
0x18005c6a5  jz      loc_18005C626
0x18005c6ab  movzx   eax, sil
0x18005c6af  mov     rbx, [rsp+28h+arg_0]
0x18005c6b4  mov     rsi, [rsp+28h+arg_8]
0x18005c6b9  add     rsp, 20h
0x18005c6bd  pop     rdi
0x18005c6be  retn
```

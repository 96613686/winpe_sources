# common_flush_and_write_nolock_wchar_t_

- ea: `0x18005c9a0`
- end: `0x18005ca6c`
- name: `common_flush_and_write_nolock_wchar_t_`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000fd80`
- `0x1800150d0`
- `0x18005c9a0`
- `0x18005cb64`
- `0x18005cc70`
- `0x18005e024`

## pseudocode

```c
__int64 __fastcall common_flush_and_write_nolock_wchar_t_(unsigned __int16 a1, __int64 a2, __int64 a3)
{
  bool v7; // al

  fileno((FILE *)a2);
  if ( (*(_DWORD *)(a2 + 20) & 6) == 0 )
  {
    *(_DWORD *)(a3 + 44) = 9;
LABEL_3:
    *(_BYTE *)(a3 + 48) = 1;
LABEL_4:
    _InterlockedOr((volatile signed __int32 *)(a2 + 20), 0x10u);
    return 0xFFFF;
  }
  if ( (*(_DWORD *)(a2 + 20) & 0x1000) != 0 )
  {
    *(_DWORD *)(a3 + 44) = 34;
    goto LABEL_3;
  }
  if ( (*(_DWORD *)(a2 + 20) & 1) != 0 )
  {
    v7 = stream_is_at_end_of_file_nolock(a2);
    *(_DWORD *)(a2 + 16) = 0;
    if ( !v7 )
      goto LABEL_4;
    *(_QWORD *)a2 = *(_QWORD *)(a2 + 8);
    _InterlockedAnd((volatile signed __int32 *)(a2 + 20), 0xFFFFFFFE);
  }
  _InterlockedOr((volatile signed __int32 *)(a2 + 20), 2u);
  _InterlockedAnd((volatile signed __int32 *)(a2 + 20), 0xFFFFFFF7);
  *(_DWORD *)(a2 + 16) = 0;
  if ( (*(_DWORD *)(a2 + 20) & 0x4C0) == 0 && !_acrt_should_use_temporary_buffer((FILE *)a2) )
    _acrt_stdio_allocate_buffer_nolock(a2);
  if ( !(unsigned __int8)write_buffer_nolock_wchar_t_(a1, a2, a3) )
    goto LABEL_4;
  return a1;
}

```

## disassembly

```asm
0x18005c9a0  mov     [rsp+arg_0], rbx
0x18005c9a5  mov     [rsp+arg_8], rsi
0x18005c9aa  push    rdi
0x18005c9ab  sub     rsp, 20h
0x18005c9af  mov     esi, ecx
0x18005c9b1  mov     rdi, r8
0x18005c9b4  mov     rcx, rdx; Stream
0x18005c9b7  mov     rbx, rdx
0x18005c9ba  call    _fileno
0x18005c9bf  mov     eax, [rbx+14h]
0x18005c9c2  nop
0x18005c9c3  test    al, 6
0x18005c9c5  jnz     short loc_18005C9DE
0x18005c9c7  mov     dword ptr [rdi+2Ch], 9
0x18005c9ce  mov     byte ptr [rdi+30h], 1
0x18005c9d2  lock or dword ptr [rbx+14h], 10h
0x18005c9d7  mov     eax, 0FFFFh
0x18005c9dc  jmp     short loc_18005CA5C
0x18005c9de  mov     eax, [rbx+14h]
0x18005c9e1  nop
0x18005c9e2  shr     eax, 0Ch
0x18005c9e5  test    al, 1
0x18005c9e7  jz      short loc_18005C9F2
0x18005c9e9  mov     dword ptr [rdi+2Ch], 22h ; '"'
0x18005c9f0  jmp     short loc_18005C9CE
0x18005c9f2  mov     eax, [rbx+14h]
0x18005c9f5  nop
0x18005c9f6  test    al, 1
0x18005c9f8  jz      short loc_18005CA16
0x18005c9fa  mov     rcx, rbx
0x18005c9fd  call    stream_is_at_end_of_file_nolock
0x18005ca02  and     dword ptr [rbx+10h], 0
0x18005ca06  test    al, al
0x18005ca08  jz      short loc_18005C9D2
0x18005ca0a  mov     rax, [rbx+8]
0x18005ca0e  mov     [rbx], rax
0x18005ca11  lock and dword ptr [rbx+14h], 0FFFFFFFEh
0x18005ca16  lock or dword ptr [rbx+14h], 2
0x18005ca1b  lock and dword ptr [rbx+14h], 0FFFFFFF7h
0x18005ca20  and     dword ptr [rbx+10h], 0
0x18005ca24  mov     eax, [rbx+14h]
0x18005ca27  nop
0x18005ca28  test    eax, 4C0h
0x18005ca2d  jnz     short loc_18005CA43
0x18005ca2f  mov     rcx, rbx; Stream
0x18005ca32  call    __acrt_should_use_temporary_buffer
0x18005ca37  test    al, al
0x18005ca39  jnz     short loc_18005CA43
0x18005ca3b  mov     rcx, rbx
0x18005ca3e  call    __acrt_stdio_allocate_buffer_nolock
0x18005ca43  mov     r8, rdi
0x18005ca46  mov     rdx, rbx
0x18005ca49  movzx   ecx, si
0x18005ca4c  call    write_buffer_nolock_wchar_t_
0x18005ca51  test    al, al
0x18005ca53  jz      loc_18005C9D2
0x18005ca59  movzx   eax, si
0x18005ca5c  mov     rbx, [rsp+28h+arg_0]
0x18005ca61  mov     rsi, [rsp+28h+arg_8]
0x18005ca66  add     rsp, 20h
0x18005ca6a  pop     rdi
0x18005ca6b  retn
```

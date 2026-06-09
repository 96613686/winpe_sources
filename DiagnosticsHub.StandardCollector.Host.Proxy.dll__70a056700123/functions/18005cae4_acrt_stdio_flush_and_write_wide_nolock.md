# __acrt_stdio_flush_and_write_wide_nolock

- ea: `0x18005cae4`
- end: `0x18005cbb0`
- name: `__acrt_stdio_flush_and_write_wide_nolock`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180058510`
- `0x1800585c8`

## callees

- `0x18000f620`
- `0x180014970`
- `0x18005c884`
- `0x18005c990`
- `0x18005cae4`
- `0x18005dd44`

## pseudocode

```c
__int64 __fastcall _acrt_stdio_flush_and_write_wide_nolock(unsigned __int16 a1, __int64 a2, __int64 a3)
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
0x18005cae4  mov     [rsp+arg_0], rbx
0x18005cae9  mov     [rsp+arg_8], rsi
0x18005caee  push    rdi
0x18005caef  sub     rsp, 20h
0x18005caf3  mov     esi, ecx
0x18005caf5  mov     rdi, r8
0x18005caf8  mov     rcx, rdx; Stream
0x18005cafb  mov     rbx, rdx
0x18005cafe  call    _fileno
0x18005cb03  mov     eax, [rbx+14h]
0x18005cb06  nop
0x18005cb07  test    al, 6
0x18005cb09  jnz     short loc_18005CB22
0x18005cb0b  mov     dword ptr [rdi+2Ch], 9
0x18005cb12  mov     byte ptr [rdi+30h], 1
0x18005cb16  lock or dword ptr [rbx+14h], 10h
0x18005cb1b  mov     eax, 0FFFFh
0x18005cb20  jmp     short loc_18005CBA0
0x18005cb22  mov     eax, [rbx+14h]
0x18005cb25  nop
0x18005cb26  shr     eax, 0Ch
0x18005cb29  test    al, 1
0x18005cb2b  jz      short loc_18005CB36
0x18005cb2d  mov     dword ptr [rdi+2Ch], 22h ; '"'
0x18005cb34  jmp     short loc_18005CB12
0x18005cb36  mov     eax, [rbx+14h]
0x18005cb39  nop
0x18005cb3a  test    al, 1
0x18005cb3c  jz      short loc_18005CB5A
0x18005cb3e  mov     rcx, rbx
0x18005cb41  call    stream_is_at_end_of_file_nolock
0x18005cb46  and     dword ptr [rbx+10h], 0
0x18005cb4a  test    al, al
0x18005cb4c  jz      short loc_18005CB16
0x18005cb4e  mov     rax, [rbx+8]
0x18005cb52  mov     [rbx], rax
0x18005cb55  lock and dword ptr [rbx+14h], 0FFFFFFFEh
0x18005cb5a  lock or dword ptr [rbx+14h], 2
0x18005cb5f  lock and dword ptr [rbx+14h], 0FFFFFFF7h
0x18005cb64  and     dword ptr [rbx+10h], 0
0x18005cb68  mov     eax, [rbx+14h]
0x18005cb6b  nop
0x18005cb6c  test    eax, 4C0h
0x18005cb71  jnz     short loc_18005CB87
0x18005cb73  mov     rcx, rbx; Stream
0x18005cb76  call    __acrt_should_use_temporary_buffer
0x18005cb7b  test    al, al
0x18005cb7d  jnz     short loc_18005CB87
0x18005cb7f  mov     rcx, rbx
0x18005cb82  call    __acrt_stdio_allocate_buffer_nolock
0x18005cb87  mov     r8, rdi
0x18005cb8a  mov     rdx, rbx
0x18005cb8d  movzx   ecx, si
0x18005cb90  call    write_buffer_nolock_wchar_t_
0x18005cb95  test    al, al
0x18005cb97  jz      loc_18005CB16
0x18005cb9d  movzx   eax, si
0x18005cba0  mov     rbx, [rsp+28h+arg_0]
0x18005cba5  mov     rsi, [rsp+28h+arg_8]
0x18005cbaa  add     rsp, 20h
0x18005cbae  pop     rdi
0x18005cbaf  retn
```

# __acrt_stdio_flush_and_write_narrow_nolock

- ea: `0x18005ca18`
- end: `0x18005cae3`
- name: `__acrt_stdio_flush_and_write_narrow_nolock`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180058834`
- `0x180058998`
- `0x180058a44`

## callees

- `0x18000f620`
- `0x180014970`
- `0x18005c78c`
- `0x18005c990`
- `0x18005ca18`
- `0x18005dd44`

## pseudocode

```c
__int64 __fastcall _acrt_stdio_flush_and_write_narrow_nolock(unsigned __int8 a1, __int64 a2, __int64 a3)
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
  if ( (*(_DWORD *)(a2 + 20) & 0x4C0) == 0 && !(unsigned __int8)_acrt_should_use_temporary_buffer((FILE *)a2) )
    _acrt_stdio_allocate_buffer_nolock(a2);
  LOBYTE(v6) = a1;
  if ( !(unsigned __int8)write_buffer_nolock_char_(v6, a2, a3) )
    goto LABEL_4;
  return a1;
}

```

## disassembly

```asm
0x18005ca18  mov     [rsp+arg_0], rbx
0x18005ca1d  mov     [rsp+arg_8], rsi
0x18005ca22  push    rdi
0x18005ca23  sub     rsp, 20h
0x18005ca27  mov     esi, ecx
0x18005ca29  mov     rdi, r8
0x18005ca2c  mov     rcx, rdx; Stream
0x18005ca2f  mov     rbx, rdx
0x18005ca32  call    _fileno
0x18005ca37  mov     eax, [rbx+14h]
0x18005ca3a  nop
0x18005ca3b  test    al, 6
0x18005ca3d  jnz     short loc_18005CA54
0x18005ca3f  mov     dword ptr [rdi+2Ch], 9
0x18005ca46  mov     byte ptr [rdi+30h], 1
0x18005ca4a  lock or dword ptr [rbx+14h], 10h
0x18005ca4f  or      eax, 0FFFFFFFFh
0x18005ca52  jmp     short loc_18005CAD3
0x18005ca54  mov     eax, [rbx+14h]
0x18005ca57  nop
0x18005ca58  shr     eax, 0Ch
0x18005ca5b  test    al, 1
0x18005ca5d  jz      short loc_18005CA68
0x18005ca5f  mov     dword ptr [rdi+2Ch], 22h ; '"'
0x18005ca66  jmp     short loc_18005CA46
0x18005ca68  mov     eax, [rbx+14h]
0x18005ca6b  nop
0x18005ca6c  test    al, 1
0x18005ca6e  jz      short loc_18005CA8C
0x18005ca70  mov     rcx, rbx
0x18005ca73  call    stream_is_at_end_of_file_nolock
0x18005ca78  and     dword ptr [rbx+10h], 0
0x18005ca7c  test    al, al
0x18005ca7e  jz      short loc_18005CA4A
0x18005ca80  mov     rax, [rbx+8]
0x18005ca84  mov     [rbx], rax
0x18005ca87  lock and dword ptr [rbx+14h], 0FFFFFFFEh
0x18005ca8c  lock or dword ptr [rbx+14h], 2
0x18005ca91  lock and dword ptr [rbx+14h], 0FFFFFFF7h
0x18005ca96  and     dword ptr [rbx+10h], 0
0x18005ca9a  mov     eax, [rbx+14h]
0x18005ca9d  nop
0x18005ca9e  test    eax, 4C0h
0x18005caa3  jnz     short loc_18005CAB9
0x18005caa5  mov     rcx, rbx; Stream
0x18005caa8  call    __acrt_should_use_temporary_buffer
0x18005caad  test    al, al
0x18005caaf  jnz     short loc_18005CAB9
0x18005cab1  mov     rcx, rbx
0x18005cab4  call    __acrt_stdio_allocate_buffer_nolock
0x18005cab9  mov     r8, rdi
0x18005cabc  mov     rdx, rbx
0x18005cabf  mov     cl, sil
0x18005cac2  call    write_buffer_nolock_char_
0x18005cac7  test    al, al
0x18005cac9  jz      loc_18005CA4A
0x18005cacf  movzx   eax, sil
0x18005cad3  mov     rbx, [rsp+28h+arg_0]
0x18005cad8  mov     rsi, [rsp+28h+arg_8]
0x18005cadd  add     rsp, 20h
0x18005cae1  pop     rdi
0x18005cae2  retn
```

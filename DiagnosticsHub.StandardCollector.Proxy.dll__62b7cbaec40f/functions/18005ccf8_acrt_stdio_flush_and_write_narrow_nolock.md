# __acrt_stdio_flush_and_write_narrow_nolock

- ea: `0x18005ccf8`
- end: `0x18005cdc3`
- name: `__acrt_stdio_flush_and_write_narrow_nolock`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180058b14`
- `0x180058c78`
- `0x180058d24`

## callees

- `0x18000fd80`
- `0x1800150d0`
- `0x18005ca6c`
- `0x18005cc70`
- `0x18005ccf8`
- `0x18005e024`

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
0x18005ccf8  mov     [rsp+arg_0], rbx
0x18005ccfd  mov     [rsp+arg_8], rsi
0x18005cd02  push    rdi
0x18005cd03  sub     rsp, 20h
0x18005cd07  mov     esi, ecx
0x18005cd09  mov     rdi, r8
0x18005cd0c  mov     rcx, rdx; Stream
0x18005cd0f  mov     rbx, rdx
0x18005cd12  call    _fileno
0x18005cd17  mov     eax, [rbx+14h]
0x18005cd1a  nop
0x18005cd1b  test    al, 6
0x18005cd1d  jnz     short loc_18005CD34
0x18005cd1f  mov     dword ptr [rdi+2Ch], 9
0x18005cd26  mov     byte ptr [rdi+30h], 1
0x18005cd2a  lock or dword ptr [rbx+14h], 10h
0x18005cd2f  or      eax, 0FFFFFFFFh
0x18005cd32  jmp     short loc_18005CDB3
0x18005cd34  mov     eax, [rbx+14h]
0x18005cd37  nop
0x18005cd38  shr     eax, 0Ch
0x18005cd3b  test    al, 1
0x18005cd3d  jz      short loc_18005CD48
0x18005cd3f  mov     dword ptr [rdi+2Ch], 22h ; '"'
0x18005cd46  jmp     short loc_18005CD26
0x18005cd48  mov     eax, [rbx+14h]
0x18005cd4b  nop
0x18005cd4c  test    al, 1
0x18005cd4e  jz      short loc_18005CD6C
0x18005cd50  mov     rcx, rbx
0x18005cd53  call    stream_is_at_end_of_file_nolock
0x18005cd58  and     dword ptr [rbx+10h], 0
0x18005cd5c  test    al, al
0x18005cd5e  jz      short loc_18005CD2A
0x18005cd60  mov     rax, [rbx+8]
0x18005cd64  mov     [rbx], rax
0x18005cd67  lock and dword ptr [rbx+14h], 0FFFFFFFEh
0x18005cd6c  lock or dword ptr [rbx+14h], 2
0x18005cd71  lock and dword ptr [rbx+14h], 0FFFFFFF7h
0x18005cd76  and     dword ptr [rbx+10h], 0
0x18005cd7a  mov     eax, [rbx+14h]
0x18005cd7d  nop
0x18005cd7e  test    eax, 4C0h
0x18005cd83  jnz     short loc_18005CD99
0x18005cd85  mov     rcx, rbx; Stream
0x18005cd88  call    __acrt_should_use_temporary_buffer
0x18005cd8d  test    al, al
0x18005cd8f  jnz     short loc_18005CD99
0x18005cd91  mov     rcx, rbx
0x18005cd94  call    __acrt_stdio_allocate_buffer_nolock
0x18005cd99  mov     r8, rdi
0x18005cd9c  mov     rdx, rbx
0x18005cd9f  mov     cl, sil
0x18005cda2  call    write_buffer_nolock_char_
0x18005cda7  test    al, al
0x18005cda9  jz      loc_18005CD2A
0x18005cdaf  movzx   eax, sil
0x18005cdb3  mov     rbx, [rsp+28h+arg_0]
0x18005cdb8  mov     rsi, [rsp+28h+arg_8]
0x18005cdbd  add     rsp, 20h
0x18005cdc1  pop     rdi
0x18005cdc2  retn
```

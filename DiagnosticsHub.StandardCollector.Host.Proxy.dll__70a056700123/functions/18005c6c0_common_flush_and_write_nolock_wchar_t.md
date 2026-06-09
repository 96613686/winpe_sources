# common_flush_and_write_nolock_wchar_t_

- ea: `0x18005c6c0`
- end: `0x18005c78c`
- name: `common_flush_and_write_nolock_wchar_t_`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000f620`
- `0x180014970`
- `0x18005c6c0`
- `0x18005c884`
- `0x18005c990`
- `0x18005dd44`

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
0x18005c6c0  mov     [rsp+arg_0], rbx
0x18005c6c5  mov     [rsp+arg_8], rsi
0x18005c6ca  push    rdi
0x18005c6cb  sub     rsp, 20h
0x18005c6cf  mov     esi, ecx
0x18005c6d1  mov     rdi, r8
0x18005c6d4  mov     rcx, rdx; Stream
0x18005c6d7  mov     rbx, rdx
0x18005c6da  call    _fileno
0x18005c6df  mov     eax, [rbx+14h]
0x18005c6e2  nop
0x18005c6e3  test    al, 6
0x18005c6e5  jnz     short loc_18005C6FE
0x18005c6e7  mov     dword ptr [rdi+2Ch], 9
0x18005c6ee  mov     byte ptr [rdi+30h], 1
0x18005c6f2  lock or dword ptr [rbx+14h], 10h
0x18005c6f7  mov     eax, 0FFFFh
0x18005c6fc  jmp     short loc_18005C77C
0x18005c6fe  mov     eax, [rbx+14h]
0x18005c701  nop
0x18005c702  shr     eax, 0Ch
0x18005c705  test    al, 1
0x18005c707  jz      short loc_18005C712
0x18005c709  mov     dword ptr [rdi+2Ch], 22h ; '"'
0x18005c710  jmp     short loc_18005C6EE
0x18005c712  mov     eax, [rbx+14h]
0x18005c715  nop
0x18005c716  test    al, 1
0x18005c718  jz      short loc_18005C736
0x18005c71a  mov     rcx, rbx
0x18005c71d  call    stream_is_at_end_of_file_nolock
0x18005c722  and     dword ptr [rbx+10h], 0
0x18005c726  test    al, al
0x18005c728  jz      short loc_18005C6F2
0x18005c72a  mov     rax, [rbx+8]
0x18005c72e  mov     [rbx], rax
0x18005c731  lock and dword ptr [rbx+14h], 0FFFFFFFEh
0x18005c736  lock or dword ptr [rbx+14h], 2
0x18005c73b  lock and dword ptr [rbx+14h], 0FFFFFFF7h
0x18005c740  and     dword ptr [rbx+10h], 0
0x18005c744  mov     eax, [rbx+14h]
0x18005c747  nop
0x18005c748  test    eax, 4C0h
0x18005c74d  jnz     short loc_18005C763
0x18005c74f  mov     rcx, rbx; Stream
0x18005c752  call    __acrt_should_use_temporary_buffer
0x18005c757  test    al, al
0x18005c759  jnz     short loc_18005C763
0x18005c75b  mov     rcx, rbx
0x18005c75e  call    __acrt_stdio_allocate_buffer_nolock
0x18005c763  mov     r8, rdi
0x18005c766  mov     rdx, rbx
0x18005c769  movzx   ecx, si
0x18005c76c  call    write_buffer_nolock_wchar_t_
0x18005c771  test    al, al
0x18005c773  jz      loc_18005C6F2
0x18005c779  movzx   eax, si
0x18005c77c  mov     rbx, [rsp+28h+arg_0]
0x18005c781  mov     rsi, [rsp+28h+arg_8]
0x18005c786  add     rsp, 20h
0x18005c78a  pop     rdi
0x18005c78b  retn
```

# common_initialize_environment_nolock_char_

- ea: `0x180005134`
- end: `0x1800051a7`
- name: `common_initialize_environment_nolock_char_`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000501c`
- `0x1800050bc`
- `0x180005a08`
- `0x180005ad4`
- `0x180005b74`

## callees

- `0x180005134`
- `0x180005288`
- `0x180008040`
- `0x18000aba0`
- `0x18000b914`

## pseudocode

```c
__int64 common_initialize_environment_nolock_char_()
{
  unsigned int v0; // edi
  char *narrow_environment_from_os; // rax
  char *v3; // rbx
  void *environment_char; // rax

  v0 = 0;
  if ( environ_table )
    return 0;
  _acrt_initialize_multibyte();
  narrow_environment_from_os = (char *)_dcrt_get_narrow_environment_from_os();
  v3 = narrow_environment_from_os;
  if ( narrow_environment_from_os )
  {
    environment_char = (void *)create_environment_char_(narrow_environment_from_os);
    if ( environment_char )
    {
      _dcrt_initial_narrow_environment = environment_char;
      environ_table = environment_char;
    }
    else
    {
      v0 = -1;
    }
    free_base(0);
    free_base(v3);
    return v0;
  }
  else
  {
    free_base(0);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x180005134  mov     [rsp+arg_0], rbx
0x180005139  push    rdi
0x18000513a  sub     rsp, 20h
0x18000513e  xor     edi, edi
0x180005140  cmp     cs:_environ_table, rdi
0x180005147  jz      short loc_18000514D
0x180005149  xor     eax, eax
0x18000514b  jmp     short loc_18000519C
0x18000514d  call    __acrt_initialize_multibyte
0x180005152  call    __dcrt_get_narrow_environment_from_os
0x180005157  mov     rbx, rax
0x18000515a  test    rax, rax
0x18000515d  jnz     short loc_18000516B
0x18000515f  xor     ecx, ecx; Block
0x180005161  call    _free_base
0x180005166  or      eax, 0FFFFFFFFh
0x180005169  jmp     short loc_18000519C
0x18000516b  mov     rcx, rbx; Source
0x18000516e  call    create_environment_char_
0x180005173  test    rax, rax
0x180005176  jnz     short loc_18000517D
0x180005178  or      edi, 0FFFFFFFFh
0x18000517b  jmp     short loc_18000518B
0x18000517d  mov     cs:__dcrt_initial_narrow_environment, rax
0x180005184  mov     cs:_environ_table, rax
0x18000518b  xor     ecx, ecx; Block
0x18000518d  call    _free_base
0x180005192  mov     rcx, rbx; Block
0x180005195  call    _free_base
0x18000519a  mov     eax, edi
0x18000519c  mov     rbx, [rsp+28h+arg_0]
0x1800051a1  add     rsp, 20h
0x1800051a5  pop     rdi
0x1800051a6  retn
```

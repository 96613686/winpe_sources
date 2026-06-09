# common_initialize_environment_nolock_char_

- ea: `0x1800049d8`
- end: `0x180004a4b`
- name: `common_initialize_environment_nolock_char_`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800048c0`
- `0x180004960`
- `0x1800052ac`
- `0x180005378`
- `0x180005418`

## callees

- `0x1800049d8`
- `0x180004b2c`
- `0x1800078e0`
- `0x18000a440`
- `0x18000b1b4`

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
0x1800049d8  mov     [rsp+arg_0], rbx
0x1800049dd  push    rdi
0x1800049de  sub     rsp, 20h
0x1800049e2  xor     edi, edi
0x1800049e4  cmp     cs:_environ_table, rdi
0x1800049eb  jz      short loc_1800049F1
0x1800049ed  xor     eax, eax
0x1800049ef  jmp     short loc_180004A40
0x1800049f1  call    __acrt_initialize_multibyte
0x1800049f6  call    __dcrt_get_narrow_environment_from_os
0x1800049fb  mov     rbx, rax
0x1800049fe  test    rax, rax
0x180004a01  jnz     short loc_180004A0F
0x180004a03  xor     ecx, ecx; Block
0x180004a05  call    _free_base
0x180004a0a  or      eax, 0FFFFFFFFh
0x180004a0d  jmp     short loc_180004A40
0x180004a0f  mov     rcx, rbx; Source
0x180004a12  call    create_environment_char_
0x180004a17  test    rax, rax
0x180004a1a  jnz     short loc_180004A21
0x180004a1c  or      edi, 0FFFFFFFFh
0x180004a1f  jmp     short loc_180004A2F
0x180004a21  mov     cs:__dcrt_initial_narrow_environment, rax
0x180004a28  mov     cs:_environ_table, rax
0x180004a2f  xor     ecx, ecx; Block
0x180004a31  call    _free_base
0x180004a36  mov     rcx, rbx; Block
0x180004a39  call    _free_base
0x180004a3e  mov     eax, edi
0x180004a40  mov     rbx, [rsp+28h+arg_0]
0x180004a45  add     rsp, 20h
0x180004a49  pop     rdi
0x180004a4a  retn
```

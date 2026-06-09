# common_initialize_environment_nolock_char_

- ea: `0x18000df28`
- end: `0x18000df94`
- name: `common_initialize_environment_nolock_char_`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e150`

## callees

- `0x18000df28`
- `0x18000df94`
- `0x18000fe3c`
- `0x180013450`
- `0x180013954`

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
    environment_char = create_environment_char_(narrow_environment_from_os);
    if ( environment_char )
    {
      _dcrt_initial_narrow_environment = environment_char;
      environ_table = (__int64)environment_char;
    }
    else
    {
      v0 = -1;
    }
    free_base(0);
  }
  else
  {
    v0 = -1;
  }
  free_base(v3);
  return v0;
}

```

## disassembly

```asm
0x18000df28  mov     [rsp+arg_0], rbx
0x18000df2d  push    rdi
0x18000df2e  sub     rsp, 20h
0x18000df32  xor     edi, edi
0x18000df34  cmp     cs:_environ_table, rdi
0x18000df3b  jz      short loc_18000DF41
0x18000df3d  xor     eax, eax
0x18000df3f  jmp     short loc_18000DF89
0x18000df41  call    __acrt_initialize_multibyte
0x18000df46  call    __dcrt_get_narrow_environment_from_os
0x18000df4b  mov     rbx, rax
0x18000df4e  test    rax, rax
0x18000df51  jnz     short loc_18000DF58
0x18000df53  or      edi, 0FFFFFFFFh
0x18000df56  jmp     short loc_18000DF7F
0x18000df58  mov     rcx, rbx; Source
0x18000df5b  call    create_environment_char_
0x18000df60  test    rax, rax
0x18000df63  jnz     short loc_18000DF6A
0x18000df65  or      edi, 0FFFFFFFFh
0x18000df68  jmp     short loc_18000DF78
0x18000df6a  mov     cs:__dcrt_initial_narrow_environment, rax
0x18000df71  mov     cs:_environ_table, rax
0x18000df78  xor     ecx, ecx; Block
0x18000df7a  call    _free_base
0x18000df7f  mov     rcx, rbx; Block
0x18000df82  call    _free_base
0x18000df87  mov     eax, edi
0x18000df89  mov     rbx, [rsp+28h+arg_0]
0x18000df8e  add     rsp, 20h
0x18000df92  pop     rdi
0x18000df93  retn
```

# common_show_message_box_char_

- ea: `0x180021134`
- end: `0x1800211d5`
- name: `common_show_message_box_char_`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800073c0`
- `0x180007434`
- `0x18000df34`
- `0x18000e17c`
- `0x18000e400`
- `0x18000e4d0`
- `0x180021134`
- `0x18002219c`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180021151`
- `KERNEL32!IsDebuggerPresent` at `0x180021151`

## pseudocode

```c
__int64 __fastcall common_show_message_box_char_(__int64 a1, __int64 a2, unsigned int a3)
{
  BOOL v6; // ebx
  __int64 parent_window; // rcx

  v6 = IsDebuggerPresent();
  if ( v6 )
  {
    if ( a1 )
      _acrt_OutputDebugStringA(a1);
    if ( (unsigned int)_acrt_get_windowing_model_policy() != 1 )
      return 4;
  }
  if ( (unsigned int)_acrt_get_developer_information_policy() != 2 || !(unsigned __int8)_acrt_can_show_message_box() )
    return (unsigned int)v6 + 3;
  if ( (unsigned __int8)_acrt_is_interactive() )
  {
    parent_window = _acrt_get_parent_window();
  }
  else
  {
    a3 |= 0x200000u;
    parent_window = 0;
  }
  return _acrt_MessageBoxA(parent_window, a1, a2, a3);
}

```

## disassembly

```asm
0x180021134  mov     [rsp+arg_0], rbx
0x180021139  mov     [rsp+arg_8], rbp
0x18002113e  mov     [rsp+arg_10], rsi
0x180021143  push    rdi
0x180021144  sub     rsp, 20h
0x180021148  mov     esi, r8d
0x18002114b  mov     rbp, rdx
0x18002114e  mov     rdi, rcx
0x180021151  call    cs:__imp_IsDebuggerPresent
0x180021157  mov     ebx, eax
0x180021159  test    eax, eax
0x18002115b  jz      short loc_18002117B
0x18002115d  test    rdi, rdi
0x180021160  jz      short loc_18002116A
0x180021162  mov     rcx, rdi
0x180021165  call    __acrt_OutputDebugStringA
0x18002116a  call    __acrt_get_windowing_model_policy
0x18002116f  cmp     eax, 1
0x180021172  jz      short loc_18002117B
0x180021174  mov     eax, 4
0x180021179  jmp     short loc_1800211C0
0x18002117b  call    __acrt_get_developer_information_policy
0x180021180  cmp     eax, 2
0x180021183  jnz     short loc_1800211B7
0x180021185  call    __acrt_can_show_message_box
0x18002118a  test    al, al
0x18002118c  jz      short loc_1800211B7
0x18002118e  call    __acrt_is_interactive
0x180021193  test    al, al
0x180021195  jnz     short loc_1800211AD
0x180021197  bts     esi, 15h
0x18002119b  xor     ecx, ecx
0x18002119d  mov     rdx, rdi
0x1800211a0  mov     r8, rbp
0x1800211a3  mov     r9d, esi
0x1800211a6  call    __acrt_MessageBoxA
0x1800211ab  jmp     short loc_1800211C0
0x1800211ad  call    __acrt_get_parent_window
0x1800211b2  mov     rcx, rax
0x1800211b5  jmp     short loc_18002119D
0x1800211b7  neg     ebx
0x1800211b9  sbb     eax, eax
0x1800211bb  neg     eax
0x1800211bd  add     eax, 3
0x1800211c0  mov     rbx, [rsp+28h+arg_0]
0x1800211c5  mov     rbp, [rsp+28h+arg_8]
0x1800211ca  mov     rsi, [rsp+28h+arg_10]
0x1800211cf  add     rsp, 20h
0x1800211d3  pop     rdi
0x1800211d4  retn
```

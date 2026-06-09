# common_show_message_box_char_

- ea: `0x1800209d4`
- end: `0x180020a75`
- name: `common_show_message_box_char_`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006c60`
- `0x180006cd4`
- `0x18000d7d4`
- `0x18000da1c`
- `0x18000dca0`
- `0x18000dd70`
- `0x1800209d4`
- `0x180021a3c`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800209f1`
- `KERNEL32!IsDebuggerPresent` at `0x1800209f1`

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
0x1800209d4  mov     [rsp+arg_0], rbx
0x1800209d9  mov     [rsp+arg_8], rbp
0x1800209de  mov     [rsp+arg_10], rsi
0x1800209e3  push    rdi
0x1800209e4  sub     rsp, 20h
0x1800209e8  mov     esi, r8d
0x1800209eb  mov     rbp, rdx
0x1800209ee  mov     rdi, rcx
0x1800209f1  call    cs:__imp_IsDebuggerPresent
0x1800209f7  mov     ebx, eax
0x1800209f9  test    eax, eax
0x1800209fb  jz      short loc_180020A1B
0x1800209fd  test    rdi, rdi
0x180020a00  jz      short loc_180020A0A
0x180020a02  mov     rcx, rdi
0x180020a05  call    __acrt_OutputDebugStringA
0x180020a0a  call    __acrt_get_windowing_model_policy
0x180020a0f  cmp     eax, 1
0x180020a12  jz      short loc_180020A1B
0x180020a14  mov     eax, 4
0x180020a19  jmp     short loc_180020A60
0x180020a1b  call    __acrt_get_developer_information_policy
0x180020a20  cmp     eax, 2
0x180020a23  jnz     short loc_180020A57
0x180020a25  call    __acrt_can_show_message_box
0x180020a2a  test    al, al
0x180020a2c  jz      short loc_180020A57
0x180020a2e  call    __acrt_is_interactive
0x180020a33  test    al, al
0x180020a35  jnz     short loc_180020A4D
0x180020a37  bts     esi, 15h
0x180020a3b  xor     ecx, ecx
0x180020a3d  mov     rdx, rdi
0x180020a40  mov     r8, rbp
0x180020a43  mov     r9d, esi
0x180020a46  call    __acrt_MessageBoxA
0x180020a4b  jmp     short loc_180020A60
0x180020a4d  call    __acrt_get_parent_window
0x180020a52  mov     rcx, rax
0x180020a55  jmp     short loc_180020A3D
0x180020a57  neg     ebx
0x180020a59  sbb     eax, eax
0x180020a5b  neg     eax
0x180020a5d  add     eax, 3
0x180020a60  mov     rbx, [rsp+28h+arg_0]
0x180020a65  mov     rbp, [rsp+28h+arg_8]
0x180020a6a  mov     rsi, [rsp+28h+arg_10]
0x180020a6f  add     rsp, 20h
0x180020a73  pop     rdi
0x180020a74  retn
```

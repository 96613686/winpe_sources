# common_show_message_box_wchar_t_

- ea: `0x180020a78`
- end: `0x180020b1a`
- name: `common_show_message_box_wchar_t_`
- size: `162`
- prototype: `__int64 __fastcall(LPCWSTR lpOutputString)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006c60`
- `0x180006cd4`
- `0x18000d854`
- `0x18000da1c`
- `0x18000dca0`
- `0x18000dd70`
- `0x180020a78`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180020aa9`
- `KERNEL32!OutputDebugStringW` at `0x180020aa9`
- `KERNEL32!IsDebuggerPresent` at `0x180020a95`
- `KERNEL32!IsDebuggerPresent` at `0x180020a95`

## pseudocode

```c
__int64 __fastcall common_show_message_box_wchar_t_(LPCWSTR lpOutputString, __int64 a2, unsigned int a3)
{
  BOOL v6; // ebx
  __int64 parent_window; // rcx

  v6 = IsDebuggerPresent();
  if ( v6 )
  {
    if ( lpOutputString )
      OutputDebugStringW(lpOutputString);
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
  return _acrt_MessageBoxW(parent_window, lpOutputString, a2, a3);
}

```

## disassembly

```asm
0x180020a78  mov     [rsp+arg_0], rbx
0x180020a7d  mov     [rsp+arg_8], rbp
0x180020a82  mov     [rsp+arg_10], rsi
0x180020a87  push    rdi
0x180020a88  sub     rsp, 20h
0x180020a8c  mov     esi, r8d
0x180020a8f  mov     rbp, rdx
0x180020a92  mov     rdi, rcx
0x180020a95  call    cs:__imp_IsDebuggerPresent
0x180020a9b  mov     ebx, eax
0x180020a9d  test    eax, eax
0x180020a9f  jz      short loc_180020AC0
0x180020aa1  test    rdi, rdi
0x180020aa4  jz      short loc_180020AAF
0x180020aa6  mov     rcx, rdi; lpOutputString
0x180020aa9  call    cs:__imp_OutputDebugStringW
0x180020aaf  call    __acrt_get_windowing_model_policy
0x180020ab4  cmp     eax, 1
0x180020ab7  jz      short loc_180020AC0
0x180020ab9  mov     eax, 4
0x180020abe  jmp     short loc_180020B05
0x180020ac0  call    __acrt_get_developer_information_policy
0x180020ac5  cmp     eax, 2
0x180020ac8  jnz     short loc_180020AFC
0x180020aca  call    __acrt_can_show_message_box
0x180020acf  test    al, al
0x180020ad1  jz      short loc_180020AFC
0x180020ad3  call    __acrt_is_interactive
0x180020ad8  test    al, al
0x180020ada  jnz     short loc_180020AF2
0x180020adc  bts     esi, 15h
0x180020ae0  xor     ecx, ecx
0x180020ae2  mov     rdx, rdi
0x180020ae5  mov     r8, rbp
0x180020ae8  mov     r9d, esi
0x180020aeb  call    __acrt_MessageBoxW
0x180020af0  jmp     short loc_180020B05
0x180020af2  call    __acrt_get_parent_window
0x180020af7  mov     rcx, rax
0x180020afa  jmp     short loc_180020AE2
0x180020afc  neg     ebx
0x180020afe  sbb     eax, eax
0x180020b00  neg     eax
0x180020b02  add     eax, 3
0x180020b05  mov     rbx, [rsp+28h+arg_0]
0x180020b0a  mov     rbp, [rsp+28h+arg_8]
0x180020b0f  mov     rsi, [rsp+28h+arg_10]
0x180020b14  add     rsp, 20h
0x180020b18  pop     rdi
0x180020b19  retn
```

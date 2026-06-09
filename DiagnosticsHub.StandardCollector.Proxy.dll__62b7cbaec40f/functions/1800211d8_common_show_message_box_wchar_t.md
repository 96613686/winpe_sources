# common_show_message_box_wchar_t_

- ea: `0x1800211d8`
- end: `0x18002127a`
- name: `common_show_message_box_wchar_t_`
- size: `162`
- prototype: `__int64 __fastcall(LPCWSTR lpOutputString)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800073c0`
- `0x180007434`
- `0x18000dfb4`
- `0x18000e17c`
- `0x18000e400`
- `0x18000e4d0`
- `0x1800211d8`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180021209`
- `KERNEL32!OutputDebugStringW` at `0x180021209`
- `KERNEL32!IsDebuggerPresent` at `0x1800211f5`
- `KERNEL32!IsDebuggerPresent` at `0x1800211f5`

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
0x1800211d8  mov     [rsp+arg_0], rbx
0x1800211dd  mov     [rsp+arg_8], rbp
0x1800211e2  mov     [rsp+arg_10], rsi
0x1800211e7  push    rdi
0x1800211e8  sub     rsp, 20h
0x1800211ec  mov     esi, r8d
0x1800211ef  mov     rbp, rdx
0x1800211f2  mov     rdi, rcx
0x1800211f5  call    cs:__imp_IsDebuggerPresent
0x1800211fb  mov     ebx, eax
0x1800211fd  test    eax, eax
0x1800211ff  jz      short loc_180021220
0x180021201  test    rdi, rdi
0x180021204  jz      short loc_18002120F
0x180021206  mov     rcx, rdi; lpOutputString
0x180021209  call    cs:__imp_OutputDebugStringW
0x18002120f  call    __acrt_get_windowing_model_policy
0x180021214  cmp     eax, 1
0x180021217  jz      short loc_180021220
0x180021219  mov     eax, 4
0x18002121e  jmp     short loc_180021265
0x180021220  call    __acrt_get_developer_information_policy
0x180021225  cmp     eax, 2
0x180021228  jnz     short loc_18002125C
0x18002122a  call    __acrt_can_show_message_box
0x18002122f  test    al, al
0x180021231  jz      short loc_18002125C
0x180021233  call    __acrt_is_interactive
0x180021238  test    al, al
0x18002123a  jnz     short loc_180021252
0x18002123c  bts     esi, 15h
0x180021240  xor     ecx, ecx
0x180021242  mov     rdx, rdi
0x180021245  mov     r8, rbp
0x180021248  mov     r9d, esi
0x18002124b  call    __acrt_MessageBoxW
0x180021250  jmp     short loc_180021265
0x180021252  call    __acrt_get_parent_window
0x180021257  mov     rcx, rax
0x18002125a  jmp     short loc_180021242
0x18002125c  neg     ebx
0x18002125e  sbb     eax, eax
0x180021260  neg     eax
0x180021262  add     eax, 3
0x180021265  mov     rbx, [rsp+28h+arg_0]
0x18002126a  mov     rbp, [rsp+28h+arg_8]
0x18002126f  mov     rsi, [rsp+28h+arg_10]
0x180021274  add     rsp, 20h
0x180021278  pop     rdi
0x180021279  retn
```

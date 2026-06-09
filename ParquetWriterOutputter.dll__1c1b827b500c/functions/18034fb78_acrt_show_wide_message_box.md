# __acrt_show_wide_message_box

- ea: `0x18034fb78`
- end: `0x18034fc91`
- name: `__acrt_show_wide_message_box`
- size: `281`
- prototype: `__int64 __fastcall(LPCWSTR lpOutputString)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180344c84`

## callees

- `0x18034ea6c`
- `0x18034eb80`
- `0x18034ec0c`
- `0x18034ecd8`
- `0x18034edac`
- `0x18034fb78`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18034fc3d`
- `KERNEL32!CloseHandle` at `0x18034fc3d`
- `KERNEL32!WaitForSingleObjectEx` at `0x18034fc30`
- `KERNEL32!WaitForSingleObjectEx` at `0x18034fc30`
- `KERNEL32!IsDebuggerPresent` at `0x18034fba2`
- `KERNEL32!IsDebuggerPresent` at `0x18034fbd4`
- `KERNEL32!IsDebuggerPresent` at `0x18034fba2`
- `KERNEL32!IsDebuggerPresent` at `0x18034fbd4`
- `KERNEL32!CreateThread` at `0x18034fc18`
- `KERNEL32!CreateThread` at `0x18034fc18`
- `KERNEL32!OutputDebugStringW` at `0x18034fbb6`
- `KERNEL32!OutputDebugStringW` at `0x18034fbb6`

## pseudocode

```c
__int64 __fastcall _acrt_show_wide_message_box(LPCWSTR lpOutputString, __int64 a2, unsigned int a3)
{
  char is_packaged_app; // bp
  unsigned int v7; // edi
  HANDLE Thread; // rax
  void *v9; // rbx
  __int64 parent_window; // rcx
  _QWORD Parameter[2]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v13; // [rsp+40h] [rbp-18h]
  unsigned int v14; // [rsp+44h] [rbp-14h]

  is_packaged_app = _acrt_is_packaged_app();
  v7 = 0;
  if ( !IsDebuggerPresent() )
    goto LABEL_20;
  if ( lpOutputString )
    OutputDebugStringW(lpOutputString);
  if ( is_packaged_app )
  {
    return 4;
  }
  else
  {
LABEL_20:
    if ( (unsigned __int8)_acrt_can_show_message_box() )
    {
      if ( is_packaged_app )
      {
        Parameter[0] = a2;
        Parameter[1] = lpOutputString;
        v13 = a3;
        v14 = 0;
        Thread = CreateThread(0, 0, message_box_wait_thread_wchar_t_, Parameter, 0, 0);
        v9 = Thread;
        if ( Thread != (HANDLE)-1LL )
        {
          if ( !WaitForSingleObjectEx(Thread, 0xFFFFFFFF, 0) )
            v7 = v14;
          CloseHandle(v9);
        }
      }
      else
      {
        if ( (unsigned __int8)_acrt_is_interactive() )
        {
          parent_window = _acrt_get_parent_window();
        }
        else
        {
          a3 |= 0x200000u;
          parent_window = 0;
        }
        return (unsigned int)_acrt_MessageBoxW(parent_window, lpOutputString, a2, a3);
      }
    }
    else
    {
      return (unsigned int)IsDebuggerPresent() + 3;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18034fb78  mov     rax, rsp
0x18034fb7b  mov     [rax+8], rbx
0x18034fb7f  mov     [rax+10h], rbp
0x18034fb83  mov     [rax+18h], rsi
0x18034fb87  mov     [rax+20h], rdi
0x18034fb8b  push    r14
0x18034fb8d  sub     rsp, 50h
0x18034fb91  mov     esi, r8d
0x18034fb94  mov     r14, rdx
0x18034fb97  mov     rbx, rcx
0x18034fb9a  call    __acrt_is_packaged_app
0x18034fb9f  mov     bpl, al
0x18034fba2  call    cs:__imp_IsDebuggerPresent
0x18034fba8  xor     edi, edi
0x18034fbaa  test    eax, eax
0x18034fbac  jz      short loc_18034FBCB
0x18034fbae  test    rbx, rbx
0x18034fbb1  jz      short loc_18034FBBC
0x18034fbb3  mov     rcx, rbx; lpOutputString
0x18034fbb6  call    cs:__imp_OutputDebugStringW
0x18034fbbc  test    bpl, bpl
0x18034fbbf  jz      short loc_18034FBCB
0x18034fbc1  mov     edi, 4
0x18034fbc6  jmp     loc_18034FC74
0x18034fbcb  call    __acrt_can_show_message_box
0x18034fbd0  test    al, al
0x18034fbd2  jnz     short loc_18034FBE8
0x18034fbd4  call    cs:__imp_IsDebuggerPresent
0x18034fbda  neg     eax
0x18034fbdc  sbb     edi, edi
0x18034fbde  neg     edi
0x18034fbe0  add     edi, 3
0x18034fbe3  jmp     loc_18034FC74
0x18034fbe8  test    bpl, bpl
0x18034fbeb  jz      short loc_18034FC4B
0x18034fbed  mov     [rsp+58h+lpThreadId], rdi; lpThreadId
0x18034fbf2  lea     r9, [rsp+58h+Parameter]; lpParameter
0x18034fbf7  lea     r8, message_box_wait_thread_wchar_t_; lpStartAddress
0x18034fbfe  mov     [rsp+58h+dwCreationFlags], edi; dwCreationFlags
0x18034fc02  xor     edx, edx; dwStackSize
0x18034fc04  mov     [rsp+58h+Parameter], r14
0x18034fc09  xor     ecx, ecx; lpThreadAttributes
0x18034fc0b  mov     [rsp+58h+var_20], rbx
0x18034fc10  mov     [rsp+58h+var_18], esi
0x18034fc14  mov     [rsp+58h+var_14], edi
0x18034fc18  call    cs:__imp_CreateThread
0x18034fc1e  mov     rbx, rax
0x18034fc21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18034fc25  jz      short loc_18034FC74
0x18034fc27  xor     r8d, r8d; bAlertable
0x18034fc2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18034fc2d  mov     rcx, rax; hHandle
0x18034fc30  call    cs:__imp_WaitForSingleObjectEx
0x18034fc36  mov     rcx, rbx; hObject
0x18034fc39  test    eax, eax
0x18034fc3b  jz      short loc_18034FC45
0x18034fc3d  call    cs:__imp_CloseHandle
0x18034fc43  jmp     short loc_18034FC74
0x18034fc45  mov     edi, [rsp+58h+var_14]
0x18034fc49  jmp     short loc_18034FC3D
0x18034fc4b  call    __acrt_is_interactive
0x18034fc50  test    al, al
0x18034fc52  jnz     short loc_18034FC5C
0x18034fc54  bts     esi, 15h
0x18034fc58  xor     ecx, ecx
0x18034fc5a  jmp     short loc_18034FC64
0x18034fc5c  call    __acrt_get_parent_window
0x18034fc61  mov     rcx, rax
0x18034fc64  mov     r9d, esi
0x18034fc67  mov     r8, r14
0x18034fc6a  mov     rdx, rbx
0x18034fc6d  call    __acrt_MessageBoxW
0x18034fc72  mov     edi, eax
0x18034fc74  mov     rbx, [rsp+58h+arg_0]
0x18034fc79  mov     eax, edi
0x18034fc7b  mov     rdi, [rsp+58h+arg_18]
0x18034fc80  mov     rbp, [rsp+58h+arg_8]
0x18034fc85  mov     rsi, [rsp+58h+arg_10]
0x18034fc8a  add     rsp, 50h
0x18034fc8e  pop     r14
0x18034fc90  retn
```

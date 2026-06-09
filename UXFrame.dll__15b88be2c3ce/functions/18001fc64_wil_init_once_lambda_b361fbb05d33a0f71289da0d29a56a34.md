# wil::init_once__lambda_b361fbb05d33a0f71289da0d29a56a34___

- ea: `0x18001fc64`
- end: `0x18001fceb`
- name: `wil::init_once__lambda_b361fbb05d33a0f71289da0d29a56a34___`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800283e0`

## callees

- `0x180002b20`
- `0x180017008`
- `0x18001fc64`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001fc95`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001fc95`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001fcb5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001fcb5`

## string_xrefs

- `0x18001fcd9`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
char __fastcall wil::init_once__lambda_b361fbb05d33a0f71289da0d29a56a34___(__int64 a1, _BYTE *a2)
{
  const char *v3; // r9
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\win32_helpers.h",
      v3);
  if ( !fPending )
    return 0;
  *a2 = 1;
  InitOnceComplete(&InitOnce, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18001fc64  push    rbx
0x18001fc66  sub     rsp, 30h
0x18001fc6a  mov     rax, cs:__security_cookie
0x18001fc71  xor     rax, rsp
0x18001fc74  mov     [rsp+38h+var_10], rax
0x18001fc79  mov     rbx, rdx
0x18001fc7c  mov     [rsp+38h+fPending], 0
0x18001fc84  xor     edx, edx; dwFlags
0x18001fc86  lea     r8, [rsp+38h+fPending]; fPending
0x18001fc8b  xor     r9d, r9d; lpContext
0x18001fc8e  lea     rcx, InitOnce; lpInitOnce
0x18001fc95  call    cs:__imp___std_init_once_begin_initialize
0x18001fc9b  test    eax, eax
0x18001fc9d  jz      short loc_18001FCD4
0x18001fc9f  cmp     [rsp+38h+fPending], 0
0x18001fca4  jz      short loc_18001FCBF
0x18001fca6  xor     r8d, r8d; lpContext
0x18001fca9  mov     byte ptr [rbx], 1
0x18001fcac  xor     edx, edx; dwFlags
0x18001fcae  lea     rcx, InitOnce; lpInitOnce
0x18001fcb5  call    cs:__imp_InitOnceComplete
0x18001fcbb  mov     al, 1
0x18001fcbd  jmp     short loc_18001FCC1
0x18001fcbf  xor     al, al
0x18001fcc1  mov     rcx, [rsp+38h+var_10]
0x18001fcc6  xor     rcx, rsp; StackCookie
0x18001fcc9  call    __security_check_cookie
0x18001fcce  add     rsp, 30h
0x18001fcd2  pop     rbx
0x18001fcd3  retn
0x18001fcd4  mov     rcx, [rsp+38h]; this
0x18001fcd9  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18001fce0  mov     edx, 3BCh; void *
0x18001fce5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

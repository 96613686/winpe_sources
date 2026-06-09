# wil::init_once__lambda_019472cbb20ec0888b6e44961382cbad___

- ea: `0x18000ac48`
- end: `0x18000acdb`
- name: `wil::init_once__lambda_019472cbb20ec0888b6e44961382cbad___`
- size: `147`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002da60`
- `0x18002dfe0`
- `0x18004488c`

## callees

- `0x180002b20`
- `0x18000ac48`
- `0x18000ee1c`
- `0x180017008`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ac79`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ac79`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000acaa`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000acaa`

## string_xrefs

- `0x18000acc9`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char wil::init_once__lambda_019472cbb20ec0888b6e44961382cbad___()
{
  const char *v0; // r9
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&ThreadManager::s_instanceInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\win32_helpers.h",
      v0);
  if ( !fPending )
    return 0;
  lambda_019472cbb20ec0888b6e44961382cbad_::operator()(retaddr);
  InitOnceComplete(&ThreadManager::s_instanceInitOnce, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18000ac48  push    rbx
0x18000ac4a  sub     rsp, 40h
0x18000ac4e  mov     rax, cs:__security_cookie
0x18000ac55  xor     rax, rsp
0x18000ac58  mov     [rsp+48h+var_10], rax
0x18000ac5d  mov     [rsp+48h+fPending], 0
0x18000ac65  xor     r9d, r9d; lpContext
0x18000ac68  lea     r8, [rsp+48h+fPending]; fPending
0x18000ac6d  xor     edx, edx; dwFlags
0x18000ac6f  lea     rbx, ?s_instanceInitOnce@ThreadManager@@0T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE ThreadManager::s_instanceInitOnce
0x18000ac76  mov     rcx, rbx; lpInitOnce
0x18000ac79  call    cs:__imp___std_init_once_begin_initialize
0x18000ac7f  mov     rcx, [rsp+48h]; this
0x18000ac84  test    eax, eax
0x18000ac86  jz      short loc_18000ACC9
0x18000ac88  cmp     [rsp+48h+fPending], 0
0x18000ac8d  jz      short loc_18000ACB4
0x18000ac8f  mov     [rsp+48h+var_28], rbx
0x18000ac94  mov     [rsp+48h+var_20], 4
0x18000ac9c  call    _lambda_019472cbb20ec0888b6e44961382cbad___operator__
0x18000aca1  nop
0x18000aca2  xor     r8d, r8d; lpContext
0x18000aca5  xor     edx, edx; dwFlags
0x18000aca7  mov     rcx, rbx; lpInitOnce
0x18000acaa  call    cs:__imp_InitOnceComplete
0x18000acb0  mov     al, 1
0x18000acb2  jmp     short loc_18000ACB6
0x18000acb4  xor     al, al
0x18000acb6  mov     rcx, [rsp+48h+var_10]
0x18000acbb  xor     rcx, rsp; StackCookie
0x18000acbe  call    __security_check_cookie
0x18000acc3  add     rsp, 40h
0x18000acc7  pop     rbx
0x18000acc8  retn
0x18000acc9  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18000acd0  mov     edx, 3BCh; void *
0x18000acd5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

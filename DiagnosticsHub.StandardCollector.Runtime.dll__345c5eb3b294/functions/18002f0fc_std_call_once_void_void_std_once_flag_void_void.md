# std::call_once<void (&)(void),>(std::once_flag &,void (&)(void))

- ea: `0x18002f0fc`
- end: `0x18002f17b`
- name: `??$call_once@A6AXXZ$$V@std@@YAXAEAUonce_flag@0@A6AXXZ@Z`
- size: `127`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d9a4`
- `0x18002da4c`

## callees

- `0x18002d42c`
- `0x18002f0fc`
- `0x180049b50`
- `0x18004ae00`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18002f125`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002f125`
- `KERNEL32!InitOnceComplete` at `0x18002f158`
- `KERNEL32!InitOnceComplete` at `0x18002f158`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002f12f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002f12f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL std::call_once<void (&)(void),>()
{
  BOOL result; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  BOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  result = __std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0);
  if ( !result )
    abort();
  if ( fPending )
  {
    anonymous_namespace_::GetCollectorSid();
    result = InitOnceComplete(&InitOnce, 0, 0);
    if ( !result )
      _std_init_once_link_alternate_names_and_abort(v2, v1);
  }
  return result;
}

```

## disassembly

```asm
0x18002f0fc  push    rbx
0x18002f0fe  sub     rsp, 40h
0x18002f102  mov     rax, cs:__security_cookie
0x18002f109  xor     rax, rsp
0x18002f10c  mov     [rsp+48h+var_10], rax
0x18002f111  xor     r9d, r9d; lpContext
0x18002f114  lea     r8, [rsp+48h+fPending]; fPending
0x18002f119  xor     edx, edx; dwFlags
0x18002f11b  lea     rbx, InitOnce
0x18002f122  mov     rcx, rbx; lpInitOnce
0x18002f125  call    cs:__imp___std_init_once_begin_initialize
0x18002f12b  test    eax, eax
0x18002f12d  jnz     short loc_18002F136
0x18002f12f  call    cs:__imp_abort
0x18002f136  cmp     [rsp+48h+fPending], 0
0x18002f13b  jz      short loc_18002F162
0x18002f13d  mov     [rsp+48h+var_28], rbx
0x18002f142  mov     [rsp+48h+var_20], 4
0x18002f14a  call    _anonymous_namespace___GetCollectorSid
0x18002f14f  nop
0x18002f150  xor     r8d, r8d; lpContext
0x18002f153  xor     edx, edx; dwFlags
0x18002f155  mov     rcx, rbx; lpInitOnce
0x18002f158  call    cs:__imp_InitOnceComplete
0x18002f15e  test    eax, eax
0x18002f160  jz      short loc_18002F175
0x18002f162  mov     rcx, [rsp+48h+var_10]
0x18002f167  xor     rcx, rsp; StackCookie
0x18002f16a  call    __security_check_cookie
0x18002f16f  add     rsp, 40h
0x18002f173  pop     rbx
0x18002f174  retn
0x18002f175  call    __std_init_once_link_alternate_names_and_abort
```

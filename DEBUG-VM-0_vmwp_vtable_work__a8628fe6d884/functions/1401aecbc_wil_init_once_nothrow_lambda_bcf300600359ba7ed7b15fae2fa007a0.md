# wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___

- ea: `0x1401aecbc`
- end: `0x1401aed89`
- name: `wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___`
- size: `205`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400844a8`

## callees

- `0x1400b42b0`
- `0x1400d6a74`
- `0x140132940`
- `0x1401aecbc`
- `0x1401af4e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aed4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aed67`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aed4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aed67`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1401aecea`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1401aecea`

## pseudocode

```c
__int64 wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___()
{
  const char *v0; // r9
  int v2; // eax
  unsigned int v3; // ebx
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  fPending = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v0);
  if ( fPending )
  {
    v2 = lambda_bcf300600359ba7ed7b15fae2fa007a0_::operator()();
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"wil",
        (const char *)(unsigned int)v2,
        fPending);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v3;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1401aecbc  push    rbx
0x1401aecbe  sub     rsp, 30h
0x1401aecc2  mov     rax, cs:__security_cookie
0x1401aecc9  xor     rax, rsp
0x1401aeccc  mov     [rsp+38h+var_10], rax
0x1401aecd1  mov     [rsp+38h+fPending], 0; int
0x1401aecd9  xor     r9d, r9d; lpContext
0x1401aecdc  lea     r8, [rsp+38h+fPending]; fPending
0x1401aece1  xor     edx, edx; dwFlags
0x1401aece3  lea     rcx, InitOnce; lpInitOnce
0x1401aecea  call    cs:__imp_InitOnceBeginInitialize
0x1401aecf1  nop     dword ptr [rax+rax+00h]
0x1401aecf6  test    eax, eax
0x1401aecf8  jnz     short loc_1401AED12
0x1401aecfa  mov     rcx, [rsp+38h]; this
0x1401aecff  lea     r8, aWil; "wil"
0x1401aed06  mov     edx, 37Ah; void *
0x1401aed0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1401aed10  jmp     short loc_1401AED75
0x1401aed12  cmp     [rsp+38h+fPending], 0
0x1401aed17  jz      short loc_1401AED73
0x1401aed19  call    _lambda_bcf300600359ba7ed7b15fae2fa007a0___operator__
0x1401aed1e  mov     ebx, eax
0x1401aed20  test    eax, eax
0x1401aed22  jns     short loc_1401AED5B
0x1401aed24  mov     rcx, [rsp+38h]; this
0x1401aed29  mov     r9d, eax; char *
0x1401aed2c  lea     r8, aWil; "wil"
0x1401aed33  mov     edx, 37Fh; void *
0x1401aed38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aed3d  xor     r8d, r8d; lpContext
0x1401aed40  lea     edx, [r8+4]; dwFlags
0x1401aed44  lea     rcx, InitOnce; lpInitOnce
0x1401aed4b  call    cs:__imp_InitOnceComplete
0x1401aed52  nop     dword ptr [rax+rax+00h]
0x1401aed57  mov     eax, ebx
0x1401aed59  jmp     short loc_1401AED75
0x1401aed5b  xor     r8d, r8d; lpContext
0x1401aed5e  xor     edx, edx; dwFlags
0x1401aed60  lea     rcx, InitOnce; lpInitOnce
0x1401aed67  call    cs:__imp_InitOnceComplete
0x1401aed6e  nop     dword ptr [rax+rax+00h]
0x1401aed73  xor     eax, eax
0x1401aed75  mov     rcx, [rsp+38h+var_10]
0x1401aed7a  xor     rcx, rsp; StackCookie
0x1401aed7d  call    __security_check_cookie
0x1401aed82  add     rsp, 30h
0x1401aed86  pop     rbx
0x1401aed87  retn
```

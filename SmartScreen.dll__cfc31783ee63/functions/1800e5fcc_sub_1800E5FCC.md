# sub_1800E5FCC

- ea: `0x1800e5fcc`
- end: `0x1800e6066`
- name: `sub_1800E5FCC`
- size: `154`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800d17f0`
- `0x1800d6280`
- `0x1800e8eb0`
- `0x1800eae88`
- `0x1800ebe30`
- `0x1800ed9bc`

## callees

- `0x1800e5fcc`
- `0x1800f13b0`
- `0x1800f4270`
- `0x1800fee84`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e600c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e600c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e602b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e602b`

## pseudocode

```c
void __fastcall sub_1800E5FCC(__int64 a1, int a2)
{
  union _RTL_RUN_ONCE *v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF

  if ( a2 == 3 || !a2 )
  {
    *(_DWORD *)(a1 + 648) = a2;
  }
  else
  {
    v4 = (union _RTL_RUN_ONCE *)(a1 + 640);
    if ( !InitOnceBeginInitialize((LPINIT_ONCE)(a1 + 640), 0, &fPending, 0) )
      sub_1800FEE84(v5);
    if ( fPending )
    {
      *(_DWORD *)(a1 + 648) = a2;
      if ( !InitOnceComplete(v4, 0, 0) )
        sub_1800F13B0(v7, v6);
    }
  }
}

```

## disassembly

```asm
0x1800e5fcc  mov     [rsp+arg_8], rbx
0x1800e5fd1  mov     [rsp+arg_10], rsi
0x1800e5fd6  push    rdi
0x1800e5fd7  sub     rsp, 30h
0x1800e5fdb  mov     rax, cs:__security_cookie
0x1800e5fe2  xor     rax, rsp
0x1800e5fe5  mov     [rsp+38h+var_10], rax
0x1800e5fea  mov     ebx, edx
0x1800e5fec  mov     rdi, rcx
0x1800e5fef  cmp     edx, 3
0x1800e5ff2  jz      short loc_1800E6037
0x1800e5ff4  test    edx, edx
0x1800e5ff6  jz      short loc_1800E6037
0x1800e5ff8  lea     rsi, [rcx+280h]
0x1800e5fff  xor     r9d, r9d; lpContext
0x1800e6002  mov     rcx, rsi; lpInitOnce
0x1800e6005  lea     r8, [rsp+38h+fPending]; fPending
0x1800e600a  xor     edx, edx; dwFlags
0x1800e600c  call    cs:InitOnceBeginInitialize
0x1800e6012  test    eax, eax
0x1800e6014  jz      short loc_1800E605A
0x1800e6016  cmp     [rsp+38h+fPending], 0
0x1800e601b  jz      short loc_1800E603D
0x1800e601d  xor     r8d, r8d; lpContext
0x1800e6020  mov     [rdi+288h], ebx
0x1800e6026  xor     edx, edx; dwFlags
0x1800e6028  mov     rcx, rsi; lpInitOnce
0x1800e602b  call    cs:InitOnceComplete
0x1800e6031  test    eax, eax
0x1800e6033  jz      short loc_1800E6060
0x1800e6035  jmp     short loc_1800E603D
0x1800e6037  mov     [rcx+288h], ebx
0x1800e603d  mov     rcx, [rsp+38h+var_10]
0x1800e6042  xor     rcx, rsp; StackCookie
0x1800e6045  call    __security_check_cookie
0x1800e604a  mov     rbx, [rsp+38h+arg_8]
0x1800e604f  mov     rsi, [rsp+38h+arg_10]
0x1800e6054  add     rsp, 30h
0x1800e6058  pop     rdi
0x1800e6059  retn
0x1800e605a  call    sub_1800FEE84
0x1800e6060  call    sub_1800F13B0
```

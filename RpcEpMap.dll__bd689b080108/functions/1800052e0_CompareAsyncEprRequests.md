# CompareAsyncEprRequests

- ea: `0x1800052e0`
- end: `0x18000536a`
- name: `CompareAsyncEprRequests`
- size: `138`
- prototype: `_BOOL8 __fastcall(_QWORD *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800052e0`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x180005323`
- `RPCRT4!UuidIsNil` at `0x180005345`
- `RPCRT4!UuidIsNil` at `0x180005323`
- `RPCRT4!UuidIsNil` at `0x180005345`

## pseudocode

```c
_BOOL8 __fastcall CompareAsyncEprRequests(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rcx
  RPC_STATUS Status; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1 - *(_QWORD *)a2;
  if ( *a1 == *(_QWORD *)a2 )
    v3 = a1[1] - *(_QWORD *)(a2 + 8);
  if ( v3 )
    return 0;
  v5 = a1 + 2;
  Status = 0;
  if ( UuidIsNil((UUID *)a1 + 1, &Status) )
    return 1;
  Status = 0;
  if ( UuidIsNil((UUID *)(a2 + 16), &Status) )
    return 1;
  v6 = *v5 - *(_QWORD *)(a2 + 16);
  if ( *v5 == *(_QWORD *)(a2 + 16) )
    v6 = v5[1] - *(_QWORD *)(a2 + 24);
  return v6 == 0;
}

```

## disassembly

```asm
0x1800052e0  mov     [rsp+arg_8], rbx
0x1800052e5  push    rdi
0x1800052e6  sub     rsp, 20h
0x1800052ea  mov     rax, [rcx]
0x1800052ed  mov     rbx, rdx
0x1800052f0  sub     rax, [rdx]
0x1800052f3  jnz     short loc_1800052FD
0x1800052f5  mov     rax, [rcx+8]
0x1800052f9  sub     rax, [rdx+8]
0x1800052fd  test    rax, rax
0x180005300  jz      short loc_18000530F
0x180005302  xor     eax, eax
0x180005304  mov     rbx, [rsp+28h+arg_8]
0x180005309  add     rsp, 20h
0x18000530d  pop     rdi
0x18000530e  retn
0x18000530f  lea     rdi, [rcx+10h]
0x180005313  mov     [rsp+28h+Status], 0
0x18000531b  mov     rcx, rdi; Uuid
0x18000531e  lea     rdx, [rsp+28h+Status]; Status
0x180005323  call    cs:__imp_UuidIsNil
0x180005329  test    eax, eax
0x18000532b  jz      short loc_180005334
0x18000532d  mov     eax, 1
0x180005332  jmp     short loc_180005304
0x180005334  lea     rdx, [rsp+28h+Status]; Status
0x180005339  mov     [rsp+28h+Status], 0
0x180005341  lea     rcx, [rbx+10h]; Uuid
0x180005345  call    cs:__imp_UuidIsNil
0x18000534b  test    eax, eax
0x18000534d  jnz     short loc_18000532D
0x18000534f  mov     rcx, [rdi]
0x180005352  sub     rcx, [rbx+10h]
0x180005356  jnz     short loc_180005360
0x180005358  mov     rcx, [rdi+8]
0x18000535c  sub     rcx, [rbx+18h]
0x180005360  xor     eax, eax
0x180005362  test    rcx, rcx
0x180005365  setz    al
0x180005368  jmp     short loc_180005304
```

# wil::ResultFromCaughtException(void)

- ea: `0x18000ea84`
- end: `0x18000eac4`
- name: `?ResultFromCaughtException@wil@@YAJXZ`
- size: `64`
- prototype: `__int64 __fastcall(wil *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180012311`
- `0x180012348`
- `0x1800123c7`
- `0x18001240f`
- `0x180012457`
- `0x1800124b1`
- `0x18001251d`
- `0x180012577`

## callees

- `0x18000ea84`
- `0x18000ef68`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall wil::ResultFromCaughtException(wil *this, unsigned int a2, __int64 a3, int a4)
{
  __int64 result; // rax
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF
  char v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = 0;
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (result = *(unsigned int *)g_pfnResultFromCaughtExceptionInternal(v5, 0, 0, &v6), (int)result >= 0) )
  {
    wil::details::in1diag3::_FailFast_Hr(this, a2, (const char *)0x8007023ELL, a4);
  }
  return result;
}

```

## disassembly

```asm
0x18000ea84  sub     rsp, 48h
0x18000ea88  mov     [rsp+48h+arg_0], 0
0x18000ea8d  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000ea94  test    rax, rax
0x18000ea97  jz      short loc_18000EAB8
0x18000ea99  lea     r9, [rsp+48h+arg_0]
0x18000ea9e  xor     r8d, r8d
0x18000eaa1  xor     edx, edx
0x18000eaa3  lea     rcx, [rsp+48h+var_18]
0x18000eaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaad  mov     eax, [rax]
0x18000eaaf  test    eax, eax
0x18000eab1  jns     short loc_18000EAB8
0x18000eab3  add     rsp, 48h
0x18000eab7  retn
0x18000eab8  mov     r8d, 8007023Eh; char *
0x18000eabe  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(uint,char const *,long)
```

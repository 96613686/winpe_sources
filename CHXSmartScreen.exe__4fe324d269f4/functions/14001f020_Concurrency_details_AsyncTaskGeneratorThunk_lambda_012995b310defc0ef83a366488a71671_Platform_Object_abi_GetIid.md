# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_GetIids

- ea: `0x14001f020`
- end: `0x14001f08c`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_GetIids`
- size: `108`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14001f0a0`
- `0x14001f0b0`
- `0x14001f0c0`
- `0x14001f0d0`
- `0x14001f0e0`
- `0x14001f0f0`
- `0x14001f100`
- `0x14001f110`
- `0x14001f120`
- `0x14001f140`

## callees

- `0x140002844`
- `0x140031960`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_Platform::Object_::__abi_GetIids(
        __int64 a1,
        int a2,
        const struct __s_GUID *a3)
{
  __int64 v4; // [rsp+20h] [rbp-30h] BYREF
  int v5; // [rsp+28h] [rbp-28h]
  int v6; // [rsp+2Ch] [rbp-24h]
  __int64 v7; // [rsp+30h] [rbp-20h]
  int v8; // [rsp+38h] [rbp-18h]
  int v9; // [rsp+3Ch] [rbp-14h]

  v5 = 1693275798;
  v6 = -442324011;
  v7 = 56;
  v8 = 192;
  v9 = 1174405120;
  return __winRT::__getIids((__winRT *)2, a2, (unsigned int *)&v4, a3, (struct Platform::Guid **)0x3CE1F94B41AE1ED7LL);
}

```

## disassembly

```asm
0x14001f020  push    rbp
0x14001f022  mov     rbp, rsp
0x14001f025  sub     rsp, 50h
0x14001f029  mov     rax, cs:__security_cookie
0x14001f030  xor     rax, rsp
0x14001f033  mov     [rbp+var_10], rax
0x14001f037  mov     r9, r8; struct __s_GUID *
0x14001f03a  mov     dword ptr [rbp+var_30], 41AE1ED7h
0x14001f041  lea     r8, [rbp+var_30]; unsigned int *
0x14001f045  mov     dword ptr [rbp+var_30+4], 3CE1F94Bh
0x14001f04c  mov     ecx, 2; this
0x14001f051  mov     [rbp+var_28], 64ED5696h
0x14001f058  mov     [rbp+var_24], 0E5A2ABD5h
0x14001f05f  mov     [rbp+var_20], 38h ; '8'
0x14001f067  mov     [rbp+var_18], 0C0h
0x14001f06e  mov     [rbp+var_14], 46000000h
0x14001f075  call    ?__getIids@__winRT@@YAJHPEAKPEBU__s_GUID@@PEAPEAVGuid@Platform@@@Z; __winRT::__getIids(int,ulong *,__s_GUID const *,Platform::Guid * *)
0x14001f07a  mov     rcx, [rbp+var_10]
0x14001f07e  xor     rcx, rsp; StackCookie
0x14001f081  call    __security_check_cookie
0x14001f086  add     rsp, 50h
0x14001f08a  pop     rbp
0x14001f08b  retn
```

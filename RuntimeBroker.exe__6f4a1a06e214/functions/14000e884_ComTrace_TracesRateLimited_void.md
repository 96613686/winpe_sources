# ComTrace::TracesRateLimited_(void)

- ea: `0x14000e884`
- end: `0x14000e8dc`
- name: `?TracesRateLimited_@ComTrace@@QEAAXXZ`
- size: `88`
- prototype: `void __fastcall(ComTrace *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e7cc`

## callees

- `0x140001898`
- `0x140008c80`
- `0x14000e06c`
- `0x14000e884`

## pseudocode

```c
void __fastcall ComTrace::TracesRateLimited_(ComTrace *this)
{
  const struct _tlgProvider_t *v1; // rax
  _BYTE v2[32]; // [rsp+30h] [rbp-38h] BYREF

  v1 = ComTrace::Provider((__int64)this);
  if ( *(_DWORD *)v1 > 2u )
    tlgWriteTransfer_EtwEventWriteTransfer((__int64)v1, (unsigned __int8 *)byte_14001472B, 0, 0, 2, (__int64)v2);
}

```

## disassembly

```asm
0x14000e884  sub     rsp, 68h
0x14000e888  mov     rax, cs:__security_cookie
0x14000e88f  xor     rax, rsp
0x14000e892  mov     [rsp+68h+var_18], rax
0x14000e897  call    ?Provider@ComTrace@@SAPEBU_tlgProvider_t@@XZ; ComTrace::Provider(void)
0x14000e89c  mov     ecx, [rax]
0x14000e89e  cmp     ecx, 2
0x14000e8a1  jbe     short loc_14000E8CA
0x14000e8a3  lea     rcx, [rsp+68h+var_38]
0x14000e8a8  xor     r9d, r9d
0x14000e8ab  mov     [rsp+68h+var_40], rcx
0x14000e8b0  lea     rdx, byte_14001472B
0x14000e8b7  mov     rcx, rax
0x14000e8ba  mov     [rsp+68h+var_48], 2
0x14000e8c2  xor     r8d, r8d
0x14000e8c5  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x14000e8ca  mov     rcx, [rsp+68h+var_18]
0x14000e8cf  xor     rcx, rsp; StackCookie
0x14000e8d2  call    __security_check_cookie
0x14000e8d7  add     rsp, 68h
0x14000e8db  retn
```

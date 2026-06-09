# __security_init_cookie_ex

- ea: `0x180007af4`
- end: `0x180007b52`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007aa8`

## callees

- `0x180007af4`

## pseudocode

```c
unsigned __int64 *__fastcall _security_init_cookie_ex(unsigned __int64 *a1)
{
  unsigned __int64 v1; // rax
  unsigned __int64 *result; // rax

  v1 = __rdtsc();
  *a1 = ((unsigned __int64)a1 ^ ((((unsigned __int64)HIDWORD(v1) << 32) | (unsigned int)v1) >> 4)) & 0xFFFFFFFFFFFFLL;
  if ( !*a1 || (result = a1, *a1 == 0x2B992DDFA232LL) )
  {
    result = a1;
    *a1 = 0x2B992DDFA233LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007af4  mov     [rsp+arg_0], rcx
0x180007af9  rdtsc
0x180007afb  shl     rdx, 20h
0x180007aff  or      rax, rdx
0x180007b02  shr     rax, 4
0x180007b06  xor     rax, [rsp+arg_0]
0x180007b0b  mov     rcx, 0FFFFFFFFFFFFh
0x180007b15  and     rax, rcx
0x180007b18  mov     rcx, [rsp+arg_0]
0x180007b1d  mov     [rcx], rax
0x180007b20  mov     rax, [rsp+arg_0]
0x180007b25  cmp     qword ptr [rax], 0
0x180007b29  jz      short loc_180007B3F
0x180007b2b  mov     rax, [rsp+arg_0]
0x180007b30  mov     rcx, 2B992DDFA232h
0x180007b3a  cmp     [rax], rcx
0x180007b3d  jnz     short locret_180007B51
0x180007b3f  mov     rax, [rsp+arg_0]
0x180007b44  mov     rcx, 2B992DDFA233h
0x180007b4e  mov     [rax], rcx
0x180007b51  retn
```

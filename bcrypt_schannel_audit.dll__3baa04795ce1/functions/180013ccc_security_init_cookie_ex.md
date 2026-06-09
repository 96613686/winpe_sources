# __security_init_cookie_ex

- ea: `0x180013ccc`
- end: `0x180013d2a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013c80`

## callees

- `0x180013ccc`

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
0x180013ccc  mov     [rsp+arg_0], rcx
0x180013cd1  rdtsc
0x180013cd3  shl     rdx, 20h
0x180013cd7  or      rax, rdx
0x180013cda  shr     rax, 4
0x180013cde  xor     rax, [rsp+arg_0]
0x180013ce3  mov     rcx, 0FFFFFFFFFFFFh
0x180013ced  and     rax, rcx
0x180013cf0  mov     rcx, [rsp+arg_0]
0x180013cf5  mov     [rcx], rax
0x180013cf8  mov     rax, [rsp+arg_0]
0x180013cfd  cmp     qword ptr [rax], 0
0x180013d01  jz      short loc_180013D17
0x180013d03  mov     rax, [rsp+arg_0]
0x180013d08  mov     rcx, 2B992DDFA232h
0x180013d12  cmp     [rax], rcx
0x180013d15  jnz     short locret_180013D29
0x180013d17  mov     rax, [rsp+arg_0]
0x180013d1c  mov     rcx, 2B992DDFA233h
0x180013d26  mov     [rax], rcx
0x180013d29  retn
```

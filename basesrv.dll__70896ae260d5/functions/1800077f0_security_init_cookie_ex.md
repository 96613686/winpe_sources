# __security_init_cookie_ex

- ea: `0x1800077f0`
- end: `0x18000784e`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800077a4`

## callees

- `0x1800077f0`

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
0x1800077f0  mov     [rsp+arg_0], rcx
0x1800077f5  rdtsc
0x1800077f7  shl     rdx, 20h
0x1800077fb  or      rax, rdx
0x1800077fe  shr     rax, 4
0x180007802  xor     rax, [rsp+arg_0]
0x180007807  mov     rcx, 0FFFFFFFFFFFFh
0x180007811  and     rax, rcx
0x180007814  mov     rcx, [rsp+arg_0]
0x180007819  mov     [rcx], rax
0x18000781c  mov     rax, [rsp+arg_0]
0x180007821  cmp     qword ptr [rax], 0
0x180007825  jz      short loc_18000783B
0x180007827  mov     rax, [rsp+arg_0]
0x18000782c  mov     rcx, 2B992DDFA232h
0x180007836  cmp     [rax], rcx
0x180007839  jnz     short locret_18000784D
0x18000783b  mov     rax, [rsp+arg_0]
0x180007840  mov     rcx, 2B992DDFA233h
0x18000784a  mov     [rax], rcx
0x18000784d  retn
```

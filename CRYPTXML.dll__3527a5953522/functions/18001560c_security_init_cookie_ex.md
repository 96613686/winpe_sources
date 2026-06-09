# __security_init_cookie_ex

- ea: `0x18001560c`
- end: `0x18001566a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800155c0`

## callees

- `0x18001560c`

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
0x18001560c  mov     [rsp+arg_0], rcx
0x180015611  rdtsc
0x180015613  shl     rdx, 20h
0x180015617  or      rax, rdx
0x18001561a  shr     rax, 4
0x18001561e  xor     rax, [rsp+arg_0]
0x180015623  mov     rcx, 0FFFFFFFFFFFFh
0x18001562d  and     rax, rcx
0x180015630  mov     rcx, [rsp+arg_0]
0x180015635  mov     [rcx], rax
0x180015638  mov     rax, [rsp+arg_0]
0x18001563d  cmp     qword ptr [rax], 0
0x180015641  jz      short loc_180015657
0x180015643  mov     rax, [rsp+arg_0]
0x180015648  mov     rcx, 2B992DDFA232h
0x180015652  cmp     [rax], rcx
0x180015655  jnz     short locret_180015669
0x180015657  mov     rax, [rsp+arg_0]
0x18001565c  mov     rcx, 2B992DDFA233h
0x180015666  mov     [rax], rcx
0x180015669  retn
```

# __security_init_cookie_ex

- ea: `0x14000166c`
- end: `0x1400016ca`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001620`

## callees

- `0x14000166c`

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
0x14000166c  mov     [rsp+arg_0], rcx
0x140001671  rdtsc
0x140001673  shl     rdx, 20h
0x140001677  or      rax, rdx
0x14000167a  shr     rax, 4
0x14000167e  xor     rax, [rsp+arg_0]
0x140001683  mov     rcx, 0FFFFFFFFFFFFh
0x14000168d  and     rax, rcx
0x140001690  mov     rcx, [rsp+arg_0]
0x140001695  mov     [rcx], rax
0x140001698  mov     rax, [rsp+arg_0]
0x14000169d  cmp     qword ptr [rax], 0
0x1400016a1  jz      short loc_1400016B7
0x1400016a3  mov     rax, [rsp+arg_0]
0x1400016a8  mov     rcx, 2B992DDFA232h
0x1400016b2  cmp     [rax], rcx
0x1400016b5  jnz     short locret_1400016C9
0x1400016b7  mov     rax, [rsp+arg_0]
0x1400016bc  mov     rcx, 2B992DDFA233h
0x1400016c6  mov     [rax], rcx
0x1400016c9  retn
```

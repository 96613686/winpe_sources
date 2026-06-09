# PszAllocW

- ea: `0x18000ff30`
- end: `0x18000ff72`
- name: `PszAllocW`
- size: `66`
- prototype: `void *__fastcall(unsigned int, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001150`
- `0x180003dc0`
- `0x18000ab80`
- `0x18000ffa0`

## callees

- `0x180001740`
- `0x18000ff30`
- `0x180012988`

## pseudocode

```c
void *__fastcall PszAllocW(unsigned int a1, __int64 a2)
{
  __int64 v2; // rbx
  unsigned int v4; // [rsp+40h] [rbp+8h] BYREF
  void *v5; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v5 = 0;
  if ( a1 )
  {
    v4 = 0;
    if ( (int)SafeScaleSumD2(&v4, a2, a1) >= 0 )
    {
      HrAlloc(&v5, v4);
      return v5;
    }
  }
  return (void *)v2;
}

```

## disassembly

```asm
0x18000ff30  push    rbx
0x18000ff32  sub     rsp, 30h
0x18000ff36  xor     ebx, ebx
0x18000ff38  mov     [rsp+38h+arg_8], rbx
0x18000ff3d  test    ecx, ecx
0x18000ff3f  jz      short loc_18000FF69
0x18000ff41  mov     r8d, ecx
0x18000ff44  mov     [rsp+38h+arg_0], ebx
0x18000ff48  lea     rcx, [rsp+38h+arg_0]
0x18000ff4d  call    SafeScaleSumD2
0x18000ff52  test    eax, eax
0x18000ff54  js      short loc_18000FF69
0x18000ff56  mov     edx, [rsp+38h+arg_0]; unsigned int
0x18000ff5a  lea     rcx, [rsp+38h+arg_8]; void **
0x18000ff5f  call    ?HrAlloc@@YAJPEAPEAXK@Z; HrAlloc(void * *,ulong)
0x18000ff64  mov     rbx, [rsp+38h+arg_8]
0x18000ff69  mov     rax, rbx
0x18000ff6c  add     rsp, 30h
0x18000ff70  pop     rbx
0x18000ff71  retn
```

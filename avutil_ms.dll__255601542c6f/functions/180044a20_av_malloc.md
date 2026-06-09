# av_malloc

- ea: `0x180044a20`
- end: `0x180044a64`
- name: `av_malloc`
- size: `68`
- prototype: `void *__fastcall(size_t)`
- caller_count: `47`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cf40`
- `0x18002d020`
- `0x18002ebe0`
- `0x1800368a0`
- `0x180036c70`
- `0x180037300`
- `0x18003a890`
- `0x18003afb0`
- `0x18003d990`
- `0x180040350`
- `0x180044a20`
- `0x180044a70`
- `0x180044aa0`
- `0x180044cc0`
- `0x180044fcc`
- `0x180046350`
- `0x1800475f0`
- `0x180049074`
- `0x180049a10`
- `0x18004a380`
- `0x18004ded0`
- `0x18004f6e0`
- `0x180054394`
- `0x180054690`
- `0x180054810`
- `0x1800549bc`
- `0x180054c7c`
- `0x180058780`
- `0x180058960`
- `0x180058cf0`
- `0x180059680`
- `0x180059d60`
- `0x18005f6e0`
- `0x180063a40`
- `0x180063c00`
- `0x180063f60`
- `0x1800648f0`
- `0x180064fc0`
- `0x18006a6f0`
- `0x18006ed60`
- `0x18006ef00`
- `0x18006f390`
- `0x18006fdc0`
- `0x180070530`
- `0x180075f90`
- `0x180078390`
- `0x180078480`

## callees

- `0x180044a20`
- `0x180078dba`

## pseudocode

```c
void *__fastcall av_malloc(size_t a1)
{
  void *result; // rax
  __int64 v3; // rdx
  signed __int32 v4[10]; // [rsp+0h] [rbp-28h] BYREF

  _InterlockedOr(v4, 0);
  if ( a1 > qword_1800A9028 )
    return 0;
  _mm_lfence();
  result = aligned_malloc(a1, 0x40u);
  if ( !result && !a1 )
    return (void *)av_malloc(1, v3);
  return result;
}

```

## disassembly

```asm
0x180044a20  push    rbx
0x180044a22  sub     rsp, 20h
0x180044a26  mov     rbx, rcx
0x180044a29  lock or [rsp+28h+var_28], 0
0x180044a2e  cmp     rcx, cs:qword_1800A9028
0x180044a35  jbe     short loc_180044A3F
0x180044a37  xor     eax, eax
0x180044a39  add     rsp, 20h
0x180044a3d  pop     rbx
0x180044a3e  retn
0x180044a3f  lfence
0x180044a42  mov     edx, 40h ; '@'; Alignment
0x180044a47  call    _aligned_malloc
0x180044a4c  test    rax, rax
0x180044a4f  jnz     short loc_180044A5E
0x180044a51  test    rbx, rbx
0x180044a54  jnz     short loc_180044A5E
0x180044a56  lea     ecx, [rax+1]
0x180044a59  call    av_malloc
0x180044a5e  add     rsp, 20h
0x180044a62  pop     rbx
0x180044a63  retn
```

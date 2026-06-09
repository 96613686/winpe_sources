# AipForEachPlugin

- ea: `0x140036e80`
- end: `0x140036ed8`
- name: `AipForEachPlugin`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002318c`
- `0x1400237dc`
- `0x1400387a4`

## callees

- `0x140006a60`
- `0x140036e80`

## pseudocode

```c
__int64 __fastcall AipForEachPlugin(__int64 (__fastcall *a1)(__int64 *, __int64 *, __int64), __int64 a2)
{
  __int64 i; // rbx
  __int64 result; // rax

  for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
  {
    result = a1(&qword_140009040[9 * i], &qword_1400192B0[i], a2);
    if ( (int)result < 0 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x140036e80  push    rbx
0x140036e82  push    rsi
0x140036e83  push    rdi
0x140036e84  push    r14
0x140036e86  sub     rsp, 28h
0x140036e8a  mov     rdi, rdx
0x140036e8d  lea     r14, cs:140000000h
0x140036e94  mov     rsi, rcx
0x140036e97  xor     ebx, ebx
0x140036e99  cmp     ebx, 4
0x140036e9c  jnb     short loc_140036ECB
0x140036e9e  lea     rax, [rbx+rbx*8]
0x140036ea2  mov     r8, rdi
0x140036ea5  lea     rcx, rva qword_140009040[r14]
0x140036eac  lea     rcx, [rcx+rax*8]
0x140036eb0  mov     rax, rsi
0x140036eb3  lea     rdx, rva qword_1400192B0[r14]
0x140036eba  lea     rdx, [rdx+rbx*8]
0x140036ebe  call    _guard_dispatch_icall
0x140036ec3  test    eax, eax
0x140036ec5  js      short loc_140036ECD
0x140036ec7  inc     ebx
0x140036ec9  jmp     short loc_140036E99
0x140036ecb  xor     eax, eax
0x140036ecd  add     rsp, 28h
0x140036ed1  pop     r14
0x140036ed3  pop     rdi
0x140036ed4  pop     rsi
0x140036ed5  pop     rbx
0x140036ed6  retn
```

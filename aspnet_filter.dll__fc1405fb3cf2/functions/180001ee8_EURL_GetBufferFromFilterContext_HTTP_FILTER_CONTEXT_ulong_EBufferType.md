# EURL::GetBufferFromFilterContext(_HTTP_FILTER_CONTEXT *,ulong,EBufferType)

- ea: `0x180001ee8`
- end: `0x180001fa4`
- name: `?GetBufferFromFilterContext@EURL@@SAPEADPEAU_HTTP_FILTER_CONTEXT@@KW4EBufferType@@@Z`
- size: `188`
- prototype: `void *__fastcall(__int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001ba0`
- `0x18000291c`

## callees

- `0x180001ee8`
- `0x18000318c`
- `0x1800031fc`

## pseudocode

```c
void *__fastcall EURL::GetBufferFromFilterContext(__int64 a1, unsigned int a2, int a3)
{
  _DWORD *v3; // rbx
  unsigned __int64 v5; // rbp
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  __int64 v9; // r14
  void *v10; // rsi
  void *v11; // rax

  v3 = *(_DWORD **)(a1 + 24);
  v5 = a2;
  if ( !v3 )
  {
    v7 = MemAlloc(0x20u);
    v3 = v7;
    if ( !v7 )
      return 0;
    *(_QWORD *)v7 = 0;
    v7[2] = 0;
    *((_QWORD *)v7 + 2) = 0;
    v7[6] = 0;
    *(_QWORD *)(a1 + 24) = v7;
  }
  if ( !a3 )
  {
    v8 = v3;
    v9 = 2;
    goto LABEL_8;
  }
  if ( a3 != 1 )
    return 0;
  v8 = v3 + 4;
  v9 = 6;
LABEL_8:
  if ( v3[v9] < (unsigned int)v5 )
  {
    v10 = *(void **)v8;
    v11 = MemAlloc(v5);
    *(_QWORD *)v8 = v11;
    if ( !v11 )
    {
      *(_QWORD *)v8 = v10;
      return 0;
    }
    v3[v9] = v5;
    if ( v10 )
      MemFree(v10);
  }
  return *(void **)v8;
}

```

## disassembly

```asm
0x180001ee8  mov     rax, rsp
0x180001eeb  mov     [rax+8], rbx
0x180001eef  mov     [rax+10h], rbp
0x180001ef3  mov     [rax+18h], rsi
0x180001ef7  mov     [rax+20h], rdi
0x180001efb  push    r14
0x180001efd  sub     rsp, 20h
0x180001f01  mov     rbx, [rcx+18h]
0x180001f05  mov     edi, r8d
0x180001f08  mov     ebp, edx
0x180001f0a  mov     rsi, rcx
0x180001f0d  test    rbx, rbx
0x180001f10  jnz     short loc_180001F37
0x180001f12  lea     ecx, [rbx+20h]; unsigned __int64
0x180001f15  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180001f1a  mov     rbx, rax
0x180001f1d  test    rax, rax
0x180001f20  jz      short loc_180001F71
0x180001f22  and     qword ptr [rax], 0
0x180001f26  and     dword ptr [rax+8], 0
0x180001f2a  and     qword ptr [rax+10h], 0
0x180001f2f  and     dword ptr [rax+18h], 0
0x180001f33  mov     [rsi+18h], rax
0x180001f37  test    edi, edi
0x180001f39  jnz     short loc_180001F46
0x180001f3b  mov     rdi, rbx
0x180001f3e  mov     r14d, 8
0x180001f44  jmp     short loc_180001F55
0x180001f46  cmp     edi, 1
0x180001f49  jnz     short loc_180001F71
0x180001f4b  lea     rdi, [rbx+10h]
0x180001f4f  mov     r14d, 18h
0x180001f55  cmp     [r14+rbx], ebp
0x180001f59  jnb     short loc_180001F9F
0x180001f5b  mov     rsi, [rdi]
0x180001f5e  mov     rcx, rbp; unsigned __int64
0x180001f61  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180001f66  mov     [rdi], rax
0x180001f69  test    rax, rax
0x180001f6c  jnz     short loc_180001F8E
0x180001f6e  mov     [rdi], rsi
0x180001f71  xor     eax, eax
0x180001f73  mov     rbx, [rsp+28h+arg_0]
0x180001f78  mov     rbp, [rsp+28h+arg_8]
0x180001f7d  mov     rsi, [rsp+28h+arg_10]
0x180001f82  mov     rdi, [rsp+28h+arg_18]
0x180001f87  add     rsp, 20h
0x180001f8b  pop     r14
0x180001f8d  retn
0x180001f8e  mov     [r14+rbx], ebp
0x180001f92  test    rsi, rsi
0x180001f95  jz      short loc_180001F9F
0x180001f97  mov     rcx, rsi; lpMem
0x180001f9a  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180001f9f  mov     rax, [rdi]
0x180001fa2  jmp     short loc_180001F73
```

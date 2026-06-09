# __std_exception_copy

- ea: `0x180009350`
- end: `0x1800093dd`
- name: `__std_exception_copy`
- size: `141`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180008350`
- `0x1800083ac`
- `0x180008408`
- `0x18000a9c0`

## callees

- `0x180009350`
- `0x18000bb08`
- `0x18000bc80`
- `0x18000e820`

## pseudocode

```c
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  char *v5; // rax
  char *v6; // rbx

  if ( *(_BYTE *)(a1 + 8) && *(_QWORD *)a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(*(_QWORD *)a1 + v4) );
    v5 = (char *)malloc(v4 + 1);
    v6 = v5;
    if ( v5 )
    {
      strcpy_s(v5, v4 + 1, *(const char **)a1);
      *(_BYTE *)(a2 + 8) = 1;
      *(_QWORD *)a2 = v6;
      v6 = 0;
    }
    free(v6);
  }
  else
  {
    *(_QWORD *)a2 = *(_QWORD *)a1;
    *(_BYTE *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180009350  mov     [rsp+arg_0], rbx
0x180009355  mov     [rsp+arg_8], rsi
0x18000935a  mov     [rsp+arg_10], rdi
0x18000935f  push    r14
0x180009361  sub     rsp, 20h
0x180009365  cmp     byte ptr [rcx+8], 0
0x180009369  mov     r14, rdx
0x18000936c  mov     rsi, rcx
0x18000936f  jz      short loc_1800093BD
0x180009371  mov     rax, [rcx]
0x180009374  test    rax, rax
0x180009377  jz      short loc_1800093BD
0x180009379  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000937d  inc     rdi
0x180009380  cmp     byte ptr [rax+rdi], 0
0x180009384  jnz     short loc_18000937D
0x180009386  lea     rcx, [rdi+1]; Size
0x18000938a  call    malloc
0x18000938f  mov     rbx, rax
0x180009392  test    rax, rax
0x180009395  jz      short loc_1800093B3
0x180009397  mov     r8, [rsi]; Source
0x18000939a  lea     rdx, [rdi+1]; SizeInBytes
0x18000939e  mov     rcx, rax; Destination
0x1800093a1  call    strcpy_s
0x1800093a6  mov     rax, rbx
0x1800093a9  mov     byte ptr [r14+8], 1
0x1800093ae  mov     [r14], rax
0x1800093b1  xor     ebx, ebx
0x1800093b3  mov     rcx, rbx; Block
0x1800093b6  call    free
0x1800093bb  jmp     short loc_1800093C7
0x1800093bd  mov     rax, [rcx]
0x1800093c0  mov     [rdx], rax
0x1800093c3  mov     byte ptr [rdx+8], 0
0x1800093c7  mov     rbx, [rsp+28h+arg_0]
0x1800093cc  mov     rsi, [rsp+28h+arg_8]
0x1800093d1  mov     rdi, [rsp+28h+arg_10]
0x1800093d6  add     rsp, 20h
0x1800093da  pop     r14
0x1800093dc  retn
```

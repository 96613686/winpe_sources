# GetPointersOfAttributesValues

- ea: `0x1800b1d64`
- end: `0x1800b1e85`
- name: `GetPointersOfAttributesValues`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b2070`

## callees

- `0x1800b1d64`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800b1e06`
- `ntdll!RtlCompareMemory` at `0x1800b1e4b`
- `ntdll!RtlCompareMemory` at `0x1800b1e06`
- `ntdll!RtlCompareMemory` at `0x1800b1e4b`

## pseudocode

```c
void __fastcall GetPointersOfAttributesValues(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 i; // rbp
  __int64 v7; // rsi
  SIZE_T v8; // rbx
  SIZE_T v9; // rbx

  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 || a2 )
  {
    if ( a1 )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); i = (unsigned int)(i + 1) )
      {
        v7 = *(_QWORD *)(a1 + 8);
        if ( *(_DWORD *)(v7 + 40 * i + 24) && *(_QWORD *)(v7 + 40 * i + 32) )
        {
          if ( a3
            && (*(_WORD *)(v7 + 40 * i) & 0xFFFE) == 0x22
            && (v8 = *(unsigned __int16 *)(v7 + 40 * i),
                RtlCompareMemory(*(const void **)(v7 + 40 * i + 8), L"EDP://PolicyFlags", v8) == v8) )
          {
            *a3 = *(_QWORD *)(v7 + 40 * i + 32);
          }
          else if ( a2 && (*(_WORD *)(v7 + 40 * i) & 0xFFFE) == 0x2A )
          {
            v9 = *(unsigned __int16 *)(v7 + 40 * i);
            if ( RtlCompareMemory(*(const void **)(v7 + 40 * i + 8), L"EDP://EvaluationFlags", v9) == v9 )
              *a2 = *(_QWORD *)(v7 + 40 * i + 32);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800b1d64  push    rbx
0x1800b1d66  push    rbp
0x1800b1d67  push    rsi
0x1800b1d68  push    rdi
0x1800b1d69  push    r13
0x1800b1d6b  push    r14
0x1800b1d6d  push    r15
0x1800b1d6f  sub     rsp, 20h
0x1800b1d73  mov     r15, r8
0x1800b1d76  mov     r14, rdx
0x1800b1d79  mov     r13, rcx
0x1800b1d7c  test    r8, r8
0x1800b1d7f  jz      short loc_1800B1D88
0x1800b1d81  mov     qword ptr [r8], 0
0x1800b1d88  test    r14, r14
0x1800b1d8b  jz      short loc_1800B1D94
0x1800b1d8d  mov     qword ptr [rdx], 0
0x1800b1d94  test    r15, r15
0x1800b1d97  jnz     short loc_1800B1DA2
0x1800b1d99  test    r14, r14
0x1800b1d9c  jz      loc_1800B1E75
0x1800b1da2  test    r13, r13
0x1800b1da5  jz      loc_1800B1E75
0x1800b1dab  xor     ebp, ebp
0x1800b1dad  cmp     [rcx+4], ebp
0x1800b1db0  jbe     loc_1800B1E75
0x1800b1db6  mov     ecx, 0FFFEh
0x1800b1dbb  mov     rsi, [r13+8]
0x1800b1dbf  lea     rdi, ds:0[rbp*4]
0x1800b1dc7  add     rdi, rbp
0x1800b1dca  cmp     dword ptr [rsi+rdi*8+18h], 0
0x1800b1dcf  jz      loc_1800B1E64
0x1800b1dd5  cmp     qword ptr [rsi+rdi*8+20h], 0
0x1800b1ddb  jz      loc_1800B1E64
0x1800b1de1  test    r15, r15
0x1800b1de4  jz      short loc_1800B1E26
0x1800b1de6  movzx   eax, word ptr [rsi+rdi*8]
0x1800b1dea  and     ax, cx
0x1800b1ded  cmp     ax, 22h ; '"'
0x1800b1df1  jnz     short loc_1800B1E26
0x1800b1df3  movzx   ebx, word ptr [rsi+rdi*8]
0x1800b1df7  lea     rdx, SourceString; "EDP://PolicyFlags"
0x1800b1dfe  mov     rcx, [rsi+rdi*8+8]; Source1
0x1800b1e03  mov     r8d, ebx; Length
0x1800b1e06  call    cs:__imp_RtlCompareMemory
0x1800b1e0d  nop     dword ptr [rax+rax+00h]
0x1800b1e12  cmp     rax, rbx
0x1800b1e15  jnz     short loc_1800B1E21
0x1800b1e17  mov     rax, [rsi+rdi*8+20h]
0x1800b1e1c  mov     [r15], rax
0x1800b1e1f  jmp     short loc_1800B1E64
0x1800b1e21  mov     ecx, 0FFFEh
0x1800b1e26  test    r14, r14
0x1800b1e29  jz      short loc_1800B1E64
0x1800b1e2b  movzx   eax, word ptr [rsi+rdi*8]
0x1800b1e2f  and     ax, cx
0x1800b1e32  cmp     ax, 2Ah ; '*'
0x1800b1e36  jnz     short loc_1800B1E64
0x1800b1e38  movzx   ebx, word ptr [rsi+rdi*8]
0x1800b1e3c  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1800b1e43  mov     rcx, [rsi+rdi*8+8]; Source1
0x1800b1e48  mov     r8d, ebx; Length
0x1800b1e4b  call    cs:__imp_RtlCompareMemory
0x1800b1e52  nop     dword ptr [rax+rax+00h]
0x1800b1e57  cmp     rax, rbx
0x1800b1e5a  jnz     short loc_1800B1E64
0x1800b1e5c  mov     rax, [rsi+rdi*8+20h]
0x1800b1e61  mov     [r14], rax
0x1800b1e64  inc     ebp
0x1800b1e66  mov     ecx, 0FFFEh
0x1800b1e6b  cmp     ebp, [r13+4]
0x1800b1e6f  jb      loc_1800B1DBB
0x1800b1e75  add     rsp, 20h
0x1800b1e79  pop     r15
0x1800b1e7b  pop     r14
0x1800b1e7d  pop     r13
0x1800b1e7f  pop     rdi
0x1800b1e80  pop     rsi
0x1800b1e81  pop     rbp
0x1800b1e82  pop     rbx
0x1800b1e83  retn
```

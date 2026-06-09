# GetPointersOfAttributesValues

- ea: `0x1800177a8`
- end: `0x1800178c9`
- name: `GetPointersOfAttributesValues`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017ab4`

## callees

- `0x1800177a8`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x18001784a`
- `ntdll!RtlCompareMemory` at `0x18001788f`
- `ntdll!RtlCompareMemory` at `0x18001784a`
- `ntdll!RtlCompareMemory` at `0x18001788f`

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
0x1800177a8  push    rbx
0x1800177aa  push    rbp
0x1800177ab  push    rsi
0x1800177ac  push    rdi
0x1800177ad  push    r13
0x1800177af  push    r14
0x1800177b1  push    r15
0x1800177b3  sub     rsp, 20h
0x1800177b7  mov     r15, r8
0x1800177ba  mov     r14, rdx
0x1800177bd  mov     r13, rcx
0x1800177c0  test    r8, r8
0x1800177c3  jz      short loc_1800177CC
0x1800177c5  mov     qword ptr [r8], 0
0x1800177cc  test    r14, r14
0x1800177cf  jz      short loc_1800177D8
0x1800177d1  mov     qword ptr [rdx], 0
0x1800177d8  test    r15, r15
0x1800177db  jnz     short loc_1800177E6
0x1800177dd  test    r14, r14
0x1800177e0  jz      loc_1800178B9
0x1800177e6  test    r13, r13
0x1800177e9  jz      loc_1800178B9
0x1800177ef  xor     ebp, ebp
0x1800177f1  cmp     [rcx+4], ebp
0x1800177f4  jbe     loc_1800178B9
0x1800177fa  mov     ecx, 0FFFEh
0x1800177ff  mov     rsi, [r13+8]
0x180017803  lea     rdi, ds:0[rbp*4]
0x18001780b  add     rdi, rbp
0x18001780e  cmp     dword ptr [rsi+rdi*8+18h], 0
0x180017813  jz      loc_1800178A8
0x180017819  cmp     qword ptr [rsi+rdi*8+20h], 0
0x18001781f  jz      loc_1800178A8
0x180017825  test    r15, r15
0x180017828  jz      short loc_18001786A
0x18001782a  movzx   eax, word ptr [rsi+rdi*8]
0x18001782e  and     ax, cx
0x180017831  cmp     ax, 22h ; '"'
0x180017835  jnz     short loc_18001786A
0x180017837  movzx   ebx, word ptr [rsi+rdi*8]
0x18001783b  lea     rdx, SourceString; "EDP://PolicyFlags"
0x180017842  mov     rcx, [rsi+rdi*8+8]; Source1
0x180017847  mov     r8d, ebx; Length
0x18001784a  call    cs:__imp_RtlCompareMemory
0x180017851  nop     dword ptr [rax+rax+00h]
0x180017856  cmp     rax, rbx
0x180017859  jnz     short loc_180017865
0x18001785b  mov     rax, [rsi+rdi*8+20h]
0x180017860  mov     [r15], rax
0x180017863  jmp     short loc_1800178A8
0x180017865  mov     ecx, 0FFFEh
0x18001786a  test    r14, r14
0x18001786d  jz      short loc_1800178A8
0x18001786f  movzx   eax, word ptr [rsi+rdi*8]
0x180017873  and     ax, cx
0x180017876  cmp     ax, 2Ah ; '*'
0x18001787a  jnz     short loc_1800178A8
0x18001787c  movzx   ebx, word ptr [rsi+rdi*8]
0x180017880  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x180017887  mov     rcx, [rsi+rdi*8+8]; Source1
0x18001788c  mov     r8d, ebx; Length
0x18001788f  call    cs:__imp_RtlCompareMemory
0x180017896  nop     dword ptr [rax+rax+00h]
0x18001789b  cmp     rax, rbx
0x18001789e  jnz     short loc_1800178A8
0x1800178a0  mov     rax, [rsi+rdi*8+20h]
0x1800178a5  mov     [r14], rax
0x1800178a8  inc     ebp
0x1800178aa  mov     ecx, 0FFFEh
0x1800178af  cmp     ebp, [r13+4]
0x1800178b3  jb      loc_1800177FF
0x1800178b9  add     rsp, 20h
0x1800178bd  pop     r15
0x1800178bf  pop     r14
0x1800178c1  pop     r13
0x1800178c3  pop     rdi
0x1800178c4  pop     rsi
0x1800178c5  pop     rbp
0x1800178c6  pop     rbx
0x1800178c7  retn
```

# GetPointersOfAttributesValues

- ea: `0x140004b48`
- end: `0x140004d7c`
- name: `GetPointersOfAttributesValues`
- size: `564`
- prototype: `void __fastcall(__int64, _QWORD *, _QWORD *, _DWORD *, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400051c4`
- `0x14000525c`
- `0x140005370`

## callees

- `0x140004b48`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140004c38`
- `ntoskrnl!RtlCompareMemory` at `0x140004c82`
- `ntoskrnl!RtlCompareMemory` at `0x140004cd1`
- `ntoskrnl!RtlCompareMemory` at `0x140004d2d`
- `ntoskrnl!RtlCompareMemory` at `0x140004c38`
- `ntoskrnl!RtlCompareMemory` at `0x140004c82`
- `ntoskrnl!RtlCompareMemory` at `0x140004cd1`
- `ntoskrnl!RtlCompareMemory` at `0x140004d2d`

## pseudocode

```c
void __fastcall GetPointersOfAttributesValues(__int64 a1, _QWORD *a2, _QWORD *a3, _DWORD *a4, _QWORD *a5, _QWORD *a6)
{
  __int64 v9; // rsi
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rdi
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int i; // [rsp+90h] [rbp+28h]

  v9 = a1;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 || a4 || a5 || a6 || a2 )
  {
    if ( a1 )
    {
      v11 = 0;
      for ( i = 0; (unsigned int)v11 < *(_DWORD *)(a1 + 4); i = v11 )
      {
        v12 = *(_QWORD *)(v9 + 8);
        v13 = 5 * v11;
        if ( *(_DWORD *)(v12 + 40 * v11 + 24) && *(_QWORD *)(v12 + 40 * v11 + 32) )
        {
          if ( a3
            && (v14 = *(unsigned __int16 *)(v12 + 40 * v11), (v14 & 0xFFFE) == 0x22)
            && RtlCompareMemory(
                 *(const void **)(v12 + 40 * v11 + 8),
                 L"EDP://PolicyFlags",
                 *(unsigned __int16 *)(v12 + 40 * v11)) == v14 )
          {
            *a3 = *(_QWORD *)(v12 + 8 * v13 + 32);
          }
          else if ( a2
                 && (v15 = *(unsigned __int16 *)(v12 + 8 * v13), (v15 & 0xFFFE) == 0x2A)
                 && RtlCompareMemory(
                      *(const void **)(v12 + 8 * v13 + 8),
                      L"EDP://EvaluationFlags",
                      *(unsigned __int16 *)(v12 + 8 * v13)) == v15 )
          {
            *a2 = *(_QWORD *)(v12 + 8 * v13 + 32);
          }
          else if ( (a4 || a5)
                 && (v16 = *(unsigned __int16 *)(v12 + 8 * v13), (v16 & 0xFFFE) == 0x26)
                 && RtlCompareMemory(
                      *(const void **)(v12 + 8 * v13 + 8),
                      L"EDP://EnterpriseIds",
                      *(unsigned __int16 *)(v12 + 8 * v13)) == v16 )
          {
            if ( a4 )
              *a4 = *(_DWORD *)(v12 + 8 * v13 + 24);
            if ( a5 )
              *a5 = *(_QWORD *)(v12 + 8 * v13 + 32);
          }
          else if ( a6 )
          {
            v17 = *(unsigned __int16 *)(v12 + 8 * v13);
            if ( (v17 & 0xFFFE) == 0x32
              && RtlCompareMemory(
                   *(const void **)(v12 + 8 * v13 + 8),
                   L"PEDP://IntentEnterpriseId",
                   *(unsigned __int16 *)(v12 + 8 * v13)) == v17 )
            {
              *a6 = *(_QWORD *)(v12 + 8 * v13 + 32);
            }
          }
        }
        v9 = a1;
        v11 = (unsigned int)(i + 1);
      }
    }
  }
}

```

## disassembly

```asm
0x140004b48  mov     [rsp+arg_0], rcx
0x140004b4d  push    rbx
0x140004b4e  push    rbp
0x140004b4f  push    rsi
0x140004b50  push    rdi
0x140004b51  push    r12
0x140004b53  push    r13
0x140004b55  push    r14
0x140004b57  push    r15
0x140004b59  sub     rsp, 28h
0x140004b5d  mov     r15, r9
0x140004b60  mov     r13, r8
0x140004b63  mov     r12, rdx
0x140004b66  mov     rsi, rcx
0x140004b69  test    r8, r8
0x140004b6c  jz      short loc_140004B75
0x140004b6e  mov     qword ptr [r8], 0
0x140004b75  test    r15, r15
0x140004b78  jz      short loc_140004B81
0x140004b7a  mov     dword ptr [r9], 0
0x140004b81  mov     r14, [rsp+68h+arg_20]
0x140004b89  test    r14, r14
0x140004b8c  jz      short loc_140004B95
0x140004b8e  mov     qword ptr [r14], 0
0x140004b95  mov     rbp, [rsp+68h+arg_28]
0x140004b9d  test    rbp, rbp
0x140004ba0  jz      short loc_140004BAA
0x140004ba2  mov     qword ptr [rbp+0], 0
0x140004baa  test    r12, r12
0x140004bad  jz      short loc_140004BB6
0x140004baf  mov     qword ptr [rdx], 0
0x140004bb6  test    r13, r13
0x140004bb9  jnz     short loc_140004BD3
0x140004bbb  test    r15, r15
0x140004bbe  jnz     short loc_140004BD3
0x140004bc0  test    r14, r14
0x140004bc3  jnz     short loc_140004BD3
0x140004bc5  test    rbp, rbp
0x140004bc8  jnz     short loc_140004BD3
0x140004bca  test    r12, r12
0x140004bcd  jz      loc_140004D6A
0x140004bd3  test    rcx, rcx
0x140004bd6  jz      loc_140004D6A
0x140004bdc  xor     eax, eax
0x140004bde  mov     dword ptr [rsp+68h+arg_20], eax
0x140004be5  cmp     [rcx+4], eax
0x140004be8  jbe     loc_140004D6A
0x140004bee  mov     edx, 0FFFEh
0x140004bf3  mov     rsi, [rsi+8]
0x140004bf7  lea     rdi, [rax+rax*4]
0x140004bfb  cmp     dword ptr [rsi+rdi*8+18h], 0
0x140004c00  jz      loc_140004D4C
0x140004c06  cmp     qword ptr [rsi+rdi*8+20h], 0
0x140004c0c  jz      loc_140004D4C
0x140004c12  test    r13, r13
0x140004c15  jz      short loc_140004C5C
0x140004c17  movzx   ecx, word ptr [rsi+rdi*8]
0x140004c1b  movzx   eax, cx
0x140004c1e  and     ax, dx
0x140004c21  cmp     ax, 22h ; '"'
0x140004c25  jnz     short loc_140004C5C
0x140004c27  mov     ebx, ecx
0x140004c29  lea     rdx, SourceString; "EDP://PolicyFlags"
0x140004c30  mov     r8d, ecx; Length
0x140004c33  mov     rcx, [rsi+rdi*8+8]; Source1
0x140004c38  call    cs:__imp_RtlCompareMemory
0x140004c3f  nop     dword ptr [rax+rax+00h]
0x140004c44  mov     edx, 0FFFEh
0x140004c49  cmp     rax, rbx
0x140004c4c  jnz     short loc_140004C5C
0x140004c4e  mov     rax, [rsi+rdi*8+20h]
0x140004c53  mov     [r13+0], rax
0x140004c57  jmp     loc_140004D4C
0x140004c5c  test    r12, r12
0x140004c5f  jz      short loc_140004CA1
0x140004c61  movzx   ecx, word ptr [rsi+rdi*8]
0x140004c65  movzx   eax, cx
0x140004c68  and     ax, dx
0x140004c6b  cmp     ax, 2Ah ; '*'
0x140004c6f  jnz     short loc_140004CA1
0x140004c71  mov     ebx, ecx
0x140004c73  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x140004c7a  mov     r8d, ecx; Length
0x140004c7d  mov     rcx, [rsi+rdi*8+8]; Source1
0x140004c82  call    cs:__imp_RtlCompareMemory
0x140004c89  nop     dword ptr [rax+rax+00h]
0x140004c8e  cmp     rax, rbx
0x140004c91  jnz     short loc_140004CA1
0x140004c93  mov     rax, [rsi+rdi*8+20h]
0x140004c98  mov     [r12], rax
0x140004c9c  jmp     loc_140004D47
0x140004ca1  test    r15, r15
0x140004ca4  jnz     short loc_140004CAB
0x140004ca6  test    r14, r14
0x140004ca9  jz      short loc_140004D02
0x140004cab  movzx   ecx, word ptr [rsi+rdi*8]
0x140004caf  mov     edx, 0FFFEh
0x140004cb4  movzx   eax, cx
0x140004cb7  and     ax, dx
0x140004cba  cmp     ax, 26h ; '&'
0x140004cbe  jnz     short loc_140004D07
0x140004cc0  mov     ebx, ecx
0x140004cc2  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x140004cc9  mov     r8d, ecx; Length
0x140004ccc  mov     rcx, [rsi+rdi*8+8]; Source1
0x140004cd1  call    cs:__imp_RtlCompareMemory
0x140004cd8  nop     dword ptr [rax+rax+00h]
0x140004cdd  cmp     rax, rbx
0x140004ce0  jnz     short loc_140004D02
0x140004ce2  test    r15, r15
0x140004ce5  jz      short loc_140004CEE
0x140004ce7  mov     eax, [rsi+rdi*8+18h]
0x140004ceb  mov     [r15], eax
0x140004cee  mov     edx, 0FFFEh
0x140004cf3  test    r14, r14
0x140004cf6  jz      short loc_140004D4C
0x140004cf8  mov     rax, [rsi+rdi*8+20h]
0x140004cfd  mov     [r14], rax
0x140004d00  jmp     short loc_140004D4C
0x140004d02  mov     edx, 0FFFEh
0x140004d07  test    rbp, rbp
0x140004d0a  jz      short loc_140004D4C
0x140004d0c  movzx   ecx, word ptr [rsi+rdi*8]
0x140004d10  movzx   eax, cx
0x140004d13  and     ax, dx
0x140004d16  cmp     ax, 32h ; '2'
0x140004d1a  jnz     short loc_140004D4C
0x140004d1c  mov     ebx, ecx
0x140004d1e  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x140004d25  mov     r8d, ecx; Length
0x140004d28  mov     rcx, [rsi+rdi*8+8]; Source1
0x140004d2d  call    cs:__imp_RtlCompareMemory
0x140004d34  nop     dword ptr [rax+rax+00h]
0x140004d39  cmp     rax, rbx
0x140004d3c  jnz     short loc_140004D47
0x140004d3e  mov     rax, [rsi+rdi*8+20h]
0x140004d43  mov     [rbp+0], rax
0x140004d47  mov     edx, 0FFFEh
0x140004d4c  mov     eax, dword ptr [rsp+68h+arg_20]
0x140004d53  mov     rsi, [rsp+68h+arg_0]
0x140004d58  inc     eax
0x140004d5a  mov     dword ptr [rsp+68h+arg_20], eax
0x140004d61  cmp     eax, [rsi+4]
0x140004d64  jb      loc_140004BF3
0x140004d6a  add     rsp, 28h
0x140004d6e  pop     r15
0x140004d70  pop     r14
0x140004d72  pop     r13
0x140004d74  pop     r12
0x140004d76  pop     rdi
0x140004d77  pop     rsi
0x140004d78  pop     rbp
0x140004d79  pop     rbx
0x140004d7a  retn
```

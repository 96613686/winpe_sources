# avpriv_update_cur_dts

- ea: `0x180019f50`
- end: `0x180019fca`
- name: `avpriv_update_cur_dts`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001aaf0`
- `0x18001ae48`

## callees

- `0x180019f50`
- `0x18001bc5a`

## pseudocode

```c
_UNKNOWN **__fastcall avpriv_update_cur_dts(__int64 a1, __int64 a2, __int64 a3)
{
  _UNKNOWN **result; // rax
  __int64 i; // rdi
  __int64 v8; // rbx
  _UNKNOWN *retaddr; // [rsp+28h] [rbp+0h] BYREF

  result = &retaddr;
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 44); *(_QWORD *)(v8 + 840) = result )
  {
    v8 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * i);
    result = (_UNKNOWN **)av_rescale(
                            a3,
                            *(int *)(a2 + 32) * (__int64)*(int *)(v8 + 36),
                            *(int *)(a2 + 36) * (__int64)*(int *)(v8 + 32));
    i = (unsigned int)(i + 1);
  }
  return result;
}

```

## disassembly

```asm
0x180019f50  mov     rax, rsp
0x180019f53  mov     [rax+8], rbx
0x180019f57  mov     [rax+10h], rbp
0x180019f5b  mov     [rax+18h], rsi
0x180019f5f  mov     [rax+20h], rdi
0x180019f63  push    r14
0x180019f65  sub     rsp, 20h
0x180019f69  xor     edi, edi
0x180019f6b  mov     r14, r8
0x180019f6e  mov     rbp, rdx
0x180019f71  mov     rsi, rcx
0x180019f74  cmp     [rcx+2Ch], edi
0x180019f77  jbe     short loc_180019FAF
0x180019f79  mov     rax, [rsi+30h]
0x180019f7d  mov     rcx, r14
0x180019f80  mov     rbx, [rax+rdi*8]
0x180019f84  movsxd  rax, dword ptr [rbp+24h]
0x180019f88  movsxd  r8, dword ptr [rbx+20h]
0x180019f8c  movsxd  rdx, dword ptr [rbx+24h]
0x180019f90  imul    r8, rax
0x180019f94  movsxd  rax, dword ptr [rbp+20h]
0x180019f98  imul    rdx, rax
0x180019f9c  call    av_rescale
0x180019fa1  inc     edi
0x180019fa3  mov     [rbx+348h], rax
0x180019faa  cmp     edi, [rsi+2Ch]
0x180019fad  jb      short loc_180019F79
0x180019faf  mov     rbx, [rsp+28h+arg_0]
0x180019fb4  mov     rbp, [rsp+28h+arg_8]
0x180019fb9  mov     rsi, [rsp+28h+arg_10]
0x180019fbe  mov     rdi, [rsp+28h+arg_18]
0x180019fc3  add     rsp, 20h
0x180019fc7  pop     r14
0x180019fc9  retn
```

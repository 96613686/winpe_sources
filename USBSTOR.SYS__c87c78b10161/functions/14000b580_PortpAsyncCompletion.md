# PortpAsyncCompletion

- ea: `0x14000b580`
- end: `0x14000b608`
- name: `PortpAsyncCompletion`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b580`
- `0x14000b610`

## import_xrefs

- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000b5b7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000b5b7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000b5da`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000b5da`

## pseudocode

```c
__int64 __fastcall PortpAsyncCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rax
  __int64 v6; // rbx
  KIRQL Irql; // [rsp+40h] [rbp+18h] BYREF

  v3 = *(_QWORD *)(a3 + 16);
  if ( _InterlockedExchange64((volatile __int64 *)(v3 + 104), 0) )
  {
    *(_QWORD *)(*(_QWORD *)(v3 + 184) + 32LL) = 0;
LABEL_4:
    PortpCompleteRequestIrp(*(_QWORD *)(a3 + 16), (char *)a3);
    return 3221225494LL;
  }
  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  v5 = *(_QWORD *)(v3 + 184);
  v6 = *(_QWORD *)(v5 + 32);
  *(_QWORD *)(v5 + 32) = 0;
  IoReleaseCancelSpinLock(Irql);
  if ( !v6 )
    goto LABEL_4;
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000b580  mov     [rsp+arg_0], rbx
0x14000b585  push    rdi
0x14000b586  sub     rsp, 20h
0x14000b58a  mov     rbx, [r8+10h]
0x14000b58e  xor     eax, eax
0x14000b590  mov     rdi, r8
0x14000b593  xchg    rax, [rbx+68h]
0x14000b597  test    rax, rax
0x14000b59a  jz      short loc_14000B5AD
0x14000b59c  mov     rax, [rbx+0B8h]
0x14000b5a3  mov     qword ptr [rax+20h], 0
0x14000b5ab  jmp     short loc_14000B5EB
0x14000b5ad  lea     rcx, [rsp+28h+Irql]; Irql
0x14000b5b2  mov     [rsp+28h+Irql], 0
0x14000b5b7  call    cs:__imp_IoAcquireCancelSpinLock
0x14000b5be  nop     dword ptr [rax+rax+00h]
0x14000b5c3  mov     rax, [rbx+0B8h]
0x14000b5ca  mov     rbx, [rax+20h]
0x14000b5ce  mov     qword ptr [rax+20h], 0
0x14000b5d6  mov     cl, [rsp+28h+Irql]; Irql
0x14000b5da  call    cs:__imp_IoReleaseCancelSpinLock
0x14000b5e1  nop     dword ptr [rax+rax+00h]
0x14000b5e6  test    rbx, rbx
0x14000b5e9  jnz     short loc_14000B5F7
0x14000b5eb  mov     rcx, [rdi+10h]
0x14000b5ef  mov     rdx, rdi
0x14000b5f2  call    PortpCompleteRequestIrp
0x14000b5f7  mov     rbx, [rsp+28h+arg_0]
0x14000b5fc  mov     eax, 0C0000016h
0x14000b601  add     rsp, 20h
0x14000b605  pop     rdi
0x14000b606  retn
```

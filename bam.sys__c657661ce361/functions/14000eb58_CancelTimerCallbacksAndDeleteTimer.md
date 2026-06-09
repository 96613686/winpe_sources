# CancelTimerCallbacksAndDeleteTimer

- ea: `0x14000eb58`
- end: `0x14000ebf9`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000edc8`
- `0x14000f0c0`

## callees

- `0x14000eb58`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000ebae`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ebae`
- `ntoskrnl!ExDeleteTimer` at `0x14000ebdb`
- `ntoskrnl!ExDeleteTimer` at `0x14000ebdb`

## pseudocode

```c
__int64 __fastcall CancelTimerCallbacksAndDeleteTimer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 result; // rax
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]

  if ( *(_QWORD *)(a1 + 360) )
  {
    v9 = 0;
    v8 = 0;
    v5 = 2;
    v4 = *(_QWORD *)(a1 + 264);
    LOWORD(v5) = *(_WORD *)(v4 + 56);
    *(_WORD *)(v4 + 56) = 2;
    if ( (_WORD)v5 == 1 )
      KeWaitForSingleObject((PVOID)(*(_QWORD *)(a1 + 264) + 32LL), Executive, 0, 0, 0);
    v6 = *(_QWORD *)(a1 + 360);
    LOBYTE(a3) = 1;
    LOBYTE(v5) = 1;
    v8 = 0;
    v9 = 0;
    result = ExDeleteTimer(v6, v5, a3, &v8);
    *(_QWORD *)(a1 + 360) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000eb58  push    rbx
0x14000eb5a  sub     rsp, 50h
0x14000eb5e  cmp     qword ptr [rcx+168h], 0
0x14000eb66  mov     rbx, rcx
0x14000eb69  jz      loc_14000EBF2
0x14000eb6f  xor     eax, eax
0x14000eb71  xorps   xmm0, xmm0
0x14000eb74  mov     [rsp+58h+var_18], rax
0x14000eb79  movups  [rsp+58h+var_28], xmm0
0x14000eb7e  lea     edx, [rax+2]
0x14000eb81  mov     rax, [rcx+108h]
0x14000eb88  xchg    dx, [rax+38h]
0x14000eb8c  cmp     dx, 1
0x14000eb90  jnz     short loc_14000EBBA
0x14000eb92  mov     rcx, [rcx+108h]
0x14000eb99  xor     r9d, r9d; Alertable
0x14000eb9c  add     rcx, 20h ; ' '; Object
0x14000eba0  mov     [rsp+58h+Timeout], 0; Timeout
0x14000eba9  xor     r8d, r8d; WaitMode
0x14000ebac  xor     edx, edx; WaitReason
0x14000ebae  call    cs:__imp_KeWaitForSingleObject
0x14000ebb5  nop     dword ptr [rax+rax+00h]
0x14000ebba  mov     rcx, [rbx+168h]
0x14000ebc1  lea     r9, [rsp+58h+var_28]
0x14000ebc6  mov     r8b, 1
0x14000ebc9  xorps   xmm0, xmm0
0x14000ebcc  xor     eax, eax
0x14000ebce  mov     dl, r8b
0x14000ebd1  movups  [rsp+58h+var_28], xmm0
0x14000ebd6  mov     [rsp+58h+var_18], rax
0x14000ebdb  call    cs:__imp_ExDeleteTimer
0x14000ebe2  nop     dword ptr [rax+rax+00h]
0x14000ebe7  mov     qword ptr [rbx+168h], 0
0x14000ebf2  add     rsp, 50h
0x14000ebf6  pop     rbx
0x14000ebf7  retn
```

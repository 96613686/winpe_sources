# CancelTimerCallbacksAndDeleteTimer

- ea: `0x140046614`
- end: `0x1400466b5`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140036f5c`
- `0x1400467f4`

## callees

- `0x140046614`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14004666a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004666a`
- `ntoskrnl!ExDeleteTimer` at `0x140046697`
- `ntoskrnl!ExDeleteTimer` at `0x140046697`

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
0x140046614  push    rbx
0x140046616  sub     rsp, 50h
0x14004661a  cmp     qword ptr [rcx+168h], 0
0x140046622  mov     rbx, rcx
0x140046625  jz      loc_1400466AE
0x14004662b  xor     eax, eax
0x14004662d  xorps   xmm0, xmm0
0x140046630  mov     [rsp+58h+var_18], rax
0x140046635  movups  [rsp+58h+var_28], xmm0
0x14004663a  lea     edx, [rax+2]
0x14004663d  mov     rax, [rcx+108h]
0x140046644  xchg    dx, [rax+38h]
0x140046648  cmp     dx, 1
0x14004664c  jnz     short loc_140046676
0x14004664e  mov     rcx, [rcx+108h]
0x140046655  xor     r9d, r9d; Alertable
0x140046658  add     rcx, 20h ; ' '; Object
0x14004665c  mov     [rsp+58h+Timeout], 0; Timeout
0x140046665  xor     r8d, r8d; WaitMode
0x140046668  xor     edx, edx; WaitReason
0x14004666a  call    cs:__imp_KeWaitForSingleObject
0x140046671  nop     dword ptr [rax+rax+00h]
0x140046676  mov     rcx, [rbx+168h]
0x14004667d  lea     r9, [rsp+58h+var_28]
0x140046682  mov     r8b, 1
0x140046685  xorps   xmm0, xmm0
0x140046688  xor     eax, eax
0x14004668a  mov     dl, r8b
0x14004668d  movups  [rsp+58h+var_28], xmm0
0x140046692  mov     [rsp+58h+var_18], rax
0x140046697  call    cs:__imp_ExDeleteTimer
0x14004669e  nop     dword ptr [rax+rax+00h]
0x1400466a3  mov     qword ptr [rbx+168h], 0
0x1400466ae  add     rsp, 50h
0x1400466b2  pop     rbx
0x1400466b3  retn
```

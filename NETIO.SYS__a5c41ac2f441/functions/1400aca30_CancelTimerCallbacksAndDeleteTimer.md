# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1400aca30`
- end: `0x1400acad1`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400acca0`
- `0x1400acf54`

## callees

- `0x1400aca30`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x1400acab3`
- `ntoskrnl!ExDeleteTimer` at `0x1400acab3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400aca86`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400aca86`

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
0x1400aca30  push    rbx
0x1400aca32  sub     rsp, 50h
0x1400aca36  cmp     qword ptr [rcx+168h], 0
0x1400aca3e  mov     rbx, rcx
0x1400aca41  jz      loc_1400ACACA
0x1400aca47  xor     eax, eax
0x1400aca49  xorps   xmm0, xmm0
0x1400aca4c  mov     [rsp+58h+var_18], rax
0x1400aca51  movups  [rsp+58h+var_28], xmm0
0x1400aca56  lea     edx, [rax+2]
0x1400aca59  mov     rax, [rcx+108h]
0x1400aca60  xchg    dx, [rax+38h]
0x1400aca64  cmp     dx, 1
0x1400aca68  jnz     short loc_1400ACA92
0x1400aca6a  mov     rcx, [rcx+108h]
0x1400aca71  xor     r9d, r9d; Alertable
0x1400aca74  add     rcx, 20h ; ' '; Object
0x1400aca78  mov     [rsp+58h+Timeout], 0; Timeout
0x1400aca81  xor     r8d, r8d; WaitMode
0x1400aca84  xor     edx, edx; WaitReason
0x1400aca86  call    cs:__imp_KeWaitForSingleObject
0x1400aca8d  nop     dword ptr [rax+rax+00h]
0x1400aca92  mov     rcx, [rbx+168h]
0x1400aca99  lea     r9, [rsp+58h+var_28]
0x1400aca9e  mov     r8b, 1
0x1400acaa1  xorps   xmm0, xmm0
0x1400acaa4  xor     eax, eax
0x1400acaa6  mov     dl, r8b
0x1400acaa9  movups  [rsp+58h+var_28], xmm0
0x1400acaae  mov     [rsp+58h+var_18], rax
0x1400acab3  call    cs:__imp_ExDeleteTimer
0x1400acaba  nop     dword ptr [rax+rax+00h]
0x1400acabf  mov     qword ptr [rbx+168h], 0
0x1400acaca  add     rsp, 50h
0x1400acace  pop     rbx
0x1400acacf  retn
```

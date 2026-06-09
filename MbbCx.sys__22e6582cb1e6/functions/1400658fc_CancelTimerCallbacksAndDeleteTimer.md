# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1400658fc`
- end: `0x14006599d`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140065adc`
- `0x140066384`

## callees

- `0x1400658fc`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x14006597f`
- `ntoskrnl!ExDeleteTimer` at `0x14006597f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065952`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065952`

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
0x1400658fc  push    rbx
0x1400658fe  sub     rsp, 50h
0x140065902  cmp     qword ptr [rcx+168h], 0
0x14006590a  mov     rbx, rcx
0x14006590d  jz      loc_140065996
0x140065913  xor     eax, eax
0x140065915  xorps   xmm0, xmm0
0x140065918  mov     [rsp+58h+var_18], rax
0x14006591d  movups  [rsp+58h+var_28], xmm0
0x140065922  lea     edx, [rax+2]
0x140065925  mov     rax, [rcx+108h]
0x14006592c  xchg    dx, [rax+38h]
0x140065930  cmp     dx, 1
0x140065934  jnz     short loc_14006595E
0x140065936  mov     rcx, [rcx+108h]
0x14006593d  xor     r9d, r9d; Alertable
0x140065940  add     rcx, 20h ; ' '; Object
0x140065944  mov     [rsp+58h+Timeout], 0; Timeout
0x14006594d  xor     r8d, r8d; WaitMode
0x140065950  xor     edx, edx; WaitReason
0x140065952  call    cs:__imp_KeWaitForSingleObject
0x140065959  nop     dword ptr [rax+rax+00h]
0x14006595e  mov     rcx, [rbx+168h]
0x140065965  lea     r9, [rsp+58h+var_28]
0x14006596a  mov     r8b, 1
0x14006596d  xorps   xmm0, xmm0
0x140065970  xor     eax, eax
0x140065972  mov     dl, r8b
0x140065975  movups  [rsp+58h+var_28], xmm0
0x14006597a  mov     [rsp+58h+var_18], rax
0x14006597f  call    cs:__imp_ExDeleteTimer
0x140065986  nop     dword ptr [rax+rax+00h]
0x14006598b  mov     qword ptr [rbx+168h], 0
0x140065996  add     rsp, 50h
0x14006599a  pop     rbx
0x14006599b  retn
```

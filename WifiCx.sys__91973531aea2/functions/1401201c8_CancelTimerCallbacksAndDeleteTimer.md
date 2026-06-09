# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1401201c8`
- end: `0x140120269`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140120438`
- `0x140120b98`

## callees

- `0x1401201c8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14012021e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012021e`
- `ntoskrnl!ExDeleteTimer` at `0x14012024b`
- `ntoskrnl!ExDeleteTimer` at `0x14012024b`

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
0x1401201c8  push    rbx
0x1401201ca  sub     rsp, 50h
0x1401201ce  cmp     qword ptr [rcx+168h], 0
0x1401201d6  mov     rbx, rcx
0x1401201d9  jz      loc_140120262
0x1401201df  xor     eax, eax
0x1401201e1  xorps   xmm0, xmm0
0x1401201e4  mov     [rsp+58h+var_18], rax
0x1401201e9  movups  [rsp+58h+var_28], xmm0
0x1401201ee  lea     edx, [rax+2]
0x1401201f1  mov     rax, [rcx+108h]
0x1401201f8  xchg    dx, [rax+38h]
0x1401201fc  cmp     dx, 1
0x140120200  jnz     short loc_14012022A
0x140120202  mov     rcx, [rcx+108h]
0x140120209  xor     r9d, r9d; Alertable
0x14012020c  add     rcx, 20h ; ' '; Object
0x140120210  mov     [rsp+58h+Timeout], 0; Timeout
0x140120219  xor     r8d, r8d; WaitMode
0x14012021c  xor     edx, edx; WaitReason
0x14012021e  call    cs:__imp_KeWaitForSingleObject
0x140120225  nop     dword ptr [rax+rax+00h]
0x14012022a  mov     rcx, [rbx+168h]
0x140120231  lea     r9, [rsp+58h+var_28]
0x140120236  mov     r8b, 1
0x140120239  xorps   xmm0, xmm0
0x14012023c  xor     eax, eax
0x14012023e  mov     dl, r8b
0x140120241  movups  [rsp+58h+var_28], xmm0
0x140120246  mov     [rsp+58h+var_18], rax
0x14012024b  call    cs:__imp_ExDeleteTimer
0x140120252  nop     dword ptr [rax+rax+00h]
0x140120257  mov     qword ptr [rbx+168h], 0
0x140120262  add     rsp, 50h
0x140120266  pop     rbx
0x140120267  retn
```

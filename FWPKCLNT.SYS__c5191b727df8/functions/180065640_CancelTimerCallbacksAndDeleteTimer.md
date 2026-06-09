# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180065640`
- end: `0x1800656e1`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180065778`
- `0x180065904`

## callees

- `0x180065640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x180065696`
- `ntoskrnl!KeWaitForSingleObject` at `0x180065696`
- `ntoskrnl!ExDeleteTimer` at `0x1800656c3`
- `ntoskrnl!ExDeleteTimer` at `0x1800656c3`

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
0x180065640  push    rbx
0x180065642  sub     rsp, 50h
0x180065646  cmp     qword ptr [rcx+168h], 0
0x18006564e  mov     rbx, rcx
0x180065651  jz      loc_1800656DA
0x180065657  xor     eax, eax
0x180065659  xorps   xmm0, xmm0
0x18006565c  mov     [rsp+58h+var_18], rax
0x180065661  movups  [rsp+58h+var_28], xmm0
0x180065666  lea     edx, [rax+2]
0x180065669  mov     rax, [rcx+108h]
0x180065670  xchg    dx, [rax+38h]
0x180065674  cmp     dx, 1
0x180065678  jnz     short loc_1800656A2
0x18006567a  mov     rcx, [rcx+108h]
0x180065681  xor     r9d, r9d; Alertable
0x180065684  add     rcx, 20h ; ' '; Object
0x180065688  mov     [rsp+58h+Timeout], 0; Timeout
0x180065691  xor     r8d, r8d; WaitMode
0x180065694  xor     edx, edx; WaitReason
0x180065696  call    cs:__imp_KeWaitForSingleObject
0x18006569d  nop     dword ptr [rax+rax+00h]
0x1800656a2  mov     rcx, [rbx+168h]
0x1800656a9  lea     r9, [rsp+58h+var_28]
0x1800656ae  mov     r8b, 1
0x1800656b1  xorps   xmm0, xmm0
0x1800656b4  xor     eax, eax
0x1800656b6  mov     dl, r8b
0x1800656b9  movups  [rsp+58h+var_28], xmm0
0x1800656be  mov     [rsp+58h+var_18], rax
0x1800656c3  call    cs:__imp_ExDeleteTimer
0x1800656ca  nop     dword ptr [rax+rax+00h]
0x1800656cf  mov     qword ptr [rbx+168h], 0
0x1800656da  add     rsp, 50h
0x1800656de  pop     rbx
0x1800656df  retn
```

# sub_18000BBCC

- ea: `0x18000bbcc`
- end: `0x18000bc6a`
- name: `sub_18000BBCC`
- size: `158`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18016f3e0`
- `0x18016f47a`
- `0x18016f514`
- `0x18016f559`
- `0x18016f5c8`
- `0x18016f60d`
- `0x18016f6d2`
- `0x18016f717`
- `0x18016f7b8`

## import_xrefs

- `VCRUNTIME140!__std_exception_destroy` at `0x18000bc4f`
- `VCRUNTIME140!__std_exception_destroy` at `0x18000bc4f`
- `VCRUNTIME140!__std_exception_copy` at `0x18000bc03`
- `VCRUNTIME140!__std_exception_copy` at `0x18000bc03`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000bc2d`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000bc2d`
- `MSVCP140!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18000bc41`
- `MSVCP140!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18000bc41`

## pseudocode

```c
_QWORD *__fastcall sub_18000BBCC(_QWORD *a1, __int64 a2)
{
  __int64 v4; // [rsp+28h] [rbp-38h] BYREF
  char v5; // [rsp+30h] [rbp-30h]
  void **v6; // [rsp+38h] [rbp-28h] BYREF
  __int128 v7; // [rsp+40h] [rbp-20h] BYREF
  int v8; // [rsp+50h] [rbp-10h]

  v4 = a2;
  v5 = 1;
  v6 = &std::exception::`vftable';
  v7 = 0;
  _std_exception_copy(&v4, &v7);
  v8 = 0;
  v6 = &ChartPlayer::ChartPlayerError::`vftable';
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCopyException(a1, &v6, &_TI3_AUChartPlayerError_ChartPlayer__);
  v6 = &std::exception::`vftable';
  _std_exception_destroy(&v7);
  return a1;
}

```

## disassembly

```asm
0x18000bbcc  mov     [rsp-8+arg_8], rbx
0x18000bbd1  mov     [rsp-8+arg_10], rsi
0x18000bbd6  push    rbp
0x18000bbd7  mov     rbp, rsp
0x18000bbda  sub     rsp, 60h
0x18000bbde  mov     rbx, rcx
0x18000bbe1  mov     [rbp+var_38], rdx
0x18000bbe5  xorps   xmm0, xmm0
0x18000bbe8  mov     [rbp+var_30], 1
0x18000bbec  lea     rsi, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000bbf3  lea     rdx, [rbp+var_20]
0x18000bbf7  mov     [rbp+var_28], rsi
0x18000bbfb  lea     rcx, [rbp+var_38]
0x18000bbff  movups  [rbp+var_20], xmm0
0x18000bc03  call    cs:__std_exception_copy
0x18000bc09  lea     rax, ??_7ChartPlayerError@ChartPlayer@@6B@; const ChartPlayer::ChartPlayerError::`vftable'
0x18000bc10  mov     [rbp+var_10], 0
0x18000bc17  mov     rcx, rbx
0x18000bc1a  mov     [rbp+var_28], rax
0x18000bc1e  mov     qword ptr [rbx], 0
0x18000bc25  mov     qword ptr [rbx+8], 0
0x18000bc2d  call    cs:?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000bc33  lea     r8, __TI3?AUChartPlayerError@ChartPlayer@@; throw info for 'struct ChartPlayer::ChartPlayerError'
0x18000bc3a  mov     rcx, rbx
0x18000bc3d  lea     rdx, [rbp+var_28]
0x18000bc41  call    cs:?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18000bc47  lea     rcx, [rbp+var_20]
0x18000bc4b  mov     [rbp+var_28], rsi
0x18000bc4f  call    cs:__std_exception_destroy
0x18000bc55  mov     rax, rbx
0x18000bc58  lea     r11, [rsp+60h+var_s0]
0x18000bc5d  mov     rbx, [r11+18h]
0x18000bc61  mov     rsi, [r11+20h]
0x18000bc65  mov     rsp, r11
0x18000bc68  pop     rbp
0x18000bc69  retn
```

# CGeodeticBoolean::CGeodeticBoolean(double,MGL_COMBINE_MODE,C1DGeometry *,C1DGeometry *)

- ea: `0x10040abd0`
- end: `0x10040acc6`
- name: `??0CGeodeticBoolean@@QEAA@NW4MGL_COMBINE_MODE@@PEAVC1DGeometry@@1@Z`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100416de0`
- `0x100418d90`

## callees

- `0x100409aa0`
- `0x10040a580`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGeodeticBoolean::CGeodeticBoolean(__int64 a1, double a2, int a3, __int64 a4, __int64 a5)
{
  struct IMglGeometrySink *v8; // rax
  struct IMglGeometrySink *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx

  CGeodeticScannerConstruction::CGeodeticScannerConstruction((CGeodeticScannerConstruction *)a1, a2);
  *(_QWORD *)a1 = &CGeodeticBoolean::`vftable';
  *(_DWORD *)(a1 + 1136) = a3;
  v8 = (struct IMglGeometrySink *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 648) + 112LL))(*(_QWORD *)(a1 + 648));
  CProjectionBoolean::CProjectionBoolean(a1 + 1144, v8, a3);
  v9 = (struct IMglGeometrySink *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 656) + 112LL))(*(_QWORD *)(a1 + 656));
  CProjectionBoolean::CProjectionBoolean(a1 + 1968, v9, *(_DWORD *)(a1 + 1136));
  *(_QWORD *)(a1 + 2792) = a5;
  *(_QWORD *)(a1 + 736) = a1 + 1144;
  v10 = *(_QWORD *)(a1 + 1152);
  *(_QWORD *)(a1 + 752) = v10;
  *(_QWORD *)(*(_QWORD *)(a1 + 648) + 24LL) = v10;
  *(_QWORD *)(a1 + 744) = a1 + 1968;
  v11 = *(_QWORD *)(a1 + 1976);
  *(_QWORD *)(a1 + 760) = v11;
  *(_QWORD *)(*(_QWORD *)(a1 + 656) + 24LL) = v11;
  *(_QWORD *)(a1 + 560) = a4;
  return a1;
}

```

## disassembly

```asm
0x10040abd0  mov     [rsp+arg_0], rcx
0x10040abd5  push    rdi
0x10040abd6  sub     rsp, 30h
0x10040abda  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10040abe3  mov     [rsp+38h+arg_8], rbx
0x10040abe8  mov     [rsp+38h+arg_10], rbp
0x10040abed  mov     [rsp+38h+arg_18], rsi
0x10040abf2  mov     rbp, r9
0x10040abf5  mov     ebx, r8d
0x10040abf8  mov     rsi, rcx
0x10040abfb  call    ??0CGeodeticScannerConstruction@@QEAA@N@Z; CGeodeticScannerConstruction::CGeodeticScannerConstruction(double)
0x10040ac00  nop
0x10040ac01  lea     rax, ??_7CGeodeticBoolean@@6B@; const CGeodeticBoolean::`vftable'
0x10040ac08  mov     [rsi], rax
0x10040ac0b  mov     [rsi+470h], ebx
0x10040ac11  mov     rcx, [rsi+288h]
0x10040ac18  lea     rdi, [rsi+478h]
0x10040ac1f  mov     rax, [rcx]
0x10040ac22  call    qword ptr [rax+70h]
0x10040ac25  mov     rdx, rax
0x10040ac28  mov     r8d, ebx
0x10040ac2b  mov     rcx, rdi
0x10040ac2e  call    ??0CProjectionBoolean@@QEAA@PEAUIMglGeometrySink@@W4MGL_COMBINE_MODE@@@Z; CProjectionBoolean::CProjectionBoolean(IMglGeometrySink *,MGL_COMBINE_MODE)
0x10040ac33  nop
0x10040ac34  mov     rcx, [rsi+290h]
0x10040ac3b  lea     rbx, [rsi+7B0h]
0x10040ac42  mov     rax, [rcx]
0x10040ac45  call    qword ptr [rax+70h]
0x10040ac48  mov     rdx, rax
0x10040ac4b  mov     r8d, [rsi+470h]
0x10040ac52  mov     rcx, rbx
0x10040ac55  call    ??0CProjectionBoolean@@QEAA@PEAUIMglGeometrySink@@W4MGL_COMBINE_MODE@@@Z; CProjectionBoolean::CProjectionBoolean(IMglGeometrySink *,MGL_COMBINE_MODE)
0x10040ac5a  nop
0x10040ac5b  mov     rax, [rsp+38h+arg_20]
0x10040ac60  mov     [rsi+0AE8h], rax
0x10040ac67  mov     [rsi+2E0h], rdi
0x10040ac6e  mov     rcx, [rsi+480h]
0x10040ac75  mov     [rsi+2F0h], rcx
0x10040ac7c  mov     rax, [rsi+288h]
0x10040ac83  mov     [rax+18h], rcx
0x10040ac87  mov     [rsi+2E8h], rbx
0x10040ac8e  mov     rcx, [rsi+7B8h]
0x10040ac95  mov     [rsi+2F8h], rcx
0x10040ac9c  mov     rax, [rsi+290h]
0x10040aca3  mov     [rax+18h], rcx
0x10040aca7  mov     [rsi+230h], rbp
0x10040acae  mov     rax, rsi
0x10040acb1  mov     rbx, [rsp+38h+arg_8]
0x10040acb6  mov     rbp, [rsp+38h+arg_10]
0x10040acbb  mov     rsi, [rsp+38h+arg_18]
0x10040acc0  add     rsp, 30h
0x10040acc4  pop     rdi
0x10040acc5  retn
```

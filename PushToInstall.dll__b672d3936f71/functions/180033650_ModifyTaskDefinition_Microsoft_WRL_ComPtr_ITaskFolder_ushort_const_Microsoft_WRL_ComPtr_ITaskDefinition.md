# ModifyTaskDefinition(Microsoft::WRL::ComPtr<ITaskFolder>,ushort const *,Microsoft::WRL::ComPtr<ITaskDefinition>)

- ea: `0x180033650`
- end: `0x1800337e0`
- name: `?ModifyTaskDefinition@@YAXV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@PEBGV?$ComPtr@UITaskDefinition@@@23@@Z`
- size: `400`
- prototype: `HRESULT __fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800338b4`
- `0x180033af0`

## callees

- `0x18002008c`
- `0x180022810`
- `0x180033650`
- `0x18004f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003369c`
- `OLEAUT32!__imp_SysAllocString` at `0x18003369c`
- `OLEAUT32!__imp_VariantInit` at `0x18003367a`
- `OLEAUT32!__imp_VariantInit` at `0x180033685`
- `OLEAUT32!__imp_VariantInit` at `0x18003367a`
- `OLEAUT32!__imp_VariantInit` at `0x180033685`
- `OLEAUT32!__imp_VariantClear` at `0x18003375c`
- `OLEAUT32!__imp_VariantClear` at `0x180033767`
- `OLEAUT32!__imp_VariantClear` at `0x18003375c`
- `OLEAUT32!__imp_VariantClear` at `0x180033767`

## string_xrefs

- `0x1800337bc`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x1800337ce`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall ModifyTaskDefinition(__int64 *a1, __int64 a2, _QWORD *a3)
{
  const char *v6; // r9
  __int64 v7; // rcx
  int v8; // eax
  HRESULT result; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  VARIANTARG v12; // [rsp+58h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-31h] BYREF
  VARIANTARG v14; // [rsp+88h] [rbp-19h]
  VARIANTARG v15; // [rsp+A8h] [rbp+7h]
  VARIANTARG v16[2]; // [rsp+C8h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  VariantInit(&pvarg);
  VariantInit(&v12);
  v12.vt = 8;
  v12.llVal = (LONGLONG)SysAllocString(L"D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;GRGX;;;SU)");
  if ( !v12.llVal )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      v6);
  v7 = *a1;
  v14 = v12;
  v15 = pvarg;
  v16[0] = pvarg;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v7 + 136LL))(v7, a2, *a3, 4);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)(unsigned int)v8,
      (int)v16);
  VariantClear(&v12);
  result = VariantClear(&pvarg);
  v10 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = *a3;
  if ( *a3 )
  {
    *a3 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return result;
}

```

## disassembly

```asm
0x180033650  mov     rax, rsp
0x180033653  mov     [rax+10h], rbx
0x180033657  mov     [rax+18h], r8
0x18003365b  mov     [rax+8], rcx
0x18003365f  push    rbp
0x180033660  push    rsi
0x180033661  push    rdi
0x180033662  lea     rbp, [rax-5Fh]
0x180033666  sub     rsp, 0E0h
0x18003366d  mov     rbx, r8
0x180033670  mov     rsi, rdx
0x180033673  mov     rdi, rcx
0x180033676  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003367a  call    cs:__imp_VariantInit
0x180033680  nop
0x180033681  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180033685  call    cs:__imp_VariantInit
0x18003368b  nop
0x18003368c  mov     eax, 8
0x180033691  mov     word ptr [rbp+57h+var_A0], ax
0x180033695  lea     rcx, aDPAFaSyAFaBaAG; "D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;GRGX;;;S"...
0x18003369c  call    cs:__imp_SysAllocString
0x1800336a2  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1800336a6  mov     rcx, [rbp+5Fh]; this
0x1800336aa  test    rax, rax
0x1800336ad  jz      loc_1800337CE
0x1800336b3  mov     [rbp+57h+arg_18], 0
0x1800336bb  mov     rcx, [rdi]
0x1800336be  movups  xmm3, xmmword ptr [rbp+57h+pvarg]
0x1800336c2  movsd   xmm2, qword ptr [rbp+57h+pvarg+10h]
0x1800336c7  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x1800336cb  movaps  [rbp+57h+var_70], xmm0
0x1800336cf  movsd   xmm1, qword ptr [rbp+57h+var_A0+10h]
0x1800336d4  movsd   [rbp+57h+var_60], xmm1
0x1800336d9  movaps  [rbp+57h+var_50], xmm3
0x1800336dd  movsd   [rbp+57h+var_40], xmm2
0x1800336e2  movaps  xmmword ptr [rbp+57h+var_30], xmm3
0x1800336e6  movsd   [rbp+57h+var_20], xmm2
0x1800336eb  mov     rax, [rcx]
0x1800336ee  lea     rdx, [rbp+57h+arg_18]
0x1800336f2  mov     [rsp+40h], rdx
0x1800336f7  lea     rdx, [rbp+57h+var_70]
0x1800336fb  mov     [rsp+0F0h+var_B8], rdx
0x180033700  mov     dword ptr [rsp+0F0h+var_C0], 5
0x180033708  lea     rdx, [rbp+57h+var_50]
0x18003370c  mov     qword ptr [rsp+0F0h+var_C8], rdx
0x180033711  lea     rdx, [rbp+57h+var_30]
0x180033715  mov     qword ptr [rsp+0F0h+var_D0], rdx; int
0x18003371a  mov     r9d, 4
0x180033720  mov     r8, [rbx]
0x180033723  mov     rdx, rsi
0x180033726  mov     rax, [rax+88h]
0x18003372d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033732  mov     rcx, [rbp+5Fh]; this
0x180033736  test    eax, eax
0x180033738  js      short loc_1800337B9
0x18003373a  mov     rcx, [rbp+57h+arg_18]
0x18003373e  test    rcx, rcx
0x180033741  jz      short loc_180033758
0x180033743  mov     [rbp+57h+arg_18], 0
0x18003374b  mov     rax, [rcx]
0x18003374e  mov     rax, [rax+10h]
0x180033752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033757  nop
0x180033758  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18003375c  call    cs:__imp_VariantClear
0x180033762  nop
0x180033763  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180033767  call    cs:__imp_VariantClear
0x18003376d  nop
0x18003376e  mov     rcx, [rdi]
0x180033771  test    rcx, rcx
0x180033774  jz      short loc_18003378A
0x180033776  mov     qword ptr [rdi], 0
0x18003377d  mov     rax, [rcx]
0x180033780  mov     rax, [rax+10h]
0x180033784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033789  nop
0x18003378a  mov     rcx, [rbx]
0x18003378d  test    rcx, rcx
0x180033790  jz      short loc_1800337A6
0x180033792  mov     qword ptr [rbx], 0
0x180033799  mov     rax, [rcx]
0x18003379c  mov     rax, [rax+10h]
0x1800337a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337a5  nop
0x1800337a6  mov     rbx, [rsp+0F0h+arg_8]
0x1800337ae  add     rsp, 0E0h
0x1800337b5  pop     rdi
0x1800337b6  pop     rsi
0x1800337b7  pop     rbp
0x1800337b8  retn
0x1800337b9  mov     r9d, eax; char *
0x1800337bc  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800337c3  mov     edx, 51h ; 'Q'; void *
0x1800337c8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800337ce  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800337d5  mov     edx, 4Eh ; 'N'; void *
0x1800337da  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```

# CAccumulator<CSimpleCheckerModuleD,CIsSimpleResult,CBoundsSettings<CSimpleCheckerModuleD>>::Reset(void)

- ea: `0x100420250`
- end: `0x100420378`
- name: `?Reset@?$CAccumulator@VCSimpleCheckerModuleD@@VCIsSimpleResult@@U?$CBoundsSettings@VCSimpleCheckerModuleD@@@@@@IEAAJXZ`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x100414770`
- `0x10041dc00`

## callees

- `0x1004030e0`
- `0x100420250`
- `0x100432b80`
- `0x100441de0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004202b6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004202b6`

## string_xrefs

- `0x1004202a0`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAccumulator<CSimpleCheckerModuleD,CIsSimpleResult,CBoundsSettings<CSimpleCheckerModuleD>>::Reset(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  double *v3; // rax
  double *v4; // rdi
  CScanner *v5; // rbx
  _QWORD *v6; // rcx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 24);
  if ( v2 )
    (**v2)(v2, 1);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  if ( g_SOSHost )
    v3 = (double *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, __int64))(*g_SOSMemObj + 120LL))(
                     g_SOSMemObj,
                     768,
                     "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                     26,
                     -2);
  else
    v3 = (double *)malloc(0x300u);
  v4 = v3;
  if ( v3 )
  {
    v5 = (CScanner *)(v3 + 30);
    CFlatteningScannerModule::CFlatteningScannerModule((CFlatteningScannerModule *)v3, (struct CScanner *)(v3 + 30));
    *v6 = &CSimpleCheckerModuleD::`vftable';
    CScanner::CScanner(v5, 0, 0);
    *(_QWORD *)v5 = &CSimpleChecker::`vftable';
    *((_BYTE *)v5 + 520) = 1;
  }
  else
  {
    v4 = 0;
  }
  *(_QWORD *)(a1 + 24) = v4;
  if ( !v4 )
    return 2147942414LL;
  if ( (int)CWorkspaceTransform::SetWithScaleFactor(v4 + 1, a1 + 32) >= 0 )
    v4[26] = fmin(v4[11], v4[12]);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 24) + 192LL;
  return 0;
}

```

## disassembly

```asm
0x100420250  push    rdi
0x100420252  sub     rsp, 30h
0x100420256  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10042025f  mov     [rsp+38h+arg_10], rbx
0x100420264  mov     [rsp+38h+arg_18], rsi
0x100420269  mov     rsi, rcx
0x10042026c  mov     rcx, [rcx+18h]
0x100420270  test    rcx, rcx
0x100420273  jz      short loc_10042027F
0x100420275  mov     rax, [rcx]
0x100420278  mov     edx, 1
0x10042027d  call    qword ptr [rax]
0x10042027f  xor     ebx, ebx
0x100420281  mov     [rsi+18h], rbx
0x100420285  mov     [rsi+10h], rbx
0x100420289  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rbx; SOS_AutoHost g_SOSHost
0x100420290  jz      short loc_1004202B1
0x100420292  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100420299  mov     rax, [rcx]
0x10042029c  lea     r9d, [rbx+1Ah]
0x1004202a0  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004202a7  mov     edx, 300h
0x1004202ac  call    qword ptr [rax+78h]
0x1004202af  jmp     short loc_1004202BC
0x1004202b1  mov     ecx, 300h; Size
0x1004202b6  call    cs:__imp_malloc
0x1004202bc  mov     rdi, rax
0x1004202bf  mov     [rsp+38h+arg_0], rax
0x1004202c4  test    rax, rax
0x1004202c7  jz      short loc_10042030C
0x1004202c9  lea     rbx, [rax+0F0h]
0x1004202d0  mov     rdx, rbx; struct CScanner *
0x1004202d3  mov     rcx, rax; this
0x1004202d6  call    ??0CFlatteningScannerModule@@QEAA@AEAVCScanner@@@Z; CFlatteningScannerModule::CFlatteningScannerModule(CScanner &)
0x1004202db  nop
0x1004202dc  lea     rax, ??_7CSimpleCheckerModuleD@@6B@; const CSimpleCheckerModuleD::`vftable'
0x1004202e3  mov     [rcx], rax
0x1004202e6  mov     [rsp+38h+arg_8], rbx
0x1004202eb  xor     r8d, r8d; bool
0x1004202ee  xor     edx, edx; bool
0x1004202f0  mov     rcx, rbx; this
0x1004202f3  call    ??0CScanner@@QEAA@_N0@Z; CScanner::CScanner(bool,bool)
0x1004202f8  nop
0x1004202f9  lea     rax, ??_7CSimpleChecker@@6B@; const CSimpleChecker::`vftable'
0x100420300  mov     [rbx], rax
0x100420303  mov     byte ptr [rbx+208h], 1
0x10042030a  jmp     short loc_10042030F
0x10042030c  mov     rdi, rbx
0x10042030f  mov     [rsi+18h], rdi
0x100420313  test    rdi, rdi
0x100420316  jnz     short loc_10042032D
0x100420318  mov     eax, 8007000Eh
0x10042031d  mov     rbx, [rsp+38h+arg_10]
0x100420322  mov     rsi, [rsp+38h+arg_18]
0x100420327  add     rsp, 30h
0x10042032b  pop     rdi
0x10042032c  retn
0x10042032d  lea     rdx, [rsi+20h]
0x100420331  lea     rcx, [rdi+8]
0x100420335  movsd   xmm2, cs:__real@3ff0000000000000
0x10042033d  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x100420342  test    eax, eax
0x100420344  js      short loc_100420358
0x100420346  movsd   xmm0, qword ptr [rdi+58h]
0x10042034b  minsd   xmm0, qword ptr [rdi+60h]
0x100420350  movsd   qword ptr [rdi+0D0h], xmm0
0x100420358  mov     rax, [rsi+18h]
0x10042035c  add     rax, 0C0h
0x100420362  mov     [rsi+10h], rax
0x100420366  xor     eax, eax
0x100420368  mov     rbx, [rsp+38h+arg_10]
0x10042036d  mov     rsi, [rsp+38h+arg_18]
0x100420372  add     rsp, 30h
0x100420376  pop     rdi
0x100420377  retn
```

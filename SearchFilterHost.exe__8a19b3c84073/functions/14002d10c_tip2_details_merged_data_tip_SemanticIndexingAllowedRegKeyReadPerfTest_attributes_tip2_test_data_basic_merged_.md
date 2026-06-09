# tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>(void)

- ea: `0x14002d10c`
- end: `0x14002d1f5`
- name: `??0?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ`
- size: `233`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002fd70`

## callees

- `0x14000df7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14002d183`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14002d183`

## string_xrefs

- `0x14002d123`: `SemanticIndexingAllowedRegKeyReadPerfTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>(
        __int64 a1)
{
  int v2; // r10d
  __int64 v3; // r9
  __int64 result; // rax

  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  *(_QWORD *)(a1 + 8) = a1;
  tip2::test_state::test_state((tip2::test_state *)(a1 + 16));
  *(_DWORD *)(a1 + 192) = 0;
  *(_DWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_DWORD *)(a1 + 42) = v2;
  *(_WORD *)(a1 + 46) = v2;
  *(_DWORD *)(a1 + 24) = 49605212;
  *(_DWORD *)(a1 + 28) = 180480;
  *(_QWORD *)(a1 + 32) = v3;
  *(_WORD *)(a1 + 40) = 1;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 304) = 0;
  *(_QWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 328) = 0;
  *(_QWORD *)a1 = &tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::`vftable';
  *(_QWORD *)(a1 + 256) = a1 + 16;
  result = a1;
  *(_DWORD *)(a1 + 336) = 1;
  return result;
}

```

## disassembly

```asm
0x14002d10c  mov     [rsp+arg_0], rbx
0x14002d111  push    rdi
0x14002d112  sub     rsp, 20h
0x14002d116  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x14002d11d  mov     rbx, rcx
0x14002d120  mov     [rcx], rax
0x14002d123  lea     r9, aSemanticindexi; "SemanticIndexingAllowedRegKeyReadPerfTe"...
0x14002d12a  mov     [rcx+8], rcx
0x14002d12e  xor     edi, edi
0x14002d130  add     rcx, 10h; this
0x14002d134  xor     r10d, r10d
0x14002d137  call    ??0test_state@tip2@@QEAA@XZ; tip2::test_state::test_state(void)
0x14002d13c  mov     [rbx+0C0h], edi
0x14002d142  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14002d149  mov     [rbx+0F0h], edi
0x14002d14f  mov     [rbx+0F8h], rdi
0x14002d156  mov     [rbx+2Ah], r10d
0x14002d15a  mov     [rbx+2Eh], r10w
0x14002d15f  mov     dword ptr [rbx+18h], 2F4EA5Ch
0x14002d166  mov     dword ptr [rbx+1Ch], 2C100h
0x14002d16d  mov     [rbx+20h], r9
0x14002d171  mov     word ptr [rbx+28h], 1
0x14002d177  mov     [rbx+30h], rdi
0x14002d17b  mov     [rbx+38h], rdi
0x14002d17f  mov     [rbx+40h], rdi
0x14002d183  call    cs:__imp_InitializeCriticalSection
0x14002d189  mov     [rbx+108h], rdi
0x14002d190  lea     rax, ??_7?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::`vftable'
0x14002d197  mov     [rbx+110h], rdi
0x14002d19e  mov     [rbx+118h], rdi
0x14002d1a5  mov     [rbx+120h], rdi
0x14002d1ac  mov     [rbx+128h], rdi
0x14002d1b3  mov     [rbx+130h], rdi
0x14002d1ba  mov     [rbx+138h], rdi
0x14002d1c1  mov     [rbx+140h], rdi
0x14002d1c8  mov     [rbx+148h], rdi
0x14002d1cf  mov     [rbx], rax
0x14002d1d2  lea     rax, [rbx+10h]
0x14002d1d6  mov     [rbx+100h], rax
0x14002d1dd  mov     rax, rbx
0x14002d1e0  mov     dword ptr [rbx+150h], 1
0x14002d1ea  mov     rbx, [rsp+28h+arg_0]
0x14002d1ef  add     rsp, 20h
0x14002d1f3  pop     rdi
0x14002d1f4  retn
```

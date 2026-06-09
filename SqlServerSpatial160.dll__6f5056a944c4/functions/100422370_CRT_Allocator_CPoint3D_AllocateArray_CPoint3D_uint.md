# CRT_Allocator<CPoint3D>::AllocateArray(CPoint3D * *,uint)

- ea: `0x100422370`
- end: `0x1004223f0`
- name: `?AllocateArray@?$CRT_Allocator@VCPoint3D@@@@SAJPEAPEAVCPoint3D@@I@Z`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100429c60`
- `0x100461890`

## callees

- `0x100422370`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004223cc`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004223cc`

## string_xrefs

- `0x1004223ba`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRT_Allocator<CPoint3D>::AllocateArray(_QWORD *a1, unsigned int a2)
{
  size_t v3; // r10
  void *v4; // rax
  void *v5; // rcx
  __int64 result; // rax

  v3 = 24LL * a2;
  if ( !is_mul_ok(a2, 0x18u) )
    v3 = -1;
  if ( g_SOSHost )
    v4 = (void *)(*(__int64 (__fastcall **)(_QWORD, size_t, const char *, __int64, __int64))(*g_SOSMemObj + 120LL))(
                   g_SOSMemObj,
                   v3,
                   "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                   26,
                   -2);
  else
    v4 = malloc(v3);
  v5 = v4;
  *a1 = v4;
  result = 2147942414LL;
  if ( v5 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x100422370  push    rbx
0x100422372  sub     rsp, 30h
0x100422376  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10042237f  mov     rbx, rcx
0x100422382  mov     r8d, edx
0x100422385  mov     [rsp+38h+arg_0], r8
0x10042238a  mov     eax, 18h
0x10042238f  mul     r8
0x100422392  mov     r10, rax
0x100422395  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10042239c  cmovo   r10, rax
0x1004223a0  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x1004223a8  jz      short loc_1004223C9
0x1004223aa  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004223b1  mov     rax, [rcx]
0x1004223b4  mov     r9d, 1Ah
0x1004223ba  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004223c1  mov     rdx, r10
0x1004223c4  call    qword ptr [rax+78h]
0x1004223c7  jmp     short loc_1004223D2
0x1004223c9  mov     rcx, r10; Size
0x1004223cc  call    cs:__imp_malloc
0x1004223d2  mov     rcx, rax
0x1004223d5  mov     [rsp+38h+arg_10], rax
0x1004223da  mov     [rbx], rax
0x1004223dd  mov     eax, 8007000Eh
0x1004223e2  xor     edx, edx
0x1004223e4  test    rcx, rcx
0x1004223e7  cmovnz  eax, edx
0x1004223ea  add     rsp, 30h
0x1004223ee  pop     rbx
0x1004223ef  retn
```

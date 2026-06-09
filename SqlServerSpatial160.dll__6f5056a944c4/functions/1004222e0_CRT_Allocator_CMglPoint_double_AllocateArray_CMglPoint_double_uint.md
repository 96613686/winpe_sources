# CRT_Allocator<CMglPoint<double>>::AllocateArray(CMglPoint<double> * *,uint)

- ea: `0x1004222e0`
- end: `0x100422360`
- name: `?AllocateArray@?$CRT_Allocator@V?$CMglPoint@N@@@@SAJPEAPEAV?$CMglPoint@N@@I@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100439310`

## callees

- `0x1004222e0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042233c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10042233c`

## string_xrefs

- `0x10042232a`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRT_Allocator<CMglPoint<double>>::AllocateArray(_QWORD *a1, unsigned int a2)
{
  size_t v3; // r10
  void *v4; // rax
  void *v5; // rcx
  __int64 result; // rax

  v3 = 16LL * a2;
  if ( !is_mul_ok(a2, 0x10u) )
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
0x1004222e0  push    rbx
0x1004222e2  sub     rsp, 30h
0x1004222e6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004222ef  mov     rbx, rcx
0x1004222f2  mov     r8d, edx
0x1004222f5  mov     [rsp+38h+arg_0], r8
0x1004222fa  mov     eax, 10h
0x1004222ff  mul     r8
0x100422302  mov     r10, rax
0x100422305  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10042230c  cmovo   r10, rax
0x100422310  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100422318  jz      short loc_100422339
0x10042231a  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100422321  mov     rax, [rcx]
0x100422324  mov     r9d, 1Ah
0x10042232a  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100422331  mov     rdx, r10
0x100422334  call    qword ptr [rax+78h]
0x100422337  jmp     short loc_100422342
0x100422339  mov     rcx, r10; Size
0x10042233c  call    cs:__imp_malloc
0x100422342  mov     rcx, rax
0x100422345  mov     [rsp+38h+arg_10], rax
0x10042234a  mov     [rbx], rax
0x10042234d  mov     eax, 8007000Eh
0x100422352  xor     edx, edx
0x100422354  test    rcx, rcx
0x100422357  cmovnz  eax, edx
0x10042235a  add     rsp, 30h
0x10042235e  pop     rbx
0x10042235f  retn
```

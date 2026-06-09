# CommonUtil::UtilRegAdjustValue(ulong,unsigned __int64,void *,unsigned __int64 *)

- ea: `0x1400024e8`
- end: `0x14000253a`
- name: `?UtilRegAdjustValue@CommonUtil@@YAJK_KPEAXPEA_K@Z`
- size: `82`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int, unsigned __int64, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005050`

## callees

- `0x140002d42`
- `0x140024c40`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegAdjustValue(CommonUtil *this, __int64 a2, __int64 a3, void *a4)
{
  unsigned int v7; // ebp
  __int64 v8; // rax

  v7 = (unsigned int)this;
  v8 = MpUtilsExportFunctions_0(this, a2);
  return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, void *))(v8 + 256))(v7, a2, a3, a4);
}

```

## disassembly

```asm
0x1400024e8  mov     [rsp+arg_0], rbx
0x1400024ed  mov     [rsp+arg_8], rbp
0x1400024f2  mov     [rsp+arg_10], rsi
0x1400024f7  push    rdi
0x1400024f8  sub     rsp, 30h
0x1400024fc  mov     rbx, r9
0x1400024ff  mov     rdi, r8
0x140002502  mov     rsi, rdx
0x140002505  mov     ebp, ecx
0x140002507  call    MpUtilsExportFunctions_0
0x14000250c  mov     r9, rbx
0x14000250f  mov     r8, rdi
0x140002512  mov     rdx, rsi
0x140002515  mov     ecx, ebp
0x140002517  mov     rax, [rax+100h]
0x14000251e  call    cs:__guard_dispatch_icall_fptr
0x140002524  nop
0x140002525  mov     rbx, [rsp+38h+arg_0]
0x14000252a  mov     rbp, [rsp+38h+arg_8]
0x14000252f  mov     rsi, [rsp+38h+arg_10]
0x140002534  add     rsp, 30h
0x140002538  pop     rdi
0x140002539  retn
```

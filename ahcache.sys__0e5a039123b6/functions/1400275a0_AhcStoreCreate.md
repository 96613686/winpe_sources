# AhcStoreCreate

- ea: `0x1400275a0`
- end: `0x140027697`
- name: `AhcStoreCreate`
- size: `247`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400279dc`
- `0x140029020`

## callees

- `0x1400275a0`
- `0x14003e364`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14002766f`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14002766f`

## string_xrefs

- `0x1400275dc`: `AhcStoreCreate`

## pseudocode

```c
__int64 __fastcall AhcStoreCreate(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v12; // rbx
  __int64 result; // rax
  __int64 v14; // rax

  v12 = AslAlloc(a1, 176, 1);
  if ( v12 )
  {
    v14 = -1;
    if ( a2 )
      v14 = a2;
    *(_QWORD *)(v12 + 120) = v14;
    *(_QWORD *)(v12 + 144) = a5;
    *(_QWORD *)(v12 + 152) = a6;
    *(_QWORD *)(v12 + 160) = a7;
    *(_QWORD *)(v12 + 168) = a8;
    *(_QWORD *)(v12 + 128) = a3;
    *(_QWORD *)(v12 + 136) = a4;
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)v12,
      (PRTL_AVL_COMPARE_ROUTINE)AhcpAVLTableCompare,
      AhcpAVLTableAllocate,
      AhcpAVLTableFree,
      0);
    *(_QWORD *)(v12 + 112) = v12 + 104;
    *(_QWORD *)(v12 + 104) = v12 + 104;
    result = 0;
    *a1 = v12;
  }
  else
  {
    AslLogCallPrintf(1, "AhcStoreCreate", 495, "Failed to allocate memory for creating AVL store");
    return 3221225495LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400275a0  push    rbx
0x1400275a2  push    rbp
0x1400275a3  push    rsi
0x1400275a4  push    rdi
0x1400275a5  push    r14
0x1400275a7  sub     rsp, 30h
0x1400275ab  mov     rbp, r8
0x1400275ae  mov     rdi, rdx
0x1400275b1  mov     edx, 0B0h
0x1400275b6  mov     r8d, 1
0x1400275bc  mov     rsi, r9
0x1400275bf  mov     r14, rcx
0x1400275c2  call    AslAlloc
0x1400275c7  mov     rbx, rax
0x1400275ca  test    rax, rax
0x1400275cd  jnz     short loc_1400275F5
0x1400275cf  lea     r9, aFailedToAlloca_18; "Failed to allocate memory for creating "...
0x1400275d6  mov     r8d, 1EFh
0x1400275dc  lea     rdx, aAhcstorecreate; "AhcStoreCreate"
0x1400275e3  lea     ecx, [rax+1]
0x1400275e6  call    AslLogCallPrintf
0x1400275eb  mov     eax, 0C0000017h
0x1400275f0  jmp     loc_14002768B
0x1400275f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400275f9  mov     [rsp+58h+TableContext], 0; TableContext
0x140027602  test    rdi, rdi
0x140027605  lea     r9, AhcpAVLTableFree; FreeRoutine
0x14002760c  lea     r8, AhcpAVLTableAllocate; AllocateRoutine
0x140027613  mov     rcx, rbx; Table
0x140027616  cmovnz  rax, rdi
0x14002761a  lea     rdx, AhcpAVLTableCompare; CompareRoutine
0x140027621  mov     [rbx+78h], rax
0x140027625  mov     rax, [rsp+58h+arg_20]
0x14002762d  mov     [rbx+90h], rax
0x140027634  mov     rax, [rsp+58h+arg_28]
0x14002763c  mov     [rbx+98h], rax
0x140027643  mov     rax, [rsp+58h+arg_30]
0x14002764b  mov     [rbx+0A0h], rax
0x140027652  mov     rax, [rsp+58h+arg_38]
0x14002765a  mov     [rbx+0A8h], rax
0x140027661  mov     [rbx+80h], rbp
0x140027668  mov     [rbx+88h], rsi
0x14002766f  call    cs:__imp_RtlInitializeGenericTableAvl
0x140027676  nop     dword ptr [rax+rax+00h]
0x14002767b  lea     rax, [rbx+68h]
0x14002767f  mov     [rax+8], rax
0x140027683  mov     [rax], rax
0x140027686  xor     eax, eax
0x140027688  mov     [r14], rbx
0x14002768b  add     rsp, 30h
0x14002768f  pop     r14
0x140027691  pop     rdi
0x140027692  pop     rsi
0x140027693  pop     rbp
0x140027694  pop     rbx
0x140027695  retn
```

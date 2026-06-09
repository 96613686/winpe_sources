# __tailMerge_ext_ms_win_resourcemanager_crm_private_ext_l1_1_0_dll

- ea: `0x18001464d`
- end: `0x1800146c6`
- name: `__tailMerge_ext_ms_win_resourcemanager_crm_private_ext_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800146cc`
- `0x1800146de`
- `0x1800146f0`
- `0x180014702`
- `0x180014714`
- `0x180014726`
- `0x180014738`

## callees

- `0x18000f260`
- `0x18001464d`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_resourcemanager_crm_private_ext_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resourcemanager_crm_private_ext_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001464d  mov     [rsp+arg_0], rcx
0x180014652  mov     [rsp+arg_8], rdx
0x180014657  mov     [rsp+arg_10], r8
0x18001465c  mov     [rsp+arg_18], r9
0x180014661  sub     rsp, 68h
0x180014665  movdqa  [rsp+68h+var_48], xmm0
0x18001466b  movdqa  [rsp+68h+var_38], xmm1
0x180014671  movdqa  [rsp+68h+var_28], xmm2
0x180014677  movdqa  [rsp+68h+var_18], xmm3
0x18001467d  mov     rdx, rax
0x180014680  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resourcemanager_crm_private_ext_l1_1_0_dll
0x180014687  call    __delayLoadHelper2
0x18001468c  movdqa  xmm0, [rsp+68h+var_48]
0x180014692  movdqa  xmm1, [rsp+68h+var_38]
0x180014698  movdqa  xmm2, [rsp+68h+var_28]
0x18001469e  movdqa  xmm3, [rsp+68h+var_18]
0x1800146a4  mov     rcx, [rsp+68h+arg_0]
0x1800146a9  mov     rdx, [rsp+68h+arg_8]
0x1800146ae  mov     r8, [rsp+68h+arg_10]
0x1800146b6  mov     r9, [rsp+68h+arg_18]
0x1800146be  add     rsp, 68h
0x1800146c2  jmp     short $+2
0x1800146c4  jmp     rax
```

# ??1?$unique_struct@U?$co_array_t@U_MVProvisionData@@@@P6AXPEAU1@@_E$1?FreeProvisionDataArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ

- ea: `0x180008f38`
- end: `0x180008f7c`
- name: `??1?$unique_struct@U?$co_array_t@U_MVProvisionData@@@@P6AXPEAU1@@_E$1?FreeProvisionDataArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800118dc`

## callees

- `0x180008f38`
- `0x180009354`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f64`

## pseudocode

```c
void __fastcall __1__unique_struct_U__co_array_t_U_MVProvisionData____P6AXPEAU1___E_1_FreeProvisionDataArray__YAX0_Z__T_0A__wil__QEAA_XZ(
        __int64 a1)
{
  unsigned int i; // edi

  for ( i = 0; i < *(_DWORD *)(a1 + 8); ++i )
    FreeProvisionData((struct _MVProvisionData *)(*(_QWORD *)a1 + 104LL * i));
  CoTaskMemFree(*(LPVOID *)a1);
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180008f38  mov     [rsp+arg_0], rbx
0x180008f3d  push    rdi
0x180008f3e  sub     rsp, 20h
0x180008f42  xor     edi, edi
0x180008f44  mov     rbx, rcx
0x180008f47  cmp     [rcx+8], edi
0x180008f4a  jbe     short loc_180008F61
0x180008f4c  mov     eax, edi
0x180008f4e  imul    rcx, rax, 68h ; 'h'
0x180008f52  add     rcx, [rbx]; struct _MVProvisionData *
0x180008f55  call    ?FreeProvisionData@@YAXPEAU_MVProvisionData@@@Z; FreeProvisionData(_MVProvisionData *)
0x180008f5a  inc     edi
0x180008f5c  cmp     edi, [rbx+8]
0x180008f5f  jb      short loc_180008F4C
0x180008f61  mov     rcx, [rbx]; pv
0x180008f64  call    cs:__imp_CoTaskMemFree
0x180008f6a  mov     qword ptr [rbx], 0
0x180008f71  mov     rbx, [rsp+28h+arg_0]
0x180008f76  add     rsp, 20h
0x180008f7a  pop     rdi
0x180008f7b  retn
```

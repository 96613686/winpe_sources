# ??1?$out_ptr_t@V?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@PEA_W$$V@utl@@QEAA@XZ

- ea: `0x14001724c`
- end: `0x140017272`
- name: `??1?$out_ptr_t@V?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@PEA_W$$V@utl@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001cea1`

## callees

- `0x14001724c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017267`

## pseudocode

```c
void __fastcall __1__out_ptr_t_V__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__PEA_W__V_utl__QEAA_XZ(
        void **a1)
{
  void *v1; // rdx
  void **v2; // rax
  void *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void **)a1[1];
    v3 = *v2;
    *v2 = v1;
    if ( v3 )
      CoTaskMemFree(v3);
  }
}

```

## disassembly

```asm
0x14001724c  sub     rsp, 28h
0x140017250  mov     rdx, [rcx]
0x140017253  test    rdx, rdx
0x140017256  jz      short loc_14001726D
0x140017258  mov     rax, [rcx+8]
0x14001725c  mov     rcx, [rax]; pv
0x14001725f  mov     [rax], rdx
0x140017262  test    rcx, rcx
0x140017265  jz      short loc_14001726D
0x140017267  call    cs:__imp_CoTaskMemFree
0x14001726d  add     rsp, 28h
0x140017271  retn
```

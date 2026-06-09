# win_dox::close_stat_free::close(tagSTATSTG * *)

- ea: `0x18004ec1c`
- end: `0x18004ec45`
- name: `?close@close_stat_free@win_dox@@SAXPEAPEAUtagSTATSTG@@@Z`
- size: `41`
- prototype: `void __fastcall(struct tagSTATSTG **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004df0c`
- `0x18004e11c`
- `0x18004e4ac`
- `0x18004ebf0`

## callees

- `0x18004ec1c`
- `0x1800cce54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec3d`

## pseudocode

```c
void __fastcall win_dox::close_stat_free::close(struct tagSTATSTG **a1)
{
  LPOLESTR pwcsName; // rcx

  pwcsName = (*a1)->pwcsName;
  if ( pwcsName )
    CoTaskMemFree(pwcsName);
  operator delete(*a1);
}

```

## disassembly

```asm
0x18004ec1c  push    rbx
0x18004ec1e  sub     rsp, 20h
0x18004ec22  mov     rax, [rcx]
0x18004ec25  mov     rbx, rcx
0x18004ec28  mov     rcx, [rax]; pv
0x18004ec2b  test    rcx, rcx
0x18004ec2e  jnz     short loc_18004EC3D
0x18004ec30  mov     rcx, [rbx]; Block
0x18004ec33  add     rsp, 20h
0x18004ec37  pop     rbx
0x18004ec38  jmp     ??3@YAXPEAX@Z; operator delete(void *)
0x18004ec3d  call    cs:__imp_CoTaskMemFree
0x18004ec43  jmp     short loc_18004EC30
```

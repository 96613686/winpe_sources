# DeleteMediaType(_AMMediaType *)

- ea: `0x180029f5c`
- end: `0x180029f84`
- name: `?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z`
- size: `40`
- prototype: `void __fastcall(struct _AMMediaType *pv)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011860`
- `0x180026394`

## callees

- `0x180029f5c`
- `0x180029f8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f71`

## pseudocode

```c
void __fastcall DeleteMediaType(struct _AMMediaType *pv)
{
  if ( pv )
  {
    FreeMediaType(pv);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180029f5c  test    rcx, rcx
0x180029f5f  jz      short locret_180029F82
0x180029f61  push    rbx
0x180029f62  sub     rsp, 20h
0x180029f66  mov     rbx, rcx
0x180029f69  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180029f6e  mov     rcx, rbx; pv
0x180029f71  call    cs:__imp_CoTaskMemFree
0x180029f78  nop     dword ptr [rax+rax+00h]
0x180029f7d  add     rsp, 20h
0x180029f81  pop     rbx
0x180029f82  retn
```

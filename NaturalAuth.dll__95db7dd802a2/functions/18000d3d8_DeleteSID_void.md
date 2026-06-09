# DeleteSID(void * *)

- ea: `0x18000d3d8`
- end: `0x18000d3fc`
- name: `?DeleteSID@@YAXPEAPEAX@Z`
- size: `36`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180013d30`
- `0x1800144b0`

## callees

- `0x18000d3d8`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18000d3e9`
- `ntdll!RtlFreeSid` at `0x18000d3e9`

## pseudocode

```c
void __fastcall DeleteSID(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    RtlFreeSid(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000d3d8  push    rbx
0x18000d3da  sub     rsp, 20h
0x18000d3de  mov     rbx, rcx
0x18000d3e1  mov     rcx, [rcx]; Sid
0x18000d3e4  test    rcx, rcx
0x18000d3e7  jz      short loc_18000D3F6
0x18000d3e9  call    cs:__imp_RtlFreeSid
0x18000d3ef  mov     qword ptr [rbx], 0
0x18000d3f6  add     rsp, 20h
0x18000d3fa  pop     rbx
0x18000d3fb  retn
```

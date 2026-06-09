# MbbCxCompleteWdfRequest(_WWAN_NDIS_OID_REQUEST *,int,unsigned __int64)

- ea: `0x14000f970`
- end: `0x14000f9af`
- name: `?MbbCxCompleteWdfRequest@@YAXPEAU_WWAN_NDIS_OID_REQUEST@@H_K@Z`
- size: `63`
- prototype: `void __fastcall(struct _WWAN_NDIS_OID_REQUEST *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f900`

## callees

- `0x1400018f0`
- `0x140047e90`

## pseudocode

```c
void __fastcall MbbCxCompleteWdfRequest(struct _MINIPORT_INTERFACE_CONTEXT **a1, unsigned int a2, __int64 a3)
{
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct _MINIPORT_INTERFACE_CONTEXT *, _QWORD, __int64))(WdfFunctions_01031 + 2120))(
    WdfDriverGlobals,
    *a1,
    a2,
    a3);
  DereferenceSession(a1[32]);
}

```

## disassembly

```asm
0x14000f970  push    rbx
0x14000f972  sub     rsp, 30h
0x14000f976  mov     rax, cs:WdfFunctions_01031
0x14000f97d  mov     r9, r8
0x14000f980  mov     r8d, edx
0x14000f983  mov     rbx, rcx
0x14000f986  mov     rdx, [rcx]
0x14000f989  mov     rcx, cs:WdfDriverGlobals
0x14000f990  mov     rax, [rax+848h]
0x14000f997  call    _guard_dispatch_icall
0x14000f99c  mov     rcx, [rbx+100h]; struct _MINIPORT_INTERFACE_CONTEXT *
0x14000f9a3  call    ?DereferenceSession@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; DereferenceSession(_MINIPORT_INTERFACE_CONTEXT *)
0x14000f9a8  add     rsp, 30h
0x14000f9ac  pop     rbx
0x14000f9ad  retn
```

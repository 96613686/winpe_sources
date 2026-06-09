# BthUsb_ScoFreeReadResources(_DEVICE_EXTENSION *)

- ea: `0x1400077c4`
- end: `0x140007899`
- name: `?BthUsb_ScoFreeReadResources@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `213`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140005180`
- `0x1400078a0`

## callees

- `0x14000175c`
- `0x1400076e8`
- `0x1400077c4`
- `0x14000dbc4`
- `0x14000de00`

## pseudocode

```c
void __fastcall BthUsb_ScoFreeReadResources(struct _DEVICE_EXTENSION *a1)
{
  int v2; // edx
  int v3; // r8d
  char v4; // bl
  int v5; // edx
  int v6; // r8d

  BthUsb_ScoFreePartialUsbCtx(a1);
  v4 = 1;
  LOBYTE(v2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v2,
    v3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    13,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  ResourceQueue_StopAndWait(&a1->Sco.ReadCtxQueue);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v5) = v4;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    v6,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    14,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  a1->Sco.ReadCtxQueue.FnDestroyItems(a1->Sco.ReadCtxQueue.ContextFn, &a1->Sco.ReadCtxQueue.ListEntry);
}

```

## disassembly

```asm
0x1400077c4  mov     [rsp+arg_0], rbx
0x1400077c9  mov     [rsp+arg_8], rbp
0x1400077ce  push    rdi
0x1400077cf  sub     rsp, 40h
0x1400077d3  mov     rdi, rcx
0x1400077d6  call    ?BthUsb_ScoFreePartialUsbCtx@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoFreePartialUsbCtx(_DEVICE_EXTENSION *)
0x1400077db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077e2  mov     bl, 1
0x1400077e4  mov     eax, [rcx+2Ch]
0x1400077e7  test    al, 8
0x1400077e9  jz      short loc_1400077F5
0x1400077eb  cmp     byte ptr [rcx+29h], 4
0x1400077ef  jb      short loc_1400077F5
0x1400077f1  mov     dl, bl
0x1400077f3  jmp     short loc_1400077F7
0x1400077f5  xor     dl, dl
0x1400077f7  mov     r9, [rcx+40h]
0x1400077fb  lea     rbp, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007802  mov     rcx, [rcx+18h]
0x140007806  mov     [rsp+48h+var_10], rbp
0x14000780b  mov     [rsp+48h+var_18], 0Dh
0x140007812  mov     [rsp+48h+var_20], 4
0x14000781a  mov     [rsp+48h+var_28], 4
0x14000781f  call    WPP_RECORDER_AND_TRACE_SF_
0x140007824  lea     rcx, [rdi+198h]
0x14000782b  call    ResourceQueue_StopAndWait
0x140007830  mov     rcx, cs:WPP_GLOBAL_Control
0x140007837  mov     eax, [rcx+2Ch]
0x14000783a  test    al, 8
0x14000783c  jz      short loc_140007844
0x14000783e  cmp     byte ptr [rcx+29h], 4
0x140007842  jnb     short loc_140007846
0x140007844  xor     bl, bl
0x140007846  mov     r9, [rcx+40h]
0x14000784a  mov     dl, bl
0x14000784c  mov     rcx, [rcx+18h]
0x140007850  mov     [rsp+48h+var_10], rbp
0x140007855  mov     [rsp+48h+var_18], 0Eh
0x14000785c  mov     [rsp+48h+var_20], 4
0x140007864  mov     [rsp+48h+var_28], 4
0x140007869  call    WPP_RECORDER_AND_TRACE_SF_
0x14000786e  mov     rax, [rdi+1E8h]
0x140007875  lea     rdx, [rdi+1A8h]
0x14000787c  mov     rcx, [rdi+1F0h]
0x140007883  call    _guard_dispatch_icall
0x140007888  mov     rbx, [rsp+48h+arg_0]
0x14000788d  mov     rbp, [rsp+48h+arg_8]
0x140007892  add     rsp, 40h
0x140007896  pop     rdi
0x140007897  retn
```

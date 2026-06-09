# BthUsb_ScoFreeWriteResources(_DEVICE_EXTENSION *)

- ea: `0x140009000`
- end: `0x1400090d0`
- name: `?BthUsb_ScoFreeWriteResources@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `208`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140005180`

## callees

- `0x14000175c`
- `0x140009000`
- `0x14000dbc4`
- `0x14000de00`

## pseudocode

```c
void __fastcall BthUsb_ScoFreeWriteResources(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
{
  char v4; // bl
  bool v5; // dl
  int v6; // r8d

  v4 = 1;
  v5 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    13,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
  ResourceQueue_StopAndWait(&a1->Sco.WriteCtxQueue);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    v6,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    14,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
  a1->Sco.WriteCtxQueue.FnDestroyItems(a1->Sco.WriteCtxQueue.ContextFn, &a1->Sco.WriteCtxQueue.ListEntry);
}

```

## disassembly

```asm
0x140009000  mov     [rsp+arg_0], rbx
0x140009005  mov     [rsp+arg_8], rbp
0x14000900a  push    rdi
0x14000900b  sub     rsp, 40h
0x14000900f  mov     rdi, rcx
0x140009012  mov     rcx, cs:WPP_GLOBAL_Control
0x140009019  mov     bl, 1
0x14000901b  mov     eax, [rcx+2Ch]
0x14000901e  test    al, 8
0x140009020  jz      short loc_14000902C
0x140009022  cmp     byte ptr [rcx+29h], 4
0x140009026  jb      short loc_14000902C
0x140009028  mov     dl, bl
0x14000902a  jmp     short loc_14000902E
0x14000902c  xor     dl, dl
0x14000902e  mov     r9, [rcx+40h]
0x140009032  lea     rbp, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x140009039  mov     rcx, [rcx+18h]
0x14000903d  mov     [rsp+48h+var_10], rbp
0x140009042  mov     [rsp+48h+var_18], 0Dh
0x140009049  mov     [rsp+48h+var_20], 4
0x140009051  mov     [rsp+48h+var_28], 4
0x140009056  call    WPP_RECORDER_AND_TRACE_SF_
0x14000905b  lea     rcx, [rdi+138h]
0x140009062  call    ResourceQueue_StopAndWait
0x140009067  mov     rcx, cs:WPP_GLOBAL_Control
0x14000906e  mov     eax, [rcx+2Ch]
0x140009071  test    al, 8
0x140009073  jz      short loc_14000907B
0x140009075  cmp     byte ptr [rcx+29h], 4
0x140009079  jnb     short loc_14000907D
0x14000907b  xor     bl, bl
0x14000907d  mov     r9, [rcx+40h]
0x140009081  mov     dl, bl
0x140009083  mov     rcx, [rcx+18h]
0x140009087  mov     [rsp+48h+var_10], rbp
0x14000908c  mov     [rsp+48h+var_18], 0Eh
0x140009093  mov     [rsp+48h+var_20], 4
0x14000909b  mov     [rsp+48h+var_28], 4
0x1400090a0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400090a5  mov     rax, [rdi+188h]
0x1400090ac  lea     rdx, [rdi+148h]
0x1400090b3  mov     rcx, [rdi+190h]
0x1400090ba  call    _guard_dispatch_icall
0x1400090bf  mov     rbx, [rsp+48h+arg_0]
0x1400090c4  mov     rbp, [rsp+48h+arg_8]
0x1400090c9  add     rsp, 40h
0x1400090cd  pop     rdi
0x1400090ce  retn
```

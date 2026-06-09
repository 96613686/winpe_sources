# BthUsb_ScoWriteStart(_DEVICE_EXTENSION *)

- ea: `0x140009740`
- end: `0x1400097f8`
- name: `?BthUsb_ScoWriteStart@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140008f40`

## callees

- `0x14000175c`
- `0x140009740`
- `0x14000db18`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoWriteStart(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
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
    15,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
  ResourceQueue_Start(&a1->Sco.WriteCtxQueue);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    v6,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    16,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140009740  mov     [rsp+arg_0], rbx
0x140009745  mov     [rsp+arg_8], rbp
0x14000974a  push    rdi
0x14000974b  sub     rsp, 40h
0x14000974f  mov     rdi, rcx
0x140009752  mov     rcx, cs:WPP_GLOBAL_Control
0x140009759  mov     bl, 1
0x14000975b  mov     eax, [rcx+2Ch]
0x14000975e  test    al, 8
0x140009760  jz      short loc_14000976C
0x140009762  cmp     byte ptr [rcx+29h], 4
0x140009766  jb      short loc_14000976C
0x140009768  mov     dl, bl
0x14000976a  jmp     short loc_14000976E
0x14000976c  xor     dl, dl
0x14000976e  mov     r9, [rcx+40h]
0x140009772  lea     rbp, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x140009779  mov     rcx, [rcx+18h]
0x14000977d  mov     [rsp+48h+var_10], rbp
0x140009782  mov     [rsp+48h+var_18], 0Fh
0x140009789  mov     [rsp+48h+var_20], 4
0x140009791  mov     [rsp+48h+var_28], 4
0x140009796  call    WPP_RECORDER_AND_TRACE_SF_
0x14000979b  lea     rcx, [rdi+138h]
0x1400097a2  call    ResourceQueue_Start
0x1400097a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400097ae  mov     eax, [rcx+2Ch]
0x1400097b1  test    al, 8
0x1400097b3  jz      short loc_1400097BB
0x1400097b5  cmp     byte ptr [rcx+29h], 4
0x1400097b9  jnb     short loc_1400097BD
0x1400097bb  xor     bl, bl
0x1400097bd  mov     r9, [rcx+40h]
0x1400097c1  mov     dl, bl
0x1400097c3  mov     rcx, [rcx+18h]
0x1400097c7  mov     [rsp+48h+var_10], rbp
0x1400097cc  mov     [rsp+48h+var_18], 10h
0x1400097d3  mov     [rsp+48h+var_20], 4
0x1400097db  mov     [rsp+48h+var_28], 4
0x1400097e0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400097e5  mov     rbx, [rsp+48h+arg_0]
0x1400097ea  xor     eax, eax
0x1400097ec  mov     rbp, [rsp+48h+arg_8]
0x1400097f1  add     rsp, 40h
0x1400097f5  pop     rdi
0x1400097f6  retn
```

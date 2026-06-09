# BthUsb_ScoWriteStop(_DEVICE_EXTENSION *)

- ea: `0x140009800`
- end: `0x1400098b6`
- name: `?BthUsb_ScoWriteStop@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `182`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140009a90`

## callees

- `0x14000175c`
- `0x140009800`
- `0x14000db7c`

## pseudocode

```c
void __fastcall BthUsb_ScoWriteStop(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
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
    17,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
  ResourceQueue_Stop(&a1->Sco.WriteCtxQueue);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    v6,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    18,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
}

```

## disassembly

```asm
0x140009800  mov     [rsp+arg_0], rbx
0x140009805  mov     [rsp+arg_8], rbp
0x14000980a  push    rdi
0x14000980b  sub     rsp, 40h
0x14000980f  mov     rdi, rcx
0x140009812  mov     rcx, cs:WPP_GLOBAL_Control
0x140009819  mov     bl, 1
0x14000981b  mov     eax, [rcx+2Ch]
0x14000981e  test    al, 8
0x140009820  jz      short loc_14000982C
0x140009822  cmp     byte ptr [rcx+29h], 4
0x140009826  jb      short loc_14000982C
0x140009828  mov     dl, bl
0x14000982a  jmp     short loc_14000982E
0x14000982c  xor     dl, dl
0x14000982e  mov     r9, [rcx+40h]
0x140009832  lea     rbp, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x140009839  mov     rcx, [rcx+18h]
0x14000983d  mov     [rsp+48h+var_10], rbp
0x140009842  mov     [rsp+48h+var_18], 11h
0x140009849  mov     [rsp+48h+var_20], 4
0x140009851  mov     [rsp+48h+var_28], 4
0x140009856  call    WPP_RECORDER_AND_TRACE_SF_
0x14000985b  lea     rcx, [rdi+138h]
0x140009862  call    ResourceQueue_Stop
0x140009867  mov     rcx, cs:WPP_GLOBAL_Control
0x14000986e  mov     eax, [rcx+2Ch]
0x140009871  test    al, 8
0x140009873  jz      short loc_14000987B
0x140009875  cmp     byte ptr [rcx+29h], 4
0x140009879  jnb     short loc_14000987D
0x14000987b  xor     bl, bl
0x14000987d  mov     r9, [rcx+40h]
0x140009881  mov     dl, bl
0x140009883  mov     rcx, [rcx+18h]
0x140009887  mov     [rsp+48h+var_10], rbp
0x14000988c  mov     [rsp+48h+var_18], 12h
0x140009893  mov     [rsp+48h+var_20], 4
0x14000989b  mov     [rsp+48h+var_28], 4
0x1400098a0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400098a5  mov     rbx, [rsp+48h+arg_0]
0x1400098aa  mov     rbp, [rsp+48h+arg_8]
0x1400098af  add     rsp, 40h
0x1400098b3  pop     rdi
0x1400098b4  retn
```

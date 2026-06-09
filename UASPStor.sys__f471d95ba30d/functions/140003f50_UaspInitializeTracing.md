# UaspInitializeTracing

- ea: `0x140003f50`
- end: `0x14000402a`
- name: `UaspInitializeTracing`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x14000d7f0`
- `0x1400150bc`
- `0x140015184`

## import_xrefs

- `WppRecorder!imp_WppRecorderConfigure` at `0x140004005`
- `WppRecorder!imp_WppRecorderConfigure` at `0x140004005`

## pseudocode

```c
__int64 __fastcall UaspInitializeTracing(__int64 a1, __int64 a2)
{
  _DWORD v5[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+28h] [rbp-20h]

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_Uasp;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  v5[1] = 1;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport(a1, a2);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(a1, a2);
  v5[0] = 16;
  v6 = 0x200000002LL;
  return imp_WppRecorderConfigure(WPP_GLOBAL_Control, v5);
}

```

## disassembly

```asm
0x140003f50  mov     [rsp+arg_10], rbx
0x140003f55  push    rdi
0x140003f56  sub     rsp, 40h
0x140003f5a  mov     rax, cs:__security_cookie
0x140003f61  xor     rax, rsp
0x140003f64  mov     [rsp+48h+var_18], rax
0x140003f69  lea     rax, WPP_ThisDir_CTLGUID_Uasp
0x140003f70  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x140003f7b  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140003f82  xorps   xmm0, xmm0
0x140003f85  xor     eax, eax
0x140003f87  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x140003f92  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x140003f98  mov     rdi, rdx
0x140003f9b  mov     rbx, rcx
0x140003f9e  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140003fa9  movups  [rsp+48h+var_28], xmm0
0x140003fae  mov     cs:WPP_MAIN_CB.Timer, 1
0x140003fb9  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x140003fc4  call    WppLoadTracingSupport
0x140003fc9  mov     rdx, rdi
0x140003fcc  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140003fd7  mov     rcx, rbx
0x140003fda  call    WppInitKm
0x140003fdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fe6  lea     rdx, [rsp+48h+var_28]
0x140003feb  mov     eax, 2
0x140003ff0  mov     dword ptr [rsp+48h+var_28], 10h
0x140003ff8  mov     dword ptr [rsp+48h+var_28+8], eax
0x140003ffc  mov     dword ptr [rsp+48h+var_28+0Ch], eax
0x140004000  mov     byte ptr [rsp+48h+var_28+4], 1
0x140004005  call    cs:__imp_imp_WppRecorderConfigure
0x14000400c  nop     dword ptr [rax+rax+00h]
0x140004011  mov     rcx, [rsp+48h+var_18]
0x140004016  xor     rcx, rsp; StackCookie
0x140004019  call    __security_check_cookie
0x14000401e  mov     rbx, [rsp+48h+arg_10]
0x140004023  add     rsp, 40h
0x140004027  pop     rdi
0x140004028  retn
```

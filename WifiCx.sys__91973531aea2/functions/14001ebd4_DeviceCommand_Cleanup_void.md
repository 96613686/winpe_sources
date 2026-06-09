# DeviceCommand::Cleanup(void)

- ea: `0x14001ebd4`
- end: `0x14001ec83`
- name: `?Cleanup@DeviceCommand@@IEAAXXZ`
- size: `175`
- prototype: `void __fastcall(DeviceCommand *__hidden this)`
- caller_count: `18`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001eaf4`
- `0x14002b068`
- `0x14004cedc`
- `0x140053fb4`
- `0x140061710`
- `0x1400687d0`
- `0x1400703e8`
- `0x1400706d4`
- `0x1400707a0`
- `0x1400709ac`
- `0x140070a1c`
- `0x140076b38`
- `0x140082a18`
- `0x14008fc30`
- `0x1400a10cc`
- `0x1400a1178`
- `0x1400bb6c4`
- `0x1400bd508`

## callees

- `0x14000d054`
- `0x14001ebd4`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001ec5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ec5b`

## pseudocode

```c
void __fastcall DeviceCommand::Cleanup(DeviceCommand *this)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)*((_QWORD *)this + 19);
  if ( v2 )
  {
    if ( g_Feature_56544556_MoveToWDFMemory_IsEnabled )
    {
      if ( (unsigned __int64)v2 < 0x10 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            1,
            13,
            (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
      }
      else
      {
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 1664))(WdfDriverGlobals, *(v2 - 1));
      }
    }
    else
    {
      ExFreePoolWithTag(v2, 0x47696457u);
    }
    *((_QWORD *)this + 19) = 0;
    *((_DWORD *)this + 36) = 0;
  }
}

```

## disassembly

```asm
0x14001ebd4  push    rbx
0x14001ebd6  sub     rsp, 30h
0x14001ebda  mov     rbx, rcx
0x14001ebdd  mov     rcx, [rcx+98h]; P
0x14001ebe4  test    rcx, rcx
0x14001ebe7  jz      loc_14001EC7C
0x14001ebed  cmp     cs:?g_Feature_56544556_MoveToWDFMemory_IsEnabled@@3_NA, 0; bool g_Feature_56544556_MoveToWDFMemory_IsEnabled
0x14001ebf4  jz      short loc_14001EC56
0x14001ebf6  cmp     rcx, 10h
0x14001ebfa  jb      short loc_14001EC1C
0x14001ebfc  mov     rax, cs:WdfFunctions_01031
0x14001ec03  mov     rdx, [rcx-8]
0x14001ec07  mov     rcx, cs:WdfDriverGlobals
0x14001ec0e  mov     rax, [rax+680h]
0x14001ec15  call    _guard_dispatch_icall
0x14001ec1a  jmp     short loc_14001EC67
0x14001ec1c  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ec23  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ec2a  jz      short loc_14001EC67
0x14001ec2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec33  lea     rax, WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids
0x14001ec3a  mov     r9d, 0Dh
0x14001ec40  mov     [rsp+38h+var_18], rax
0x14001ec45  mov     dl, 2
0x14001ec47  mov     rcx, [rcx+40h]
0x14001ec4b  lea     r8d, [r9-0Ch]
0x14001ec4f  call    WPP_RECORDER_SF_
0x14001ec54  jmp     short loc_14001EC67
0x14001ec56  mov     edx, 47696457h; Tag
0x14001ec5b  call    cs:__imp_ExFreePoolWithTag
0x14001ec62  nop     dword ptr [rax+rax+00h]
0x14001ec67  mov     qword ptr [rbx+98h], 0
0x14001ec72  mov     dword ptr [rbx+90h], 0
0x14001ec7c  add     rsp, 30h
0x14001ec80  pop     rbx
0x14001ec81  retn
```

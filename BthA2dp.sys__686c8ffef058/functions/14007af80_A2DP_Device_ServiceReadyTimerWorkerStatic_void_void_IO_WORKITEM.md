# A2DP_Device::ServiceReadyTimerWorkerStatic(void *,void *,_IO_WORKITEM *)

- ea: `0x14007af80`
- end: `0x14007b046`
- name: `?ServiceReadyTimerWorkerStatic@A2DP_Device@@_C2PAGE@@AXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `198`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x140003530`
- `0x140006b70`
- `0x14002d7a4`
- `0x140031e18`
- `0x14007af80`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14007b01a`
- `ntoskrnl!IoFreeWorkItem` at `0x14007b01a`

## string_xrefs

- `0x14007b02b`: `ServiceReadyTimerWorkerStatic`

## pseudocode

```c
void __fastcall A2DP_Device::ServiceReadyTimerWorkerStatic(PVOID IoObject, char *Context, PIO_WORKITEM IoWorkItem)
{
  struct _IO_WORKITEM *v3; // rdi
  char *v4; // rbx

  v3 = IoWorkItem;
  v4 = Context;
  LOBYTE(Context) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
  if ( (_BYTE)Context || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(IoWorkItem) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)Context,
      (_DWORD)IoWorkItem,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      4,
      166,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v4);
  }
  A2DP_Device::OnServiceReadyInternal((A2DP_Device *)v4);
  wil::operation_guard::release((wil::operation_guard *)(v4 + 3376));
  IoFreeWorkItem(v3);
  A2DP_Device::Release((A2DP_Device *)v4, 1, "ServiceReadyTimerWorkerStatic");
}

```

## disassembly

```asm
0x14007af80  mov     [rsp+arg_0], rbx
0x14007af85  push    rdi
0x14007af86  sub     rsp, 50h
0x14007af8a  mov     rdi, r8
0x14007af8d  mov     rbx, rdx
0x14007af90  mov     rcx, cs:WPP_GLOBAL_Control
0x14007af97  lea     rax, WPP_GLOBAL_Control
0x14007af9e  cmp     rcx, rax
0x14007afa1  jz      short loc_14007AFB4
0x14007afa3  mov     eax, [rcx+2Ch]
0x14007afa6  test    al, 8
0x14007afa8  jz      short loc_14007AFB4
0x14007afaa  cmp     byte ptr [rcx+29h], 3
0x14007afae  jb      short loc_14007AFB4
0x14007afb0  mov     dl, 1
0x14007afb2  jmp     short loc_14007AFB6
0x14007afb4  xor     dl, dl
0x14007afb6  lea     rax, WPP_RECORDER_INITIALIZED
0x14007afbd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007afc4  setnz   r8b
0x14007afc8  test    dl, dl
0x14007afca  jnz     short loc_14007AFD1
0x14007afcc  test    r8b, r8b
0x14007afcf  jz      short loc_14007B003
0x14007afd1  mov     r9, [rcx+40h]
0x14007afd5  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14007afdc  mov     rcx, [rcx+18h]
0x14007afe0  mov     [rsp+58h+var_18], rbx
0x14007afe5  mov     [rsp+58h+var_20], rax
0x14007afea  mov     [rsp+58h+var_28], 0A6h
0x14007aff1  mov     [rsp+58h+var_30], 4
0x14007aff9  mov     [rsp+58h+var_38], 3
0x14007affe  call    WPP_RECORDER_AND_TRACE_SF_q
0x14007b003  mov     rcx, rbx; this
0x14007b006  call    ?OnServiceReadyInternal@A2DP_Device@@AEAAXXZ; A2DP_Device::OnServiceReadyInternal(void)
0x14007b00b  lea     rcx, [rbx+0D30h]; this
0x14007b012  call    ?release@operation_guard@wil@@QEAAXXZ; wil::operation_guard::release(void)
0x14007b017  mov     rcx, rdi; IoWorkItem
0x14007b01a  call    cs:__imp_IoFreeWorkItem
0x14007b021  nop     dword ptr [rax+rax+00h]
0x14007b026  mov     edx, 1; __int16
0x14007b02b  lea     r8, aServicereadyti_0; "ServiceReadyTimerWorkerStatic"
0x14007b032  mov     rcx, rbx; this
0x14007b035  call    ?Release@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::Release(short,char const *)
0x14007b03a  mov     rbx, [rsp+58h+arg_0]
0x14007b03f  add     rsp, 50h
0x14007b043  pop     rdi
0x14007b044  retn
```

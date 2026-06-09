# A2DP_Device::StopServiceReadyTimer(void)

- ea: `0x14001dda8`
- end: `0x14001de62`
- name: `?StopServiceReadyTimer@A2DP_Device@@AEAAXXZ`
- size: `186`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x14001dc6c`
- `0x140032818`
- `0x140033e10`

## callees

- `0x140003530`
- `0x140006b70`
- `0x14001dda8`
- `0x14002d7a4`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14001de2b`
- `ntoskrnl!KeCancelTimer` at `0x14001de2b`

## string_xrefs

- `0x14001de4c`: `StopServiceReadyTimer`

## pseudocode

```c
void __fastcall A2DP_Device::StopServiceReadyTimer(A2DP_Device *this)
{
  bool v2; // dl

  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      40,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)this);
  if ( KeCancelTimer((PKTIMER)((char *)this + 3152)) )
  {
    wil::operation_guard::release((A2DP_Device *)((char *)this + 3376));
    A2DP_Device::Release(this, 1, "StopServiceReadyTimer");
  }
}

```

## disassembly

```asm
0x14001dda8  push    rbx
0x14001ddaa  sub     rsp, 50h
0x14001ddae  mov     rbx, rcx
0x14001ddb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddb8  lea     rax, WPP_GLOBAL_Control
0x14001ddbf  cmp     rcx, rax
0x14001ddc2  jz      short loc_14001DDD5
0x14001ddc4  mov     eax, [rcx+2Ch]
0x14001ddc7  test    al, 10h
0x14001ddc9  jz      short loc_14001DDD5
0x14001ddcb  cmp     byte ptr [rcx+29h], 4
0x14001ddcf  jb      short loc_14001DDD5
0x14001ddd1  mov     dl, 1
0x14001ddd3  jmp     short loc_14001DDD7
0x14001ddd5  xor     dl, dl
0x14001ddd7  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ddde  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dde5  setnz   r8b
0x14001dde9  test    dl, dl
0x14001ddeb  jnz     short loc_14001DDF2
0x14001dded  test    r8b, r8b
0x14001ddf0  jz      short loc_14001DE24
0x14001ddf2  mov     r9, [rcx+40h]
0x14001ddf6  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001ddfd  mov     rcx, [rcx+18h]
0x14001de01  mov     [rsp+58h+var_18], rbx
0x14001de06  mov     [rsp+58h+var_20], rax
0x14001de0b  mov     [rsp+58h+var_28], 28h ; '('
0x14001de12  mov     [rsp+58h+var_30], 5
0x14001de1a  mov     [rsp+58h+var_38], 4
0x14001de1f  call    WPP_RECORDER_AND_TRACE_SF_q
0x14001de24  lea     rcx, [rbx+0C50h]; PKTIMER
0x14001de2b  call    cs:__imp_KeCancelTimer
0x14001de32  nop     dword ptr [rax+rax+00h]
0x14001de37  test    al, al
0x14001de39  jz      short loc_14001DE5B
0x14001de3b  lea     rcx, [rbx+0D30h]; this
0x14001de42  call    ?release@operation_guard@wil@@QEAAXXZ; wil::operation_guard::release(void)
0x14001de47  mov     edx, 1; __int16
0x14001de4c  lea     r8, aStopservicerea; "StopServiceReadyTimer"
0x14001de53  mov     rcx, rbx; this
0x14001de56  call    ?Release@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::Release(short,char const *)
0x14001de5b  add     rsp, 50h
0x14001de5f  pop     rbx
0x14001de60  retn
```

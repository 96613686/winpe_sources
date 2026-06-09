# ScoAudioDataQueueReady(WDFQUEUE__ *,void *)

- ea: `0x14000d090`
- end: `0x14000d13a`
- name: `?ScoAudioDataQueueReady@@YAXPEAUWDFQUEUE__@@PEAX@Z`
- size: `170`
- prototype: `void __fastcall(struct WDFQUEUE__ *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400010f4`
- `0x14000d090`
- `0x140010eb0`
- `0x14001adc0`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoAudioDataQueueReady(struct WDFQUEUE__ *a1, void *a2)
{
  int v3; // edx
  int v4; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+38h] [rbp-40h] BYREF
  int *v6; // [rsp+58h] [rbp-20h]
  __int64 v7; // [rsp+60h] [rbp-18h]

  v3 = **(_DWORD **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFQUEUE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      a1,
                      off_1400221A0);
  if ( (unsigned int)dword_140022000 > 5 )
  {
    v4 = v3;
    v6 = &v4;
    v7 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140022000, (unsigned __int8 *)&word_14001EF66, 0, 0, 3u, &v5);
  }
  ScoStreamProcessDataQueue(a1);
}

```

## disassembly

```asm
0x14000d090  push    rbx
0x14000d092  sub     rsp, 70h
0x14000d096  mov     rax, cs:__security_cookie
0x14000d09d  xor     rax, rsp
0x14000d0a0  mov     [rsp+78h+var_10], rax
0x14000d0a5  mov     rax, cs:WdfFunctions_01015
0x14000d0ac  mov     rbx, rcx
0x14000d0af  mov     r8, cs:off_1400221A0
0x14000d0b6  mov     rdx, rcx
0x14000d0b9  mov     rcx, cs:WdfDriverGlobals
0x14000d0c0  mov     rax, [rax+650h]
0x14000d0c7  call    _guard_dispatch_icall
0x14000d0cc  mov     rcx, [rax]
0x14000d0cf  mov     eax, cs:dword_140022000
0x14000d0d5  mov     edx, [rcx]
0x14000d0d7  cmp     eax, 5
0x14000d0da  jbe     short loc_14000D11E
0x14000d0dc  lea     rax, [rsp+78h+var_48]
0x14000d0e1  mov     [rsp+78h+var_48], edx
0x14000d0e5  mov     [rsp+78h+var_20], rax
0x14000d0ea  lea     rdx, word_14001EF66
0x14000d0f1  lea     rax, [rsp+78h+var_40]
0x14000d0f6  mov     [rsp+78h+var_18], 4
0x14000d0ff  mov     [rsp+78h+var_50], rax
0x14000d104  lea     rcx, dword_140022000
0x14000d10b  xor     r9d, r9d
0x14000d10e  mov     [rsp+78h+var_58], 3
0x14000d116  xor     r8d, r8d
0x14000d119  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d11e  mov     rcx, rbx; struct WDFQUEUE__ *
0x14000d121  call    ?ScoStreamProcessDataQueue@@YAXPEAUWDFQUEUE__@@@Z; ScoStreamProcessDataQueue(WDFQUEUE__ *)
0x14000d126  mov     rcx, [rsp+78h+var_10]
0x14000d12b  xor     rcx, rsp; StackCookie
0x14000d12e  call    __security_check_cookie
0x14000d133  add     rsp, 70h
0x14000d137  pop     rbx
0x14000d138  retn
```

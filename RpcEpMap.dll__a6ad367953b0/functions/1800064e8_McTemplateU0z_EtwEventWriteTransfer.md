# McTemplateU0z_EtwEventWriteTransfer

- ea: `0x1800064e8`
- end: `0x180006544`
- name: `McTemplateU0z_EtwEventWriteTransfer`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005ae0`

## callees

- `0x18000502c`
- `0x18000a980`

## pseudocode

```c
__int64 __fastcall McTemplateU0z_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF

  v4[3] = 74;
  v4[2] = L"bc90d167-9470-4139-a9ba-be0bbbf5b74d";
  return McGenEventWrite_EtwEventWriteTransfer(
           SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
           (__int64)&ServiceTriggerPerfTriggersDisabled,
           a3,
           2,
           (__int64)v4);
}

```

## disassembly

```asm
0x1800064e8  mov     r11, rsp
0x1800064eb  sub     rsp, 68h
0x1800064ef  mov     rax, cs:__security_cookie
0x1800064f6  xor     rax, rsp
0x1800064f9  mov     [rsp+68h+var_18], rax
0x1800064fe  lea     rax, aBc90d167947041; "bc90d167-9470-4139-a9ba-be0bbbf5b74d"
0x180006505  mov     qword ptr [r11-20h], 4Ah ; 'J'
0x18000650d  mov     [r11-28h], rax
0x180006511  lea     rdx, ServiceTriggerPerfTriggersDisabled
0x180006518  lea     rax, [r11-38h]
0x18000651c  mov     r9d, 2
0x180006522  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x180006529  mov     [r11-48h], rax
0x18000652d  call    McGenEventWrite_EtwEventWriteTransfer
0x180006532  mov     rcx, [rsp+68h+var_18]
0x180006537  xor     rcx, rsp; StackCookie
0x18000653a  call    __security_check_cookie
0x18000653f  add     rsp, 68h
0x180006543  retn
```

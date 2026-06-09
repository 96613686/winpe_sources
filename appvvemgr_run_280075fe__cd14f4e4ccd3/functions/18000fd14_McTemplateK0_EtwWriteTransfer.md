# McTemplateK0_EtwWriteTransfer

- ea: `0x18000fd14`
- end: `0x18000fd56`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `66`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a1d0`
- `0x18000fe44`
- `0x180010374`
- `0x1800107e4`
- `0x180012004`
- `0x180012264`
- `0x1800124d0`
- `0x180015fa4`
- `0x18001aea0`

## callees

- `0x18000fcb4`
- `0x18001baf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(
           (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
           a2,
           a3,
           1u,
           &v4);
}

```

## disassembly

```asm
0x18000fd14  sub     rsp, 58h
0x18000fd18  mov     rax, cs:__security_cookie
0x18000fd1f  xor     rax, rsp
0x18000fd22  mov     [rsp+58h+var_18], rax
0x18000fd27  lea     rax, [rsp+58h+var_28]
0x18000fd2c  mov     r9d, 1
0x18000fd32  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x18000fd39  mov     [rsp+58h+var_38], rax
0x18000fd3e  call    McGenEventWrite_EtwWriteTransfer
0x18000fd43  mov     rcx, [rsp+58h+var_18]
0x18000fd48  xor     rcx, rsp; StackCookie
0x18000fd4b  call    __security_check_cookie
0x18000fd50  add     rsp, 58h
0x18000fd54  retn
```

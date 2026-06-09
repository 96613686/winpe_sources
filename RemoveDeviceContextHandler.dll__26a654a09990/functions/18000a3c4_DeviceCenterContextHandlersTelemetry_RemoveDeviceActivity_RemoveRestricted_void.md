# DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveRestricted(void)

- ea: `0x18000a3c4`
- end: `0x18000a44c`
- name: `?RemoveRestricted@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXXZ`
- size: `136`
- prototype: `void __fastcall(DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007a10`

## callees

- `0x1800018dc`
- `0x180009170`
- `0x18000a3c4`
- `0x18000c990`

## pseudocode

```c
void __fastcall DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveRestricted(
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-38h] BYREF

  v2 = DeviceCenterContextHandlersLogging::Provider();
  if ( *(_DWORD *)v2 > 5u
    && (*((_QWORD *)v2 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v2 + 3) & 0x200000000000LL) == *((_QWORD *)v2 + 3) )
  {
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v2,
      (unsigned __int8 *)&byte_180010E8F,
      (const GUID *)(*((_QWORD *)this + 34) + 8LL),
      0,
      2u,
      &v3);
  }
}

```

## disassembly

```asm
0x18000a3c4  push    rbx
0x18000a3c6  sub     rsp, 60h
0x18000a3ca  mov     rax, cs:__security_cookie
0x18000a3d1  xor     rax, rsp
0x18000a3d4  mov     [rsp+68h+var_18], rax
0x18000a3d9  mov     rbx, rcx
0x18000a3dc  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x18000a3e1  mov     edx, [rax]
0x18000a3e3  cmp     edx, 5
0x18000a3e6  jbe     short loc_18000A439
0x18000a3e8  mov     r8, [rax+18h]
0x18000a3ec  mov     r9, 200000000000h
0x18000a3f6  mov     rdx, [rax+10h]
0x18000a3fa  test    r9, rdx
0x18000a3fd  jz      short loc_18000A439
0x18000a3ff  mov     rcx, r8
0x18000a402  and     rcx, r9
0x18000a405  cmp     rcx, r8
0x18000a408  jnz     short loc_18000A439
0x18000a40a  mov     r8, [rbx+110h]
0x18000a411  lea     rcx, [rsp+68h+var_38]
0x18000a416  mov     [rsp+68h+var_40], rcx
0x18000a41b  lea     rdx, byte_180010E8F
0x18000a422  mov     rcx, rax
0x18000a425  mov     [rsp+68h+var_48], 2
0x18000a42d  add     r8, 8
0x18000a431  xor     r9d, r9d
0x18000a434  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a439  mov     rcx, [rsp+68h+var_18]
0x18000a43e  xor     rcx, rsp; StackCookie
0x18000a441  call    __security_check_cookie
0x18000a446  add     rsp, 60h
0x18000a44a  pop     rbx
0x18000a44b  retn
```

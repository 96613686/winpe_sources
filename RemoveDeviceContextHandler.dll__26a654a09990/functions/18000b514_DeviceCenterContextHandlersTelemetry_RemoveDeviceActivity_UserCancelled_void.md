# DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::UserCancelled(void)

- ea: `0x18000b514`
- end: `0x18000b59c`
- name: `?UserCancelled@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXXZ`
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
- `0x18000b514`
- `0x18000c990`

## pseudocode

```c
void __fastcall DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::UserCancelled(
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
      (unsigned __int8 *)&byte_180010EAF,
      (const GUID *)(*((_QWORD *)this + 34) + 8LL),
      0,
      2u,
      &v3);
  }
}

```

## disassembly

```asm
0x18000b514  push    rbx
0x18000b516  sub     rsp, 60h
0x18000b51a  mov     rax, cs:__security_cookie
0x18000b521  xor     rax, rsp
0x18000b524  mov     [rsp+68h+var_18], rax
0x18000b529  mov     rbx, rcx
0x18000b52c  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x18000b531  mov     edx, [rax]
0x18000b533  cmp     edx, 5
0x18000b536  jbe     short loc_18000B589
0x18000b538  mov     r8, [rax+18h]
0x18000b53c  mov     r9, 200000000000h
0x18000b546  mov     rdx, [rax+10h]
0x18000b54a  test    r9, rdx
0x18000b54d  jz      short loc_18000B589
0x18000b54f  mov     rcx, r8
0x18000b552  and     rcx, r9
0x18000b555  cmp     rcx, r8
0x18000b558  jnz     short loc_18000B589
0x18000b55a  mov     r8, [rbx+110h]
0x18000b561  lea     rcx, [rsp+68h+var_38]
0x18000b566  mov     [rsp+68h+var_40], rcx
0x18000b56b  lea     rdx, byte_180010EAF
0x18000b572  mov     rcx, rax
0x18000b575  mov     [rsp+68h+var_48], 2
0x18000b57d  add     r8, 8
0x18000b581  xor     r9d, r9d
0x18000b584  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b589  mov     rcx, [rsp+68h+var_18]
0x18000b58e  xor     rcx, rsp; StackCookie
0x18000b591  call    __security_check_cookie
0x18000b596  add     rsp, 60h
0x18000b59a  pop     rbx
0x18000b59b  retn
```

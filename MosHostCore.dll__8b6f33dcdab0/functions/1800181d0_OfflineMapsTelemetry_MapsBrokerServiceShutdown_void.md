# OfflineMapsTelemetry::MapsBrokerServiceShutdown_(void)

- ea: `0x1800181d0`
- end: `0x180018281`
- name: `?MapsBrokerServiceShutdown_@OfflineMapsTelemetry@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cb60`

## callees

- `0x1800010c0`
- `0x18000186c`
- `0x180003410`
- `0x180009e6c`
- `0x1800181d0`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::MapsBrokerServiceShutdown_(OfflineMapsTelemetry *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r10
  __int64 v4; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v5[32]; // [rsp+40h] [rbp-58h] BYREF
  char *v6; // [rsp+60h] [rbp-38h]
  __int64 v7; // [rsp+68h] [rbp-30h]
  __int64 *v8; // [rsp+70h] [rbp-28h]
  __int64 v9; // [rsp+78h] [rbp-20h]

  v2 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL) )
    {
      v4 = 0x2000000;
      v6 = (char *)this + 24;
      v8 = &v4;
      v9 = 8;
      v7 = 16;
      tlgWriteTransfer_EventWriteTransfer(v3, byte_18002DD1B, 0, 0, 4, v5);
    }
  }
}

```

## disassembly

```asm
0x1800181d0  push    rbx
0x1800181d2  sub     rsp, 90h
0x1800181d9  mov     rax, cs:__security_cookie
0x1800181e0  xor     rax, rsp
0x1800181e3  mov     [rsp+98h+var_18], rax
0x1800181eb  mov     rbx, rcx
0x1800181ee  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x1800181f3  mov     r10, rax
0x1800181f6  mov     edx, [rax]
0x1800181f8  cmp     edx, 5
0x1800181fb  jbe     short loc_180018268
0x1800181fd  mov     rdx, 400000000000h
0x180018207  mov     rcx, rax
0x18001820a  call    _tlgKeywordOn
0x18001820f  test    al, al
0x180018211  jz      short loc_180018268
0x180018213  lea     rax, [rbx+18h]
0x180018217  mov     [rsp+98h+var_68], 2000000h
0x180018220  mov     [rsp+98h+var_38], rax
0x180018225  lea     rcx, [rsp+98h+var_68]
0x18001822a  lea     rax, [rsp+98h+var_58]
0x18001822f  mov     [rsp+98h+var_28], rcx
0x180018234  mov     [rsp+98h+var_70], rax
0x180018239  lea     rdx, byte_18002DD1B
0x180018240  xor     r9d, r9d
0x180018243  mov     [rsp+98h+var_78], 4
0x18001824b  xor     r8d, r8d
0x18001824e  mov     [rsp+98h+var_20], 8
0x180018257  mov     rcx, r10
0x18001825a  mov     [rsp+98h+var_30], 10h
0x180018263  call    _tlgWriteTransfer_EventWriteTransfer
0x180018268  mov     rcx, [rsp+98h+var_18]
0x180018270  xor     rcx, rsp; StackCookie
0x180018273  call    __security_check_cookie
0x180018278  add     rsp, 90h
0x18001827f  pop     rbx
0x180018280  retn
```

# OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(long,ulong)

- ea: `0x18000b1cc`
- end: `0x18000b285`
- name: `?ServiceNotReady@ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAAXJK@Z`
- size: `185`
- prototype: `void __fastcall(OfflineMapsTelemetry::ClientOpenConnectionActivity *this, int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a810`
- `0x18000d760`
- `0x18000f0c0`
- `0x18000fdb0`

## callees

- `0x18000163c`
- `0x180002550`
- `0x180005c50`
- `0x18000b1cc`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(
        OfflineMapsTelemetry::ClientOpenConnectionActivity *this,
        int a2,
        int a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  int v8; // [rsp+30h] [rbp-39h] BYREF
  int v9; // [rsp+34h] [rbp-35h] BYREF
  __int64 v10; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-29h] BYREF
  int *v12; // [rsp+60h] [rbp-9h]
  __int64 v13; // [rsp+68h] [rbp-1h]
  int *v14; // [rsp+70h] [rbp+7h]
  __int64 v15; // [rsp+78h] [rbp+Fh]
  __int64 *v16; // [rsp+80h] [rbp+17h]
  __int64 v17; // [rsp+88h] [rbp+1Fh]

  v6 = OfflineMapsTraceLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v7 = *((_QWORD *)this + 34);
    v16 = &v10;
    v10 = 0x1000000;
    v14 = &v8;
    v8 = a3;
    v12 = &v9;
    v9 = a2;
    v17 = 8;
    v15 = 4;
    v13 = 4;
    tlgWriteTransfer_EventWriteTransfer(v6, word_1800179CA, v7 + 8, 0, 5, v11);
  }
}

```

## disassembly

```asm
0x18000b1cc  push    rbp
0x18000b1ce  push    rbx
0x18000b1cf  push    rsi
0x18000b1d0  push    rdi
0x18000b1d1  lea     rbp, [rsp-3Fh]
0x18000b1d6  sub     rsp, 0A8h
0x18000b1dd  mov     rax, cs:__security_cookie
0x18000b1e4  xor     rax, rsp
0x18000b1e7  mov     [rbp+57h+var_30], rax
0x18000b1eb  mov     ebx, r8d
0x18000b1ee  mov     edi, edx
0x18000b1f0  mov     rsi, rcx
0x18000b1f3  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000b1f8  mov     r9d, [rax]
0x18000b1fb  cmp     r9d, 5
0x18000b1ff  jbe     short loc_18000B26D
0x18000b201  mov     r8, [rsi+110h]
0x18000b208  lea     rcx, [rbp+57h+var_88]
0x18000b20c  mov     [rbp+57h+var_40], rcx
0x18000b210  lea     rdx, word_1800179CA
0x18000b217  lea     rcx, [rbp+57h+var_90]
0x18000b21b  mov     [rbp+57h+var_88], 1000000h
0x18000b223  mov     [rbp+57h+var_50], rcx
0x18000b227  add     r8, 8
0x18000b22b  lea     rcx, [rbp+57h+var_8C]
0x18000b22f  mov     [rbp+57h+var_90], ebx
0x18000b232  mov     [rbp+57h+var_60], rcx
0x18000b236  xor     r9d, r9d
0x18000b239  lea     rcx, [rbp+57h+var_80]
0x18000b23d  mov     [rbp+57h+var_8C], edi
0x18000b240  mov     [rsp+0C0h+var_98], rcx
0x18000b245  mov     rcx, rax
0x18000b248  mov     [rbp+57h+var_38], 8
0x18000b250  mov     [rbp+57h+var_48], 4
0x18000b258  mov     [rbp+57h+var_58], 4
0x18000b260  mov     [rsp+0C0h+var_A0], 5
0x18000b268  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b26d  mov     rcx, [rbp+57h+var_30]
0x18000b271  xor     rcx, rsp; StackCookie
0x18000b274  call    __security_check_cookie
0x18000b279  add     rsp, 0A8h
0x18000b280  pop     rdi
0x18000b281  pop     rsi
0x18000b282  pop     rbx
0x18000b283  pop     rbp
0x18000b284  retn
```

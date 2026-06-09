# McTemplateK0q_EtwWriteTransfer

- ea: `0x18000fd5c`
- end: `0x18000fdba`
- name: `McTemplateK0q_EtwWriteTransfer`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800054e8`
- `0x180016f64`
- `0x180018ea0`
- `0x18001a594`

## callees

- `0x18000fcb4`
- `0x18001baf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0q_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  int *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  v7 = 4;
  v6 = &v8;
  return McGenEventWrite_EtwWriteTransfer(
           (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
           a2,
           &GUID_NULL,
           2u,
           &v5);
}

```

## disassembly

```asm
0x18000fd5c  mov     r11, rsp
0x18000fd5f  mov     [r11+20h], r9d
0x18000fd63  sub     rsp, 68h
0x18000fd67  mov     rax, cs:__security_cookie
0x18000fd6e  xor     rax, rsp
0x18000fd71  mov     [rsp+68h+var_18], rax
0x18000fd76  lea     rax, [r11+20h]
0x18000fd7a  mov     qword ptr [r11-20h], 4
0x18000fd82  mov     [r11-28h], rax
0x18000fd86  lea     r8, GUID_NULL
0x18000fd8d  lea     rax, [r11-38h]
0x18000fd91  mov     r9d, 2
0x18000fd97  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x18000fd9e  mov     [r11-48h], rax
0x18000fda2  call    McGenEventWrite_EtwWriteTransfer
0x18000fda7  mov     rcx, [rsp+68h+var_18]
0x18000fdac  xor     rcx, rsp; StackCookie
0x18000fdaf  call    __security_check_cookie
0x18000fdb4  add     rsp, 68h
0x18000fdb8  retn
```

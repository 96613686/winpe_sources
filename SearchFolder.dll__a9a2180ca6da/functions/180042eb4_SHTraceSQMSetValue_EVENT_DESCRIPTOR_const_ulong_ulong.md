# SHTraceSQMSetValue(_EVENT_DESCRIPTOR const *,ulong,ulong)

- ea: `0x180042eb4`
- end: `0x180042f71`
- name: `?SHTraceSQMSetValue@@YAXPEBU_EVENT_DESCRIPTOR@@KK@Z`
- size: `189`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044360`

## callees

- `0x180006900`
- `0x180042eb4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180042f56`
- `ntdll!EtwEventWrite` at `0x180042f56`
- `ntdll!EtwEventEnabled` at `0x180042ee7`
- `ntdll!EtwEventEnabled` at `0x180042ee7`

## pseudocode

```c
void __fastcall SHTraceSQMSetValue(const struct _EVENT_DESCRIPTOR *a1, __int64 a2, int a3)
{
  int v3; // [rsp+20h] [rbp-60h] BYREF
  int v4; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v5[8]; // [rsp+30h] [rbp-50h] BYREF
  int v6; // [rsp+A0h] [rbp+20h] BYREF

  v6 = a3;
  v3 = 5069;
  if ( (unsigned __int8)EtwEventEnabled(
                          Microsoft_Windows_Shell_Core_Provider_Context,
                          ShellTraceId_OpenSearch_Http_Response) )
  {
    v5[0] = &g_SHSqmGlobalSession;
    v4 = 5;
    v5[2] = &v3;
    v5[1] = 16;
    v5[4] = &v4;
    v5[6] = &v6;
    v5[3] = 4;
    v5[5] = 4;
    v5[7] = 4;
    EtwEventWrite(Microsoft_Windows_Shell_Core_Provider_Context, ShellTraceId_OpenSearch_Http_Response, 4, v5);
  }
}

```

## disassembly

```asm
0x180042eb4  mov     [rsp-8+arg_10], r8d
0x180042eb9  push    rbp
0x180042eba  mov     rbp, rsp
0x180042ebd  sub     rsp, 80h
0x180042ec4  mov     rax, cs:__security_cookie
0x180042ecb  xor     rax, rsp
0x180042ece  mov     [rbp+var_10], rax
0x180042ed2  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x180042ed9  lea     rdx, ShellTraceId_OpenSearch_Http_Response
0x180042ee0  mov     [rbp+var_60], 13CDh
0x180042ee7  call    cs:__imp_EtwEventEnabled
0x180042eed  test    al, al
0x180042eef  jz      short loc_180042F5C
0x180042ef1  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x180042ef8  lea     rax, ?g_SHSqmGlobalSession@@3U_GUID@@B; _GUID const g_SHSqmGlobalSession
0x180042eff  mov     [rbp+var_50], rax
0x180042f03  lea     r9, [rbp+var_50]
0x180042f07  xorps   xmm0, xmm0
0x180042f0a  mov     [rbp+var_58], 5
0x180042f11  mov     r8d, 4
0x180042f17  lea     rax, [rbp+var_60]
0x180042f1b  movups  [rbp+var_48], xmm0
0x180042f1f  mov     qword ptr [rbp+var_48+8], rax
0x180042f23  lea     rdx, ShellTraceId_OpenSearch_Http_Response
0x180042f2a  movups  [rbp+var_38], xmm0
0x180042f2e  lea     rax, [rbp+var_58]
0x180042f32  mov     qword ptr [rbp+var_48], 10h
0x180042f3a  movups  [rbp+var_28], xmm0
0x180042f3e  mov     qword ptr [rbp+var_38+8], rax
0x180042f42  lea     rax, [rbp+arg_10]
0x180042f46  mov     qword ptr [rbp+var_28+8], rax
0x180042f4a  mov     qword ptr [rbp+var_38], r8
0x180042f4e  mov     qword ptr [rbp+var_28], r8
0x180042f52  mov     [rbp+var_18], r8
0x180042f56  call    cs:__imp_EtwEventWrite
0x180042f5c  mov     rcx, [rbp+var_10]
0x180042f60  xor     rcx, rsp; StackCookie
0x180042f63  call    __security_check_cookie
0x180042f68  add     rsp, 80h
0x180042f6f  pop     rbp
0x180042f70  retn
```

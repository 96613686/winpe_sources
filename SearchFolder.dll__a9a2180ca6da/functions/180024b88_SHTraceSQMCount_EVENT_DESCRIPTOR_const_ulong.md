# SHTraceSQMCount(_EVENT_DESCRIPTOR const *,ulong)

- ea: `0x180024b88`
- end: `0x180024c48`
- name: `?SHTraceSQMCount@@YAXPEBU_EVENT_DESCRIPTOR@@K@Z`
- size: `192`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044618`

## callees

- `0x180006900`
- `0x180024b88`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180024c2d`
- `ntdll!EtwEventWrite` at `0x180024c2d`
- `ntdll!EtwEventEnabled` at `0x180024bb7`
- `ntdll!EtwEventEnabled` at `0x180024bb7`

## pseudocode

```c
void __fastcall SHTraceSQMCount(const struct _EVENT_DESCRIPTOR *a1)
{
  int v1; // [rsp+20h] [rbp-60h] BYREF
  int v2; // [rsp+28h] [rbp-58h] BYREF
  int v3; // [rsp+2Ch] [rbp-54h] BYREF
  _QWORD v4[8]; // [rsp+30h] [rbp-50h] BYREF

  v1 = 5232;
  if ( (unsigned __int8)EtwEventEnabled(
                          Microsoft_Windows_Shell_Core_Provider_Context,
                          ShellTraceId_OpenSearch_Provider_Queried) )
  {
    v4[0] = &g_SHSqmGlobalSession;
    v2 = 6;
    v3 = 1;
    v4[1] = 16;
    v4[2] = &v1;
    v4[3] = 4;
    v4[4] = &v2;
    v4[6] = &v3;
    v4[5] = 4;
    v4[7] = 4;
    EtwEventWrite(Microsoft_Windows_Shell_Core_Provider_Context, ShellTraceId_OpenSearch_Provider_Queried, 4, v4);
  }
}

```

## disassembly

```asm
0x180024b88  push    rbp
0x180024b8a  mov     rbp, rsp
0x180024b8d  sub     rsp, 80h
0x180024b94  mov     rax, cs:__security_cookie
0x180024b9b  xor     rax, rsp
0x180024b9e  mov     [rbp+var_10], rax
0x180024ba2  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x180024ba9  lea     rdx, ShellTraceId_OpenSearch_Provider_Queried
0x180024bb0  mov     [rbp+var_60], 1470h
0x180024bb7  call    cs:__imp_EtwEventEnabled
0x180024bbd  test    al, al
0x180024bbf  jz      short loc_180024C33
0x180024bc1  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x180024bc8  lea     rax, ?g_SHSqmGlobalSession@@3U_GUID@@B; _GUID const g_SHSqmGlobalSession
0x180024bcf  mov     [rbp+var_50], rax
0x180024bd3  lea     r9, [rbp+var_50]
0x180024bd7  xorps   xmm0, xmm0
0x180024bda  mov     [rbp+var_58], 6
0x180024be1  mov     r8d, 4
0x180024be7  mov     [rbp+var_54], 1
0x180024bee  movups  [rbp+var_48], xmm0
0x180024bf2  lea     rax, [rbp+var_60]
0x180024bf6  mov     qword ptr [rbp+var_48], 10h
0x180024bfe  mov     qword ptr [rbp+var_48+8], rax
0x180024c02  lea     rdx, ShellTraceId_OpenSearch_Provider_Queried
0x180024c09  movups  [rbp+var_38], xmm0
0x180024c0d  lea     rax, [rbp+var_58]
0x180024c11  mov     qword ptr [rbp+var_38], r8
0x180024c15  movups  [rbp+var_28], xmm0
0x180024c19  mov     qword ptr [rbp+var_38+8], rax
0x180024c1d  lea     rax, [rbp+var_54]
0x180024c21  mov     qword ptr [rbp+var_28+8], rax
0x180024c25  mov     qword ptr [rbp+var_28], r8
0x180024c29  mov     [rbp+var_18], r8
0x180024c2d  call    cs:__imp_EtwEventWrite
0x180024c33  mov     rcx, [rbp+var_10]
0x180024c37  xor     rcx, rsp; StackCookie
0x180024c3a  call    __security_check_cookie
0x180024c3f  add     rsp, 80h
0x180024c46  pop     rbp
0x180024c47  retn
```

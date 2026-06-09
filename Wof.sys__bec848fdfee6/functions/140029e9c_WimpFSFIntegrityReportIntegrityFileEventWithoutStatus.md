# WimpFSFIntegrityReportIntegrityFileEventWithoutStatus

- ea: `0x140029e9c`
- end: `0x140029f72`
- name: `WimpFSFIntegrityReportIntegrityFileEventWithoutStatus`
- size: `214`
- prototype: `BOOLEAN __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400284d8`

## callees

- `0x140011560`
- `0x140029e9c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029ed9`
- `ntoskrnl!EtwEventEnabled` at `0x140029ed9`
- `ntoskrnl!EtwWrite` at `0x140029f44`
- `ntoskrnl!EtwWrite` at `0x140029f44`

## pseudocode

```c
BOOLEAN __fastcall WimpFSFIntegrityReportIntegrityFileEventWithoutStatus(
        PCEVENT_DESCRIPTOR EventDescriptor,
        __int64 a2,
        unsigned __int16 *a3)
{
  BOOLEAN result; // al
  unsigned __int16 v6; // ax
  __int16 v7; // [rsp+30h] [rbp-50h] BYREF
  __int64 v8; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+50h] [rbp-30h]
  int v11; // [rsp+58h] [rbp-28h]
  int v12; // [rsp+5Ch] [rbp-24h]
  __int64 *v13; // [rsp+60h] [rbp-20h]
  __int64 v14; // [rsp+68h] [rbp-18h]

  v8 = a2;
  v7 = 0;
  result = EtwEventEnabled(g_WimIntegrityEtwEventHandle, EventDescriptor);
  if ( result )
  {
    v6 = *a3;
    v11 = *a3;
    v7 = v6 >> 1;
    UserData.Ptr = (ULONGLONG)&v7;
    v10 = *((_QWORD *)a3 + 1);
    v13 = &v8;
    *(_QWORD *)&UserData.Size = 2;
    v12 = 0;
    v14 = 8;
    return EtwWrite(g_WimIntegrityEtwEventHandle, EventDescriptor, 0, 3u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140029e9c  mov     [rsp-8+arg_10], rbx
0x140029ea1  mov     [rsp-8+arg_18], rdi
0x140029ea6  push    rbp
0x140029ea7  mov     rbp, rsp
0x140029eaa  sub     rsp, 80h
0x140029eb1  mov     rax, cs:__security_cookie
0x140029eb8  xor     rax, rsp
0x140029ebb  mov     [rbp+var_10], rax
0x140029ebf  mov     [rbp+var_48], rdx
0x140029ec3  mov     rdi, rcx
0x140029ec6  mov     rdx, rcx; EventDescriptor
0x140029ec9  xor     eax, eax
0x140029ecb  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029ed2  mov     rbx, r8
0x140029ed5  mov     [rbp+var_50], ax
0x140029ed9  call    cs:__imp_EtwEventEnabled
0x140029ee0  nop     dword ptr [rax+rax+00h]
0x140029ee5  test    al, al
0x140029ee7  jz      short loc_140029F50
0x140029ee9  movzx   ecx, word ptr [rbx]
0x140029eec  mov     r9d, 3; UserDataCount
0x140029ef2  movzx   eax, cx
0x140029ef5  mov     [rbp+var_28], ecx
0x140029ef8  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029eff  xor     r8d, r8d; ActivityId
0x140029f02  shr     ax, 1
0x140029f05  mov     rdx, rdi; EventDescriptor
0x140029f08  mov     [rbp+var_50], ax
0x140029f0c  lea     rax, [rbp+var_50]
0x140029f10  mov     [rbp+var_40.Ptr], rax
0x140029f14  mov     rax, [rbx+8]
0x140029f18  mov     [rbp+var_30], rax
0x140029f1c  lea     rax, [rbp+var_48]
0x140029f20  mov     [rbp+var_20], rax
0x140029f24  lea     rax, [rbp+var_40]
0x140029f28  mov     [rsp+80h+UserData], rax; UserData
0x140029f2d  mov     qword ptr [rbp+var_40.Size], 2
0x140029f35  mov     [rbp+var_24], 0
0x140029f3c  mov     [rbp+var_18], 8
0x140029f44  call    cs:__imp_EtwWrite
0x140029f4b  nop     dword ptr [rax+rax+00h]
0x140029f50  mov     rcx, [rbp+var_10]
0x140029f54  xor     rcx, rsp; StackCookie
0x140029f57  call    __security_check_cookie
0x140029f5c  lea     r11, [rsp+80h+var_s0]
0x140029f64  mov     rbx, [r11+20h]
0x140029f68  mov     rdi, [r11+28h]
0x140029f6c  mov     rsp, r11
0x140029f6f  pop     rbp
0x140029f70  retn
```

# WimpFSFIntegrityReportBlockFailure

- ea: `0x140029ca0`
- end: `0x140029da9`
- name: `WimpFSFIntegrityReportBlockFailure`
- size: `265`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140027ffc`
- `0x140028f44`

## callees

- `0x140011560`
- `0x1400295e4`
- `0x140029ca0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029ce2`
- `ntoskrnl!EtwEventEnabled` at `0x140029ce2`
- `ntoskrnl!EtwWrite` at `0x140029d7a`
- `ntoskrnl!EtwWrite` at `0x140029d7a`

## pseudocode

```c
void __fastcall WimpFSFIntegrityReportBlockFailure(__int64 a1, int a2)
{
  __int64 v3; // rdx
  int v4; // ecx
  __int16 v5; // [rsp+30h] [rbp-9h] BYREF
  int v6; // [rsp+34h] [rbp-5h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp+7h] BYREF
  __int64 v8; // [rsp+50h] [rbp+17h]
  int v9; // [rsp+58h] [rbp+1Fh]
  int v10; // [rsp+5Ch] [rbp+23h]
  int *v11; // [rsp+60h] [rbp+27h]
  __int64 v12; // [rsp+68h] [rbp+2Fh]
  int *v13; // [rsp+70h] [rbp+37h]
  __int64 v14; // [rsp+78h] [rbp+3Fh]
  int v15; // [rsp+A8h] [rbp+6Fh] BYREF

  v15 = a2;
  v6 = 4096;
  v5 = 0;
  if ( EtwEventEnabled(g_WimIntegrityEtwEventHandle, &WofIntegrityBlockVerificationFailureEventId)
    && _InterlockedIncrement((volatile signed __int32 *)(a1 + 188)) <= 16 )
  {
    v3 = *(_QWORD *)(a1 + 160);
    v5 = *(_WORD *)(v3 + 88) >> 1;
    UserData.Ptr = (ULONGLONG)&v5;
    *(_QWORD *)&UserData.Size = 2;
    v4 = *(unsigned __int16 *)(v3 + 88);
    v8 = *(_QWORD *)(v3 + 96);
    v11 = &v15;
    v13 = &v6;
    v9 = v4;
    v10 = 0;
    v12 = 4;
    v14 = 4;
    EtwWrite(g_WimIntegrityEtwEventHandle, &WofIntegrityBlockVerificationFailureEventId, 0, 4u, &UserData);
  }
  WimpFSFBreakForIntegrityFailure();
}

```

## disassembly

```asm
0x140029ca0  mov     [rsp-8+arg_10], rbx
0x140029ca5  mov     [rsp-8+arg_8], edx
0x140029ca9  push    rbp
0x140029caa  lea     rbp, [rsp-57h]
0x140029caf  sub     rsp, 90h
0x140029cb6  mov     rax, cs:__security_cookie
0x140029cbd  xor     rax, rsp
0x140029cc0  mov     [rbp+57h+var_10], rax
0x140029cc4  mov     rbx, rcx
0x140029cc7  mov     [rbp+57h+var_5C], 1000h
0x140029cce  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029cd5  lea     rdx, WofIntegrityBlockVerificationFailureEventId; EventDescriptor
0x140029cdc  xor     eax, eax
0x140029cde  mov     [rbp+57h+var_60], ax
0x140029ce2  call    cs:__imp_EtwEventEnabled
0x140029ce9  nop     dword ptr [rax+rax+00h]
0x140029cee  test    al, al
0x140029cf0  jz      loc_140029D86
0x140029cf6  mov     eax, 1
0x140029cfb  lock xadd [rbx+0BCh], eax
0x140029d03  inc     eax
0x140029d05  cmp     eax, 10h
0x140029d08  jg      short loc_140029D86
0x140029d0a  mov     rdx, [rbx+0A0h]
0x140029d11  mov     r9d, 4; UserDataCount
0x140029d17  xor     r8d, r8d; ActivityId
0x140029d1a  movzx   eax, word ptr [rdx+58h]
0x140029d1e  shr     ax, 1
0x140029d21  mov     [rbp+57h+var_60], ax
0x140029d25  lea     rax, [rbp+57h+var_60]
0x140029d29  mov     [rbp+57h+var_50.Ptr], rax
0x140029d2d  mov     qword ptr [rbp+57h+var_50.Size], 2
0x140029d35  mov     rax, [rdx+60h]
0x140029d39  movzx   ecx, word ptr [rdx+58h]
0x140029d3d  lea     rdx, WofIntegrityBlockVerificationFailureEventId; EventDescriptor
0x140029d44  mov     [rbp+57h+var_40], rax
0x140029d48  lea     rax, [rbp+57h+arg_8]
0x140029d4c  mov     [rbp+57h+var_30], rax
0x140029d50  lea     rax, [rbp+57h+var_5C]
0x140029d54  mov     [rbp+57h+var_20], rax
0x140029d58  lea     rax, [rbp+57h+var_50]
0x140029d5c  mov     [rbp+57h+var_38], ecx
0x140029d5f  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029d66  mov     [rsp+90h+UserData], rax; UserData
0x140029d6b  mov     [rbp+57h+var_34], 0
0x140029d72  mov     [rbp+57h+var_28], r9
0x140029d76  mov     [rbp+57h+var_18], r9
0x140029d7a  call    cs:__imp_EtwWrite
0x140029d81  nop     dword ptr [rax+rax+00h]
0x140029d86  call    WimpFSFBreakForIntegrityFailure
0x140029d8b  mov     rcx, [rbp+57h+var_10]
0x140029d8f  xor     rcx, rsp; StackCookie
0x140029d92  call    __security_check_cookie
0x140029d97  mov     rbx, [rsp+90h+arg_10]
0x140029d9f  add     rsp, 90h
0x140029da6  pop     rbp
0x140029da7  retn
```

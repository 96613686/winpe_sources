# WimpFSFIntegrityReportIntegrityFileEvent

- ea: `0x140029db0`
- end: `0x140029e94`
- name: `WimpFSFIntegrityReportIntegrityFileEvent`
- size: `228`
- prototype: `BOOLEAN __fastcall(__int64, int, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400284d8`
- `0x14002ac38`

## callees

- `0x140011560`
- `0x140029db0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029def`
- `ntoskrnl!EtwEventEnabled` at `0x140029def`
- `ntoskrnl!EtwWrite` at `0x140029e6a`
- `ntoskrnl!EtwWrite` at `0x140029e6a`

## pseudocode

```c
BOOLEAN __fastcall WimpFSFIntegrityReportIntegrityFileEvent(__int64 a1, int a2, __int64 a3, unsigned __int16 *a4)
{
  BOOLEAN result; // al
  unsigned __int16 v6; // ax
  __int16 v7; // [rsp+30h] [rbp-9h] BYREF
  __int64 v8; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp+7h] BYREF
  __int64 v10; // [rsp+50h] [rbp+17h]
  int v11; // [rsp+58h] [rbp+1Fh]
  int v12; // [rsp+5Ch] [rbp+23h]
  __int64 *v13; // [rsp+60h] [rbp+27h]
  __int64 v14; // [rsp+68h] [rbp+2Fh]
  int *v15; // [rsp+70h] [rbp+37h]
  __int64 v16; // [rsp+78h] [rbp+3Fh]
  int v17; // [rsp+A8h] [rbp+6Fh] BYREF

  v17 = a2;
  v8 = a3;
  v7 = 0;
  result = EtwEventEnabled(g_WimIntegrityEtwEventHandle, &WofIntegrityFileOpenFailureEventId);
  if ( result )
  {
    v6 = *a4;
    v11 = *a4;
    v7 = v6 >> 1;
    UserData.Ptr = (ULONGLONG)&v7;
    v10 = *((_QWORD *)a4 + 1);
    v13 = &v8;
    v15 = &v17;
    *(_QWORD *)&UserData.Size = 2;
    v12 = 0;
    v14 = 8;
    v16 = 4;
    return EtwWrite(g_WimIntegrityEtwEventHandle, &WofIntegrityFileOpenFailureEventId, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140029db0  mov     [rsp-8+arg_0], rbx
0x140029db5  mov     [rsp-8+arg_8], edx
0x140029db9  push    rbp
0x140029dba  lea     rbp, [rsp-57h]
0x140029dbf  sub     rsp, 90h
0x140029dc6  mov     rax, cs:__security_cookie
0x140029dcd  xor     rax, rsp
0x140029dd0  mov     [rbp+57h+var_10], rax
0x140029dd4  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029ddb  lea     rdx, WofIntegrityFileOpenFailureEventId; EventDescriptor
0x140029de2  xor     eax, eax
0x140029de4  mov     [rbp+57h+var_58], r8
0x140029de8  mov     [rbp+57h+var_60], ax
0x140029dec  mov     rbx, r9
0x140029def  call    cs:__imp_EtwEventEnabled
0x140029df6  nop     dword ptr [rax+rax+00h]
0x140029dfb  test    al, al
0x140029dfd  jz      short loc_140029E76
0x140029dff  movzx   ecx, word ptr [rbx]
0x140029e02  lea     rdx, WofIntegrityFileOpenFailureEventId; EventDescriptor
0x140029e09  movzx   eax, cx
0x140029e0c  mov     [rbp+57h+var_38], ecx
0x140029e0f  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029e16  mov     r9d, 4; UserDataCount
0x140029e1c  shr     ax, 1
0x140029e1f  xor     r8d, r8d; ActivityId
0x140029e22  mov     [rbp+57h+var_60], ax
0x140029e26  lea     rax, [rbp+57h+var_60]
0x140029e2a  mov     [rbp+57h+var_50.Ptr], rax
0x140029e2e  mov     rax, [rbx+8]
0x140029e32  mov     [rbp+57h+var_40], rax
0x140029e36  lea     rax, [rbp+57h+var_58]
0x140029e3a  mov     [rbp+57h+var_30], rax
0x140029e3e  lea     rax, [rbp+57h+arg_8]
0x140029e42  mov     [rbp+57h+var_20], rax
0x140029e46  lea     rax, [rbp+57h+var_50]
0x140029e4a  mov     [rsp+90h+UserData], rax; UserData
0x140029e4f  mov     qword ptr [rbp+57h+var_50.Size], 2
0x140029e57  mov     [rbp+57h+var_34], 0
0x140029e5e  mov     [rbp+57h+var_28], 8
0x140029e66  mov     [rbp+57h+var_18], r9
0x140029e6a  call    cs:__imp_EtwWrite
0x140029e71  nop     dword ptr [rax+rax+00h]
0x140029e76  mov     rcx, [rbp+57h+var_10]
0x140029e7a  xor     rcx, rsp; StackCookie
0x140029e7d  call    __security_check_cookie
0x140029e82  mov     rbx, [rsp+90h+arg_0]
0x140029e8a  add     rsp, 90h
0x140029e91  pop     rbp
0x140029e92  retn
```

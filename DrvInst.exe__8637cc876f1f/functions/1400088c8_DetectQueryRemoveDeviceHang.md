# DetectQueryRemoveDeviceHang

- ea: `0x1400088c8`
- end: `0x140008a59`
- name: `DetectQueryRemoveDeviceHang`
- size: `401`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x140009050`

## callees

- `0x1400088c8`
- `0x140008cf8`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000892c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000892c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008949`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008949`
- `DEVRTL!DevRtlWriteTextLogError` at `0x140008a04`
- `DEVRTL!DevRtlWriteTextLogError` at `0x140008a2e`
- `DEVRTL!DevRtlWriteTextLogError` at `0x140008a04`
- `DEVRTL!DevRtlWriteTextLogError` at `0x140008a2e`

## string_xrefs

- `0x140008932`: `Unable to enumerate devices pending query remove. Error = 0x%08X`
- `0x140008975`: `Detected driver hang while installing device '%ws'.`
- `0x1400089ba`: `Detected driver hang in related device '%ws' while installing device '%ws'.`
- `0x1400089c3`: `Detected driver hang in related device while installing device '%ws'.`
- `0x1400089ea`: `Detected driver hang in unrelated device '%ws' while installing device '%ws'.`
- `0x140008a0c`: `Detected driver hang in unrelated device while installing device '%ws'.`

## pseudocode

```c
__int64 __fastcall DetectQueryRemoveDeviceHang(__int64 a1, __int64 a2)
{
  DWORD LastError; // ebx
  const char *v5; // rax
  __int64 v7; // [rsp+40h] [rbp-1D8h] BYREF
  _WORD v8[200]; // [rsp+48h] [rbp-1D0h] BYREF
  int v9; // [rsp+1D8h] [rbp-40h]
  int v10; // [rsp+1DCh] [rbp-3Ch]
  __int64 v11; // [rsp+1E0h] [rbp-38h]

  memset_0(&v7, 0, 0x1A8u);
  v7 = a1;
  v9 = 0;
  v11 = a2;
  if ( !(unsigned int)EnumPendingQueryRemoveDevices(DetectQueryRemoveDeviceHangCallback, &v7) )
  {
    LastError = GetLastError();
    DevRtlWriteTextLog(a2, 1, 2, "Unable to enumerate devices pending query remove. Error = 0x%08X", LastError);
    return LastError;
  }
  LastError = 0;
  if ( !v9 )
    return LastError;
  if ( (v10 & 0x20000) != 0 )
  {
    LastError = 480;
    v5 = "Detected driver hang while installing device '%ws'.";
LABEL_14:
    DevRtlWriteTextLogError(a2, 1, 65537, LastError, v5, a1);
    return LastError;
  }
  if ( (v10 & 0x10000) == 0 )
  {
    LastError = 482;
    if ( v8[0] )
    {
      DevRtlWriteTextLogError(
        a2,
        1,
        65537,
        482,
        "Detected driver hang in unrelated device '%ws' while installing device '%ws'.",
        v8,
        a1);
      return LastError;
    }
    v5 = "Detected driver hang in unrelated device while installing device '%ws'.";
    goto LABEL_14;
  }
  LastError = 481;
  if ( v8[0] )
    DevRtlWriteTextLogError(
      a2,
      1,
      65537,
      481,
      "Detected driver hang in related device '%ws' while installing device '%ws'.",
      v8,
      a1);
  else
    DevRtlWriteTextLogError(
      a2,
      1,
      65537,
      481,
      "Detected driver hang in related device while installing device '%ws'.",
      a1);
  return LastError;
}

```

## disassembly

```asm
0x1400088c8  mov     [rsp+arg_10], rbx
0x1400088cd  push    rbp
0x1400088ce  push    rsi
0x1400088cf  push    rdi
0x1400088d0  sub     rsp, 200h
0x1400088d7  mov     rax, cs:__security_cookie
0x1400088de  xor     rax, rsp
0x1400088e1  mov     [rsp+218h+var_28], rax
0x1400088e9  mov     rdi, rdx
0x1400088ec  mov     rsi, rcx
0x1400088ef  xor     edx, edx; Val
0x1400088f1  lea     rcx, [rsp+218h+var_1D8]; void *
0x1400088f6  mov     r8d, 1A8h; Size
0x1400088fc  call    memset_0
0x140008901  xor     ebp, ebp
0x140008903  mov     [rsp+218h+var_1D8], rsi
0x140008908  lea     rdx, [rsp+218h+var_1D8]
0x14000890d  mov     [rsp+218h+var_40], ebp
0x140008914  lea     rcx, DetectQueryRemoveDeviceHangCallback
0x14000891b  mov     [rsp+218h+var_38], rdi
0x140008923  call    EnumPendingQueryRemoveDevices
0x140008928  test    eax, eax
0x14000892a  jnz     short loc_140008954
0x14000892c  call    cs:__imp_GetLastError
0x140008932  lea     r9, aUnableToEnumer; "Unable to enumerate devices pending que"...
0x140008939  mov     rcx, rdi
0x14000893c  lea     edx, [rbp+1]
0x14000893f  mov     dword ptr [rsp+218h+var_1F8], eax
0x140008943  lea     r8d, [rbp+2]
0x140008947  mov     ebx, eax
0x140008949  call    cs:__imp_DevRtlWriteTextLog
0x14000894f  jmp     loc_140008A34
0x140008954  mov     ebx, ebp
0x140008956  cmp     [rsp+218h+var_40], ebp
0x14000895d  jbe     loc_140008A34
0x140008963  test    [rsp+218h+var_3C], 20000h
0x14000896e  jz      short loc_140008981
0x140008970  mov     ebx, 1E0h
0x140008975  lea     rax, aDetectedDriver_0; "Detected driver hang while installing d"...
0x14000897c  jmp     loc_140008A13
0x140008981  test    [rsp+218h+var_3C], 10000h
0x14000898c  jz      short loc_1400089CC
0x14000898e  mov     ebx, 1E1h
0x140008993  mov     edx, 1
0x140008998  mov     r9d, ebx
0x14000899b  mov     r8d, 10001h
0x1400089a1  mov     rcx, rdi
0x1400089a4  cmp     [rsp+218h+var_1D0], bp
0x1400089a9  jz      short loc_1400089C3
0x1400089ab  lea     rax, [rsp+218h+var_1D0]
0x1400089b0  mov     [rsp+218h+var_1E8], rsi
0x1400089b5  mov     [rsp+218h+var_1F0], rax
0x1400089ba  lea     rax, aDetectedDriver; "Detected driver hang in related device "...
0x1400089c1  jmp     short loc_1400089FF
0x1400089c3  lea     rax, aDetectedDriver_2; "Detected driver hang in related device "...
0x1400089ca  jmp     short loc_140008A24
0x1400089cc  mov     ebx, 1E2h
0x1400089d1  cmp     [rsp+218h+var_1D0], bp
0x1400089d6  jz      short loc_140008A0C
0x1400089d8  lea     rax, [rsp+218h+var_1D0]
0x1400089dd  mov     [rsp+218h+var_1E8], rsi
0x1400089e2  mov     [rsp+218h+var_1F0], rax
0x1400089e7  mov     r9d, ebx
0x1400089ea  lea     rax, aDetectedDriver_1; "Detected driver hang in unrelated devic"...
0x1400089f1  mov     edx, 1
0x1400089f6  mov     r8d, 10001h
0x1400089fc  mov     rcx, rdi
0x1400089ff  mov     [rsp+218h+var_1F8], rax
0x140008a04  call    cs:__imp_DevRtlWriteTextLogError
0x140008a0a  jmp     short loc_140008A34
0x140008a0c  lea     rax, aDetectedDriver_3; "Detected driver hang in unrelated devic"...
0x140008a13  mov     r9d, ebx
0x140008a16  mov     r8d, 10001h
0x140008a1c  mov     edx, 1
0x140008a21  mov     rcx, rdi
0x140008a24  mov     [rsp+218h+var_1F0], rsi
0x140008a29  mov     [rsp+218h+var_1F8], rax
0x140008a2e  call    cs:__imp_DevRtlWriteTextLogError
0x140008a34  mov     eax, ebx
0x140008a36  mov     rcx, [rsp+218h+var_28]
0x140008a3e  xor     rcx, rsp; StackCookie
0x140008a41  call    __security_check_cookie
0x140008a46  mov     rbx, [rsp+218h+arg_10]
0x140008a4e  add     rsp, 200h
0x140008a55  pop     rdi
0x140008a56  pop     rsi
0x140008a57  pop     rbp
0x140008a58  retn
```

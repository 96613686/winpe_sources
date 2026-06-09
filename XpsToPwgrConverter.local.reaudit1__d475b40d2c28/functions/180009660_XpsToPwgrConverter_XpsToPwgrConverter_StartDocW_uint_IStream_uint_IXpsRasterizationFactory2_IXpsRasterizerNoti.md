# XpsToPwgrConverter::XpsToPwgrConverter::StartDocW(uint,IStream *,uint,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *,char const *,char const *,_CRYPT_INFO *,_DOC_SETTINGS,IFilePoolTemp *)

- ea: `0x180009660`
- end: `0x1800096df`
- name: `?StartDocW@XpsToPwgrConverter@1@UEAAJIPEAUIStream@@IPEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@PEBD3PEAU_CRYPT_INFO@@U_DOC_SETTINGS@@PEAUIFilePoolTemp@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008b34`

## pseudocode

```c
__int64 __fastcall XpsToPwgrConverter::XpsToPwgrConverter::StartDocW(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        __int64 a10,
        char a11)
{
  _QWORD v12[12]; // [rsp+20h] [rbp-60h] BYREF
  int v13; // [rsp+98h] [rbp+18h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+20h] BYREF
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v14 = a3;
  v13 = a2;
  v12[8] = a1;
  v12[0] = &a7;
  v12[1] = &a8;
  v12[2] = &a9;
  v12[3] = &v13;
  v12[4] = &a11;
  v12[5] = &v14;
  v12[6] = &a5;
  v12[7] = &a6;
  v12[9] = &v15;
  v12[10] = a10;
  return PrintCore::CaptureAndConvertExceptionToHR__lambda_623f55ecb320f80d4938f7f48b0af6f3___(v12);
}

```

## disassembly

```asm
0x180009660  mov     [rsp-8+arg_18], r9d
0x180009665  mov     [rsp-8+arg_10], r8
0x18000966a  mov     [rsp-8+arg_8], edx
0x18000966e  push    rbp
0x18000966f  mov     rbp, rsp
0x180009672  sub     rsp, 80h
0x180009679  lea     rax, [rbp+arg_30]
0x18000967d  mov     [rbp+var_20], rcx
0x180009681  mov     [rbp+var_60], rax
0x180009685  lea     rcx, [rbp+var_60]
0x180009689  lea     rax, [rbp+arg_38]
0x18000968d  mov     [rbp+var_58], rax
0x180009691  lea     rax, [rbp+arg_40]
0x180009695  mov     [rbp+var_50], rax
0x180009699  lea     rax, [rbp+arg_8]
0x18000969d  mov     [rbp+var_48], rax
0x1800096a1  lea     rax, [rbp+arg_50]
0x1800096a5  mov     [rbp+var_40], rax
0x1800096a9  lea     rax, [rbp+arg_10]
0x1800096ad  mov     [rbp+var_38], rax
0x1800096b1  lea     rax, [rbp+arg_20]
0x1800096b5  mov     [rbp+var_30], rax
0x1800096b9  lea     rax, [rbp+arg_28]
0x1800096bd  mov     [rbp+var_28], rax
0x1800096c1  lea     rax, [rbp+arg_18]
0x1800096c5  mov     [rbp+var_18], rax
0x1800096c9  mov     rax, [rbp+arg_48]
0x1800096cd  mov     [rbp+var_10], rax
0x1800096d1  call    PrintCore__CaptureAndConvertExceptionToHR__lambda_623f55ecb320f80d4938f7f48b0af6f3___
0x1800096d6  add     rsp, 80h
0x1800096dd  pop     rbp
0x1800096de  retn
```

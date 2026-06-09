# sub_1800A9EBC

- ea: `0x1800a9ebc`
- end: `0x1800aa11c`
- name: `sub_1800A9EBC`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a73f0`

## callees

- `0x180018910`
- `0x18001f8d8`
- `0x180023834`
- `0x180029f10`
- `0x180029f2c`
- `0x1800a9ebc`
- `0x1800fe010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800aa015`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800aa015`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aa047`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aa051`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aa047`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aa051`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a9f97`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a9f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f84`
- `WINSPOOL!OpenPrinterW` at `0x1800a9eef`
- `WINSPOOL!OpenPrinterW` at `0x1800a9eef`
- `WINSPOOL!GetPrinterW` at `0x1800a9f6e`
- `WINSPOOL!GetPrinterW` at `0x1800a9fd7`
- `WINSPOOL!GetPrinterW` at `0x1800a9f6e`
- `WINSPOOL!GetPrinterW` at `0x1800a9fd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall sub_1800A9EBC(WCHAR *a1, char a2, __int64 a3)
{
  __int64 v3; // rbx
  BOOL v6; // eax
  int v7; // eax
  __int64 v8; // rsi
  BYTE *v9; // rax
  BYTE *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  DWORD cbBuf; // [rsp+30h] [rbp-68h] BYREF
  HANDLE hPrinter; // [rsp+38h] [rbp-60h] BYREF
  __int64 v16; // [rsp+40h] [rbp-58h] BYREF
  __int64 v17; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-48h] BYREF
  char v19; // [rsp+60h] [rbp-38h]
  BYTE *v20; // [rsp+68h] [rbp-30h]
  char v21; // [rsp+70h] [rbp-28h]
  void *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v24; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a3;
  hPrinter = 0;
  v6 = OpenPrinterW(a1, &hPrinter, 0);
  try
  {
    if ( !v6 )
      sub_180029F10(retaddr, 16, "OnecoreUAP\\internal\\Printscan\\inc\\IppTelemetryUtils.h");
    v24 = 0;
    v7 = sub_180023834(hPrinter);
    if ( v7 < 0 )
      sub_180018910((int)retaddr, 19, (int)"OnecoreUAP\\internal\\Printscan\\inc\\IppTelemetryUtils.h", v7);
    v8 = v24;
    v18[1] = v24;
    v19 = 1;
    cbBuf = 0;
    if ( GetPrinterW(hPrinter, 5u, 0, 0, &cbBuf) )
      sub_180018910((int)retaddr, 23, (int)"OnecoreUAP\\internal\\Printscan\\inc\\IppTelemetryUtils.h", -2147418113);
    if ( GetLastError() != 122 )
      sub_180029F10(retaddr, 24, "OnecoreUAP\\internal\\Printscan\\inc\\IppTelemetryUtils.h");
    v9 = (BYTE *)_o_malloc(cbBuf);
    v10 = v9;
    if ( !v9 )
      sub_180029F2C(retaddr, 27, "OnecoreUAP\\internal\\Printscan\\inc\\IppTelemetryUtils.h");
    v20 = v9;
    v21 = 1;
    if ( !GetPrinterW(hPrinter, 5u, v9, cbBuf, &cbBuf) )
      sub_180029F10(retaddr, 30, "OnecoreUAP\\internal\\Printscan\\inc\\IppTelemetryUtils.h");
    LOBYTE(v24) = a2;
    v16 = *((_QWORD *)v10 + 1);
    v17 = *(_QWORD *)(v8 + 120);
    v18[0] = a1;
    v11 = *(_QWORD *)(v3 + 56);
    if ( !v11 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64, _QWORD *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v11 + 16LL))(
      v11,
      v18,
      &v17,
      &v16,
      &v24);
    _o_free(v10);
    _o_free(v8);
    Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(&hPrinter);
  }
  catch ( ... )
  {
    sub_180016918(retaddr, 34, "OnecoreUAP\\internal\\Printscan\\inc\\IppTelemetryUtils.h");
    v3 = a3;
  }
  v13 = *(_QWORD *)(v3 + 56);
  if ( v13 )
  {
    LOBYTE(v12) = v13 != v3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, v12);
    *(_QWORD *)(v3 + 56) = 0;
  }
}

```

## disassembly

```asm
0x1800a9ebc  mov     rax, rsp
0x1800a9ebf  mov     [rax+8], rbx
0x1800a9ec3  mov     [rax+10h], rsi
0x1800a9ec7  mov     [rax+18h], r8
0x1800a9ecb  push    rdi
0x1800a9ecc  push    r14
0x1800a9ece  push    r15
0x1800a9ed0  sub     rsp, 80h
0x1800a9ed7  mov     rbx, r8
0x1800a9eda  mov     r15b, dl
0x1800a9edd  mov     r14, rcx
0x1800a9ee0  mov     qword ptr [rax-60h], 0
0x1800a9ee8  xor     r8d, r8d; pDefault
0x1800a9eeb  lea     rdx, [rax-60h]; phPrinter
0x1800a9eef  call    cs:OpenPrinterW
0x1800a9ef5  mov     rcx, [rsp+98h]
0x1800a9efd  test    eax, eax
0x1800a9eff  jz      loc_1800AA0A9
0x1800a9f05  mov     [rsp+98h+arg_18], 0
0x1800a9f11  lea     rdx, [rsp+98h+arg_18]
0x1800a9f19  mov     rcx, [rsp+98h+hPrinter]; hPrinter
0x1800a9f1e  call    sub_180023834
0x1800a9f23  mov     rcx, [rsp+98h]
0x1800a9f2b  test    eax, eax
0x1800a9f2d  js      loc_1800AA0B8
0x1800a9f33  mov     rsi, [rsp+98h+arg_18]
0x1800a9f3b  mov     [rsp+98h+var_40], rsi
0x1800a9f40  mov     [rsp+98h+var_38], 1
0x1800a9f45  mov     [rsp+98h+cbBuf], 0
0x1800a9f4d  mov     rdi, [rsp+98h]
0x1800a9f55  lea     rax, [rsp+98h+cbBuf]
0x1800a9f5a  mov     [rsp+98h+pcbNeeded], rax; pcbNeeded
0x1800a9f5f  xor     r9d, r9d; cbBuf
0x1800a9f62  xor     r8d, r8d; pPrinter
0x1800a9f65  lea     edx, [r9+5]; Level
0x1800a9f69  mov     rcx, [rsp+98h+hPrinter]; hPrinter
0x1800a9f6e  call    cs:GetPrinterW
0x1800a9f74  test    eax, eax
0x1800a9f76  jnz     loc_1800AA0CD
0x1800a9f7c  mov     rdi, [rsp+98h]
0x1800a9f84  call    cs:__imp_GetLastError
0x1800a9f8a  cmp     eax, 7Ah ; 'z'
0x1800a9f8d  jnz     loc_1800AA0E7
0x1800a9f93  mov     ecx, [rsp+98h+cbBuf]
0x1800a9f97  call    cs:__imp__o_malloc
0x1800a9f9d  mov     rdi, rax
0x1800a9fa0  mov     rcx, [rsp+98h]
0x1800a9fa8  test    rax, rax
0x1800a9fab  jz      loc_1800AA0FB
0x1800a9fb1  mov     [rsp+98h+var_30], rdi
0x1800a9fb6  mov     [rsp+98h+var_28], 1
0x1800a9fbb  lea     rax, [rsp+98h+cbBuf]
0x1800a9fc0  mov     [rsp+98h+pcbNeeded], rax; pcbNeeded
0x1800a9fc5  mov     r9d, [rsp+98h+cbBuf]; cbBuf
0x1800a9fca  mov     r8, rdi; pPrinter
0x1800a9fcd  mov     edx, 5; Level
0x1800a9fd2  mov     rcx, [rsp+98h+hPrinter]; hPrinter
0x1800a9fd7  call    cs:GetPrinterW
0x1800a9fdd  mov     rcx, [rsp+98h]
0x1800a9fe5  test    eax, eax
0x1800a9fe7  jz      loc_1800AA10B
0x1800a9fed  mov     byte ptr [rsp+98h+arg_18], r15b
0x1800a9ff5  mov     rax, [rdi+8]
0x1800a9ff9  mov     [rsp+98h+var_58], rax
0x1800a9ffe  mov     rax, [rsi+78h]
0x1800aa002  mov     [rsp+98h+var_50], rax
0x1800aa007  mov     [rsp+98h+var_48], r14
0x1800aa00c  mov     rcx, [rbx+38h]
0x1800aa010  test    rcx, rcx
0x1800aa013  jnz     short loc_1800AA01B
0x1800aa015  call    cs:?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800aa01b  mov     rax, [rcx]
0x1800aa01e  lea     rdx, [rsp+98h+arg_18]
0x1800aa026  mov     [rsp+98h+pcbNeeded], rdx
0x1800aa02b  lea     r9, [rsp+98h+var_58]
0x1800aa030  lea     r8, [rsp+98h+var_50]
0x1800aa035  lea     rdx, [rsp+98h+var_48]
0x1800aa03a  mov     rax, [rax+10h]
0x1800aa03e  call    j__guard_dispatch_icall
0x1800aa043  nop
0x1800aa044  mov     rcx, rdi
0x1800aa047  call    cs:__imp__o_free
0x1800aa04d  nop
0x1800aa04e  mov     rcx, rsi
0x1800aa051  call    cs:__imp__o_free
0x1800aa057  nop
0x1800aa058  lea     rcx, [rsp+98h+hPrinter]; this
0x1800aa05d  call    ??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_6; Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)
0x1800aa062  nop
0x1800aa063  jmp     short loc_1800AA06D
0x1800aa065  mov     rbx, [rsp+98h+arg_10]
0x1800aa06d  mov     rcx, [rbx+38h]
0x1800aa071  test    rcx, rcx
0x1800aa074  jz      short loc_1800AA090
0x1800aa076  mov     rax, [rcx]
0x1800aa079  cmp     rcx, rbx
0x1800aa07c  setnz   dl
0x1800aa07f  mov     rax, [rax+20h]
0x1800aa083  call    j__guard_dispatch_icall
0x1800aa088  mov     qword ptr [rbx+38h], 0
0x1800aa090  lea     r11, [rsp+98h+var_18]
0x1800aa098  mov     rbx, [r11+20h]
0x1800aa09c  mov     rsi, [r11+28h]
0x1800aa0a0  mov     rsp, r11
0x1800aa0a3  pop     r15
0x1800aa0a5  pop     r14
0x1800aa0a7  pop     rdi
0x1800aa0a8  retn
0x1800aa0a9  lea     r8, aOnecoreuapInte_23; "OnecoreUAP\\internal\\Printscan\\inc\\I"...
0x1800aa0b0  lea     edx, [rax+10h]
0x1800aa0b3  call    sub_180029F10
0x1800aa0b8  mov     r9d, eax
0x1800aa0bb  lea     r8, aOnecoreuapInte_23; "OnecoreUAP\\internal\\Printscan\\inc\\I"...
0x1800aa0c2  mov     edx, 13h
0x1800aa0c7  call    sub_180018910
0x1800aa0cd  mov     r9d, 8000FFFFh
0x1800aa0d3  lea     r8, aOnecoreuapInte_23; "OnecoreUAP\\internal\\Printscan\\inc\\I"...
0x1800aa0da  mov     edx, 17h
0x1800aa0df  mov     rcx, rdi
0x1800aa0e2  call    sub_180018910
0x1800aa0e7  lea     r8, aOnecoreuapInte_23; "OnecoreUAP\\internal\\Printscan\\inc\\I"...
0x1800aa0ee  mov     edx, 18h
0x1800aa0f3  mov     rcx, rdi
0x1800aa0f6  call    sub_180029F10
0x1800aa0fb  lea     r8, aOnecoreuapInte_23; "OnecoreUAP\\internal\\Printscan\\inc\\I"...
0x1800aa102  lea     edx, [rax+1Bh]
0x1800aa105  call    sub_180029F2C
0x1800aa10b  lea     r8, aOnecoreuapInte_23; "OnecoreUAP\\internal\\Printscan\\inc\\I"...
0x1800aa112  lea     edx, [rax+1Eh]
0x1800aa115  call    sub_180029F10
```

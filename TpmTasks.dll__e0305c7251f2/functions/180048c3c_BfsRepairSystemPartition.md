# BfsRepairSystemPartition

- ea: `0x180048c3c`
- end: `0x180048ec6`
- name: `BfsRepairSystemPartition`
- size: `650`
- prototype: `__int64 __fastcall(__int64, wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x18003ee78`

## callees

- `0x18000282c`
- `0x180002858`
- `0x1800078b0`
- `0x18000858c`
- `0x180008598`
- `0x180048c3c`
- `0x180048f2c`
- `0x18004cc68`
- `0x18004ccf0`
- `0x18004cdac`
- `0x18004cdd4`
- `0x18004d778`
- `0x18004d7b4`
- `0x18004d7e4`
- `0x18004dc10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180048e79`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180048e79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048e98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d2f`

## string_xrefs

- `0x180048c99`: `\Logs\bfsvc\repair.log`
- `0x180048d38`: `BfsRepair: Failed to repair BCD store. Error: %08x`
- `0x180048cca`: `BfsRepairSystemPartition flags(0x%08x), system root: %ws, online: %ws, boot files: %ws, caller: %d`
- `0x180048d09`: `BfsRepair: BCD failed validation check after file system repair.`

## pseudocode

```c
__int64 __fastcall BfsRepairSystemPartition(__int64 a1, wchar_t *a2)
{
  __int64 LastError; // rsi
  int v4; // r14d
  DWORD v5; // r12d
  __int64 v6; // rcx
  DWORD v7; // eax
  int v8; // r13d
  DWORD v9; // edi
  unsigned int v10; // ebx
  int v12; // [rsp+30h] [rbp-D0h]
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v15; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+4Ch] [rbp-B4h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v20; // [rsp+5Ch] [rbp-A4h] BYREF
  char v21[32]; // [rsp+60h] [rbp-A0h] BYREF
  int *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  int *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  DWORD *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  int *v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  int *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  int *v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  int *v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+E8h] [rbp-18h]
  DWORD *v36; // [rsp+F0h] [rbp-10h]
  __int64 v37; // [rsp+F8h] [rbp-8h]
  wchar_t Destination[264]; // [rsp+100h] [rbp+0h] BYREF

  LODWORD(LastError) = 0;
  v13 = 0;
  v4 = 0;
  v5 = 0;
  BfspLogInitializeFromFlags(80);
  wcscpy_s(Destination, 0x104u, a2);
  wcscat_s(Destination, 0x104u, L"\\Logs\\bfsvc\\repair.log");
  BfspInitializeFileLogging(Destination);
  v12 = 2;
  BfspLogMessage(
    2,
    L"BfsRepairSystemPartition flags(0x%08x), system root: %ws, online: %ws, boot files: %ws, caller: %d",
    80,
    a2,
    L"True",
    L"None",
    v12);
  v7 = BfspChkDiskHelper(v6, &v13);
  v8 = v13;
  v9 = v7;
  if ( v13 )
    v5 = v7;
  v10 = 1;
  if ( !(unsigned int)BfsValidateBcdStore() )
  {
    v4 = 1;
    BfspLogMessage(3, L"BfsRepair: BCD failed validation check after file system repair.");
    if ( !(unsigned int)BfsInitializeBcdStoreEx(a2, 0xD144u) )
    {
      LastError = GetLastError();
      BfspLogMessage(4, L"BfsRepair: Failed to repair BCD store. Error: %08x", LastError);
    }
  }
  if ( (int)RegisterBfsTelemetryProvider() >= 0 )
  {
    if ( (unsigned int)dword_1800A3150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800A3150, 0x800000000000LL) )
    {
      v13 = 2;
      v22 = &v13;
      v23 = 4;
      v24 = &v14;
      v14 = v8;
      v26 = &v15;
      v25 = 4;
      v28 = &v16;
      v15 = v5;
      v30 = &v17;
      v32 = &v18;
      v34 = &v19;
      v36 = &v20;
      v27 = 4;
      v16 = v4;
      v29 = 4;
      v17 = LastError;
      v31 = 4;
      v18 = 0;
      v33 = 4;
      v19 = 0;
      v35 = 4;
      v20 = v9;
      v37 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800A3150, word_1800957B2, 0, 0, 10, v21);
    }
    UnregisterBfsTelemetryProvider();
  }
  if ( FileLoggingEnabled )
  {
    fclose(LogFileStream);
    LogFileStream = 0;
    FileLoggingEnabled = 0;
  }
  BfspLogDestroy();
  if ( v9 )
  {
    SetLastError(v9);
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180048c3c  push    rbp
0x180048c3e  push    rbx
0x180048c3f  push    rsi
0x180048c40  push    rdi
0x180048c41  push    r12
0x180048c43  push    r13
0x180048c45  push    r14
0x180048c47  push    r15
0x180048c49  lea     rbp, [rsp-228h]
0x180048c51  sub     rsp, 328h
0x180048c58  mov     rax, cs:__security_cookie
0x180048c5f  xor     rax, rsp
0x180048c62  mov     [rbp+260h+var_50], rax
0x180048c69  xor     esi, esi
0x180048c6b  mov     [rsp+360h+var_320], 0
0x180048c73  mov     r15, rdx
0x180048c76  xor     r14d, r14d
0x180048c79  xor     r12d, r12d
0x180048c7c  lea     edi, [rsi+50h]
0x180048c7f  mov     ecx, edi
0x180048c81  call    BfspLogInitializeFromFlags
0x180048c86  mov     ebx, 104h
0x180048c8b  lea     rcx, [rbp+260h+Destination]; Destination
0x180048c8f  mov     edx, ebx; SizeInWords
0x180048c91  mov     r8, r15; Source
0x180048c94  call    wcscpy_s
0x180048c99  lea     r8, aLogsBfsvcRepai; "\\Logs\\bfsvc\\repair.log"
0x180048ca0  mov     edx, ebx; SizeInWords
0x180048ca2  lea     rcx, [rbp+260h+Destination]; Destination
0x180048ca6  call    wcscat_s
0x180048cab  lea     rcx, [rbp+260h+Destination]; FileName
0x180048caf  call    BfspInitializeFileLogging
0x180048cb4  lea     ecx, [rsi+2]
0x180048cb7  mov     r9, r15
0x180048cba  mov     [rsp+360h+var_330], ecx
0x180048cbe  lea     rax, aNone; "None"
0x180048cc5  mov     [rsp+360h+var_338], rax
0x180048cca  lea     rdx, aBfsrepairsyste; "BfsRepairSystemPartition flags(0x%08x),"...
0x180048cd1  lea     rax, aTrue_0; "True"
0x180048cd8  mov     r8d, edi
0x180048cdb  mov     [rsp+360h+var_340], rax
0x180048ce0  call    BfspLogMessage
0x180048ce5  lea     rdx, [rsp+360h+var_320]
0x180048cea  call    BfspChkDiskHelper
0x180048cef  mov     r13d, [rsp+360h+var_320]
0x180048cf4  mov     edi, eax
0x180048cf6  test    r13d, r13d
0x180048cf9  cmovnz  r12d, eax
0x180048cfd  call    BfsValidateBcdStore
0x180048d02  lea     ebx, [rsi+1]
0x180048d05  test    eax, eax
0x180048d07  jnz     short loc_180048D4B
0x180048d09  lea     rdx, aBfsrepairBcdFa; "BfsRepair: BCD failed validation check "...
0x180048d10  mov     r14d, ebx
0x180048d13  lea     ecx, [rsi+3]
0x180048d16  call    BfspLogMessage
0x180048d1b  mov     edx, 0D144h
0x180048d20  mov     rcx, r15; Src
0x180048d23  call    BfsInitializeBcdStoreEx
0x180048d28  xor     r15d, r15d
0x180048d2b  test    eax, eax
0x180048d2d  jnz     short loc_180048D4E
0x180048d2f  call    cs:__imp_GetLastError
0x180048d35  mov     r8d, eax
0x180048d38  lea     rdx, aBfsrepairFaile_5; "BfsRepair: Failed to repair BCD store. "...
0x180048d3f  lea     ecx, [rbx+3]
0x180048d42  mov     esi, eax
0x180048d44  call    BfspLogMessage
0x180048d49  jmp     short loc_180048D4E
0x180048d4b  xor     r15d, r15d
0x180048d4e  call    RegisterBfsTelemetryProvider
0x180048d53  test    eax, eax
0x180048d55  js      loc_180048E69
0x180048d5b  mov     ecx, cs:dword_1800A3150
0x180048d61  cmp     ecx, 5
0x180048d64  jbe     loc_180048E64
0x180048d6a  mov     rdx, 800000000000h
0x180048d74  lea     rcx, dword_1800A3150
0x180048d7b  call    _tlgKeywordOn
0x180048d80  test    al, al
0x180048d82  jz      loc_180048E64
0x180048d88  lea     rax, [rsp+360h+var_320]
0x180048d8d  mov     [rsp+360h+var_320], 2
0x180048d95  mov     [rbp+260h+var_2E0], rax
0x180048d99  lea     rdx, word_1800957B2
0x180048da0  lea     rax, [rsp+360h+var_31C]
0x180048da5  mov     [rbp+260h+var_2D8], 4
0x180048dad  mov     [rbp+260h+var_2D0], rax
0x180048db1  lea     rcx, dword_1800A3150
0x180048db8  lea     rax, [rsp+360h+var_318]
0x180048dbd  mov     [rsp+360h+var_31C], r13d
0x180048dc2  mov     [rbp+260h+var_2C0], rax
0x180048dc6  xor     r9d, r9d
0x180048dc9  lea     rax, [rsp+360h+var_314]
0x180048dce  mov     [rbp+260h+var_2C8], 4
0x180048dd6  mov     [rbp+260h+var_2B0], rax
0x180048dda  xor     r8d, r8d
0x180048ddd  lea     rax, [rsp+360h+var_310]
0x180048de2  mov     [rsp+360h+var_318], r12d
0x180048de7  mov     [rbp+260h+var_2A0], rax
0x180048deb  lea     rax, [rsp+360h+var_30C]
0x180048df0  mov     [rbp+260h+var_290], rax
0x180048df4  lea     rax, [rsp+360h+var_308]
0x180048df9  mov     [rbp+260h+var_280], rax
0x180048dfd  lea     rax, [rsp+360h+var_304]
0x180048e02  mov     [rbp+260h+var_270], rax
0x180048e06  lea     rax, [rsp+360h+var_300]
0x180048e0b  mov     [rsp+360h+var_338], rax
0x180048e10  mov     dword ptr [rsp+360h+var_340], 0Ah
0x180048e18  mov     [rbp+260h+var_2B8], 4
0x180048e20  mov     [rsp+360h+var_314], r14d
0x180048e25  mov     [rbp+260h+var_2A8], 4
0x180048e2d  mov     [rsp+360h+var_310], esi
0x180048e31  mov     [rbp+260h+var_298], 4
0x180048e39  mov     [rsp+360h+var_30C], r15d
0x180048e3e  mov     [rbp+260h+var_288], 4
0x180048e46  mov     [rsp+360h+var_308], r15d
0x180048e4b  mov     [rbp+260h+var_278], 4
0x180048e53  mov     [rsp+360h+var_304], edi
0x180048e57  mov     [rbp+260h+var_268], 4
0x180048e5f  call    _tlgWriteTransfer_EventWriteTransfer
0x180048e64  call    UnregisterBfsTelemetryProvider
0x180048e69  cmp     cs:FileLoggingEnabled, r15d
0x180048e70  jz      short loc_180048E8D
0x180048e72  mov     rcx, cs:LogFileStream; Stream
0x180048e79  call    cs:__imp_fclose
0x180048e7f  mov     cs:LogFileStream, r15
0x180048e86  mov     cs:FileLoggingEnabled, r15d
0x180048e8d  call    BfspLogDestroy
0x180048e92  test    edi, edi
0x180048e94  jz      short loc_180048EA1
0x180048e96  mov     ecx, edi; dwErrCode
0x180048e98  call    cs:__imp_SetLastError
0x180048e9e  mov     ebx, r15d
0x180048ea1  mov     eax, ebx
0x180048ea3  mov     rcx, [rbp+260h+var_50]
0x180048eaa  xor     rcx, rsp; StackCookie
0x180048ead  call    __security_check_cookie
0x180048eb2  add     rsp, 328h
0x180048eb9  pop     r15
0x180048ebb  pop     r14
0x180048ebd  pop     r13
0x180048ebf  pop     r12
0x180048ec1  pop     rdi
0x180048ec2  pop     rsi
0x180048ec3  pop     rbx
0x180048ec4  pop     rbp
0x180048ec5  retn
```

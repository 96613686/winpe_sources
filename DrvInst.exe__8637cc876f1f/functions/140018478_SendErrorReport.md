# SendErrorReport

- ea: `0x140018478`
- end: `0x1400185f6`
- name: `SendErrorReport`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140012d44`
- `0x1400165ac`

## callees

- `0x140016610`
- `0x140016800`
- `0x140018478`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001850f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140018549`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140018595`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400185a6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001850f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140018549`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140018595`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400185a6`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1400184fe`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x14001853a`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1400184fe`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x14001853a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140018586`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400185cf`
- `DEVRTL!DevRtlWriteTextLog` at `0x140018586`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400185cf`
- `faultrep!ReportCoreHang` at `0x140018565`
- `faultrep!ReportCoreHang` at `0x140018565`

## pseudocode

```c
int __fastcall SendErrorReport(int a1, unsigned int a2, int a3, unsigned __int64 a4)
{
  int v7; // ebx
  int v8; // edi
  int result; // eax
  _DWORD v10[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pwzFile[264]; // [rsp+250h] [rbp+150h] BYREF

  v10[0] = a1;
  v7 = 0;
  v8 = 0;
  memset_0(pwzFile, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  if ( CreateTemporaryLogFile(pwzFile, a4) )
  {
    if ( WerRegisterFile(pwzFile, WerRegFileTypeOther, 1u) >= 0 )
      v8 = 1;
    else
      DeleteFileW(pwzFile);
  }
  if ( a3 && (unsigned int)CreateKernelDump(FileName) )
  {
    if ( WerRegisterFile(FileName, WerRegFileTypeOther, 1u) >= 0 )
      v7 = 1;
    else
      DeleteFileW(FileName);
  }
  result = ReportCoreHang(v10, 1, a2, 40);
  if ( result >= 0 )
  {
    if ( v7 )
      return DevRtlWriteTextLog(a4, 1, 5, "Successfully sent hang dump '%ws' to WER.", FileName);
  }
  else
  {
    result = DevRtlWriteTextLog(a4, 1, 2, "Unable to send hang report via WER. Status = 0x%08X", result);
    if ( v7 )
      result = DeleteFileW(FileName);
    if ( v8 )
      return DeleteFileW(pwzFile);
  }
  return result;
}

```

## disassembly

```asm
0x140018478  push    rbp
0x14001847a  push    rbx
0x14001847b  push    rsi
0x14001847c  push    rdi
0x14001847d  push    r12
0x14001847f  push    r14
0x140018481  push    r15
0x140018483  lea     rbp, [rsp-370h]
0x14001848b  sub     rsp, 470h
0x140018492  mov     rax, cs:__security_cookie
0x140018499  xor     rax, rsp
0x14001849c  mov     [rbp+3A0h+var_40], rax
0x1400184a3  mov     r14d, r8d
0x1400184a6  mov     [rsp+4A0h+var_470], ecx
0x1400184aa  mov     r15d, edx
0x1400184ad  lea     rcx, [rbp+3A0h+pwzFile]; void *
0x1400184b4  mov     r12d, 208h
0x1400184ba  xor     edx, edx; Val
0x1400184bc  mov     r8d, r12d; Size
0x1400184bf  mov     rsi, r9
0x1400184c2  xor     ebx, ebx
0x1400184c4  xor     edi, edi
0x1400184c6  call    memset_0
0x1400184cb  mov     r8d, r12d; Size
0x1400184ce  lea     rcx, [rsp+4A0h+FileName]; void *
0x1400184d3  xor     edx, edx; Val
0x1400184d5  call    memset_0
0x1400184da  mov     rdx, rsi
0x1400184dd  lea     rcx, [rbp+3A0h+pwzFile]; lpFileName
0x1400184e4  call    CreateTemporaryLogFile
0x1400184e9  lea     r12d, [rbx+1]
0x1400184ed  test    eax, eax
0x1400184ef  jz      short loc_14001851A
0x1400184f1  mov     r8d, r12d; dwFlags
0x1400184f4  lea     edx, [rbx+2]; regFileType
0x1400184f7  lea     rcx, [rbp+3A0h+pwzFile]; pwzFile
0x1400184fe  call    cs:__imp_WerRegisterFile
0x140018504  test    eax, eax
0x140018506  jns     short loc_140018517
0x140018508  lea     rcx, [rbp+3A0h+pwzFile]; lpFileName
0x14001850f  call    cs:__imp_DeleteFileW
0x140018515  jmp     short loc_14001851A
0x140018517  mov     edi, r12d
0x14001851a  test    r14d, r14d
0x14001851d  jz      short loc_140018554
0x14001851f  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x140018524  call    CreateKernelDump
0x140018529  test    eax, eax
0x14001852b  jz      short loc_140018554
0x14001852d  mov     r8d, r12d; dwFlags
0x140018530  lea     rcx, [rsp+4A0h+FileName]; pwzFile
0x140018535  mov     edx, 2; regFileType
0x14001853a  call    cs:__imp_WerRegisterFile
0x140018540  test    eax, eax
0x140018542  jns     short loc_140018551
0x140018544  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x140018549  call    cs:__imp_DeleteFileW
0x14001854f  jmp     short loc_140018554
0x140018551  mov     ebx, r12d
0x140018554  mov     r9d, 28h ; '('
0x14001855a  lea     rcx, [rsp+4A0h+var_470]
0x14001855f  mov     r8d, r15d
0x140018562  mov     edx, r12d
0x140018565  call    cs:__imp_ReportCoreHang
0x14001856b  test    eax, eax
0x14001856d  jns     short loc_1400185AE
0x14001856f  lea     r9, aUnableToSendHa; "Unable to send hang report via WER. Sta"...
0x140018576  mov     dword ptr [rsp+4A0h+var_480], eax
0x14001857a  mov     r8d, 2
0x140018580  mov     edx, r12d
0x140018583  mov     rcx, rsi
0x140018586  call    cs:__imp_DevRtlWriteTextLog
0x14001858c  test    ebx, ebx
0x14001858e  jz      short loc_14001859B
0x140018590  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x140018595  call    cs:__imp_DeleteFileW
0x14001859b  test    edi, edi
0x14001859d  jz      short loc_1400185D5
0x14001859f  lea     rcx, [rbp+3A0h+pwzFile]; lpFileName
0x1400185a6  call    cs:__imp_DeleteFileW
0x1400185ac  jmp     short loc_1400185D5
0x1400185ae  test    ebx, ebx
0x1400185b0  jz      short loc_1400185D5
0x1400185b2  lea     rax, [rsp+4A0h+FileName]
0x1400185b7  mov     r8d, 5
0x1400185bd  lea     r9, aSuccessfullySe; "Successfully sent hang dump '%ws' to WE"...
0x1400185c4  mov     [rsp+4A0h+var_480], rax
0x1400185c9  mov     edx, r12d
0x1400185cc  mov     rcx, rsi
0x1400185cf  call    cs:__imp_DevRtlWriteTextLog
0x1400185d5  mov     rcx, [rbp+3A0h+var_40]
0x1400185dc  xor     rcx, rsp; StackCookie
0x1400185df  call    __security_check_cookie
0x1400185e4  add     rsp, 470h
0x1400185eb  pop     r15
0x1400185ed  pop     r14
0x1400185ef  pop     r12
0x1400185f1  pop     rdi
0x1400185f2  pop     rsi
0x1400185f3  pop     rbx
0x1400185f4  pop     rbp
0x1400185f5  retn
```

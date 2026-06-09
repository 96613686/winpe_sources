# CExec::Tools::CopyData(void *,void *)

- ea: `0x1400130d8`
- end: `0x140013216`
- name: `?CopyData@Tools@CExec@@YAXPEAX0@Z`
- size: `318`
- prototype: `void __fastcall(HANDLE hFile, HANDLE, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140010cf4`

## callees

- `0x140002310`
- `0x140002334`
- `0x140002ecc`
- `0x14000d338`
- `0x14000e828`
- `0x140012ffc`
- `0x14001306c`
- `0x1400130d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400131bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400131bb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400131b1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400131b1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013181`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013181`

## string_xrefs

- `0x1400131eb`: `onecore\vm\compute\service\cexec\service\cexectools.cpp`
- `0x140013204`: `onecore\vm\compute\service\cexec\service\cexectools.cpp`

## pseudocode

```c
void __fastcall CExec::Tools::CopyData(HANDLE hFile, HANDLE a2, void *a3)
{
  void *v5; // rax
  _QWORD *v6; // rcx
  const void *v7; // rbx
  const char *v8; // r9
  DWORD LastError; // eax
  unsigned int lpOverlapped; // [rsp+20h] [rbp-40h]
  LPCVOID lpBuffer[2]; // [rsp+30h] [rbp-30h] BYREF
  char *v12; // [rsp+40h] [rbp-20h]
  DWORD nNumberOfBytesToWrite; // [rsp+48h] [rbp-18h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *(_OWORD *)lpBuffer = 0;
  v12 = 0;
  v5 = operator new(0x10027u);
  if ( !v5 )
    __fastfail(5u);
  v6 = (_QWORD *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v6 - 1) = v5;
  lpBuffer[0] = v6;
  v7 = v6 + 0x2000;
  v12 = (char *)(v6 + 0x2000);
  memset_0(v6, 0, 0x10000u);
  lpBuffer[1] = v7;
  *(_QWORD *)NumberOfBytesWritten = 0;
  std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(NumberOfBytesWritten);
  while ( 1 )
  {
    nNumberOfBytesToWrite = 0;
    if ( !ReadFile(hFile, (LPVOID)lpBuffer[0], LODWORD(lpBuffer[1]) - LODWORD(lpBuffer[0]), &nNumberOfBytesToWrite, 0) )
      break;
    if ( !nNumberOfBytesToWrite )
      goto LABEL_8;
    NumberOfBytesWritten[0] = 0;
    if ( !WriteFile(a2, lpBuffer[0], nNumberOfBytesToWrite, NumberOfBytesWritten, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexectools.cpp",
        v8);
  }
  LastError = GetLastError();
  if ( LastError != 109 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexectools.cpp",
      (const char *)LastError,
      lpOverlapped);
LABEL_8:
  std::vector<char>::~vector<char>(lpBuffer);
}

```

## disassembly

```asm
0x1400130d8  mov     [rsp-18h+arg_10], rbx
0x1400130dd  push    rbp
0x1400130de  push    rsi
0x1400130df  push    rdi
0x1400130e0  mov     rbp, rsp
0x1400130e3  sub     rsp, 60h
0x1400130e7  mov     rax, cs:__security_cookie
0x1400130ee  xor     rax, rsp
0x1400130f1  mov     [rbp+var_8], rax
0x1400130f5  mov     rsi, rdx
0x1400130f8  mov     rdi, rcx
0x1400130fb  xor     eax, eax
0x1400130fd  xorps   xmm1, xmm1
0x140013100  movdqu  xmmword ptr [rbp+lpBuffer], xmm1
0x140013105  mov     [rbp+var_20], rax
0x140013109  mov     ecx, 10027h; Size
0x14001310e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013113  test    rax, rax
0x140013116  jnz     short loc_14001311D
0x140013118  lea     ecx, [rax+5]
0x14001311b  int     29h; Win8: RtlFailFast(ecx)
0x14001311d  lea     rcx, [rax+27h]
0x140013121  and     rcx, 0FFFFFFFFFFFFFFE0h; void *
0x140013125  mov     [rcx-8], rax
0x140013129  mov     [rbp+lpBuffer], rcx
0x14001312d  lea     rbx, [rcx+10000h]
0x140013134  mov     [rbp+var_20], rbx
0x140013138  xor     edx, edx; Val
0x14001313a  mov     r8d, 10000h; Size
0x140013140  call    memset_0
0x140013145  mov     [rbp+lpBuffer+8], rbx
0x140013149  mov     qword ptr [rbp+NumberOfBytesWritten], 0
0x140013151  lea     rcx, [rbp+NumberOfBytesWritten]
0x140013155  call    ??1?$_Tidy_guard@V?$vector@DV?$allocator@D@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(void)
0x14001315a  nop
0x14001315b  jmp     short loc_14001318F
0x14001315d  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140013161  test    r8d, r8d
0x140013164  jz      short loc_1400131C6
0x140013166  mov     [rbp+NumberOfBytesWritten], 0
0x14001316d  mov     qword ptr [rsp+60h+lpOverlapped], 0; lpOverlapped
0x140013176  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001317a  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x14001317e  mov     rcx, rsi; hFile
0x140013181  call    cs:__imp_WriteFile
0x140013187  mov     rcx, [rbp+18h]; this
0x14001318b  test    eax, eax
0x14001318d  jz      short loc_1400131EB
0x14001318f  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x140013193  mov     r8d, dword ptr [rbp+lpBuffer+8]
0x140013197  mov     qword ptr [rsp+60h+lpOverlapped], 0; unsigned int
0x1400131a0  mov     [rbp+nNumberOfBytesToWrite], 0
0x1400131a7  lea     r9, [rbp+nNumberOfBytesToWrite]; lpNumberOfBytesRead
0x1400131ab  sub     r8d, edx; nNumberOfBytesToRead
0x1400131ae  mov     rcx, rdi; hFile
0x1400131b1  call    cs:__imp_ReadFile
0x1400131b7  test    eax, eax
0x1400131b9  jnz     short loc_14001315D
0x1400131bb  call    cs:__imp_GetLastError
0x1400131c1  cmp     eax, 6Dh ; 'm'
0x1400131c4  jnz     short loc_1400131FD
0x1400131c6  lea     rcx, [rbp+lpBuffer]
0x1400131ca  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1400131cf  mov     rcx, [rbp+var_8]
0x1400131d3  xor     rcx, rsp; StackCookie
0x1400131d6  call    __security_check_cookie
0x1400131db  mov     rbx, [rsp+60h+arg_10]
0x1400131e3  add     rsp, 60h
0x1400131e7  pop     rdi
0x1400131e8  pop     rsi
0x1400131e9  pop     rbp
0x1400131ea  retn
0x1400131eb  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\service\\cexec\\s"...
0x1400131f2  mov     edx, 38h ; '8'; void *
0x1400131f7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400131fd  mov     rcx, [rbp+18h]; this
0x140013201  mov     r9d, eax; char *
0x140013204  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\service\\cexec\\s"...
0x14001320b  mov     edx, 2Fh ; '/'; void *
0x140013210  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```

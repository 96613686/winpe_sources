# BfspPrintFileOwnerProcess

- ea: `0x140003368`
- end: `0x140003688`
- name: `BfspPrintFileOwnerProcess`
- size: `800`
- prototype: `int __fastcall(LPCWSTR lpFileName)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400030c0`
- `0x140009fd4`
- `0x14000bd28`
- `0x14000d2b4`
- `0x14000ec18`
- `0x14000ed44`

## callees

- `0x140002928`
- `0x140003368`
- `0x14000e628`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000341a`
- `KERNEL32!GetLastError` at `0x14000341a`
- `KERNEL32!HeapFree` at `0x140003613`
- `KERNEL32!HeapFree` at `0x140003636`
- `KERNEL32!HeapFree` at `0x140003670`
- `KERNEL32!HeapFree` at `0x140003613`
- `KERNEL32!HeapFree` at `0x140003636`
- `KERNEL32!HeapFree` at `0x140003670`
- `KERNEL32!HeapAlloc` at `0x140003451`
- `KERNEL32!HeapAlloc` at `0x140003582`
- `KERNEL32!HeapAlloc` at `0x140003451`
- `KERNEL32!HeapAlloc` at `0x140003582`
- `KERNEL32!GetProcessHeap` at `0x140003440`
- `KERNEL32!GetProcessHeap` at `0x140003571`
- `KERNEL32!GetProcessHeap` at `0x140003605`
- `KERNEL32!GetProcessHeap` at `0x140003628`
- `KERNEL32!GetProcessHeap` at `0x140003662`
- `KERNEL32!GetProcessHeap` at `0x140003440`
- `KERNEL32!GetProcessHeap` at `0x140003571`
- `KERNEL32!GetProcessHeap` at `0x140003605`
- `KERNEL32!GetProcessHeap` at `0x140003628`
- `KERNEL32!GetProcessHeap` at `0x140003662`
- `KERNEL32!CreateFileW` at `0x14000340b`
- `KERNEL32!CreateFileW` at `0x14000340b`
- `KERNEL32!CloseHandle` at `0x14000363f`
- `KERNEL32!CloseHandle` at `0x14000363f`
- `ntdll!NtQueryInformationFile` at `0x140003479`
- `ntdll!NtQueryInformationFile` at `0x140003479`
- `ntdll!NtClose` at `0x1400035f6`
- `ntdll!NtClose` at `0x1400035f6`
- `ntdll!NtOpenProcess` at `0x14000350f`
- `ntdll!NtOpenProcess` at `0x14000350f`
- `ntdll!NtQueryInformationProcess` at `0x14000354a`
- `ntdll!NtQueryInformationProcess` at `0x1400035b6`
- `ntdll!NtQueryInformationProcess` at `0x14000354a`
- `ntdll!NtQueryInformationProcess` at `0x1400035b6`

## string_xrefs

- `0x1400033d3`: `BfspPrintFileOwnerProcess: Failed to acquire debugprivilege`
- `0x140003423`: `BfspPrintFileOwnerProcess: Failed to open file!Last Error = %#x`
- `0x140003519`: `BfspPrintFileOwnerProcess: NtOpenProcess failed!Status = %#x`

## pseudocode

```c
int __fastcall BfspPrintFileOwnerProcess(LPCWSTR lpFileName)
{
  int result; // eax
  HANDLE FileW; // r14
  DWORD LastError; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rax
  _DWORD *v7; // rsi
  NTSTATUS v8; // eax
  const wchar_t *v9; // rdx
  _QWORD *v10; // rbx
  int v11; // r15d
  NTSTATUS v12; // eax
  const wchar_t *v13; // rdx
  ULONG v14; // ebx
  HANDLE v15; // rax
  const wchar_t *v16; // r8
  HANDLE v17; // rax
  HANDLE v18; // rax
  void *v19; // rbx
  HANDLE v20; // rax
  _CLIENT_ID ClientId; // [rsp+40h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  ULONG Length; // [rsp+D0h] [rbp+67h] BYREF
  void *ProcessHandle; // [rsp+D8h] [rbp+6Fh] BYREF
  LPVOID lpMem; // [rsp+E0h] [rbp+77h]

  result = 0;
  ProcessHandle = 0;
  Length = 0;
  lpMem = 0;
  ClientId = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !lpFileName || !LogEnabled )
    return result;
  if ( !(unsigned int)BfspAdjustDebugPrivilege(1u) )
  {
    result = BfspLogMessage(4, L"BfspPrintFileOwnerProcess: Failed to acquire debugprivilege");
    goto LABEL_36;
  }
  FileW = CreateFileW(lpFileName, 0x100080u, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    result = BfspLogMessage(4, L"BfspPrintFileOwnerProcess: Failed to open file!Last Error = %#x", LastError);
    goto LABEL_36;
  }
  Length = 1024;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x400u);
  v7 = v6;
  if ( v6 )
  {
    v8 = NtQueryInformationFile(FileW, &IoStatusBlock, v6, Length, FileProcessIdsUsingFileInformation);
    if ( v8 < 0 )
    {
      BfspLogMessage(4, L"BfspPrintFileOwnerProcess: NtQueryInformationFilefailed! Status = %#x", (unsigned int)v8);
LABEL_34:
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v7);
      goto LABEL_35;
    }
    v9 = L"Printing processes using %s file.";
    if ( !*v7 )
      v9 = L"No process found using %s file.";
    BfspLogMessage(4, v9, lpFileName);
    ProcessHandle = 0;
    v10 = 0;
    v11 = 0;
    if ( !*v7 )
      goto LABEL_34;
    while ( 1 )
    {
      ClientId.UniqueThread = 0;
      ClientId.UniqueProcess = *(HANDLE *)&v7[2 * v11 + 2];
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v12 = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
      if ( v12 < 0 )
        break;
      Length = 0;
      v12 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, 0, 0, &Length);
      if ( v12 != -2147483643 && v12 != -1073741789 && v12 != -1073741820 )
      {
        v13 = L"BfspPrintFileOwnerProcess: NtQueryInformationProcessfailed in unexpected manner! Status = %#x";
        goto LABEL_15;
      }
      v14 = Length;
      v15 = GetProcessHeap();
      v10 = HeapAlloc(v15, 8u, v14);
      if ( v10 )
      {
        v12 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, v10, Length, &Length);
        if ( v12 >= 0 )
        {
          if ( *(_WORD *)v10 )
            v16 = (const wchar_t *)v10[1];
          else
            v16 = L"System";
          BfspLogMessage(4, L"Process Name = %s", v16);
          goto LABEL_29;
        }
        v13 = L"BfspPrintFileOwnerProcess: NtQueryInformationProcessfailed! Status = %#x";
        goto LABEL_15;
      }
      BfspLogMessage(4, L"BfspPrintFileOwnerProcess: Malloc failed!Size = %#x", Length);
LABEL_29:
      if ( ProcessHandle )
      {
        NtClose(ProcessHandle);
        ProcessHandle = 0;
      }
      if ( v10 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v10);
        v10 = 0;
      }
      if ( (unsigned int)++v11 >= *v7 )
        goto LABEL_34;
    }
    v13 = L"BfspPrintFileOwnerProcess: NtOpenProcess failed!Status = %#x";
LABEL_15:
    BfspLogMessage(4, v13, (unsigned int)v12);
    goto LABEL_29;
  }
LABEL_35:
  result = CloseHandle(FileW);
LABEL_36:
  v19 = lpMem;
  if ( lpMem )
  {
    if ( *(_DWORD *)lpMem != 1 || (*((_BYTE *)lpMem + 12) & 2) == 0 )
      BfspAdjustDebugPrivilege(0);
    v20 = GetProcessHeap();
    return HeapFree(v20, 0, v19);
  }
  return result;
}

```

## disassembly

```asm
0x140003368  push    rbp
0x14000336a  push    rbx
0x14000336b  push    rsi
0x14000336c  push    rdi
0x14000336d  push    r12
0x14000336f  push    r14
0x140003371  push    r15
0x140003373  lea     rbp, [rsp-27h]
0x140003378  sub     rsp, 90h
0x14000337f  xorps   xmm0, xmm0
0x140003382  xor     r12d, r12d
0x140003385  xor     eax, eax
0x140003387  mov     [rbp+57h+ProcessHandle], r12
0x14000338b  mov     [rbp+57h+Length], r12d
0x14000338f  xorps   xmm1, xmm1
0x140003392  mov     [rbp+57h+lpMem], r12
0x140003396  mov     rbx, rcx
0x140003399  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000339d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400033a1  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x1400033a5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1400033a9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400033ad  test    rcx, rcx
0x1400033b0  jz      loc_140003676
0x1400033b6  cmp     cs:LogEnabled, r12d
0x1400033bd  jz      loc_140003676
0x1400033c3  lea     rdx, [rbp+57h+lpMem]
0x1400033c7  lea     ecx, [rax+1]
0x1400033ca  call    BfspAdjustDebugPrivilege
0x1400033cf  test    eax, eax
0x1400033d1  jnz     short loc_1400033E7
0x1400033d3  lea     rdx, aBfspprintfileo_1; "BfspPrintFileOwnerProcess: Failed to ac"...
0x1400033da  lea     ecx, [rax+4]
0x1400033dd  call    BfspLogMessage
0x1400033e2  jmp     loc_140003645
0x1400033e7  xor     r9d, r9d; lpSecurityAttributes
0x1400033ea  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x1400033ef  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400033f7  mov     edx, 100080h; dwDesiredAccess
0x1400033fc  mov     rcx, rbx; lpFileName
0x1400033ff  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x140003407  lea     r8d, [r9+7]; dwShareMode
0x14000340b  call    cs:__imp_CreateFileW
0x140003411  mov     r14, rax
0x140003414  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003418  jnz     short loc_140003438
0x14000341a  call    cs:__imp_GetLastError
0x140003420  mov     r8d, eax
0x140003423  lea     rdx, aBfspprintfileo_2; "BfspPrintFileOwnerProcess: Failed to op"...
0x14000342a  lea     ecx, [r14+5]
0x14000342e  call    BfspLogMessage
0x140003433  jmp     loc_140003645
0x140003438  mov     edi, 400h
0x14000343d  mov     [rbp+57h+Length], edi
0x140003440  call    cs:__imp_GetProcessHeap
0x140003446  mov     r8d, edi; dwBytes
0x140003449  mov     edx, 8; dwFlags
0x14000344e  mov     rcx, rax; hHeap
0x140003451  call    cs:__imp_HeapAlloc
0x140003457  mov     rsi, rax
0x14000345a  test    rax, rax
0x14000345d  jz      loc_14000363C
0x140003463  mov     r9d, [rbp+57h+Length]; Length
0x140003467  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000346b  mov     r8, rax; FileInformation
0x14000346e  mov     [rsp+0C0h+dwCreationDisposition], 2Fh ; '/'; FileInformationClass
0x140003476  mov     rcx, r14; FileHandle
0x140003479  call    cs:__imp_NtQueryInformationFile
0x14000347f  test    eax, eax
0x140003481  jns     short loc_14000349C
0x140003483  mov     r8d, eax
0x140003486  lea     rdx, aBfspprintfileo_0; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x14000348d  mov     ecx, 4
0x140003492  call    BfspLogMessage
0x140003497  jmp     loc_140003628
0x14000349c  cmp     [rsi], r12d
0x14000349f  lea     rax, aNoProcessFound; "No process found using %s file."
0x1400034a6  lea     rdx, aPrintingProces; "Printing processes using %s file."
0x1400034ad  mov     edi, 4
0x1400034b2  cmovbe  rdx, rax
0x1400034b6  mov     r8, rbx
0x1400034b9  mov     ecx, edi
0x1400034bb  call    BfspLogMessage
0x1400034c0  mov     [rbp+57h+ProcessHandle], r12
0x1400034c4  mov     rbx, r12
0x1400034c7  mov     r15d, r12d
0x1400034ca  cmp     [rsi], r12d
0x1400034cd  jbe     loc_140003628
0x1400034d3  mov     eax, r15d
0x1400034d6  lea     r9, [rbp+57h+ClientId]; ClientId
0x1400034da  mov     [rbp+57h+ClientId.UniqueThread], r12
0x1400034de  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400034e2  xorps   xmm0, xmm0
0x1400034e5  mov     edx, 1000h; DesiredAccess
0x1400034ea  mov     rcx, [rsi+rax*8+8]
0x1400034ef  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x1400034f3  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1400034f7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400034fe  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140003502  mov     [rbp+57h+ObjectAttributes.Attributes], r12d
0x140003506  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x14000350a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000350f  call    cs:__imp_NtOpenProcess
0x140003515  test    eax, eax
0x140003517  jns     short loc_14000352F
0x140003519  lea     rdx, aBfspprintfileo; "BfspPrintFileOwnerProcess: NtOpenProces"...
0x140003520  mov     r8d, eax
0x140003523  mov     ecx, edi
0x140003525  call    BfspLogMessage
0x14000352a  jmp     loc_1400035ED
0x14000352f  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140003533  lea     rax, [rbp+57h+Length]
0x140003537  xor     r9d, r9d; ProcessInformationLength
0x14000353a  mov     [rbp+57h+Length], r12d
0x14000353e  xor     r8d, r8d; ProcessInformation
0x140003541  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; ReturnLength
0x140003546  lea     edx, [r9+1Bh]; ProcessInformationClass
0x14000354a  call    cs:__imp_NtQueryInformationProcess
0x140003550  cmp     eax, 80000005h
0x140003555  jz      short loc_14000356E
0x140003557  cmp     eax, 0C0000023h
0x14000355c  jz      short loc_14000356E
0x14000355e  cmp     eax, 0C0000004h
0x140003563  jz      short loc_14000356E
0x140003565  lea     rdx, aBfspprintfileo_5; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x14000356c  jmp     short loc_140003520
0x14000356e  mov     ebx, [rbp+57h+Length]
0x140003571  call    cs:__imp_GetProcessHeap
0x140003577  mov     r8d, ebx; dwBytes
0x14000357a  mov     edx, 8; dwFlags
0x14000357f  mov     rcx, rax; hHeap
0x140003582  call    cs:__imp_HeapAlloc
0x140003588  mov     rbx, rax
0x14000358b  test    rax, rax
0x14000358e  jnz     short loc_14000359D
0x140003590  mov     r8d, [rbp+57h+Length]
0x140003594  lea     rdx, aBfspprintfileo_3; "BfspPrintFileOwnerProcess: Malloc faile"...
0x14000359b  jmp     short loc_140003523
0x14000359d  mov     r9d, [rbp+57h+Length]; ProcessInformationLength
0x1400035a1  lea     rax, [rbp+57h+Length]
0x1400035a5  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1400035a9  mov     r8, rbx; ProcessInformation
0x1400035ac  mov     edx, 1Bh; ProcessInformationClass
0x1400035b1  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; ReturnLength
0x1400035b6  call    cs:__imp_NtQueryInformationProcess
0x1400035bc  test    eax, eax
0x1400035be  jns     short loc_1400035CC
0x1400035c0  lea     rdx, aBfspprintfileo_4; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x1400035c7  jmp     loc_140003520
0x1400035cc  lea     rdx, aProcessNameS; "Process Name = %s"
0x1400035d3  mov     ecx, edi
0x1400035d5  cmp     [rbx], r12w
0x1400035d9  jbe     short loc_1400035E1
0x1400035db  mov     r8, [rbx+8]
0x1400035df  jmp     short loc_1400035E8
0x1400035e1  lea     r8, aSystem; "System"
0x1400035e8  call    BfspLogMessage
0x1400035ed  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x1400035f1  test    rcx, rcx
0x1400035f4  jz      short loc_140003600
0x1400035f6  call    cs:__imp_NtClose
0x1400035fc  mov     [rbp+57h+ProcessHandle], r12
0x140003600  test    rbx, rbx
0x140003603  jz      short loc_14000361C
0x140003605  call    cs:__imp_GetProcessHeap
0x14000360b  mov     r8, rbx; lpMem
0x14000360e  xor     edx, edx; dwFlags
0x140003610  mov     rcx, rax; hHeap
0x140003613  call    cs:__imp_HeapFree
0x140003619  mov     rbx, r12
0x14000361c  inc     r15d
0x14000361f  cmp     r15d, [rsi]
0x140003622  jb      loc_1400034D3
0x140003628  call    cs:__imp_GetProcessHeap
0x14000362e  mov     r8, rsi; lpMem
0x140003631  xor     edx, edx; dwFlags
0x140003633  mov     rcx, rax; hHeap
0x140003636  call    cs:__imp_HeapFree
0x14000363c  mov     rcx, r14; hObject
0x14000363f  call    cs:__imp_CloseHandle
0x140003645  mov     rbx, [rbp+57h+lpMem]
0x140003649  test    rbx, rbx
0x14000364c  jz      short loc_140003676
0x14000364e  cmp     dword ptr [rbx], 1
0x140003651  jnz     short loc_140003659
0x140003653  test    byte ptr [rbx+0Ch], 2
0x140003657  jnz     short loc_140003662
0x140003659  xor     edx, edx
0x14000365b  xor     ecx, ecx
0x14000365d  call    BfspAdjustDebugPrivilege
0x140003662  call    cs:__imp_GetProcessHeap
0x140003668  mov     r8, rbx; lpMem
0x14000366b  xor     edx, edx; dwFlags
0x14000366d  mov     rcx, rax; hHeap
0x140003670  call    cs:__imp_HeapFree
0x140003676  add     rsp, 90h
0x14000367d  pop     r15
0x14000367f  pop     r14
0x140003681  pop     r12
0x140003683  pop     rdi
0x140003684  pop     rsi
0x140003685  pop     rbx
0x140003686  pop     rbp
0x140003687  retn
```

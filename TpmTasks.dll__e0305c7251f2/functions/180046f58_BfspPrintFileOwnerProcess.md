# BfspPrintFileOwnerProcess

- ea: `0x180046f58`
- end: `0x180047278`
- name: `BfspPrintFileOwnerProcess`
- size: `800`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180047280`

## callees

- `0x18004646c`
- `0x180046f58`
- `0x18004cdd4`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180047069`
- `ntdll!NtQueryInformationFile` at `0x180047069`
- `ntdll!NtOpenProcess` at `0x1800470ff`
- `ntdll!NtOpenProcess` at `0x1800470ff`
- `ntdll!NtQueryInformationProcess` at `0x18004713a`
- `ntdll!NtQueryInformationProcess` at `0x1800471a6`
- `ntdll!NtQueryInformationProcess` at `0x18004713a`
- `ntdll!NtQueryInformationProcess` at `0x1800471a6`
- `ntdll!NtClose` at `0x1800471e6`
- `ntdll!NtClose` at `0x1800471e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046ffb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046ffb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047260`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047260`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800471f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047218`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047252`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800471f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047218`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047252`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047041`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047172`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047041`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004700a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004700a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004722f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004722f`

## string_xrefs

- `0x180047013`: `BfspPrintFileOwnerProcess: Failed to open file!Last Error = %#x`
- `0x180046fc3`: `BfspPrintFileOwnerProcess: Failed to acquire debugprivilege`
- `0x180047109`: `BfspPrintFileOwnerProcess: NtOpenProcess failed!Status = %#x`

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
  LPVOID lpMem; // [rsp+E0h] [rbp+77h] BYREF

  result = 0;
  ProcessHandle = 0;
  Length = 0;
  lpMem = 0;
  ClientId = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !lpFileName || !LogEnabled )
    return result;
  if ( !(unsigned int)BfspAdjustDebugPrivilege(1, &lpMem) )
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
      BfspAdjustDebugPrivilege(0, 0);
    v20 = GetProcessHeap();
    return HeapFree(v20, 0, v19);
  }
  return result;
}

```

## disassembly

```asm
0x180046f58  push    rbp
0x180046f5a  push    rbx
0x180046f5b  push    rsi
0x180046f5c  push    rdi
0x180046f5d  push    r12
0x180046f5f  push    r14
0x180046f61  push    r15
0x180046f63  lea     rbp, [rsp-27h]
0x180046f68  sub     rsp, 90h
0x180046f6f  xorps   xmm0, xmm0
0x180046f72  xor     r12d, r12d
0x180046f75  xor     eax, eax
0x180046f77  mov     [rbp+57h+ProcessHandle], r12
0x180046f7b  mov     [rbp+57h+Length], r12d
0x180046f7f  xorps   xmm1, xmm1
0x180046f82  mov     [rbp+57h+lpMem], r12
0x180046f86  mov     rbx, rcx
0x180046f89  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180046f8d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180046f91  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x180046f95  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180046f99  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180046f9d  test    rcx, rcx
0x180046fa0  jz      loc_180047266
0x180046fa6  cmp     cs:LogEnabled, r12d
0x180046fad  jz      loc_180047266
0x180046fb3  lea     rdx, [rbp+57h+lpMem]
0x180046fb7  lea     ecx, [rax+1]
0x180046fba  call    BfspAdjustDebugPrivilege
0x180046fbf  test    eax, eax
0x180046fc1  jnz     short loc_180046FD7
0x180046fc3  lea     rdx, aBfspprintfileo_1; "BfspPrintFileOwnerProcess: Failed to ac"...
0x180046fca  lea     ecx, [rax+4]
0x180046fcd  call    BfspLogMessage
0x180046fd2  jmp     loc_180047235
0x180046fd7  xor     r9d, r9d; lpSecurityAttributes
0x180046fda  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x180046fdf  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180046fe7  mov     edx, 100080h; dwDesiredAccess
0x180046fec  mov     rcx, rbx; lpFileName
0x180046fef  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180046ff7  lea     r8d, [r9+7]; dwShareMode
0x180046ffb  call    cs:__imp_CreateFileW
0x180047001  mov     r14, rax
0x180047004  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047008  jnz     short loc_180047028
0x18004700a  call    cs:__imp_GetLastError
0x180047010  mov     r8d, eax
0x180047013  lea     rdx, aBfspprintfileo_2; "BfspPrintFileOwnerProcess: Failed to op"...
0x18004701a  lea     ecx, [r14+5]
0x18004701e  call    BfspLogMessage
0x180047023  jmp     loc_180047235
0x180047028  mov     edi, 400h
0x18004702d  mov     [rbp+57h+Length], edi
0x180047030  call    cs:__imp_GetProcessHeap
0x180047036  mov     r8d, edi; dwBytes
0x180047039  mov     edx, 8; dwFlags
0x18004703e  mov     rcx, rax; hHeap
0x180047041  call    cs:__imp_HeapAlloc
0x180047047  mov     rsi, rax
0x18004704a  test    rax, rax
0x18004704d  jz      loc_18004722C
0x180047053  mov     r9d, [rbp+57h+Length]; Length
0x180047057  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18004705b  mov     r8, rax; FileInformation
0x18004705e  mov     [rsp+0C0h+dwCreationDisposition], 2Fh ; '/'; FileInformationClass
0x180047066  mov     rcx, r14; FileHandle
0x180047069  call    cs:__imp_NtQueryInformationFile
0x18004706f  test    eax, eax
0x180047071  jns     short loc_18004708C
0x180047073  mov     r8d, eax
0x180047076  lea     rdx, aBfspprintfileo_0; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x18004707d  mov     ecx, 4
0x180047082  call    BfspLogMessage
0x180047087  jmp     loc_180047218
0x18004708c  cmp     [rsi], r12d
0x18004708f  lea     rax, aNoProcessFound; "No process found using %s file."
0x180047096  lea     rdx, aPrintingProces; "Printing processes using %s file."
0x18004709d  mov     edi, 4
0x1800470a2  cmovbe  rdx, rax
0x1800470a6  mov     r8, rbx
0x1800470a9  mov     ecx, edi
0x1800470ab  call    BfspLogMessage
0x1800470b0  mov     [rbp+57h+ProcessHandle], r12
0x1800470b4  mov     rbx, r12
0x1800470b7  mov     r15d, r12d
0x1800470ba  cmp     [rsi], r12d
0x1800470bd  jbe     loc_180047218
0x1800470c3  mov     eax, r15d
0x1800470c6  lea     r9, [rbp+57h+ClientId]; ClientId
0x1800470ca  mov     [rbp+57h+ClientId.UniqueThread], r12
0x1800470ce  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800470d2  xorps   xmm0, xmm0
0x1800470d5  mov     edx, 1000h; DesiredAccess
0x1800470da  mov     rcx, [rsi+rax*8+8]
0x1800470df  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x1800470e3  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800470e7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800470ee  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1800470f2  mov     [rbp+57h+ObjectAttributes.Attributes], r12d
0x1800470f6  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x1800470fa  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800470ff  call    cs:__imp_NtOpenProcess
0x180047105  test    eax, eax
0x180047107  jns     short loc_18004711F
0x180047109  lea     rdx, aBfspprintfileo; "BfspPrintFileOwnerProcess: NtOpenProces"...
0x180047110  mov     r8d, eax
0x180047113  mov     ecx, edi
0x180047115  call    BfspLogMessage
0x18004711a  jmp     loc_1800471DD
0x18004711f  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180047123  lea     rax, [rbp+57h+Length]
0x180047127  xor     r9d, r9d; ProcessInformationLength
0x18004712a  mov     [rbp+57h+Length], r12d
0x18004712e  xor     r8d, r8d; ProcessInformation
0x180047131  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; ReturnLength
0x180047136  lea     edx, [r9+1Bh]; ProcessInformationClass
0x18004713a  call    cs:__imp_NtQueryInformationProcess
0x180047140  cmp     eax, 80000005h
0x180047145  jz      short loc_18004715E
0x180047147  cmp     eax, 0C0000023h
0x18004714c  jz      short loc_18004715E
0x18004714e  cmp     eax, 0C0000004h
0x180047153  jz      short loc_18004715E
0x180047155  lea     rdx, aBfspprintfileo_5; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x18004715c  jmp     short loc_180047110
0x18004715e  mov     ebx, [rbp+57h+Length]
0x180047161  call    cs:__imp_GetProcessHeap
0x180047167  mov     r8d, ebx; dwBytes
0x18004716a  mov     edx, 8; dwFlags
0x18004716f  mov     rcx, rax; hHeap
0x180047172  call    cs:__imp_HeapAlloc
0x180047178  mov     rbx, rax
0x18004717b  test    rax, rax
0x18004717e  jnz     short loc_18004718D
0x180047180  mov     r8d, [rbp+57h+Length]
0x180047184  lea     rdx, aBfspprintfileo_3; "BfspPrintFileOwnerProcess: Malloc faile"...
0x18004718b  jmp     short loc_180047113
0x18004718d  mov     r9d, [rbp+57h+Length]; ProcessInformationLength
0x180047191  lea     rax, [rbp+57h+Length]
0x180047195  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180047199  mov     r8, rbx; ProcessInformation
0x18004719c  mov     edx, 1Bh; ProcessInformationClass
0x1800471a1  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; ReturnLength
0x1800471a6  call    cs:__imp_NtQueryInformationProcess
0x1800471ac  test    eax, eax
0x1800471ae  jns     short loc_1800471BC
0x1800471b0  lea     rdx, aBfspprintfileo_4; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x1800471b7  jmp     loc_180047110
0x1800471bc  lea     rdx, aProcessNameS; "Process Name = %s"
0x1800471c3  mov     ecx, edi
0x1800471c5  cmp     [rbx], r12w
0x1800471c9  jbe     short loc_1800471D1
0x1800471cb  mov     r8, [rbx+8]
0x1800471cf  jmp     short loc_1800471D8
0x1800471d1  lea     r8, aSystem; "System"
0x1800471d8  call    BfspLogMessage
0x1800471dd  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x1800471e1  test    rcx, rcx
0x1800471e4  jz      short loc_1800471F0
0x1800471e6  call    cs:__imp_NtClose
0x1800471ec  mov     [rbp+57h+ProcessHandle], r12
0x1800471f0  test    rbx, rbx
0x1800471f3  jz      short loc_18004720C
0x1800471f5  call    cs:__imp_GetProcessHeap
0x1800471fb  mov     r8, rbx; lpMem
0x1800471fe  xor     edx, edx; dwFlags
0x180047200  mov     rcx, rax; hHeap
0x180047203  call    cs:__imp_HeapFree
0x180047209  mov     rbx, r12
0x18004720c  inc     r15d
0x18004720f  cmp     r15d, [rsi]
0x180047212  jb      loc_1800470C3
0x180047218  call    cs:__imp_GetProcessHeap
0x18004721e  mov     r8, rsi; lpMem
0x180047221  xor     edx, edx; dwFlags
0x180047223  mov     rcx, rax; hHeap
0x180047226  call    cs:__imp_HeapFree
0x18004722c  mov     rcx, r14; hObject
0x18004722f  call    cs:__imp_CloseHandle
0x180047235  mov     rbx, [rbp+57h+lpMem]
0x180047239  test    rbx, rbx
0x18004723c  jz      short loc_180047266
0x18004723e  cmp     dword ptr [rbx], 1
0x180047241  jnz     short loc_180047249
0x180047243  test    byte ptr [rbx+0Ch], 2
0x180047247  jnz     short loc_180047252
0x180047249  xor     edx, edx
0x18004724b  xor     ecx, ecx
0x18004724d  call    BfspAdjustDebugPrivilege
0x180047252  call    cs:__imp_GetProcessHeap
0x180047258  mov     r8, rbx; lpMem
0x18004725b  xor     edx, edx; dwFlags
0x18004725d  mov     rcx, rax; hHeap
0x180047260  call    cs:__imp_HeapFree
0x180047266  add     rsp, 90h
0x18004726d  pop     r15
0x18004726f  pop     r14
0x180047271  pop     r12
0x180047273  pop     rdi
0x180047274  pop     rsi
0x180047275  pop     rbx
0x180047276  pop     rbp
0x180047277  retn
```

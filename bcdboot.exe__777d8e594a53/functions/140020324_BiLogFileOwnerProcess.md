# BiLogFileOwnerProcess

- ea: `0x140020324`
- end: `0x140020671`
- name: `BiLogFileOwnerProcess`
- size: `845`
- prototype: `char __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001b764`

## callees

- `0x1400133e4`
- `0x140020324`

## import_xrefs

- `ntdll!ZwClose` at `0x140020596`
- `ntdll!ZwClose` at `0x14002060b`
- `ntdll!ZwClose` at `0x140020654`
- `ntdll!ZwClose` at `0x140020596`
- `ntdll!ZwClose` at `0x14002060b`
- `ntdll!ZwClose` at `0x140020654`
- `ntdll!ZwQueryInformationProcess` at `0x140020507`
- `ntdll!ZwQueryInformationProcess` at `0x140020564`
- `ntdll!ZwQueryInformationProcess` at `0x140020507`
- `ntdll!ZwQueryInformationProcess` at `0x140020564`
- `ntdll!ZwQueryInformationFile` at `0x14002045a`
- `ntdll!ZwQueryInformationFile` at `0x14002045a`
- `ntdll!ZwOpenProcess` at `0x1400204de`
- `ntdll!ZwOpenProcess` at `0x1400204de`
- `ntdll!RtlAllocateHeap` at `0x14002041f`
- `ntdll!RtlAllocateHeap` at `0x140020539`
- `ntdll!RtlAllocateHeap` at `0x14002041f`
- `ntdll!RtlAllocateHeap` at `0x140020539`
- `ntdll!RtlFreeHeap` at `0x1400205b2`
- `ntdll!RtlFreeHeap` at `0x140020628`
- `ntdll!RtlFreeHeap` at `0x140020645`
- `ntdll!RtlFreeHeap` at `0x1400205b2`
- `ntdll!RtlFreeHeap` at `0x140020628`
- `ntdll!RtlFreeHeap` at `0x140020645`
- `ntdll!ZwOpenFile` at `0x1400203e0`
- `ntdll!ZwOpenFile` at `0x1400203e0`

## string_xrefs

- `0x140020392`: `Attempting to determine owner of file %ws.`
- `0x1400203ed`: `Failed to open file attributes. Status: %x`
- `0x1400205ee`: `Failed to open process. Status: %x`

## pseudocode

```c
char __fastcall BiLogFileOwnerProcess(struct _UNICODE_STRING *a1)
{
  char result; // al
  _QWORD *v3; // rdi
  NTSTATUS v4; // eax
  unsigned int *v5; // rsi
  const wchar_t *v6; // rdx
  unsigned int *Heap; // rax
  const wchar_t *v8; // rdx
  unsigned int v9; // r14d
  NTSTATUS v10; // eax
  unsigned int v11; // eax
  NTSTATUS v12; // eax
  const wchar_t *v13; // r9
  struct _CLIENT_ID ClientId; // [rsp+30h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES v17; // [rsp+80h] [rbp+7h] BYREF
  ULONG Length; // [rsp+E8h] [rbp+6Fh] BYREF
  void *ProcessHandle; // [rsp+F0h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  result = 0;
  Length = 0;
  ProcessHandle = 0;
  FileHandle = 0;
  ClientId = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v17, 0, 44);
  if ( byte_14003F840 )
  {
    v3 = 0;
    BiLogMessage(2, L"Attempting to determine owner of file %ws.", a1->Buffer);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = a1;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u);
    if ( v4 < 0 )
    {
      v5 = 0;
      v6 = L"Failed to open file attributes. Status: %x";
LABEL_4:
      result = BiLogMessage(4, v6, (unsigned int)v4);
      goto LABEL_29;
    }
    Length = 1024;
    Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
    v5 = Heap;
    if ( Heap )
    {
      v4 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, Heap, Length, FileProcessIdsUsingFileInformation);
      if ( v4 < 0 )
      {
        v6 = L"Failed to query processes. Status: %x";
        goto LABEL_4;
      }
      if ( *v5 )
      {
        BiLogMessage(2, L"Found %d processes using this file.");
        ProcessHandle = 0;
        v9 = 0;
        if ( !*v5 )
        {
LABEL_34:
          result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
LABEL_35:
          if ( FileHandle )
            return ZwClose(FileHandle);
          return result;
        }
        while ( 1 )
        {
          ClientId.UniqueThread = 0;
          ClientId.UniqueProcess = *(HANDLE *)&v5[2 * v9 + 2];
          v17.Length = 48;
          memset(&v17.RootDirectory, 0, 20);
          *(_OWORD *)&v17.SecurityDescriptor = 0;
          v10 = ZwOpenProcess(&ProcessHandle, 0x1000u, &v17, &ClientId);
          if ( v10 < 0 )
            break;
          Length = 0;
          v11 = ZwQueryInformationProcess(ProcessHandle, ProcessImageFileName, 0, 0, &Length);
          if ( v11 != -2147483643 && v11 != -1073741789 && v11 != -1073741820 )
          {
            result = BiLogMessage(4, L"Failed to query process information for size. Status: %x", v11);
            goto LABEL_28;
          }
          v3 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Length);
          if ( !v3 )
          {
            result = BiLogMessage(4, L"Failed to allocate memory for space for process name.");
            goto LABEL_29;
          }
          v12 = ZwQueryInformationProcess(ProcessHandle, ProcessImageFileName, v3, Length, &Length);
          if ( v12 < 0 )
          {
            result = BiLogMessage(4, L"Failed to query process info. Status: %x", (unsigned int)v12);
            goto LABEL_29;
          }
          if ( *(_WORD *)v3 )
            v13 = (const wchar_t *)v3[1];
          else
            v13 = L"System";
          BiLogMessage(4, L"Process Name [%d]: %ws", v9, v13);
          ZwClose(ProcessHandle);
          ProcessHandle = 0;
          result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
          ++v9;
          v3 = 0;
          if ( v9 >= *v5 )
            goto LABEL_29;
        }
        result = BiLogMessage(4, L"Failed to open process. Status: %x", (unsigned int)v10);
LABEL_28:
        v3 = 0;
LABEL_29:
        if ( ProcessHandle )
          result = ZwClose(ProcessHandle);
        if ( v3 )
          result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
        if ( !v5 )
          goto LABEL_35;
        goto LABEL_34;
      }
      v8 = L"No processes are using this file.";
    }
    else
    {
      v8 = L"Failed to allocate process ID buffer.";
    }
    result = BiLogMessage(4, v8);
    goto LABEL_29;
  }
  return result;
}

```

## disassembly

```asm
0x140020324  mov     [rsp-8+arg_0], rbx
0x140020329  mov     [rsp-8+Length], edx
0x14002032d  push    rbp
0x14002032e  push    rsi
0x14002032f  push    rdi
0x140020330  push    r14
0x140020332  push    r15
0x140020334  lea     rbp, [rsp-37h]
0x140020339  sub     rsp, 0B0h
0x140020340  xorps   xmm0, xmm0
0x140020343  xor     r15d, r15d
0x140020346  xor     eax, eax
0x140020348  mov     [rbp+57h+Length], r15d
0x14002034c  cmp     cs:byte_14003F840, r15b
0x140020353  xorps   xmm1, xmm1
0x140020356  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14002035a  mov     rbx, rcx
0x14002035d  mov     [rbp+57h+ProcessHandle], r15
0x140020361  movups  xmmword ptr [rbp+57h+var_50.ObjectName], xmm0
0x140020365  mov     [rbp+57h+FileHandle], r15
0x140020369  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14002036d  movups  xmmword ptr [rbp+57h+var_50+1Ch], xmm0
0x140020371  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x140020375  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x140020379  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002037d  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x140020381  jz      loc_14002065A
0x140020387  mov     r8, [rcx+8]
0x14002038b  lea     r14d, [rax+2]
0x14002038f  mov     ecx, r14d
0x140020392  lea     rdx, aAttemptingToDe; "Attempting to determine owner of file %"...
0x140020399  mov     edi, r15d
0x14002039c  call    BiLogMessage
0x1400203a1  xorps   xmm0, xmm0
0x1400203a4  mov     [rsp+0D0h+OpenOptions], 4020h; OpenOptions
0x1400203ac  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400203b0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400203b7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400203bb  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1400203bf  mov     edx, 100080h; DesiredAccess
0x1400203c4  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1400203cb  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400203cf  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x1400203d3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400203d8  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x1400203e0  call    cs:__imp_ZwOpenFile
0x1400203e6  test    eax, eax
0x1400203e8  jns     short loc_140020406
0x1400203ea  mov     esi, r15d
0x1400203ed  lea     rdx, aFailedToOpenFi_0; "Failed to open file attributes. Status:"...
0x1400203f4  mov     ecx, 4
0x1400203f9  mov     r8d, eax
0x1400203fc  call    BiLogMessage
0x140020401  jmp     loc_140020602
0x140020406  mov     r8d, 400h; Size
0x14002040c  xor     edx, edx; Flags
0x14002040e  mov     [rbp+57h+Length], r8d
0x140020412  mov     rcx, gs:60h
0x14002041b  mov     rcx, [rcx+30h]; HeapHandle
0x14002041f  call    cs:__imp_RtlAllocateHeap
0x140020425  mov     rsi, rax
0x140020428  test    rax, rax
0x14002042b  jnz     short loc_140020443
0x14002042d  lea     rdx, aFailedToAlloca_1; "Failed to allocate process ID buffer."
0x140020434  mov     ecx, 4
0x140020439  call    BiLogMessage
0x14002043e  jmp     loc_140020602
0x140020443  mov     r9d, [rbp+57h+Length]; Length
0x140020447  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14002044b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002044f  mov     r8, rsi; FileInformation
0x140020452  mov     [rsp+0D0h+ShareAccess], 2Fh ; '/'; FileInformationClass
0x14002045a  call    cs:__imp_ZwQueryInformationFile
0x140020460  test    eax, eax
0x140020462  jns     short loc_14002046D
0x140020464  lea     rdx, aFailedToQueryP_1; "Failed to query processes. Status: %x"
0x14002046b  jmp     short loc_1400203F4
0x14002046d  mov     r8d, [rsi]
0x140020470  test    r8d, r8d
0x140020473  jnz     short loc_14002047E
0x140020475  lea     rdx, aNoProcessesAre; "No processes are using this file."
0x14002047c  jmp     short loc_140020434
0x14002047e  lea     rdx, aFoundDProcesse; "Found %d processes using this file."
0x140020485  mov     ecx, r14d
0x140020488  call    BiLogMessage
0x14002048d  mov     [rbp+57h+ProcessHandle], r15
0x140020491  mov     r14d, r15d
0x140020494  cmp     [rsi], r15d
0x140020497  jbe     loc_140020633
0x14002049d  mov     ebx, 4
0x1400204a2  mov     eax, r14d
0x1400204a5  lea     r9, [rbp+57h+ClientId]; ClientId
0x1400204a9  mov     [rbp+57h+ClientId.UniqueThread], r15
0x1400204ad  lea     r8, [rbp+57h+var_50]; ObjectAttributes
0x1400204b1  xorps   xmm0, xmm0
0x1400204b4  mov     edx, 1000h; DesiredAccess
0x1400204b9  mov     rcx, [rsi+rax*8+8]
0x1400204be  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x1400204c2  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1400204c6  mov     [rbp+57h+var_50.Length], 30h ; '0'
0x1400204cd  mov     [rbp+57h+var_50.RootDirectory], r15
0x1400204d1  mov     [rbp+57h+var_50.Attributes], r15d
0x1400204d5  mov     [rbp+57h+var_50.ObjectName], r15
0x1400204d9  movdqu  xmmword ptr [rbp+57h+var_50.SecurityDescriptor], xmm0
0x1400204de  call    cs:__imp_ZwOpenProcess
0x1400204e4  test    eax, eax
0x1400204e6  js      loc_1400205EE
0x1400204ec  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1400204f0  lea     rax, [rbp+57h+Length]
0x1400204f4  xor     r9d, r9d; ProcessInformationLength
0x1400204f7  mov     [rbp+57h+Length], r15d
0x1400204fb  xor     r8d, r8d; ProcessInformation
0x1400204fe  mov     qword ptr [rsp+0D0h+ShareAccess], rax; ReturnLength
0x140020503  lea     edx, [r9+1Bh]; ProcessInformationClass
0x140020507  call    cs:__imp_ZwQueryInformationProcess
0x14002050d  cmp     eax, 80000005h
0x140020512  jz      short loc_140020526
0x140020514  cmp     eax, 0C0000023h
0x140020519  jz      short loc_140020526
0x14002051b  cmp     eax, 0C0000004h
0x140020520  jnz     loc_1400205C9
0x140020526  mov     rcx, gs:60h
0x14002052f  xor     edx, edx; Flags
0x140020531  mov     r8d, [rbp+57h+Length]; Size
0x140020535  mov     rcx, [rcx+30h]; HeapHandle
0x140020539  call    cs:__imp_RtlAllocateHeap
0x14002053f  mov     rdi, rax
0x140020542  test    rax, rax
0x140020545  jz      loc_1400205E0
0x14002054b  mov     r9d, [rbp+57h+Length]; ProcessInformationLength
0x14002054f  lea     rax, [rbp+57h+Length]
0x140020553  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140020557  mov     r8, rdi; ProcessInformation
0x14002055a  mov     edx, 1Bh; ProcessInformationClass
0x14002055f  mov     qword ptr [rsp+0D0h+ShareAccess], rax; ReturnLength
0x140020564  call    cs:__imp_ZwQueryInformationProcess
0x14002056a  test    eax, eax
0x14002056c  js      short loc_1400205D2
0x14002056e  cmp     [rdi], r15w
0x140020572  jbe     short loc_14002057A
0x140020574  mov     r9, [rdi+8]
0x140020578  jmp     short loc_140020581
0x14002057a  lea     r9, aSystem; "System"
0x140020581  mov     r8d, r14d
0x140020584  lea     rdx, aProcessNameDWs; "Process Name [%d]: %ws"
0x14002058b  mov     ecx, ebx
0x14002058d  call    BiLogMessage
0x140020592  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140020596  call    cs:__imp_ZwClose
0x14002059c  mov     [rbp+57h+ProcessHandle], r15
0x1400205a0  mov     r8, rdi; P
0x1400205a3  mov     rcx, gs:60h
0x1400205ac  xor     edx, edx; Flags
0x1400205ae  mov     rcx, [rcx+30h]; HeapHandle
0x1400205b2  call    cs:__imp_RtlFreeHeap
0x1400205b8  inc     r14d
0x1400205bb  mov     rdi, r15
0x1400205be  cmp     r14d, [rsi]
0x1400205c1  jb      loc_1400204A2
0x1400205c7  jmp     short loc_140020602
0x1400205c9  lea     rdx, aFailedToQueryP; "Failed to query process information for"...
0x1400205d0  jmp     short loc_1400205F5
0x1400205d2  lea     rdx, aFailedToQueryP_0; "Failed to query process info. Status: %"...
0x1400205d9  mov     ecx, ebx
0x1400205db  jmp     loc_1400203F9
0x1400205e0  lea     rdx, aFailedToAlloca; "Failed to allocate memory for space for"...
0x1400205e7  mov     ecx, ebx
0x1400205e9  jmp     loc_140020439
0x1400205ee  lea     rdx, aFailedToOpenPr; "Failed to open process. Status: %x"
0x1400205f5  mov     r8d, eax
0x1400205f8  mov     ecx, ebx
0x1400205fa  call    BiLogMessage
0x1400205ff  mov     rdi, r15
0x140020602  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140020606  test    rcx, rcx
0x140020609  jz      short loc_140020611
0x14002060b  call    cs:__imp_ZwClose
0x140020611  test    rdi, rdi
0x140020614  jz      short loc_14002062E
0x140020616  mov     rcx, gs:60h
0x14002061f  mov     r8, rdi; P
0x140020622  xor     edx, edx; Flags
0x140020624  mov     rcx, [rcx+30h]; HeapHandle
0x140020628  call    cs:__imp_RtlFreeHeap
0x14002062e  test    rsi, rsi
0x140020631  jz      short loc_14002064B
0x140020633  mov     rcx, gs:60h
0x14002063c  mov     r8, rsi; P
0x14002063f  xor     edx, edx; Flags
0x140020641  mov     rcx, [rcx+30h]; HeapHandle
0x140020645  call    cs:__imp_RtlFreeHeap
0x14002064b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14002064f  test    rcx, rcx
0x140020652  jz      short loc_14002065A
0x140020654  call    cs:__imp_ZwClose
0x14002065a  mov     rbx, [rsp+0D0h+arg_0]
0x140020662  add     rsp, 0B0h
0x140020669  pop     r15
0x14002066b  pop     r14
0x14002066d  pop     rdi
0x14002066e  pop     rsi
0x14002066f  pop     rbp
0x140020670  retn
```

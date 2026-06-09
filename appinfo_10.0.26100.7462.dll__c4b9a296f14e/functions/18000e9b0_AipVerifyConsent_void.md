# AipVerifyConsent(void *)

- ea: `0x18000e9b0`
- end: `0x18000ec54`
- name: `?AipVerifyConsent@@YAKPEAX@Z`
- size: `676`
- prototype: `unsigned int __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180024a98`

## callees

- `0x18000e9b0`
- `0x1800449d6`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eab5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eab5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ebd9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ebd9`
- `ntdll!NtReadVirtualMemory` at `0x18000ea9e`
- `ntdll!NtReadVirtualMemory` at `0x18000eaeb`
- `ntdll!NtReadVirtualMemory` at `0x18000ea9e`
- `ntdll!NtReadVirtualMemory` at `0x18000eaeb`
- `ntdll!RtlImageNtHeaderEx` at `0x18000eb0e`
- `ntdll!RtlImageNtHeaderEx` at `0x18000eb0e`
- `ntdll!NtQueryInformationProcess` at `0x18000ea5d`
- `ntdll!NtQueryInformationProcess` at `0x18000ea5d`
- `ntdll!NtQuerySystemInformation` at `0x18000ea28`
- `ntdll!NtQuerySystemInformation` at `0x18000ea28`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ea6f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ea6f`

## pseudocode

```c
__int64 __fastcall AipVerifyConsent(HANDLE hProcess)
{
  DWORD LastError; // ebx
  HLOCAL v3; // rdi
  int InformationProcess; // eax
  unsigned int v5; // r8d
  char *v6; // r14
  unsigned __int64 i; // rdx
  __int16 SystemInformation; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ReturnLength[2]; // [rsp+38h] [rbp-C8h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buffer[16]; // [rsp+80h] [rbp-80h] BYREF
  PVOID BaseAddress; // [rsp+90h] [rbp-70h]
  _BYTE Buf1[112]; // [rsp+850h] [rbp+750h] BYREF

  LastError = 0;
  SystemInformation = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(Buffer, 0, 0x7D0u);
  NtHeader = 0;
  *(_QWORD *)ReturnLength = 0;
  v3 = 0;
  if ( NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, ReturnLength) < 0
    || !(_BYTE)SystemInformation
    || HIBYTE(SystemInformation) )
  {
    InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    if ( InformationProcess >= 0 )
    {
      InformationProcess = NtReadVirtualMemory(
                             hProcess,
                             *((PVOID *)&ProcessInformation[0] + 1),
                             Buffer,
                             0x7D0u,
                             (PSIZE_T)ReturnLength);
      if ( InformationProcess >= 0 )
      {
        v3 = LocalAlloc(0, 0x1000u);
        if ( !v3 )
        {
          LastError = 8;
          goto LABEL_25;
        }
        InformationProcess = NtReadVirtualMemory(hProcess, BaseAddress, v3, 0x1000u, (PSIZE_T)ReturnLength);
        if ( InformationProcess >= 0 )
        {
          InformationProcess = RtlImageNtHeaderEx(0, v3, *(ULONGLONG *)ReturnLength, &NtHeader);
          if ( InformationProcess >= 0 )
          {
            if ( NtHeader->OptionalHeader.Magic == 523
              && (unsigned __int64)NtHeader->OptionalHeader.SizeOfHeaders <= *(_QWORD *)ReturnLength
              && SLOBYTE(NtHeader->OptionalHeader.DllCharacteristics) < 0 )
            {
              v5 = 0;
              v6 = (char *)&NtHeader->OptionalHeader + NtHeader->FileHeader.SizeOfOptionalHeader;
              for ( i = v6 - (_BYTE *)v3; v5 < NtHeader->FileHeader.NumberOfSections; i += 40LL )
              {
                if ( i > *(_QWORD *)ReturnLength - 40LL )
                  goto LABEL_24;
                if ( *(_QWORD *)v6 == 0x746E65736E6F63LL )
                  break;
                ++v5;
                v6 += 40;
              }
              if ( v5 != NtHeader->FileHeader.NumberOfSections && *((_DWORD *)v6 + 2) == 98 )
              {
                memset_0(Buf1, 0, 0x62u);
                if ( !ReadProcessMemory(hProcess, (char *)BaseAddress + *((unsigned int *)v6 + 3), Buf1, 0x62u, 0) )
                {
                  LastError = GetLastError();
                  goto LABEL_25;
                }
                if ( !memcmp_0(Buf1, L"Microsoft Windows (c) 2009 Microsoft Corporation", 0x62u) )
                  goto LABEL_25;
              }
            }
LABEL_24:
            LastError = 577;
            goto LABEL_25;
          }
        }
      }
    }
    LastError = RtlNtStatusToDosErrorNoTeb(InformationProcess);
  }
LABEL_25:
  LocalFree(v3);
  return LastError;
}

```

## disassembly

```asm
0x18000e9b0  mov     [rsp-8+arg_8], rbx
0x18000e9b5  mov     [rsp-8+arg_10], rsi
0x18000e9ba  push    rbp
0x18000e9bb  push    rdi
0x18000e9bc  push    r14
0x18000e9be  lea     rbp, [rsp-7D0h]
0x18000e9c6  sub     rsp, 8D0h
0x18000e9cd  mov     rax, cs:__security_cookie
0x18000e9d4  xor     rax, rsp
0x18000e9d7  mov     [rbp+7E0h+var_20], rax
0x18000e9de  xorps   xmm0, xmm0
0x18000e9e1  mov     rsi, rcx
0x18000e9e4  xor     ebx, ebx
0x18000e9e6  lea     rcx, [rbp+7E0h+Buffer]; void *
0x18000e9ea  xor     edx, edx; Val
0x18000e9ec  mov     [rsp+8E0h+SystemInformation], bx
0x18000e9f1  mov     r8d, 7D0h; Size
0x18000e9f7  movups  [rsp+8E0h+ProcessInformation], xmm0
0x18000e9fc  movups  [rsp+8E0h+var_888], xmm0
0x18000ea01  movups  [rsp+8E0h+var_878], xmm0
0x18000ea06  call    memset_0
0x18000ea0b  lea     r9, [rsp+8E0h+ReturnLength]; ReturnLength
0x18000ea10  mov     [rsp+8E0h+NtHeader], rbx
0x18000ea15  lea     r8d, [rbx+2]; SystemInformationLength
0x18000ea19  mov     qword ptr [rsp+8E0h+ReturnLength], rbx
0x18000ea1e  lea     rdx, [rsp+8E0h+SystemInformation]; SystemInformation
0x18000ea23  mov     edi, ebx
0x18000ea25  lea     ecx, [rbx+23h]; SystemInformationClass
0x18000ea28  call    cs:__imp_NtQuerySystemInformation
0x18000ea2f  nop     dword ptr [rax+rax+00h]
0x18000ea34  test    eax, eax
0x18000ea36  js      short loc_18000EA48
0x18000ea38  cmp     byte ptr [rsp+8E0h+SystemInformation], bl
0x18000ea3c  jz      short loc_18000EA48
0x18000ea3e  cmp     byte ptr [rsp+8E0h+SystemInformation+1], bl
0x18000ea42  jz      loc_18000EC1B
0x18000ea48  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18000ea4e  mov     [rsp+8E0h+var_8C0], rbx; ReturnLength
0x18000ea53  lea     r8, [rsp+8E0h+ProcessInformation]; ProcessInformation
0x18000ea58  xor     edx, edx; ProcessInformationClass
0x18000ea5a  mov     rcx, rsi; ProcessHandle
0x18000ea5d  call    cs:__imp_NtQueryInformationProcess
0x18000ea64  nop     dword ptr [rax+rax+00h]
0x18000ea69  test    eax, eax
0x18000ea6b  jns     short loc_18000EA82
0x18000ea6d  mov     ecx, eax; Status
0x18000ea6f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ea76  nop     dword ptr [rax+rax+00h]
0x18000ea7b  mov     ebx, eax
0x18000ea7d  jmp     loc_18000EC1B
0x18000ea82  mov     rdx, qword ptr [rsp+8E0h+ProcessInformation+8]; BaseAddress
0x18000ea87  lea     rax, [rsp+8E0h+ReturnLength]
0x18000ea8c  mov     r9d, 7D0h; NumberOfBytesToRead
0x18000ea92  mov     [rsp+8E0h+var_8C0], rax; NumberOfBytesRead
0x18000ea97  lea     r8, [rbp+7E0h+Buffer]; Buffer
0x18000ea9b  mov     rcx, rsi; ProcessHandle
0x18000ea9e  call    cs:__imp_NtReadVirtualMemory
0x18000eaa5  nop     dword ptr [rax+rax+00h]
0x18000eaaa  test    eax, eax
0x18000eaac  js      short loc_18000EA6D
0x18000eaae  mov     edx, 1000h; uBytes
0x18000eab3  xor     ecx, ecx; uFlags
0x18000eab5  call    cs:__imp_LocalAlloc
0x18000eabc  nop     dword ptr [rax+rax+00h]
0x18000eac1  mov     rdi, rax
0x18000eac4  test    rax, rax
0x18000eac7  jnz     short loc_18000EAD1
0x18000eac9  lea     ebx, [rax+8]
0x18000eacc  jmp     loc_18000EC1B
0x18000ead1  mov     rdx, [rbp+7E0h+BaseAddress]; BaseAddress
0x18000ead5  lea     rax, [rsp+8E0h+ReturnLength]
0x18000eada  mov     r9d, 1000h; NumberOfBytesToRead
0x18000eae0  mov     [rsp+8E0h+var_8C0], rax; NumberOfBytesRead
0x18000eae5  mov     r8, rdi; Buffer
0x18000eae8  mov     rcx, rsi; ProcessHandle
0x18000eaeb  call    cs:__imp_NtReadVirtualMemory
0x18000eaf2  nop     dword ptr [rax+rax+00h]
0x18000eaf7  test    eax, eax
0x18000eaf9  js      loc_18000EA6D
0x18000eaff  mov     r8, qword ptr [rsp+8E0h+ReturnLength]; Size
0x18000eb04  lea     r9, [rsp+8E0h+NtHeader]; NtHeader
0x18000eb09  mov     rdx, rdi; BaseAddress
0x18000eb0c  xor     ecx, ecx; Flags
0x18000eb0e  call    cs:__imp_RtlImageNtHeaderEx
0x18000eb15  nop     dword ptr [rax+rax+00h]
0x18000eb1a  test    eax, eax
0x18000eb1c  js      loc_18000EA6D
0x18000eb22  mov     r9, [rsp+8E0h+NtHeader]
0x18000eb27  mov     eax, 20Bh
0x18000eb2c  cmp     [r9+18h], ax
0x18000eb31  jnz     loc_18000EC16
0x18000eb37  mov     eax, [r9+54h]
0x18000eb3b  mov     r10, qword ptr [rsp+8E0h+ReturnLength]
0x18000eb40  cmp     rax, r10
0x18000eb43  ja      loc_18000EC16
0x18000eb49  test    byte ptr [r9+5Eh], 80h
0x18000eb4e  jz      loc_18000EC16
0x18000eb54  movzx   r14d, word ptr [r9+14h]
0x18000eb59  mov     r8d, ebx
0x18000eb5c  movzx   r11d, word ptr [r9+6]
0x18000eb61  add     r14, 18h
0x18000eb65  mov     rax, cs:qword_18004B4C8
0x18000eb6c  add     r14, r9
0x18000eb6f  mov     rdx, r14
0x18000eb72  sub     rdx, rdi
0x18000eb75  cmp     r8d, r11d
0x18000eb78  jnb     short loc_18000EB99
0x18000eb7a  lea     rcx, [r10-28h]
0x18000eb7e  cmp     rdx, rcx
0x18000eb81  ja      loc_18000EC16
0x18000eb87  cmp     rax, [r14]
0x18000eb8a  jz      short loc_18000EB99
0x18000eb8c  inc     r8d
0x18000eb8f  add     r14, 28h ; '('
0x18000eb93  add     rdx, 28h ; '('
0x18000eb97  jmp     short loc_18000EB75
0x18000eb99  movzx   eax, word ptr [r9+6]
0x18000eb9e  cmp     r8d, eax
0x18000eba1  jz      short loc_18000EC16
0x18000eba3  cmp     dword ptr [r14+8], 62h ; 'b'
0x18000eba8  jnz     short loc_18000EC16
0x18000ebaa  xor     edx, edx; Val
0x18000ebac  lea     rcx, [rbp+7E0h+Buf1]; void *
0x18000ebb3  lea     r8d, [rdx+62h]; Size
0x18000ebb7  call    memset_0
0x18000ebbc  mov     edx, [r14+0Ch]
0x18000ebc0  lea     r8, [rbp+7E0h+Buf1]; lpBuffer
0x18000ebc7  add     rdx, [rbp+7E0h+BaseAddress]; lpBaseAddress
0x18000ebcb  mov     r9d, 62h ; 'b'; nSize
0x18000ebd1  mov     rcx, rsi; hProcess
0x18000ebd4  mov     [rsp+8E0h+var_8C0], rbx; lpNumberOfBytesRead
0x18000ebd9  call    cs:__imp_ReadProcessMemory
0x18000ebe0  nop     dword ptr [rax+rax+00h]
0x18000ebe5  test    eax, eax
0x18000ebe7  jnz     short loc_18000EBF9
0x18000ebe9  call    cs:__imp_GetLastError
0x18000ebf0  nop     dword ptr [rax+rax+00h]
0x18000ebf5  mov     ebx, eax
0x18000ebf7  jmp     short loc_18000EC1B
0x18000ebf9  mov     r8d, 62h ; 'b'; Size
0x18000ebff  lea     rdx, aMicrosoftWindo_0; "Microsoft Windows (c) 2009 Microsoft Co"...
0x18000ec06  lea     rcx, [rbp+7E0h+Buf1]; Buf1
0x18000ec0d  call    memcmp_0
0x18000ec12  test    eax, eax
0x18000ec14  jz      short loc_18000EC1B
0x18000ec16  mov     ebx, 241h
0x18000ec1b  mov     rcx, rdi; hMem
0x18000ec1e  call    cs:__imp_LocalFree
0x18000ec25  nop     dword ptr [rax+rax+00h]
0x18000ec2a  mov     eax, ebx
0x18000ec2c  mov     rcx, [rbp+7E0h+var_20]
0x18000ec33  xor     rcx, rsp; StackCookie
0x18000ec36  call    __security_check_cookie
0x18000ec3b  lea     r11, [rsp+8E0h+var_10]
0x18000ec43  mov     rbx, [r11+28h]
0x18000ec47  mov     rsi, [r11+30h]
0x18000ec4b  mov     rsp, r11
0x18000ec4e  pop     r14
0x18000ec50  pop     rdi
0x18000ec51  pop     rbp
0x18000ec52  retn
```

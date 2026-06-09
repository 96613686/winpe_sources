# AipVerifyConsent(void *)

- ea: `0x18000ea70`
- end: `0x18000ed14`
- name: `?AipVerifyConsent@@YAKPEAX@Z`
- size: `676`
- prototype: `unsigned int __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800263a8`

## callees

- `0x18000ea70`
- `0x180042906`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ecde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ecde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eb75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eb75`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ec99`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ec99`
- `ntdll!NtReadVirtualMemory` at `0x18000eb5e`
- `ntdll!NtReadVirtualMemory` at `0x18000ebab`
- `ntdll!NtReadVirtualMemory` at `0x18000eb5e`
- `ntdll!NtReadVirtualMemory` at `0x18000ebab`
- `ntdll!RtlImageNtHeaderEx` at `0x18000ebce`
- `ntdll!RtlImageNtHeaderEx` at `0x18000ebce`
- `ntdll!NtQueryInformationProcess` at `0x18000eb1d`
- `ntdll!NtQueryInformationProcess` at `0x18000eb1d`
- `ntdll!NtQuerySystemInformation` at `0x18000eae8`
- `ntdll!NtQuerySystemInformation` at `0x18000eae8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000eb2f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000eb2f`

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
0x18000ea70  mov     [rsp-8+arg_8], rbx
0x18000ea75  mov     [rsp-8+arg_10], rsi
0x18000ea7a  push    rbp
0x18000ea7b  push    rdi
0x18000ea7c  push    r14
0x18000ea7e  lea     rbp, [rsp-7D0h]
0x18000ea86  sub     rsp, 8D0h
0x18000ea8d  mov     rax, cs:__security_cookie
0x18000ea94  xor     rax, rsp
0x18000ea97  mov     [rbp+7E0h+var_20], rax
0x18000ea9e  xorps   xmm0, xmm0
0x18000eaa1  mov     rsi, rcx
0x18000eaa4  xor     ebx, ebx
0x18000eaa6  lea     rcx, [rbp+7E0h+Buffer]; void *
0x18000eaaa  xor     edx, edx; Val
0x18000eaac  mov     [rsp+8E0h+SystemInformation], bx
0x18000eab1  mov     r8d, 7D0h; Size
0x18000eab7  movups  [rsp+8E0h+ProcessInformation], xmm0
0x18000eabc  movups  [rsp+8E0h+var_888], xmm0
0x18000eac1  movups  [rsp+8E0h+var_878], xmm0
0x18000eac6  call    memset_0
0x18000eacb  lea     r9, [rsp+8E0h+ReturnLength]; ReturnLength
0x18000ead0  mov     [rsp+8E0h+NtHeader], rbx
0x18000ead5  lea     r8d, [rbx+2]; SystemInformationLength
0x18000ead9  mov     qword ptr [rsp+8E0h+ReturnLength], rbx
0x18000eade  lea     rdx, [rsp+8E0h+SystemInformation]; SystemInformation
0x18000eae3  mov     edi, ebx
0x18000eae5  lea     ecx, [rbx+23h]; SystemInformationClass
0x18000eae8  call    cs:__imp_NtQuerySystemInformation
0x18000eaef  nop     dword ptr [rax+rax+00h]
0x18000eaf4  test    eax, eax
0x18000eaf6  js      short loc_18000EB08
0x18000eaf8  cmp     byte ptr [rsp+8E0h+SystemInformation], bl
0x18000eafc  jz      short loc_18000EB08
0x18000eafe  cmp     byte ptr [rsp+8E0h+SystemInformation+1], bl
0x18000eb02  jz      loc_18000ECDB
0x18000eb08  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18000eb0e  mov     [rsp+8E0h+var_8C0], rbx; ReturnLength
0x18000eb13  lea     r8, [rsp+8E0h+ProcessInformation]; ProcessInformation
0x18000eb18  xor     edx, edx; ProcessInformationClass
0x18000eb1a  mov     rcx, rsi; ProcessHandle
0x18000eb1d  call    cs:__imp_NtQueryInformationProcess
0x18000eb24  nop     dword ptr [rax+rax+00h]
0x18000eb29  test    eax, eax
0x18000eb2b  jns     short loc_18000EB42
0x18000eb2d  mov     ecx, eax; Status
0x18000eb2f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000eb36  nop     dword ptr [rax+rax+00h]
0x18000eb3b  mov     ebx, eax
0x18000eb3d  jmp     loc_18000ECDB
0x18000eb42  mov     rdx, qword ptr [rsp+8E0h+ProcessInformation+8]; BaseAddress
0x18000eb47  lea     rax, [rsp+8E0h+ReturnLength]
0x18000eb4c  mov     r9d, 7D0h; NumberOfBytesToRead
0x18000eb52  mov     [rsp+8E0h+var_8C0], rax; NumberOfBytesRead
0x18000eb57  lea     r8, [rbp+7E0h+Buffer]; Buffer
0x18000eb5b  mov     rcx, rsi; ProcessHandle
0x18000eb5e  call    cs:__imp_NtReadVirtualMemory
0x18000eb65  nop     dword ptr [rax+rax+00h]
0x18000eb6a  test    eax, eax
0x18000eb6c  js      short loc_18000EB2D
0x18000eb6e  mov     edx, 1000h; uBytes
0x18000eb73  xor     ecx, ecx; uFlags
0x18000eb75  call    cs:__imp_LocalAlloc
0x18000eb7c  nop     dword ptr [rax+rax+00h]
0x18000eb81  mov     rdi, rax
0x18000eb84  test    rax, rax
0x18000eb87  jnz     short loc_18000EB91
0x18000eb89  lea     ebx, [rax+8]
0x18000eb8c  jmp     loc_18000ECDB
0x18000eb91  mov     rdx, [rbp+7E0h+BaseAddress]; BaseAddress
0x18000eb95  lea     rax, [rsp+8E0h+ReturnLength]
0x18000eb9a  mov     r9d, 1000h; NumberOfBytesToRead
0x18000eba0  mov     [rsp+8E0h+var_8C0], rax; NumberOfBytesRead
0x18000eba5  mov     r8, rdi; Buffer
0x18000eba8  mov     rcx, rsi; ProcessHandle
0x18000ebab  call    cs:__imp_NtReadVirtualMemory
0x18000ebb2  nop     dword ptr [rax+rax+00h]
0x18000ebb7  test    eax, eax
0x18000ebb9  js      loc_18000EB2D
0x18000ebbf  mov     r8, qword ptr [rsp+8E0h+ReturnLength]; Size
0x18000ebc4  lea     r9, [rsp+8E0h+NtHeader]; NtHeader
0x18000ebc9  mov     rdx, rdi; BaseAddress
0x18000ebcc  xor     ecx, ecx; Flags
0x18000ebce  call    cs:__imp_RtlImageNtHeaderEx
0x18000ebd5  nop     dword ptr [rax+rax+00h]
0x18000ebda  test    eax, eax
0x18000ebdc  js      loc_18000EB2D
0x18000ebe2  mov     r9, [rsp+8E0h+NtHeader]
0x18000ebe7  mov     eax, 20Bh
0x18000ebec  cmp     [r9+18h], ax
0x18000ebf1  jnz     loc_18000ECD6
0x18000ebf7  mov     eax, [r9+54h]
0x18000ebfb  mov     r10, qword ptr [rsp+8E0h+ReturnLength]
0x18000ec00  cmp     rax, r10
0x18000ec03  ja      loc_18000ECD6
0x18000ec09  test    byte ptr [r9+5Eh], 80h
0x18000ec0e  jz      loc_18000ECD6
0x18000ec14  movzx   r14d, word ptr [r9+14h]
0x18000ec19  mov     r8d, ebx
0x18000ec1c  movzx   r11d, word ptr [r9+6]
0x18000ec21  add     r14, 18h
0x18000ec25  mov     rax, cs:qword_180048548
0x18000ec2c  add     r14, r9
0x18000ec2f  mov     rdx, r14
0x18000ec32  sub     rdx, rdi
0x18000ec35  cmp     r8d, r11d
0x18000ec38  jnb     short loc_18000EC59
0x18000ec3a  lea     rcx, [r10-28h]
0x18000ec3e  cmp     rdx, rcx
0x18000ec41  ja      loc_18000ECD6
0x18000ec47  cmp     rax, [r14]
0x18000ec4a  jz      short loc_18000EC59
0x18000ec4c  inc     r8d
0x18000ec4f  add     r14, 28h ; '('
0x18000ec53  add     rdx, 28h ; '('
0x18000ec57  jmp     short loc_18000EC35
0x18000ec59  movzx   eax, word ptr [r9+6]
0x18000ec5e  cmp     r8d, eax
0x18000ec61  jz      short loc_18000ECD6
0x18000ec63  cmp     dword ptr [r14+8], 62h ; 'b'
0x18000ec68  jnz     short loc_18000ECD6
0x18000ec6a  xor     edx, edx; Val
0x18000ec6c  lea     rcx, [rbp+7E0h+Buf1]; void *
0x18000ec73  lea     r8d, [rdx+62h]; Size
0x18000ec77  call    memset_0
0x18000ec7c  mov     edx, [r14+0Ch]
0x18000ec80  lea     r8, [rbp+7E0h+Buf1]; lpBuffer
0x18000ec87  add     rdx, [rbp+7E0h+BaseAddress]; lpBaseAddress
0x18000ec8b  mov     r9d, 62h ; 'b'; nSize
0x18000ec91  mov     rcx, rsi; hProcess
0x18000ec94  mov     [rsp+8E0h+var_8C0], rbx; lpNumberOfBytesRead
0x18000ec99  call    cs:__imp_ReadProcessMemory
0x18000eca0  nop     dword ptr [rax+rax+00h]
0x18000eca5  test    eax, eax
0x18000eca7  jnz     short loc_18000ECB9
0x18000eca9  call    cs:__imp_GetLastError
0x18000ecb0  nop     dword ptr [rax+rax+00h]
0x18000ecb5  mov     ebx, eax
0x18000ecb7  jmp     short loc_18000ECDB
0x18000ecb9  mov     r8d, 62h ; 'b'; Size
0x18000ecbf  lea     rdx, aMicrosoftWindo_0; "Microsoft Windows (c) 2009 Microsoft Co"...
0x18000ecc6  lea     rcx, [rbp+7E0h+Buf1]; Buf1
0x18000eccd  call    memcmp_0
0x18000ecd2  test    eax, eax
0x18000ecd4  jz      short loc_18000ECDB
0x18000ecd6  mov     ebx, 241h
0x18000ecdb  mov     rcx, rdi; hMem
0x18000ecde  call    cs:__imp_LocalFree
0x18000ece5  nop     dword ptr [rax+rax+00h]
0x18000ecea  mov     eax, ebx
0x18000ecec  mov     rcx, [rbp+7E0h+var_20]
0x18000ecf3  xor     rcx, rsp; StackCookie
0x18000ecf6  call    __security_check_cookie
0x18000ecfb  lea     r11, [rsp+8E0h+var_10]
0x18000ed03  mov     rbx, [r11+28h]
0x18000ed07  mov     rsi, [r11+30h]
0x18000ed0b  mov     rsp, r11
0x18000ed0e  pop     r14
0x18000ed10  pop     rdi
0x18000ed11  pop     rbp
0x18000ed12  retn
```

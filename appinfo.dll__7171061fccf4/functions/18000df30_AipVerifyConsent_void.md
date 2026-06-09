# AipVerifyConsent(void *)

- ea: `0x18000df30`
- end: `0x18000e190`
- name: `?AipVerifyConsent@@YAKPEAX@Z`
- size: `608`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800290b4`

## callees

- `0x18000df30`
- `0x180046df6`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e13a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e13a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e169`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e169`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e022`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e022`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000e130`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000e130`
- `ntdll!NtReadVirtualMemory` at `0x18000e011`
- `ntdll!NtReadVirtualMemory` at `0x18000e054`
- `ntdll!NtReadVirtualMemory` at `0x18000e011`
- `ntdll!NtReadVirtualMemory` at `0x18000e054`
- `ntdll!RtlImageNtHeaderEx` at `0x18000e06d`
- `ntdll!RtlImageNtHeaderEx` at `0x18000e06d`
- `ntdll!NtQueryInformationProcess` at `0x18000dfdc`
- `ntdll!NtQueryInformationProcess` at `0x18000dfdc`
- `ntdll!NtQuerySystemInformation` at `0x18000dfad`
- `ntdll!NtQuerySystemInformation` at `0x18000dfad`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000dfe8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000dfe8`

## pseudocode

```c
__int64 __fastcall AipVerifyConsent(HANDLE hProcess)
{
  DWORD LastError; // edi
  HLOCAL v3; // rbx
  int InformationProcess; // eax
  unsigned int v5; // r8d
  char *i; // r14
  __int16 SystemInformation; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ReturnLength[2]; // [rsp+38h] [rbp-C8h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buffer[16]; // [rsp+80h] [rbp-80h] BYREF
  PVOID BaseAddress; // [rsp+90h] [rbp-70h]
  _BYTE Buf1[112]; // [rsp+850h] [rbp+750h] BYREF

  SystemInformation = 0;
  LastError = 0;
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
              for ( i = (char *)&NtHeader->OptionalHeader + NtHeader->FileHeader.SizeOfOptionalHeader;
                    v5 < NtHeader->FileHeader.NumberOfSections;
                    i += 40 )
              {
                if ( i - (_BYTE *)v3 > (unsigned __int64)(*(_QWORD *)ReturnLength - 40LL) )
                  goto LABEL_24;
                if ( *(_QWORD *)i == 0x746E65736E6F63LL )
                  break;
                ++v5;
              }
              if ( v5 != NtHeader->FileHeader.NumberOfSections && *((_DWORD *)i + 2) == 98 )
              {
                memset_0(Buf1, 0, 0x62u);
                if ( !ReadProcessMemory(hProcess, (char *)BaseAddress + *((unsigned int *)i + 3), Buf1, 0x62u, 0) )
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
0x18000df30  push    rbp
0x18000df32  push    rbx
0x18000df33  push    rsi
0x18000df34  push    rdi
0x18000df35  push    r14
0x18000df37  push    r15
0x18000df39  lea     rbp, [rsp-7D8h]
0x18000df41  sub     rsp, 8D8h
0x18000df48  mov     rax, cs:__security_cookie
0x18000df4f  xor     rax, rsp
0x18000df52  mov     [rbp+800h+var_40], rax
0x18000df59  xorps   xmm0, xmm0
0x18000df5c  mov     rsi, rcx
0x18000df5f  xor     r15d, r15d
0x18000df62  lea     rcx, [rbp+800h+Buffer]; void *
0x18000df66  xor     edx, edx; Val
0x18000df68  mov     [rsp+900h+SystemInformation], r15w
0x18000df6e  mov     r8d, 7D0h; Size
0x18000df74  mov     edi, r15d
0x18000df77  movups  [rsp+900h+ProcessInformation], xmm0
0x18000df7c  movups  [rsp+900h+var_8A8], xmm0
0x18000df81  movups  [rsp+900h+var_898], xmm0
0x18000df86  call    memset_0
0x18000df8b  lea     r9, [rsp+900h+ReturnLength]; ReturnLength
0x18000df90  mov     [rsp+900h+NtHeader], r15
0x18000df95  mov     r8d, 2; SystemInformationLength
0x18000df9b  mov     qword ptr [rsp+900h+ReturnLength], r15
0x18000dfa0  lea     rdx, [rsp+900h+SystemInformation]; SystemInformation
0x18000dfa5  mov     ecx, 23h ; '#'; SystemInformationClass
0x18000dfaa  mov     ebx, r15d
0x18000dfad  call    cs:__imp_NtQuerySystemInformation
0x18000dfb3  test    eax, eax
0x18000dfb5  js      short loc_18000DFC7
0x18000dfb7  cmp     byte ptr [rsp+900h+SystemInformation], bl
0x18000dfbb  jz      short loc_18000DFC7
0x18000dfbd  cmp     byte ptr [rsp+900h+SystemInformation+1], bl
0x18000dfc1  jz      loc_18000E166
0x18000dfc7  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18000dfcd  mov     [rsp+900h+var_8E0], r15; ReturnLength
0x18000dfd2  lea     r8, [rsp+900h+ProcessInformation]; ProcessInformation
0x18000dfd7  xor     edx, edx; ProcessInformationClass
0x18000dfd9  mov     rcx, rsi; ProcessHandle
0x18000dfdc  call    cs:__imp_NtQueryInformationProcess
0x18000dfe2  test    eax, eax
0x18000dfe4  jns     short loc_18000DFF5
0x18000dfe6  mov     ecx, eax; Status
0x18000dfe8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000dfee  mov     edi, eax
0x18000dff0  jmp     loc_18000E166
0x18000dff5  mov     rdx, qword ptr [rsp+900h+ProcessInformation+8]; BaseAddress
0x18000dffa  lea     rax, [rsp+900h+ReturnLength]
0x18000dfff  mov     r9d, 7D0h; NumberOfBytesToRead
0x18000e005  mov     [rsp+900h+var_8E0], rax; NumberOfBytesRead
0x18000e00a  lea     r8, [rbp+800h+Buffer]; Buffer
0x18000e00e  mov     rcx, rsi; ProcessHandle
0x18000e011  call    cs:__imp_NtReadVirtualMemory
0x18000e017  test    eax, eax
0x18000e019  js      short loc_18000DFE6
0x18000e01b  mov     edx, 1000h; uBytes
0x18000e020  xor     ecx, ecx; uFlags
0x18000e022  call    cs:__imp_LocalAlloc
0x18000e028  mov     rbx, rax
0x18000e02b  test    rax, rax
0x18000e02e  jnz     short loc_18000E03A
0x18000e030  mov     edi, 8
0x18000e035  jmp     loc_18000E166
0x18000e03a  mov     rdx, [rbp+800h+BaseAddress]; BaseAddress
0x18000e03e  lea     rax, [rsp+900h+ReturnLength]
0x18000e043  mov     r9d, 1000h; NumberOfBytesToRead
0x18000e049  mov     [rsp+900h+var_8E0], rax; NumberOfBytesRead
0x18000e04e  mov     r8, rbx; Buffer
0x18000e051  mov     rcx, rsi; ProcessHandle
0x18000e054  call    cs:__imp_NtReadVirtualMemory
0x18000e05a  test    eax, eax
0x18000e05c  js      short loc_18000DFE6
0x18000e05e  mov     r8, qword ptr [rsp+900h+ReturnLength]; Size
0x18000e063  lea     r9, [rsp+900h+NtHeader]; NtHeader
0x18000e068  mov     rdx, rbx; BaseAddress
0x18000e06b  xor     ecx, ecx; Flags
0x18000e06d  call    cs:__imp_RtlImageNtHeaderEx
0x18000e073  test    eax, eax
0x18000e075  js      loc_18000DFE6
0x18000e07b  mov     r9, [rsp+900h+NtHeader]
0x18000e080  mov     eax, 20Bh
0x18000e085  cmp     [r9+18h], ax
0x18000e08a  jnz     loc_18000E161
0x18000e090  mov     eax, [r9+54h]
0x18000e094  mov     r10, qword ptr [rsp+900h+ReturnLength]
0x18000e099  cmp     rax, r10
0x18000e09c  ja      loc_18000E161
0x18000e0a2  test    byte ptr [r9+5Eh], 80h
0x18000e0a7  jz      loc_18000E161
0x18000e0ad  movzx   r14d, word ptr [r9+14h]
0x18000e0b2  mov     r8d, r15d
0x18000e0b5  movzx   r11d, word ptr [r9+6]
0x18000e0ba  add     r14, 18h
0x18000e0be  mov     rax, cs:qword_18004D718
0x18000e0c5  add     r14, r9
0x18000e0c8  cmp     r8d, r11d
0x18000e0cb  jnb     short loc_18000E0EE
0x18000e0cd  mov     rdx, r14
0x18000e0d0  lea     rcx, [r10-28h]
0x18000e0d4  sub     rdx, rbx
0x18000e0d7  cmp     rdx, rcx
0x18000e0da  ja      loc_18000E161
0x18000e0e0  cmp     rax, [r14]
0x18000e0e3  jz      short loc_18000E0EE
0x18000e0e5  inc     r8d
0x18000e0e8  add     r14, 28h ; '('
0x18000e0ec  jmp     short loc_18000E0C8
0x18000e0ee  movzx   eax, word ptr [r9+6]
0x18000e0f3  cmp     r8d, eax
0x18000e0f6  jz      short loc_18000E161
0x18000e0f8  cmp     dword ptr [r14+8], 62h ; 'b'
0x18000e0fd  jnz     short loc_18000E161
0x18000e0ff  xor     edx, edx; Val
0x18000e101  lea     rcx, [rbp+800h+Buf1]; void *
0x18000e108  mov     r8d, 62h ; 'b'; Size
0x18000e10e  call    memset_0
0x18000e113  mov     edx, [r14+0Ch]
0x18000e117  lea     r8, [rbp+800h+Buf1]; lpBuffer
0x18000e11e  add     rdx, [rbp+800h+BaseAddress]; lpBaseAddress
0x18000e122  mov     r9d, 62h ; 'b'; nSize
0x18000e128  mov     rcx, rsi; hProcess
0x18000e12b  mov     [rsp+900h+var_8E0], r15; lpNumberOfBytesRead
0x18000e130  call    cs:__imp_ReadProcessMemory
0x18000e136  test    eax, eax
0x18000e138  jnz     short loc_18000E144
0x18000e13a  call    cs:__imp_GetLastError
0x18000e140  mov     edi, eax
0x18000e142  jmp     short loc_18000E166
0x18000e144  mov     r8d, 62h ; 'b'; Size
0x18000e14a  lea     rdx, aMicrosoftWindo_0; "Microsoft Windows (c) 2009 Microsoft Co"...
0x18000e151  lea     rcx, [rbp+800h+Buf1]; Buf1
0x18000e158  call    memcmp_0
0x18000e15d  test    eax, eax
0x18000e15f  jz      short loc_18000E166
0x18000e161  mov     edi, 241h
0x18000e166  mov     rcx, rbx; hMem
0x18000e169  call    cs:__imp_LocalFree
0x18000e16f  mov     eax, edi
0x18000e171  mov     rcx, [rbp+800h+var_40]
0x18000e178  xor     rcx, rsp; StackCookie
0x18000e17b  call    __security_check_cookie
0x18000e180  add     rsp, 8D8h
0x18000e187  pop     r15
0x18000e189  pop     r14
0x18000e18b  pop     rdi
0x18000e18c  pop     rsi
0x18000e18d  pop     rbx
0x18000e18e  pop     rbp
0x18000e18f  retn
```

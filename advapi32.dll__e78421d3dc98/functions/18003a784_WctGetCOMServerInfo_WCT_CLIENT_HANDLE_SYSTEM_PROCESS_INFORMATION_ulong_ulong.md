# WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)

- ea: `0x18003a784`
- end: `0x18003a9f6`
- name: `?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z`
- size: `626`
- prototype: `void __fastcall(struct _WCT_CLIENT_HANDLE *, struct _SYSTEM_PROCESS_INFORMATION *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b80c`

## callees

- `0x18003a784`
- `0x18003ac90`
- `0x18003b1f8`
- `0x18003b57c`
- `0x18003b748`
- `0x18005fd08`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18003a8ec`
- `ntdll!NtQueryInformationThread` at `0x18003a8ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003a8bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003a8bc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003a84b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003a84b`
- `KERNEL32!ReadProcessMemory` at `0x18003a932`
- `KERNEL32!ReadProcessMemory` at `0x18003a96b`
- `KERNEL32!ReadProcessMemory` at `0x18003a932`
- `KERNEL32!ReadProcessMemory` at `0x18003a96b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WctGetCOMServerInfo(
        struct _WCT_CLIENT_HANDLE *a1,
        struct _SYSTEM_PROCESS_INFORMATION *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  ULONG v7; // r14d
  _QWORD *v8; // rcx
  HANDLE v9; // rax
  HANDLE v10; // rbx
  struct _SYSTEM_PROCESS_INFORMATION *v11; // r15
  DWORD LowPart; // r12d
  HANDLE v13; // rax
  NTSTATUS v14; // edi
  ULONG ReturnLength; // [rsp+30h] [rbp-49h] BYREF
  int v16; // [rsp+34h] [rbp-45h] BYREF
  HANDLE v17; // [rsp+38h] [rbp-41h] BYREF
  HANDLE hProcess; // [rsp+40h] [rbp-39h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-31h] BYREF
  __int64 Buffer; // [rsp+50h] [rbp-29h] BYREF
  _OWORD ThreadInformation[7]; // [rsp+58h] [rbp-21h] BYREF

  v7 = 0;
  hProcess = 0;
  memset(ThreadInformation, 0, 48);
  v16 = 0;
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  Buffer = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( dword_1800A3224 )
  {
    v9 = OpenProcess(0x450u, 0, *a4);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hProcess, v9);
    v10 = hProcess;
    if ( (unsigned __int64)hProcess + 1 > 1 && !(unsigned int)WctIsWow64(hProcess) )
    {
      while ( a2 )
      {
        if ( *a4 == LODWORD(a2->UniqueProcessId) )
        {
          v11 = a2 + 1;
          while ( v7 < a2->NumberOfThreads )
          {
            LowPart = v11->KernelTime.LowPart;
            v13 = OpenThread(0x40u, 0, LowPart);
            v17 = v13;
            if ( (unsigned __int64)v13 + 1 <= 1 )
              goto LABEL_26;
            v14 = NtQueryInformationThread(v13, ThreadBasicInformation, ThreadInformation, 0x30u, &ReturnLength);
            tlx::unique_any<tlx::file_handle_traits>::reset(&v17, 0);
            if ( v14 < 0
              || ReturnLength != 48
              || !ReadProcessMemory(
                    v10,
                    (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 5976LL),
                    &Buffer,
                    8u,
                    &NumberOfBytesRead)
              || NumberOfBytesRead != 8 )
            {
              goto LABEL_26;
            }
            if ( Buffer
              && ReadProcessMemory(v10, (LPCVOID)(Buffer + (unsigned int)dword_1800A3224), &v16, 4u, 0)
              && v16 == *((_DWORD *)a1 + 4) )
            {
              *a3 = LowPart;
LABEL_26:
              tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v17);
              goto LABEL_27;
            }
            v11 = (struct _SYSTEM_PROCESS_INFORMATION *)((char *)v11 + 136);
            tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v17);
            ++v7;
          }
          break;
        }
        if ( !a2->NextEntryOffset )
          break;
        a2 = (struct _SYSTEM_PROCESS_INFORMATION *)((char *)a2 + a2->NextEntryOffset);
      }
    }
LABEL_27:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_4c32fa7a72a13340317baef891270170_Traceguids, *a3);
  }
  else if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
  {
    WPP_SF_(v8[2], 41, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hProcess);
}

```

## disassembly

```asm
0x18003a784  mov     [rsp-8+arg_0], rcx
0x18003a789  push    rbp
0x18003a78a  push    rbx
0x18003a78b  push    rsi
0x18003a78c  push    rdi
0x18003a78d  push    r12
0x18003a78f  push    r13
0x18003a791  push    r14
0x18003a793  push    r15
0x18003a795  lea     rbp, [rsp-1Fh]
0x18003a79a  sub     rsp, 98h
0x18003a7a1  mov     rdi, r9
0x18003a7a4  mov     r13, r8
0x18003a7a7  mov     rsi, rdx
0x18003a7aa  xor     r14d, r14d
0x18003a7ad  mov     [rbp+57h+hProcess], r14
0x18003a7b1  xorps   xmm0, xmm0
0x18003a7b4  movups  [rbp+57h+ThreadInformation], xmm0
0x18003a7b8  movups  [rbp+57h+var_68], xmm0
0x18003a7bc  movups  [rbp+57h+var_58], xmm0
0x18003a7c0  mov     [rbp+57h+var_9C], r14d
0x18003a7c4  mov     [rbp+57h+NumberOfBytesRead], r14
0x18003a7c8  mov     [rbp+57h+var_A0], r14d
0x18003a7cc  mov     [rbp+57h+Buffer], r14
0x18003a7d0  lea     rax, WPP_GLOBAL_Control
0x18003a7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7de  cmp     rcx, rax
0x18003a7e1  jz      short loc_18003A80B
0x18003a7e3  test    byte ptr [rcx+1Ch], 4
0x18003a7e7  jz      short loc_18003A80B
0x18003a7e9  lea     edx, [r14+28h]
0x18003a7ed  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003a7f4  mov     rcx, [rcx+10h]
0x18003a7f8  call    WPP_SF_
0x18003a7fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a804  lea     rax, WPP_GLOBAL_Control
0x18003a80b  cmp     cs:dword_1800A3224, r14d
0x18003a812  jnz     short loc_18003A841
0x18003a814  cmp     rcx, rax
0x18003a817  jz      loc_18003A9D9
0x18003a81d  test    byte ptr [rcx+1Ch], 4
0x18003a821  jz      loc_18003A9D9
0x18003a827  mov     edx, 29h ; ')'
0x18003a82c  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003a833  mov     rcx, [rcx+10h]
0x18003a837  call    WPP_SF_
0x18003a83c  jmp     loc_18003A9D9
0x18003a841  mov     r8d, [rdi]; dwProcessId
0x18003a844  xor     edx, edx; bInheritHandle
0x18003a846  mov     ecx, 450h; dwDesiredAccess
0x18003a84b  call    cs:__imp_OpenProcess
0x18003a851  mov     rdx, rax
0x18003a854  lea     rcx, [rbp+57h+hProcess]
0x18003a858  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003a85d  mov     rbx, [rbp+57h+hProcess]
0x18003a861  lea     rax, [rbx+1]
0x18003a865  cmp     rax, 1
0x18003a869  jbe     loc_18003A9A6
0x18003a86f  mov     rcx, rbx; void *
0x18003a872  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18003a877  test    eax, eax
0x18003a879  jnz     loc_18003A9A6
0x18003a87f  test    rsi, rsi
0x18003a882  jz      loc_18003A9A6
0x18003a888  mov     eax, [rsi+50h]
0x18003a88b  cmp     [rdi], eax
0x18003a88d  jz      short loc_18003A89F
0x18003a88f  cmp     [rsi], r14d
0x18003a892  jz      loc_18003A9A6
0x18003a898  mov     eax, [rsi]
0x18003a89a  add     rsi, rax
0x18003a89d  jmp     short loc_18003A87F
0x18003a89f  lea     r15, [rsi+100h]
0x18003a8a6  cmp     r14d, [rsi+4]
0x18003a8aa  jnb     loc_18003A9A6
0x18003a8b0  mov     r12d, [r15+30h]
0x18003a8b4  mov     r8d, r12d; dwThreadId
0x18003a8b7  xor     edx, edx; bInheritHandle
0x18003a8b9  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18003a8bc  call    cs:__imp_OpenThread
0x18003a8c2  mov     [rbp+57h+var_98], rax
0x18003a8c6  lea     rcx, [rax+1]
0x18003a8ca  cmp     rcx, 1
0x18003a8ce  jbe     loc_18003A99D
0x18003a8d4  lea     rcx, [rbp+57h+var_A0]
0x18003a8d8  mov     [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x18003a8dd  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18003a8e3  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18003a8e7  xor     edx, edx; ThreadInformationClass
0x18003a8e9  mov     rcx, rax; ThreadHandle
0x18003a8ec  call    cs:__imp_NtQueryInformationThread
0x18003a8f2  mov     edi, eax
0x18003a8f4  xor     edx, edx
0x18003a8f6  lea     rcx, [rbp+57h+var_98]
0x18003a8fa  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003a8ff  test    edi, edi
0x18003a901  js      loc_18003A99D
0x18003a907  cmp     [rbp+57h+var_A0], 30h ; '0'
0x18003a90b  jnz     loc_18003A99D
0x18003a911  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]
0x18003a915  add     rdx, 1758h; lpBaseAddress
0x18003a91c  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18003a920  mov     [rsp+0D0h+ReturnLength], rax; lpNumberOfBytesRead
0x18003a925  mov     r9d, 8; nSize
0x18003a92b  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18003a92f  mov     rcx, rbx; hProcess
0x18003a932  call    cs:__imp_ReadProcessMemory
0x18003a938  test    eax, eax
0x18003a93a  jz      short loc_18003A99D
0x18003a93c  cmp     [rbp+57h+NumberOfBytesRead], 8
0x18003a941  jnz     short loc_18003A99D
0x18003a943  mov     rax, [rbp+57h+Buffer]
0x18003a947  test    rax, rax
0x18003a94a  jz      short loc_18003A981
0x18003a94c  mov     edx, cs:dword_1800A3224
0x18003a952  add     rdx, rax; lpBaseAddress
0x18003a955  mov     [rsp+0D0h+ReturnLength], 0; lpNumberOfBytesRead
0x18003a95e  mov     r9d, 4; nSize
0x18003a964  lea     r8, [rbp+57h+var_9C]; lpBuffer
0x18003a968  mov     rcx, rbx; hProcess
0x18003a96b  call    cs:__imp_ReadProcessMemory
0x18003a971  test    eax, eax
0x18003a973  jz      short loc_18003A981
0x18003a975  mov     rax, [rbp+57h+arg_0]
0x18003a979  mov     eax, [rax+10h]
0x18003a97c  cmp     [rbp+57h+var_9C], eax
0x18003a97f  jz      short loc_18003A999
0x18003a981  add     r15, 88h
0x18003a988  lea     rcx, [rbp+57h+var_98]
0x18003a98c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003a991  inc     r14d
0x18003a994  jmp     loc_18003A8A6
0x18003a999  mov     [r13+0], r12d
0x18003a99d  lea     rcx, [rbp+57h+var_98]
0x18003a9a1  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003a9a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9ad  lea     rax, WPP_GLOBAL_Control
0x18003a9b4  cmp     rcx, rax
0x18003a9b7  jz      short loc_18003A9D9
0x18003a9b9  test    byte ptr [rcx+1Ch], 4
0x18003a9bd  jz      short loc_18003A9D9
0x18003a9bf  mov     edx, 2Ah ; '*'
0x18003a9c4  mov     r9d, [r13+0]
0x18003a9c8  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003a9cf  mov     rcx, [rcx+10h]
0x18003a9d3  call    WPP_SF_d
0x18003a9d8  nop
0x18003a9d9  lea     rcx, [rbp+57h+hProcess]
0x18003a9dd  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003a9e2  add     rsp, 98h
0x18003a9e9  pop     r15
0x18003a9eb  pop     r14
0x18003a9ed  pop     r13
0x18003a9ef  pop     r12
0x18003a9f1  pop     rdi
0x18003a9f2  pop     rsi
0x18003a9f3  pop     rbx
0x18003a9f4  pop     rbp
0x18003a9f5  retn
```

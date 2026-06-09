# WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)

- ea: `0x18003f5cc`
- end: `0x18003f874`
- name: `?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z`
- size: `680`
- prototype: `void __fastcall(struct _WCT_CLIENT_HANDLE *, struct _SYSTEM_PROCESS_INFORMATION *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003fddc`

## callees

- `0x18003f5cc`
- `0x18003faec`
- `0x18003fb18`
- `0x18003fd04`
- `0x18006c5ec`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18003f744`
- `ntdll!NtQueryInformationThread` at `0x18003f744`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003f70b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003f70b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003f696`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003f696`
- `KERNEL32!ReadProcessMemory` at `0x18003f78d`
- `KERNEL32!ReadProcessMemory` at `0x18003f7cc`
- `KERNEL32!ReadProcessMemory` at `0x18003f78d`
- `KERNEL32!ReadProcessMemory` at `0x18003f7cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WctGetCOMServerInfo(
        struct _WCT_CLIENT_HANDLE *a1,
        struct _SYSTEM_PROCESS_INFORMATION *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int *v5; // rsi
  ULONG v7; // r15d
  _QWORD *v8; // rcx
  HANDLE v9; // rdx
  HANDLE v10; // r14
  __int64 v11; // rcx
  struct _SYSTEM_PROCESS_INFORMATION *v12; // r13
  DWORD LowPart; // r12d
  char *v14; // rax
  char *v15; // rsi
  char *v16; // rcx
  NTSTATUS v17; // ebx
  __int64 v18; // rcx
  char *v19; // rdx
  ULONG ReturnLength; // [rsp+38h] [rbp-39h] BYREF
  int v21; // [rsp+3Ch] [rbp-35h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+40h] [rbp-31h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-29h] BYREF
  HANDLE v24; // [rsp+50h] [rbp-21h]
  char *v25; // [rsp+58h] [rbp-19h]
  _OWORD ThreadInformation[6]; // [rsp+60h] [rbp-11h] BYREF

  v5 = a3;
  v7 = 0;
  v24 = 0;
  memset(ThreadInformation, 0, 48);
  v21 = 0;
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  Buffer = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( dword_1800B2368 )
  {
    v10 = OpenProcess(0x450u, 0, *a4);
    v24 = v10;
    tlx::file_handle_traits::operator()(v11, 0);
    if ( (unsigned __int64)v10 + 1 > 1 && !(unsigned int)WctIsWow64(v10) )
    {
      while ( a2 )
      {
        if ( *a4 == LODWORD(a2->UniqueProcessId) )
        {
          v12 = a2 + 1;
          while ( v7 < a2->NumberOfThreads )
          {
            LowPart = v12->KernelTime.LowPart;
            v14 = (char *)OpenThread(0x40u, 0, LowPart);
            v15 = v14;
            v25 = v14;
            v16 = v14 + 1;
            if ( (unsigned __int64)(v14 + 1) <= 1 )
            {
              v19 = v14;
              goto LABEL_29;
            }
            v17 = NtQueryInformationThread(v14, ThreadBasicInformation, ThreadInformation, 0x30u, &ReturnLength);
            tlx::file_handle_traits::operator()(v18, v15);
            if ( v17 < 0
              || ReturnLength != 48
              || !ReadProcessMemory(
                    v10,
                    (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 5976LL),
                    &Buffer,
                    8u,
                    &NumberOfBytesRead)
              || NumberOfBytesRead != 8 )
            {
              v19 = 0;
LABEL_29:
              tlx::file_handle_traits::operator()(v16, v19);
              break;
            }
            if ( Buffer
              && ReadProcessMemory(v10, (LPCVOID)(Buffer + (unsigned int)dword_1800B2368), &v21, 4u, 0)
              && v21 == *((_DWORD *)a1 + 4) )
            {
              v5 = a3;
              *a3 = LowPart;
              tlx::file_handle_traits::operator()(v16, 0);
              goto LABEL_31;
            }
            v12 = (struct _SYSTEM_PROCESS_INFORMATION *)((char *)v12 + 136);
            tlx::file_handle_traits::operator()(v16, 0);
            ++v7;
          }
          v5 = a3;
          break;
        }
        if ( !a2->NextEntryOffset )
          break;
        a2 = (struct _SYSTEM_PROCESS_INFORMATION *)((char *)a2 + a2->NextEntryOffset);
      }
    }
LABEL_31:
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, *v5);
    v9 = v10;
  }
  else
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      WPP_SF_(v8[2], 41, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
    v9 = 0;
  }
  tlx::file_handle_traits::operator()(v8, v9);
}

```

## disassembly

```asm
0x18003f5cc  mov     rax, rsp
0x18003f5cf  mov     [rax+10h], rbx
0x18003f5d3  mov     [rax+18h], r8
0x18003f5d7  mov     [rax+8], rcx
0x18003f5db  push    rbp
0x18003f5dc  push    rsi
0x18003f5dd  push    rdi
0x18003f5de  push    r12
0x18003f5e0  push    r13
0x18003f5e2  push    r14
0x18003f5e4  push    r15
0x18003f5e6  lea     rbp, [rax-5Fh]
0x18003f5ea  sub     rsp, 90h
0x18003f5f1  mov     rbx, r9
0x18003f5f4  mov     rsi, r8
0x18003f5f7  mov     rdi, rdx
0x18003f5fa  xor     r15d, r15d
0x18003f5fd  mov     [rbp+57h+var_78], r15
0x18003f601  xorps   xmm0, xmm0
0x18003f604  movups  [rbp+57h+ThreadInformation], xmm0
0x18003f608  movups  [rbp+57h+var_58], xmm0
0x18003f60c  movups  [rbp+57h+var_48], xmm0
0x18003f610  mov     [rbp+57h+var_8C], r15d
0x18003f614  mov     [rbp+57h+NumberOfBytesRead], r15
0x18003f618  mov     [rbp+57h+ReturnLength], r15d
0x18003f61c  mov     [rbp+57h+Buffer], r15
0x18003f620  lea     rax, WPP_GLOBAL_Control
0x18003f627  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f62e  cmp     rcx, rax
0x18003f631  jz      short loc_18003F65B
0x18003f633  test    byte ptr [rcx+1Ch], 4
0x18003f637  jz      short loc_18003F65B
0x18003f639  lea     edx, [r15+28h]
0x18003f63d  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003f644  mov     rcx, [rcx+10h]
0x18003f648  call    WPP_SF_
0x18003f64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f654  lea     rax, WPP_GLOBAL_Control
0x18003f65b  cmp     cs:dword_1800B2368, r15d
0x18003f662  jnz     short loc_18003F68C
0x18003f664  cmp     rcx, rax
0x18003f667  jz      short loc_18003F685
0x18003f669  test    byte ptr [rcx+1Ch], 4
0x18003f66d  jz      short loc_18003F685
0x18003f66f  mov     edx, 29h ; ')'
0x18003f674  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003f67b  mov     rcx, [rcx+10h]
0x18003f67f  call    WPP_SF_
0x18003f684  nop
0x18003f685  xor     edx, edx
0x18003f687  jmp     loc_18003F853
0x18003f68c  mov     r8d, [rbx]; dwProcessId
0x18003f68f  xor     edx, edx; bInheritHandle
0x18003f691  mov     ecx, 450h; dwDesiredAccess
0x18003f696  call    cs:__imp_OpenProcess
0x18003f69d  nop     dword ptr [rax+rax+00h]
0x18003f6a2  mov     r14, rax
0x18003f6a5  mov     [rbp+57h+var_78], rax
0x18003f6a9  xor     edx, edx
0x18003f6ab  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f6b0  lea     rcx, [r14+1]
0x18003f6b4  cmp     rcx, 1
0x18003f6b8  jbe     loc_18003F81E
0x18003f6be  mov     rcx, r14; void *
0x18003f6c1  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18003f6c6  test    eax, eax
0x18003f6c8  jnz     loc_18003F81E
0x18003f6ce  test    rdi, rdi
0x18003f6d1  jz      loc_18003F81E
0x18003f6d7  mov     eax, [rdi+50h]
0x18003f6da  cmp     [rbx], eax
0x18003f6dc  jz      short loc_18003F6EE
0x18003f6de  cmp     [rdi], r15d
0x18003f6e1  jz      loc_18003F81E
0x18003f6e7  mov     eax, [rdi]
0x18003f6e9  add     rdi, rax
0x18003f6ec  jmp     short loc_18003F6CE
0x18003f6ee  lea     r13, [rdi+100h]
0x18003f6f5  cmp     r15d, [rdi+4]
0x18003f6f9  jnb     loc_18003F81A
0x18003f6ff  mov     r12d, [r13+30h]
0x18003f703  mov     r8d, r12d; dwThreadId
0x18003f706  xor     edx, edx; bInheritHandle
0x18003f708  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18003f70b  call    cs:__imp_OpenThread
0x18003f712  nop     dword ptr [rax+rax+00h]
0x18003f717  mov     rsi, rax
0x18003f71a  mov     [rbp+57h+var_70], rax
0x18003f71e  lea     rcx, [rax+1]
0x18003f722  cmp     rcx, 1
0x18003f726  jbe     loc_18003F812
0x18003f72c  lea     rax, [rbp+57h+ReturnLength]
0x18003f730  mov     [rsp+20h], rax; ReturnLength
0x18003f735  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18003f73b  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18003f73f  xor     edx, edx; ThreadInformationClass
0x18003f741  mov     rcx, rsi; ThreadHandle
0x18003f744  call    cs:__imp_NtQueryInformationThread
0x18003f74b  nop     dword ptr [rax+rax+00h]
0x18003f750  mov     ebx, eax
0x18003f752  mov     rdx, rsi
0x18003f755  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f75a  test    ebx, ebx
0x18003f75c  js      loc_18003F80E
0x18003f762  cmp     [rbp+57h+ReturnLength], 30h ; '0'
0x18003f766  jnz     loc_18003F80E
0x18003f76c  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]
0x18003f770  add     rdx, 1758h; lpBaseAddress
0x18003f777  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18003f77b  mov     [rsp+20h], rax; lpNumberOfBytesRead
0x18003f780  mov     r9d, 8; nSize
0x18003f786  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18003f78a  mov     rcx, r14; hProcess
0x18003f78d  call    cs:__imp_ReadProcessMemory
0x18003f794  nop     dword ptr [rax+rax+00h]
0x18003f799  test    eax, eax
0x18003f79b  jz      short loc_18003F80E
0x18003f79d  cmp     [rbp+57h+NumberOfBytesRead], 8
0x18003f7a2  jnz     short loc_18003F80E
0x18003f7a4  mov     rax, [rbp+57h+Buffer]
0x18003f7a8  test    rax, rax
0x18003f7ab  jz      short loc_18003F7E8
0x18003f7ad  mov     edx, cs:dword_1800B2368
0x18003f7b3  add     rdx, rax; lpBaseAddress
0x18003f7b6  mov     qword ptr [rsp+20h], 0; lpNumberOfBytesRead
0x18003f7bf  mov     r9d, 4; nSize
0x18003f7c5  lea     r8, [rbp+57h+var_8C]; lpBuffer
0x18003f7c9  mov     rcx, r14; hProcess
0x18003f7cc  call    cs:__imp_ReadProcessMemory
0x18003f7d3  nop     dword ptr [rax+rax+00h]
0x18003f7d8  test    eax, eax
0x18003f7da  jz      short loc_18003F7E8
0x18003f7dc  mov     rax, [rbp+57h+arg_0]
0x18003f7e0  mov     eax, [rax+10h]
0x18003f7e3  cmp     [rbp+57h+var_8C], eax
0x18003f7e6  jz      short loc_18003F7FE
0x18003f7e8  add     r13, 88h
0x18003f7ef  xor     edx, edx
0x18003f7f1  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f7f6  inc     r15d
0x18003f7f9  jmp     loc_18003F6F5
0x18003f7fe  mov     rsi, [rbp+57h+arg_10]
0x18003f802  mov     [rsi], r12d
0x18003f805  xor     edx, edx
0x18003f807  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f80c  jmp     short loc_18003F81E
0x18003f80e  xor     edx, edx
0x18003f810  jmp     short loc_18003F815
0x18003f812  mov     rdx, rsi
0x18003f815  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f81a  mov     rsi, [rbp+57h+arg_10]
0x18003f81e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f825  lea     rax, WPP_GLOBAL_Control
0x18003f82c  cmp     rcx, rax
0x18003f82f  jz      short loc_18003F850
0x18003f831  test    byte ptr [rcx+1Ch], 4
0x18003f835  jz      short loc_18003F850
0x18003f837  mov     edx, 2Ah ; '*'
0x18003f83c  mov     r9d, [rsi]
0x18003f83f  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003f846  mov     rcx, [rcx+10h]
0x18003f84a  call    WPP_SF_d
0x18003f84f  nop
0x18003f850  mov     rdx, r14
0x18003f853  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f858  mov     rbx, [rsp+0C0h+arg_8]
0x18003f860  add     rsp, 90h
0x18003f867  pop     r15
0x18003f869  pop     r14
0x18003f86b  pop     r13
0x18003f86d  pop     r12
0x18003f86f  pop     rdi
0x18003f870  pop     rsi
0x18003f871  pop     rbp
0x18003f872  retn
```

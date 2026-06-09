# K32GetModuleBaseNameW

- ea: `0x1800ad4b0`
- end: `0x1800ad719`
- name: `K32GetModuleBaseNameW`
- size: `617`
- prototype: `DWORD __stdcall(HANDLE hProcess, HMODULE hModule, LPWSTR lpBaseName, DWORD nSize)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800ad410`

## callees

- `0x1800134a0`
- `0x180037714`
- `0x1800ad4b0`
- `0x1800ade50`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800ad70a`
- `ntdll!RtlNtStatusToDosError` at `0x1800ad70a`
- `ntdll!NtQueryInformationProcess` at `0x1800ad52d`
- `ntdll!NtQueryInformationProcess` at `0x1800ad52d`
- `ntdll!NtReadVirtualMemory` at `0x1800ad56e`
- `ntdll!NtReadVirtualMemory` at `0x1800ad5ab`
- `ntdll!NtReadVirtualMemory` at `0x1800ad5ef`
- `ntdll!NtReadVirtualMemory` at `0x1800ad65e`
- `ntdll!NtReadVirtualMemory` at `0x1800ad6cf`
- `ntdll!NtReadVirtualMemory` at `0x1800ad56e`
- `ntdll!NtReadVirtualMemory` at `0x1800ad5ab`
- `ntdll!NtReadVirtualMemory` at `0x1800ad5ef`
- `ntdll!NtReadVirtualMemory` at `0x1800ad65e`
- `ntdll!NtReadVirtualMemory` at `0x1800ad6cf`

## pseudocode

```c
DWORD __stdcall K32GetModuleBaseNameW(HANDLE hProcess, HMODULE hModule, LPWSTR lpBaseName, DWORD nSize)
{
  int InformationProcess; // eax
  __int64 v9; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // rax
  ULONG v14; // ecx
  DWORD v15; // ebx
  unsigned int v16; // edx
  __int64 v17; // rsi
  DWORD v18; // r8d
  ULONG_PTR NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h]
  HMODULE v27; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v28; // [rsp+D8h] [rbp-28h]
  PVOID BaseAddress; // [rsp+E0h] [rbp-20h]
  __int16 v30; // [rsp+ECh] [rbp-14h]

  memset_0(v25, 0, 0x88u);
  v21 = hModule;
  Buffer = 0;
  v22 = 0;
  memset(ProcessInformation, 0, 44);
  InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
  {
    v14 = RtlNtStatusToDosError(InformationProcess);
    goto LABEL_29;
  }
  v9 = *((_QWORD *)&ProcessInformation[0] + 1);
  if ( !v21
    && (NumberOfBytesRead = 0,
        v10 = NtReadVirtualMemory(
                hProcess,
                (PVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 16LL),
                &v21,
                8u,
                &NumberOfBytesRead),
        v10 < 0)
    || (NumberOfBytesRead = 0,
        v10 = NtReadVirtualMemory(hProcess, (PVOID)(v9 + 24), &Buffer, 8u, &NumberOfBytesRead),
        v10 < 0) )
  {
LABEL_22:
    BaseSetLastNTError((unsigned int)v10);
    return 0;
  }
  if ( !Buffer )
  {
LABEL_11:
    v14 = 6;
LABEL_29:
    SetLastError_0(v14);
    return 0;
  }
  v11 = Buffer + 32;
  NumberOfBytesRead = 0;
  v10 = NtReadVirtualMemory(hProcess, (PVOID)(Buffer + 32), &v22, 8u, &NumberOfBytesRead);
  if ( v10 < 0 )
    goto LABEL_22;
  v12 = 0;
  v13 = v22;
  while ( v13 != v11 )
  {
    NumberOfBytesRead = 0;
    v10 = NtReadVirtualMemory(hProcess, (PVOID)(v13 - 16), v25, 0x88u, &NumberOfBytesRead);
    if ( v10 < 0 )
      goto LABEL_22;
    if ( v27 == v21 )
    {
      if ( !v30 )
        return 0;
      goto LABEL_13;
    }
    v13 = v26;
    ++v12;
    v22 = v26;
    if ( v12 > 0x2710 )
      goto LABEL_11;
  }
  if ( !(unsigned int)Wow64FindModuleEx(hProcess) )
    return 0;
LABEL_13:
  v15 = 2 * nSize;
  v16 = v28 + 2;
  NumberOfBytesRead = 0;
  v17 = 2 * nSize;
  if ( 2 * nSize >= v16 )
    v17 = v16;
  v10 = NtReadVirtualMemory(hProcess, BaseAddress, lpBaseName, (unsigned int)v17, &NumberOfBytesRead);
  if ( v10 < 0 )
    goto LABEL_22;
  v18 = v17 - 2;
  if ( v17 != v28 + 2LL )
    v18 = v17;
  if ( v18 >= v15 )
  {
    if ( v15 )
      lpBaseName[((unsigned __int64)v15 >> 1) - 1] = 0;
  }
  else
  {
    lpBaseName[(unsigned __int64)v18 >> 1] = 0;
  }
  return v18 >> 1;
}

```

## disassembly

```asm
0x1800ad4b0  push    rbp; GetModuleBaseNameW
0x1800ad4b2  push    rbx
0x1800ad4b3  push    rsi
0x1800ad4b4  push    rdi
0x1800ad4b5  push    r12
0x1800ad4b7  push    r13
0x1800ad4b9  push    r14
0x1800ad4bb  push    r15
0x1800ad4bd  lea     rbp, [rsp-28h]
0x1800ad4c2  sub     rsp, 128h
0x1800ad4c9  mov     rax, cs:__security_cookie
0x1800ad4d0  xor     rax, rsp
0x1800ad4d3  mov     [rbp+60h+var_50], rax
0x1800ad4d7  mov     r14, r8
0x1800ad4da  mov     rbx, rdx
0x1800ad4dd  mov     rdi, rcx
0x1800ad4e0  xor     edx, edx; Val
0x1800ad4e2  mov     r8d, 88h; Size
0x1800ad4e8  lea     rcx, [rbp+60h+var_E0]; void *
0x1800ad4ec  mov     r15d, r9d
0x1800ad4ef  call    memset_0
0x1800ad4f4  xorps   xmm0, xmm0
0x1800ad4f7  mov     [rsp+160h+var_128], rbx
0x1800ad4fc  xor     r12d, r12d
0x1800ad4ff  lea     r8, [rsp+160h+ProcessInformation]; ProcessInformation
0x1800ad504  xor     eax, eax
0x1800ad506  mov     [rsp+160h+Buffer], r12
0x1800ad50b  movups  xmmword ptr [rsp+160h+var_100], xmm0
0x1800ad510  xor     edx, edx; ProcessInformationClass
0x1800ad512  mov     [rsp+160h+var_120], r12
0x1800ad517  mov     rcx, rdi; ProcessHandle
0x1800ad51a  mov     [rsp+160h+ReturnLength], r12; ReturnLength
0x1800ad51f  lea     r9d, [rax+30h]; ProcessInformationLength
0x1800ad523  movups  [rsp+160h+ProcessInformation], xmm0
0x1800ad528  movups  xmmword ptr [rsp+160h+var_100+0Ch], xmm0
0x1800ad52d  call    cs:__imp_NtQueryInformationProcess
0x1800ad533  test    eax, eax
0x1800ad535  js      loc_1800AD708
0x1800ad53b  lea     r13d, [r12+8]
0x1800ad540  mov     rbx, qword ptr [rsp+160h+ProcessInformation+8]
0x1800ad545  cmp     [rsp+160h+var_128], r12
0x1800ad54a  jz      loc_1800AD6B1
0x1800ad550  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800ad555  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800ad55a  lea     rdx, [rbx+18h]; BaseAddress
0x1800ad55e  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800ad563  mov     r9, r13; NumberOfBytesToRead
0x1800ad566  lea     r8, [rsp+160h+Buffer]; Buffer
0x1800ad56b  mov     rcx, rdi; ProcessHandle
0x1800ad56e  call    cs:__imp_NtReadVirtualMemory
0x1800ad574  test    eax, eax
0x1800ad576  js      loc_1800AD6DD
0x1800ad57c  mov     rax, [rsp+160h+Buffer]
0x1800ad581  test    rax, rax
0x1800ad584  jz      loc_1800AD61B
0x1800ad58a  lea     rsi, [rax+20h]
0x1800ad58e  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800ad593  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800ad598  mov     rdx, rsi; BaseAddress
0x1800ad59b  mov     r9, r13; NumberOfBytesToRead
0x1800ad59e  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800ad5a3  lea     r8, [rsp+160h+var_120]; Buffer
0x1800ad5a8  mov     rcx, rdi; ProcessHandle
0x1800ad5ab  call    cs:__imp_NtReadVirtualMemory
0x1800ad5b1  test    eax, eax
0x1800ad5b3  js      loc_1800AD6DD
0x1800ad5b9  mov     rdx, [rsp+160h+var_128]
0x1800ad5be  mov     ebx, r12d
0x1800ad5c1  mov     rax, [rsp+160h+var_120]
0x1800ad5c6  lea     r8, [rbp+60h+var_E0]; Buffer
0x1800ad5ca  mov     rcx, rdi; ProcessHandle
0x1800ad5cd  cmp     rax, rsi
0x1800ad5d0  jz      loc_1800AD6F9
0x1800ad5d6  lea     rdx, [rax-10h]; BaseAddress
0x1800ad5da  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800ad5df  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800ad5e4  mov     r9d, 88h; NumberOfBytesToRead
0x1800ad5ea  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800ad5ef  call    cs:__imp_NtReadVirtualMemory
0x1800ad5f5  test    eax, eax
0x1800ad5f7  js      loc_1800AD6DD
0x1800ad5fd  mov     rdx, [rsp+160h+var_128]
0x1800ad602  cmp     [rbp+60h+var_B0], rdx
0x1800ad606  jz      short loc_1800AD625
0x1800ad608  mov     rax, [rbp+60h+var_D0]
0x1800ad60c  inc     ebx
0x1800ad60e  mov     [rsp+160h+var_120], rax
0x1800ad613  cmp     ebx, 2710h
0x1800ad619  jbe     short loc_1800AD5C6
0x1800ad61b  mov     ecx, 6
0x1800ad620  jmp     loc_1800AD712
0x1800ad625  cmp     [rbp+60h+var_74], r12w
0x1800ad62a  jz      loc_1800AD6E4
0x1800ad630  movzx   edx, [rbp+60h+var_88]
0x1800ad634  lea     ebx, [r15+r15]
0x1800ad638  add     edx, 2
0x1800ad63b  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800ad640  cmp     ebx, edx
0x1800ad642  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800ad647  mov     esi, ebx
0x1800ad649  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800ad64e  cmovnb  esi, edx
0x1800ad651  mov     r8, r14; Buffer
0x1800ad654  mov     rdx, [rbp+60h+BaseAddress]; BaseAddress
0x1800ad658  mov     r9d, esi; NumberOfBytesToRead
0x1800ad65b  mov     rcx, rdi; ProcessHandle
0x1800ad65e  call    cs:__imp_NtReadVirtualMemory
0x1800ad664  test    eax, eax
0x1800ad666  js      short loc_1800AD6DD
0x1800ad668  movzx   eax, [rbp+60h+var_88]
0x1800ad66c  lea     r8d, [rsi-2]
0x1800ad670  add     rax, 2
0x1800ad674  cmp     rsi, rax
0x1800ad677  cmovnz  r8d, esi
0x1800ad67b  cmp     r8d, ebx
0x1800ad67e  jnb     short loc_1800AD6E8
0x1800ad680  mov     ecx, r8d
0x1800ad683  shr     rcx, 1
0x1800ad686  mov     [r14+rcx*2], r12w
0x1800ad68b  shr     r8d, 1
0x1800ad68e  mov     eax, r8d
0x1800ad691  mov     rcx, [rbp+60h+var_50]
0x1800ad695  xor     rcx, rsp; StackCookie
0x1800ad698  call    __security_check_cookie
0x1800ad69d  add     rsp, 128h
0x1800ad6a4  pop     r15
0x1800ad6a6  pop     r14
0x1800ad6a8  pop     r13
0x1800ad6aa  pop     r12
0x1800ad6ac  pop     rdi
0x1800ad6ad  pop     rsi
0x1800ad6ae  pop     rbx
0x1800ad6af  pop     rbp
0x1800ad6b0  retn
0x1800ad6b1  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800ad6b6  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800ad6bb  lea     rdx, [rbx+10h]; BaseAddress
0x1800ad6bf  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800ad6c4  mov     r9, r13; NumberOfBytesToRead
0x1800ad6c7  lea     r8, [rsp+160h+var_128]; Buffer
0x1800ad6cc  mov     rcx, rdi; ProcessHandle
0x1800ad6cf  call    cs:__imp_NtReadVirtualMemory
0x1800ad6d5  test    eax, eax
0x1800ad6d7  jns     loc_1800AD550
0x1800ad6dd  mov     ecx, eax
0x1800ad6df  call    BaseSetLastNTError
0x1800ad6e4  xor     eax, eax
0x1800ad6e6  jmp     short loc_1800AD691
0x1800ad6e8  test    ebx, ebx
0x1800ad6ea  jz      short loc_1800AD68B
0x1800ad6ec  mov     edx, ebx
0x1800ad6ee  shr     rdx, 1
0x1800ad6f1  mov     [r14+rdx*2-2], r12w
0x1800ad6f7  jmp     short loc_1800AD68B
0x1800ad6f9  call    Wow64FindModuleEx
0x1800ad6fe  test    eax, eax
0x1800ad700  jnz     loc_1800AD630
0x1800ad706  jmp     short loc_1800AD6E4
0x1800ad708  mov     ecx, eax; Status
0x1800ad70a  call    cs:__imp_RtlNtStatusToDosError
0x1800ad710  mov     ecx, eax; dwErrCode
0x1800ad712  call    SetLastError_0
0x1800ad717  jmp     short loc_1800AD6E4
```

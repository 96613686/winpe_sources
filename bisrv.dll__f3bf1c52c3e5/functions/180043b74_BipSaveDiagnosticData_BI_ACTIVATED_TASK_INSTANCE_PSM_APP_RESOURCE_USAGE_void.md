# BipSaveDiagnosticData(_BI_ACTIVATED_TASK_INSTANCE *,_PSM_APP_RESOURCE_USAGE *,void *)

- ea: `0x180043b74`
- end: `0x180043e53`
- name: `?BipSaveDiagnosticData@@YAXPEAU_BI_ACTIVATED_TASK_INSTANCE@@PEAU_PSM_APP_RESOURCE_USAGE@@PEAX@Z`
- size: `735`
- prototype: `void(struct _BI_ACTIVATED_TASK_INSTANCE *, struct _PSM_APP_RESOURCE_USAGE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000f334`

## callees

- `0x180013d20`
- `0x180043b74`
- `0x180043e5c`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtWriteVirtualMemory` at `0x180043e30`
- `ntdll!NtWriteVirtualMemory` at `0x180043e30`
- `ntdll!NtReadVirtualMemory` at `0x180043c45`
- `ntdll!NtReadVirtualMemory` at `0x180043caf`
- `ntdll!NtReadVirtualMemory` at `0x180043ce2`
- `ntdll!NtReadVirtualMemory` at `0x180043c45`
- `ntdll!NtReadVirtualMemory` at `0x180043caf`
- `ntdll!NtReadVirtualMemory` at `0x180043ce2`
- `ntdll!NtQueryInformationProcess` at `0x180043c11`
- `ntdll!NtQueryInformationProcess` at `0x180043c80`
- `ntdll!NtQueryInformationProcess` at `0x180043c11`
- `ntdll!NtQueryInformationProcess` at `0x180043c80`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043d17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043d17`

## pseudocode

```c
void __fastcall BipSaveDiagnosticData(
        struct _BI_ACTIVATED_TASK_INSTANCE *a1,
        struct _PSM_APP_RESOURCE_USAGE *a2,
        void *a3)
{
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int8 v8; // al
  __int64 v9; // rcx
  char ActivationType; // al
  int v11; // r8d
  int v12; // eax
  ULONG_PTR NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Buffer; // [rsp+38h] [rbp-C8h] BYREF
  PVOID BaseAddress; // [rsp+40h] [rbp-C0h] BYREF
  __int64 ProcessInformation; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v18[3]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v19[230]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v20[8]; // [rsp+428h] [rbp+328h] BYREF
  int v21; // [rsp+468h] [rbp+368h]

  SystemTimeAsFileTime = 0;
  BaseAddress = 0;
  NumberOfBytesRead = 0;
  memset(v18, 0, sizeof(v18));
  memset_0(v19, 0, 0x498u);
  ProcessInformation = 0;
  Buffer = 0;
  if ( NtQueryInformationProcess(a3, ProcessWow64Information, &ProcessInformation, 8u, 0) >= 0 )
  {
    if ( ProcessInformation )
    {
      if ( NtReadVirtualMemory(a3, (PVOID)(ProcessInformation + 20), &Buffer, 4u, &NumberOfBytesRead) < 0
        || NumberOfBytesRead != 4 )
      {
        return;
      }
      v6 = Buffer;
      BaseAddress = (PVOID)Buffer;
    }
    else
    {
      if ( NtQueryInformationProcess(a3, ProcessBasicInformation, v18, 0x30u, 0) < 0
        || NtReadVirtualMemory(a3, (PVOID)(*((_QWORD *)&v18[0] + 1) + 40LL), &BaseAddress, 8u, &NumberOfBytesRead) < 0
        || NumberOfBytesRead != 8 )
      {
        return;
      }
      v6 = (unsigned __int64)BaseAddress;
    }
    if ( NtReadVirtualMemory(a3, (PVOID)v6, v19, 0x498u, &NumberOfBytesRead) >= 0
      && NumberOfBytesRead == 1176
      && v19[0] == 1176
      && v19[1] == 1464157250 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      memset_0(v20, 0, 0x48u);
      v7 = *((unsigned int *)a1 + 70);
      v20[0] = *(_QWORD *)((char *)a1 + 156);
      v20[1] = SystemTimeAsFileTime;
      v20[2] = *((_QWORD *)a2 + 5) - *((_QWORD *)a1 + 26);
      v20[3] = *((_QWORD *)a2 + 6) - *((_QWORD *)a1 + 27);
      v20[4] = *((_QWORD *)a2 + 4) - *((_QWORD *)a1 + 25);
      v20[5] = *((_QWORD *)a2 + 3) - *((_QWORD *)a1 + 24);
      v20[6] = *(_QWORD *)a2 - *((_QWORD *)a1 + 21);
      v20[7] = *((_QWORD *)a2 + 1) - *((_QWORD *)a1 + 22);
      v8 = BipTaskCancellationReasonFromInternalReason(v7);
      v9 = *((_QWORD *)a1 + 8);
      v21 = v8;
      ActivationType = BipGetActivationType(v9);
      v12 = v11 | ((ActivationType & 7) << 8);
      v21 = v12;
      if ( (*((_BYTE *)P + 48) & 2) != 0 )
      {
        v12 |= 0x800u;
        v21 = v12;
      }
      if ( (*((_BYTE *)P + 48) & 1) != 0 )
        v21 = v12 | 0x1000;
      NtWriteVirtualMemory(a3, (char *)BaseAddress + 920, v20, 0x48u, 0);
    }
  }
}

```

## disassembly

```asm
0x180043b74  push    rbp
0x180043b76  push    rbx
0x180043b77  push    rsi
0x180043b78  push    rdi
0x180043b79  push    r15
0x180043b7b  lea     rbp, [rsp-440h]
0x180043b83  sub     rsp, 540h
0x180043b8a  mov     rax, cs:__security_cookie
0x180043b91  xor     rax, rsp
0x180043b94  mov     [rbp+460h+var_30], rax
0x180043b9b  xorps   xmm0, xmm0
0x180043b9e  mov     qword ptr [rsp+560h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180043ba7  mov     rbx, r8
0x180043baa  mov     [rsp+560h+BaseAddress], 0
0x180043bb3  mov     rsi, rdx
0x180043bb6  mov     [rsp+560h+NumberOfBytesRead], 0
0x180043bbf  mov     rdi, rcx
0x180043bc2  mov     r15d, 498h
0x180043bc8  mov     r8d, r15d; Size
0x180043bcb  lea     rcx, [rbp+460h+var_4D0]; void *
0x180043bcf  xor     edx, edx; Val
0x180043bd1  movups  [rsp+560h+var_508], xmm0
0x180043bd6  movups  [rsp+560h+var_4F8], xmm0
0x180043bdb  movups  [rsp+560h+var_4E8], xmm0
0x180043be0  call    memset_0
0x180043be5  mov     r9d, 8; ProcessInformationLength
0x180043beb  mov     [rsp+560h+ProcessInformation], 0
0x180043bf4  lea     r8, [rsp+560h+ProcessInformation]; ProcessInformation
0x180043bf9  mov     [rsp+560h+Buffer], 0
0x180043c01  mov     rcx, rbx; ProcessHandle
0x180043c04  mov     [rsp+560h+ReturnLength], 0; ReturnLength
0x180043c0d  lea     edx, [r9+12h]; ProcessInformationClass
0x180043c11  call    cs:__imp_NtQueryInformationProcess
0x180043c17  test    eax, eax
0x180043c19  js      loc_180043E36
0x180043c1f  mov     rdx, [rsp+560h+ProcessInformation]
0x180043c24  mov     rcx, rbx; ProcessHandle
0x180043c27  test    rdx, rdx
0x180043c2a  jz      short loc_180043C6A
0x180043c2c  lea     rax, [rsp+560h+NumberOfBytesRead]
0x180043c31  add     rdx, 14h; BaseAddress
0x180043c35  mov     r9d, 4; NumberOfBytesToRead
0x180043c3b  mov     [rsp+560h+ReturnLength], rax; NumberOfBytesRead
0x180043c40  lea     r8, [rsp+560h+Buffer]; Buffer
0x180043c45  call    cs:__imp_NtReadVirtualMemory
0x180043c4b  test    eax, eax
0x180043c4d  js      loc_180043E36
0x180043c53  cmp     [rsp+560h+NumberOfBytesRead], 4
0x180043c59  jnz     loc_180043E36
0x180043c5f  mov     edx, [rsp+560h+Buffer]
0x180043c63  mov     [rsp+560h+BaseAddress], rdx
0x180043c68  jmp     short loc_180043CCE
0x180043c6a  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180043c70  mov     [rsp+560h+ReturnLength], 0; ReturnLength
0x180043c79  lea     r8, [rsp+560h+var_508]; ProcessInformation
0x180043c7e  xor     edx, edx; ProcessInformationClass
0x180043c80  call    cs:__imp_NtQueryInformationProcess
0x180043c86  test    eax, eax
0x180043c88  js      loc_180043E36
0x180043c8e  mov     rdx, qword ptr [rsp+560h+var_508+8]
0x180043c93  lea     rax, [rsp+560h+NumberOfBytesRead]
0x180043c98  add     rdx, 28h ; '('; BaseAddress
0x180043c9c  mov     [rsp+560h+ReturnLength], rax; NumberOfBytesRead
0x180043ca1  mov     r9d, 8; NumberOfBytesToRead
0x180043ca7  lea     r8, [rsp+560h+BaseAddress]; Buffer
0x180043cac  mov     rcx, rbx; ProcessHandle
0x180043caf  call    cs:__imp_NtReadVirtualMemory
0x180043cb5  test    eax, eax
0x180043cb7  js      loc_180043E36
0x180043cbd  cmp     [rsp+560h+NumberOfBytesRead], 8
0x180043cc3  jnz     loc_180043E36
0x180043cc9  mov     rdx, [rsp+560h+BaseAddress]; BaseAddress
0x180043cce  lea     rax, [rsp+560h+NumberOfBytesRead]
0x180043cd3  mov     r9, r15; NumberOfBytesToRead
0x180043cd6  lea     r8, [rbp+460h+var_4D0]; Buffer
0x180043cda  mov     [rsp+560h+ReturnLength], rax; NumberOfBytesRead
0x180043cdf  mov     rcx, rbx; ProcessHandle
0x180043ce2  call    cs:__imp_NtReadVirtualMemory
0x180043ce8  test    eax, eax
0x180043cea  js      loc_180043E36
0x180043cf0  cmp     [rsp+560h+NumberOfBytesRead], r15
0x180043cf5  jnz     loc_180043E36
0x180043cfb  cmp     [rbp+460h+var_4D0], r15d
0x180043cff  jnz     loc_180043E36
0x180043d05  cmp     [rbp+460h+var_4CC], 57454442h
0x180043d0c  jnz     loc_180043E36
0x180043d12  lea     rcx, [rsp+560h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180043d17  call    cs:__imp_GetSystemTimeAsFileTime
0x180043d1d  mov     r15d, 48h ; 'H'
0x180043d23  lea     rcx, [rbp+460h+var_138]; void *
0x180043d2a  mov     r8d, r15d; Size
0x180043d2d  xor     edx, edx; Val
0x180043d2f  call    memset_0
0x180043d34  mov     rax, [rdi+9Ch]
0x180043d3b  mov     ecx, [rdi+118h]
0x180043d41  mov     [rbp+460h+var_138], rax
0x180043d48  mov     rax, qword ptr [rsp+560h+SystemTimeAsFileTime.dwLowDateTime]
0x180043d4d  mov     [rbp+460h+var_130], rax
0x180043d54  mov     rax, [rsi+28h]
0x180043d58  sub     rax, [rdi+0D0h]
0x180043d5f  mov     [rbp+460h+var_128], rax
0x180043d66  mov     rax, [rsi+30h]
0x180043d6a  sub     rax, [rdi+0D8h]
0x180043d71  mov     [rbp+460h+var_120], rax
0x180043d78  mov     rax, [rsi+20h]
0x180043d7c  sub     rax, [rdi+0C8h]
0x180043d83  mov     [rbp+460h+var_118], rax
0x180043d8a  mov     rax, [rsi+18h]
0x180043d8e  sub     rax, [rdi+0C0h]
0x180043d95  mov     [rbp+460h+var_110], rax
0x180043d9c  mov     rax, [rsi]
0x180043d9f  sub     rax, [rdi+0A8h]
0x180043da6  mov     [rbp+460h+var_108], rax
0x180043dad  mov     rax, [rsi+8]
0x180043db1  sub     rax, [rdi+0B0h]
0x180043db8  mov     [rbp+460h+var_100], rax
0x180043dbf  call    BipTaskCancellationReasonFromInternalReason
0x180043dc4  mov     rcx, [rdi+40h]
0x180043dc8  movzx   r8d, al
0x180043dcc  mov     [rbp+460h+var_F8], r8d
0x180043dd3  call    BipGetActivationType
0x180043dd8  mov     rcx, cs:P
0x180043ddf  and     eax, 7
0x180043de2  shl     eax, 8
0x180043de5  or      eax, r8d
0x180043de8  mov     [rbp+460h+var_F8], eax
0x180043dee  test    byte ptr [rcx+30h], 2
0x180043df2  jz      short loc_180043DFE
0x180043df4  bts     eax, 0Bh
0x180043df8  mov     [rbp+460h+var_F8], eax
0x180043dfe  test    byte ptr [rcx+30h], 1
0x180043e02  jz      short loc_180043E0E
0x180043e04  bts     eax, 0Ch
0x180043e08  mov     [rbp+460h+var_F8], eax
0x180043e0e  mov     rdx, [rsp+560h+BaseAddress]
0x180043e13  lea     r8, [rbp+460h+var_138]; Buffer
0x180043e1a  add     rdx, 398h; BaseAddress
0x180043e21  mov     [rsp+560h+ReturnLength], 0; NumberOfBytesWritten
0x180043e2a  mov     r9, r15; NumberOfBytesToWrite
0x180043e2d  mov     rcx, rbx; ProcessHandle
0x180043e30  call    cs:__imp_NtWriteVirtualMemory
0x180043e36  mov     rcx, [rbp+460h+var_30]
0x180043e3d  xor     rcx, rsp; StackCookie
0x180043e40  call    __security_check_cookie
0x180043e45  add     rsp, 540h
0x180043e4c  pop     r15
0x180043e4e  pop     rdi
0x180043e4f  pop     rsi
0x180043e50  pop     rbx
0x180043e51  pop     rbp
0x180043e52  retn
```

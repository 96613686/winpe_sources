# CfSetDiagFlags

- ea: `0x140045ff0`
- end: `0x1400460f3`
- name: `CfSetDiagFlags`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14003a8e8`

## callees

- `0x140045ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400460c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400460c8`
- `ntdll!RtlNtStatusToDosError` at `0x14004603a`
- `ntdll!RtlNtStatusToDosError` at `0x14004603a`
- `ntdll!NtQueryInformationProcess` at `0x140046032`
- `ntdll!NtQueryInformationProcess` at `0x140046032`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140046075`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140046075`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1400460ba`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1400460ba`

## pseudocode

```c
__int64 CfSetDiagFlags()
{
  NTSTATUS InformationProcess; // eax
  signed int v1; // eax
  bool v2; // sf
  signed int v3; // eax
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  signed int v7; // eax
  bool v8; // sf
  int v10; // [rsp+30h] [rbp-40h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+38h] [rbp-38h] BYREF
  unsigned int Buffer; // [rsp+80h] [rbp+10h] BYREF

  v10 = 1;
  Buffer = 0;
  memset(ProcessInformation, 0, 44);
  InformationProcess = NtQueryInformationProcess(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         ProcessBasicInformation,
                         ProcessInformation,
                         0x30u,
                         0);
  v1 = RtlNtStatusToDosError(InformationProcess);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( v2 )
    return 0;
  if ( ReadProcessMemory(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 1964LL),
         &Buffer,
         4u,
         0) )
  {
    v3 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    v3 = (unsigned __int16)LastError | 0x80070000;
  }
  v5 = v3 < 0;
LABEL_9:
  if ( v5 )
    return 0;
  if ( WriteProcessMemory(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         (LPVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 1964LL),
         &v10,
         4u,
         0) )
  {
    v6 = 0;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7 < 0;
    if ( v7 <= 0 )
      goto LABEL_15;
    v6 = (unsigned __int16)v7 | 0x80070000;
  }
  v8 = v6 < 0;
LABEL_15:
  if ( !v8 )
    return Buffer;
  return 0;
}

```

## disassembly

```asm
0x140045ff0  mov     [rsp-8+arg_8], r14
0x140045ff5  mov     [rsp-8+Buffer], ecx
0x140045ff9  push    rbp
0x140045ffa  mov     rbp, rsp
0x140045ffd  sub     rsp, 70h
0x140046001  xor     eax, eax
0x140046003  mov     [rbp+var_40], 1
0x14004600a  xorps   xmm0, xmm0
0x14004600d  mov     [rbp+Buffer], eax
0x140046010  movups  xmmword ptr [rbp+var_28], xmm0
0x140046014  or      r14, 0FFFFFFFFFFFFFFFFh
0x140046018  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14004601d  lea     r9d, [rax+30h]; ProcessInformationLength
0x140046021  xor     edx, edx; ProcessInformationClass
0x140046023  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x140046027  mov     rcx, r14; ProcessHandle
0x14004602a  movups  [rbp+ProcessInformation], xmm0
0x14004602e  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x140046032  call    cs:__imp_NtQueryInformationProcess
0x140046038  mov     ecx, eax; Status
0x14004603a  call    cs:__imp_RtlNtStatusToDosError
0x140046040  test    eax, eax
0x140046042  jle     short loc_14004604E
0x140046044  movzx   eax, ax
0x140046047  or      eax, 80070000h
0x14004604c  test    eax, eax
0x14004604e  js      loc_1400460E3
0x140046054  mov     rdx, qword ptr [rbp+ProcessInformation+8]
0x140046058  lea     r8, [rbp+Buffer]; lpBuffer
0x14004605c  add     rdx, 7ACh; lpBaseAddress
0x140046063  mov     [rsp+70h+ReturnLength], 0; lpNumberOfBytesRead
0x14004606c  mov     r9d, 4; nSize
0x140046072  mov     rcx, r14; hProcess
0x140046075  call    cs:__imp_ReadProcessMemory
0x14004607b  test    eax, eax
0x14004607d  jz      short loc_140046083
0x14004607f  xor     eax, eax
0x140046081  jmp     short loc_140046095
0x140046083  call    cs:__imp_GetLastError
0x140046089  test    eax, eax
0x14004608b  jle     short loc_140046097
0x14004608d  movzx   eax, ax
0x140046090  or      eax, 80070000h
0x140046095  test    eax, eax
0x140046097  js      short loc_1400460E3
0x140046099  mov     rdx, qword ptr [rbp+ProcessInformation+8]
0x14004609d  lea     r8, [rbp+var_40]; lpBuffer
0x1400460a1  add     rdx, 7ACh; lpBaseAddress
0x1400460a8  mov     [rsp+70h+ReturnLength], 0; lpNumberOfBytesWritten
0x1400460b1  mov     r9d, 4; nSize
0x1400460b7  mov     rcx, r14; hProcess
0x1400460ba  call    cs:__imp_WriteProcessMemory
0x1400460c0  test    eax, eax
0x1400460c2  jz      short loc_1400460C8
0x1400460c4  xor     eax, eax
0x1400460c6  jmp     short loc_1400460DA
0x1400460c8  call    cs:__imp_GetLastError
0x1400460ce  test    eax, eax
0x1400460d0  jle     short loc_1400460DC
0x1400460d2  movzx   eax, ax
0x1400460d5  or      eax, 80070000h
0x1400460da  test    eax, eax
0x1400460dc  js      short loc_1400460E3
0x1400460de  mov     eax, [rbp+Buffer]
0x1400460e1  jmp     short loc_1400460E5
0x1400460e3  xor     eax, eax
0x1400460e5  mov     r14, [rsp+70h+arg_8]
0x1400460ed  add     rsp, 70h
0x1400460f1  pop     rbp
0x1400460f2  retn
```

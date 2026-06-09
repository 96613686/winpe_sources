# OrchestrateBootCommand

- ea: `0x180047e1c`
- end: `0x1800481c1`
- name: `OrchestrateBootCommand`
- size: `933`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180024320`
- `0x180028e74`
- `0x180028f50`

## callees

- `0x180047e1c`
- `0x18004a000`
- `0x18004a728`
- `0x18004aa44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004815e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004815e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004816c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004816c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004817b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004817b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048193`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047eea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047f82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048017`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800480b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047eea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047f82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048017`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800480b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047ea6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047f43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047fd8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048073`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047ea6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047f43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047fd8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047ed6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047f6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048003`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004809e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047ed6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047f6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048003`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004809e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047ee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047f7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004800f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800480aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047ee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047f7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004800f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800480aa`

## pseudocode

```c
signed int __fastcall OrchestrateBootCommand(__int64 a1, DWORD a2)
{
  __int64 Expand; // rax
  _WORD *v3; // rdi
  bool v4; // r14
  LSTATUS v5; // ebx
  bool v6; // si
  LSTATUS v7; // ebx
  bool v8; // r15
  LSTATUS v9; // ebx
  int v10; // r14d
  LSTATUS v11; // esi
  int v12; // ebx
  __int64 v13; // rax
  HANDLE ProcessHeap; // rax
  signed int result; // eax
  signed int LastError; // eax
  bool v17; // sf
  __int64 Data; // [rsp+90h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+98h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF

  dwDisposition = a2;
  Data = a1;
  Expand = AllocateExpand(L"oobe\\windeploy.exe");
  LODWORD(Data) = 2;
  hKey = 0;
  v3 = (_WORD *)Expand;
  dwDisposition = 0;
  v4 = Expand != 0;
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( !v5 )
  {
    v5 = RegSetValueExW(hKey, L"SetupType", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  SetLastError(v5);
  LODWORD(Data) = 4;
  hKey = 0;
  dwDisposition = 0;
  v6 = v4 && v5 == 0;
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( !v7 )
  {
    v7 = RegSetValueExW(hKey, L"SetupPhase", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  SetLastError(v7);
  LODWORD(Data) = 0;
  hKey = 0;
  v8 = 0;
  if ( !v7 )
    v8 = v6;
  dwDisposition = 0;
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( !v9 )
  {
    v9 = RegSetValueExW(hKey, L"SystemSetupInProgress", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  SetLastError(v9);
  LODWORD(Data) = 1;
  hKey = 0;
  dwDisposition = 0;
  v10 = v8 && v9 == 0;
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( !v11 )
  {
    v11 = RegSetValueExW(hKey, L"OOBEInProgress", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  SetLastError(v11);
  v12 = 0;
  if ( !v11 )
    v12 = v10;
  if ( v12 )
  {
    if ( !v3 )
    {
      if ( !(unsigned int)RegExists(-2147483646, L"System\\Setup", L"CmdLine") )
        return 0;
      v12 = RegSetBinEx(-2147483646, L"System\\Setup", L"CmdLine", 1, &Class, 2);
      goto LABEL_22;
    }
    v13 = -1;
    do
      ++v13;
    while ( v3[v13] );
    v12 = RegSetBinEx(-2147483646, L"System\\Setup", L"CmdLine", 1, v3, 2 * (int)v13 + 2);
  }
  else if ( !v3 )
  {
    goto LABEL_24;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v3);
LABEL_22:
  if ( v12 )
    return 0;
LABEL_24:
  LastError = GetLastError();
  v17 = LastError < 0;
  if ( LastError > 0 )
    v17 = 1;
  if ( !v17 )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180047e1c  mov     [rsp-38h+arg_18], rbx
0x180047e21  mov     [rsp-38h+dwDisposition], edx
0x180047e25  mov     [rsp-38h+Data], rcx
0x180047e2a  push    rbp
0x180047e2b  push    rsi
0x180047e2c  push    rdi
0x180047e2d  push    r12
0x180047e2f  push    r13
0x180047e31  push    r14
0x180047e33  push    r15
0x180047e35  mov     rbp, rsp
0x180047e38  sub     rsp, 50h
0x180047e3c  lea     rcx, aOobeWindeployE; "oobe\\windeploy.exe"
0x180047e43  call    AllocateExpand
0x180047e48  xor     r12d, r12d
0x180047e4b  mov     dword ptr [rbp+Data], 2
0x180047e52  test    rax, rax
0x180047e55  mov     [rbp+hKey], r12
0x180047e59  mov     rdi, rax
0x180047e5c  mov     [rbp+dwDisposition], r12d
0x180047e60  lea     rax, [rbp+dwDisposition]
0x180047e64  mov     r14d, r12d
0x180047e67  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180047e6c  lea     r9, Class; lpClass
0x180047e73  lea     rax, [rbp+hKey]
0x180047e77  setnz   r14b
0x180047e7b  mov     [rsp+50h+phkResult], rax; phkResult
0x180047e80  lea     rdx, aSystemSetup; "System\\Setup"
0x180047e87  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180047e8c  mov     r15, 0FFFFFFFF80000002h
0x180047e93  mov     [rsp+50h+samDesired], 20006h; samDesired
0x180047e9b  xor     r8d, r8d; Reserved
0x180047e9e  mov     rcx, r15; hKey
0x180047ea1  mov     [rsp+50h+dwOptions], r12d; dwOptions
0x180047ea6  call    cs:__imp_RegCreateKeyExW
0x180047eac  lea     r13d, [r12+4]
0x180047eb1  mov     ebx, eax
0x180047eb3  test    eax, eax
0x180047eb5  jnz     short loc_180047EE8
0x180047eb7  mov     rcx, [rbp+hKey]; hKey
0x180047ebb  lea     rax, [rbp+Data]
0x180047ebf  mov     [rsp+50h+samDesired], r13d; cbData
0x180047ec4  lea     rdx, aSetuptype; "SetupType"
0x180047ecb  mov     r9d, r13d; dwType
0x180047ece  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180047ed3  xor     r8d, r8d; Reserved
0x180047ed6  call    cs:__imp_RegSetValueExW
0x180047edc  mov     rcx, [rbp+hKey]; hKey
0x180047ee0  mov     ebx, eax
0x180047ee2  call    cs:__imp_RegCloseKey
0x180047ee8  mov     ecx, ebx; dwErrCode
0x180047eea  call    cs:__imp_SetLastError
0x180047ef0  mov     esi, r12d
0x180047ef3  mov     dword ptr [rbp+Data], r13d
0x180047ef7  lea     rax, [rbp+dwDisposition]
0x180047efb  mov     [rbp+hKey], r12
0x180047eff  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180047f04  lea     rdx, aSystemSetup; "System\\Setup"
0x180047f0b  lea     rax, [rbp+hKey]
0x180047f0f  mov     [rbp+dwDisposition], r12d
0x180047f13  mov     [rsp+50h+phkResult], rax; phkResult
0x180047f18  test    ebx, ebx
0x180047f1a  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180047f1f  mov     rcx, r15; hKey
0x180047f22  setz    sil
0x180047f26  mov     [rsp+50h+samDesired], 20006h; samDesired
0x180047f2e  and     esi, r14d
0x180047f31  mov     [rsp+50h+dwOptions], r12d; dwOptions
0x180047f36  lea     r14, Class
0x180047f3d  xor     r8d, r8d; Reserved
0x180047f40  mov     r9, r14; lpClass
0x180047f43  call    cs:__imp_RegCreateKeyExW
0x180047f49  mov     ebx, eax
0x180047f4b  test    eax, eax
0x180047f4d  jnz     short loc_180047F80
0x180047f4f  mov     rcx, [rbp+hKey]; hKey
0x180047f53  lea     rax, [rbp+Data]
0x180047f57  mov     [rsp+50h+samDesired], r13d; cbData
0x180047f5c  lea     rdx, aSetupphase; "SetupPhase"
0x180047f63  mov     r9d, r13d; dwType
0x180047f66  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180047f6b  xor     r8d, r8d; Reserved
0x180047f6e  call    cs:__imp_RegSetValueExW
0x180047f74  mov     rcx, [rbp+hKey]; hKey
0x180047f78  mov     ebx, eax
0x180047f7a  call    cs:__imp_RegCloseKey
0x180047f80  mov     ecx, ebx; dwErrCode
0x180047f82  call    cs:__imp_SetLastError
0x180047f88  lea     rax, [rbp+dwDisposition]
0x180047f8c  mov     dword ptr [rbp+Data], r12d
0x180047f90  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180047f95  lea     rdx, aSystemSetup; "System\\Setup"
0x180047f9c  lea     rax, [rbp+hKey]
0x180047fa0  mov     [rbp+hKey], r12
0x180047fa4  mov     [rsp+50h+phkResult], rax; phkResult
0x180047fa9  test    ebx, ebx
0x180047fab  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180047fb0  mov     r15d, r12d
0x180047fb3  cmovz   r15d, esi
0x180047fb7  mov     [rsp+50h+samDesired], 20006h; samDesired
0x180047fbf  mov     rsi, 0FFFFFFFF80000002h
0x180047fc6  mov     [rsp+50h+dwOptions], r12d; dwOptions
0x180047fcb  mov     r9, r14; lpClass
0x180047fce  mov     [rbp+dwDisposition], r12d
0x180047fd2  xor     r8d, r8d; Reserved
0x180047fd5  mov     rcx, rsi; hKey
0x180047fd8  call    cs:__imp_RegCreateKeyExW
0x180047fde  mov     ebx, eax
0x180047fe0  test    eax, eax
0x180047fe2  jnz     short loc_180048015
0x180047fe4  mov     rcx, [rbp+hKey]; hKey
0x180047fe8  lea     rax, [rbp+Data]
0x180047fec  mov     [rsp+50h+samDesired], r13d; cbData
0x180047ff1  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x180047ff8  mov     r9d, r13d; dwType
0x180047ffb  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180048000  xor     r8d, r8d; Reserved
0x180048003  call    cs:__imp_RegSetValueExW
0x180048009  mov     rcx, [rbp+hKey]; hKey
0x18004800d  mov     ebx, eax
0x18004800f  call    cs:__imp_RegCloseKey
0x180048015  mov     ecx, ebx; dwErrCode
0x180048017  call    cs:__imp_SetLastError
0x18004801d  mov     r14d, r12d
0x180048020  mov     dword ptr [rbp+Data], 1
0x180048027  lea     rax, [rbp+dwDisposition]
0x18004802b  mov     [rbp+hKey], r12
0x18004802f  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180048034  lea     r9, Class; lpClass
0x18004803b  lea     rax, [rbp+hKey]
0x18004803f  mov     [rbp+dwDisposition], r12d
0x180048043  mov     [rsp+50h+phkResult], rax; phkResult
0x180048048  test    ebx, ebx
0x18004804a  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18004804f  mov     rcx, rsi; hKey
0x180048052  setz    r14b
0x180048056  mov     [rsp+50h+samDesired], 20006h; samDesired
0x18004805e  and     r14d, r15d
0x180048061  mov     [rsp+50h+dwOptions], r12d; dwOptions
0x180048066  lea     r15, aSystemSetup; "System\\Setup"
0x18004806d  xor     r8d, r8d; Reserved
0x180048070  mov     rdx, r15; lpSubKey
0x180048073  call    cs:__imp_RegCreateKeyExW
0x180048079  mov     esi, eax
0x18004807b  test    eax, eax
0x18004807d  jnz     short loc_1800480B0
0x18004807f  mov     rcx, [rbp+hKey]; hKey
0x180048083  lea     rax, [rbp+Data]
0x180048087  mov     [rsp+50h+samDesired], r13d; cbData
0x18004808c  lea     rdx, aOobeinprogress; "OOBEInProgress"
0x180048093  mov     r9d, r13d; dwType
0x180048096  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18004809b  xor     r8d, r8d; Reserved
0x18004809e  call    cs:__imp_RegSetValueExW
0x1800480a4  mov     rcx, [rbp+hKey]; hKey
0x1800480a8  mov     esi, eax
0x1800480aa  call    cs:__imp_RegCloseKey
0x1800480b0  mov     ecx, esi; dwErrCode
0x1800480b2  call    cs:__imp_SetLastError
0x1800480b8  test    esi, esi
0x1800480ba  mov     ebx, r12d
0x1800480bd  cmovz   ebx, r14d
0x1800480c1  test    ebx, ebx
0x1800480c3  jz      loc_180048159
0x1800480c9  test    rdi, rdi
0x1800480cc  jz      short loc_18004810C
0x1800480ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800480d2  inc     rax
0x1800480d5  cmp     [rdi+rax*2], r12w
0x1800480da  jnz     short loc_1800480D2
0x1800480dc  lea     eax, ds:2[rax*2]
0x1800480e3  mov     r9d, 1
0x1800480e9  mov     [rsp+50h+samDesired], eax
0x1800480ed  lea     r8, aCmdline; "CmdLine"
0x1800480f4  mov     rdx, r15
0x1800480f7  mov     qword ptr [rsp+50h+dwOptions], rdi
0x1800480fc  mov     rcx, 0FFFFFFFF80000002h
0x180048103  call    RegSetBinEx
0x180048108  mov     ebx, eax
0x18004810a  jmp     short loc_18004815E
0x18004810c  mov     rbx, 0FFFFFFFF80000002h
0x180048113  lea     r8, aCmdline; "CmdLine"
0x18004811a  mov     rcx, rbx
0x18004811d  mov     rdx, r15
0x180048120  call    RegExists
0x180048125  test    eax, eax
0x180048127  jz      short loc_180048176
0x180048129  lea     rax, Class
0x180048130  mov     [rsp+50h+samDesired], 2
0x180048138  mov     r9d, 1
0x18004813e  mov     qword ptr [rsp+50h+dwOptions], rax
0x180048143  lea     r8, aCmdline; "CmdLine"
0x18004814a  mov     rdx, r15
0x18004814d  mov     rcx, rbx
0x180048150  call    RegSetBinEx
0x180048155  mov     ebx, eax
0x180048157  jmp     short loc_180048172
0x180048159  test    rdi, rdi
0x18004815c  jz      short loc_18004817B
0x18004815e  call    cs:__imp_GetProcessHeap
0x180048164  mov     r8, rdi; lpMem
0x180048167  xor     edx, edx; dwFlags
0x180048169  mov     rcx, rax; hHeap
0x18004816c  call    cs:__imp_HeapFree
0x180048172  test    ebx, ebx
0x180048174  jz      short loc_18004817B
0x180048176  mov     eax, r12d
0x180048179  jmp     short loc_1800481A9
0x18004817b  call    cs:__imp_GetLastError
0x180048181  mov     ebx, 80070000h
0x180048186  test    eax, eax
0x180048188  jle     short loc_180048191
0x18004818a  movzx   eax, ax
0x18004818d  or      eax, ebx
0x18004818f  test    eax, eax
0x180048191  jns     short loc_1800481A4
0x180048193  call    cs:__imp_GetLastError
0x180048199  test    eax, eax
0x18004819b  jle     short loc_1800481A9
0x18004819d  movzx   eax, ax
0x1800481a0  or      eax, ebx
0x1800481a2  jmp     short loc_1800481A9
0x1800481a4  mov     eax, 80004005h
0x1800481a9  mov     rbx, [rsp+50h+arg_18]
0x1800481b1  add     rsp, 50h
0x1800481b5  pop     r15
0x1800481b7  pop     r14
0x1800481b9  pop     r13
0x1800481bb  pop     r12
0x1800481bd  pop     rdi
0x1800481be  pop     rsi
0x1800481bf  pop     rbp
0x1800481c0  retn
```

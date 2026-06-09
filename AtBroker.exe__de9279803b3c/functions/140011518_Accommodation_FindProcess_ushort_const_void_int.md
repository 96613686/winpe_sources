# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x140011518`
- end: `0x1400116bc`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `420`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d778`

## callees

- `0x140011518`
- `0x140015b00`
- `0x140015b90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140011670`
- `KERNEL32!CloseHandle` at `0x140011670`
- `KERNEL32!GetCurrentProcessId` at `0x140011598`
- `KERNEL32!GetCurrentProcessId` at `0x140011598`
- `KERNEL32!K32GetModuleBaseNameW` at `0x14001164f`
- `KERNEL32!K32GetModuleBaseNameW` at `0x14001164f`
- `KERNEL32!K32EnumProcessModules` at `0x140011630`
- `KERNEL32!K32EnumProcessModules` at `0x140011630`
- `KERNEL32!ProcessIdToSessionId` at `0x1400115b0`
- `KERNEL32!ProcessIdToSessionId` at `0x1400115d9`
- `KERNEL32!ProcessIdToSessionId` at `0x1400115b0`
- `KERNEL32!ProcessIdToSessionId` at `0x1400115d9`
- `KERNEL32!K32EnumProcesses` at `0x140011572`
- `KERNEL32!K32EnumProcesses` at `0x140011572`
- `KERNEL32!OpenProcess` at `0x140011606`
- `KERNEL32!OpenProcess` at `0x140011606`
- `msvcrt!_wcsicmp` at `0x140011663`
- `msvcrt!_wcsicmp` at `0x140011663`

## pseudocode

```c
__int64 __fastcall Accommodation::FindProcess(const unsigned __int16 *a1, void **a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // r15d
  DWORD v6; // esi
  __int64 v7; // rbx
  DWORD v8; // ecx
  DWORD v9; // r8d
  HANDLE v10; // rax
  void *v11; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pSessionId; // [rsp+24h] [rbp-DCh] BYREF
  DWORD v15; // [rsp+28h] [rbp-D8h] BYREF
  DWORD v16; // [rsp+2Ch] [rbp-D4h] BYREF
  HMODULE hModule; // [rsp+30h] [rbp-D0h] BYREF
  DWORD idProcess[2048]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR BaseName[264]; // [rsp+2040h] [rbp+1F40h] BYREF

  *a2 = 0;
  cbNeeded = 0;
  if ( !K32EnumProcesses(idProcess, 0x2000u, &cbNeeded) )
    return 0;
  cbNeeded >>= 2;
  if ( cbNeeded > 0x800 )
    cbNeeded = 2048;
  CurrentProcessId = GetCurrentProcessId();
  pSessionId = 0;
  v5 = CurrentProcessId;
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 0;
  v6 = 0;
  v7 = 0;
  if ( !cbNeeded )
    return v6;
  while ( 1 )
  {
    v8 = idProcess[v7];
    v15 = 0;
    if ( !ProcessIdToSessionId(v8, &v15) )
      goto LABEL_14;
    if ( v15 != pSessionId )
      goto LABEL_14;
    v9 = idProcess[v7];
    if ( v5 == v9 )
      goto LABEL_14;
    v10 = OpenProcess(0x410u, 0, v9);
    v11 = v10;
    if ( !v10 )
      goto LABEL_14;
    hModule = 0;
    v16 = 0;
    if ( K32EnumProcessModules(v10, &hModule, 8u, &v16) )
    {
      if ( K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u) && !_wcsicmp(BaseName, a1) )
        break;
    }
    CloseHandle(v11);
LABEL_14:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= cbNeeded )
      return v6;
  }
  v6 = idProcess[v7];
  *a2 = v11;
  return v6;
}

```

## disassembly

```asm
0x140011518  mov     [rsp-8+arg_10], rbx
0x14001151d  push    rbp
0x14001151e  push    rsi
0x14001151f  push    rdi
0x140011520  push    r12
0x140011522  push    r13
0x140011524  push    r14
0x140011526  push    r15
0x140011528  lea     rbp, [rsp-2160h]
0x140011530  mov     eax, 2260h
0x140011535  call    _alloca_probe
0x14001153a  sub     rsp, rax
0x14001153d  mov     rax, cs:__security_cookie
0x140011544  xor     rax, rsp
0x140011547  mov     [rbp+2190h+var_40], rax
0x14001154e  mov     r12, rdx
0x140011551  mov     qword ptr [rdx], 0
0x140011558  mov     r13, rcx
0x14001155b  mov     [rsp+2290h+cbNeeded], 0
0x140011563  mov     edx, 2000h; cb
0x140011568  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x14001156d  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x140011572  call    cs:__imp_K32EnumProcesses
0x140011578  test    eax, eax
0x14001157a  jz      loc_140011690
0x140011580  mov     eax, [rsp+2290h+cbNeeded]
0x140011584  mov     ecx, 800h
0x140011589  shr     eax, 2
0x14001158c  mov     [rsp+2290h+cbNeeded], eax
0x140011590  cmp     eax, ecx
0x140011592  jbe     short loc_140011598
0x140011594  mov     [rsp+2290h+cbNeeded], ecx
0x140011598  call    cs:__imp_GetCurrentProcessId
0x14001159e  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x1400115a3  mov     [rsp+2290h+pSessionId], 0
0x1400115ab  mov     ecx, eax; dwProcessId
0x1400115ad  mov     r15d, eax
0x1400115b0  call    cs:__imp_ProcessIdToSessionId
0x1400115b6  test    eax, eax
0x1400115b8  jz      loc_140011690
0x1400115be  xor     esi, esi
0x1400115c0  xor     ebx, ebx
0x1400115c2  cmp     [rsp+2290h+cbNeeded], ebx
0x1400115c6  jbe     loc_14001168C
0x1400115cc  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1400115d0  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x1400115d5  mov     [rsp+2290h+var_2268], esi
0x1400115d9  call    cs:__imp_ProcessIdToSessionId
0x1400115df  test    eax, eax
0x1400115e1  jz      loc_140011676
0x1400115e7  mov     eax, [rsp+2290h+pSessionId]
0x1400115eb  cmp     [rsp+2290h+var_2268], eax
0x1400115ef  jnz     loc_140011676
0x1400115f5  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1400115fa  cmp     r15d, r8d
0x1400115fd  jz      short loc_140011676
0x1400115ff  xor     edx, edx; bInheritHandle
0x140011601  mov     ecx, 410h; dwDesiredAccess
0x140011606  call    cs:__imp_OpenProcess
0x14001160c  mov     rdi, rax
0x14001160f  test    rax, rax
0x140011612  jz      short loc_140011676
0x140011614  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x140011619  mov     [rsp+2290h+hModule], rsi
0x14001161e  mov     r8d, 8; cb
0x140011624  mov     [rsp+2290h+var_2264], esi
0x140011628  lea     rdx, [rsp+2290h+hModule]; lphModule
0x14001162d  mov     rcx, rax; hProcess
0x140011630  call    cs:__imp_K32EnumProcessModules
0x140011636  test    eax, eax
0x140011638  jz      short loc_14001166D
0x14001163a  mov     rdx, [rsp+2290h+hModule]; hModule
0x14001163f  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x140011646  mov     r9d, 104h; nSize
0x14001164c  mov     rcx, rdi; hProcess
0x14001164f  call    cs:__imp_K32GetModuleBaseNameW
0x140011655  test    eax, eax
0x140011657  jz      short loc_14001166D
0x140011659  mov     rdx, r13; String2
0x14001165c  lea     rcx, [rbp+2190h+BaseName]; String1
0x140011663  call    cs:__imp__wcsicmp
0x140011669  test    eax, eax
0x14001166b  jz      short loc_140011684
0x14001166d  mov     rcx, rdi; hObject
0x140011670  call    cs:__imp_CloseHandle
0x140011676  inc     ebx
0x140011678  cmp     ebx, [rsp+2290h+cbNeeded]
0x14001167c  jb      loc_1400115CC
0x140011682  jmp     short loc_14001168C
0x140011684  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x140011688  mov     [r12], rdi
0x14001168c  mov     eax, esi
0x14001168e  jmp     short loc_140011692
0x140011690  xor     eax, eax
0x140011692  mov     rcx, [rbp+2190h+var_40]
0x140011699  xor     rcx, rsp; StackCookie
0x14001169c  call    __security_check_cookie
0x1400116a1  mov     rbx, [rsp+2290h+arg_10]
0x1400116a9  add     rsp, 2260h
0x1400116b0  pop     r15
0x1400116b2  pop     r14
0x1400116b4  pop     r13
0x1400116b6  pop     r12
0x1400116b8  pop     rdi
0x1400116b9  pop     rsi
0x1400116ba  pop     rbp
0x1400116bb  retn
```

# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x18023acfc`
- end: `0x18023aed4`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `472`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18023aedc`

## callees

- `0x18000c840`
- `0x18023acfc`
- `0x180271d80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18023ae75`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18023ae75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18023ad82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18023ad82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023ae88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023ae88`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18023ae06`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18023ae06`
- `KERNEL32!ProcessIdToSessionId` at `0x18023ada0`
- `KERNEL32!ProcessIdToSessionId` at `0x18023adcf`
- `KERNEL32!ProcessIdToSessionId` at `0x18023ada0`
- `KERNEL32!ProcessIdToSessionId` at `0x18023adcf`
- `KERNEL32!K32EnumProcesses` at `0x18023ad56`
- `KERNEL32!K32EnumProcesses` at `0x18023ad56`
- `KERNEL32!K32EnumProcessModules` at `0x18023ae36`
- `KERNEL32!K32EnumProcessModules` at `0x18023ae36`
- `KERNEL32!K32GetModuleBaseNameW` at `0x18023ae5b`
- `KERNEL32!K32GetModuleBaseNameW` at `0x18023ae5b`

## pseudocode

```c
__int64 __fastcall Accommodation::FindProcess(const unsigned __int16 *a1, void **a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // r15d
  DWORD v6; // esi
  __int64 i; // rbx
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
  for ( i = 0; (unsigned int)i < cbNeeded; i = (unsigned int)(i + 1) )
  {
    v8 = idProcess[i];
    v15 = 0;
    if ( ProcessIdToSessionId(v8, &v15) )
    {
      if ( v15 == pSessionId )
      {
        v9 = idProcess[i];
        if ( v5 != v9 )
        {
          v10 = OpenProcess(0x410u, 0, v9);
          v11 = v10;
          if ( v10 )
          {
            hModule = 0;
            v16 = 0;
            if ( K32EnumProcessModules(v10, &hModule, 8u, &v16)
              && K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u)
              && !(unsigned int)_o__wcsicmp(BaseName, a1) )
            {
              v6 = idProcess[i];
              *a2 = v11;
              return v6;
            }
            CloseHandle(v11);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18023acfc  mov     [rsp-8+arg_10], rbx
0x18023ad01  push    rbp
0x18023ad02  push    rsi
0x18023ad03  push    rdi
0x18023ad04  push    r12
0x18023ad06  push    r13
0x18023ad08  push    r14
0x18023ad0a  push    r15
0x18023ad0c  lea     rbp, [rsp-2160h]
0x18023ad14  mov     eax, 2260h
0x18023ad19  call    _alloca_probe
0x18023ad1e  sub     rsp, rax
0x18023ad21  mov     rax, cs:__security_cookie
0x18023ad28  xor     rax, rsp
0x18023ad2b  mov     [rbp+2190h+var_40], rax
0x18023ad32  mov     r12, rdx
0x18023ad35  mov     qword ptr [rdx], 0
0x18023ad3c  mov     r13, rcx
0x18023ad3f  mov     [rsp+2290h+cbNeeded], 0
0x18023ad47  mov     edx, 2000h; cb
0x18023ad4c  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x18023ad51  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x18023ad56  call    cs:__imp_K32EnumProcesses
0x18023ad5d  nop     dword ptr [rax+rax+00h]
0x18023ad62  test    eax, eax
0x18023ad64  jz      loc_18023AEA7
0x18023ad6a  mov     eax, [rsp+2290h+cbNeeded]
0x18023ad6e  mov     ecx, 800h
0x18023ad73  shr     eax, 2
0x18023ad76  mov     [rsp+2290h+cbNeeded], eax
0x18023ad7a  cmp     eax, ecx
0x18023ad7c  jbe     short loc_18023AD82
0x18023ad7e  mov     [rsp+2290h+cbNeeded], ecx
0x18023ad82  call    cs:__imp_GetCurrentProcessId
0x18023ad89  nop     dword ptr [rax+rax+00h]
0x18023ad8e  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x18023ad93  mov     [rsp+2290h+pSessionId], 0
0x18023ad9b  mov     ecx, eax; dwProcessId
0x18023ad9d  mov     r15d, eax
0x18023ada0  call    cs:__imp_ProcessIdToSessionId
0x18023ada7  nop     dword ptr [rax+rax+00h]
0x18023adac  test    eax, eax
0x18023adae  jz      loc_18023AEA7
0x18023adb4  xor     esi, esi
0x18023adb6  xor     ebx, ebx
0x18023adb8  cmp     ebx, [rsp+2290h+cbNeeded]
0x18023adbc  jnb     loc_18023AEA3
0x18023adc2  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x18023adc6  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x18023adcb  mov     [rsp+2290h+var_2268], esi
0x18023adcf  call    cs:__imp_ProcessIdToSessionId
0x18023add6  nop     dword ptr [rax+rax+00h]
0x18023addb  test    eax, eax
0x18023addd  jz      loc_18023AE94
0x18023ade3  mov     eax, [rsp+2290h+pSessionId]
0x18023ade7  cmp     [rsp+2290h+var_2268], eax
0x18023adeb  jnz     loc_18023AE94
0x18023adf1  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x18023adf6  cmp     r15d, r8d
0x18023adf9  jz      loc_18023AE94
0x18023adff  xor     edx, edx; bInheritHandle
0x18023ae01  mov     ecx, 410h; dwDesiredAccess
0x18023ae06  call    cs:__imp_OpenProcess
0x18023ae0d  nop     dword ptr [rax+rax+00h]
0x18023ae12  mov     rdi, rax
0x18023ae15  test    rax, rax
0x18023ae18  jz      short loc_18023AE94
0x18023ae1a  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x18023ae1f  mov     [rsp+2290h+hModule], rsi
0x18023ae24  mov     r8d, 8; cb
0x18023ae2a  mov     [rsp+2290h+var_2264], esi
0x18023ae2e  lea     rdx, [rsp+2290h+hModule]; lphModule
0x18023ae33  mov     rcx, rax; hProcess
0x18023ae36  call    cs:__imp_K32EnumProcessModules
0x18023ae3d  nop     dword ptr [rax+rax+00h]
0x18023ae42  test    eax, eax
0x18023ae44  jz      short loc_18023AE85
0x18023ae46  mov     rdx, [rsp+2290h+hModule]; hModule
0x18023ae4b  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x18023ae52  mov     r9d, 104h; nSize
0x18023ae58  mov     rcx, rdi; hProcess
0x18023ae5b  call    cs:__imp_K32GetModuleBaseNameW
0x18023ae62  nop     dword ptr [rax+rax+00h]
0x18023ae67  test    eax, eax
0x18023ae69  jz      short loc_18023AE85
0x18023ae6b  mov     rdx, r13
0x18023ae6e  lea     rcx, [rbp+2190h+BaseName]
0x18023ae75  call    cs:__imp__o__wcsicmp
0x18023ae7c  nop     dword ptr [rax+rax+00h]
0x18023ae81  test    eax, eax
0x18023ae83  jz      short loc_18023AE9B
0x18023ae85  mov     rcx, rdi; hObject
0x18023ae88  call    cs:__imp_CloseHandle
0x18023ae8f  nop     dword ptr [rax+rax+00h]
0x18023ae94  inc     ebx
0x18023ae96  jmp     loc_18023ADB8
0x18023ae9b  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x18023ae9f  mov     [r12], rdi
0x18023aea3  mov     eax, esi
0x18023aea5  jmp     short loc_18023AEA9
0x18023aea7  xor     eax, eax
0x18023aea9  mov     rcx, [rbp+2190h+var_40]
0x18023aeb0  xor     rcx, rsp; StackCookie
0x18023aeb3  call    __security_check_cookie
0x18023aeb8  mov     rbx, [rsp+2290h+arg_10]
0x18023aec0  add     rsp, 2260h
0x18023aec7  pop     r15
0x18023aec9  pop     r14
0x18023aecb  pop     r13
0x18023aecd  pop     r12
0x18023aecf  pop     rdi
0x18023aed0  pop     rsi
0x18023aed1  pop     rbp
0x18023aed2  retn
```

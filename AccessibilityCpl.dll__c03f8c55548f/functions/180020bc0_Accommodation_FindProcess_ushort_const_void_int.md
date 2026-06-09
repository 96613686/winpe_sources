# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x180020bc0`
- end: `0x180020d5d`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `413`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020dfc`

## callees

- `0x180020bc0`
- `0x18002d220`
- `0x18002d2b0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180020d0b`
- `msvcrt!_wcsicmp` at `0x180020d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020c40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d18`
- `KERNEL32!K32EnumProcesses` at `0x180020c1a`
- `KERNEL32!K32EnumProcesses` at `0x180020c1a`
- `KERNEL32!ProcessIdToSessionId` at `0x180020c58`
- `KERNEL32!ProcessIdToSessionId` at `0x180020c81`
- `KERNEL32!ProcessIdToSessionId` at `0x180020c58`
- `KERNEL32!ProcessIdToSessionId` at `0x180020c81`
- `KERNEL32!OpenProcess` at `0x180020cae`
- `KERNEL32!OpenProcess` at `0x180020cae`
- `KERNEL32!K32EnumProcessModules` at `0x180020cd8`
- `KERNEL32!K32EnumProcessModules` at `0x180020cd8`
- `KERNEL32!K32GetModuleBaseNameW` at `0x180020cf7`
- `KERNEL32!K32GetModuleBaseNameW` at `0x180020cf7`

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
              && !_wcsicmp(BaseName, a1) )
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
0x180020bc0  mov     [rsp-8+arg_10], rbx
0x180020bc5  push    rbp
0x180020bc6  push    rsi
0x180020bc7  push    rdi
0x180020bc8  push    r12
0x180020bca  push    r13
0x180020bcc  push    r14
0x180020bce  push    r15
0x180020bd0  lea     rbp, [rsp-2160h]
0x180020bd8  mov     eax, 2260h
0x180020bdd  call    _alloca_probe
0x180020be2  sub     rsp, rax
0x180020be5  mov     rax, cs:__security_cookie
0x180020bec  xor     rax, rsp
0x180020bef  mov     [rbp+2190h+var_40], rax
0x180020bf6  mov     r12, rdx
0x180020bf9  mov     qword ptr [rdx], 0
0x180020c00  mov     r13, rcx
0x180020c03  mov     [rsp+2290h+cbNeeded], 0
0x180020c0b  mov     edx, 2000h; cb
0x180020c10  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x180020c15  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x180020c1a  call    cs:__imp_K32EnumProcesses
0x180020c20  test    eax, eax
0x180020c22  jz      loc_180020D31
0x180020c28  mov     eax, [rsp+2290h+cbNeeded]
0x180020c2c  mov     ecx, 800h
0x180020c31  shr     eax, 2
0x180020c34  mov     [rsp+2290h+cbNeeded], eax
0x180020c38  cmp     eax, ecx
0x180020c3a  jbe     short loc_180020C40
0x180020c3c  mov     [rsp+2290h+cbNeeded], ecx
0x180020c40  call    cs:__imp_GetCurrentProcessId
0x180020c46  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x180020c4b  mov     [rsp+2290h+pSessionId], 0
0x180020c53  mov     ecx, eax; dwProcessId
0x180020c55  mov     r15d, eax
0x180020c58  call    cs:__imp_ProcessIdToSessionId
0x180020c5e  test    eax, eax
0x180020c60  jz      loc_180020D31
0x180020c66  xor     esi, esi
0x180020c68  xor     ebx, ebx
0x180020c6a  cmp     ebx, [rsp+2290h+cbNeeded]
0x180020c6e  jnb     loc_180020D2D
0x180020c74  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x180020c78  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x180020c7d  mov     [rsp+2290h+var_2268], esi
0x180020c81  call    cs:__imp_ProcessIdToSessionId
0x180020c87  test    eax, eax
0x180020c89  jz      loc_180020D1E
0x180020c8f  mov     eax, [rsp+2290h+pSessionId]
0x180020c93  cmp     [rsp+2290h+var_2268], eax
0x180020c97  jnz     loc_180020D1E
0x180020c9d  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x180020ca2  cmp     r15d, r8d
0x180020ca5  jz      short loc_180020D1E
0x180020ca7  xor     edx, edx; bInheritHandle
0x180020ca9  mov     ecx, 410h; dwDesiredAccess
0x180020cae  call    cs:__imp_OpenProcess
0x180020cb4  mov     rdi, rax
0x180020cb7  test    rax, rax
0x180020cba  jz      short loc_180020D1E
0x180020cbc  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x180020cc1  mov     [rsp+2290h+hModule], rsi
0x180020cc6  mov     r8d, 8; cb
0x180020ccc  mov     [rsp+2290h+var_2264], esi
0x180020cd0  lea     rdx, [rsp+2290h+hModule]; lphModule
0x180020cd5  mov     rcx, rax; hProcess
0x180020cd8  call    cs:__imp_K32EnumProcessModules
0x180020cde  test    eax, eax
0x180020ce0  jz      short loc_180020D15
0x180020ce2  mov     rdx, [rsp+2290h+hModule]; hModule
0x180020ce7  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x180020cee  mov     r9d, 104h; nSize
0x180020cf4  mov     rcx, rdi; hProcess
0x180020cf7  call    cs:__imp_K32GetModuleBaseNameW
0x180020cfd  test    eax, eax
0x180020cff  jz      short loc_180020D15
0x180020d01  mov     rdx, r13; String2
0x180020d04  lea     rcx, [rbp+2190h+BaseName]; String1
0x180020d0b  call    cs:__imp__wcsicmp
0x180020d11  test    eax, eax
0x180020d13  jz      short loc_180020D25
0x180020d15  mov     rcx, rdi; hObject
0x180020d18  call    cs:__imp_CloseHandle
0x180020d1e  inc     ebx
0x180020d20  jmp     loc_180020C6A
0x180020d25  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x180020d29  mov     [r12], rdi
0x180020d2d  mov     eax, esi
0x180020d2f  jmp     short loc_180020D33
0x180020d31  xor     eax, eax
0x180020d33  mov     rcx, [rbp+2190h+var_40]
0x180020d3a  xor     rcx, rsp; StackCookie
0x180020d3d  call    __security_check_cookie
0x180020d42  mov     rbx, [rsp+2290h+arg_10]
0x180020d4a  add     rsp, 2260h
0x180020d51  pop     r15
0x180020d53  pop     r14
0x180020d55  pop     r13
0x180020d57  pop     r12
0x180020d59  pop     rdi
0x180020d5a  pop     rsi
0x180020d5b  pop     rbp
0x180020d5c  retn
```

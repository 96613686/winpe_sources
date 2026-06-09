# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x1803990ec`
- end: `0x1803992cb`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `479`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1803992d4`

## callees

- `0x180142e10`
- `0x1803990ec`
- `0x1803ad690`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180399265`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180399265`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180399190`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1803991bf`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180399190`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1803991bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180399172`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180399172`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180399278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180399278`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803991f6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803991f6`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x180399226`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x180399226`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180399146`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180399146`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18039924b`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18039924b`

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
      if ( K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u) && !(unsigned int)_o__wcsicmp(BaseName, a1) )
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
0x1803990ec  mov     [rsp-8+arg_10], rbx
0x1803990f1  push    rbp
0x1803990f2  push    rsi
0x1803990f3  push    rdi
0x1803990f4  push    r12
0x1803990f6  push    r13
0x1803990f8  push    r14
0x1803990fa  push    r15
0x1803990fc  lea     rbp, [rsp-2160h]
0x180399104  mov     eax, 2260h
0x180399109  call    _alloca_probe
0x18039910e  sub     rsp, rax
0x180399111  mov     rax, cs:__security_cookie
0x180399118  xor     rax, rsp
0x18039911b  mov     [rbp+2190h+var_40], rax
0x180399122  mov     r12, rdx
0x180399125  mov     qword ptr [rdx], 0
0x18039912c  mov     r13, rcx
0x18039912f  mov     [rsp+2290h+cbNeeded], 0
0x180399137  mov     edx, 2000h; cb
0x18039913c  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x180399141  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x180399146  call    cs:__imp_K32EnumProcesses
0x18039914d  nop     dword ptr [rax+rax+00h]
0x180399152  test    eax, eax
0x180399154  jz      loc_18039929E
0x18039915a  mov     eax, [rsp+2290h+cbNeeded]
0x18039915e  mov     ecx, 800h
0x180399163  shr     eax, 2
0x180399166  mov     [rsp+2290h+cbNeeded], eax
0x18039916a  cmp     eax, ecx
0x18039916c  jbe     short loc_180399172
0x18039916e  mov     [rsp+2290h+cbNeeded], ecx
0x180399172  call    cs:__imp_GetCurrentProcessId
0x180399179  nop     dword ptr [rax+rax+00h]
0x18039917e  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x180399183  mov     [rsp+2290h+pSessionId], 0
0x18039918b  mov     ecx, eax; dwProcessId
0x18039918d  mov     r15d, eax
0x180399190  call    cs:__imp_ProcessIdToSessionId
0x180399197  nop     dword ptr [rax+rax+00h]
0x18039919c  test    eax, eax
0x18039919e  jz      loc_18039929E
0x1803991a4  xor     esi, esi
0x1803991a6  xor     ebx, ebx
0x1803991a8  cmp     [rsp+2290h+cbNeeded], ebx
0x1803991ac  jbe     loc_18039929A
0x1803991b2  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1803991b6  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x1803991bb  mov     [rsp+2290h+var_2268], esi
0x1803991bf  call    cs:__imp_ProcessIdToSessionId
0x1803991c6  nop     dword ptr [rax+rax+00h]
0x1803991cb  test    eax, eax
0x1803991cd  jz      loc_180399284
0x1803991d3  mov     eax, [rsp+2290h+pSessionId]
0x1803991d7  cmp     [rsp+2290h+var_2268], eax
0x1803991db  jnz     loc_180399284
0x1803991e1  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1803991e6  cmp     r15d, r8d
0x1803991e9  jz      loc_180399284
0x1803991ef  xor     edx, edx; bInheritHandle
0x1803991f1  mov     ecx, 410h; dwDesiredAccess
0x1803991f6  call    cs:__imp_OpenProcess
0x1803991fd  nop     dword ptr [rax+rax+00h]
0x180399202  mov     rdi, rax
0x180399205  test    rax, rax
0x180399208  jz      short loc_180399284
0x18039920a  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x18039920f  mov     [rsp+2290h+hModule], rsi
0x180399214  mov     r8d, 8; cb
0x18039921a  mov     [rsp+2290h+var_2264], esi
0x18039921e  lea     rdx, [rsp+2290h+hModule]; lphModule
0x180399223  mov     rcx, rax; hProcess
0x180399226  call    cs:__imp_K32EnumProcessModules
0x18039922d  nop     dword ptr [rax+rax+00h]
0x180399232  test    eax, eax
0x180399234  jz      short loc_180399275
0x180399236  mov     rdx, [rsp+2290h+hModule]; hModule
0x18039923b  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x180399242  mov     r9d, 104h; nSize
0x180399248  mov     rcx, rdi; hProcess
0x18039924b  call    cs:__imp_K32GetModuleBaseNameW
0x180399252  nop     dword ptr [rax+rax+00h]
0x180399257  test    eax, eax
0x180399259  jz      short loc_180399275
0x18039925b  mov     rdx, r13
0x18039925e  lea     rcx, [rbp+2190h+BaseName]
0x180399265  call    cs:__imp__o__wcsicmp
0x18039926c  nop     dword ptr [rax+rax+00h]
0x180399271  test    eax, eax
0x180399273  jz      short loc_180399292
0x180399275  mov     rcx, rdi; hObject
0x180399278  call    cs:__imp_CloseHandle
0x18039927f  nop     dword ptr [rax+rax+00h]
0x180399284  inc     ebx
0x180399286  cmp     ebx, [rsp+2290h+cbNeeded]
0x18039928a  jb      loc_1803991B2
0x180399290  jmp     short loc_18039929A
0x180399292  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x180399296  mov     [r12], rdi
0x18039929a  mov     eax, esi
0x18039929c  jmp     short loc_1803992A0
0x18039929e  xor     eax, eax
0x1803992a0  mov     rcx, [rbp+2190h+var_40]
0x1803992a7  xor     rcx, rsp; StackCookie
0x1803992aa  call    __security_check_cookie
0x1803992af  mov     rbx, [rsp+2290h+arg_10]
0x1803992b7  add     rsp, 2260h
0x1803992be  pop     r15
0x1803992c0  pop     r14
0x1803992c2  pop     r13
0x1803992c4  pop     r12
0x1803992c6  pop     rdi
0x1803992c7  pop     rsi
0x1803992c8  pop     rbp
0x1803992c9  retn
```

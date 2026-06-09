# GetDynamicResourcePath(wchar_t * *,int *,int *)

- ea: `0x180255ff4`
- end: `0x180256153`
- name: `?GetDynamicResourcePath@@YAJPEAPEA_WPEAH1@Z`
- size: `351`
- prototype: `__int64 __fastcall(PWSTR *ppszPath, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fa610`

## callees

- `0x1800fa740`
- `0x180255ff4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18025607c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18025607c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802560eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180256113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802560eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180256113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180256019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180256019`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180256059`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180256059`
- `SHLWAPI!StrStrIW` at `0x1802560a1`
- `SHLWAPI!StrStrIW` at `0x1802560bc`
- `SHLWAPI!StrStrIW` at `0x1802560d7`
- `SHLWAPI!StrStrIW` at `0x1802560a1`
- `SHLWAPI!StrStrIW` at `0x1802560bc`
- `SHLWAPI!StrStrIW` at `0x1802560d7`
- `SHELL32!SHGetKnownFolderPath` at `0x180256138`
- `SHELL32!SHGetKnownFolderPath` at `0x180256138`

## pseudocode

```c
__int64 __fastcall GetDynamicResourcePath(PWSTR *ppszPath, int *a2, int *a3)
{
  WCHAR *v6; // rax
  unsigned int v7; // edi
  unsigned __int64 retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  *a3 = 0;
  v6 = (WCHAR *)CoTaskMemAlloc(0x208u);
  *ppszPath = v6;
  if ( v6 )
  {
    if ( ExpandEnvironmentStringsW(L"%localappdata%\\Microsoft", v6, 0x104u) - 1 <= 0x103
      && (unsigned int)_o__wcsicmp(L"%localappdata%\\Microsoft", *ppszPath) )
    {
      v7 = 0;
      if ( *ppszPath
        && (StrStrIW(*ppszPath, L"\\WPNETWORK")
         || StrStrIW(*ppszPath, L"\\SYSTEM\\")
         || StrStrIW(*ppszPath, L"\\DefApps\\")) )
      {
        CoTaskMemFree(*ppszPath);
        *ppszPath = 0;
        *a3 = 1;
      }
      else if ( *ppszPath )
      {
        *a2 = 1;
        return v7;
      }
    }
    else
    {
      CoTaskMemFree(*ppszPath);
      *ppszPath = 0;
    }
    return (unsigned int)SHGetKnownFolderPath(&FOLDERID_SharedData, 0x8000u, 0, ppszPath);
  }
  v7 = -2147467261;
  FailFastWithHR(-2147467261, retaddr, 0x222u);
  return v7;
}

```

## disassembly

```asm
0x180255ff4  push    rbx
0x180255ff6  push    rsi
0x180255ff7  push    rdi
0x180255ff8  push    r14
0x180255ffa  sub     rsp, 28h
0x180255ffe  mov     rbx, rcx
0x180256001  mov     dword ptr [rdx], 0
0x180256007  mov     ecx, 208h; cb
0x18025600c  mov     dword ptr [r8], 0
0x180256013  mov     r14, r8
0x180256016  mov     rsi, rdx
0x180256019  call    cs:__imp_CoTaskMemAlloc
0x180256020  nop     dword ptr [rax+rax+00h]
0x180256025  mov     [rbx], rax
0x180256028  test    rax, rax
0x18025602b  jnz     short loc_180256049
0x18025602d  mov     rdx, [rsp+48h]; unsigned __int64
0x180256032  mov     edi, 80004003h
0x180256037  mov     ecx, edi; int
0x180256039  mov     r8d, 222h; unsigned __int64
0x18025603f  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x180256044  jmp     loc_180256146
0x180256049  mov     r8d, 104h; nSize
0x18025604f  lea     rcx, aLocalappdataMi; "%localappdata%\\Microsoft"
0x180256056  mov     rdx, rax; lpDst
0x180256059  call    cs:__imp_ExpandEnvironmentStringsW
0x180256060  nop     dword ptr [rax+rax+00h]
0x180256065  dec     eax
0x180256067  cmp     eax, 103h
0x18025606c  ja      loc_180256110
0x180256072  mov     rdx, [rbx]
0x180256075  lea     rcx, aLocalappdataMi; "%localappdata%\\Microsoft"
0x18025607c  call    cs:__imp__o__wcsicmp
0x180256083  nop     dword ptr [rax+rax+00h]
0x180256088  test    eax, eax
0x18025608a  jz      loc_180256110
0x180256090  mov     rcx, [rbx]; pszFirst
0x180256093  xor     edi, edi
0x180256095  test    rcx, rcx
0x180256098  jz      short loc_180256103
0x18025609a  lea     rdx, pszSrch; "\\WPNETWORK"
0x1802560a1  call    cs:__imp_StrStrIW
0x1802560a8  nop     dword ptr [rax+rax+00h]
0x1802560ad  test    rax, rax
0x1802560b0  jnz     short loc_1802560E8
0x1802560b2  mov     rcx, [rbx]; pszFirst
0x1802560b5  lea     rdx, aSystem_1; "\\SYSTEM\\"
0x1802560bc  call    cs:__imp_StrStrIW
0x1802560c3  nop     dword ptr [rax+rax+00h]
0x1802560c8  test    rax, rax
0x1802560cb  jnz     short loc_1802560E8
0x1802560cd  mov     rcx, [rbx]; pszFirst
0x1802560d0  lea     rdx, aDefapps; "\\DefApps\\"
0x1802560d7  call    cs:__imp_StrStrIW
0x1802560de  nop     dword ptr [rax+rax+00h]
0x1802560e3  test    rax, rax
0x1802560e6  jz      short loc_180256103
0x1802560e8  mov     rcx, [rbx]; pv
0x1802560eb  call    cs:__imp_CoTaskMemFree
0x1802560f2  nop     dword ptr [rax+rax+00h]
0x1802560f7  mov     [rbx], rdi
0x1802560fa  mov     dword ptr [r14], 1
0x180256101  jmp     short loc_180256126
0x180256103  cmp     [rbx], rdi
0x180256106  jz      short loc_180256126
0x180256108  mov     dword ptr [rsi], 1
0x18025610e  jmp     short loc_180256146
0x180256110  mov     rcx, [rbx]; pv
0x180256113  call    cs:__imp_CoTaskMemFree
0x18025611a  nop     dword ptr [rax+rax+00h]
0x18025611f  mov     qword ptr [rbx], 0
0x180256126  mov     r9, rbx; ppszPath
0x180256129  lea     rcx, ?FOLDERID_SharedData@@3U_GUID@@B; rfid
0x180256130  xor     r8d, r8d; hToken
0x180256133  mov     edx, 8000h; dwFlags
0x180256138  call    cs:__imp_SHGetKnownFolderPath
0x18025613f  nop     dword ptr [rax+rax+00h]
0x180256144  mov     edi, eax
0x180256146  mov     eax, edi
0x180256148  add     rsp, 28h
0x18025614c  pop     r14
0x18025614e  pop     rdi
0x18025614f  pop     rsi
0x180256150  pop     rbx
0x180256151  retn
```

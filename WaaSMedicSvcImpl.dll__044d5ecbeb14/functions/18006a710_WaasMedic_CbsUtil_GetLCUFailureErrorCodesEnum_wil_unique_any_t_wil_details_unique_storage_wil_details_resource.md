# WaasMedic::CbsUtil::GetLCUFailureErrorCodesEnum(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18006a710`
- end: `0x18006a93c`
- name: `?GetLCUFailureErrorCodesEnum@CbsUtil@WaasMedic@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@@Z`
- size: `556`
- prototype: `__int64 __fastcall(int, LPDWORD lpcbMaxValueNameLen)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006ab9c`

## callees

- `0x18000bbd4`
- `0x180028f10`
- `0x18002e81c`
- `0x180037654`
- `0x18006a710`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a73c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a8bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a8ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a73c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a8bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a8ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a74a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a8cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a8fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a74a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a8cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a8fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a8b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a8b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a752`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a77a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a8d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a752`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a77a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a8d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006a84c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006a84c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a7a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a7a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a772`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a772`

## string_xrefs

- `0x18006a795`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrors`
- `0x18006a915`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrors`

## pseudocode

```c
int __fastcall WaasMedic::CbsUtil::GetLCUFailureErrorCodesEnum(HKEY *a1, LPDWORD lpcbMaxValueNameLen, void **a3)
{
  void *v4; // rsi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  HKEY v9; // rsi
  DWORD v10; // ebx
  LSTATUS v11; // eax
  signed int v12; // ebx
  __int64 v13; // rdx
  HKEY v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rdx
  void *v18; // rsi
  void *v19; // rbp
  DWORD v20; // ebx
  HANDLE v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-88h]
  _QWORD v25[9]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  DWORD cValues; // [rsp+B0h] [rbp+8h] BYREF

  *lpcbMaxValueNameLen = 0;
  v4 = *a3;
  if ( *a3 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    SetLastError(LastError);
  }
  *a3 = 0;
  v9 = *a1;
  if ( *a1 )
  {
    v10 = GetLastError();
    RegCloseKey(v9);
    SetLastError(v10);
  }
  *a1 = 0;
  v11 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\LCUInstallErrors",
          0,
          1u,
          a1);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( (unsigned int)(v12 + 2147024894) <= 1 )
  {
    LogLevelW(
      4u,
      L"The key %s was not found, condition is not applicable.",
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\LCUInstallErrors");
  }
  else
  {
    if ( v12 < 0 )
    {
      v13 = 395;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
        (const char *)(unsigned int)v12,
        phkResult);
      return v12;
    }
    v15 = *a1;
    cValues = 0;
    v16 = RegQueryInfoKeyW(v15, 0, 0, 0, 0, 0, 0, &cValues, lpcbMaxValueNameLen, 0, 0, 0);
    if ( v16 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x199,
               (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
               (const char *)v16,
               phkResult);
    LogLevelW(4u, L"Found %d LCU error entries.", cValues);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v25,
      v17,
      ++*lpcbMaxValueNameLen);
    if ( a3 == v25 )
    {
      v22 = (void *)v25[0];
    }
    else
    {
      v18 = *a3;
      v19 = (void *)v25[0];
      if ( *a3 )
      {
        v20 = GetLastError();
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v18);
        SetLastError(v20);
      }
      *a3 = v19;
      v22 = 0;
    }
    if ( v22 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
    }
    if ( !*a3 )
    {
      v12 = -2147024882;
      v13 = 415;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006a710  push    rbx
0x18006a712  push    rbp
0x18006a713  push    rsi
0x18006a714  push    rdi
0x18006a715  push    r14
0x18006a717  push    r15
0x18006a719  sub     rsp, 78h
0x18006a71d  mov     dword ptr [rdx], 0
0x18006a723  mov     rdi, r8
0x18006a726  mov     rsi, [r8]
0x18006a729  mov     r15, rdx
0x18006a72c  mov     r14, rcx
0x18006a72f  test    rsi, rsi
0x18006a732  jz      short loc_18006A758
0x18006a734  call    cs:__imp_GetLastError
0x18006a73a  mov     ebx, eax
0x18006a73c  call    cs:__imp_GetProcessHeap
0x18006a742  mov     r8, rsi; lpMem
0x18006a745  xor     edx, edx; dwFlags
0x18006a747  mov     rcx, rax; hHeap
0x18006a74a  call    cs:__imp_HeapFree
0x18006a750  mov     ecx, ebx; dwErrCode
0x18006a752  call    cs:__imp_SetLastError
0x18006a758  mov     qword ptr [rdi], 0
0x18006a75f  mov     rsi, [r14]
0x18006a762  test    rsi, rsi
0x18006a765  jz      short loc_18006A780
0x18006a767  call    cs:__imp_GetLastError
0x18006a76d  mov     rcx, rsi; hKey
0x18006a770  mov     ebx, eax
0x18006a772  call    cs:__imp_RegCloseKey
0x18006a778  mov     ecx, ebx; dwErrCode
0x18006a77a  call    cs:__imp_SetLastError
0x18006a780  mov     r9d, 1; samDesired
0x18006a786  mov     qword ptr [r14], 0
0x18006a78d  xor     r8d, r8d; ulOptions
0x18006a790  mov     [rsp+0A8h+phkResult], r14; int
0x18006a795  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006a79c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006a7a3  call    cs:__imp_RegOpenKeyExW
0x18006a7a9  mov     ebx, eax
0x18006a7ab  test    eax, eax
0x18006a7ad  jle     short loc_18006A7B8
0x18006a7af  movzx   ebx, ax
0x18006a7b2  or      ebx, 80070000h
0x18006a7b8  lea     ecx, [rbx+7FF8FFFEh]
0x18006a7be  cmp     ecx, 1
0x18006a7c1  jbe     loc_18006A915
0x18006a7c7  test    ebx, ebx
0x18006a7c9  jns     short loc_18006A7EE
0x18006a7cb  mov     edx, 18Bh; void *
0x18006a7d0  mov     rcx, [rsp+0A8h]; this
0x18006a7d8  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a7df  mov     r9d, ebx; char *
0x18006a7e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a7e7  mov     eax, ebx
0x18006a7e9  jmp     loc_18006A92F
0x18006a7ee  mov     rcx, [r14]; hKey
0x18006a7f1  lea     rax, [rsp+0A8h+cValues]
0x18006a7f9  mov     [rsp+0A8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18006a802  xor     r9d, r9d; lpReserved
0x18006a805  mov     [rsp+0A8h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18006a80e  xor     r8d, r8d; lpcchClass
0x18006a811  mov     [rsp+0A8h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18006a81a  xor     edx, edx; lpClass
0x18006a81c  mov     [rsp+0A8h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18006a821  mov     [rsp+0A8h+lpcValues], rax; lpcValues
0x18006a826  mov     [rsp+0A8h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18006a82f  mov     [rsp+0A8h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18006a838  mov     [rsp+0A8h+phkResult], 0; unsigned int
0x18006a841  mov     [rsp+0A8h+cValues], 0
0x18006a84c  call    cs:__imp_RegQueryInfoKeyW
0x18006a852  test    eax, eax
0x18006a854  jz      short loc_18006A877
0x18006a856  mov     rcx, [rsp+0A8h]; this
0x18006a85e  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a865  mov     r9d, eax; char *
0x18006a868  mov     edx, 199h; void *
0x18006a86d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006a872  jmp     loc_18006A92F
0x18006a877  mov     r8d, [rsp+0A8h+cValues]
0x18006a87f  lea     rdx, aFoundDLcuError; "Found %d LCU error entries."
0x18006a886  mov     ecx, 4; unsigned __int8
0x18006a88b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006a890  inc     dword ptr [r15]
0x18006a893  lea     rcx, [rsp+0A8h+var_48]
0x18006a898  mov     r8d, [r15]
0x18006a89b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18006a8a0  lea     rax, [rsp+0A8h+var_48]
0x18006a8a5  cmp     rdi, rax
0x18006a8a8  jz      short loc_18006A8E2
0x18006a8aa  mov     rsi, [rdi]
0x18006a8ad  mov     rbp, [rsp+0A8h+var_48]
0x18006a8b2  test    rsi, rsi
0x18006a8b5  jz      short loc_18006A8DB
0x18006a8b7  call    cs:__imp_GetLastError
0x18006a8bd  mov     ebx, eax
0x18006a8bf  call    cs:__imp_GetProcessHeap
0x18006a8c5  mov     r8, rsi; lpMem
0x18006a8c8  xor     edx, edx; dwFlags
0x18006a8ca  mov     rcx, rax; hHeap
0x18006a8cd  call    cs:__imp_HeapFree
0x18006a8d3  mov     ecx, ebx; dwErrCode
0x18006a8d5  call    cs:__imp_SetLastError
0x18006a8db  mov     [rdi], rbp
0x18006a8de  xor     ebx, ebx
0x18006a8e0  jmp     short loc_18006A8E7
0x18006a8e2  mov     rbx, [rsp+0A8h+var_48]
0x18006a8e7  test    rbx, rbx
0x18006a8ea  jz      short loc_18006A900
0x18006a8ec  call    cs:__imp_GetProcessHeap
0x18006a8f2  mov     r8, rbx; lpMem
0x18006a8f5  xor     edx, edx; dwFlags
0x18006a8f7  mov     rcx, rax; hHeap
0x18006a8fa  call    cs:__imp_HeapFree
0x18006a900  cmp     qword ptr [rdi], 0
0x18006a904  jnz     short loc_18006A92D
0x18006a906  mov     ebx, 8007000Eh
0x18006a90b  mov     edx, 19Fh
0x18006a910  jmp     loc_18006A7D0
0x18006a915  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006a91c  mov     ecx, 4; unsigned __int8
0x18006a921  lea     rdx, aTheKeySWasNotF; "The key %s was not found, condition is "...
0x18006a928  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006a92d  xor     eax, eax
0x18006a92f  add     rsp, 78h
0x18006a933  pop     r15
0x18006a935  pop     r14
0x18006a937  pop     rdi
0x18006a938  pop     rsi
0x18006a939  pop     rbp
0x18006a93a  pop     rbx
0x18006a93b  retn
```

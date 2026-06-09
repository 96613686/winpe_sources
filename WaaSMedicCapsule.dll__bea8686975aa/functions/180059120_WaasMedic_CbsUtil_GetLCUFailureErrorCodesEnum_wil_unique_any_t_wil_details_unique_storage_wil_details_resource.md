# WaasMedic::CbsUtil::GetLCUFailureErrorCodesEnum(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180059120`
- end: `0x18005934c`
- name: `?GetLCUFailureErrorCodesEnum@CbsUtil@WaasMedic@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@@Z`
- size: `556`
- prototype: `__int64 __fastcall(int, LPDWORD lpcbMaxValueNameLen)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800595ac`
- `0x180059794`

## callees

- `0x180009a54`
- `0x18002543c`
- `0x18002c284`
- `0x180033290`
- `0x180059120`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005915a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800592dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005930a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005915a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800592dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005930a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800592cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800592fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800592cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800592fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800592c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800592c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059162`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005918a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800592e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059162`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005918a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800592e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005925c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005925c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800591b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800591b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059182`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059182`

## string_xrefs

- `0x1800591a5`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrors`
- `0x180059325`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrors`

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
0x180059120  push    rbx
0x180059122  push    rbp
0x180059123  push    rsi
0x180059124  push    rdi
0x180059125  push    r14
0x180059127  push    r15
0x180059129  sub     rsp, 78h
0x18005912d  mov     dword ptr [rdx], 0
0x180059133  mov     rdi, r8
0x180059136  mov     rsi, [r8]
0x180059139  mov     r15, rdx
0x18005913c  mov     r14, rcx
0x18005913f  test    rsi, rsi
0x180059142  jz      short loc_180059168
0x180059144  call    cs:__imp_GetLastError
0x18005914a  mov     ebx, eax
0x18005914c  call    cs:__imp_GetProcessHeap
0x180059152  mov     r8, rsi; lpMem
0x180059155  xor     edx, edx; dwFlags
0x180059157  mov     rcx, rax; hHeap
0x18005915a  call    cs:__imp_HeapFree
0x180059160  mov     ecx, ebx; dwErrCode
0x180059162  call    cs:__imp_SetLastError
0x180059168  mov     qword ptr [rdi], 0
0x18005916f  mov     rsi, [r14]
0x180059172  test    rsi, rsi
0x180059175  jz      short loc_180059190
0x180059177  call    cs:__imp_GetLastError
0x18005917d  mov     rcx, rsi; hKey
0x180059180  mov     ebx, eax
0x180059182  call    cs:__imp_RegCloseKey
0x180059188  mov     ecx, ebx; dwErrCode
0x18005918a  call    cs:__imp_SetLastError
0x180059190  mov     r9d, 1; samDesired
0x180059196  mov     qword ptr [r14], 0
0x18005919d  xor     r8d, r8d; ulOptions
0x1800591a0  mov     [rsp+0A8h+phkResult], r14; int
0x1800591a5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800591ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800591b3  call    cs:__imp_RegOpenKeyExW
0x1800591b9  mov     ebx, eax
0x1800591bb  test    eax, eax
0x1800591bd  jle     short loc_1800591C8
0x1800591bf  movzx   ebx, ax
0x1800591c2  or      ebx, 80070000h
0x1800591c8  lea     ecx, [rbx+7FF8FFFEh]
0x1800591ce  cmp     ecx, 1
0x1800591d1  jbe     loc_180059325
0x1800591d7  test    ebx, ebx
0x1800591d9  jns     short loc_1800591FE
0x1800591db  mov     edx, 18Bh; void *
0x1800591e0  mov     rcx, [rsp+0A8h]; this
0x1800591e8  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800591ef  mov     r9d, ebx; char *
0x1800591f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800591f7  mov     eax, ebx
0x1800591f9  jmp     loc_18005933F
0x1800591fe  mov     rcx, [r14]; hKey
0x180059201  lea     rax, [rsp+0A8h+cValues]
0x180059209  mov     [rsp+0A8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180059212  xor     r9d, r9d; lpReserved
0x180059215  mov     [rsp+0A8h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18005921e  xor     r8d, r8d; lpcchClass
0x180059221  mov     [rsp+0A8h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18005922a  xor     edx, edx; lpClass
0x18005922c  mov     [rsp+0A8h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180059231  mov     [rsp+0A8h+lpcValues], rax; lpcValues
0x180059236  mov     [rsp+0A8h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18005923f  mov     [rsp+0A8h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180059248  mov     [rsp+0A8h+phkResult], 0; unsigned int
0x180059251  mov     [rsp+0A8h+cValues], 0
0x18005925c  call    cs:__imp_RegQueryInfoKeyW
0x180059262  test    eax, eax
0x180059264  jz      short loc_180059287
0x180059266  mov     rcx, [rsp+0A8h]; this
0x18005926e  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180059275  mov     r9d, eax; char *
0x180059278  mov     edx, 199h; void *
0x18005927d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180059282  jmp     loc_18005933F
0x180059287  mov     r8d, [rsp+0A8h+cValues]
0x18005928f  lea     rdx, aFoundDLcuError; "Found %d LCU error entries."
0x180059296  mov     ecx, 4; unsigned __int8
0x18005929b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800592a0  inc     dword ptr [r15]
0x1800592a3  lea     rcx, [rsp+0A8h+var_48]
0x1800592a8  mov     r8d, [r15]
0x1800592ab  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800592b0  lea     rax, [rsp+0A8h+var_48]
0x1800592b5  cmp     rdi, rax
0x1800592b8  jz      short loc_1800592F2
0x1800592ba  mov     rsi, [rdi]
0x1800592bd  mov     rbp, [rsp+0A8h+var_48]
0x1800592c2  test    rsi, rsi
0x1800592c5  jz      short loc_1800592EB
0x1800592c7  call    cs:__imp_GetLastError
0x1800592cd  mov     ebx, eax
0x1800592cf  call    cs:__imp_GetProcessHeap
0x1800592d5  mov     r8, rsi; lpMem
0x1800592d8  xor     edx, edx; dwFlags
0x1800592da  mov     rcx, rax; hHeap
0x1800592dd  call    cs:__imp_HeapFree
0x1800592e3  mov     ecx, ebx; dwErrCode
0x1800592e5  call    cs:__imp_SetLastError
0x1800592eb  mov     [rdi], rbp
0x1800592ee  xor     ebx, ebx
0x1800592f0  jmp     short loc_1800592F7
0x1800592f2  mov     rbx, [rsp+0A8h+var_48]
0x1800592f7  test    rbx, rbx
0x1800592fa  jz      short loc_180059310
0x1800592fc  call    cs:__imp_GetProcessHeap
0x180059302  mov     r8, rbx; lpMem
0x180059305  xor     edx, edx; dwFlags
0x180059307  mov     rcx, rax; hHeap
0x18005930a  call    cs:__imp_HeapFree
0x180059310  cmp     qword ptr [rdi], 0
0x180059314  jnz     short loc_18005933D
0x180059316  mov     ebx, 8007000Eh
0x18005931b  mov     edx, 19Fh
0x180059320  jmp     loc_1800591E0
0x180059325  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005932c  mov     ecx, 4; unsigned __int8
0x180059331  lea     rdx, aTheKeySWasNotF; "The key %s was not found, condition is "...
0x180059338  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005933d  xor     eax, eax
0x18005933f  add     rsp, 78h
0x180059343  pop     r15
0x180059345  pop     r14
0x180059347  pop     rdi
0x180059348  pop     rsi
0x180059349  pop     rbp
0x18005934a  pop     rbx
0x18005934b  retn
```

# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x180028e60`
- end: `0x18002913c`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `732`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x1800288dc`

## callees

- `0x180028890`
- `0x180028e60`

## import_xrefs

- `msvcrt!free` at `0x180028ebe`
- `msvcrt!free` at `0x180029058`
- `msvcrt!free` at `0x1800290c5`
- `msvcrt!free` at `0x1800290fc`
- `msvcrt!free` at `0x180028ebe`
- `msvcrt!free` at `0x180029058`
- `msvcrt!free` at `0x1800290c5`
- `msvcrt!free` at `0x1800290fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002909d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002909d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028edf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028f6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ff5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002904f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028f6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ff5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002904f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029092`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029086`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029086`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f15`
- `KERNEL32!CreateEventW` at `0x180028ed1`
- `KERNEL32!CreateEventW` at `0x180028ed1`
- `ADVAPI32!RegEnumValueW` at `0x180028fae`
- `ADVAPI32!RegEnumValueW` at `0x180029036`
- `ADVAPI32!RegEnumValueW` at `0x180028fae`
- `ADVAPI32!RegEnumValueW` at `0x180029036`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180028f54`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180028f54`

## string_xrefs

- `0x18002907f`: `SymbolicLinkValue`

## pseudocode

```c
signed int __fastcall SettingsCopier::GetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        DWORD a3,
        WCHAR *a4,
        DWORD cchValueName,
        DWORD *a6,
        void **a7,
        DWORD *a8)
{
  DWORD *v8; // r12
  DWORD *v9; // r13
  void **v11; // rsi
  void *v14; // rcx
  HANDLE EventW; // r14
  signed int result; // eax
  LSTATUS v17; // ebx
  LSTATUS v18; // edi
  LSTATUS v19; // eax
  DWORD v20; // ebx
  BYTE *lpData; // [rsp+30h] [rbp-30h]
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  DWORD v23; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v24; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+58h] BYREF

  v8 = a6;
  v9 = a8;
  v11 = a7;
  *a4 = 0;
  *v8 = 0;
  *v9 = 0;
  v14 = *v11;
  hKeya = 0;
  cchValueName = 260;
  Type = 0;
  cbData = 0;
  v23 = 0;
  v24 = 0;
  free(v14);
  *v11 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v17 = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x20019u, &hKeya);
    if ( v17 )
    {
      CloseHandle(EventW);
      goto LABEL_6;
    }
    v18 = 1;
    v17 = RegNotifyChangeKeyValue(hKeya, 0, 5u, EventW, 1);
    if ( v17 )
      goto LABEL_10;
    cchValueName = 260;
    v19 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, 0, &cbData);
    v17 = v19;
    if ( v19 == 259 )
      goto LABEL_17;
    if ( v19 && v19 != 234 )
    {
LABEL_10:
      CloseHandle(EventW);
      RegCloseKey(hKeya);
      goto LABEL_6;
    }
    if ( cbData )
    {
      if ( !(unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(v11, cbData) )
      {
        v18 = -2147024882;
LABEL_17:
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        return v18;
      }
      lpData = (BYTE *)*v11;
      cchValueName = 260;
      v17 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, lpData, &cbData);
      if ( v17 )
      {
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        free(*v11);
        *v11 = 0;
LABEL_6:
        if ( v17 > 0 )
          return (unsigned __int16)v17 | 0x80070000;
        return v17;
      }
    }
    v18 = RegQueryValueExW(hKeya, L"SymbolicLinkValue", 0, &v23, 0, &v24);
    RegCloseKey(hKeya);
    v20 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v20 )
    {
      v17 = -2147023590;
LABEL_29:
      free(*v11);
      *v11 = 0;
      *a4 = 0;
      return v17;
    }
    if ( v18 )
    {
      if ( v18 != 2 )
      {
        free(*v11);
        *v11 = 0;
        *a4 = 0;
        if ( v18 > 0 )
          return (unsigned __int16)v18 | 0x80070000;
        return v18;
      }
    }
    else if ( v23 == 6 )
    {
      v17 = -2147023432;
      goto LABEL_29;
    }
    *v8 = Type;
    *v9 = cbData;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180028e60  mov     [rsp-38h+arg_0], rbx
0x180028e65  mov     [rsp-38h+dwIndex], r8d
0x180028e6a  push    rbp
0x180028e6b  push    rsi
0x180028e6c  push    rdi
0x180028e6d  push    r12
0x180028e6f  push    r13
0x180028e71  push    r14
0x180028e73  push    r15
0x180028e75  mov     rbp, rsp
0x180028e78  sub     rsp, 60h
0x180028e7c  mov     r12, [rbp+arg_28]
0x180028e80  xor     r14d, r14d
0x180028e83  mov     r13, [rbp+arg_38]
0x180028e87  mov     rdi, rcx
0x180028e8a  mov     rsi, [rbp+arg_30]
0x180028e8e  mov     r15, r9
0x180028e91  mov     [r9], r14w
0x180028e95  mov     rbx, rdx
0x180028e98  mov     [r12], r14d
0x180028e9c  mov     [r13+0], r14d
0x180028ea0  mov     rcx, [rsi]; Block
0x180028ea3  mov     [rbp+hKey], r14
0x180028ea7  mov     [rbp+cchValueName], 104h
0x180028eae  mov     [rbp+Type], r14d
0x180028eb2  mov     [rbp+cbData], r14d
0x180028eb6  mov     [rbp+var_1C], r14d
0x180028eba  mov     [rbp+var_18], r14d
0x180028ebe  call    cs:__imp_free
0x180028ec4  xor     r9d, r9d; lpName
0x180028ec7  mov     [rsi], r14
0x180028eca  xor     r8d, r8d; bInitialState
0x180028ecd  xor     edx, edx; bManualReset
0x180028ecf  xor     ecx, ecx; lpEventAttributes
0x180028ed1  call    cs:__imp_CreateEventW
0x180028ed7  mov     r14, rax
0x180028eda  test    rax, rax
0x180028edd  jnz     short loc_180028EFA
0x180028edf  call    cs:__imp_GetLastError
0x180028ee5  test    eax, eax
0x180028ee7  jle     loc_180029124
0x180028eed  movzx   eax, ax
0x180028ef0  or      eax, 80070000h
0x180028ef5  jmp     loc_180029124
0x180028efa  lea     rax, [rbp+hKey]
0x180028efe  mov     r9d, 20019h; samDesired
0x180028f04  mov     r8d, 8; ulOptions
0x180028f0a  mov     [rsp+60h+phkResult], rax; phkResult
0x180028f0f  mov     rdx, rbx; lpSubKey
0x180028f12  mov     rcx, rdi; hKey
0x180028f15  call    cs:__imp_RegOpenKeyExW
0x180028f1b  mov     ebx, eax
0x180028f1d  test    eax, eax
0x180028f1f  jz      short loc_180028F3E
0x180028f21  mov     rcx, r14; hObject
0x180028f24  call    cs:__imp_CloseHandle
0x180028f2a  test    ebx, ebx
0x180028f2c  jle     short loc_180028F37
0x180028f2e  movzx   ebx, bx
0x180028f31  or      ebx, 80070000h
0x180028f37  mov     eax, ebx
0x180028f39  jmp     loc_180029124
0x180028f3e  mov     rcx, [rbp+hKey]; hKey
0x180028f42  mov     edi, 1
0x180028f47  mov     r9, r14; hEvent
0x180028f4a  mov     dword ptr [rsp+60h+phkResult], edi; fAsynchronous
0x180028f4e  xor     edx, edx; bWatchSubtree
0x180028f50  lea     r8d, [rdi+4]; dwNotifyFilter
0x180028f54  call    cs:__imp_RegNotifyChangeKeyValue
0x180028f5a  mov     ebx, eax
0x180028f5c  test    eax, eax
0x180028f5e  jz      short loc_180028F75
0x180028f60  mov     rcx, r14; hObject
0x180028f63  call    cs:__imp_CloseHandle
0x180028f69  mov     rcx, [rbp+hKey]; hKey
0x180028f6d  call    cs:__imp_RegCloseKey
0x180028f73  jmp     short loc_180028F2A
0x180028f75  mov     edx, [rbp+dwIndex]; dwIndex
0x180028f78  lea     rax, [rbp+cbData]
0x180028f7c  mov     rcx, [rbp+hKey]; hKey
0x180028f80  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180028f84  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180028f89  mov     r8, r15; lpValueName
0x180028f8c  lea     rax, [rbp+Type]
0x180028f90  mov     [rsp+60h+lpData], 0; lpData
0x180028f99  mov     [rsp+60h+lpType], rax; lpType
0x180028f9e  mov     [rsp+60h+phkResult], 0; lpReserved
0x180028fa7  mov     [rbp+cchValueName], 104h
0x180028fae  call    cs:__imp_RegEnumValueW
0x180028fb4  mov     ebx, eax
0x180028fb6  cmp     eax, 103h
0x180028fbb  jz      short loc_180028FE8
0x180028fbd  xor     edi, edi
0x180028fbf  test    eax, eax
0x180028fc1  jz      short loc_180028FCA
0x180028fc3  cmp     eax, 0EAh
0x180028fc8  jnz     short loc_180028F60
0x180028fca  mov     eax, [rbp+cbData]
0x180028fcd  test    eax, eax
0x180028fcf  jz      loc_180029066
0x180028fd5  mov     edx, eax
0x180028fd7  mov     rcx, rsi
0x180028fda  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180028fdf  test    al, al
0x180028fe1  jnz     short loc_180029002
0x180028fe3  mov     edi, 8007000Eh
0x180028fe8  mov     rcx, r14; hObject
0x180028feb  call    cs:__imp_CloseHandle
0x180028ff1  mov     rcx, [rbp+hKey]; hKey
0x180028ff5  call    cs:__imp_RegCloseKey
0x180028ffb  mov     eax, edi
0x180028ffd  jmp     loc_180029124
0x180029002  mov     edx, [rbp+dwIndex]; dwIndex
0x180029005  lea     rax, [rbp+cbData]
0x180029009  mov     rcx, [rbp+hKey]; hKey
0x18002900d  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180029011  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180029016  mov     r8, r15; lpValueName
0x180029019  mov     rax, [rsi]
0x18002901c  mov     [rsp+60h+lpData], rax; lpData
0x180029021  lea     rax, [rbp+Type]
0x180029025  mov     [rsp+60h+lpType], rax; lpType
0x18002902a  mov     [rsp+60h+phkResult], rdi; lpReserved
0x18002902f  mov     [rbp+cchValueName], 104h
0x180029036  call    cs:__imp_RegEnumValueW
0x18002903c  mov     ebx, eax
0x18002903e  test    eax, eax
0x180029040  jz      short loc_180029066
0x180029042  mov     rcx, r14; hObject
0x180029045  call    cs:__imp_CloseHandle
0x18002904b  mov     rcx, [rbp+hKey]; hKey
0x18002904f  call    cs:__imp_RegCloseKey
0x180029055  mov     rcx, [rsi]; Block
0x180029058  call    cs:__imp_free
0x18002905e  mov     [rsi], rdi
0x180029061  jmp     loc_180028F2A
0x180029066  mov     rcx, [rbp+hKey]; hKey
0x18002906a  lea     rax, [rbp+var_18]
0x18002906e  mov     [rsp+60h+lpType], rax; lpcbData
0x180029073  lea     r9, [rbp+var_1C]; lpType
0x180029077  xor     r8d, r8d; lpReserved
0x18002907a  mov     [rsp+60h+phkResult], rdi; lpData
0x18002907f  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x180029086  call    cs:__imp_RegQueryValueExW
0x18002908c  mov     rcx, [rbp+hKey]; hKey
0x180029090  mov     edi, eax
0x180029092  call    cs:__imp_RegCloseKey
0x180029098  xor     edx, edx; dwMilliseconds
0x18002909a  mov     rcx, r14; hHandle
0x18002909d  call    cs:__imp_WaitForSingleObject
0x1800290a3  mov     rcx, r14; hObject
0x1800290a6  mov     ebx, eax
0x1800290a8  call    cs:__imp_CloseHandle
0x1800290ae  test    ebx, ebx
0x1800290b0  jnz     short loc_1800290B9
0x1800290b2  mov     ebx, 8007051Ah
0x1800290b7  jmp     short loc_1800290F9
0x1800290b9  test    edi, edi
0x1800290bb  jz      short loc_1800290EE
0x1800290bd  cmp     edi, 2
0x1800290c0  jz      short loc_180029114
0x1800290c2  mov     rcx, [rsi]; Block
0x1800290c5  call    cs:__imp_free
0x1800290cb  xor     eax, eax
0x1800290cd  mov     qword ptr [rsi], 0
0x1800290d4  mov     [r15], ax
0x1800290d8  test    edi, edi
0x1800290da  jle     loc_180028FFB
0x1800290e0  movzx   edi, di
0x1800290e3  or      edi, 80070000h
0x1800290e9  jmp     loc_180028FFB
0x1800290ee  cmp     [rbp+var_1C], 6
0x1800290f2  jnz     short loc_180029114
0x1800290f4  mov     ebx, 800705B8h
0x1800290f9  mov     rcx, [rsi]; Block
0x1800290fc  call    cs:__imp_free
0x180029102  xor     ecx, ecx
0x180029104  mov     qword ptr [rsi], 0
0x18002910b  mov     [r15], cx
0x18002910f  jmp     loc_180028F37
0x180029114  mov     eax, [rbp+Type]
0x180029117  mov     [r12], eax
0x18002911b  mov     eax, [rbp+cbData]
0x18002911e  mov     [r13+0], eax
0x180029122  xor     eax, eax
0x180029124  mov     rbx, [rsp+60h+arg_0]
0x18002912c  add     rsp, 60h
0x180029130  pop     r15
0x180029132  pop     r14
0x180029134  pop     r13
0x180029136  pop     r12
0x180029138  pop     rdi
0x180029139  pop     rsi
0x18002913a  pop     rbp
0x18002913b  retn
```

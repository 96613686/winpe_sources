# _lambda_5d8abe126ccde22c1560365abf811aa4_::operator()

- ea: `0x1800a1fe0`
- end: `0x1800a217c`
- name: `_lambda_5d8abe126ccde22c1560365abf811aa4_::operator()`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a01a0`

## callees

- `0x180006e50`
- `0x1800a1fe0`
- `0x1800abbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a2084`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a2084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2149`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2149`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2069`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2069`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a20ad`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a210b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a20ad`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a210b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2139`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a20cd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a211d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a20cd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a211d`

## pseudocode

```c
__int64 __fastcall lambda_5d8abe126ccde22c1560365abf811aa4_::operator()(
        __int64 a1,
        SystemSettings::StorageSenseHandlers::CAppNotificationSink *a2)
{
  __int64 v2; // rax
  signed int v3; // ebx
  HKEY *phkResult; // rdi
  HANDLE EventW; // rax
  HKEY v6; // rcx
  HKEY v7; // rcx
  void *v8; // r9
  DWORD v9; // ebx
  signed int i; // ebx
  HKEY v11; // rcx
  void *v12; // rcx
  HANDLE Handles; // [rsp+38h] [rbp-11h] BYREF
  __int128 v16; // [rsp+40h] [rbp-9h]
  __int64 v17; // [rsp+50h] [rbp+7h]
  __int64 v18; // [rsp+58h] [rbp+Fh]
  HKEY hKey; // [rsp+60h] [rbp+17h] BYREF
  __int128 v20; // [rsp+68h] [rbp+1Fh]
  __int64 v21; // [rsp+78h] [rbp+2Fh]

  v21 = 0;
  Handles = 0;
  v2 = *((_QWORD *)a2 + 9);
  v3 = 0;
  v17 = 0;
  v18 = v2;
  hKey = 0;
  v20 = 0;
  v16 = 0;
  do
  {
    phkResult = &hKey + v3;
    if ( RegOpenKeyExW(
           (HKEY)*(&SystemSettings::StorageSenseHandlers::m_rgKeys + 66 * v3),
           (LPCWSTR)&SystemSettings::StorageSenseHandlers::m_rgKeys + 264 * v3 + 4,
           0,
           0x20019u,
           phkResult) )
    {
      *phkResult = 0;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    v6 = *phkResult;
    *(&Handles + v3) = EventW;
    if ( v6 && EventW )
      RegNotifyChangeKeyValue(v6, 0, 1u, EventW, 1);
    ++v3;
  }
  while ( (unsigned int)v3 < 4 );
  while ( 1 )
  {
    v9 = WaitForMultipleObjects(5u, &Handles, 0, 0xFFFFFFFF);
    if ( v9 >= 4 )
      break;
    SystemSettings::StorageSenseHandlers::CAppNotificationSink::OnListChange(a2);
    v7 = *(&hKey + v9);
    if ( v7 )
    {
      v8 = *(&Handles + v9);
      if ( v8 )
        RegNotifyChangeKeyValue(v7, 0, 4u, v8, 1);
    }
  }
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    v11 = *(&hKey + i);
    if ( v11 )
      RegCloseKey(v11);
    v12 = *(&Handles + i);
    if ( v12 )
      CloseHandle(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a1fe0  mov     [rsp-8+arg_0], rbx
0x1800a1fe5  mov     [rsp-8+arg_10], rsi
0x1800a1fea  push    rbp
0x1800a1feb  push    rdi
0x1800a1fec  push    r14
0x1800a1fee  lea     rbp, [rsp-47h]
0x1800a1ff3  sub     rsp, 90h
0x1800a1ffa  mov     rax, cs:__security_cookie
0x1800a2001  xor     rax, rsp
0x1800a2004  mov     [rbp+57h+var_20], rax
0x1800a2008  xor     eax, eax
0x1800a200a  mov     [rbp+57h+var_70], rdx
0x1800a200e  xorps   xmm0, xmm0
0x1800a2011  mov     [rbp+57h+var_28], rax
0x1800a2015  mov     [rbp+57h+Handles], rax
0x1800a2019  lea     r14, ?m_rgKeys@StorageSenseHandlers@SystemSettings@@3PAUAPPREGKEY@12@A; SystemSettings::StorageSenseHandlers::APPREGKEY near * SystemSettings::StorageSenseHandlers::m_rgKeys
0x1800a2020  mov     rax, [rdx+48h]
0x1800a2024  xor     ebx, ebx
0x1800a2026  movups  [rbp+57h+var_50], xmm0
0x1800a202a  mov     qword ptr [rbp+57h+var_50+8], rax
0x1800a202e  mov     [rbp+57h+hKey], 0
0x1800a2036  movups  [rbp+57h+var_38], xmm0
0x1800a203a  movups  [rbp+57h+var_60], xmm0
0x1800a203e  movsxd  rsi, ebx
0x1800a2041  lea     rdi, [rbp+57h+hKey]
0x1800a2045  imul    rcx, rsi, 210h
0x1800a204c  lea     rdx, [r14+8]
0x1800a2050  mov     r9d, 20019h; samDesired
0x1800a2056  add     rdx, rcx; lpSubKey
0x1800a2059  lea     rdi, [rdi+rsi*8]
0x1800a205d  xor     r8d, r8d; ulOptions
0x1800a2060  mov     [rsp+0A0h+phkResult], rdi; phkResult
0x1800a2065  mov     rcx, [rcx+r14]; hKey
0x1800a2069  call    cs:__imp_RegOpenKeyExW
0x1800a206f  test    eax, eax
0x1800a2071  jz      short loc_1800A207A
0x1800a2073  mov     qword ptr [rdi], 0
0x1800a207a  xor     r9d, r9d; lpName
0x1800a207d  xor     r8d, r8d; bInitialState
0x1800a2080  xor     edx, edx; bManualReset
0x1800a2082  xor     ecx, ecx; lpEventAttributes
0x1800a2084  call    cs:__imp_CreateEventW
0x1800a208a  mov     rcx, [rdi]; hKey
0x1800a208d  mov     [rbp+rsi*8+57h+Handles], rax
0x1800a2092  test    rcx, rcx
0x1800a2095  jz      short loc_1800A20B3
0x1800a2097  test    rax, rax
0x1800a209a  jz      short loc_1800A20B3
0x1800a209c  xor     edx, edx; bWatchSubtree
0x1800a209e  mov     dword ptr [rsp+0A0h+phkResult], 1; fAsynchronous
0x1800a20a6  mov     r9, rax; hEvent
0x1800a20a9  lea     r8d, [rdx+1]; dwNotifyFilter
0x1800a20ad  call    cs:__imp_RegNotifyChangeKeyValue
0x1800a20b3  inc     ebx
0x1800a20b5  cmp     ebx, 4
0x1800a20b8  jb      short loc_1800A203E
0x1800a20ba  xor     r8d, r8d; bWaitAll
0x1800a20bd  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800a20c1  or      edi, 0FFFFFFFFh
0x1800a20c4  mov     r9d, edi; dwMilliseconds
0x1800a20c7  lea     esi, [r8+5]
0x1800a20cb  mov     ecx, esi; nCount
0x1800a20cd  call    cs:__imp_WaitForMultipleObjects
0x1800a20d3  mov     r14, [rbp+57h+var_70]
0x1800a20d7  jmp     short loc_1800A2123
0x1800a20d9  cmp     ebx, 4
0x1800a20dc  jnb     short loc_1800A212A
0x1800a20de  mov     rcx, r14; this
0x1800a20e1  call    ?OnListChange@CAppNotificationSink@StorageSenseHandlers@SystemSettings@@QEAAXXZ; SystemSettings::StorageSenseHandlers::CAppNotificationSink::OnListChange(void)
0x1800a20e6  mov     r9d, ebx
0x1800a20e9  mov     rcx, [rbp+r9*8+57h+hKey]; hKey
0x1800a20ee  test    rcx, rcx
0x1800a20f1  jz      short loc_1800A2111
0x1800a20f3  mov     r9, [rbp+r9*8+57h+Handles]; hEvent
0x1800a20f8  test    r9, r9
0x1800a20fb  jz      short loc_1800A2111
0x1800a20fd  xor     edx, edx; bWatchSubtree
0x1800a20ff  mov     dword ptr [rsp+0A0h+phkResult], 1; fAsynchronous
0x1800a2107  lea     r8d, [rdx+4]; dwNotifyFilter
0x1800a210b  call    cs:__imp_RegNotifyChangeKeyValue
0x1800a2111  mov     r9d, edi; dwMilliseconds
0x1800a2114  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800a2118  xor     r8d, r8d; bWaitAll
0x1800a211b  mov     ecx, esi; nCount
0x1800a211d  call    cs:__imp_WaitForMultipleObjects
0x1800a2123  mov     ebx, eax
0x1800a2125  cmp     eax, 4
0x1800a2128  jnz     short loc_1800A20D9
0x1800a212a  xor     ebx, ebx
0x1800a212c  movsxd  rdi, ebx
0x1800a212f  mov     rcx, [rbp+rdi*8+57h+hKey]; hKey
0x1800a2134  test    rcx, rcx
0x1800a2137  jz      short loc_1800A213F
0x1800a2139  call    cs:__imp_RegCloseKey
0x1800a213f  mov     rcx, [rbp+rdi*8+57h+Handles]; hObject
0x1800a2144  test    rcx, rcx
0x1800a2147  jz      short loc_1800A214F
0x1800a2149  call    cs:__imp_CloseHandle
0x1800a214f  inc     ebx
0x1800a2151  cmp     ebx, 4
0x1800a2154  jb      short loc_1800A212C
0x1800a2156  xor     eax, eax
0x1800a2158  mov     rcx, [rbp+57h+var_20]
0x1800a215c  xor     rcx, rsp; StackCookie
0x1800a215f  call    __security_check_cookie
0x1800a2164  lea     r11, [rsp+0A0h+var_10]
0x1800a216c  mov     rbx, [r11+20h]
0x1800a2170  mov     rsi, [r11+30h]
0x1800a2174  mov     rsp, r11
0x1800a2177  pop     r14
0x1800a2179  pop     rdi
0x1800a217a  pop     rbp
0x1800a217b  retn
```

# InitializeEndpointManager

- ea: `0x180008e98`
- end: `0x1800090fd`
- name: `InitializeEndpointManager`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800081a4`

## callees

- `0x180008390`
- `0x180008e98`
- `0x180009104`
- `0x180009270`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x180008f89`
- `ntdll!EtwEventRegister` at `0x180008f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000907c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000907c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008f26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000903d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008f26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000903d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009056`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009056`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ee3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ff7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ee3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ff7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800090ae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800090ae`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000906a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000906a`

## string_xrefs

- `0x180008ed9`: `System\CurrentControlSet\Services\RpcSs`
- `0x180008fed`: `Software\Microsoft\Windows\CurrentVersion\NetworkServiceTriggers\Config\`
- `0x18000905c`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 InitializeEndpointManager()
{
  __int64 v0; // rdx
  __int64 v1; // rdx
  __int64 v2; // rdx
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  LSTATUS ValueW; // eax
  int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdi
  _QWORD *v11; // rax
  __int64 v12; // rax
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  int pvData; // [rsp+68h] [rbp+28h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+30h] BYREF

  hkey = 0;
  pcbData = 0;
  pvData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\RpcSs", 0, 0x20019u, &hkey) )
  {
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"ListenOnInternet", 2u, 0, &pvData, &pcbData) )
    {
      if ( (_WORD)pvData == 89
        || (unsigned __int16)(pvData - 78) <= 0x2Bu
        && (v0 = 0x80100000001LL, _bittest64(&v0, (unsigned int)(pvData - 78)))
        && (fListenOnInternet = 0, (_WORD)pvData == 121) )
      {
        fListenOnInternet = 1;
      }
    }
    RegCloseKey(hkey);
  }
  if ( (unsigned int)EtwEventRegister(&EpmapEtwGuid, 0, 0, &g_EpmapEtwHandle) )
    g_EpmapEtwHandle = 0;
  v3 = McGenEventRegister_EtwEventRegister(
         &EndpointTriggerGuid,
         v1,
         &EndpointTriggerGuid_Context,
         &EndpointTriggerGuid_Context);
  if ( !v3 )
  {
    v3 = McGenEventRegister_EtwEventRegister(
           &SERVICE_TRIGGER_PERF_EVENT_GUID,
           v2,
           &SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
           &SERVICE_TRIGGER_PERF_EVENT_GUID_Context);
    if ( !v3 )
    {
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\NetworkServiceTriggers\\Config\\",
             0,
             0x20019u,
             &hkey) )
      {
        v4 = 300000;
      }
      else
      {
        pcbData = 4;
        ValueW = RegGetValueW(hkey, 0, L"RpcTimeout", 0x10u, 0, &pvData, &pcbData);
        v6 = pvData;
        if ( ValueW )
          v6 = 300000;
        v4 = v6;
        RegCloseKey(hkey);
      }
      g_hSC_AutoStartComplete = (__int64)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
      if ( g_hSC_AutoStartComplete )
      {
        v3 = NtrbInitialize(v8, v7, v4);
        if ( !v3 )
        {
          v9 = 0;
          v10 = 0;
          do
          {
            InitializeCriticalSection((LPCRITICAL_SECTION)&RtdsTriggerUpdateLock + v9);
            v11 = (_QWORD *)((char *)&RtdsTriggerDbList + v10);
            *(_QWORD *)((char *)&unk_180013D28 + v10) = (char *)&RtdsTriggerDbList + v10;
            v10 += 16;
            *v11 = v11;
            v12 = 56 * v9++;
            *(_QWORD *)((char *)&unk_1800133E8 + v12) = 0;
          }
          while ( v9 != 2 );
          v3 = 0;
          ConfigInitialProtocols();
        }
      }
      else
      {
        return GetLastError();
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180008e98  mov     [rsp-18h+arg_18], rbx
0x180008e9d  push    rbp
0x180008e9e  push    rdi
0x180008e9f  push    r14
0x180008ea1  mov     rbp, rsp
0x180008ea4  sub     rsp, 40h
0x180008ea8  lea     rax, [rbp+hkey]
0x180008eac  mov     [rbp+hkey], 0
0x180008eb4  mov     edi, 20019h
0x180008eb9  mov     [rbp+arg_0], 0
0x180008ec0  mov     r14, 0FFFFFFFF80000002h
0x180008ec7  mov     [rbp+arg_8], 0
0x180008ece  mov     r9d, edi; samDesired
0x180008ed1  mov     [rsp+40h+phkResult], rax; phkResult
0x180008ed6  mov     rcx, r14; hKey
0x180008ed9  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Rp"...
0x180008ee0  xor     r8d, r8d; ulOptions
0x180008ee3  call    cs:__imp_RegOpenKeyExW
0x180008ee9  test    eax, eax
0x180008eeb  jnz     loc_180008F76
0x180008ef1  mov     rcx, [rbp+hkey]; hkey
0x180008ef5  lea     rax, [rbp+arg_0]
0x180008ef9  mov     [rsp+40h+pcbData], rax; pcbData
0x180008efe  lea     r8, aListenonintern; "ListenOnInternet"
0x180008f05  lea     rax, [rbp+arg_8]
0x180008f09  mov     [rbp+arg_0], 4
0x180008f10  mov     [rsp+40h+pvData], rax; pvData
0x180008f15  mov     r9d, 2; dwFlags
0x180008f1b  xor     edx, edx; lpSubKey
0x180008f1d  mov     [rsp+40h+phkResult], 0; pdwType
0x180008f26  call    cs:__imp_RegGetValueW
0x180008f2c  test    eax, eax
0x180008f2e  jnz     short loc_180008F6C
0x180008f30  mov     ecx, [rbp+arg_8]
0x180008f33  cmp     cx, 59h ; 'Y'
0x180008f37  jz      short loc_180008F62
0x180008f39  lea     eax, [rcx-4Eh]
0x180008f3c  cmp     ax, 2Bh ; '+'
0x180008f40  ja      short loc_180008F6C
0x180008f42  mov     rdx, 80100000001h
0x180008f4c  bt      rdx, rax
0x180008f50  jnb     short loc_180008F6C
0x180008f52  mov     cs:?fListenOnInternet@@3HA, 0; int fListenOnInternet
0x180008f5c  cmp     cx, 79h ; 'y'
0x180008f60  jnz     short loc_180008F6C
0x180008f62  mov     cs:?fListenOnInternet@@3HA, 1; int fListenOnInternet
0x180008f6c  mov     rcx, [rbp+hkey]; hKey
0x180008f70  call    cs:__imp_RegCloseKey
0x180008f76  lea     r9, g_EpmapEtwHandle
0x180008f7d  xor     r8d, r8d
0x180008f80  xor     edx, edx
0x180008f82  lea     rcx, EpmapEtwGuid
0x180008f89  call    cs:__imp_EtwEventRegister
0x180008f8f  test    eax, eax
0x180008f91  jz      short loc_180008F9E
0x180008f93  mov     cs:g_EpmapEtwHandle, 0
0x180008f9e  lea     r8, EndpointTriggerGuid_Context
0x180008fa5  mov     r9, r8
0x180008fa8  lea     rcx, EndpointTriggerGuid
0x180008faf  call    McGenEventRegister_EtwEventRegister
0x180008fb4  mov     ebx, eax
0x180008fb6  test    eax, eax
0x180008fb8  jnz     loc_1800090ED
0x180008fbe  lea     r8, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x180008fc5  mov     r9, r8
0x180008fc8  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID
0x180008fcf  call    McGenEventRegister_EtwEventRegister
0x180008fd4  mov     ebx, eax
0x180008fd6  test    eax, eax
0x180008fd8  jnz     loc_1800090ED
0x180008fde  lea     rax, [rbp+hkey]
0x180008fe2  mov     r9d, edi; samDesired
0x180008fe5  xor     r8d, r8d; ulOptions
0x180008fe8  mov     [rsp+40h+phkResult], rax; phkResult
0x180008fed  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008ff4  mov     rcx, r14; hKey
0x180008ff7  call    cs:__imp_RegOpenKeyExW
0x180008ffd  test    eax, eax
0x180008fff  jz      short loc_180009008
0x180009001  mov     ebx, 493E0h
0x180009006  jmp     short loc_18000905C
0x180009008  mov     rcx, [rbp+hkey]; hkey
0x18000900c  lea     rax, [rbp+arg_0]
0x180009010  mov     [rsp+40h+pcbData], rax; pcbData
0x180009015  lea     r8, aRpctimeout; "RpcTimeout"
0x18000901c  lea     rax, [rbp+arg_8]
0x180009020  mov     [rbp+arg_0], 4
0x180009027  mov     [rsp+40h+pvData], rax; pvData
0x18000902c  mov     r9d, 10h; dwFlags
0x180009032  xor     edx, edx; lpSubKey
0x180009034  mov     [rsp+40h+phkResult], 0; pdwType
0x18000903d  call    cs:__imp_RegGetValueW
0x180009043  mov     ecx, [rbp+arg_8]
0x180009046  mov     ebx, 493E0h
0x18000904b  test    eax, eax
0x18000904d  cmovnz  ecx, ebx
0x180009050  mov     ebx, ecx
0x180009052  mov     rcx, [rbp+hkey]; hKey
0x180009056  call    cs:__imp_RegCloseKey
0x18000905c  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x180009063  xor     edx, edx; bInheritHandle
0x180009065  mov     ecx, 100000h; dwDesiredAccess
0x18000906a  call    cs:__imp_OpenEventW
0x180009070  mov     cs:g_hSC_AutoStartComplete, rax
0x180009077  test    rax, rax
0x18000907a  jnz     short loc_180009086
0x18000907c  call    cs:__imp_GetLastError
0x180009082  mov     ebx, eax
0x180009084  jmp     short loc_1800090ED
0x180009086  mov     r8d, ebx
0x180009089  call    NtrbInitialize
0x18000908e  mov     ebx, eax
0x180009090  test    eax, eax
0x180009092  jnz     short loc_1800090ED
0x180009094  xor     ebx, ebx
0x180009096  lea     r14, __ImageBase
0x18000909d  xor     edi, edi
0x18000909f  lea     rax, [rbx+rbx*4]
0x1800090a3  lea     rcx, rva RtdsTriggerUpdateLock[r14]
0x1800090aa  lea     rcx, [rcx+rax*8]; lpCriticalSection
0x1800090ae  call    cs:__imp_InitializeCriticalSection
0x1800090b4  lea     rax, rva RtdsTriggerDbList[r14]
0x1800090bb  add     rax, rdi
0x1800090be  mov     [rdi+r14+13D28h], rax
0x1800090c6  add     rdi, 10h
0x1800090ca  mov     [rax], rax
0x1800090cd  imul    rax, rbx, 38h ; '8'
0x1800090d1  inc     rbx
0x1800090d4  mov     qword ptr [rax+r14+133E8h], 0
0x1800090e0  cmp     rbx, 2
0x1800090e4  jnz     short loc_18000909F
0x1800090e6  xor     ebx, ebx
0x1800090e8  call    ?ConfigInitialProtocols@@YAKXZ; ConfigInitialProtocols(void)
0x1800090ed  mov     eax, ebx
0x1800090ef  mov     rbx, [rsp+40h+arg_18]
0x1800090f4  add     rsp, 40h
0x1800090f8  pop     r14
0x1800090fa  pop     rdi
0x1800090fb  pop     rbp
0x1800090fc  retn
```

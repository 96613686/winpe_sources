# PhoneCallIdGenerator::GeneratePhoneCallId(uint *)

- ea: `0x18007cbfc`
- end: `0x18007cdd2`
- name: `?GeneratePhoneCallId@PhoneCallIdGenerator@@QEAAJPEAI@Z`
- size: `470`
- prototype: `__int64 __fastcall(PhoneCallIdGenerator *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006ffcc`

## callees

- `0x180006e94`
- `0x18001db10`
- `0x18007cbfc`
- `0x18007cdd8`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cd81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cdac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cd81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cdac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007cd4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007cd4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007cce4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007cce4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007cc7f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007cc7f`

## string_xrefs

- `0x18007cc4d`: `Software\Microsoft\Phone\ServiceVolatile\Volatile`

## pseudocode

```c
__int64 __fastcall PhoneCallIdGenerator::GeneratePhoneCallId(PhoneCallIdGenerator *this, unsigned int *a2)
{
  HKEY v3; // rcx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  LSTATUS v11; // eax
  int v12; // eax
  LSTATUS v13; // eax
  BackTraceCollection *v14; // rcx
  BYTE Data[4]; // [rsp+50h] [rbp-20h] BYREF
  DWORD Type; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+58h] [rbp-18h] BYREF
  BYTE v19[4]; // [rsp+5Ch] [rbp-14h] BYREF

  EnterCriticalSection(&stru_1800B41B8);
  v3 = g_phoneCallIdGenerator;
  if ( !g_phoneCallIdGenerator )
  {
    phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&g_phoneCallIdGenerator);
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Phone\\ServiceVolatile\\Volatile",
            0,
            0,
            1u,
            3u,
            0,
            phkResult,
            0);
    v7 = Key;
    if ( Key )
    {
      if ( Key > 0 )
        v7 = (unsigned __int16)Key | 0x80070000;
      BackTraceCollection::Capture(v6, v7);
      v10 = 28;
      goto LABEL_23;
    }
    v3 = g_phoneCallIdGenerator;
  }
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v11 = RegQueryValueExW(v3, L"NextCallId", 0, &Type, Data, &cbData);
  v7 = v11;
  if ( v11 )
  {
    if ( v11 != 2 )
    {
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      v10 = 56;
      goto LABEL_23;
    }
LABEL_14:
    v12 = 1;
    *(_DWORD *)Data = 1;
    goto LABEL_15;
  }
  if ( Type != 4 || cbData != 4 )
  {
    v7 = -2147418113;
    v10 = 41;
    goto LABEL_23;
  }
  v12 = *(_DWORD *)Data;
  if ( !*(_DWORD *)Data )
    goto LABEL_14;
LABEL_15:
  *(_DWORD *)v19 = v12 + 1;
  v13 = RegSetValueExW(g_phoneCallIdGenerator, L"NextCallId", 0, 4u, v19, 4u);
  v7 = v13;
  if ( !v13 )
  {
    *a2 = *(_DWORD *)Data;
    LeaveCriticalSection(&stru_1800B41B8);
    return 0;
  }
  if ( v13 > 0 )
    v7 = (unsigned __int16)v13 | 0x80070000;
  BackTraceCollection::Capture(v14, v7);
  v10 = 68;
LABEL_23:
  Log_HREvent_25(v7, v8, v9, v10);
  LeaveCriticalSection(&stru_1800B41B8);
  return v7;
}

```

## disassembly

```asm
0x18007cbfc  mov     [rsp-8+arg_0], rbx
0x18007cc01  mov     [rsp-8+arg_10], rdi
0x18007cc06  push    rbp
0x18007cc07  mov     rbp, rsp
0x18007cc0a  sub     rsp, 70h
0x18007cc0e  mov     rax, cs:__security_cookie
0x18007cc15  xor     rax, rsp
0x18007cc18  mov     [rbp+var_10], rax
0x18007cc1c  lea     rcx, stru_1800B41B8; lpCriticalSection
0x18007cc23  mov     rdi, rdx
0x18007cc26  call    cs:__imp_EnterCriticalSection
0x18007cc2c  mov     rcx, cs:?g_phoneCallIdGenerator@@3VPhoneCallIdGenerator@@A; PhoneCallIdGenerator g_phoneCallIdGenerator
0x18007cc33  test    rcx, rcx
0x18007cc36  jnz     short loc_18007CCAF
0x18007cc38  lea     rcx, ?g_phoneCallIdGenerator@@3VPhoneCallIdGenerator@@A; PhoneCallIdGenerator g_phoneCallIdGenerator
0x18007cc3f  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18007cc44  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18007cc4d  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Phone\\ServiceVola"...
0x18007cc54  mov     [rsp+70h+phkResult], rax; phkResult
0x18007cc59  xor     r9d, r9d; lpClass
0x18007cc5c  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007cc65  xor     r8d, r8d; Reserved
0x18007cc68  mov     [rsp+70h+samDesired], 3; samDesired
0x18007cc70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cc77  mov     [rsp+70h+dwOptions], 1; dwOptions
0x18007cc7f  call    cs:__imp_RegCreateKeyExW
0x18007cc85  mov     ebx, eax
0x18007cc87  test    eax, eax
0x18007cc89  jz      short loc_18007CCA8
0x18007cc8b  jle     short loc_18007CC96
0x18007cc8d  movzx   ebx, ax
0x18007cc90  or      ebx, 80070000h
0x18007cc96  mov     edx, ebx; int
0x18007cc98  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18007cc9d  mov     r9d, 1Ch
0x18007cca3  jmp     loc_18007CD9E
0x18007cca8  mov     rcx, cs:?g_phoneCallIdGenerator@@3VPhoneCallIdGenerator@@A; hKey
0x18007ccaf  lea     rax, [rbp+cbData]
0x18007ccb3  mov     dword ptr [rbp+Data], 0
0x18007ccba  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x18007ccbf  lea     r9, [rbp+Type]; lpType
0x18007ccc3  lea     rax, [rbp+Data]
0x18007ccc7  mov     [rbp+Type], 0
0x18007ccce  xor     r8d, r8d; lpReserved
0x18007ccd1  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18007ccd6  lea     rdx, ValueName; "NextCallId"
0x18007ccdd  mov     [rbp+cbData], 4
0x18007cce4  call    cs:__imp_RegQueryValueExW
0x18007ccea  mov     ebx, eax
0x18007ccec  test    eax, eax
0x18007ccee  jnz     short loc_18007CD15
0x18007ccf0  cmp     [rbp+Type], 4
0x18007ccf4  jnz     short loc_18007CD05
0x18007ccf6  cmp     [rbp+cbData], 4
0x18007ccfa  jnz     short loc_18007CD05
0x18007ccfc  mov     eax, dword ptr [rbp+Data]
0x18007ccff  test    eax, eax
0x18007cd01  jz      short loc_18007CD1A
0x18007cd03  jmp     short loc_18007CD22
0x18007cd05  mov     ebx, 8000FFFFh
0x18007cd0a  mov     r9d, 29h ; ')'
0x18007cd10  jmp     loc_18007CD9E
0x18007cd15  cmp     eax, 2
0x18007cd18  jnz     short loc_18007CD8B
0x18007cd1a  mov     eax, 1
0x18007cd1f  mov     dword ptr [rbp+Data], eax
0x18007cd22  mov     rcx, cs:?g_phoneCallIdGenerator@@3VPhoneCallIdGenerator@@A; hKey
0x18007cd29  lea     rdx, ValueName; "NextCallId"
0x18007cd30  inc     eax
0x18007cd32  mov     [rsp+70h+samDesired], 4; cbData
0x18007cd3a  mov     dword ptr [rbp+var_14], eax
0x18007cd3d  mov     r9d, 4; dwType
0x18007cd43  lea     rax, [rbp+var_14]
0x18007cd47  xor     r8d, r8d; Reserved
0x18007cd4a  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18007cd4f  call    cs:__imp_RegSetValueExW
0x18007cd55  mov     ebx, eax
0x18007cd57  test    eax, eax
0x18007cd59  jz      short loc_18007CD75
0x18007cd5b  jle     short loc_18007CD66
0x18007cd5d  movzx   ebx, ax
0x18007cd60  or      ebx, 80070000h
0x18007cd66  mov     edx, ebx; int
0x18007cd68  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18007cd6d  mov     r9d, 44h ; 'D'
0x18007cd73  jmp     short loc_18007CD9E
0x18007cd75  mov     eax, dword ptr [rbp+Data]
0x18007cd78  lea     rcx, stru_1800B41B8; lpCriticalSection
0x18007cd7f  mov     [rdi], eax
0x18007cd81  call    cs:__imp_LeaveCriticalSection
0x18007cd87  xor     eax, eax
0x18007cd89  jmp     short loc_18007CDB4
0x18007cd8b  test    eax, eax
0x18007cd8d  jle     short loc_18007CD98
0x18007cd8f  movzx   ebx, ax
0x18007cd92  or      ebx, 80070000h
0x18007cd98  mov     r9d, 38h ; '8'
0x18007cd9e  mov     ecx, ebx
0x18007cda0  call    Log_HREvent_25
0x18007cda5  lea     rcx, stru_1800B41B8; lpCriticalSection
0x18007cdac  call    cs:__imp_LeaveCriticalSection
0x18007cdb2  mov     eax, ebx
0x18007cdb4  mov     rcx, [rbp+var_10]
0x18007cdb8  xor     rcx, rsp; StackCookie
0x18007cdbb  call    __security_check_cookie
0x18007cdc0  lea     r11, [rsp+70h+var_s0]
0x18007cdc5  mov     rbx, [r11+10h]
0x18007cdc9  mov     rdi, [r11+20h]
0x18007cdcd  mov     rsp, r11
0x18007cdd0  pop     rbp
0x18007cdd1  retn
```

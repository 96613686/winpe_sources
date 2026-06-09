# EnterpriseConfig::GenerateRequestId(_GUID *)

- ea: `0x1800277d0`
- end: `0x180027a12`
- name: `?GenerateRequestId@EnterpriseConfig@@SAJPEAU_GUID@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013400`
- `0x18001a704`

## callees

- `0x18001b4bc`
- `0x1800277d0`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002786d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002786d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027880`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800279d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800279d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002784e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002784e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800278cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800278cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027993`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800279e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800279e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027908`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027908`

## string_xrefs

- `0x1800278bf`: `Software\Microsoft\EnterpriseAppManagement\Service`

## pseudocode

```c
__int64 __fastcall EnterpriseConfig::GenerateRequestId(struct _GUID *a1)
{
  int Data1; // esi
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  int v5; // edi
  int v6; // eax
  BYTE Data[8]; // [rsp+58h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-31h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-29h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-25h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-21h] BYREF
  int v13; // [rsp+78h] [rbp-19h] BYREF
  __int64 v14; // [rsp+7Ch] [rbp-15h]
  int v15; // [rsp+84h] [rbp-Dh]
  struct _RTL_CRITICAL_SECTION *v16; // [rsp+88h] [rbp-9h]
  GUID v17; // [rsp+90h] [rbp-1h] BYREF

  Data1 = GUID_NULL.Data1;
  *(_DWORD *)Data = 1;
  hKey = 0;
  dwDisposition = 0;
  Type = 0;
  cbData = 0;
  v17 = GUID_NULL;
  v16 = &EnterpriseConfig::m_csLock;
  EnterCriticalSection(&EnterpriseConfig::m_csLock);
  if ( a1 )
  {
    hKey = 0;
    v4 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\EnterpriseAppManagement\\Service",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKey,
           &dwDisposition);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"LastRequestId", 0, &Type, Data, &cbData) || Type == 4 )
      {
        v3 = 0;
        v5 = 0;
        while ( !v5 )
        {
          do
          {
            Data1 = 1;
            if ( *(_DWORD *)Data != -1 )
              Data1 = *(_DWORD *)Data + 1;
            *(_DWORD *)Data = Data1;
            v13 = Data1;
            v14 = *(_QWORD *)&GUID_NULL.Data2;
            v15 = *(_DWORD *)&GUID_NULL.Data4[4];
            v6 = EnrollmentManager::RetrieveGUID(1, &v13, 0, &v17);
            v3 = v6;
          }
          while ( !v6 );
          if ( v6 == -2147023888 )
          {
            if ( RegSetValueExW(hKey, L"LastRequestId", 0, 4u, Data, 4u) )
            {
              v3 = -2147467259;
              goto LABEL_21;
            }
            v3 = 0;
            v5 = 1;
          }
          else if ( v6 < 0 )
          {
            goto LABEL_21;
          }
        }
        a1->Data1 = Data1;
        *(_QWORD *)&a1->Data2 = *(_QWORD *)&GUID_NULL.Data2;
        *(_DWORD *)&a1->Data4[4] = *(_DWORD *)&GUID_NULL.Data4[4];
      }
      else
      {
        v3 = -2147023884;
      }
    }
  }
  else
  {
    v3 = -2147024809;
  }
LABEL_21:
  LeaveCriticalSection(&EnterpriseConfig::m_csLock);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x1800277d0  mov     rax, rsp
0x1800277d3  push    rbp
0x1800277d4  push    rbx
0x1800277d5  push    rsi
0x1800277d6  push    rdi
0x1800277d7  push    r14
0x1800277d9  push    r15
0x1800277db  lea     rbp, [rax-5Fh]
0x1800277df  sub     rsp, 0B8h
0x1800277e6  movaps  xmmword ptr [rax-48h], xmm6
0x1800277ea  mov     rax, cs:__security_cookie
0x1800277f1  xor     rax, rsp
0x1800277f4  mov     qword ptr [rbp+57h+var_48], rax
0x1800277f8  mov     r14, rcx
0x1800277fb  mov     esi, cs:GUID_NULL.Data1
0x180027801  movsd   xmm6, qword ptr cs:GUID_NULL.Data2
0x180027809  mov     r15d, dword ptr cs:GUID_NULL.Data4+4
0x180027810  mov     dword ptr [rbp+57h+Data], 1
0x180027817  mov     [rbp+57h+hKey], 0
0x18002781f  mov     [rbp+57h+dwDisposition], 0
0x180027826  mov     [rbp+57h+Type], 0
0x18002782d  mov     [rbp+57h+cbData], 0
0x180027834  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002783b  movdqu  [rbp+57h+var_58], xmm0
0x180027840  lea     rax, ?m_csLock@EnterpriseConfig@@0Vrecursive_mutex@utl@@A; utl::recursive_mutex EnterpriseConfig::m_csLock
0x180027847  mov     [rbp+57h+var_60], rax
0x18002784b  mov     rcx, rax; lpCriticalSection
0x18002784e  call    cs:__imp_EnterCriticalSection
0x180027854  nop
0x180027855  test    r14, r14
0x180027858  jnz     short loc_180027864
0x18002785a  mov     ebx, 80070057h
0x18002785f  jmp     loc_1800279CF
0x180027864  mov     rdi, [rbp+57h+hKey]
0x180027868  test    rdi, rdi
0x18002786b  jz      short loc_180027886
0x18002786d  call    cs:__imp_GetLastError
0x180027873  mov     ebx, eax
0x180027875  mov     rcx, rdi; hKey
0x180027878  call    cs:__imp_RegCloseKey
0x18002787e  mov     ecx, ebx; dwErrCode
0x180027880  call    cs:__imp_SetLastError
0x180027886  mov     [rbp+57h+hKey], 0
0x18002788e  lea     rax, [rbp+57h+dwDisposition]
0x180027892  mov     [rsp+40h], rax; lpdwDisposition
0x180027897  lea     rax, [rbp+57h+hKey]
0x18002789b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800278a0  mov     [rsp+0E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800278a9  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x1800278b1  mov     [rsp+0E0h+dwOptions], 0; dwOptions
0x1800278b9  xor     r9d, r9d; lpClass
0x1800278bc  xor     r8d, r8d; Reserved
0x1800278bf  lea     rdx, SubKey; "Software\\Microsoft\\EnterpriseAppManag"...
0x1800278c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800278cd  call    cs:__imp_RegCreateKeyExW
0x1800278d3  mov     ebx, eax
0x1800278d5  test    eax, eax
0x1800278d7  jnz     loc_1800279C4
0x1800278dd  mov     [rbp+57h+cbData], 4
0x1800278e4  lea     rax, [rbp+57h+cbData]
0x1800278e8  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x1800278ed  lea     rax, [rbp+57h+Data]
0x1800278f1  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x1800278f6  lea     r9, [rbp+57h+Type]; lpType
0x1800278fa  xor     r8d, r8d; lpReserved
0x1800278fd  lea     rdx, aLastrequestid; "LastRequestId"
0x180027904  mov     rcx, [rbp+57h+hKey]; hKey
0x180027908  call    cs:__imp_RegQueryValueExW
0x18002790e  test    eax, eax
0x180027910  jnz     short loc_180027922
0x180027912  cmp     [rbp+57h+Type], 4
0x180027916  jz      short loc_180027922
0x180027918  mov     ebx, 800703F4h
0x18002791d  jmp     loc_1800279CF
0x180027922  xor     ebx, ebx
0x180027924  xor     edi, edi
0x180027926  test    edi, edi
0x180027928  jnz     loc_1800279B5
0x18002792e  mov     eax, dword ptr [rbp+57h+Data]
0x180027931  cmp     eax, 0FFFFFFFFh
0x180027934  mov     esi, 1
0x180027939  jz      short loc_18002793E
0x18002793b  lea     esi, [rax+1]
0x18002793e  mov     dword ptr [rbp+57h+Data], esi
0x180027941  mov     [rbp+57h+var_70], esi
0x180027944  movsd   [rbp+57h+var_6C], xmm6
0x180027949  mov     [rbp+57h+var_64], r15d
0x18002794d  xor     r8d, r8d
0x180027950  lea     r9, [rbp+57h+var_58]
0x180027954  lea     rdx, [rbp+57h+var_70]
0x180027958  lea     ecx, [r8+1]
0x18002795c  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x180027961  mov     ebx, eax
0x180027963  test    eax, eax
0x180027965  jz      short loc_18002792E
0x180027967  cmp     eax, 800703F0h
0x18002796c  jnz     short loc_1800279A4
0x18002796e  mov     [rsp+0E0h+samDesired], 4; cbData
0x180027976  lea     rax, [rbp+57h+Data]
0x18002797a  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002797f  mov     r9d, 4; dwType
0x180027985  xor     r8d, r8d; Reserved
0x180027988  lea     rdx, aLastrequestid; "LastRequestId"
0x18002798f  mov     rcx, [rbp+57h+hKey]; hKey
0x180027993  call    cs:__imp_RegSetValueExW
0x180027999  test    eax, eax
0x18002799b  jnz     short loc_1800279AE
0x18002799d  xor     ebx, ebx
0x18002799f  lea     edi, [rax+1]
0x1800279a2  jmp     short loc_180027926
0x1800279a4  test    eax, eax
0x1800279a6  jns     loc_180027926
0x1800279ac  jmp     short loc_1800279CF
0x1800279ae  mov     ebx, 80004005h
0x1800279b3  jmp     short loc_1800279CF
0x1800279b5  mov     [r14], esi
0x1800279b8  movsd   qword ptr [r14+4], xmm6
0x1800279be  mov     [r14+0Ch], r15d
0x1800279c2  jmp     short loc_1800279CF
0x1800279c4  jle     short loc_1800279CF
0x1800279c6  movzx   ebx, ax
0x1800279c9  or      ebx, 80070000h
0x1800279cf  lea     rcx, ?m_csLock@EnterpriseConfig@@0Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800279d6  call    cs:__imp_LeaveCriticalSection
0x1800279dc  nop
0x1800279dd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800279e1  test    rcx, rcx
0x1800279e4  jz      short loc_1800279EC
0x1800279e6  call    cs:__imp_RegCloseKey
0x1800279ec  mov     eax, ebx
0x1800279ee  mov     rcx, qword ptr [rbp+57h+var_48]
0x1800279f2  xor     rcx, rsp; StackCookie
0x1800279f5  call    __security_check_cookie
0x1800279fa  movaps  xmm6, [rsp+0E0h+var_48+8]
0x180027a02  add     rsp, 0B8h
0x180027a09  pop     r15
0x180027a0b  pop     r14
0x180027a0d  pop     rdi
0x180027a0e  pop     rsi
0x180027a0f  pop     rbx
0x180027a10  pop     rbp
0x180027a11  retn
```

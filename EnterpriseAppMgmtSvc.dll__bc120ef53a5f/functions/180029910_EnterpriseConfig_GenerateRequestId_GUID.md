# EnterpriseConfig::GenerateRequestId(_GUID *)

- ea: `0x180029910`
- end: `0x180029b8c`
- name: `?GenerateRequestId@EnterpriseConfig@@SAJPEAU_GUID@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013eb4`
- `0x18001b9f4`

## callees

- `0x18001c818`
- `0x180029910`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800299d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800299d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029b43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029b43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002998e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002998e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029a25`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029a25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029af7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029af7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800299c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029b59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800299c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029b59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029a66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029a66`

## string_xrefs

- `0x180029a17`: `Software\Microsoft\EnterpriseAppManagement\Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180029910  mov     rax, rsp
0x180029913  push    rbp
0x180029914  push    rbx
0x180029915  push    rsi
0x180029916  push    rdi
0x180029917  push    r14
0x180029919  push    r15
0x18002991b  lea     rbp, [rax-5Fh]
0x18002991f  sub     rsp, 0B8h
0x180029926  movaps  xmmword ptr [rax-48h], xmm6
0x18002992a  mov     rax, cs:__security_cookie
0x180029931  xor     rax, rsp
0x180029934  mov     qword ptr [rbp+57h+var_48], rax
0x180029938  mov     r14, rcx
0x18002993b  mov     esi, cs:GUID_NULL.Data1
0x180029941  movsd   xmm6, qword ptr cs:GUID_NULL.Data2
0x180029949  mov     r15d, dword ptr cs:GUID_NULL.Data4+4
0x180029950  mov     dword ptr [rbp+57h+Data], 1
0x180029957  mov     [rbp+57h+hKey], 0
0x18002995f  mov     [rbp+57h+dwDisposition], 0
0x180029966  mov     [rbp+57h+Type], 0
0x18002996d  mov     [rbp+57h+cbData], 0
0x180029974  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002997b  movdqu  [rbp+57h+var_58], xmm0
0x180029980  lea     rax, ?m_csLock@EnterpriseConfig@@0Vrecursive_mutex@utl@@A; utl::recursive_mutex EnterpriseConfig::m_csLock
0x180029987  mov     [rbp+57h+var_60], rax
0x18002998b  mov     rcx, rax; lpCriticalSection
0x18002998e  call    cs:__imp_EnterCriticalSection
0x180029995  nop     dword ptr [rax+rax+00h]
0x18002999a  nop
0x18002999b  test    r14, r14
0x18002999e  jnz     short loc_1800299AA
0x1800299a0  mov     ebx, 80070057h
0x1800299a5  jmp     loc_180029B3C
0x1800299aa  mov     rdi, [rbp+57h+hKey]
0x1800299ae  test    rdi, rdi
0x1800299b1  jz      short loc_1800299DE
0x1800299b3  call    cs:__imp_GetLastError
0x1800299ba  nop     dword ptr [rax+rax+00h]
0x1800299bf  mov     ebx, eax
0x1800299c1  mov     rcx, rdi; hKey
0x1800299c4  call    cs:__imp_RegCloseKey
0x1800299cb  nop     dword ptr [rax+rax+00h]
0x1800299d0  mov     ecx, ebx; dwErrCode
0x1800299d2  call    cs:__imp_SetLastError
0x1800299d9  nop     dword ptr [rax+rax+00h]
0x1800299de  mov     [rbp+57h+hKey], 0
0x1800299e6  lea     rax, [rbp+57h+dwDisposition]
0x1800299ea  mov     [rsp+40h], rax; lpdwDisposition
0x1800299ef  lea     rax, [rbp+57h+hKey]
0x1800299f3  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800299f8  mov     [rsp+0E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180029a01  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x180029a09  mov     [rsp+0E0h+dwOptions], 0; dwOptions
0x180029a11  xor     r9d, r9d; lpClass
0x180029a14  xor     r8d, r8d; Reserved
0x180029a17  lea     rdx, SubKey; "Software\\Microsoft\\EnterpriseAppManag"...
0x180029a1e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029a25  call    cs:__imp_RegCreateKeyExW
0x180029a2c  nop     dword ptr [rax+rax+00h]
0x180029a31  mov     ebx, eax
0x180029a33  test    eax, eax
0x180029a35  jnz     loc_180029B31
0x180029a3b  mov     [rbp+57h+cbData], 4
0x180029a42  lea     rax, [rbp+57h+cbData]
0x180029a46  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x180029a4b  lea     rax, [rbp+57h+Data]
0x180029a4f  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x180029a54  lea     r9, [rbp+57h+Type]; lpType
0x180029a58  xor     r8d, r8d; lpReserved
0x180029a5b  lea     rdx, aLastrequestid; "LastRequestId"
0x180029a62  mov     rcx, [rbp+57h+hKey]; hKey
0x180029a66  call    cs:__imp_RegQueryValueExW
0x180029a6d  nop     dword ptr [rax+rax+00h]
0x180029a72  test    eax, eax
0x180029a74  jnz     short loc_180029A86
0x180029a76  cmp     [rbp+57h+Type], 4
0x180029a7a  jz      short loc_180029A86
0x180029a7c  mov     ebx, 800703F4h
0x180029a81  jmp     loc_180029B3C
0x180029a86  xor     ebx, ebx
0x180029a88  xor     edi, edi
0x180029a8a  test    edi, edi
0x180029a8c  jnz     loc_180029B22
0x180029a92  mov     eax, dword ptr [rbp+57h+Data]
0x180029a95  cmp     eax, 0FFFFFFFFh
0x180029a98  mov     esi, 1
0x180029a9d  jz      short loc_180029AA2
0x180029a9f  lea     esi, [rax+1]
0x180029aa2  mov     dword ptr [rbp+57h+Data], esi
0x180029aa5  mov     [rbp+57h+var_70], esi
0x180029aa8  movsd   [rbp+57h+var_6C], xmm6
0x180029aad  mov     [rbp+57h+var_64], r15d
0x180029ab1  xor     r8d, r8d
0x180029ab4  lea     r9, [rbp+57h+var_58]
0x180029ab8  lea     rdx, [rbp+57h+var_70]
0x180029abc  lea     ecx, [r8+1]
0x180029ac0  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x180029ac5  mov     ebx, eax
0x180029ac7  test    eax, eax
0x180029ac9  jz      short loc_180029A92
0x180029acb  cmp     eax, 800703F0h
0x180029ad0  jnz     short loc_180029B11
0x180029ad2  mov     [rsp+0E0h+samDesired], 4; cbData
0x180029ada  lea     rax, [rbp+57h+Data]
0x180029ade  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x180029ae3  mov     r9d, 4; dwType
0x180029ae9  xor     r8d, r8d; Reserved
0x180029aec  lea     rdx, aLastrequestid; "LastRequestId"
0x180029af3  mov     rcx, [rbp+57h+hKey]; hKey
0x180029af7  call    cs:__imp_RegSetValueExW
0x180029afe  nop     dword ptr [rax+rax+00h]
0x180029b03  test    eax, eax
0x180029b05  jnz     short loc_180029B1B
0x180029b07  xor     ebx, ebx
0x180029b09  lea     edi, [rax+1]
0x180029b0c  jmp     loc_180029A8A
0x180029b11  test    eax, eax
0x180029b13  jns     loc_180029A8A
0x180029b19  jmp     short loc_180029B3C
0x180029b1b  mov     ebx, 80004005h
0x180029b20  jmp     short loc_180029B3C
0x180029b22  mov     [r14], esi
0x180029b25  movsd   qword ptr [r14+4], xmm6
0x180029b2b  mov     [r14+0Ch], r15d
0x180029b2f  jmp     short loc_180029B3C
0x180029b31  jle     short loc_180029B3C
0x180029b33  movzx   ebx, ax
0x180029b36  or      ebx, 80070000h
0x180029b3c  lea     rcx, ?m_csLock@EnterpriseConfig@@0Vrecursive_mutex@utl@@A; lpCriticalSection
0x180029b43  call    cs:__imp_LeaveCriticalSection
0x180029b4a  nop     dword ptr [rax+rax+00h]
0x180029b4f  nop
0x180029b50  mov     rcx, [rbp+57h+hKey]; hKey
0x180029b54  test    rcx, rcx
0x180029b57  jz      short loc_180029B65
0x180029b59  call    cs:__imp_RegCloseKey
0x180029b60  nop     dword ptr [rax+rax+00h]
0x180029b65  mov     eax, ebx
0x180029b67  mov     rcx, qword ptr [rbp+57h+var_48]
0x180029b6b  xor     rcx, rsp; StackCookie
0x180029b6e  call    __security_check_cookie
0x180029b73  movaps  xmm6, [rsp+0E0h+var_48+8]
0x180029b7b  add     rsp, 0B8h
0x180029b82  pop     r15
0x180029b84  pop     r14
0x180029b86  pop     rdi
0x180029b87  pop     rsi
0x180029b88  pop     rbx
0x180029b89  pop     rbp
0x180029b8a  retn
```

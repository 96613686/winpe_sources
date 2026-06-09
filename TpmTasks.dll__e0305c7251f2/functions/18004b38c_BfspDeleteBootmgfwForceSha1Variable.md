# BfspDeleteBootmgfwForceSha1Variable

- ea: `0x18004b38c`
- end: `0x18004b561`
- name: `BfspDeleteBootmgfwForceSha1Variable`
- size: `469`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180049234`

## callees

- `0x1800078b0`
- `0x18004b38c`
- `0x18004cdd4`
- `0x18004cf64`
- `0x18004d118`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18004b3f9`
- `ntdll!NtQuerySystemInformation` at `0x18004b3f9`
- `ntdll!RtlInitUnicodeString` at `0x18004b47b`
- `ntdll!RtlInitUnicodeString` at `0x18004b47b`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18004b499`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18004b499`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x18004b4e5`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x18004b4e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b52a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b546`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b52a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b51b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b51b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b537`

## string_xrefs

- `0x18004b416`: `SeSystemEnvironmentPrivilege`
- `0x18004b435`: `Failed to create privilege info for BootmgfwForceSHA1 cleanup.`
- `0x18004b45a`: `Failed to acquire SE_SYSTEM_ENVIRONMENT_PRIVILEGE for BootmgfwForceSHA1 cleanup.`
- `0x18004b4ef`: `Failed to delete BootmgfwForceSHA1 variable. Status: %#x`
- `0x18004b4f8`: `Deleted BootmgfwForceSHA1 UEFI variable.`

## pseudocode

```c
NTSTATUS BfspDeleteBootmgfwForceSha1Variable()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v3; // rax
  ULONG *Attributes; // [rsp+20h] [rbp-29h]
  ULONG ReturnLength; // [rsp+30h] [rbp-19h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-11h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-9h] BYREF
  const WCHAR *v8; // [rsp+48h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  GUID VendorGuid; // [rsp+60h] [rbp+17h] BYREF
  __int128 SystemInformation; // [rsp+70h] [rbp+27h] BYREF
  __int128 v12; // [rsp+80h] [rbp+37h]

  VendorGuid.Data1 = 2012912317;
  *(_DWORD *)&VendorGuid.Data2 = 1295123289;
  *(_DWORD *)VendorGuid.Data4 = -198680387;
  SystemInformation = 0;
  *(_DWORD *)&VendorGuid.Data4[4] = 1266192359;
  ReturnLength = 0;
  NewState = 0;
  v12 = 0;
  lpMem = 0;
  DestinationString = 0;
  result = NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  if ( result >= 0 && (_DWORD)v12 == 2 )
  {
    v8 = L"SeSystemEnvironmentPrivilege";
    if ( (unsigned int)BfspCreateTokenPrivilegesInformation(&v8, 1, 1, &NewState) )
    {
      if ( (unsigned int)BfspAdjustTokenPrivileges(NewState, (struct _TOKEN_PRIVILEGES **)&lpMem) )
      {
        ReturnLength = 0;
        RtlInitUnicodeString(&DestinationString, L"BootmgfwForceSHA1");
        result = NtQuerySystemEnvironmentValueEx(&DestinationString, &VendorGuid, 0, &ReturnLength, 0);
        if ( result != -1073741568 )
        {
          if ( (int)(result + 0x80000000) < 0 || result == -1073741789 )
          {
            LODWORD(Attributes) = 1;
            v1 = NtSetSystemEnvironmentValueEx(&DestinationString, &VendorGuid, 0, 0, Attributes);
            if ( v1 >= 0 )
              result = BfspLogMessage(2, L"Deleted BootmgfwForceSHA1 UEFI variable.");
            else
              result = BfspLogMessage(3, L"Failed to delete BootmgfwForceSHA1 variable. Status: %#x", (unsigned int)v1);
          }
          else
          {
            result = BfspLogMessage(3, L"Failed to query BootmgfwForceSHA1 variable. Status: %#x", (unsigned int)result);
          }
        }
      }
      else
      {
        result = BfspLogMessage(3, L"Failed to acquire SE_SYSTEM_ENVIRONMENT_PRIVILEGE for BootmgfwForceSHA1 cleanup.");
      }
      if ( lpMem )
      {
        BfspAdjustTokenPrivileges((PTOKEN_PRIVILEGES)lpMem, 0);
        ProcessHeap = GetProcessHeap();
        result = HeapFree(ProcessHeap, 0, lpMem);
      }
    }
    else
    {
      result = BfspLogMessage(3, L"Failed to create privilege info for BootmgfwForceSHA1 cleanup.");
    }
    if ( NewState )
    {
      v3 = GetProcessHeap();
      return HeapFree(v3, 0, NewState);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004b38c  push    rbp
0x18004b38e  lea     rbp, [rsp-57h]
0x18004b393  sub     rsp, 0A0h
0x18004b39a  mov     rax, cs:__security_cookie
0x18004b3a1  xor     rax, rsp
0x18004b3a4  mov     [rbp+57h+var_10], rax
0x18004b3a8  xorps   xmm0, xmm0
0x18004b3ab  mov     [rbp+57h+VendorGuid.Data1], 77FA9ABDh
0x18004b3b2  xor     r9d, r9d; ReturnLength
0x18004b3b5  mov     dword ptr [rbp+57h+VendorGuid.Data2], 4D320359h
0x18004b3bc  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18004b3c0  mov     dword ptr [rbp+57h+VendorGuid.Data4], 0F42860BDh
0x18004b3c7  movups  [rbp+57h+SystemInformation], xmm0
0x18004b3cb  mov     dword ptr [rbp+57h+VendorGuid.Data4+4], 4B788FE7h
0x18004b3d2  lea     r8d, [r9+20h]; SystemInformationLength
0x18004b3d6  mov     [rbp+57h+ReturnLength], 0
0x18004b3dd  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18004b3e1  mov     [rbp+57h+NewState], 0
0x18004b3e9  movups  [rbp+57h+var_20], xmm0
0x18004b3ed  mov     [rbp+57h+lpMem], 0
0x18004b3f5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18004b3f9  call    cs:__imp_NtQuerySystemInformation
0x18004b3ff  test    eax, eax
0x18004b401  js      loc_18004B54C
0x18004b407  cmp     dword ptr [rbp+57h+var_20], 2
0x18004b40b  jnz     loc_18004B54C
0x18004b411  mov     edx, 1
0x18004b416  lea     rax, Name; "SeSystemEnvironmentPrivilege"
0x18004b41d  mov     r8d, edx
0x18004b420  mov     [rbp+57h+var_58], rax
0x18004b424  lea     r9, [rbp+57h+NewState]
0x18004b428  lea     rcx, [rbp+57h+var_58]
0x18004b42c  call    BfspCreateTokenPrivilegesInformation
0x18004b431  test    eax, eax
0x18004b433  jnz     short loc_18004B449
0x18004b435  lea     rdx, aFailedToCreate_7; "Failed to create privilege info for Boo"...
0x18004b43c  lea     ecx, [rax+3]
0x18004b43f  call    BfspLogMessage
0x18004b444  jmp     loc_18004B530
0x18004b449  mov     rcx, [rbp+57h+NewState]; NewState
0x18004b44d  lea     rdx, [rbp+57h+lpMem]
0x18004b451  call    BfspAdjustTokenPrivileges
0x18004b456  test    eax, eax
0x18004b458  jnz     short loc_18004B469
0x18004b45a  lea     rdx, aFailedToAcquir; "Failed to acquire SE_SYSTEM_ENVIRONMENT"...
0x18004b461  lea     ecx, [rax+3]
0x18004b464  jmp     loc_18004B504
0x18004b469  lea     rdx, aBootmgfwforces; "BootmgfwForceSHA1"
0x18004b470  mov     [rbp+57h+ReturnLength], 0
0x18004b477  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004b47b  call    cs:__imp_RtlInitUnicodeString
0x18004b481  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x18004b485  mov     [rsp+0A0h+Attributes], 0; Attributes
0x18004b48e  xor     r8d, r8d; Value
0x18004b491  lea     rdx, [rbp+57h+VendorGuid]; VendorGuid
0x18004b495  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x18004b499  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x18004b49f  cmp     eax, 0C0000100h
0x18004b4a4  jz      short loc_18004B509
0x18004b4a6  mov     edx, 80000000h
0x18004b4ab  lea     ecx, [rax+rdx]
0x18004b4ae  test    edx, ecx
0x18004b4b0  jnz     short loc_18004B4CF
0x18004b4b2  cmp     eax, 0C0000023h
0x18004b4b7  jz      short loc_18004B4CF
0x18004b4b9  lea     rdx, aFailedToQueryB; "Failed to query BootmgfwForceSHA1 varia"...
0x18004b4c0  mov     r8d, eax
0x18004b4c3  mov     ecx, 3
0x18004b4c8  call    BfspLogMessage
0x18004b4cd  jmp     short loc_18004B509
0x18004b4cf  xor     r9d, r9d; ReturnLength
0x18004b4d2  mov     dword ptr [rsp+0A0h+Attributes], 1; Attributes
0x18004b4da  xor     r8d, r8d; Value
0x18004b4dd  lea     rdx, [rbp+57h+VendorGuid]; VendorGuid
0x18004b4e1  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x18004b4e5  call    cs:__imp_NtSetSystemEnvironmentValueEx
0x18004b4eb  test    eax, eax
0x18004b4ed  jns     short loc_18004B4F8
0x18004b4ef  lea     rdx, aFailedToDelete; "Failed to delete BootmgfwForceSHA1 vari"...
0x18004b4f6  jmp     short loc_18004B4C0
0x18004b4f8  lea     rdx, aDeletedBootmgf; "Deleted BootmgfwForceSHA1 UEFI variable"...
0x18004b4ff  mov     ecx, 2
0x18004b504  call    BfspLogMessage
0x18004b509  cmp     [rbp+57h+lpMem], 0
0x18004b50e  jz      short loc_18004B530
0x18004b510  mov     rcx, [rbp+57h+lpMem]; NewState
0x18004b514  xor     edx, edx
0x18004b516  call    BfspAdjustTokenPrivileges
0x18004b51b  call    cs:__imp_GetProcessHeap
0x18004b521  mov     r8, [rbp+57h+lpMem]; lpMem
0x18004b525  xor     edx, edx; dwFlags
0x18004b527  mov     rcx, rax; hHeap
0x18004b52a  call    cs:__imp_HeapFree
0x18004b530  cmp     [rbp+57h+NewState], 0
0x18004b535  jz      short loc_18004B54C
0x18004b537  call    cs:__imp_GetProcessHeap
0x18004b53d  mov     r8, [rbp+57h+NewState]; lpMem
0x18004b541  xor     edx, edx; dwFlags
0x18004b543  mov     rcx, rax; hHeap
0x18004b546  call    cs:__imp_HeapFree
0x18004b54c  mov     rcx, [rbp+57h+var_10]
0x18004b550  xor     rcx, rsp; StackCookie
0x18004b553  call    __security_check_cookie
0x18004b558  add     rsp, 0A0h
0x18004b55f  pop     rbp
0x18004b560  retn
```

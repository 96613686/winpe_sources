# BfspDeleteBootmgfwForceSha1Variable

- ea: `0x14000c5e0`
- end: `0x14000c7b5`
- name: `BfspDeleteBootmgfwForceSha1Variable`
- size: `469`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140009fd4`

## callees

- `0x14000c5e0`
- `0x14000e628`
- `0x14000e79c`
- `0x14000e950`
- `0x140026650`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000c77e`
- `KERNEL32!HeapFree` at `0x14000c79a`
- `KERNEL32!HeapFree` at `0x14000c77e`
- `KERNEL32!HeapFree` at `0x14000c79a`
- `KERNEL32!GetProcessHeap` at `0x14000c76f`
- `KERNEL32!GetProcessHeap` at `0x14000c78b`
- `KERNEL32!GetProcessHeap` at `0x14000c76f`
- `KERNEL32!GetProcessHeap` at `0x14000c78b`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x14000c6ed`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x14000c6ed`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x14000c739`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x14000c739`
- `ntdll!NtQuerySystemInformation` at `0x14000c64d`
- `ntdll!NtQuerySystemInformation` at `0x14000c64d`
- `ntdll!RtlInitUnicodeString` at `0x14000c6cf`
- `ntdll!RtlInitUnicodeString` at `0x14000c6cf`

## string_xrefs

- `0x14000c689`: `Failed to create privilege info for BootmgfwForceSHA1 cleanup.`
- `0x14000c66a`: `SeSystemEnvironmentPrivilege`
- `0x14000c6ae`: `Failed to acquire SE_SYSTEM_ENVIRONMENT_PRIVILEGE for BootmgfwForceSHA1 cleanup.`
- `0x14000c743`: `Failed to delete BootmgfwForceSHA1 variable. Status: %#x`
- `0x14000c74c`: `Deleted BootmgfwForceSHA1 UEFI variable.`

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
    if ( (unsigned int)BfspCreateTokenPrivilegesInformation((__int64)&v8, 1u, 1, (unsigned int **)&NewState) )
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
0x14000c5e0  push    rbp
0x14000c5e2  lea     rbp, [rsp-57h]
0x14000c5e7  sub     rsp, 0A0h
0x14000c5ee  mov     rax, cs:__security_cookie
0x14000c5f5  xor     rax, rsp
0x14000c5f8  mov     [rbp+57h+var_10], rax
0x14000c5fc  xorps   xmm0, xmm0
0x14000c5ff  mov     [rbp+57h+VendorGuid.Data1], 77FA9ABDh
0x14000c606  xor     r9d, r9d; ReturnLength
0x14000c609  mov     dword ptr [rbp+57h+VendorGuid.Data2], 4D320359h
0x14000c610  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x14000c614  mov     dword ptr [rbp+57h+VendorGuid.Data4], 0F42860BDh
0x14000c61b  movups  [rbp+57h+SystemInformation], xmm0
0x14000c61f  mov     dword ptr [rbp+57h+VendorGuid.Data4+4], 4B788FE7h
0x14000c626  lea     r8d, [r9+20h]; SystemInformationLength
0x14000c62a  mov     [rbp+57h+ReturnLength], 0
0x14000c631  lea     ecx, [r9+5Ah]; SystemInformationClass
0x14000c635  mov     [rbp+57h+NewState], 0
0x14000c63d  movups  [rbp+57h+var_20], xmm0
0x14000c641  mov     [rbp+57h+lpMem], 0
0x14000c649  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000c64d  call    cs:__imp_NtQuerySystemInformation
0x14000c653  test    eax, eax
0x14000c655  js      loc_14000C7A0
0x14000c65b  cmp     dword ptr [rbp+57h+var_20], 2
0x14000c65f  jnz     loc_14000C7A0
0x14000c665  mov     edx, 1
0x14000c66a  lea     rax, Name; "SeSystemEnvironmentPrivilege"
0x14000c671  mov     r8d, edx
0x14000c674  mov     [rbp+57h+var_58], rax
0x14000c678  lea     r9, [rbp+57h+NewState]
0x14000c67c  lea     rcx, [rbp+57h+var_58]
0x14000c680  call    BfspCreateTokenPrivilegesInformation
0x14000c685  test    eax, eax
0x14000c687  jnz     short loc_14000C69D
0x14000c689  lea     rdx, aFailedToCreate_10; "Failed to create privilege info for Boo"...
0x14000c690  lea     ecx, [rax+3]
0x14000c693  call    BfspLogMessage
0x14000c698  jmp     loc_14000C784
0x14000c69d  mov     rcx, [rbp+57h+NewState]; NewState
0x14000c6a1  lea     rdx, [rbp+57h+lpMem]
0x14000c6a5  call    BfspAdjustTokenPrivileges
0x14000c6aa  test    eax, eax
0x14000c6ac  jnz     short loc_14000C6BD
0x14000c6ae  lea     rdx, aFailedToAcquir; "Failed to acquire SE_SYSTEM_ENVIRONMENT"...
0x14000c6b5  lea     ecx, [rax+3]
0x14000c6b8  jmp     loc_14000C758
0x14000c6bd  lea     rdx, aBootmgfwforces; "BootmgfwForceSHA1"
0x14000c6c4  mov     [rbp+57h+ReturnLength], 0
0x14000c6cb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000c6cf  call    cs:__imp_RtlInitUnicodeString
0x14000c6d5  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x14000c6d9  mov     [rsp+0A0h+Attributes], 0; Attributes
0x14000c6e2  xor     r8d, r8d; Value
0x14000c6e5  lea     rdx, [rbp+57h+VendorGuid]; VendorGuid
0x14000c6e9  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x14000c6ed  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x14000c6f3  cmp     eax, 0C0000100h
0x14000c6f8  jz      short loc_14000C75D
0x14000c6fa  mov     edx, 80000000h
0x14000c6ff  lea     ecx, [rax+rdx]
0x14000c702  test    edx, ecx
0x14000c704  jnz     short loc_14000C723
0x14000c706  cmp     eax, 0C0000023h
0x14000c70b  jz      short loc_14000C723
0x14000c70d  lea     rdx, aFailedToQueryB_0; "Failed to query BootmgfwForceSHA1 varia"...
0x14000c714  mov     r8d, eax
0x14000c717  mov     ecx, 3
0x14000c71c  call    BfspLogMessage
0x14000c721  jmp     short loc_14000C75D
0x14000c723  xor     r9d, r9d; ReturnLength
0x14000c726  mov     dword ptr [rsp+0A0h+Attributes], 1; Attributes
0x14000c72e  xor     r8d, r8d; Value
0x14000c731  lea     rdx, [rbp+57h+VendorGuid]; VendorGuid
0x14000c735  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x14000c739  call    cs:__imp_NtSetSystemEnvironmentValueEx
0x14000c73f  test    eax, eax
0x14000c741  jns     short loc_14000C74C
0x14000c743  lea     rdx, aFailedToDelete; "Failed to delete BootmgfwForceSHA1 vari"...
0x14000c74a  jmp     short loc_14000C714
0x14000c74c  lea     rdx, aDeletedBootmgf; "Deleted BootmgfwForceSHA1 UEFI variable"...
0x14000c753  mov     ecx, 2
0x14000c758  call    BfspLogMessage
0x14000c75d  cmp     [rbp+57h+lpMem], 0
0x14000c762  jz      short loc_14000C784
0x14000c764  mov     rcx, [rbp+57h+lpMem]; NewState
0x14000c768  xor     edx, edx
0x14000c76a  call    BfspAdjustTokenPrivileges
0x14000c76f  call    cs:__imp_GetProcessHeap
0x14000c775  mov     r8, [rbp+57h+lpMem]; lpMem
0x14000c779  xor     edx, edx; dwFlags
0x14000c77b  mov     rcx, rax; hHeap
0x14000c77e  call    cs:__imp_HeapFree
0x14000c784  cmp     [rbp+57h+NewState], 0
0x14000c789  jz      short loc_14000C7A0
0x14000c78b  call    cs:__imp_GetProcessHeap
0x14000c791  mov     r8, [rbp+57h+NewState]; lpMem
0x14000c795  xor     edx, edx; dwFlags
0x14000c797  mov     rcx, rax; hHeap
0x14000c79a  call    cs:__imp_HeapFree
0x14000c7a0  mov     rcx, [rbp+57h+var_10]
0x14000c7a4  xor     rcx, rsp; StackCookie
0x14000c7a7  call    __security_check_cookie
0x14000c7ac  add     rsp, 0A0h
0x14000c7b3  pop     rbp
0x14000c7b4  retn
```

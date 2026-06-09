# SetFolderFullControl(ushort const *)

- ea: `0x18002af4c`
- end: `0x18002b0f8`
- name: `?SetFolderFullControl@@YAJPEBG@Z`
- size: `428`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180029a80`

## callees

- `0x180002ce0`
- `0x18000d17c`
- `0x18002af4c`
- `0x18002b100`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b0b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002af9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002af9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002afaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002afaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b07d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b07d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b08b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b08b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b09d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b09d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002b064`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002b064`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002b005`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002b005`

## pseudocode

```c
__int64 __fastcall SetFolderFullControl(const unsigned __int16 *a1)
{
  signed int v1; // ebx
  HANDLE CurrentProcess; // rax
  signed int NamedSecurityInfoW; // eax
  PACL v4; // rdi
  signed int v5; // eax
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax
  PACL ppDacl; // [rsp+40h] [rbp-C0h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-B8h]
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pObjectName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = StringCchCopyW(pObjectName, 0x104u, a1);
  if ( v1 >= 0 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      ppDacl = 0;
      hMem = 0;
      NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &hMem);
      v1 = NamedSecurityInfoW;
      if ( NamedSecurityInfoW )
      {
        if ( NamedSecurityInfoW > 0 )
          v1 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
      }
      else
      {
        if ( ppDacl )
        {
          pDacl = 0;
          v1 = AddFullRightsForUser(ppDacl);
          if ( v1 >= 0 )
          {
            v4 = pDacl;
            v5 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
            if ( v5 )
            {
              if ( v5 > 0 )
                v1 = (unsigned __int16)v5 | 0x80070000;
              else
                v1 = v5;
            }
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v4);
          }
        }
        else
        {
          v1 = 1;
        }
        LocalFree(hMem);
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002af4c  mov     [rsp-8+arg_8], rbx
0x18002af51  mov     [rsp-8+arg_10], rdi
0x18002af56  push    rbp
0x18002af57  lea     rbp, [rsp-180h]
0x18002af5f  sub     rsp, 280h
0x18002af66  mov     rax, cs:__security_cookie
0x18002af6d  xor     rax, rsp
0x18002af70  mov     [rbp+180h+var_10], rax
0x18002af77  mov     r8, rcx; unsigned __int16 *
0x18002af7a  mov     edx, 104h; unsigned __int64
0x18002af7f  lea     rcx, [rsp+280h+pObjectName]; unsigned __int16 *
0x18002af84  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002af89  mov     ebx, eax
0x18002af8b  test    eax, eax
0x18002af8d  js      loc_18002B0D2
0x18002af93  mov     [rsp+280h+TokenHandle], 0
0x18002af9c  call    cs:__imp_GetCurrentProcess
0x18002afa2  lea     r8, [rsp+280h+TokenHandle]; TokenHandle
0x18002afa7  mov     edx, 8; DesiredAccess
0x18002afac  mov     rcx, rax; ProcessHandle
0x18002afaf  call    cs:__imp_OpenProcessToken
0x18002afb5  test    eax, eax
0x18002afb7  jz      loc_18002B0BD
0x18002afbd  xor     r9d, r9d; ppsidOwner
0x18002afc0  mov     [rsp+280h+var_240], 0
0x18002afc9  lea     rax, [rsp+280h+hMem]
0x18002afce  mov     [rsp+280h+hMem], 0
0x18002afd7  mov     [rsp+280h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002afdc  lea     rcx, [rsp+280h+pObjectName]; pObjectName
0x18002afe1  lea     rax, [rsp+280h+var_240]
0x18002afe6  mov     [rsp+280h+ppSacl], 0; ppSacl
0x18002afef  mov     [rsp+280h+ppDacl], rax; ppDacl
0x18002aff4  lea     edx, [r9+1]; ObjectType
0x18002aff8  lea     r8d, [r9+4]; SecurityInfo
0x18002affc  mov     [rsp+280h+ppsidGroup], 0; ppsidGroup
0x18002b005  call    cs:__imp_GetNamedSecurityInfoW
0x18002b00b  mov     ebx, eax
0x18002b00d  test    eax, eax
0x18002b00f  jnz     loc_18002B0A5
0x18002b015  mov     rcx, [rsp+280h+var_240]; Source
0x18002b01a  test    rcx, rcx
0x18002b01d  jz      short loc_18002B093
0x18002b01f  lea     rdx, [rsp+280h+pDacl]
0x18002b024  mov     [rsp+280h+pDacl], 0
0x18002b02d  call    _AddFullRightsForUser
0x18002b032  mov     ebx, eax
0x18002b034  test    eax, eax
0x18002b036  js      short loc_18002B098
0x18002b038  mov     rdi, [rsp+280h+pDacl]
0x18002b03d  lea     rcx, [rsp+280h+pObjectName]; pObjectName
0x18002b042  xor     r9d, r9d; psidOwner
0x18002b045  mov     [rsp+280h+ppSacl], 0; pSacl
0x18002b04e  mov     [rsp+280h+ppDacl], rdi; pDacl
0x18002b053  mov     [rsp+280h+ppsidGroup], 0; psidGroup
0x18002b05c  lea     edx, [r9+1]; ObjectType
0x18002b060  lea     r8d, [r9+4]; SecurityInfo
0x18002b064  call    cs:__imp_SetNamedSecurityInfoW
0x18002b06a  test    eax, eax
0x18002b06c  jz      short loc_18002B07D
0x18002b06e  jg      short loc_18002B074
0x18002b070  mov     ebx, eax
0x18002b072  jmp     short loc_18002B07D
0x18002b074  movzx   ebx, ax
0x18002b077  or      ebx, 80070000h
0x18002b07d  call    cs:__imp_GetProcessHeap
0x18002b083  mov     r8, rdi; lpMem
0x18002b086  xor     edx, edx; dwFlags
0x18002b088  mov     rcx, rax; hHeap
0x18002b08b  call    cs:__imp_HeapFree
0x18002b091  jmp     short loc_18002B098
0x18002b093  mov     ebx, 1
0x18002b098  mov     rcx, [rsp+280h+hMem]; hMem
0x18002b09d  call    cs:__imp_LocalFree
0x18002b0a3  jmp     short loc_18002B0B0
0x18002b0a5  jle     short loc_18002B0B0
0x18002b0a7  movzx   ebx, ax
0x18002b0aa  or      ebx, 80070000h
0x18002b0b0  mov     rcx, [rsp+280h+TokenHandle]; hObject
0x18002b0b5  call    cs:__imp_CloseHandle
0x18002b0bb  jmp     short loc_18002B0D2
0x18002b0bd  call    cs:__imp_GetLastError
0x18002b0c3  mov     ebx, eax
0x18002b0c5  test    eax, eax
0x18002b0c7  jle     short loc_18002B0D2
0x18002b0c9  movzx   ebx, ax
0x18002b0cc  or      ebx, 80070000h
0x18002b0d2  mov     eax, ebx
0x18002b0d4  mov     rcx, [rbp+180h+var_10]
0x18002b0db  xor     rcx, rsp; StackCookie
0x18002b0de  call    __security_check_cookie
0x18002b0e3  lea     r11, [rsp+280h+var_s0]
0x18002b0eb  mov     rbx, [r11+18h]
0x18002b0ef  mov     rdi, [r11+20h]
0x18002b0f3  mov     rsp, r11
0x18002b0f6  pop     rbp
0x18002b0f7  retn
```

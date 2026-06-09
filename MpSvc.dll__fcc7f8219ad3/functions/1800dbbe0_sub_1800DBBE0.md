# sub_1800DBBE0

- ea: `0x1800dbbe0`
- end: `0x1800dbe50`
- name: `sub_1800DBBE0`
- size: `624`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800db3c0`
- `0x1800e18d0`

## callees

- `0x18003814c`
- `0x1800381b4`
- `0x180067aa0`
- `0x1800a9750`
- `0x1800c2cd0`
- `0x1800dbbe0`
- `0x180473120`

## import_xrefs

- `MpClient!MpClientUtilExportFunctions` at `0x1800dbc3e`
- `MpClient!MpClientUtilExportFunctions` at `0x1800dbc3e`
- `MpClient!MpFreeMemory` at `0x1800dbd41`
- `MpClient!MpFreeMemory` at `0x1800dbe14`
- `MpClient!MpFreeMemory` at `0x1800dbd41`
- `MpClient!MpFreeMemory` at `0x1800dbe14`
- `KERNEL32!GetLastError` at `0x1800dbdc3`
- `KERNEL32!GetLastError` at `0x1800dbdc3`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbcd9`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbda4`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbe05`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbe23`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbcd9`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbda4`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbe05`
- `ADVAPI32!CloseServiceHandle` at `0x1800dbe23`
- `ADVAPI32!ChangeServiceConfig2W` at `0x1800dbdb9`
- `ADVAPI32!ChangeServiceConfig2W` at `0x1800dbdb9`

## string_xrefs

- `0x1800dbcee`: `ServiceName`
- `0x1800dbc4a`: `MpService_ServiceActionResetPeriod`

## pseudocode

```c
__int64 sub_1800DBBE0()
{
  int v0; // ebx
  __int64 v1; // rax
  int v2; // eax
  signed int v3; // ebx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rdx
  signed int LastError; // eax
  _DWORD Info[2]; // [rsp+28h] [rbp-19h] BYREF
  __int64 v10; // [rsp+30h] [rbp-11h]
  __int16 *v11; // [rsp+38h] [rbp-9h]
  int v12; // [rsp+40h] [rbp-1h]
  int v13; // [rsp+44h] [rbp+3h]
  _DWORD *v14; // [rsp+48h] [rbp+7h]
  __int16 v15; // [rsp+50h] [rbp+Fh] BYREF
  SC_HANDLE hSCObject; // [rsp+58h] [rbp+17h] BYREF
  __int64 v17; // [rsp+60h] [rbp+1Fh] BYREF
  int v18; // [rsp+68h] [rbp+27h] BYREF
  SC_HANDLE hService; // [rsp+70h] [rbp+2Fh] BYREF
  _DWORD v20[6]; // [rsp+78h] [rbp+37h] BYREF

  Info[1] = 0;
  v13 = 0;
  v20[1] = 1000;
  v20[0] = 1;
  v20[3] = 10000;
  v20[2] = 1;
  v20[5] = 60000;
  v20[4] = 1;
  v15 = 0;
  v0 = 86400;
  v18 = 86400;
  v1 = ((__int64 (*)(void))MpClientUtilExportFunctions)();
  if ( (*(int (__fastcall **)(const wchar_t *, __int64, int *))(v1 + 160))(
         L"MpService_ServiceActionResetPeriod",
         86400,
         &v18) >= 0 )
    v0 = v18;
  Info[0] = v0;
  v10 = 0;
  v11 = &v15;
  v12 = 3;
  v14 = v20;
  hSCObject = 0;
  v2 = sub_18003814C(&hSCObject, 1, 0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 107, qword_1804C2AE8, (unsigned int)v2);
LABEL_7:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return (unsigned int)v3;
  }
  v17 = 0;
  v5 = sub_1800C2CD0(L".", L"ServiceName", &v17);
  v3 = v5;
  if ( v5 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 108, qword_1804C2AE8, (unsigned int)v5);
LABEL_14:
    if ( v17 )
      MpFreeMemory(v17);
    goto LABEL_7;
  }
  hService = 0;
  v3 = sub_1800381B4(&hService, hSCObject, v17, 18);
  if ( v3 < 0 )
  {
    v6 = *(_QWORD *)&NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
    {
      v7 = 109;
LABEL_20:
      sub_1800A9750(*(_QWORD *)(v6 + 16), v7, qword_1804C2AE8, (unsigned int)v3);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  if ( !ChangeServiceConfig2W(hService, 2u, Info) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
    {
      v6 = *(_QWORD *)&NameType;
      if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      {
        v7 = 110;
        goto LABEL_20;
      }
LABEL_21:
      if ( hService )
        CloseServiceHandle(hService);
      goto LABEL_14;
    }
  }
  if ( hService )
    CloseServiceHandle(hService);
  if ( v17 )
    MpFreeMemory(v17);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  return 0;
}

```

## disassembly

```asm
0x1800dbbe0  mov     rax, rsp
0x1800dbbe3  mov     [rax+8], rbx
0x1800dbbe7  mov     [rax+10h], rsi
0x1800dbbeb  mov     [rax+18h], rdi
0x1800dbbef  push    rbp
0x1800dbbf0  lea     rbp, [rax-5Fh]
0x1800dbbf4  sub     rsp, 90h
0x1800dbbfb  mov     rax, cs:__security_cookie
0x1800dbc02  xor     rax, rsp
0x1800dbc05  mov     [rbp+57h+var_8], rax
0x1800dbc09  xor     edi, edi
0x1800dbc0b  mov     [rbp+57h+var_6C], edi
0x1800dbc0e  mov     [rbp+57h+var_54], edi
0x1800dbc11  mov     [rbp+57h+var_1C], 3E8h
0x1800dbc18  lea     esi, [rdi+1]
0x1800dbc1b  mov     [rbp+57h+var_20], esi
0x1800dbc1e  mov     [rbp+57h+var_14], 2710h
0x1800dbc25  mov     [rbp+57h+var_18], esi
0x1800dbc28  mov     [rbp+57h+var_C], 0EA60h
0x1800dbc2f  mov     [rbp+57h+var_10], esi
0x1800dbc32  mov     [rbp+57h+var_48], di
0x1800dbc36  mov     ebx, 15180h
0x1800dbc3b  mov     [rbp+57h+var_30], ebx
0x1800dbc3e  call    cs:MpClientUtilExportFunctions
0x1800dbc44  lea     r8, [rbp+57h+var_30]
0x1800dbc48  mov     edx, ebx
0x1800dbc4a  lea     rcx, aMpserviceServi; "MpService_ServiceActionResetPeriod"
0x1800dbc51  mov     rax, [rax+0A0h]
0x1800dbc58  call    cs:__guard_dispatch_icall_fptr
0x1800dbc5e  nop
0x1800dbc5f  test    eax, eax
0x1800dbc61  js      short loc_1800DBC66
0x1800dbc63  mov     ebx, [rbp+57h+var_30]
0x1800dbc66  mov     [rbp+57h+Info], ebx
0x1800dbc69  mov     [rbp+57h+var_68], rdi
0x1800dbc6d  lea     rax, [rbp+57h+var_48]
0x1800dbc71  mov     [rbp+57h+var_60], rax
0x1800dbc75  mov     [rbp+57h+var_58], 3
0x1800dbc7c  lea     rax, [rbp+57h+var_20]
0x1800dbc80  mov     [rbp+57h+var_50], rax
0x1800dbc84  mov     [rbp+57h+hSCObject], rdi
0x1800dbc88  xor     r9d, r9d
0x1800dbc8b  xor     r8d, r8d
0x1800dbc8e  mov     edx, esi
0x1800dbc90  lea     rcx, [rbp+57h+hSCObject]
0x1800dbc94  call    sub_18003814C
0x1800dbc99  mov     ebx, eax
0x1800dbc9b  test    eax, eax
0x1800dbc9d  jns     short loc_1800DBCE6
0x1800dbc9f  lea     rdx, NameType
0x1800dbca6  mov     rcx, cs:NameType
0x1800dbcad  cmp     rcx, rdx
0x1800dbcb0  jz      short loc_1800DBCD0
0x1800dbcb2  test    [rcx+1Ch], sil
0x1800dbcb6  jz      short loc_1800DBCD0
0x1800dbcb8  mov     edx, 6Bh ; 'k'
0x1800dbcbd  mov     r9d, eax
0x1800dbcc0  lea     r8, qword_1804C2AE8
0x1800dbcc7  mov     rcx, [rcx+10h]
0x1800dbccb  call    sub_1800A9750
0x1800dbcd0  mov     rcx, [rbp+57h+hSCObject]; hSCObject
0x1800dbcd4  test    rcx, rcx
0x1800dbcd7  jz      short loc_1800DBCDF
0x1800dbcd9  call    cs:__imp_CloseServiceHandle
0x1800dbcdf  mov     eax, ebx
0x1800dbce1  jmp     loc_1800DBE2B
0x1800dbce6  mov     [rbp+57h+var_38], rdi
0x1800dbcea  lea     r8, [rbp+57h+var_38]
0x1800dbcee  lea     rdx, aServicename; "ServiceName"
0x1800dbcf5  lea     rcx, asc_1804AB18C; "."
0x1800dbcfc  call    sub_1800C2CD0
0x1800dbd01  mov     ebx, eax
0x1800dbd03  test    eax, eax
0x1800dbd05  jns     short loc_1800DBD49
0x1800dbd07  lea     rdx, NameType
0x1800dbd0e  mov     rcx, cs:NameType
0x1800dbd15  cmp     rcx, rdx
0x1800dbd18  jz      short loc_1800DBD38
0x1800dbd1a  test    [rcx+1Ch], sil
0x1800dbd1e  jz      short loc_1800DBD38
0x1800dbd20  mov     edx, 6Ch ; 'l'
0x1800dbd25  mov     r9d, eax
0x1800dbd28  lea     r8, qword_1804C2AE8
0x1800dbd2f  mov     rcx, [rcx+10h]
0x1800dbd33  call    sub_1800A9750
0x1800dbd38  mov     rcx, [rbp+57h+var_38]
0x1800dbd3c  test    rcx, rcx
0x1800dbd3f  jz      short loc_1800DBCD0
0x1800dbd41  call    cs:__imp_MpFreeMemory
0x1800dbd47  jmp     short loc_1800DBCD0
0x1800dbd49  mov     [rbp+57h+hService], rdi
0x1800dbd4d  mov     r9d, 12h
0x1800dbd53  mov     r8, [rbp+57h+var_38]
0x1800dbd57  mov     rdx, [rbp+57h+hSCObject]
0x1800dbd5b  lea     rcx, [rbp+57h+hService]
0x1800dbd5f  call    sub_1800381B4
0x1800dbd64  mov     ebx, eax
0x1800dbd66  test    eax, eax
0x1800dbd68  jns     short loc_1800DBDAC
0x1800dbd6a  lea     rdx, NameType
0x1800dbd71  mov     rcx, cs:NameType
0x1800dbd78  cmp     rcx, rdx
0x1800dbd7b  jz      short loc_1800DBD9B
0x1800dbd7d  test    [rcx+1Ch], sil
0x1800dbd81  jz      short loc_1800DBD9B
0x1800dbd83  mov     edx, 6Dh ; 'm'
0x1800dbd88  mov     r9d, ebx
0x1800dbd8b  lea     r8, qword_1804C2AE8
0x1800dbd92  mov     rcx, [rcx+10h]
0x1800dbd96  call    sub_1800A9750
0x1800dbd9b  mov     rcx, [rbp+57h+hService]; hSCObject
0x1800dbd9f  test    rcx, rcx
0x1800dbda2  jz      short loc_1800DBD38
0x1800dbda4  call    cs:__imp_CloseServiceHandle
0x1800dbdaa  jmp     short loc_1800DBD38
0x1800dbdac  lea     r8, [rbp+57h+Info]; lpInfo
0x1800dbdb0  mov     edx, 2; dwInfoLevel
0x1800dbdb5  mov     rcx, [rbp+57h+hService]; hService
0x1800dbdb9  call    cs:ChangeServiceConfig2W
0x1800dbdbf  test    eax, eax
0x1800dbdc1  jnz     short loc_1800DBDFC
0x1800dbdc3  call    cs:GetLastError
0x1800dbdc9  mov     ebx, eax
0x1800dbdcb  test    eax, eax
0x1800dbdcd  jle     short loc_1800DBDD8
0x1800dbdcf  movzx   ebx, ax
0x1800dbdd2  or      ebx, 80070000h
0x1800dbdd8  test    ebx, ebx
0x1800dbdda  jns     short loc_1800DBDFC
0x1800dbddc  lea     rdx, NameType
0x1800dbde3  mov     rcx, cs:NameType
0x1800dbdea  cmp     rcx, rdx
0x1800dbded  jz      short loc_1800DBD9B
0x1800dbdef  test    [rcx+1Ch], sil
0x1800dbdf3  jz      short loc_1800DBD9B
0x1800dbdf5  mov     edx, 6Eh ; 'n'
0x1800dbdfa  jmp     short loc_1800DBD88
0x1800dbdfc  mov     rcx, [rbp+57h+hService]; hSCObject
0x1800dbe00  test    rcx, rcx
0x1800dbe03  jz      short loc_1800DBE0B
0x1800dbe05  call    cs:__imp_CloseServiceHandle
0x1800dbe0b  mov     rcx, [rbp+57h+var_38]
0x1800dbe0f  test    rcx, rcx
0x1800dbe12  jz      short loc_1800DBE1A
0x1800dbe14  call    cs:__imp_MpFreeMemory
0x1800dbe1a  mov     rcx, [rbp+57h+hSCObject]; hSCObject
0x1800dbe1e  test    rcx, rcx
0x1800dbe21  jz      short loc_1800DBE29
0x1800dbe23  call    cs:__imp_CloseServiceHandle
0x1800dbe29  xor     eax, eax
0x1800dbe2b  mov     rcx, [rbp+57h+var_8]
0x1800dbe2f  xor     rcx, rsp; StackCookie
0x1800dbe32  call    __security_check_cookie
0x1800dbe37  lea     r11, [rsp+90h+var_s0]
0x1800dbe3f  mov     rbx, [r11+10h]
0x1800dbe43  mov     rsi, [r11+18h]
0x1800dbe47  mov     rdi, [r11+20h]
0x1800dbe4b  mov     rsp, r11
0x1800dbe4e  pop     rbp
0x1800dbe4f  retn
```

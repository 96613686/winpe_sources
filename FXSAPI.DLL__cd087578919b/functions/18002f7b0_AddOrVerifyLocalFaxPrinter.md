# AddOrVerifyLocalFaxPrinter

- ea: `0x18002f7b0`
- end: `0x18002f9a5`
- name: `AddOrVerifyLocalFaxPrinter`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180029e10`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180016124`
- `0x18002d770`
- `0x18002d854`
- `0x18002f480`
- `0x18002f7b0`
- `0x18002ffb8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002f84c`
- `KERNEL32!GetLastError` at `0x18002f84c`
- `ADVAPI32!RegCloseKey` at `0x18002f8c0`
- `ADVAPI32!RegCloseKey` at `0x18002f8c0`

## string_xrefs

- `0x18002f8a6`: `Installed`

## pseudocode

```c
__int64 AddOrVerifyLocalFaxPrinter()
{
  _QWORD *v0; // rcx
  HKEY v1; // rax
  HKEY v2; // rdi
  DWORD LastError; // eax
  int RegistryDwordDefault; // eax
  int v6; // ebx
  const wchar_t *v7; // r9
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int Data; // [rsp+30h] [rbp+8h] BYREF
  int v13; // [rsp+38h] [rbp+10h] BYREF

  v13 = 0;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 2) != 0 && *((_BYTE *)v0 + 25) >= 5u )
      WPP_SF_(v0[2], 37, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
  }
  v1 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Setup", 0, 0x20119u);
  v2 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids, LastError);
    }
    return 0;
  }
  Data = 0;
  RegistryDwordDefault = GetRegistryDwordDefault(v1, L"Installed", (BYTE *)&Data);
  v6 = RegistryDwordDefault != 0 ? Data : 0;
  RegCloseKey(v2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v7 = &qword_1800435E8;
    if ( !v6 )
      v7 = L" not";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids, v7);
  }
  if ( !v6 )
    return 0;
  v8 = IsLocalFaxPrinterInstalled(&v13);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v8);
    }
    v9 = 0;
  }
  else
  {
    v9 = v13;
  }
  if ( v9 )
    return 0;
  v10 = AddLocalFaxPrinter();
  v11 = v10;
  if ( v10
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v10);
  }
  return v11;
}

```

## disassembly

```asm
0x18002f7b0  mov     [rsp+arg_10], rbx
0x18002f7b5  mov     [rsp+arg_18], rbp
0x18002f7ba  push    rdi
0x18002f7bb  sub     rsp, 20h
0x18002f7bf  mov     [rsp+28h+arg_8], 0
0x18002f7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7ce  lea     rbp, WPP_GLOBAL_Control
0x18002f7d5  cmp     rcx, rbp
0x18002f7d8  jz      short loc_18002F828
0x18002f7da  test    byte ptr [rcx+1Ch], 2
0x18002f7de  jz      short loc_18002F802
0x18002f7e0  cmp     byte ptr [rcx+19h], 5
0x18002f7e4  jb      short loc_18002F802
0x18002f7e6  mov     rcx, [rcx+10h]
0x18002f7ea  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18002f7f1  mov     edx, 3Ch ; '<'
0x18002f7f6  call    WPP_SF_
0x18002f7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f802  cmp     rcx, rbp
0x18002f805  jz      short loc_18002F828
0x18002f807  test    byte ptr [rcx+1Ch], 2
0x18002f80b  jz      short loc_18002F828
0x18002f80d  cmp     byte ptr [rcx+19h], 5
0x18002f811  jb      short loc_18002F828
0x18002f813  mov     rcx, [rcx+10h]
0x18002f817  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x18002f81e  mov     edx, 25h ; '%'
0x18002f823  call    WPP_SF_
0x18002f828  mov     r9d, 20119h
0x18002f82e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Fax\\Setup"
0x18002f835  xor     r8d, r8d
0x18002f838  mov     rcx, 0FFFFFFFF80000002h
0x18002f83f  call    OpenRegistryKey
0x18002f844  mov     rdi, rax
0x18002f847  test    rax, rax
0x18002f84a  jnz     short loc_18002F899
0x18002f84c  call    cs:__imp_GetLastError
0x18002f853  nop     dword ptr [rax+rax+00h]
0x18002f858  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f85f  cmp     rcx, rbp
0x18002f862  jz      short loc_18002F886
0x18002f864  test    byte ptr [rcx+1Ch], 2
0x18002f868  jz      short loc_18002F886
0x18002f86a  cmp     byte ptr [rcx+19h], 2
0x18002f86e  jb      short loc_18002F886
0x18002f870  mov     rcx, [rcx+10h]
0x18002f874  lea     edx, [rdi+26h]
0x18002f877  mov     r9d, eax
0x18002f87a  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x18002f881  call    WPP_SF_d
0x18002f886  xor     eax, eax
0x18002f888  mov     rbx, [rsp+28h+arg_10]
0x18002f88d  mov     rbp, [rsp+28h+arg_18]
0x18002f892  add     rsp, 20h
0x18002f896  pop     rdi
0x18002f897  retn
0x18002f899  lea     r8, [rsp+28h+Data]; lpData
0x18002f89e  mov     [rsp+28h+Data], 0
0x18002f8a6  lea     rdx, aInstalled; "Installed"
0x18002f8ad  mov     rcx, rdi; hKey
0x18002f8b0  call    GetRegistryDwordDefault
0x18002f8b5  neg     eax
0x18002f8b7  mov     rcx, rdi; hKey
0x18002f8ba  sbb     ebx, ebx
0x18002f8bc  and     ebx, [rsp+28h+Data]
0x18002f8c0  call    cs:__imp_RegCloseKey
0x18002f8c7  nop     dword ptr [rax+rax+00h]
0x18002f8cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8d3  cmp     rcx, rbp
0x18002f8d6  jz      short loc_18002F90D
0x18002f8d8  test    byte ptr [rcx+1Ch], 2
0x18002f8dc  jz      short loc_18002F90D
0x18002f8de  cmp     byte ptr [rcx+19h], 5
0x18002f8e2  jb      short loc_18002F90D
0x18002f8e4  mov     rcx, [rcx+10h]
0x18002f8e8  lea     rax, aNot; " not"
0x18002f8ef  test    ebx, ebx
0x18002f8f1  lea     r9, qword_1800435E8
0x18002f8f8  mov     edx, 27h ; '''
0x18002f8fd  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x18002f904  cmovz   r9, rax
0x18002f908  call    WPP_SF_S
0x18002f90d  test    ebx, ebx
0x18002f90f  jz      loc_18002F886
0x18002f915  lea     rcx, [rsp+28h+arg_8]
0x18002f91a  call    IsLocalFaxPrinterInstalled
0x18002f91f  test    eax, eax
0x18002f921  jz      short loc_18002F957
0x18002f923  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f92a  cmp     rcx, rbp
0x18002f92d  jz      short loc_18002F953
0x18002f92f  test    byte ptr [rcx+1Ch], 2
0x18002f933  jz      short loc_18002F953
0x18002f935  cmp     byte ptr [rcx+19h], 2
0x18002f939  jb      short loc_18002F953
0x18002f93b  mov     rcx, [rcx+10h]
0x18002f93f  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18002f946  mov     edx, 3Dh ; '='
0x18002f94b  mov     r9d, eax
0x18002f94e  call    WPP_SF_d
0x18002f953  xor     eax, eax
0x18002f955  jmp     short loc_18002F95B
0x18002f957  mov     eax, [rsp+28h+arg_8]
0x18002f95b  test    eax, eax
0x18002f95d  jnz     loc_18002F886
0x18002f963  call    AddLocalFaxPrinter
0x18002f968  mov     ebx, eax
0x18002f96a  test    eax, eax
0x18002f96c  jz      short loc_18002F99E
0x18002f96e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f975  cmp     rcx, rbp
0x18002f978  jz      short loc_18002F99E
0x18002f97a  test    byte ptr [rcx+1Ch], 2
0x18002f97e  jz      short loc_18002F99E
0x18002f980  cmp     byte ptr [rcx+19h], 2
0x18002f984  jb      short loc_18002F99E
0x18002f986  mov     rcx, [rcx+10h]
0x18002f98a  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18002f991  mov     edx, 3Eh ; '>'
0x18002f996  mov     r9d, eax
0x18002f999  call    WPP_SF_d
0x18002f99e  mov     eax, ebx
0x18002f9a0  jmp     loc_18002F888
```

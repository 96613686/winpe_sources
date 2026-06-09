# GetMsiPropertiesFromProcessId

- ea: `0x18003afa4`
- end: `0x18003b188`
- name: `GetMsiPropertiesFromProcessId`
- size: `484`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003a940`

## callees

- `0x180002be0`
- `0x18000f114`
- `0x180015fb0`
- `0x18003afa4`
- `0x18003b190`
- `0x18003ba40`
- `0x180040f40`

## import_xrefs

- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18003b171`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18003b171`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18003b006`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18003b006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b161`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003afcc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003afcc`

## string_xrefs

- `0x18003b072`: `Failed to open the database.`
- `0x18003afda`: `Failed to open child process.`
- `0x18003afe7`: `GetMsiPropertiesFromProcessId`
- `0x18003b01d`: `GetMsiPropertiesFromProcessId`
- `0x18003b0a9`: `GetMsiPropertiesFromProcessId`
- `0x18003b0f3`: `GetMsiPropertiesFromProcessId`
- `0x18003b12a`: `GetMsiPropertiesFromProcessId`
- `0x18003b010`: `Could not read child process data or no data available.`

## pseudocode

```c
__int64 __fastcall GetMsiPropertiesFromProcessId(__int64 a1)
{
  DWORD v1; // r8d
  unsigned int v3; // r14d
  HANDLE v4; // rax
  void *v5; // rbp
  int v6; // ecx
  _WORD *inited; // rax
  _QWORD *v8; // rdi
  int v10; // [rsp+50h] [rbp+8h] BYREF
  char v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v1 = *(_DWORD *)(a1 + 32);
  v3 = 0;
  v12 = 0;
  v10 = 0;
  v4 = OpenProcess(0x1FFFFFu, 0, v1);
  v5 = v4;
  if ( v4 )
  {
    if ( (unsigned int)BaseReadAppCompatDataForProcess(v4, &v12, 0) )
    {
      AslLogCallPrintf(
        1,
        "GetMsiPropertiesFromProcessId",
        1797,
        "Could not read child process data or no data available.");
    }
    else
    {
      v6 = (*(_DWORD *)(v12 + 728) >> 10) & 8 | 0x10;
      if ( (*(_DWORD *)(v12 + 728) & 0x4000) == 0 )
        v6 = (*(_DWORD *)(v12 + 728) >> 10) & 8;
      inited = SdbInitDatabaseEx(v6 | 1u, 0, *(_WORD *)(v12 + 532));
      v8 = inited;
      if ( inited )
      {
        if ( !(unsigned int)GetMsiPropertiesFromQueryResult(inited, v12 + 536, a1) )
          AslLogCallPrintf(1, "GetMsiPropertiesFromProcessId", 1825, "Failed to convert layers into a query result.");
        if ( !(unsigned int)SdbParseLayerString(v8, (const wchar_t *)(v12 + 3396), (_DWORD *)(v12 + 536), &v10) )
          AslLogCallPrintf(1, "GetMsiPropertiesFromProcessId", 1837, "Failed to parse the layer string.", &v11);
        if ( !(unsigned int)GetMsiPropertiesFromQueryResult(v8, v12 + 536, a1) )
          AslLogCallPrintf(1, "GetMsiPropertiesFromProcessId", 1847, "Failed to convert layers into a query result.");
        TraceQueryResultMsi(a1, v8, v12 + 536);
        v3 = 1;
        SdbReleaseDatabase(v8);
      }
      else
      {
        AslLogCallPrintf(1, "GetMsiPropertiesFromProcessId", 1814, "Failed to open the database.");
      }
    }
    CloseHandle(v5);
  }
  else
  {
    AslLogCallPrintf(1, "GetMsiPropertiesFromProcessId", 1790, "Failed to open child process.");
  }
  if ( v12 )
    BaseFreeAppCompatDataForProcess();
  return v3;
}

```

## disassembly

```asm
0x18003afa4  mov     [rsp+arg_18], rbp
0x18003afa9  push    rsi
0x18003afaa  push    rdi
0x18003afab  push    r14
0x18003afad  sub     rsp, 30h
0x18003afb1  mov     r8d, [rcx+20h]; dwProcessId
0x18003afb5  mov     rsi, rcx
0x18003afb8  xor     r14d, r14d
0x18003afbb  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18003afc0  xor     edx, edx; bInheritHandle
0x18003afc2  mov     [rsp+48h+arg_10], r14
0x18003afc7  mov     [rsp+48h+arg_0], r14d
0x18003afcc  call    cs:__imp_OpenProcess
0x18003afd2  mov     rbp, rax
0x18003afd5  test    rax, rax
0x18003afd8  jnz     short loc_18003AFFB
0x18003afda  lea     r9, aFailedToOpenCh; "Failed to open child process."
0x18003afe1  mov     r8d, 6FEh
0x18003afe7  lea     rdx, aGetmsiproperti_0; "GetMsiPropertiesFromProcessId"
0x18003afee  lea     ecx, [rax+1]
0x18003aff1  call    AslLogCallPrintf
0x18003aff6  jmp     loc_18003B167
0x18003affb  xor     r8d, r8d
0x18003affe  lea     rdx, [rsp+48h+arg_10]
0x18003b003  mov     rcx, rbp
0x18003b006  call    cs:__imp_BaseReadAppCompatDataForProcess
0x18003b00c  test    eax, eax
0x18003b00e  jz      short loc_18003B033
0x18003b010  lea     r9, aCouldNotReadCh; "Could not read child process data or no"...
0x18003b017  mov     r8d, 705h
0x18003b01d  lea     rdx, aGetmsiproperti_0; "GetMsiPropertiesFromProcessId"
0x18003b024  mov     ecx, 1
0x18003b029  call    AslLogCallPrintf
0x18003b02e  jmp     loc_18003B15E
0x18003b033  mov     r8, [rsp+48h+arg_10]
0x18003b038  mov     edx, [r8+2D8h]
0x18003b03f  shr     edx, 0Ah
0x18003b042  and     edx, 8
0x18003b045  mov     ecx, edx
0x18003b047  or      ecx, 10h
0x18003b04a  test    dword ptr [r8+2D8h], 4000h
0x18003b055  movzx   r8d, word ptr [r8+214h]
0x18003b05d  cmovz   ecx, edx
0x18003b060  xor     edx, edx
0x18003b062  or      ecx, 1
0x18003b065  call    SdbInitDatabaseEx
0x18003b06a  mov     rdi, rax
0x18003b06d  test    rax, rax
0x18003b070  jnz     short loc_18003B081
0x18003b072  lea     r9, aFailedToOpenTh_1; "Failed to open the database."
0x18003b079  mov     r8d, 716h
0x18003b07f  jmp     short loc_18003B01D
0x18003b081  mov     rdx, [rsp+48h+arg_10]
0x18003b086  mov     r8, rsi
0x18003b089  add     rdx, 218h
0x18003b090  mov     rcx, rdi
0x18003b093  call    GetMsiPropertiesFromQueryResult
0x18003b098  test    eax, eax
0x18003b09a  jnz     short loc_18003B0B8
0x18003b09c  lea     r9, aFailedToConver_29; "Failed to convert layers into a query r"...
0x18003b0a3  mov     r8d, 721h
0x18003b0a9  lea     rdx, aGetmsiproperti_0; "GetMsiPropertiesFromProcessId"
0x18003b0b0  lea     ecx, [rax+1]
0x18003b0b3  call    AslLogCallPrintf
0x18003b0b8  mov     rdx, [rsp+48h+arg_10]
0x18003b0bd  lea     rax, [rsp+48h+arg_8]
0x18003b0c2  lea     r9, [rsp+48h+arg_0]
0x18003b0c7  mov     [rsp+48h+var_28], rax
0x18003b0cc  mov     rcx, rdi
0x18003b0cf  lea     r8, [rdx+218h]
0x18003b0d6  add     rdx, 0D44h
0x18003b0dd  call    SdbParseLayerString
0x18003b0e2  test    eax, eax
0x18003b0e4  jnz     short loc_18003B102
0x18003b0e6  lea     r9, aFailedToParseT; "Failed to parse the layer string."
0x18003b0ed  mov     r8d, 72Dh
0x18003b0f3  lea     rdx, aGetmsiproperti_0; "GetMsiPropertiesFromProcessId"
0x18003b0fa  lea     ecx, [rax+1]
0x18003b0fd  call    AslLogCallPrintf
0x18003b102  mov     rdx, [rsp+48h+arg_10]
0x18003b107  mov     r8, rsi
0x18003b10a  add     rdx, 218h
0x18003b111  mov     rcx, rdi
0x18003b114  call    GetMsiPropertiesFromQueryResult
0x18003b119  test    eax, eax
0x18003b11b  jnz     short loc_18003B139
0x18003b11d  lea     r9, aFailedToConver_29; "Failed to convert layers into a query r"...
0x18003b124  mov     r8d, 737h
0x18003b12a  lea     rdx, aGetmsiproperti_0; "GetMsiPropertiesFromProcessId"
0x18003b131  lea     ecx, [rax+1]
0x18003b134  call    AslLogCallPrintf
0x18003b139  mov     r8, [rsp+48h+arg_10]
0x18003b13e  mov     rdx, rdi
0x18003b141  add     r8, 218h
0x18003b148  mov     rcx, rsi
0x18003b14b  call    TraceQueryResultMsi
0x18003b150  mov     r14d, 1
0x18003b156  mov     rcx, rdi; P
0x18003b159  call    SdbReleaseDatabase
0x18003b15e  mov     rcx, rbp; hObject
0x18003b161  call    cs:__imp_CloseHandle
0x18003b167  mov     rcx, [rsp+48h+arg_10]
0x18003b16c  test    rcx, rcx
0x18003b16f  jz      short loc_18003B177
0x18003b171  call    cs:__imp_BaseFreeAppCompatDataForProcess
0x18003b177  mov     rbp, [rsp+48h+arg_18]
0x18003b17c  mov     eax, r14d
0x18003b17f  add     rsp, 30h
0x18003b183  pop     r14
0x18003b185  pop     rdi
0x18003b186  pop     rsi
0x18003b187  retn
```

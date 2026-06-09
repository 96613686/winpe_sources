# SdbRemovePluginDll

- ea: `0x1800e4254`
- end: `0x1800e448f`
- name: `SdbRemovePluginDll`
- size: `571`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180043424`
- `0x1800e3f84`

## callees

- `0x1800116fc`
- `0x180012920`
- `0x18001cffc`
- `0x18001db24`
- `0x1800353cc`
- `0x180080038`
- `0x1800e40b0`
- `0x1800e4254`
- `0x1800f1f10`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800e430b`
- `ntdll!NtQuerySystemTime` at `0x1800e430b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e439d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e43a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e43b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e443e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e439d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e43a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e43b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e443e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4448`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800e4393`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800e442a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800e4393`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800e442a`

## string_xrefs

- `0x1800e429a`: `SdbGetPluginDll failed [%x]`
- `0x1800e42a7`: `SdbRemovePluginDll`
- `0x1800e43cd`: `SdbRemovePluginDll`
- `0x1800e440e`: `SdbRemovePluginDll`
- `0x1800e43c0`: `Can't move file [%x]`
- `0x1800e4401`: `Failed to fully move file to unique path, swallowing.`

## pseudocode

```c
__int64 __fastcall SdbRemovePluginDll(__int64 a1, __int64 a2)
{
  NTSTATUS PluginDll; // eax
  signed int LastError; // ebx
  const char *v5; // r9
  int v6; // r8d
  const char *v7; // r9
  int v8; // r8d
  NTSTATUS v10; // [rsp+20h] [rbp-E0h]
  signed int v11; // [rsp+20h] [rbp-E0h]
  union _LARGE_INTEGER SystemTime; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[40]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR NewFileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+270h] [rbp+170h] BYREF

  SystemTime.QuadPart = 0;
  PluginDll = SdbGetPluginDll(a1, a2, ExistingFileName);
  LastError = PluginDll;
  if ( PluginDll < 0 )
  {
    v5 = "SdbGetPluginDll failed [%x]";
    v6 = 1858;
LABEL_3:
    v10 = PluginDll;
    AslLogCallPrintf(1, (unsigned int)"SdbRemovePluginDll", v6, (_DWORD)v5, v10);
    return (unsigned int)LastError;
  }
  if ( !(unsigned int)AslDoesFileExistNtPath(ExistingFileName) )
    return 0;
  LastError = RtlStringCchCopyW(NewFileName, 260, ExistingFileName);
  if ( LastError < 0 )
    return (unsigned int)LastError;
  *(_WORD *)AslPathGetFileNamePart(NewFileName) = 0;
  PluginDll = NtQuerySystemTime(&SystemTime);
  LastError = PluginDll;
  if ( PluginDll < 0 )
  {
    v5 = "Can't get current time [%x]";
    v6 = 1883;
    goto LABEL_3;
  }
  LastError = RtlStringCchPrintfW(v13, 18, L"%llx_", SystemTime.QuadPart);
  if ( LastError >= 0 )
  {
    LastError = RtlStringCchCatW(NewFileName, 260, v13);
    if ( LastError >= 0 )
    {
      LastError = RtlStringCchCatW(NewFileName, 260, a1);
      if ( LastError >= 0 )
      {
        if ( !MoveFileExW(ExistingFileName, NewFileName, 2u) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          v7 = "Can't move file [%x]";
          v8 = 1905;
LABEL_16:
          v11 = LastError;
          AslLogCallPrintf(1, (unsigned int)"SdbRemovePluginDll", v8, (_DWORD)v7, v11);
          if ( LastError >= 0 )
            return (unsigned int)-1073741595;
          return (unsigned int)LastError;
        }
        if ( (unsigned int)AslDoesFileExistNtPath(ExistingFileName) )
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbRemovePluginDll",
            1913,
            (unsigned int)"Failed to fully move file to unique path, swallowing.");
        if ( !MoveFileExW(NewFileName, 0, 4u) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          v7 = "Can't register file for deletion on reboot [%x]";
          v8 = 1918;
          goto LABEL_16;
        }
        return 0;
      }
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800e4254  mov     [rsp-8+arg_10], rbx
0x1800e4259  push    rbp
0x1800e425a  push    rsi
0x1800e425b  push    rdi
0x1800e425c  lea     rbp, [rsp-390h]
0x1800e4264  sub     rsp, 490h
0x1800e426b  mov     rax, cs:__security_cookie
0x1800e4272  xor     rax, rsp
0x1800e4275  mov     [rbp+3A0h+var_20], rax
0x1800e427c  lea     r8, [rbp+3A0h+ExistingFileName]
0x1800e4283  mov     qword ptr [rsp+4A0h+SystemTime], 0
0x1800e428c  mov     rdi, rcx
0x1800e428f  call    SdbGetPluginDll
0x1800e4294  mov     ebx, eax
0x1800e4296  test    eax, eax
0x1800e4298  jns     short loc_1800E42C1
0x1800e429a  lea     r9, aSdbgetplugindl; "SdbGetPluginDll failed [%x]"
0x1800e42a1  mov     r8d, 742h
0x1800e42a7  lea     rdx, aSdbremoveplugi; "SdbRemovePluginDll"
0x1800e42ae  mov     [rsp+4A0h+var_480], eax
0x1800e42b2  mov     ecx, 1
0x1800e42b7  call    AslLogCallPrintf
0x1800e42bc  jmp     loc_1800E446B
0x1800e42c1  lea     rcx, [rbp+3A0h+ExistingFileName]; FileName
0x1800e42c8  call    AslDoesFileExistNtPath
0x1800e42cd  test    eax, eax
0x1800e42cf  jz      loc_1800E4469
0x1800e42d5  mov     esi, 104h
0x1800e42da  lea     r8, [rbp+3A0h+ExistingFileName]
0x1800e42e1  mov     edx, esi
0x1800e42e3  lea     rcx, [rsp+4A0h+NewFileName]
0x1800e42e8  call    RtlStringCchCopyW
0x1800e42ed  mov     ebx, eax
0x1800e42ef  test    eax, eax
0x1800e42f1  js      loc_1800E446B
0x1800e42f7  lea     rcx, [rsp+4A0h+NewFileName]
0x1800e42fc  call    AslPathGetFileNamePart
0x1800e4301  xor     ecx, ecx
0x1800e4303  mov     [rax], cx
0x1800e4306  lea     rcx, [rsp+4A0h+SystemTime]; SystemTime
0x1800e430b  call    cs:__imp_NtQuerySystemTime
0x1800e4311  mov     ebx, eax
0x1800e4313  test    eax, eax
0x1800e4315  jns     short loc_1800E4326
0x1800e4317  lea     r9, aCanTGetCurrent; "Can't get current time [%x]"
0x1800e431e  mov     r8d, 75Bh
0x1800e4324  jmp     short loc_1800E42A7
0x1800e4326  mov     r9, qword ptr [rsp+4A0h+SystemTime]
0x1800e432b  lea     r8, aLlx; "%llx_"
0x1800e4332  mov     edx, 12h
0x1800e4337  lea     rcx, [rsp+4A0h+var_468]
0x1800e433c  call    RtlStringCchPrintfW
0x1800e4341  mov     ebx, eax
0x1800e4343  test    eax, eax
0x1800e4345  js      loc_1800E446B
0x1800e434b  lea     r8, [rsp+4A0h+var_468]
0x1800e4350  mov     rdx, rsi
0x1800e4353  lea     rcx, [rsp+4A0h+NewFileName]
0x1800e4358  call    RtlStringCchCatW
0x1800e435d  mov     ebx, eax
0x1800e435f  test    eax, eax
0x1800e4361  js      loc_1800E446B
0x1800e4367  mov     r8, rdi
0x1800e436a  lea     rcx, [rsp+4A0h+NewFileName]
0x1800e436f  mov     rdx, rsi
0x1800e4372  call    RtlStringCchCatW
0x1800e4377  mov     ebx, eax
0x1800e4379  test    eax, eax
0x1800e437b  js      loc_1800E446B
0x1800e4381  mov     r8d, 2; dwFlags
0x1800e4387  lea     rdx, [rsp+4A0h+NewFileName]; lpNewFileName
0x1800e438c  lea     rcx, [rbp+3A0h+ExistingFileName]; lpExistingFileName
0x1800e4393  call    cs:__imp_MoveFileExW
0x1800e4399  test    eax, eax
0x1800e439b  jnz     short loc_1800E43F1
0x1800e439d  call    cs:__imp_GetLastError
0x1800e43a3  test    eax, eax
0x1800e43a5  jg      short loc_1800E43B1
0x1800e43a7  call    cs:__imp_GetLastError
0x1800e43ad  mov     ebx, eax
0x1800e43af  jmp     short loc_1800E43C0
0x1800e43b1  call    cs:__imp_GetLastError
0x1800e43b7  movzx   ebx, ax
0x1800e43ba  or      ebx, 0C0070000h
0x1800e43c0  lea     r9, aCanTMoveFileX; "Can't move file [%x]"
0x1800e43c7  mov     r8d, 771h
0x1800e43cd  lea     rdx, aSdbremoveplugi; "SdbRemovePluginDll"
0x1800e43d4  mov     [rsp+4A0h+var_480], ebx
0x1800e43d8  mov     ecx, 1
0x1800e43dd  call    AslLogCallPrintf
0x1800e43e2  test    ebx, ebx
0x1800e43e4  js      loc_1800E446B
0x1800e43ea  mov     ebx, 0C00000E5h
0x1800e43ef  jmp     short loc_1800E446B
0x1800e43f1  lea     rcx, [rbp+3A0h+ExistingFileName]; FileName
0x1800e43f8  call    AslDoesFileExistNtPath
0x1800e43fd  test    eax, eax
0x1800e43ff  jz      short loc_1800E441F
0x1800e4401  lea     r9, aFailedToFullyM; "Failed to fully move file to unique pat"...
0x1800e4408  mov     r8d, 779h
0x1800e440e  lea     rdx, aSdbremoveplugi; "SdbRemovePluginDll"
0x1800e4415  mov     ecx, 1
0x1800e441a  call    AslLogCallPrintf
0x1800e441f  xor     edx, edx; lpNewFileName
0x1800e4421  lea     rcx, [rsp+4A0h+NewFileName]; lpExistingFileName
0x1800e4426  lea     r8d, [rdx+4]; dwFlags
0x1800e442a  call    cs:__imp_MoveFileExW
0x1800e4430  test    eax, eax
0x1800e4432  jnz     short loc_1800E4469
0x1800e4434  call    cs:__imp_GetLastError
0x1800e443a  test    eax, eax
0x1800e443c  jg      short loc_1800E4448
0x1800e443e  call    cs:__imp_GetLastError
0x1800e4444  mov     ebx, eax
0x1800e4446  jmp     short loc_1800E4457
0x1800e4448  call    cs:__imp_GetLastError
0x1800e444e  movzx   ebx, ax
0x1800e4451  or      ebx, 0C0070000h
0x1800e4457  lea     r9, aCanTRegisterFi; "Can't register file for deletion on reb"...
0x1800e445e  mov     r8d, 77Eh
0x1800e4464  jmp     loc_1800E43CD
0x1800e4469  xor     ebx, ebx
0x1800e446b  mov     eax, ebx
0x1800e446d  mov     rcx, [rbp+3A0h+var_20]
0x1800e4474  xor     rcx, rsp; StackCookie
0x1800e4477  call    __security_check_cookie
0x1800e447c  mov     rbx, [rsp+4A0h+arg_10]
0x1800e4484  add     rsp, 490h
0x1800e448b  pop     rdi
0x1800e448c  pop     rsi
0x1800e448d  pop     rbp
0x1800e448e  retn
```

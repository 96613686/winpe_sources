# SdbIsExeTaggedForReinstallUpgrade

- ea: `0x180049ed0`
- end: `0x180049fef`
- name: `SdbIsExeTaggedForReinstallUpgrade`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000f114`
- `0x1800159e0`
- `0x180049ed0`
- `0x1800591b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049fa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049fa1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049f68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f74`

## string_xrefs

- `0x180049f0a`: `Microsoft_Appcompat_ReinstallUpgrade`
- `0x180049f87`: `SdbIsExeTaggedForReinstallUpgrade`
- `0x180049fbb`: `SdbIsExeTaggedForReinstallUpgrade`
- `0x180049f7a`: `Failed to open stream [%d]`

## pseudocode

```c
__int64 __fastcall SdbIsExeTaggedForReinstallUpgrade(_WORD *a1)
{
  unsigned int v1; // ebx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  FileName[0] = 0;
  v1 = 0;
  if ( a1 && *a1 )
  {
    if ( (int)RtlStringCchPrintfW(FileName, 260, L"%s:%s", a1, L"Microsoft_Appcompat_ReinstallUpgrade") >= 0 )
    {
      FileW = CreateFileW(FileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        AslLogCallPrintf(1, "SdbIsExeTaggedForReinstallUpgrade", 926, "Failed to open stream [%d]", LastError);
      }
      else
      {
        CloseHandle(FileW);
        return 1;
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbIsExeTaggedForReinstallUpgrade", 914, "Failed to append stream suffix");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbIsExeTaggedForReinstallUpgrade", 901, "Invalid parameter");
  }
  return v1;
}

```

## disassembly

```asm
0x180049ed0  mov     [rsp+arg_8], rbx
0x180049ed5  push    rdi
0x180049ed6  sub     rsp, 260h
0x180049edd  mov     rax, cs:__security_cookie
0x180049ee4  xor     rax, rsp
0x180049ee7  mov     [rsp+268h+var_18], rax
0x180049eef  xor     edi, edi
0x180049ef1  mov     [rsp+268h+FileName], di
0x180049ef6  mov     ebx, edi
0x180049ef8  test    rcx, rcx
0x180049efb  jz      loc_180049FAE
0x180049f01  cmp     [rcx], di
0x180049f04  jz      loc_180049FAE
0x180049f0a  lea     rax, aMicrosoftAppco; "Microsoft_Appcompat_ReinstallUpgrade"
0x180049f11  mov     r9, rcx
0x180049f14  lea     rcx, [rsp+268h+FileName]
0x180049f19  mov     qword ptr [rsp+268h+dwCreationDisposition], rax
0x180049f1e  lea     r8, aSS_1; "%s:%s"
0x180049f25  mov     edx, 104h
0x180049f2a  call    RtlStringCchPrintfW
0x180049f2f  test    eax, eax
0x180049f31  jns     short loc_180049F42
0x180049f33  lea     r9, aFailedToAppend_2; "Failed to append stream suffix"
0x180049f3a  mov     r8d, 392h
0x180049f40  jmp     short loc_180049FBB
0x180049f42  xor     r9d, r9d; lpSecurityAttributes
0x180049f45  mov     [rsp+268h+hTemplateFile], rdi; hTemplateFile
0x180049f4a  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180049f52  lea     rcx, [rsp+268h+FileName]; lpFileName
0x180049f57  mov     edx, 80000000h; dwDesiredAccess
0x180049f5c  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x180049f64  lea     r8d, [r9+7]; dwShareMode
0x180049f68  call    cs:__imp_CreateFileW
0x180049f6e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049f72  jnz     short loc_180049F9E
0x180049f74  call    cs:__imp_GetLastError
0x180049f7a  lea     r9, aFailedToOpenSt; "Failed to open stream [%d]"
0x180049f81  mov     r8d, 39Eh
0x180049f87  lea     rdx, aSdbisexetagged; "SdbIsExeTaggedForReinstallUpgrade"
0x180049f8e  mov     [rsp+268h+dwCreationDisposition], eax
0x180049f92  mov     ecx, 1
0x180049f97  call    AslLogCallPrintf
0x180049f9c  jmp     short loc_180049FCC
0x180049f9e  mov     rcx, rax; hObject
0x180049fa1  call    cs:__imp_CloseHandle
0x180049fa7  mov     ebx, 1
0x180049fac  jmp     short loc_180049FCC
0x180049fae  lea     r9, aInvalidParamet_1; "Invalid parameter"
0x180049fb5  mov     r8d, 385h
0x180049fbb  lea     rdx, aSdbisexetagged; "SdbIsExeTaggedForReinstallUpgrade"
0x180049fc2  mov     ecx, 1
0x180049fc7  call    AslLogCallPrintf
0x180049fcc  mov     eax, ebx
0x180049fce  mov     rcx, [rsp+268h+var_18]
0x180049fd6  xor     rcx, rsp; StackCookie
0x180049fd9  call    __security_check_cookie
0x180049fde  mov     rbx, [rsp+268h+arg_8]
0x180049fe6  add     rsp, 260h
0x180049fed  pop     rdi
0x180049fee  retn
```

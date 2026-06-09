# SdbTagExeForReinstallUpgrade

- ea: `0x18004a620`
- end: `0x18004a76f`
- name: `SdbTagExeForReinstallUpgrade`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f114`
- `0x1800159e0`
- `0x18004a620`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x18004a662`
- `ntdll!RtlDoesFileExists_U` at `0x18004a662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a71d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a71d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a6f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a6fe`

## string_xrefs

- `0x18004a67e`: `SdbTagExeForReinstallUpgrade`
- `0x18004a737`: `SdbTagExeForReinstallUpgrade`
- `0x18004a671`: `Failed to create stream as the file was not found '%S'`
- `0x18004a694`: `Microsoft_Appcompat_ReinstallUpgrade`
- `0x18004a708`: `Failed to create stream [%d]`

## pseudocode

```c
__int64 __fastcall SdbTagExeForReinstallUpgrade(const WCHAR *a1)
{
  unsigned int v2; // edi
  HANDLE FileW; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-248h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  FileName[0] = 0;
  v2 = 0;
  if ( a1 && *a1 )
  {
    if ( RtlDoesFileExists_U(a1) )
    {
      if ( (int)RtlStringCchPrintfW(FileName, 260, L"%s:%s", a1, L"Microsoft_Appcompat_ReinstallUpgrade") >= 0 )
      {
        FileW = CreateFileW(FileName, 0x40000000u, 7u, 0, 2u, 0x80u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          dwCreationDisposition[0] = GetLastError();
          AslLogCallPrintf(
            1,
            "SdbTagExeForReinstallUpgrade",
            165,
            "Failed to create stream [%d]",
            *(_QWORD *)dwCreationDisposition);
        }
        else
        {
          CloseHandle(FileW);
          return 1;
        }
      }
      else
      {
        AslLogCallPrintf(1, "SdbTagExeForReinstallUpgrade", 149, "Failed to append stream suffix");
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        "SdbTagExeForReinstallUpgrade",
        136,
        "Failed to create stream as the file was not found '%S'",
        a1);
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbTagExeForReinstallUpgrade", 125, "Invalid parameter");
  }
  return v2;
}

```

## disassembly

```asm
0x18004a620  mov     [rsp+arg_8], rbx
0x18004a625  mov     [rsp+arg_10], rsi
0x18004a62a  push    rdi
0x18004a62b  sub     rsp, 260h
0x18004a632  mov     rax, cs:__security_cookie
0x18004a639  xor     rax, rsp
0x18004a63c  mov     [rsp+268h+var_18], rax
0x18004a644  xor     esi, esi
0x18004a646  mov     rbx, rcx
0x18004a649  mov     [rsp+268h+FileName], si
0x18004a64e  mov     edi, esi
0x18004a650  test    rcx, rcx
0x18004a653  jz      loc_18004A72A
0x18004a659  cmp     [rcx], si
0x18004a65c  jz      loc_18004A72A
0x18004a662  call    cs:__imp_RtlDoesFileExists_U
0x18004a668  test    al, al
0x18004a66a  jnz     short loc_18004A694
0x18004a66c  mov     qword ptr [rsp+268h+dwCreationDisposition], rbx
0x18004a671  lea     r9, aFailedToCreate_17; "Failed to create stream as the file was"...
0x18004a678  mov     r8d, 88h
0x18004a67e  lea     rdx, aSdbtagexeforre; "SdbTagExeForReinstallUpgrade"
0x18004a685  mov     ecx, 1
0x18004a68a  call    AslLogCallPrintf
0x18004a68f  jmp     loc_18004A748
0x18004a694  lea     rax, aMicrosoftAppco; "Microsoft_Appcompat_ReinstallUpgrade"
0x18004a69b  mov     r9, rbx
0x18004a69e  lea     r8, aSS_1; "%s:%s"
0x18004a6a5  mov     qword ptr [rsp+268h+dwCreationDisposition], rax
0x18004a6aa  mov     edx, 104h
0x18004a6af  lea     rcx, [rsp+268h+FileName]
0x18004a6b4  call    RtlStringCchPrintfW
0x18004a6b9  test    eax, eax
0x18004a6bb  jns     short loc_18004A6CC
0x18004a6bd  lea     r9, aFailedToAppend_2; "Failed to append stream suffix"
0x18004a6c4  mov     r8d, 95h
0x18004a6ca  jmp     short loc_18004A737
0x18004a6cc  xor     r9d, r9d; lpSecurityAttributes
0x18004a6cf  mov     [rsp+268h+hTemplateFile], rsi; hTemplateFile
0x18004a6d4  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004a6dc  lea     rcx, [rsp+268h+FileName]; lpFileName
0x18004a6e1  mov     edx, 40000000h; dwDesiredAccess
0x18004a6e6  mov     [rsp+268h+dwCreationDisposition], 2; dwCreationDisposition
0x18004a6ee  lea     r8d, [r9+7]; dwShareMode
0x18004a6f2  call    cs:__imp_CreateFileW
0x18004a6f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a6fc  jnz     short loc_18004A71A
0x18004a6fe  call    cs:__imp_GetLastError
0x18004a704  mov     [rsp+268h+dwCreationDisposition], eax
0x18004a708  lea     r9, aFailedToCreate_13; "Failed to create stream [%d]"
0x18004a70f  mov     r8d, 0A5h
0x18004a715  jmp     loc_18004A67E
0x18004a71a  mov     rcx, rax; hObject
0x18004a71d  call    cs:__imp_CloseHandle
0x18004a723  mov     edi, 1
0x18004a728  jmp     short loc_18004A748
0x18004a72a  lea     r9, aInvalidParamet_1; "Invalid parameter"
0x18004a731  mov     r8d, 7Dh ; '}'
0x18004a737  lea     rdx, aSdbtagexeforre; "SdbTagExeForReinstallUpgrade"
0x18004a73e  mov     ecx, 1
0x18004a743  call    AslLogCallPrintf
0x18004a748  mov     eax, edi
0x18004a74a  mov     rcx, [rsp+268h+var_18]
0x18004a752  xor     rcx, rsp; StackCookie
0x18004a755  call    __security_check_cookie
0x18004a75a  lea     r11, [rsp+268h+var_8]
0x18004a762  mov     rbx, [r11+18h]
0x18004a766  mov     rsi, [r11+20h]
0x18004a76a  mov     rsp, r11
0x18004a76d  pop     rdi
0x18004a76e  retn
```

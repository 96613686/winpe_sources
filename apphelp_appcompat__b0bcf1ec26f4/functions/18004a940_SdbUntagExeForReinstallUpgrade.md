# SdbUntagExeForReinstallUpgrade

- ea: `0x18004a940`
- end: `0x18004aa3e`
- name: `SdbUntagExeForReinstallUpgrade`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000f114`
- `0x1800159e0`
- `0x18004a940`
- `0x180059270`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004a9b7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004a9b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9d3`

## string_xrefs

- `0x18004a97a`: `Microsoft_Appcompat_ReinstallUpgrade`
- `0x18004a9e6`: `SdbUntagExeForReinstallUpgrade`
- `0x18004aa0a`: `SdbUntagExeForReinstallUpgrade`
- `0x18004a9d9`: `Failed to delete stream [%d]`

## pseudocode

```c
__int64 __fastcall SdbUntagExeForReinstallUpgrade(_WORD *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  FileName[0] = 0;
  v1 = 0;
  if ( a1 && *a1 )
  {
    if ( (int)RtlStringCchPrintfW(FileName, 260, L"%s:%s", a1, L"Microsoft_Appcompat_ReinstallUpgrade") >= 0 )
    {
      if ( DeleteFileW(FileName) || GetLastError() == 2 )
      {
        return 1;
      }
      else
      {
        LastError = GetLastError();
        AslLogCallPrintf(1, "SdbUntagExeForReinstallUpgrade", 845, "Failed to delete stream [%d]", LastError);
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbUntagExeForReinstallUpgrade", 827, "Failed to append stream suffix");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbUntagExeForReinstallUpgrade", 814, "Invalid parameter");
  }
  return v1;
}

```

## disassembly

```asm
0x18004a940  mov     [rsp+arg_8], rbx
0x18004a945  push    rdi
0x18004a946  sub     rsp, 250h
0x18004a94d  mov     rax, cs:__security_cookie
0x18004a954  xor     rax, rsp
0x18004a957  mov     [rsp+258h+var_18], rax
0x18004a95f  xor     edi, edi
0x18004a961  mov     [rsp+258h+FileName], di
0x18004a966  mov     ebx, edi
0x18004a968  test    rcx, rcx
0x18004a96b  jz      loc_18004A9FD
0x18004a971  cmp     [rcx], di
0x18004a974  jz      loc_18004A9FD
0x18004a97a  lea     rax, aMicrosoftAppco; "Microsoft_Appcompat_ReinstallUpgrade"
0x18004a981  mov     r9, rcx
0x18004a984  lea     rcx, [rsp+258h+FileName]
0x18004a989  mov     [rsp+258h+var_238], rax
0x18004a98e  lea     r8, aSS_1; "%s:%s"
0x18004a995  mov     edx, 104h
0x18004a99a  call    RtlStringCchPrintfW
0x18004a99f  test    eax, eax
0x18004a9a1  jns     short loc_18004A9B2
0x18004a9a3  lea     r9, aFailedToAppend_2; "Failed to append stream suffix"
0x18004a9aa  mov     r8d, 33Bh
0x18004a9b0  jmp     short loc_18004AA0A
0x18004a9b2  lea     rcx, [rsp+258h+FileName]; lpFileName
0x18004a9b7  call    cs:__imp_DeleteFileW
0x18004a9bd  test    eax, eax
0x18004a9bf  jnz     short loc_18004A9CC
0x18004a9c1  call    cs:__imp_GetLastError
0x18004a9c7  cmp     eax, 2
0x18004a9ca  jnz     short loc_18004A9D3
0x18004a9cc  mov     ebx, 1
0x18004a9d1  jmp     short loc_18004AA1B
0x18004a9d3  call    cs:__imp_GetLastError
0x18004a9d9  lea     r9, aFailedToDelete_1; "Failed to delete stream [%d]"
0x18004a9e0  mov     r8d, 34Dh
0x18004a9e6  lea     rdx, aSdbuntagexefor; "SdbUntagExeForReinstallUpgrade"
0x18004a9ed  mov     dword ptr [rsp+258h+var_238], eax
0x18004a9f1  mov     ecx, 1
0x18004a9f6  call    AslLogCallPrintf
0x18004a9fb  jmp     short loc_18004AA1B
0x18004a9fd  lea     r9, aInvalidParamet_1; "Invalid parameter"
0x18004aa04  mov     r8d, 32Eh
0x18004aa0a  lea     rdx, aSdbuntagexefor; "SdbUntagExeForReinstallUpgrade"
0x18004aa11  mov     ecx, 1
0x18004aa16  call    AslLogCallPrintf
0x18004aa1b  mov     eax, ebx
0x18004aa1d  mov     rcx, [rsp+258h+var_18]
0x18004aa25  xor     rcx, rsp; StackCookie
0x18004aa28  call    __security_check_cookie
0x18004aa2d  mov     rbx, [rsp+258h+arg_8]
0x18004aa35  add     rsp, 250h
0x18004aa3c  pop     rdi
0x18004aa3d  retn
```

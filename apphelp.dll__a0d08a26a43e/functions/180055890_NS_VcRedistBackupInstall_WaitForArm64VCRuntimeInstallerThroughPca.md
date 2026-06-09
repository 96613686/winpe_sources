# NS_VcRedistBackupInstall::WaitForArm64VCRuntimeInstallerThroughPca

- ea: `0x180055890`
- end: `0x180055954`
- name: `NS_VcRedistBackupInstall::WaitForArm64VCRuntimeInstallerThroughPca`
- size: `196`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x180055840`
- `0x1800559a0`

## callees

- `0x18000f114`
- `0x18003c2d0`
- `0x180055890`
- `0x1800591b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180055920`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180055920`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800558bf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800558bf`

## string_xrefs

- `0x1800558d5`: `Failed to create and expand vc runtime path (%d)`
- `0x1800558b8`: `%SYSTEMROOT%\System32\vcruntime140.dll`
- `0x1800558fc`: `Buffer too small for vc runtime path`
- `0x1800558dc`: `NS_VcRedistBackupInstall::WaitForArm64VCRuntimeInstallerThroughPca`
- `0x180055903`: `NS_VcRedistBackupInstall::WaitForArm64VCRuntimeInstallerThroughPca`

## pseudocode

```c
__int64 (__fastcall *NS_VcRedistBackupInstall::WaitForArm64VCRuntimeInstallerThroughPca())(_QWORD)
{
  DWORD v0; // eax
  DWORD LastError; // eax
  __int64 (__fastcall *result)(_QWORD); // rax
  unsigned int i; // ebx
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  v0 = ExpandEnvironmentStringsW(L"%SYSTEMROOT%\\System32\\vcruntime140.dll", Dst, 0x104u);
  if ( v0 )
  {
    if ( v0 <= 0x104 )
    {
      for ( i = 0; i < 0x78; ++i )
      {
        if ( i )
          Sleep(0x3E8u);
        result = (__int64 (__fastcall *)(_QWORD))AslDoesFileExistNtPath(Dst);
        if ( (_DWORD)result )
          break;
      }
    }
    else
    {
      return AslLogCallPrintf(
               1,
               "NS_VcRedistBackupInstall::WaitForArm64VCRuntimeInstallerThroughPca",
               70,
               "Buffer too small for vc runtime path");
    }
  }
  else
  {
    LastError = GetLastError();
    return AslLogCallPrintf(
             1,
             "NS_VcRedistBackupInstall::WaitForArm64VCRuntimeInstallerThroughPca",
             65,
             "Failed to create and expand vc runtime path (%d)",
             LastError);
  }
  return result;
}

```

## disassembly

```asm
0x180055890  push    rbx
0x180055892  sub     rsp, 250h
0x180055899  mov     rax, cs:__security_cookie
0x1800558a0  xor     rax, rsp
0x1800558a3  mov     [rsp+258h+var_18], rax
0x1800558ab  mov     ebx, 104h
0x1800558b0  lea     rdx, [rsp+258h+Dst]; lpDst
0x1800558b5  mov     r8d, ebx; nSize
0x1800558b8  lea     rcx, aSystemrootSyst_0; "%SYSTEMROOT%\\System32\\vcruntime140.dl"...
0x1800558bf  call    cs:__imp_ExpandEnvironmentStringsW
0x1800558c5  test    eax, eax
0x1800558c7  jnz     short loc_1800558F2
0x1800558c9  call    cs:__imp_GetLastError
0x1800558cf  mov     r8d, 41h ; 'A'
0x1800558d5  lea     r9, aFailedToCreate_4; "Failed to create and expand vc runtime "...
0x1800558dc  lea     rdx, aNsVcredistback; "NS_VcRedistBackupInstall::WaitForArm64V"...
0x1800558e3  mov     [rsp+258h+var_238], eax
0x1800558e7  lea     ecx, [r8-40h]
0x1800558eb  call    AslLogCallPrintf
0x1800558f0  jmp     short loc_18005593B
0x1800558f2  cmp     eax, ebx
0x1800558f4  jbe     short loc_180055915
0x1800558f6  mov     r8d, 46h ; 'F'
0x1800558fc  lea     r9, aBufferTooSmall_0; "Buffer too small for vc runtime path"
0x180055903  lea     rdx, aNsVcredistback; "NS_VcRedistBackupInstall::WaitForArm64V"...
0x18005590a  lea     ecx, [r8-45h]
0x18005590e  call    AslLogCallPrintf
0x180055913  jmp     short loc_18005593B
0x180055915  xor     ebx, ebx
0x180055917  test    ebx, ebx
0x180055919  jz      short loc_180055926
0x18005591b  mov     ecx, 3E8h; dwMilliseconds
0x180055920  call    cs:__imp_Sleep
0x180055926  lea     rcx, [rsp+258h+Dst]; FileName
0x18005592b  call    AslDoesFileExistNtPath
0x180055930  test    eax, eax
0x180055932  jnz     short loc_18005593B
0x180055934  inc     ebx
0x180055936  cmp     ebx, 78h ; 'x'
0x180055939  jb      short loc_180055917
0x18005593b  mov     rcx, [rsp+258h+var_18]
0x180055943  xor     rcx, rsp; StackCookie
0x180055946  call    __security_check_cookie
0x18005594b  add     rsp, 250h
0x180055952  pop     rbx
0x180055953  retn
```

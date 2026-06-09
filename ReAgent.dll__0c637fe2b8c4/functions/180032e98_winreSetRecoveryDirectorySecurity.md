# winreSetRecoveryDirectorySecurity

- ea: `0x180032e98`
- end: `0x180033076`
- name: `winreSetRecoveryDirectorySecurity`
- size: `478`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180024800`

## callees

- `0x1800059fc`
- `0x180032e98`
- `0x18004f2ac`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032f1a`
- `KERNEL32!GetLastError` at `0x180032f8d`
- `KERNEL32!GetLastError` at `0x180033017`
- `KERNEL32!GetLastError` at `0x180032f1a`
- `KERNEL32!GetLastError` at `0x180032f8d`
- `KERNEL32!GetLastError` at `0x180033017`
- `KERNEL32!GetFileAttributesW` at `0x180032f5f`
- `KERNEL32!GetFileAttributesW` at `0x180032f5f`
- `KERNEL32!SetFileAttributesW` at `0x18003300d`
- `KERNEL32!SetFileAttributesW` at `0x18003300d`
- `KERNEL32!CreateDirectoryW` at `0x180032f83`
- `KERNEL32!CreateDirectoryW` at `0x180032f83`
- `KERNEL32!GetWindowsDirectoryW` at `0x180032f10`
- `KERNEL32!GetWindowsDirectoryW` at `0x180032f10`

## string_xrefs

- `0x180032f20`: `winreSetRecoveryDirectorySecurity: Failed to get windows dir: 0x%x`
- `0x180032f47`: `winreSetRecoveryDirectorySecurity: Checking for recovery dir [%s]`
- `0x180032f70`: `winreSetRecoveryDirectorySecurity: Recovery dir did not exist, creating with secure ACL`
- `0x180032fa0`: `winreSetRecoveryDirectorySecurity: Failed to create [%s]: 0x%x`
- `0x180032fb5`: `winreSetRecoveryDirectorySecurity: Created [%s] successfully`
- `0x180032fdb`: `winreSetRecoveryDirectorySecurity: Failed to set permissions on [%s] to [%s]: 0x%x`
- `0x180032ff5`: `winreSetRecoveryDirectorySecurity: Set [%s] permissions to [%s]`
- `0x18003302a`: `winreSetRecoveryDirectorySecurity: Failed to mark [%s] as hidden: 0x%x`
- `0x18003303f`: `winreSetRecoveryDirectorySecurity: Successfully made [%s] hidden`
- `0x18003304d`: `winreSetRecoveryDirectorySecurity: Recovery dir already exists, nothing to do`

## pseudocode

```c
__int64 winreSetRecoveryDirectorySecurity()
{
  DWORD LastError; // eax
  DWORD v2; // eax
  const unsigned __int16 *v3; // rdx
  int v4; // r8d
  unsigned int v5; // eax
  DWORD v6; // eax
  unsigned int v7; // [rsp+20h] [rbp-E0h]
  WCHAR FileName[12]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[504]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp+140h] BYREF

  wcscpy(FileName, L"?:\\Recoery");
  memset_0(v9, 0, 0x1F2u);
  memset_0(Buffer, 0, 0x20Au);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    UnattendLogW(1, L"winreSetRecoveryDirectorySecurity: Failed to get windows dir: 0x%x", LastError);
    return 0;
  }
  FileName[0] = Buffer[0];
  UnattendLogW(0, L"winreSetRecoveryDirectorySecurity: Checking for recovery dir [%s]", FileName);
  if ( GetFileAttributesW(FileName) == -1 )
  {
    UnattendLogW(0, L"winreSetRecoveryDirectorySecurity: Recovery dir did not exist, creating with secure ACL");
    if ( !CreateDirectoryW(FileName, 0) )
    {
      v2 = GetLastError();
      UnattendLogW(1, L"winreSetRecoveryDirectorySecurity: Failed to create [%s]: 0x%x", FileName, v2);
      return 0;
    }
    UnattendLogW(0, L"winreSetRecoveryDirectorySecurity: Created [%s] successfully", FileName);
    v5 = Utils::SetFileSddl(FileName, v3, v4);
    if ( v5 )
    {
      v7 = v5;
      UnattendLogW(
        1,
        L"winreSetRecoveryDirectorySecurity: Failed to set permissions on [%s] to [%s]: 0x%x",
        FileName,
        L"O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GRGX;;;AU)(A;CIOI;GRGX;;;BU)",
        v7);
      return 0;
    }
    UnattendLogW(
      0,
      L"winreSetRecoveryDirectorySecurity: Set [%s] permissions to [%s]",
      FileName,
      L"O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GRGX;;;AU)(A;CIOI;GRGX;;;BU)");
    if ( SetFileAttributesW(FileName, 0x2006u) )
    {
      UnattendLogW(0, L"winreSetRecoveryDirectorySecurity: Successfully made [%s] hidden", FileName);
    }
    else
    {
      v6 = GetLastError();
      UnattendLogW(1, L"winreSetRecoveryDirectorySecurity: Failed to mark [%s] as hidden: 0x%x", FileName, v6);
    }
  }
  else
  {
    UnattendLogW(0, L"winreSetRecoveryDirectorySecurity: Recovery dir already exists, nothing to do");
  }
  return 1;
}

```

## disassembly

```asm
0x180032e98  push    rbp
0x180032e9a  lea     rbp, [rsp-360h]
0x180032ea2  sub     rsp, 460h
0x180032ea9  mov     rax, cs:__security_cookie
0x180032eb0  xor     rax, rsp
0x180032eb3  mov     [rbp+360h+var_10], rax
0x180032eba  movups  xmm0, xmmword ptr cs:aRecovery_0+2; ":\\Recovery"
0x180032ec1  lea     rcx, [rsp+460h+var_418]; void *
0x180032ec6  mov     eax, 3Fh ; '?'
0x180032ecb  movsd   xmm1, qword ptr cs:aRecovery_0+10h; "ery"
0x180032ed3  xor     edx, edx; Val
0x180032ed5  movups  [rsp+460h+var_42E], xmm0
0x180032eda  mov     r8d, 1F2h; Size
0x180032ee0  mov     [rsp+460h+FileName], ax
0x180032ee5  movsd   qword ptr [rsp+460h+var_42E+0Eh], xmm1
0x180032eeb  call    memset_0
0x180032ef0  xor     edx, edx; Val
0x180032ef2  lea     rcx, [rbp+360h+Buffer]; void *
0x180032ef9  mov     r8d, 20Ah; Size
0x180032eff  call    memset_0
0x180032f04  mov     edx, 104h; uSize
0x180032f09  lea     rcx, [rbp+360h+Buffer]; lpBuffer
0x180032f10  call    cs:__imp_GetWindowsDirectoryW
0x180032f16  test    eax, eax
0x180032f18  jnz     short loc_180032F3B
0x180032f1a  call    cs:__imp_GetLastError
0x180032f20  lea     rdx, aWinresetrecove_23; "winreSetRecoveryDirectorySecurity: Fail"...
0x180032f27  mov     ecx, 1
0x180032f2c  mov     r8d, eax
0x180032f2f  call    UnattendLogW
0x180032f34  xor     eax, eax
0x180032f36  jmp     loc_18003305E
0x180032f3b  movzx   eax, [rbp+360h+Buffer]
0x180032f42  lea     r8, [rsp+460h+FileName]
0x180032f47  lea     rdx, aWinresetrecove_18; "winreSetRecoveryDirectorySecurity: Chec"...
0x180032f4e  mov     [rsp+460h+FileName], ax
0x180032f53  xor     ecx, ecx
0x180032f55  call    UnattendLogW
0x180032f5a  lea     rcx, [rsp+460h+FileName]; lpFileName
0x180032f5f  call    cs:__imp_GetFileAttributesW
0x180032f65  xor     ecx, ecx
0x180032f67  cmp     eax, 0FFFFFFFFh
0x180032f6a  jnz     loc_18003304D
0x180032f70  lea     rdx, aWinresetrecove_21; "winreSetRecoveryDirectorySecurity: Reco"...
0x180032f77  call    UnattendLogW
0x180032f7c  xor     edx, edx; lpSecurityAttributes
0x180032f7e  lea     rcx, [rsp+460h+FileName]; lpPathName
0x180032f83  call    cs:__imp_CreateDirectoryW
0x180032f89  test    eax, eax
0x180032f8b  jnz     short loc_180032FAE
0x180032f8d  call    cs:__imp_GetLastError
0x180032f93  lea     r8, [rsp+460h+FileName]
0x180032f98  mov     ecx, 1
0x180032f9d  mov     r9d, eax
0x180032fa0  lea     rdx, aWinresetrecove_7; "winreSetRecoveryDirectorySecurity: Fail"...
0x180032fa7  call    UnattendLogW
0x180032fac  jmp     short loc_180032F34
0x180032fae  lea     r8, [rsp+460h+FileName]
0x180032fb3  xor     ecx, ecx
0x180032fb5  lea     rdx, aWinresetrecove_13; "winreSetRecoveryDirectorySecurity: Crea"...
0x180032fbc  call    UnattendLogW
0x180032fc1  lea     rcx, [rsp+460h+FileName]; pObjectName
0x180032fc6  call    ?SetFileSddl@Utils@@SAKPEBG0H@Z; Utils::SetFileSddl(ushort const *,ushort const *,int)
0x180032fcb  lea     r9, StringSecurityDescriptor; "O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GRGX;"...
0x180032fd2  lea     r8, [rsp+460h+FileName]
0x180032fd7  test    eax, eax
0x180032fd9  jz      short loc_180032FF5
0x180032fdb  lea     rdx, aWinresetrecove_8; "winreSetRecoveryDirectorySecurity: Fail"...
0x180032fe2  mov     [rsp+460h+var_440], eax
0x180032fe6  mov     ecx, 1
0x180032feb  call    UnattendLogW
0x180032ff0  jmp     loc_180032F34
0x180032ff5  lea     rdx, aWinresetrecove_1; "winreSetRecoveryDirectorySecurity: Set "...
0x180032ffc  xor     ecx, ecx
0x180032ffe  call    UnattendLogW
0x180033003  mov     edx, 2006h; dwFileAttributes
0x180033008  lea     rcx, [rsp+460h+FileName]; lpFileName
0x18003300d  call    cs:__imp_SetFileAttributesW
0x180033013  test    eax, eax
0x180033015  jnz     short loc_180033038
0x180033017  call    cs:__imp_GetLastError
0x18003301d  lea     r8, [rsp+460h+FileName]
0x180033022  mov     ecx, 1
0x180033027  mov     r9d, eax
0x18003302a  lea     rdx, aWinresetrecove_15; "winreSetRecoveryDirectorySecurity: Fail"...
0x180033031  call    UnattendLogW
0x180033036  jmp     short loc_180033059
0x180033038  lea     r8, [rsp+460h+FileName]
0x18003303d  xor     ecx, ecx
0x18003303f  lea     rdx, aWinresetrecove_20; "winreSetRecoveryDirectorySecurity: Succ"...
0x180033046  call    UnattendLogW
0x18003304b  jmp     short loc_180033059
0x18003304d  lea     rdx, aWinresetrecove_22; "winreSetRecoveryDirectorySecurity: Reco"...
0x180033054  call    UnattendLogW
0x180033059  mov     eax, 1
0x18003305e  mov     rcx, [rbp+360h+var_10]
0x180033065  xor     rcx, rsp; StackCookie
0x180033068  call    __security_check_cookie
0x18003306d  add     rsp, 460h
0x180033074  pop     rbp
0x180033075  retn
```

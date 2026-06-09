# FveBackupMonitor::DeleteOsvRecoveryPasswordBackupTypeRecords(CNgscbToken const *)

- ea: `0x18006fc78`
- end: `0x18006fde2`
- name: `?DeleteOsvRecoveryPasswordBackupTypeRecords@FveBackupMonitor@@SAJPEBVCNgscbToken@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(const struct CNgscbToken *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180033618`
- `0x18003b560`

## callees

- `0x180009f60`
- `0x18001b7f0`
- `0x180021d18`
- `0x180026190`
- `0x180034070`
- `0x180034d28`
- `0x18006fc78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006fd6b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006fd6b`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::DeleteOsvRecoveryPasswordBackupTypeRecords(const struct CNgscbToken *a1)
{
  unsigned int v2; // eax
  signed int v3; // ebx
  unsigned int v4; // eax
  LSTATUS v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v7[0] = 0;
  if ( !a1 )
    goto LABEL_7;
  v2 = CScopedImpersonation::ImpersonateUser((CScopedImpersonation *)v7, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_929186be452536e5252128d48ffaedab_Traceguids, v2);
  if ( v3 >= 0 )
  {
LABEL_7:
    v4 = StringCchPrintfW(
           SubKey,
           0x104u,
           L"%s\\%s",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\KeyBackupMonitor",
           L"OSV");
    v3 = v4;
    if ( !v4 )
      goto LABEL_12;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_929186be452536e5252128d48ffaedab_Traceguids, v4);
    if ( v3 >= 0 )
    {
LABEL_12:
      v5 = RegDeleteTreeW(HKEY_CURRENT_USER, SubKey);
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( v3 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_929186be452536e5252128d48ffaedab_Traceguids,
          (unsigned int)v3);
    }
  }
  CScopedImpersonation::Revert((CScopedImpersonation *)v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006fc78  mov     [rsp+arg_8], rbx
0x18006fc7d  push    rsi
0x18006fc7e  sub     rsp, 260h
0x18006fc85  mov     rax, cs:__security_cookie
0x18006fc8c  xor     rax, rsp
0x18006fc8f  mov     [rsp+268h+var_18], rax
0x18006fc97  mov     rbx, rcx
0x18006fc9a  xor     edx, edx; Val
0x18006fc9c  lea     rcx, [rsp+268h+SubKey]; void *
0x18006fca1  mov     r8d, 208h; Size
0x18006fca7  call    memset_0
0x18006fcac  mov     [rsp+268h+var_238], 0
0x18006fcb1  lea     rsi, WPP_GLOBAL_Control
0x18006fcb8  test    rbx, rbx
0x18006fcbb  jz      short loc_18006FD02
0x18006fcbd  mov     rdx, rbx; struct CNgscbToken *
0x18006fcc0  lea     rcx, [rsp+268h+var_238]; this
0x18006fcc5  call    ?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z; CScopedImpersonation::ImpersonateUser(CNgscbToken const &)
0x18006fcca  mov     ebx, eax
0x18006fccc  test    eax, eax
0x18006fcce  jz      short loc_18006FD02
0x18006fcd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fcd7  cmp     rcx, rsi
0x18006fcda  jz      short loc_18006FCFA
0x18006fcdc  test    byte ptr [rcx+1Ch], 40h
0x18006fce0  jz      short loc_18006FCFA
0x18006fce2  mov     rcx, [rcx+10h]
0x18006fce6  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18006fced  mov     edx, 0Dh
0x18006fcf2  mov     r9d, eax
0x18006fcf5  call    WPP_SF_d
0x18006fcfa  test    ebx, ebx
0x18006fcfc  js      loc_18006FDB4
0x18006fd02  lea     rax, aOsv; "OSV"
0x18006fd09  mov     edx, 104h; unsigned __int64
0x18006fd0e  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006fd15  mov     [rsp+268h+var_248], rax
0x18006fd1a  lea     r8, aSS; "%s\\%s"
0x18006fd21  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18006fd26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006fd2b  mov     ebx, eax
0x18006fd2d  test    eax, eax
0x18006fd2f  jz      short loc_18006FD5F
0x18006fd31  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fd38  cmp     rcx, rsi
0x18006fd3b  jz      short loc_18006FD5B
0x18006fd3d  test    byte ptr [rcx+1Ch], 40h
0x18006fd41  jz      short loc_18006FD5B
0x18006fd43  mov     rcx, [rcx+10h]
0x18006fd47  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18006fd4e  mov     edx, 0Eh
0x18006fd53  mov     r9d, eax
0x18006fd56  call    WPP_SF_d
0x18006fd5b  test    ebx, ebx
0x18006fd5d  js      short loc_18006FDB4
0x18006fd5f  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18006fd64  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006fd6b  call    cs:__imp_RegDeleteTreeW
0x18006fd72  nop     dword ptr [rax+rax+00h]
0x18006fd77  mov     ebx, eax
0x18006fd79  test    eax, eax
0x18006fd7b  jle     short loc_18006FD86
0x18006fd7d  movzx   ebx, ax
0x18006fd80  or      ebx, 80070000h
0x18006fd86  test    ebx, ebx
0x18006fd88  jz      short loc_18006FDB4
0x18006fd8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fd91  cmp     rcx, rsi
0x18006fd94  jz      short loc_18006FDB4
0x18006fd96  test    byte ptr [rcx+1Ch], 40h
0x18006fd9a  jz      short loc_18006FDB4
0x18006fd9c  mov     rcx, [rcx+10h]
0x18006fda0  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18006fda7  mov     edx, 0Fh
0x18006fdac  mov     r9d, ebx
0x18006fdaf  call    WPP_SF_d
0x18006fdb4  lea     rcx, [rsp+268h+var_238]; this
0x18006fdb9  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x18006fdbe  mov     eax, ebx
0x18006fdc0  mov     rcx, [rsp+268h+var_18]
0x18006fdc8  xor     rcx, rsp; StackCookie
0x18006fdcb  call    __security_check_cookie
0x18006fdd0  mov     rbx, [rsp+268h+arg_8]
0x18006fdd8  add     rsp, 260h
0x18006fddf  pop     rsi
0x18006fde0  retn
```

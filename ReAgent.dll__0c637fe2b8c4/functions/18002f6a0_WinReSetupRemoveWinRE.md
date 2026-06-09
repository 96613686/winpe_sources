# WinReSetupRemoveWinRE

- ea: `0x18002f6a0`
- end: `0x18002f850`
- name: `WinReSetupRemoveWinRE`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18002cab4`

## callees

- `0x180001f94`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18002f6a0`
- `0x180030f18`
- `0x18003158c`
- `0x180031e10`
- `0x180035300`
- `0x180051dc8`
- `0x18005cf30`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002f7a1`
- `msvcrt!wcsrchr` at `0x18002f7a1`
- `KERNEL32!GetLastError` at `0x18002f7d3`
- `KERNEL32!GetLastError` at `0x18002f7d3`
- `KERNEL32!RemoveDirectoryW` at `0x18002f7c9`
- `KERNEL32!RemoveDirectoryW` at `0x18002f7c9`

## string_xrefs

- `0x18002f6dd`: `Enter WinReSetupRemoveWinRE`
- `0x18002f7bd`: `winreDeleteAllFiles failed, 0x%x`
- `0x18002f7d9`: `RemoveDirectory failed, 0x%x`
- `0x18002f7ef`: `successfully cleaned up the WinRE directory`
- `0x18002f823`: ` (WinRE)WinReSetupRemoveWinRE() returning %s`

## pseudocode

```c
__int64 __fastcall WinReSetupRemoveWinRE(__int64 a1)
{
  unsigned __int16 *v2; // rdi
  unsigned int v3; // ebx
  unsigned int WinReGuid; // eax
  unsigned int OsInfoForBootEntry; // eax
  wchar_t *v6; // rax
  unsigned int v7; // eax
  DWORD LastError; // eax
  const wchar_t *v9; // r8
  wchar_t *Str; // [rsp+20h] [rbp-38h] BYREF
  GUID v12; // [rsp+28h] [rbp-30h] BYREF
  struct _GUID v13; // [rsp+38h] [rbp-20h] BYREF

  v2 = 0;
  Str = 0;
  v12 = GUID_NULL;
  v13 = GUID_NULL;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetupRemoveWinRE");
  LogGuid(L"targetOSBCDGuid: ", a1);
  if ( (unsigned int)winreGetOSGuidOrDefault(a1, &v12) )
  {
    WinReGuid = winreGetWinReGuid((__int64)&v12, &v13);
    if ( WinReGuid )
    {
      UnattendLogW(2, L"failed to get WinRE guid, 0x%x", WinReGuid);
    }
    else
    {
      OsInfoForBootEntry = CBootCfg::GetOsInfoForBootEntry(
                             (CBootCfg *)CBootCfg::m_instance,
                             &v13,
                             (struct _SRT_OS_INFO **)&Str);
      if ( OsInfoForBootEntry )
      {
        UnattendLogW(2, L"failed to get os info for boot entry, 0x%x", OsInfoForBootEntry);
        v2 = Str;
      }
      else
      {
        v2 = Str;
        if ( *((_DWORD *)Str + 572) )
        {
          UnattendLogW(2, L"Get Os info for boot entry returned corrupt information.");
        }
        else
        {
          v6 = wcsrchr(Str, 0x5Cu);
          if ( v6 )
            *v6 = 0;
          v7 = winreDeleteAllFiles(v2);
          if ( v7 )
          {
            UnattendLogW(2, L"winreDeleteAllFiles failed, 0x%x", v7);
          }
          else if ( RemoveDirectoryW(v2) )
          {
            UnattendLogW(0, L"successfully cleaned up the WinRE directory");
          }
          else
          {
            LastError = GetLastError();
            UnattendLogW(2, L"RemoveDirectory failed, 0x%x", LastError);
          }
        }
      }
    }
    v3 = 1;
    if ( v2 )
      operator delete(v2);
  }
  else
  {
    v3 = 0;
    UnattendLogW(2, L"failed to get OS guid or default");
  }
  v9 = L"TRUE";
  if ( !v3 )
    v9 = L"FALSE";
  UnattendLogW(0, L" (WinRE)WinReSetupRemoveWinRE() returning %s", v9);
  UnattendFinalizeLog();
  return v3;
}

```

## disassembly

```asm
0x18002f6a0  mov     [rsp+arg_8], rbx
0x18002f6a5  push    rdi
0x18002f6a6  sub     rsp, 50h
0x18002f6aa  mov     rax, cs:__security_cookie
0x18002f6b1  xor     rax, rsp
0x18002f6b4  mov     [rsp+58h+var_10], rax
0x18002f6b9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002f6c0  mov     rbx, rcx
0x18002f6c3  xor     edi, edi
0x18002f6c5  xor     ecx, ecx
0x18002f6c7  mov     [rsp+58h+Str], rdi
0x18002f6cc  movdqu  [rsp+58h+var_30], xmm0
0x18002f6d2  movdqu  xmmword ptr [rsp+58h+var_20.Data1], xmm0
0x18002f6d8  call    UnattendInitializeLogEx2
0x18002f6dd  lea     rdx, aEnterWinresetu_6; "Enter WinReSetupRemoveWinRE"
0x18002f6e4  xor     ecx, ecx
0x18002f6e6  call    UnattendLogW
0x18002f6eb  mov     rdx, rbx
0x18002f6ee  lea     rcx, aTargetosbcdgui_0; "targetOSBCDGuid: "
0x18002f6f5  call    LogGuid
0x18002f6fa  lea     rdx, [rsp+58h+var_30]
0x18002f6ff  mov     rcx, rbx
0x18002f702  call    winreGetOSGuidOrDefault
0x18002f707  test    eax, eax
0x18002f709  jnz     short loc_18002F721
0x18002f70b  xor     ebx, ebx
0x18002f70d  lea     rdx, aFailedToGetOsG; "failed to get OS guid or default"
0x18002f714  lea     ecx, [rdi+2]
0x18002f717  call    UnattendLogW
0x18002f71c  jmp     loc_18002F80F
0x18002f721  lea     rdx, [rsp+58h+var_20]
0x18002f726  lea     rcx, [rsp+58h+var_30]
0x18002f72b  call    winreGetWinReGuid
0x18002f730  test    eax, eax
0x18002f732  jz      short loc_18002F740
0x18002f734  lea     rdx, aFailedToGetWin_11; "failed to get WinRE guid, 0x%x"
0x18002f73b  jmp     loc_18002F7E0
0x18002f740  lea     r8, [rsp+58h+Str]; struct _SRT_OS_INFO **
0x18002f745  lea     rdx, [rsp+58h+var_20]; struct _GUID *
0x18002f74a  lea     rcx, ?m_instance@CBootCfg@@0V1@A; this
0x18002f751  call    ?GetOsInfoForBootEntry@CBootCfg@@QEAAKPEBU_GUID@@PEAPEAU_SRT_OS_INFO@@@Z; CBootCfg::GetOsInfoForBootEntry(_GUID const *,_SRT_OS_INFO * *)
0x18002f756  test    eax, eax
0x18002f758  jz      short loc_18002F778
0x18002f75a  mov     r8d, eax
0x18002f75d  lea     rdx, aFailedToGetOsI; "failed to get os info for boot entry, 0"...
0x18002f764  mov     ecx, 2
0x18002f769  call    UnattendLogW
0x18002f76e  mov     rdi, [rsp+58h+Str]
0x18002f773  jmp     loc_18002F7FD
0x18002f778  mov     rdi, [rsp+58h+Str]
0x18002f77d  cmp     dword ptr [rdi+8F0h], 0
0x18002f784  jz      short loc_18002F799
0x18002f786  lea     rdx, aGetOsInfoForBo; "Get Os info for boot entry returned cor"...
0x18002f78d  mov     ecx, 2
0x18002f792  call    UnattendLogW
0x18002f797  jmp     short loc_18002F7FD
0x18002f799  mov     edx, 5Ch ; '\'; Ch
0x18002f79e  mov     rcx, rdi; Str
0x18002f7a1  call    cs:__imp_wcsrchr
0x18002f7a7  test    rax, rax
0x18002f7aa  jz      short loc_18002F7B1
0x18002f7ac  xor     ecx, ecx
0x18002f7ae  mov     [rax], cx
0x18002f7b1  mov     rcx, rdi
0x18002f7b4  call    winreDeleteAllFiles
0x18002f7b9  test    eax, eax
0x18002f7bb  jz      short loc_18002F7C6
0x18002f7bd  lea     rdx, aWinredeleteall; "winreDeleteAllFiles failed, 0x%x"
0x18002f7c4  jmp     short loc_18002F7E0
0x18002f7c6  mov     rcx, rdi; lpPathName
0x18002f7c9  call    cs:__imp_RemoveDirectoryW
0x18002f7cf  test    eax, eax
0x18002f7d1  jnz     short loc_18002F7EF
0x18002f7d3  call    cs:__imp_GetLastError
0x18002f7d9  lea     rdx, aRemovedirector; "RemoveDirectory failed, 0x%x"
0x18002f7e0  mov     r8d, eax
0x18002f7e3  mov     ecx, 2
0x18002f7e8  call    UnattendLogW
0x18002f7ed  jmp     short loc_18002F7FD
0x18002f7ef  lea     rdx, aSuccessfullyCl; "successfully cleaned up the WinRE direc"...
0x18002f7f6  xor     ecx, ecx
0x18002f7f8  call    UnattendLogW
0x18002f7fd  mov     ebx, 1
0x18002f802  test    rdi, rdi
0x18002f805  jz      short loc_18002F80F
0x18002f807  mov     rcx, rdi; Block
0x18002f80a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f80f  lea     rax, aFalse_0; "FALSE"
0x18002f816  test    ebx, ebx
0x18002f818  lea     r8, aTrue_0; "TRUE"
0x18002f81f  cmovz   r8, rax
0x18002f823  lea     rdx, aWinreWinresetu_0; " (WinRE)WinReSetupRemoveWinRE() returni"...
0x18002f82a  xor     ecx, ecx
0x18002f82c  call    UnattendLogW
0x18002f831  call    UnattendFinalizeLog
0x18002f836  mov     eax, ebx
0x18002f838  mov     rcx, [rsp+58h+var_10]
0x18002f83d  xor     rcx, rsp; StackCookie
0x18002f840  call    __security_check_cookie
0x18002f845  mov     rbx, [rsp+58h+arg_8]
0x18002f84a  add     rsp, 50h
0x18002f84e  pop     rdi
0x18002f84f  retn
```

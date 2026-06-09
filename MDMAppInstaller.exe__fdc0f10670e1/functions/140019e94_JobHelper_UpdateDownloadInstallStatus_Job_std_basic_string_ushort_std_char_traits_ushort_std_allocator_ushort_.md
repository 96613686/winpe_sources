# JobHelper::UpdateDownloadInstallStatus(_Job &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140019e94`
- end: `0x140019fc5`
- name: `?UpdateDownloadInstallStatus@JobHelper@@SAJAEAU_Job@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(_QWORD *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d898`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x140018520`
- `0x140019750`
- `0x140019e94`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140019f58`
- `KERNEL32!LeaveCriticalSection` at `0x140019f58`
- `KERNEL32!EnterCriticalSection` at `0x140019ed1`
- `KERNEL32!EnterCriticalSection` at `0x140019ed1`

## string_xrefs

- `0x140019f45`: `Updated job %1 with %2 = '%3'.`
- `0x140019f88`: `UpdateDownloadInstallStatus failed for job %1. Error = 0x%2!x!. Attempting to set %3 to value '%4'.`
- `0x140019f0e`: `DownloadInstall`
- `0x140019f3e`: `DownloadInstall`
- `0x140019f7b`: `DownloadInstall`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateDownloadInstallStatus(_QWORD *a1, const unsigned __int16 *a2)
{
  HKEY v4; // rcx
  int JobRegPath; // esi
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r9
  __int64 *v8; // r9
  _QWORD *v9; // rdx
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+20h] [rbp-48h]
  int v12; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v13[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v13, (__int64)&word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, a1 + 4, v13);
  if ( JobRegPath >= 0 )
  {
    v6 = (const unsigned __int16 *)v13;
    if ( v13[3] >= (unsigned __int16 *)8 )
      v6 = v13[0];
    if ( *((_QWORD *)a2 + 3) < 8u )
      v7 = a2;
    else
      v7 = *(const unsigned __int16 **)a2;
    JobRegPath = WriteRegSZValue(v4, v6, L"DownloadInstall", v7, v11, v12);
    if ( JobRegPath >= 0 )
    {
      if ( *((_QWORD *)a2 + 3) < 8u )
        v8 = (__int64 *)a2;
      else
        v8 = *(__int64 **)a2;
      if ( a1[3] < 8u )
        v9 = a1;
      else
        v9 = (_QWORD *)*a1;
      LogInfo(L"Updated job %1 with %2 = '%3'.", v9, L"DownloadInstall", v8);
    }
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath < 0 )
  {
    if ( *((_QWORD *)a2 + 3) >= 8u )
      a2 = *(const unsigned __int16 **)a2;
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    LogError(
      L"UpdateDownloadInstallStatus failed for job %1. Error = 0x%2!x!. Attempting to set %3 to value '%4'.",
      a1,
      (unsigned int)JobRegPath,
      L"DownloadInstall",
      a2);
  }
  std::wstring::_Tidy(v13, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x140019e94  mov     [rsp+arg_10], rbx
0x140019e99  mov     [rsp+arg_18], rsi
0x140019e9e  push    rdi
0x140019e9f  sub     rsp, 60h
0x140019ea3  mov     rax, cs:__security_cookie
0x140019eaa  xor     rax, rsp
0x140019ead  mov     [rsp+68h+var_18], rax
0x140019eb2  mov     rbx, rdx
0x140019eb5  mov     rdi, rcx
0x140019eb8  lea     rdx, word_14001E5B4
0x140019ebf  lea     rcx, [rsp+68h+var_38]
0x140019ec4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140019ec9  nop
0x140019eca  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140019ed1  call    cs:__imp_EnterCriticalSection
0x140019ed7  lea     rdx, [rdi+20h]
0x140019edb  lea     r8, [rsp+68h+var_38]
0x140019ee0  mov     rcx, rdi
0x140019ee3  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x140019ee8  mov     esi, eax
0x140019eea  test    eax, eax
0x140019eec  js      short loc_140019F51
0x140019eee  lea     rdx, [rsp+68h+var_38]
0x140019ef3  cmp     [rsp+68h+var_20], 8
0x140019ef9  cmovnb  rdx, [rsp+68h+var_38]; unsigned __int16 *
0x140019eff  cmp     qword ptr [rbx+18h], 8
0x140019f04  jb      short loc_140019F0B
0x140019f06  mov     r9, [rbx]
0x140019f09  jmp     short loc_140019F0E
0x140019f0b  mov     r9, rbx; unsigned __int16 *
0x140019f0e  lea     r8, aDownloadinstal; "DownloadInstall"
0x140019f15  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x140019f1a  mov     esi, eax
0x140019f1c  test    eax, eax
0x140019f1e  js      short loc_140019F51
0x140019f20  cmp     qword ptr [rbx+18h], 8
0x140019f25  jb      short loc_140019F2C
0x140019f27  mov     r9, [rbx]
0x140019f2a  jmp     short loc_140019F2F
0x140019f2c  mov     r9, rbx
0x140019f2f  cmp     qword ptr [rdi+18h], 8
0x140019f34  jb      short loc_140019F3B
0x140019f36  mov     rdx, [rdi]
0x140019f39  jmp     short loc_140019F3E
0x140019f3b  mov     rdx, rdi
0x140019f3e  lea     r8, aDownloadinstal; "DownloadInstall"
0x140019f45  lea     rcx, aUpdatedJob1Wit; "Updated job %1 with %2 = '%3'."
0x140019f4c  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140019f51  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140019f58  call    cs:__imp_LeaveCriticalSection
0x140019f5e  test    esi, esi
0x140019f60  jns     short loc_140019F95
0x140019f62  cmp     qword ptr [rbx+18h], 8
0x140019f67  jb      short loc_140019F6C
0x140019f69  mov     rbx, [rbx]
0x140019f6c  cmp     qword ptr [rdi+18h], 8
0x140019f71  jb      short loc_140019F76
0x140019f73  mov     rdi, [rdi]
0x140019f76  mov     [rsp+68h+var_48], rbx
0x140019f7b  lea     r9, aDownloadinstal; "DownloadInstall"
0x140019f82  mov     r8d, esi
0x140019f85  mov     rdx, rdi
0x140019f88  lea     rcx, aUpdatedownload_0; "UpdateDownloadInstallStatus failed for "...
0x140019f8f  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019f94  nop
0x140019f95  xor     r8d, r8d
0x140019f98  mov     dl, 1
0x140019f9a  lea     rcx, [rsp+68h+var_38]
0x140019f9f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019fa4  mov     eax, esi
0x140019fa6  mov     rcx, [rsp+68h+var_18]
0x140019fab  xor     rcx, rsp; StackCookie
0x140019fae  call    __security_check_cookie
0x140019fb3  lea     r11, [rsp+68h+var_8]
0x140019fb8  mov     rbx, [r11+20h]
0x140019fbc  mov     rsi, [r11+28h]
0x140019fc0  mov     rsp, r11
0x140019fc3  pop     rdi
0x140019fc4  retn
```

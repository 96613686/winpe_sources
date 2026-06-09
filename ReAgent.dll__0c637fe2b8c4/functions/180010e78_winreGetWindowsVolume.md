# winreGetWindowsVolume

- ea: `0x180010e78`
- end: `0x18001106c`
- name: `winreGetWindowsVolume`
- size: `500`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x18000d67c`
- `0x18003a778`
- `0x18003af14`
- `0x18003bfbc`
- `0x18003cbe8`

## callees

- `0x180001f94`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x180010e78`
- `0x180051dc8`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010ecb`
- `KERNEL32!GetLastError` at `0x180010f27`
- `KERNEL32!GetLastError` at `0x180010ecb`
- `KERNEL32!GetLastError` at `0x180010f27`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180010f19`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180010f19`
- `KERNEL32!GetSystemDirectoryW` at `0x180010ec1`
- `KERNEL32!GetSystemDirectoryW` at `0x180010ec1`

## string_xrefs

- `0x180010ee9`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010f45`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010f7d`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010ff4`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010ed9`: `failed to get system directory`

## pseudocode

```c
__int64 __fastcall winreGetWindowsVolume(struct _GUID *a1, unsigned __int16 *a2)
{
  struct _SRT_OS_INFO *v2; // rdi
  __int64 LastError; // rbx
  int v5; // esi
  struct _SRT_OS_INFO *v7; // [rsp+30h] [rbp-298h] BYREF
  unsigned __int64 v8; // [rsp+38h] [rbp-290h] BYREF
  WCHAR Buffer[304]; // [rsp+40h] [rbp-288h] BYREF

  v2 = 0;
  v8 = 0;
  v7 = 0;
  if ( !a1 )
  {
    if ( !GetSystemDirectoryW(Buffer, 0x12Eu) )
    {
      LastError = GetLastError();
      UnattendLogW(
        2,
        L"winreGetWindowsVolume %s (0x%x) in file %S line %d",
        L"failed to get system directory",
        LastError,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        1648);
      return (unsigned int)LastError;
    }
    LODWORD(LastError) = 0;
    goto LABEL_5;
  }
  LODWORD(LastError) = CBootCfg::GetOsInfoForBootEntry((CBootCfg *)CBootCfg::m_instance, a1, &v7);
  if ( (_DWORD)LastError )
  {
    UnattendLogW(
      2,
      L"winreGetWindowsVolume %s (0x%x) in file %S line %d",
      L"failed to get os info for boot entry",
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
      1655);
    v2 = v7;
  }
  else
  {
    v2 = v7;
    if ( StringCchCopyW(Buffer, 0x12Eu, (const unsigned __int16 *)v7) >= 0 )
    {
LABEL_5:
      Buffer[3] = 0;
      if ( GetVolumeNameForVolumeMountPointW(Buffer, a2, 0x12Eu) )
      {
        v5 = StringCchLengthW(a2, 0x12Eu, &v8);
        if ( v5 >= 0 )
        {
          if ( v8 > 1 )
            a2[v8 - 1] = 0;
        }
        else
        {
          UnattendLogW(
            2,
            L"winreGetWindowsVolume %s (0x%x) in file %S line %d",
            L"failed to get the length of string windows volume",
            (unsigned int)v5,
            "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
            1681);
          LODWORD(LastError) = (unsigned __int16)v5;
        }
      }
      else
      {
        LastError = GetLastError();
        UnattendLogW(
          2,
          L"winreGetWindowsVolume %s (0x%x) in file %S line %d",
          L"failed to get volume name",
          LastError,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          1674);
      }
      goto LABEL_15;
    }
    LODWORD(LastError) = 87;
  }
LABEL_15:
  if ( v2 )
    operator delete(v2);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180010e78  mov     [rsp+arg_10], rbx
0x180010e7d  push    rbp
0x180010e7e  push    rsi
0x180010e7f  push    rdi
0x180010e80  sub     rsp, 2B0h
0x180010e87  mov     rax, cs:__security_cookie
0x180010e8e  xor     rax, rsp
0x180010e91  mov     [rsp+2C8h+var_28], rax
0x180010e99  xor     edi, edi
0x180010e9b  mov     [rsp+2C8h+var_290], 0
0x180010ea4  mov     [rsp+2C8h+var_298], rdi
0x180010ea9  mov     rbp, rdx
0x180010eac  test    rcx, rcx
0x180010eaf  jnz     loc_180010F63
0x180010eb5  mov     esi, 12Eh
0x180010eba  lea     rcx, [rsp+2C8h+Buffer]; lpBuffer
0x180010ebf  mov     edx, esi; uSize
0x180010ec1  call    cs:__imp_GetSystemDirectoryW
0x180010ec7  test    eax, eax
0x180010ec9  jnz     short loc_180010F05
0x180010ecb  call    cs:__imp_GetLastError
0x180010ed1  mov     [rsp+2C8h+var_2A0], 670h
0x180010ed9  lea     r8, aFailedToGetSys_1; "failed to get system directory"
0x180010ee0  mov     ebx, eax
0x180010ee2  lea     rdx, aWinregetwindow; "winreGetWindowsVolume %s (0x%x) in file"...
0x180010ee9  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010ef0  mov     r9d, ebx
0x180010ef3  lea     ecx, [rdi+2]
0x180010ef6  mov     [rsp+2C8h+var_2A8], rax
0x180010efb  call    UnattendLogW
0x180010f00  jmp     loc_180011047
0x180010f05  xor     ebx, ebx
0x180010f07  xor     eax, eax
0x180010f09  lea     rcx, [rsp+2C8h+Buffer]; lpszVolumeMountPoint
0x180010f0e  mov     r8d, esi; cchBufferLength
0x180010f11  mov     [rsp+2C8h+var_282], ax
0x180010f16  mov     rdx, rbp; lpszVolumeName
0x180010f19  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180010f1f  test    eax, eax
0x180010f21  jnz     loc_180010FDE
0x180010f27  call    cs:__imp_GetLastError
0x180010f2d  mov     [rsp+2C8h+var_2A0], 68Ah
0x180010f35  lea     r8, aFailedToGetVol_3; "failed to get volume name"
0x180010f3c  mov     ebx, eax
0x180010f3e  lea     rdx, aWinregetwindow; "winreGetWindowsVolume %s (0x%x) in file"...
0x180010f45  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010f4c  mov     r9d, ebx
0x180010f4f  mov     ecx, 2
0x180010f54  mov     [rsp+2C8h+var_2A8], rax
0x180010f59  call    UnattendLogW
0x180010f5e  jmp     loc_18001103A
0x180010f63  mov     rdx, rcx; struct _GUID *
0x180010f66  lea     r8, [rsp+2C8h+var_298]; struct _SRT_OS_INFO **
0x180010f6b  lea     rcx, ?m_instance@CBootCfg@@0V1@A; this
0x180010f72  call    ?GetOsInfoForBootEntry@CBootCfg@@QEAAKPEBU_GUID@@PEAPEAU_SRT_OS_INFO@@@Z; CBootCfg::GetOsInfoForBootEntry(_GUID const *,_SRT_OS_INFO * *)
0x180010f77  mov     ebx, eax
0x180010f79  test    eax, eax
0x180010f7b  jz      short loc_180010FB6
0x180010f7d  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010f84  mov     [rsp+2C8h+var_2A0], 677h
0x180010f8c  mov     r9d, ebx
0x180010f8f  mov     [rsp+2C8h+var_2A8], rax
0x180010f94  lea     r8, aFailedToGetOsI_0; "failed to get os info for boot entry"
0x180010f9b  mov     ecx, 2
0x180010fa0  lea     rdx, aWinregetwindow; "winreGetWindowsVolume %s (0x%x) in file"...
0x180010fa7  call    UnattendLogW
0x180010fac  mov     rdi, [rsp+2C8h+var_298]
0x180010fb1  jmp     loc_18001103A
0x180010fb6  mov     rdi, [rsp+2C8h+var_298]
0x180010fbb  lea     rcx, [rsp+2C8h+Buffer]; unsigned __int16 *
0x180010fc0  mov     esi, 12Eh
0x180010fc5  mov     r8, rdi; unsigned __int16 *
0x180010fc8  mov     edx, esi; unsigned __int64
0x180010fca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010fcf  test    eax, eax
0x180010fd1  jns     loc_180010F07
0x180010fd7  mov     ebx, 57h ; 'W'
0x180010fdc  jmp     short loc_18001103A
0x180010fde  lea     r8, [rsp+2C8h+var_290]; unsigned __int64 *
0x180010fe3  mov     rdx, rsi; unsigned __int64
0x180010fe6  mov     rcx, rbp; unsigned __int16 *
0x180010fe9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180010fee  mov     esi, eax
0x180010ff0  test    eax, eax
0x180010ff2  jns     short loc_180011028
0x180010ff4  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010ffb  mov     [rsp+2C8h+var_2A0], 691h
0x180011003  mov     r9d, esi
0x180011006  mov     [rsp+2C8h+var_2A8], rax
0x18001100b  lea     r8, aFailedToGetThe_1; "failed to get the length of string wind"...
0x180011012  mov     ecx, 2
0x180011017  lea     rdx, aWinregetwindow; "winreGetWindowsVolume %s (0x%x) in file"...
0x18001101e  call    UnattendLogW
0x180011023  movzx   ebx, si
0x180011026  jmp     short loc_18001103A
0x180011028  mov     rcx, [rsp+2C8h+var_290]
0x18001102d  cmp     rcx, 1
0x180011031  jbe     short loc_18001103A
0x180011033  xor     eax, eax
0x180011035  mov     [rbp+rcx*2-2], ax
0x18001103a  test    rdi, rdi
0x18001103d  jz      short loc_180011047
0x18001103f  mov     rcx, rdi; Block
0x180011042  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011047  mov     eax, ebx
0x180011049  mov     rcx, [rsp+2C8h+var_28]
0x180011051  xor     rcx, rsp; StackCookie
0x180011054  call    __security_check_cookie
0x180011059  mov     rbx, [rsp+2C8h+arg_10]
0x180011061  add     rsp, 2B0h
0x180011068  pop     rdi
0x180011069  pop     rsi
0x18001106a  pop     rbp
0x18001106b  retn
```

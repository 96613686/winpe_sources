# CWUEtwConsumer::InitTraceProperties(wchar_t const *,wchar_t const *)

- ea: `0x140017020`
- end: `0x1400171b9`
- name: `?InitTraceProperties@CWUEtwConsumer@@QEAAJPEB_W0@Z`
- size: `409`
- prototype: `int(CWUEtwConsumer *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140016c54`

## callees

- `0x140015f20`
- `0x140017020`
- `0x140017934`
- `0x140018394`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017168`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140017071`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140017071`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x140017118`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x140017118`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1400170e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1400170e7`

## pseudocode

```c
__int64 __fastcall CWUEtwConsumer::InitTraceProperties(CWUEtwConsumer *this, const wchar_t *a2, const wchar_t *a3)
{
  __int64 v5; // rbx
  WCHAR *v6; // rcx
  WCHAR v7; // ax
  WCHAR *v8; // rax
  signed int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // r8
  wchar_t **v12; // r9
  const WCHAR *RegKeyPath; // rax
  int v14; // ecx
  signed int LastError; // eax
  LPDWORD lpMaximumComponentLength; // [rsp+20h] [rbp-468h]
  WCHAR pszPath[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp-238h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = 260;
  if ( ExpandEnvironmentStringsW(a3, Dst, 0x104u) - 1 > 0x102 )
  {
    return (unsigned int)-2147024774;
  }
  else
  {
    v6 = pszPath;
    do
    {
      if ( v5 == -2147483386 )
        break;
      v7 = *(WCHAR *)((char *)v6 + (char *)Dst - (char *)pszPath);
      if ( !v7 )
        break;
      *v6++ = v7;
      --v5;
    }
    while ( v5 );
    v8 = v6 - 1;
    if ( v5 )
      v8 = v6;
    *v8 = 0;
    v9 = v5 == 0 ? 0x8007007A : 0;
    if ( v5 )
    {
      if ( PathStripToRootW(pszPath) && GetVolumeInformationW(pszPath, 0, 0, 0, 0, (LPDWORD)this + 443, 0, 0) )
      {
        RegKeyPath = (const WCHAR *)GetRegKeyPath(21, v10, v11, v12);
        RegQueryDwordValueWithDefaultAndRangeCheck(
          v14,
          RegKeyPath,
          L"Flags",
          0,
          (__int64)lpMaximumComponentLength,
          0xFFFFFFFF);
        return (unsigned int)CWUEventTraceProperties::Init(
                               (CWUEtwConsumer *)((char *)this + 592),
                               a2,
                               Dst,
                               (const struct _GUID *)((char *)this + 532));
      }
      else
      {
        LastError = GetLastError();
        v9 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v9 = LastError;
        if ( v9 >= 0 )
          return (unsigned int)-2147418113;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140017020  mov     [rsp+arg_8], rbx
0x140017025  push    rbp
0x140017026  push    rsi
0x140017027  push    rdi
0x140017028  sub     rsp, 470h
0x14001702f  mov     rax, cs:__security_cookie
0x140017036  xor     rax, rsp
0x140017039  mov     [rsp+488h+var_28], rax
0x140017041  xor     ebp, ebp
0x140017043  mov     rax, r8
0x140017046  mov     rsi, rdx
0x140017049  mov     rdi, rcx
0x14001704c  test    rdx, rdx
0x14001704f  jz      loc_140017191
0x140017055  test    rax, rax
0x140017058  jz      loc_140017191
0x14001705e  mov     ebx, 104h
0x140017063  lea     rdx, [rsp+488h+Dst]; lpDst
0x14001706b  mov     r8d, ebx; nSize
0x14001706e  mov     rcx, rax; lpSrc
0x140017071  call    cs:__imp_ExpandEnvironmentStringsW
0x140017077  dec     eax
0x140017079  cmp     eax, 102h
0x14001707e  ja      loc_140017188
0x140017084  lea     rdx, [rsp+488h+Dst]
0x14001708c  lea     rax, [rsp+488h+pszPath]
0x140017091  sub     rdx, rax
0x140017094  lea     rcx, [rsp+488h+pszPath]
0x140017099  lea     rax, [rbx+7FFFFEFAh]
0x1400170a0  test    rax, rax
0x1400170a3  jz      short loc_1400170BB
0x1400170a5  movzx   eax, word ptr [rcx+rdx]
0x1400170a9  test    ax, ax
0x1400170ac  jz      short loc_1400170BB
0x1400170ae  mov     [rcx], ax
0x1400170b1  add     rcx, 2
0x1400170b5  sub     rbx, 1
0x1400170b9  jnz     short loc_140017099
0x1400170bb  lea     rax, [rcx-2]
0x1400170bf  test    rbx, rbx
0x1400170c2  cmovnz  rax, rcx
0x1400170c6  mov     [rax], bp
0x1400170c9  mov     rax, rbx
0x1400170cc  neg     rax
0x1400170cf  sbb     ecx, ecx
0x1400170d1  not     ecx
0x1400170d3  and     ecx, 8007007Ah
0x1400170d9  test    rbx, rbx
0x1400170dc  jz      loc_14001718D
0x1400170e2  lea     rcx, [rsp+488h+pszPath]; pszPath
0x1400170e7  call    cs:__imp_PathStripToRootW
0x1400170ed  test    eax, eax
0x1400170ef  jz      short loc_140017168
0x1400170f1  mov     [rsp+488h+nFileSystemNameSize], ebp; nFileSystemNameSize
0x1400170f5  lea     rax, [rdi+6ECh]
0x1400170fc  mov     [rsp+488h+lpFileSystemNameBuffer], rbp; lpFileSystemNameBuffer
0x140017101  lea     rcx, [rsp+488h+pszPath]; lpRootPathName
0x140017106  mov     [rsp+488h+lpFileSystemFlags], rax; lpFileSystemFlags
0x14001710b  xor     r9d, r9d; lpVolumeSerialNumber
0x14001710e  xor     r8d, r8d; nVolumeNameSize
0x140017111  mov     [rsp+488h+lpMaximumComponentLength], rbp; lpMaximumComponentLength
0x140017116  xor     edx, edx; lpVolumeNameBuffer
0x140017118  call    cs:__imp_GetVolumeInformationW
0x14001711e  test    eax, eax
0x140017120  jz      short loc_140017168
0x140017122  mov     ecx, 15h
0x140017127  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x14001712c  xor     r9d, r9d
0x14001712f  mov     dword ptr [rsp+488h+lpFileSystemFlags], 0FFFFFFFFh
0x140017137  lea     r8, aFlags_0; "Flags"
0x14001713e  mov     rdx, rax
0x140017141  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140017146  lea     r9, [rdi+214h]; struct _GUID *
0x14001714d  mov     rdx, rsi; wchar_t *
0x140017150  lea     rcx, [rdi+250h]; this
0x140017157  lea     r8, [rsp+488h+Dst]; wchar_t *
0x14001715f  call    ?Init@CWUEventTraceProperties@@QEAAJPEB_W0AEBU_GUID@@@Z; CWUEventTraceProperties::Init(wchar_t const *,wchar_t const *,_GUID const &)
0x140017164  mov     ecx, eax
0x140017166  jmp     short loc_14001718D
0x140017168  call    cs:__imp_GetLastError
0x14001716e  movzx   ecx, ax
0x140017171  or      ecx, 80070000h
0x140017177  test    eax, eax
0x140017179  cmovle  ecx, eax
0x14001717c  mov     eax, 8000FFFFh
0x140017181  test    ecx, ecx
0x140017183  cmovns  ecx, eax
0x140017186  jmp     short loc_14001718D
0x140017188  mov     ecx, 8007007Ah
0x14001718d  mov     eax, ecx
0x14001718f  jmp     short loc_140017196
0x140017191  mov     eax, 80070057h
0x140017196  mov     rcx, [rsp+488h+var_28]
0x14001719e  xor     rcx, rsp; StackCookie
0x1400171a1  call    __security_check_cookie
0x1400171a6  mov     rbx, [rsp+488h+arg_8]
0x1400171ae  add     rsp, 470h
0x1400171b5  pop     rdi
0x1400171b6  pop     rsi
0x1400171b7  pop     rbp
0x1400171b8  retn
```

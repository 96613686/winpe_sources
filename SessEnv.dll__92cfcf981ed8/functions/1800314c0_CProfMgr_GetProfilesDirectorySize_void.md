# CProfMgr::GetProfilesDirectorySize(void)

- ea: `0x1800314c0`
- end: `0x1800316a0`
- name: `?GetProfilesDirectorySize@CProfMgr@@AEAA_KXZ`
- size: `480`
- prototype: `unsigned __int64 __fastcall(CProfMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180032a60`

## callees

- `0x180003f30`
- `0x180016674`
- `0x18001a280`
- `0x1800314c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180031626`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180031626`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180031636`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180031636`

## string_xrefs

- `0x1800314ea`: `CProfMgr::GetProfilesDirectorySize`
- `0x180031539`: `UserSid %ws`
- `0x180031552`: `ProfilePath %ws`
- `0x1800315c8`: `ProfileDirectorySize %I64d GB`
- `0x1800315e6`: `LastAccessTime High Date: 0x%08x, Low Date: 0x%08x`
- `0x180031663`: `LastAccessTime %02d/%02d/%04d %02d:%02d`

## pseudocode

```c
__int64 __fastcall CProfMgr::GetProfilesDirectorySize(CProfMgr *this)
{
  __int64 v2; // rbp
  int UserProfileList; // eax
  __int64 i; // rdi
  _QWORD *v5; // r8
  const wchar_t *v6; // r9
  __int64 v7; // r8
  const wchar_t *v8; // r9
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // rax
  struct _FILETIME LocalFileTime; // [rsp+40h] [rbp-58h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-50h] BYREF

  v2 = 0;
  UserProfileList = CProfMgr::CreateUserProfileList(this);
  if ( UserProfileList >= 0 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 414); i = (unsigned int)(i + 1) )
    {
      v5 = *(_QWORD **)(*((_QWORD *)this + 206) + 8 * i);
      if ( v5 )
      {
        v2 += v5[3];
        _DbgPrintMessage(1, "UserSid %ws", *v5);
        _DbgPrintMessage(1, "ProfilePath %ws", *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 206) + 8 * i) + 8LL));
        v6 = L"Roaming";
        v7 = *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 206) + 8 * i) + 16LL);
        if ( (_DWORD)v7 != 1 )
          v6 = L"Non-Roaming";
        _DbgPrintMessage(1, "ProfileType 0x%08x (%ws)", v7, v6);
        v8 = L"Roaming";
        v9 = *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 206) + 8 * i) + 20LL);
        if ( (_DWORD)v9 != 1 )
          v8 = L"Non-Roaming";
        _DbgPrintMessage(1, "ProfileStatus 0x%08x (%ws)", v9, v8);
        _DbgPrintMessage(
          1,
          "ProfileDirectorySize %I64d GB",
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 206) + 8 * i) + 24LL));
        v10 = *(_QWORD *)(*((_QWORD *)this + 206) + 8 * i);
        _DbgPrintMessage(
          1,
          "LastAccessTime High Date: 0x%08x, Low Date: 0x%08x",
          *(_DWORD *)(v10 + 36),
          *(_DWORD *)(v10 + 32));
        v11 = *((_QWORD *)this + 206);
        LocalFileTime = 0;
        SystemTime = 0;
        FileTimeToLocalFileTime((const FILETIME *)(*(_QWORD *)(v11 + 8 * i) + 32LL), &LocalFileTime);
        FileTimeToSystemTime(&LocalFileTime, &SystemTime);
        _DbgPrintMessage(
          1,
          "LastAccessTime %02d/%02d/%04d %02d:%02d",
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wYear,
          SystemTime.wHour,
          SystemTime.wMinute);
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "GetUserProfileList failed: 0x%x in %s", UserProfileList, "CProfMgr::GetProfilesDirectorySize");
  }
  return v2;
}

```

## disassembly

```asm
0x1800314c0  push    rbx
0x1800314c2  push    rbp
0x1800314c3  push    rsi
0x1800314c4  push    rdi
0x1800314c5  push    r14
0x1800314c7  push    r15
0x1800314c9  sub     rsp, 68h
0x1800314cd  mov     rax, cs:__security_cookie
0x1800314d4  xor     rax, rsp
0x1800314d7  mov     [rsp+98h+var_40], rax
0x1800314dc  mov     rbx, rcx
0x1800314df  xor     ebp, ebp
0x1800314e1  call    ?CreateUserProfileList@CProfMgr@@AEAAJXZ; CProfMgr::CreateUserProfileList(void)
0x1800314e6  test    eax, eax
0x1800314e8  jns     short loc_180031508
0x1800314ea  lea     r9, aCprofmgrGetpro; "CProfMgr::GetProfilesDirectorySize"
0x1800314f1  mov     r8d, eax
0x1800314f4  lea     rdx, aGetuserprofile_0; "GetUserProfileList failed: 0x%x in %s"
0x1800314fb  lea     ecx, [rbp+8]; int
0x1800314fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031503  jmp     loc_180031683
0x180031508  xor     edi, edi
0x18003150a  cmp     [rbx+678h], edi
0x180031510  jbe     loc_180031683
0x180031516  lea     r14d, [rdi+1]
0x18003151a  lea     r15, aNonRoaming; "Non-Roaming"
0x180031521  mov     rax, [rbx+670h]
0x180031528  mov     r8, [rax+rdi*8]
0x18003152c  test    r8, r8
0x18003152f  jz      loc_180031674
0x180031535  add     rbp, [r8+18h]
0x180031539  lea     rdx, aUsersidWs; "UserSid %ws"
0x180031540  mov     r8, [r8]
0x180031543  mov     ecx, r14d; int
0x180031546  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003154b  mov     rax, [rbx+670h]
0x180031552  lea     rdx, aProfilepathWs; "ProfilePath %ws"
0x180031559  mov     ecx, r14d; int
0x18003155c  mov     r8, [rax+rdi*8]
0x180031560  mov     r8, [r8+8]
0x180031564  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031569  mov     rax, [rbx+670h]
0x180031570  lea     r9, aRoaming; "Roaming"
0x180031577  lea     rdx, aProfiletype0x0; "ProfileType 0x%08x (%ws)"
0x18003157e  mov     rcx, [rax+rdi*8]
0x180031582  mov     r8d, [rcx+10h]
0x180031586  cmp     r8d, r14d
0x180031589  mov     ecx, r14d; int
0x18003158c  cmovnz  r9, r15
0x180031590  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031595  mov     rax, [rbx+670h]
0x18003159c  lea     r9, aRoaming; "Roaming"
0x1800315a3  lea     rdx, aProfilestatus0; "ProfileStatus 0x%08x (%ws)"
0x1800315aa  mov     rcx, [rax+rdi*8]
0x1800315ae  mov     r8d, [rcx+14h]
0x1800315b2  cmp     r8d, r14d
0x1800315b5  mov     ecx, r14d; int
0x1800315b8  cmovnz  r9, r15
0x1800315bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800315c1  mov     rax, [rbx+670h]
0x1800315c8  lea     rdx, aProfiledirecto; "ProfileDirectorySize %I64d GB"
0x1800315cf  mov     ecx, r14d; int
0x1800315d2  mov     r8, [rax+rdi*8]
0x1800315d6  mov     r8, [r8+18h]
0x1800315da  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800315df  mov     rax, [rbx+670h]
0x1800315e6  lea     rdx, aLastaccesstime; "LastAccessTime High Date: 0x%08x, Low D"...
0x1800315ed  mov     ecx, r14d; int
0x1800315f0  mov     r8, [rax+rdi*8]
0x1800315f4  mov     r9d, [r8+20h]
0x1800315f8  mov     r8d, [r8+24h]
0x1800315fc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031601  mov     rax, [rbx+670h]
0x180031608  lea     rdx, [rsp+98h+LocalFileTime]; lpLocalFileTime
0x18003160d  xorps   xmm0, xmm0
0x180031610  mov     qword ptr [rsp+98h+LocalFileTime.dwLowDateTime], 0
0x180031619  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x18003161e  mov     rcx, [rax+rdi*8]
0x180031622  add     rcx, 20h ; ' '; lpFileTime
0x180031626  call    cs:__imp_FileTimeToLocalFileTime
0x18003162c  lea     rdx, [rsp+98h+SystemTime]; lpSystemTime
0x180031631  lea     rcx, [rsp+98h+LocalFileTime]; lpFileTime
0x180031636  call    cs:__imp_FileTimeToSystemTime
0x18003163c  movzx   ecx, [rsp+98h+SystemTime.wMinute]
0x180031641  movzx   edx, [rsp+98h+SystemTime.wHour]
0x180031646  movzx   r10d, [rsp+98h+SystemTime.wYear]
0x18003164c  movzx   r9d, [rsp+98h+SystemTime.wDay]
0x180031652  movzx   r8d, [rsp+98h+SystemTime.wMonth]
0x180031658  mov     [rsp+98h+var_68], ecx
0x18003165c  mov     ecx, r14d; int
0x18003165f  mov     [rsp+98h+var_70], edx
0x180031663  lea     rdx, aLastaccesstime_0; "LastAccessTime %02d/%02d/%04d %02d:%02d"
0x18003166a  mov     [rsp+98h+var_78], r10d
0x18003166f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031674  add     edi, r14d
0x180031677  cmp     edi, [rbx+678h]
0x18003167d  jb      loc_180031521
0x180031683  mov     rax, rbp
0x180031686  mov     rcx, [rsp+98h+var_40]
0x18003168b  xor     rcx, rsp; StackCookie
0x18003168e  call    __security_check_cookie
0x180031693  add     rsp, 68h
0x180031697  pop     r15
0x180031699  pop     r14
0x18003169b  pop     rdi
0x18003169c  pop     rsi
0x18003169d  pop     rbp
0x18003169e  pop     rbx
0x18003169f  retn
```

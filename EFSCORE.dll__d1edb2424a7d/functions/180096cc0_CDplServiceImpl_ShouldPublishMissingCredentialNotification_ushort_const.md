# CDplServiceImpl::ShouldPublishMissingCredentialNotification(ushort const *)

- ea: `0x180096cc0`
- end: `0x180096fda`
- name: `?ShouldPublishMissingCredentialNotification@CDplServiceImpl@@AEAAJPEBG@Z`
- size: `794`
- prototype: `int(CDplServiceImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180095594`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800857a8`
- `0x180096cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096deb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096deb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096f8d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180096f7e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180096f7e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180096ddf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180096ddf`
- `ntdll!RtlNtStatusToDosError` at `0x180096e46`
- `ntdll!RtlNtStatusToDosError` at `0x180096e46`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180096e36`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180096e36`
- `dsreg!DsrFreeJoinInfo` at `0x180096f6c`
- `dsreg!DsrFreeJoinInfo` at `0x180096f6c`
- `dsreg!DsrGetJoinInfo` at `0x180096edb`
- `dsreg!DsrGetJoinInfo` at `0x180096edb`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::ShouldPublishMissingCredentialNotification(
        CDplServiceImpl *this,
        const unsigned __int16 *a2)
{
  BOOL v2; // esi
  int v4; // ecx
  unsigned int JoinInfo; // ebx
  int v6; // r8d
  int v7; // ecx
  signed int LastError; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // edi
  signed int v11; // eax
  int v12; // ecx
  int v13; // edi
  char v15; // [rsp+20h] [rbp-20h]
  int v16; // [rsp+80h] [rbp+40h] BYREF
  int v17; // [rsp+84h] [rbp+44h]
  _DWORD *v18; // [rsp+90h] [rbp+50h] BYREF
  HANDLE hToken; // [rsp+98h] [rbp+58h] BYREF

  v17 = HIDWORD(this);
  v2 = 0;
  hToken = 0;
  v16 = 0;
  v18 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 96);
  if ( NtCurrentTeb()->IsImpersonating )
  {
    JoinInfo = -2147418113;
    v15 = 98;
    v6 = -2147418113;
LABEL_3:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 37, v15);
    goto LABEL_33;
  }
  if ( !a2 )
  {
    JoinInfo = -2147024809;
    v15 = 99;
    v6 = -2147024809;
    goto LABEL_3;
  }
  fnEfsLogTrace1Strings(v4, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 105);
  JoinInfo = EdpCredSvcQuerySessionUserTokenBySid(a2, &hToken);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              JoinInfo,
              37,
              105) < 0 )
    goto LABEL_33;
  if ( !hToken )
  {
    JoinInfo = -2147023888;
    v15 = 111;
    v6 = -2147023888;
    goto LABEL_3;
  }
  v2 = ImpersonateLoggedOnUser(hToken);
  if ( !v2 )
  {
    LastError = GetLastError();
    JoinInfo = LastError;
    if ( LastError > 0 )
      JoinInfo = (unsigned __int16)LastError | 0x80070000;
    v15 = 121;
    v6 = JoinInfo;
    goto LABEL_3;
  }
  fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 128);
  v9 = LsaLookupUserAccountType(0, &v16);
  JoinInfo = 0;
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = RtlNtStatusToDosError(v9);
    JoinInfo = v11;
    if ( !v11 || v11 == 317 )
    {
      JoinInfo = v10 | 0x10000000;
    }
    else if ( v11 > 0 )
    {
      JoinInfo = (unsigned __int16)v11 | 0x80070000;
    }
  }
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              JoinInfo,
              37,
              128) >= 0 )
  {
    v12 = v16;
    v13 = 0;
    if ( v16 == 1 || v16 == 4 )
    {
      fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 137);
      JoinInfo = DsrGetJoinInfo(0, &v18);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  JoinInfo,
                  37,
                  137) < 0 )
        goto LABEL_33;
      if ( v18 && (unsigned int)(*v18 - 1) <= 1 )
        v13 = 1;
      v12 = v16;
    }
    if ( (((v12 - 2) & 0xFFFFFFFC) != 0 || v12 == 4) && !v13 )
    {
      JoinInfo = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 37, 156);
    }
    else
    {
      JoinInfo = 0;
    }
  }
LABEL_33:
  if ( v18 )
  {
    DsrFreeJoinInfo();
    v18 = 0;
  }
  if ( v2 )
    RevertToSelf();
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    JoinInfo,
    37,
    178);
  return JoinInfo;
}

```

## disassembly

```asm
0x180096cc0  mov     [rsp-38h+arg_0], rcx
0x180096cc5  push    rbp
0x180096cc6  push    rbx
0x180096cc7  push    rsi
0x180096cc8  push    rdi
0x180096cc9  push    r12
0x180096ccb  push    r13
0x180096ccd  push    r14
0x180096ccf  mov     rbp, rsp
0x180096cd2  sub     rsp, 40h
0x180096cd6  xor     esi, esi
0x180096cd8  mov     [rbp+hToken], 0
0x180096ce0  mov     rbx, rdx
0x180096ce3  mov     dword ptr [rbp+arg_0], esi
0x180096ce6  lea     r14, sourceString
0x180096ced  mov     [rbp+arg_10], rsi
0x180096cf1  mov     r8, r14
0x180096cf4  mov     dword ptr [rsp+40h+var_20], 1F60h
0x180096cfc  lea     r12d, [rsi+25h]
0x180096d00  mov     r9d, r12d
0x180096d03  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180096d0a  call    fnEfsLogTrace1Strings
0x180096d0f  mov     eax, gs:179Ch
0x180096d17  mov     r9d, r12d
0x180096d1a  test    eax, eax
0x180096d1c  jz      short loc_180096D49
0x180096d1e  mov     ebx, 8000FFFFh
0x180096d23  mov     dword ptr [rsp+40h+var_20], 1F62h
0x180096d2b  mov     r8d, 8000FFFFh
0x180096d31  lea     rdx, EFS_TRACE_ERROR
0x180096d38  mov     rcx, cs:g_hPublisher
0x180096d3f  call    fnEfsLogTrace1
0x180096d44  jmp     loc_180096F63
0x180096d49  test    rbx, rbx
0x180096d4c  jnz     short loc_180096D63
0x180096d4e  mov     ebx, 80070057h
0x180096d53  mov     dword ptr [rsp+40h+var_20], 1F63h
0x180096d5b  mov     r8d, 80070057h
0x180096d61  jmp     short loc_180096D31
0x180096d63  mov     edi, 1F69h
0x180096d68  lea     rdx, EFS_TRACE_START_EVENT
0x180096d6f  mov     r8, r14
0x180096d72  mov     dword ptr [rsp+40h+var_20], edi
0x180096d76  call    fnEfsLogTrace1Strings
0x180096d7b  lea     rdx, [rbp+hToken]; void **
0x180096d7f  mov     rcx, rbx; unsigned __int16 *
0x180096d82  call    ?EdpCredSvcQuerySessionUserTokenBySid@@YAJPEBGPEAPEAX@Z; EdpCredSvcQuerySessionUserTokenBySid(ushort const *,void * *)
0x180096d87  mov     rcx, cs:g_hPublisher
0x180096d8e  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180096d95  mov     [rsp+40h+var_10], edi
0x180096d99  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180096da0  mov     [rsp+40h+var_18], r12d
0x180096da5  mov     r9, r14
0x180096da8  mov     dword ptr [rsp+40h+var_20], eax
0x180096dac  mov     ebx, eax
0x180096dae  call    fnEfsLogTrace1String1Dword
0x180096db3  test    eax, eax
0x180096db5  js      loc_180096F63
0x180096dbb  mov     rcx, [rbp+hToken]; hToken
0x180096dbf  test    rcx, rcx
0x180096dc2  jnz     short loc_180096DDF
0x180096dc4  mov     ebx, 800703F0h
0x180096dc9  mov     dword ptr [rsp+40h+var_20], 1F6Fh
0x180096dd1  mov     r9d, r12d
0x180096dd4  mov     r8d, 800703F0h
0x180096dda  jmp     loc_180096D31
0x180096ddf  call    cs:__imp_ImpersonateLoggedOnUser
0x180096de5  mov     esi, eax
0x180096de7  test    eax, eax
0x180096de9  jnz     short loc_180096E13
0x180096deb  call    cs:__imp_GetLastError
0x180096df1  mov     ebx, eax
0x180096df3  test    eax, eax
0x180096df5  jle     short loc_180096E00
0x180096df7  movzx   ebx, ax
0x180096dfa  or      ebx, 80070000h
0x180096e00  mov     dword ptr [rsp+40h+var_20], 1F79h
0x180096e08  mov     r9d, r12d
0x180096e0b  mov     r8d, ebx
0x180096e0e  jmp     loc_180096D31
0x180096e13  mov     r13d, 1F80h
0x180096e19  lea     rdx, EFS_TRACE_START_EVENT
0x180096e20  mov     r9d, r12d
0x180096e23  mov     dword ptr [rsp+40h+var_20], r13d
0x180096e28  mov     r8, r14
0x180096e2b  call    fnEfsLogTrace1Strings
0x180096e30  lea     rdx, [rbp+arg_0]
0x180096e34  xor     ecx, ecx
0x180096e36  call    cs:__imp_LsaLookupUserAccountType
0x180096e3c  xor     ebx, ebx
0x180096e3e  mov     edi, eax
0x180096e40  test    eax, eax
0x180096e42  jns     short loc_180096E6E
0x180096e44  mov     ecx, eax; Status
0x180096e46  call    cs:__imp_RtlNtStatusToDosError
0x180096e4c  mov     ebx, eax
0x180096e4e  test    eax, eax
0x180096e50  jz      short loc_180096E68
0x180096e52  cmp     eax, 13Dh
0x180096e57  jz      short loc_180096E68
0x180096e59  test    eax, eax
0x180096e5b  jle     short loc_180096E6E
0x180096e5d  movzx   ebx, ax
0x180096e60  or      ebx, 80070000h
0x180096e66  jmp     short loc_180096E6E
0x180096e68  mov     ebx, edi
0x180096e6a  bts     ebx, 1Ch
0x180096e6e  mov     rcx, cs:g_hPublisher
0x180096e75  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180096e7c  mov     [rsp+40h+var_10], r13d
0x180096e81  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180096e88  mov     [rsp+40h+var_18], r12d
0x180096e8d  mov     r9, r14
0x180096e90  mov     dword ptr [rsp+40h+var_20], ebx
0x180096e94  call    fnEfsLogTrace1String1Dword
0x180096e99  test    eax, eax
0x180096e9b  js      loc_180096F63
0x180096ea1  mov     ecx, dword ptr [rbp+arg_0]
0x180096ea4  xor     edi, edi
0x180096ea6  lea     r13d, [rdi+1]
0x180096eaa  cmp     ecx, r13d
0x180096ead  jz      short loc_180096EB4
0x180096eaf  cmp     ecx, 4
0x180096eb2  jnz     short loc_180096F31
0x180096eb4  mov     r14d, 1F89h
0x180096eba  lea     r8, sourceString
0x180096ec1  mov     r9d, r12d
0x180096ec4  mov     dword ptr [rsp+40h+var_20], r14d
0x180096ec9  lea     rdx, EFS_TRACE_START_EVENT
0x180096ed0  call    fnEfsLogTrace1Strings
0x180096ed5  lea     rdx, [rbp+arg_10]
0x180096ed9  xor     ecx, ecx
0x180096edb  call    cs:__imp_DsrGetJoinInfo
0x180096ee1  mov     rcx, cs:g_hPublisher
0x180096ee8  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180096eef  mov     [rsp+40h+var_10], r14d
0x180096ef4  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180096efb  lea     r14, sourceString
0x180096f02  mov     [rsp+40h+var_18], r12d
0x180096f07  mov     r9, r14
0x180096f0a  mov     dword ptr [rsp+40h+var_20], eax
0x180096f0e  mov     ebx, eax
0x180096f10  call    fnEfsLogTrace1String1Dword
0x180096f15  test    eax, eax
0x180096f17  js      short loc_180096F63
0x180096f19  mov     rcx, [rbp+arg_10]
0x180096f1d  test    rcx, rcx
0x180096f20  jz      short loc_180096F2E
0x180096f22  mov     eax, [rcx]
0x180096f24  sub     eax, r13d
0x180096f27  cmp     eax, r13d
0x180096f2a  cmovbe  edi, r13d
0x180096f2e  mov     ecx, dword ptr [rbp+arg_0]
0x180096f31  lea     eax, [rcx-2]
0x180096f34  test    eax, 0FFFFFFFCh
0x180096f39  jnz     short loc_180096F40
0x180096f3b  cmp     ecx, 4
0x180096f3e  jnz     short loc_180096F61
0x180096f40  test    edi, edi
0x180096f42  jnz     short loc_180096F61
0x180096f44  mov     ebx, r13d
0x180096f47  mov     dword ptr [rsp+40h+var_20], 1F9Ch
0x180096f4f  mov     r9d, r12d
0x180096f52  lea     rdx, EFS_TRACE_STATUS
0x180096f59  mov     r8d, r13d
0x180096f5c  jmp     loc_180096D38
0x180096f61  xor     ebx, ebx
0x180096f63  mov     rcx, [rbp+arg_10]
0x180096f67  test    rcx, rcx
0x180096f6a  jz      short loc_180096F7A
0x180096f6c  call    cs:__imp_DsrFreeJoinInfo
0x180096f72  mov     [rbp+arg_10], 0
0x180096f7a  test    esi, esi
0x180096f7c  jz      short loc_180096F84
0x180096f7e  call    cs:__imp_RevertToSelf
0x180096f84  mov     rcx, [rbp+hToken]; hObject
0x180096f88  test    rcx, rcx
0x180096f8b  jz      short loc_180096F9B
0x180096f8d  call    cs:__imp_CloseHandle
0x180096f93  mov     [rbp+hToken], 0
0x180096f9b  mov     rcx, cs:g_hPublisher
0x180096fa2  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180096fa9  mov     [rsp+40h+var_10], 1FB2h
0x180096fb1  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180096fb8  mov     [rsp+40h+var_18], r12d
0x180096fbd  mov     r9, r14
0x180096fc0  mov     dword ptr [rsp+40h+var_20], ebx
0x180096fc4  call    fnEfsLogTrace1String1Dword
0x180096fc9  mov     eax, ebx
0x180096fcb  add     rsp, 40h
0x180096fcf  pop     r14
0x180096fd1  pop     r13
0x180096fd3  pop     r12
0x180096fd5  pop     rdi
0x180096fd6  pop     rsi
0x180096fd7  pop     rbx
0x180096fd8  pop     rbp
0x180096fd9  retn
```

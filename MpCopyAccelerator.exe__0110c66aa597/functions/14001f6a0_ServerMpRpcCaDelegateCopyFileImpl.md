# ServerMpRpcCaDelegateCopyFileImpl

- ea: `0x14001f6a0`
- end: `0x14001fbd0`
- name: `ServerMpRpcCaDelegateCopyFileImpl`
- size: `1328`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, int, const WCHAR *, WCHAR *pwszNewFileName, DWORD, HRESULT *, DWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001fc90`
- `0x14001fce0`

## callees

- `0x140005c20`
- `0x14001da70`
- `0x14001e268`
- `0x14001e5a0`
- `0x14001eee0`
- `0x14001f304`
- `0x14001f6a0`
- `0x140020290`
- `0x140020654`
- `0x140020748`
- `0x140022c00`
- `0x14002380c`
- `0x1400241f8`

## import_xrefs

- `KERNEL32!CopyFileExW` at `0x14001f9b3`
- `KERNEL32!CopyFileExW` at `0x14001f9b3`
- `KERNEL32!CopyFile2` at `0x14001f942`
- `KERNEL32!CopyFile2` at `0x14001f942`
- `KERNEL32!AcquireSRWLockShared` at `0x14001f761`
- `KERNEL32!AcquireSRWLockShared` at `0x14001f761`
- `KERNEL32!ReleaseSRWLockShared` at `0x14001f8f6`
- `KERNEL32!ReleaseSRWLockShared` at `0x14001fa10`
- `KERNEL32!ReleaseSRWLockShared` at `0x14001f8f6`
- `KERNEL32!ReleaseSRWLockShared` at `0x14001fa10`
- `KERNEL32!GetLastError` at `0x14001f94a`
- `KERNEL32!GetLastError` at `0x14001f9bd`
- `KERNEL32!GetLastError` at `0x14001f94a`
- `KERNEL32!GetLastError` at `0x14001f9bd`
- `KERNEL32!WaitForSingleObject` at `0x14001f733`
- `KERNEL32!WaitForSingleObject` at `0x14001f733`
- `RPCRT4!RpcImpersonateClient` at `0x14001f802`
- `RPCRT4!RpcImpersonateClient` at `0x14001f802`

## string_xrefs

- `0x14001f7cb`: `ServerMpRpcCaDelegateCopyFileImpl was denied. Source:%s, Destination:%s, return value: %d\n`
- `0x14001fb80`: `ServerMpRpcCaDelegateCopyFileImpl was denied. Source:%s, Destination:%s, return value: %d\n`
- `0x14001f8b8`: `Unsupported Copy API has been requested. Source:%s, Destination:%s, E_INVALIDARG (%d)\n`
- `0x14001fb18`: `Copy Result - %ls:%ls, Source:%s, Destination:%s, Flags:%lu, ErrorCode:%lu\n`

## pseudocode

```c
__int64 __fastcall ServerMpRpcCaDelegateCopyFileImpl(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        int a3,
        const WCHAR *a4,
        WCHAR *pwszNewFileName,
        DWORD a6,
        HRESULT *a7,
        DWORD *a8)
{
  HANDLE *Instance; // rax
  DWORD v12; // eax
  unsigned int v13; // edi
  DWORD LastError; // r13d
  struct CCopyControl *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  RPC_STATUS v19; // eax
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  unsigned int v22; // ebx
  HRESULT v24; // ebx
  __int64 v25; // rdx
  __int64 *v26; // r9
  DWORD (__stdcall *v27)(LARGE_INTEGER, LARGE_INTEGER, LARGE_INTEGER, LARGE_INTEGER, DWORD, DWORD, HANDLE, HANDLE, LPVOID); // r8
  struct CCopyControl *v28; // rax
  volatile signed __int32 *v29; // rcx
  __int64 v30; // rbx
  DWORD dwCopyFlags[2]; // [rsp+28h] [rbp-A1h]
  __int64 v32; // [rsp+30h] [rbp-99h]
  unsigned int v33; // [rsp+50h] [rbp-79h]
  COPYFILE2_EXTENDED_PARAMETERS pExtendedParameters; // [rsp+80h] [rbp-49h] BYREF
  WINBOOL pbCancel; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v37[2]; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v38; // [rsp+B8h] [rbp-11h] BYREF

  if ( !a4 || !pwszNewFileName || !a7 || !a8 || a3 > 3 || a6 > 1 )
    return 2147942487LL;
  *a8 = 0;
  *a7 = 0;
  Instance = (HANDLE *)CCopyControl::GetInstance();
  v12 = WaitForSingleObject(*Instance, 0);
  if ( !v12 )
  {
    v13 = 1;
LABEL_79:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, v13);
    if ( dword_14003DB98 )
    {
      MpCmdLogWithTimePrintf(
        L"ServerMpRpcCaDelegateCopyFileImpl was denied. Source:%s, Destination:%s, return value: %d\n",
        a4,
        pwszNewFileName,
        v13);
      if ( qword_14003DBC8 )
        CLogHandle::Flush(qword_14003DBC8);
    }
    return 2147500037LL;
  }
  if ( v12 != 258 )
  {
    v13 = 2;
    goto LABEL_79;
  }
  LastError = 0;
  AcquireSRWLockShared(&stru_14003DBA0);
  pbCancel = 0;
  v15 = CCopyControl::GetInstance();
  v16 = CCopyControl::EnterCopyOperation(v15, &pbCancel);
  v17 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, v16);
    if ( dword_14003DB98 )
    {
      MpCmdLogWithTimePrintf(
        L"ServerMpRpcCaDelegateCopyFileImpl was denied. Source:%s, Destination:%s, return value: %d\n",
        a4,
        pwszNewFileName,
        v17);
      if ( qword_14003DBC8 )
        CLogHandle::Flush(qword_14003DBC8);
    }
    v18 = -2147467259;
LABEL_36:
    ReleaseSRWLockShared(&stru_14003DBA0);
    return v18;
  }
  LOBYTE(v38) = 0;
  *((_QWORD *)&v38 + 1) = &pbCancel;
  v18 = 0;
  v19 = RpcImpersonateClient(BindingHandle);
  if ( !v19 )
    goto LABEL_22;
  v18 = v19 | 0x80010000;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, v18);
LABEL_22:
    v21 = WPP_GLOBAL_Control;
  }
  v33 = v18;
  if ( (v18 & 0x80000000) != 0 )
  {
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
      WPP_SF_d(v21[2], 39, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, v18);
    lambda_fc2c71fad86c10a918c62dafdb315073_::operator()((char *)&v38 + 8, v20);
    goto LABEL_36;
  }
  v37[1] = (__int64)BindingHandle;
  v22 = 0;
  LOBYTE(v37[0]) = 0;
  if ( (a3 & 0xFFFFFFFD) != 0 )
  {
    if ( ((a3 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( dword_14003DB98 )
      {
        _mm_lfence();
        MpCmdLogWithTimePrintf(
          L"Unsupported Copy API has been requested. Source:%s, Destination:%s, E_INVALIDARG (%d)\n",
          a4,
          pwszNewFileName,
          (unsigned int)a3);
        if ( qword_14003DBC8 )
          CLogHandle::Flush(qword_14003DBC8);
      }
      if ( !v33 )
        MpRpcRevertToSelf();
      lambda_fc2c71fad86c10a918c62dafdb315073_::operator()((char *)&v38 + 8, v20);
      v18 = -2147024809;
      goto LABEL_36;
    }
    pExtendedParameters.dwSize = 32;
    pExtendedParameters.dwCopyFlags = a6;
    pExtendedParameters.pfCancel = &pbCancel;
    pExtendedParameters.pProgressRoutine = 0;
    pExtendedParameters.pvCallbackContext = 0;
    if ( a3 == 3 )
    {
      pExtendedParameters.pProgressRoutine = (PCOPYFILE2_PROGRESS_ROUTINE)CopyFile2ProgressRoutine;
      pExtendedParameters.pvCallbackContext = v37;
    }
    v24 = CopyFile2(a4, pwszNewFileName, &pExtendedParameters);
    LastError = GetLastError();
    *a7 = v24;
    *a8 = LastError;
    v25 = 0;
    if ( v24 >= 0 )
    {
      v22 = 0;
    }
    else if ( v24 == -2147023661 )
    {
      v22 = LOBYTE(v37[0]) != 0 ? 3 : 1;
    }
    else
    {
      v22 = 2;
    }
  }
  else
  {
    v26 = v37;
    if ( a3 != 2 )
      v26 = 0;
    v27 = (DWORD (__stdcall *)(LARGE_INTEGER, LARGE_INTEGER, LARGE_INTEGER, LARGE_INTEGER, DWORD, DWORD, HANDLE, HANDLE, LPVOID))CopyFileExWProgressRoutine;
    if ( a3 != 2 )
      v27 = 0;
    if ( !CopyFileExW(a4, pwszNewFileName, v27, v26, &pbCancel, a6) )
    {
      LastError = GetLastError();
      *a8 = LastError;
      *a7 = -2147467259;
      if ( LastError == 1235 )
        v22 = LOBYTE(v37[0]) != 0 ? 3 : 1;
      else
        v22 = 2;
    }
    v25 = 0;
  }
  _mm_lfence();
  if ( !v33 )
    MpRpcRevertToSelf();
  lambda_fc2c71fad86c10a918c62dafdb315073_::operator()((char *)&v38 + 8, v25);
  ReleaseSRWLockShared(&stru_14003DBA0);
  v28 = CCopyControl::GetInstance();
  switch ( a3 )
  {
    case 0:
      v29 = (volatile signed __int32 *)((char *)v28 + 32);
LABEL_63:
      if ( v29 )
      {
        if ( v22 )
        {
          if ( v22 == 1 )
          {
            _InterlockedIncrement(v29 + 1);
          }
          else if ( v22 == 2 )
          {
            _InterlockedIncrement(v29);
          }
          else
          {
            _InterlockedIncrement(v29 + 2);
          }
        }
        else
        {
          _InterlockedIncrement(v29 + 3);
        }
      }
      break;
    case 1:
      v29 = (volatile signed __int32 *)((char *)v28 + 64);
      goto LABEL_63;
    case 2:
      v29 = (volatile signed __int32 *)((char *)v28 + 48);
      goto LABEL_63;
    case 3:
      v29 = (volatile signed __int32 *)((char *)v28 + 80);
      goto LABEL_63;
  }
  SendThrottledDetailsTelemetry((unsigned int *)BindingHandle, (CommonUtil *)pwszNewFileName, LastError, a6);
  v38 = 0;
  MpCopyFileApiToStr(&v38, (unsigned int)a3);
  *(_OWORD *)v37 = 0;
  CopyOperationResultToStr(v37, v22);
  v30 = v37[0];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SSSSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v37[0], (__int64)a4, (__int64)pwszNewFileName, a6, LastError);
  if ( dword_14003DB98 )
  {
    LODWORD(v32) = LastError;
    dwCopyFlags[0] = a6;
    MpCmdLogWithTimePrintf(
      L"Copy Result - %ls:%ls, Source:%s, Destination:%s, Flags:%lu, ErrorCode:%lu\n",
      (_QWORD)v38,
      v30,
      a4,
      pwszNewFileName,
      *(_QWORD *)dwCopyFlags,
      v32);
    if ( qword_14003DBC8 )
      CLogHandle::Flush(qword_14003DBC8);
  }
  return 0;
}

```

## disassembly

```asm
0x14001f6a0  mov     [rsp-8+arg_8], rbx
0x14001f6a5  push    rbp
0x14001f6a6  push    rsi
0x14001f6a7  push    rdi
0x14001f6a8  push    r12
0x14001f6aa  push    r13
0x14001f6ac  push    r14
0x14001f6ae  push    r15
0x14001f6b0  lea     rbp, [rsp-7]
0x14001f6b5  sub     rsp, 0D0h
0x14001f6bc  mov     rax, cs:__security_cookie
0x14001f6c3  xor     rax, rsp
0x14001f6c6  mov     [rbp+37h+var_38], rax
0x14001f6ca  mov     r12, r9
0x14001f6cd  mov     esi, r8d
0x14001f6d0  mov     r14, rcx
0x14001f6d3  mov     [rbp+37h+var_A0], rcx
0x14001f6d7  mov     r15, [rbp+37h+pwszNewFileName]
0x14001f6db  mov     rdi, [rbp+37h+arg_30]
0x14001f6df  mov     [rbp+37h+var_98], rdi
0x14001f6e3  mov     rax, [rbp+37h+arg_38]
0x14001f6e7  mov     [rbp+37h+var_A8], rax
0x14001f6eb  xor     ebx, ebx
0x14001f6ed  test    r9, r9
0x14001f6f0  jz      loc_14001FBA4
0x14001f6f6  test    r15, r15
0x14001f6f9  jz      loc_14001FBA4
0x14001f6ff  test    rdi, rdi
0x14001f702  jz      loc_14001FBA4
0x14001f708  test    rax, rax
0x14001f70b  jz      loc_14001FBA4
0x14001f711  cmp     r8d, 3
0x14001f715  jg      loc_14001FBA4
0x14001f71b  cmp     [rbp+37h+arg_28], 1
0x14001f71f  ja      loc_14001FBA4
0x14001f725  mov     [rax], ebx
0x14001f727  mov     [rdi], ebx
0x14001f729  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001f72e  xor     edx, edx; dwMilliseconds
0x14001f730  mov     rcx, [rax]; hHandle
0x14001f733  call    cs:__imp_WaitForSingleObject
0x14001f739  test    eax, eax
0x14001f73b  jz      loc_14001FB39
0x14001f741  cmp     eax, 102h
0x14001f746  jz      short loc_14001F750
0x14001f748  lea     edi, [rbx+2]
0x14001f74b  jmp     loc_14001FB3E
0x14001f750  mov     r13d, ebx
0x14001f753  lea     rax, stru_14003DBA0
0x14001f75a  mov     [rbp+37h+var_90], rax
0x14001f75e  mov     rcx, rax; SRWLock
0x14001f761  call    cs:__imp_AcquireSRWLockShared
0x14001f767  mov     [rbp+37h+var_88], 1
0x14001f76b  mov     [rbp+37h+var_60], ebx
0x14001f76e  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001f773  lea     rdx, [rbp+37h+var_60]
0x14001f777  mov     rcx, rax
0x14001f77a  call    ?EnterCopyOperation@CCopyControl@@QEAA?AW4eEnterCopyResult@1@PEAUCancellationToken@1@@Z; CCopyControl::EnterCopyOperation(CCopyControl::CancellationToken *)
0x14001f77f  mov     ebx, eax
0x14001f781  xor     ecx, ecx
0x14001f783  test    eax, eax
0x14001f785  jz      short loc_14001F7F2
0x14001f787  lea     r14, WPP_GLOBAL_Control
0x14001f78e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f795  cmp     rcx, r14
0x14001f798  jz      short loc_14001F7B8
0x14001f79a  test    byte ptr [rcx+1Ch], 1
0x14001f79e  jz      short loc_14001F7B8
0x14001f7a0  mov     edx, 26h ; '&'
0x14001f7a5  mov     r9d, eax
0x14001f7a8  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001f7af  mov     rcx, [rcx+10h]
0x14001f7b3  call    WPP_SF_d
0x14001f7b8  xor     edi, edi
0x14001f7ba  cmp     cs:dword_14003DB98, edi
0x14001f7c0  jz      short loc_14001F7E8
0x14001f7c2  mov     r9d, ebx
0x14001f7c5  mov     r8, r15
0x14001f7c8  mov     rdx, r12
0x14001f7cb  lea     rcx, aServermprpccad; "ServerMpRpcCaDelegateCopyFileImpl was d"...
0x14001f7d2  call    ?MpCmdLogWithTimePrintf@@YAXPEB_WZZ; MpCmdLogWithTimePrintf(wchar_t const *,...)
0x14001f7d7  mov     rcx, cs:qword_14003DBC8; this
0x14001f7de  test    rcx, rcx
0x14001f7e1  jz      short loc_14001F7E8
0x14001f7e3  call    ?Flush@CLogHandle@@QEAAJXZ; CLogHandle::Flush(void)
0x14001f7e8  mov     ebx, 80004005h
0x14001f7ed  jmp     loc_14001F8EF
0x14001f7f2  mov     byte ptr [rbp+37h+var_48], cl
0x14001f7f5  lea     rax, [rbp+37h+var_60]
0x14001f7f9  mov     qword ptr [rbp+37h+var_48+8], rax
0x14001f7fd  mov     ebx, ecx
0x14001f7ff  mov     rcx, r14; BindingHandle
0x14001f802  call    cs:__imp_RpcImpersonateClient
0x14001f808  lea     r14, WPP_GLOBAL_Control
0x14001f80f  test    eax, eax
0x14001f811  jz      short loc_14001F845
0x14001f813  mov     ebx, eax
0x14001f815  or      ebx, 80010000h
0x14001f81b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f822  cmp     rcx, r14
0x14001f825  jz      short loc_14001F84C
0x14001f827  test    byte ptr [rcx+1Ch], 1
0x14001f82b  jz      short loc_14001F84C
0x14001f82d  mov     edx, 19h
0x14001f832  mov     r9d, ebx
0x14001f835  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x14001f83c  mov     rcx, [rcx+10h]
0x14001f840  call    WPP_SF_d
0x14001f845  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f84c  mov     [rbp+37h+var_B0], ebx
0x14001f84f  test    ebx, ebx
0x14001f851  jns     short loc_14001F883
0x14001f853  cmp     rcx, r14
0x14001f856  jz      short loc_14001F877
0x14001f858  test    byte ptr [rcx+1Ch], 1
0x14001f85c  jz      short loc_14001F877
0x14001f85e  mov     edx, 27h ; '''
0x14001f863  mov     r9d, ebx
0x14001f866  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001f86d  mov     rcx, [rcx+10h]
0x14001f871  call    WPP_SF_d
0x14001f876  nop
0x14001f877  lea     rcx, [rbp+37h+var_48+8]
0x14001f87b  call    _lambda_fc2c71fad86c10a918c62dafdb315073___operator__
0x14001f880  nop
0x14001f881  jmp     short loc_14001F8EF
0x14001f883  mov     rax, [rbp+37h+var_A0]
0x14001f887  mov     [rbp+37h+var_58+8], rax
0x14001f88b  xor     ebx, ebx
0x14001f88d  mov     byte ptr [rbp+37h+var_58], bl
0x14001f890  mov     ecx, 0FFFFFFFDh
0x14001f895  test    ecx, esi
0x14001f897  jz      loc_14001F983
0x14001f89d  lea     eax, [rsi-1]
0x14001f8a0  test    ecx, eax
0x14001f8a2  jz      short loc_14001F903
0x14001f8a4  cmp     cs:dword_14003DB98, ebx
0x14001f8aa  jz      short loc_14001F8D5
0x14001f8ac  lfence
0x14001f8af  mov     r9d, esi
0x14001f8b2  mov     r8, r15
0x14001f8b5  mov     rdx, r12
0x14001f8b8  lea     rcx, aUnsupportedCop; "Unsupported Copy API has been requested"...
0x14001f8bf  call    ?MpCmdLogWithTimePrintf@@YAXPEB_WZZ; MpCmdLogWithTimePrintf(wchar_t const *,...)
0x14001f8c4  mov     rcx, cs:qword_14003DBC8; this
0x14001f8cb  test    rcx, rcx
0x14001f8ce  jz      short loc_14001F8D5
0x14001f8d0  call    ?Flush@CLogHandle@@QEAAJXZ; CLogHandle::Flush(void)
0x14001f8d5  cmp     [rbp+37h+var_B0], ebx
0x14001f8d8  jnz     short loc_14001F8E0
0x14001f8da  call    ?MpRpcRevertToSelf@@YAXXZ; MpRpcRevertToSelf(void)
0x14001f8df  nop
0x14001f8e0  lea     rcx, [rbp+37h+var_48+8]
0x14001f8e4  call    _lambda_fc2c71fad86c10a918c62dafdb315073___operator__
0x14001f8e9  nop
0x14001f8ea  mov     ebx, 80070057h
0x14001f8ef  lea     rcx, stru_14003DBA0; SRWLock
0x14001f8f6  call    cs:__imp_ReleaseSRWLockShared
0x14001f8fc  mov     eax, ebx
0x14001f8fe  jmp     loc_14001FBA9
0x14001f903  mov     [rbp+37h+pExtendedParameters.dwSize], 20h ; ' '
0x14001f90a  mov     eax, [rbp+37h+arg_28]
0x14001f90d  mov     [rbp+37h+pExtendedParameters.dwCopyFlags], eax
0x14001f910  lea     rax, [rbp+37h+var_60]
0x14001f914  mov     [rbp+37h+pExtendedParameters.pfCancel], rax
0x14001f918  mov     [rbp+37h+pExtendedParameters.pProgressRoutine], rbx
0x14001f91c  mov     [rbp+37h+pExtendedParameters.pvCallbackContext], rbx
0x14001f920  cmp     esi, 3
0x14001f923  jnz     short loc_14001F938
0x14001f925  lea     rax, ?CopyFile2ProgressRoutine@@YA?AW4_COPYFILE2_MESSAGE_ACTION@@PEBUCOPYFILE2_MESSAGE@@PEAX@Z; CopyFile2ProgressRoutine(COPYFILE2_MESSAGE const *,void *)
0x14001f92c  mov     [rbp+37h+pExtendedParameters.pProgressRoutine], rax
0x14001f930  lea     rax, [rbp+37h+var_58]
0x14001f934  mov     [rbp+37h+pExtendedParameters.pvCallbackContext], rax
0x14001f938  lea     r8, [rbp+37h+pExtendedParameters]; pExtendedParameters
0x14001f93c  mov     rdx, r15; pwszNewFileName
0x14001f93f  mov     rcx, r12; pwszExistingFileName
0x14001f942  call    cs:__imp_CopyFile2
0x14001f948  mov     ebx, eax
0x14001f94a  call    cs:__imp_GetLastError
0x14001f950  mov     r13d, eax
0x14001f953  mov     [rdi], ebx
0x14001f955  mov     rax, [rbp+37h+var_A8]
0x14001f959  mov     [rax], r13d
0x14001f95c  xor     edx, edx
0x14001f95e  test    ebx, ebx
0x14001f960  jns     short loc_14001F97F
0x14001f962  cmp     ebx, 800704D3h
0x14001f968  jnz     short loc_14001F978
0x14001f96a  mov     cl, byte ptr [rbp+37h+var_58]
0x14001f96d  neg     cl
0x14001f96f  sbb     ebx, ebx
0x14001f971  and     ebx, 2
0x14001f974  inc     ebx
0x14001f976  jmp     short loc_14001F9F1
0x14001f978  mov     ebx, 2
0x14001f97d  jmp     short loc_14001F9F1
0x14001f97f  mov     ebx, edx
0x14001f981  jmp     short loc_14001F9F1
0x14001f983  lea     r9, [rbp+37h+var_58]
0x14001f987  mov     edi, 2
0x14001f98c  cmp     esi, edi
0x14001f98e  cmovnz  r9, rbx; lpData
0x14001f992  lea     r8, ?CopyFileExWProgressRoutine@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z; CopyFileExWProgressRoutine(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x14001f999  cmovnz  r8, rbx; lpProgressRoutine
0x14001f99d  mov     eax, [rbp+37h+arg_28]
0x14001f9a0  mov     [rsp+100h+dwCopyFlags], eax; dwCopyFlags
0x14001f9a4  lea     rax, [rbp+37h+var_60]
0x14001f9a8  mov     [rsp+100h+pbCancel], rax; pbCancel
0x14001f9ad  mov     rdx, r15; lpNewFileName
0x14001f9b0  mov     rcx, r12; lpExistingFileName
0x14001f9b3  call    cs:__imp_CopyFileExW
0x14001f9b9  test    eax, eax
0x14001f9bb  jnz     short loc_14001F9EF
0x14001f9bd  call    cs:__imp_GetLastError
0x14001f9c3  mov     r13d, eax
0x14001f9c6  mov     rax, [rbp+37h+var_A8]
0x14001f9ca  mov     [rax], r13d
0x14001f9cd  mov     rax, [rbp+37h+var_98]
0x14001f9d1  mov     dword ptr [rax], 80004005h
0x14001f9d7  cmp     r13d, 4D3h
0x14001f9de  jnz     short loc_14001F9ED
0x14001f9e0  mov     al, byte ptr [rbp+37h+var_58]
0x14001f9e3  neg     al
0x14001f9e5  sbb     ebx, ebx
0x14001f9e7  and     ebx, edi
0x14001f9e9  inc     ebx
0x14001f9eb  jmp     short loc_14001F9EF
0x14001f9ed  mov     ebx, edi
0x14001f9ef  xor     edx, edx
0x14001f9f1  lfence
0x14001f9f4  cmp     [rbp+37h+var_B0], edx
0x14001f9f7  jnz     short loc_14001F9FF
0x14001f9f9  call    ?MpRpcRevertToSelf@@YAXXZ; MpRpcRevertToSelf(void)
0x14001f9fe  nop
0x14001f9ff  lea     rcx, [rbp+37h+var_48+8]
0x14001fa03  call    _lambda_fc2c71fad86c10a918c62dafdb315073___operator__
0x14001fa08  nop
0x14001fa09  lea     rcx, stru_14003DBA0; SRWLock
0x14001fa10  call    cs:__imp_ReleaseSRWLockShared
0x14001fa16  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001fa1b  mov     edx, esi
0x14001fa1d  test    esi, esi
0x14001fa1f  jz      short loc_14001FA42
0x14001fa21  sub     edx, 1
0x14001fa24  jz      short loc_14001FA3C
0x14001fa26  sub     edx, 1
0x14001fa29  jz      short loc_14001FA36
0x14001fa2b  cmp     edx, 1
0x14001fa2e  jnz     short loc_14001FA75
0x14001fa30  lea     rcx, [rax+50h]
0x14001fa34  jmp     short loc_14001FA46
0x14001fa36  lea     rcx, [rax+30h]
0x14001fa3a  jmp     short loc_14001FA46
0x14001fa3c  lea     rcx, [rax+40h]
0x14001fa40  jmp     short loc_14001FA46
0x14001fa42  lea     rcx, [rax+20h]
0x14001fa46  test    rcx, rcx
0x14001fa49  jz      short loc_14001FA75
0x14001fa4b  mov     edx, ebx
0x14001fa4d  test    ebx, ebx
0x14001fa4f  jz      short loc_14001FA71
0x14001fa51  sub     edx, 1
0x14001fa54  jz      short loc_14001FA6B
0x14001fa56  sub     edx, 1
0x14001fa59  jz      short loc_14001FA66
0x14001fa5b  cmp     edx, 1
0x14001fa5e  jnz     short loc_14001FA75
0x14001fa60  lock inc dword ptr [rcx+8]
0x14001fa64  jmp     short loc_14001FA75
0x14001fa66  lock inc dword ptr [rcx]
0x14001fa69  jmp     short loc_14001FA75
0x14001fa6b  lock inc dword ptr [rcx+4]
0x14001fa6f  jmp     short loc_14001FA75
0x14001fa71  lock inc dword ptr [rcx+0Ch]
0x14001fa75  mov     edi, [rbp+37h+arg_28]
0x14001fa78  mov     dword ptr [rsp+100h+var_D0], edi; int
0x14001fa7c  mov     [rsp+100h+dwCopyFlags], r13d; int
0x14001fa81  mov     [rsp+100h+pbCancel], r15; CommonUtil *
0x14001fa86  mov     r9, r12
0x14001fa89  mov     r8d, ebx
0x14001fa8c  mov     edx, esi
0x14001fa8e  mov     rcx, [rbp+37h+var_A0]; unsigned int *
0x14001fa92  call    SendThrottledDetailsTelemetry
0x14001fa97  xorps   xmm0, xmm0
0x14001fa9a  movups  [rbp+37h+var_48], xmm0
0x14001fa9e  mov     edx, esi
0x14001faa0  lea     rcx, [rbp+37h+var_48]
0x14001faa4  call    MpCopyFileApiToStr
0x14001faa9  xorps   xmm0, xmm0
0x14001faac  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x14001fab0  mov     edx, ebx
0x14001fab2  lea     rcx, [rbp+37h+var_58]
0x14001fab6  call    CopyOperationResultToStr
0x14001fabb  mov     rbx, [rbp+37h+var_58]
0x14001fabf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fac6  cmp     rcx, r14
0x14001fac9  jz      short loc_14001FAF6
0x14001facb  test    byte ptr [rcx+1Ch], 10h
0x14001facf  jz      short loc_14001FAF6
0x14001fad1  mov     dword ptr [rsp+100h+var_C0], r13d; char
  ... truncated ...
```

# AppReadiness::GetCallingUserSidString

- ea: `0x1800122d0`
- end: `0x1800125fc`
- name: `AppReadiness::GetCallingUserSidString`
- size: `812`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180012910`
- `0x180013128`

## callees

- `0x1800122d0`
- `0x180012610`
- `0x180021750`
- `0x18003868c`
- `0x18003eec0`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012456`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012456`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180012311`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180012311`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800124dd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800124dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800124ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800124ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001257d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001257d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800124cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800124cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800124b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800124b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800123a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800125c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800123a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800125c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012374`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001252b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001258d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001252b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001258d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001255a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001255a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800123df`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800123df`

## pseudocode

```c
__int64 __fastcall AppReadiness::GetCallingUserSidString(__int64 a1, _WORD *a2, __int64 a3)
{
  int v5; // edx
  unsigned int v6; // ecx
  int Error; // edi
  PSID *v8; // r14
  HANDLE v9; // r15
  PSID *v10; // rsi
  LPWSTR v11; // r9
  __int64 v12; // rcx
  LPWSTR v13; // rdx
  __int64 v14; // r8
  _WORD *v15; // rcx
  int v16; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v19; // edx
  void *v20; // rcx
  int v21; // eax
  void **v23; // [rsp+38h] [rbp-9h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-1h] BYREF
  LPWSTR StringSid[3]; // [rsp+48h] [rbp+7h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+67h] BYREF
  __int64 ReturnLength; // [rsp+B8h] [rbp+77h] BYREF
  HANDLE hObject; // [rsp+C0h] [rbp+7Fh] BYREF

  ReturnLength = a3;
  TokenHandle = 0;
  v23 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( a1 )
  {
    if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent(a1) )
    {
      Error = -2147467263;
      goto LABEL_23;
    }
    Error = UMgrQueryUserToken(a1, &TokenHandle);
  }
  else
  {
    Error = CoImpersonateClient();
    if ( Error >= 0 )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      CoRevertToSelf();
    }
  }
  if ( Error >= 0 )
  {
    v8 = 0;
    v9 = TokenHandle;
    StringSid[1] = (LPWSTR)-1LL;
    StringSid[2] = (LPWSTR)-1LL;
    StringSid[0] = 0;
    hObject = 0;
    if ( !TokenHandle )
    {
      Error = SHOpenEffectiveToken(v6, v5, &hObject);
      if ( Error < 0 )
      {
LABEL_10:
        if ( Error < 0 )
          goto LABEL_34;
        if ( !ConvertSidToStringSidW(*v8, StringSid) )
          Error = ResultFromKnownLastError();
        LocalFree(v8);
        if ( Error < 0 )
        {
LABEL_34:
          v11 = StringSid[0];
        }
        else
        {
          v11 = StringSid[0];
          v12 = 2147483646;
          v13 = StringSid[0];
          v14 = 260;
          do
          {
            if ( !v12 )
              break;
            if ( !*v13 )
              break;
            *a2++ = *v13++;
            --v12;
            --v14;
          }
          while ( v14 );
          v15 = a2 - 1;
          Error = -2147024774;
          if ( v14 )
          {
            v15 = a2;
            Error = 0;
          }
          *v15 = 0;
        }
        if ( v11 )
          CoTaskMemFree(v11);
        goto LABEL_23;
      }
      v9 = hObject;
    }
    LODWORD(ReturnLength) = 2048;
    hMem = LocalAlloc(0x40u, 0x800u);
    v10 = (PSID *)hMem;
    if ( !hMem )
    {
      Error = -2147024882;
      goto LABEL_8;
    }
    Error = 0;
    if ( GetTokenInformation(v9, TokenUser, hMem, ReturnLength, (PDWORD)&ReturnLength) )
    {
LABEL_7:
      v8 = v10;
      goto LABEL_8;
    }
    LastError = GetLastError();
    Error = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v10);
      v21 = CTLocalAllocPolicy::Alloc(v20, v19, (unsigned int)ReturnLength, &hMem);
      v10 = (PSID *)hMem;
      Error = v21;
      if ( v21 < 0 )
      {
LABEL_37:
        LocalFree(v10);
LABEL_8:
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_10;
      }
      if ( GetTokenInformation(v9, TokenUser, hMem, ReturnLength, (PDWORD)&ReturnLength) )
        goto LABEL_7;
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        goto LABEL_35;
    }
    else if ( LastError > 0 )
    {
LABEL_35:
      Error = (unsigned __int16)LastError | 0x80070000;
    }
    if ( Error >= 0 )
      goto LABEL_7;
    goto LABEL_37;
  }
LABEL_23:
  v23 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( TokenHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits>::InternalClose(&v23) )
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    RaiseException(v16, 1u, 0, 0);
    __debugbreak();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800122d0  mov     rax, rsp
0x1800122d3  mov     [rax+18h], r8
0x1800122d7  push    rbp
0x1800122d8  push    rdi
0x1800122d9  lea     rbp, [rax-5Fh]
0x1800122dd  sub     rsp, 88h
0x1800122e4  mov     [rax+10h], rbx
0x1800122e8  mov     rdi, rcx
0x1800122eb  mov     [rax-20h], r12
0x1800122ef  mov     rbx, rdx
0x1800122f2  xor     r12d, r12d
0x1800122f5  mov     [rax-28h], r13
0x1800122f9  mov     [rbp+57h+TokenHandle], r12
0x1800122fd  lea     r13, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180012304  mov     [rbp+57h+var_60], r13
0x180012308  test    rcx, rcx
0x18001230b  jnz     loc_18001254A
0x180012311  call    cs:__imp_CoImpersonateClient
0x180012317  mov     edi, eax
0x180012319  test    eax, eax
0x18001231b  jns     loc_1800124B4
0x180012321  test    edi, edi
0x180012323  js      loc_18001245C
0x180012329  mov     [rsp+90h+var_28], r14
0x18001232e  mov     r14, r12
0x180012331  mov     [rsp+90h+var_30], r15
0x180012336  mov     r15, [rbp+57h+TokenHandle]
0x18001233a  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x180012342  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x18001234a  mov     [rbp+57h+StringSid], r12
0x18001234e  mov     [rbp+57h+hObject], r12
0x180012352  test    r15, r15
0x180012355  jz      loc_1800124E8
0x18001235b  mov     edx, 800h; uBytes
0x180012360  mov     [rsp+80h], rsi
0x180012368  mov     ecx, 40h ; '@'; uFlags
0x18001236d  mov     dword ptr [rbp+57h+ReturnLength], 800h
0x180012374  call    cs:__imp_LocalAlloc
0x18001237a  mov     [rbp+57h+hMem], rax
0x18001237e  mov     rsi, rax
0x180012381  test    rax, rax
0x180012384  jz      loc_180012504
0x18001238a  mov     r9d, dword ptr [rbp+57h+ReturnLength]; TokenInformationLength
0x18001238e  lea     rax, [rbp+57h+ReturnLength]
0x180012392  mov     r8, rsi; TokenInformation
0x180012395  mov     [rsp+20h], rax; ReturnLength
0x18001239a  mov     edx, 1; TokenInformationClass
0x18001239f  mov     rcx, r15; TokenHandle
0x1800123a2  mov     edi, r12d
0x1800123a5  call    cs:__imp_GetTokenInformation
0x1800123ab  test    eax, eax
0x1800123ad  jz      loc_18001257D
0x1800123b3  mov     r14, rsi
0x1800123b6  mov     rcx, [rbp+57h+hObject]; hObject
0x1800123ba  mov     rsi, [rsp+80h]
0x1800123c2  test    rcx, rcx
0x1800123c5  jnz     loc_1800125D9
0x1800123cb  mov     r15, [rsp+90h+var_30]
0x1800123d0  test    edi, edi
0x1800123d2  js      loc_18001250E
0x1800123d8  mov     rcx, [r14]; Sid
0x1800123db  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800123df  call    cs:__imp_ConvertSidToStringSidW
0x1800123e5  test    eax, eax
0x1800123e7  jz      loc_1800125E4
0x1800123ed  mov     rcx, r14; hMem
0x1800123f0  call    cs:__imp_LocalFree
0x1800123f6  test    edi, edi
0x1800123f8  js      loc_18001250E
0x1800123fe  mov     r9, [rbp+57h+StringSid]
0x180012402  mov     ecx, 7FFFFFFEh
0x180012407  mov     rdx, r9
0x18001240a  mov     r8d, 104h
0x180012410  test    rcx, rcx
0x180012413  jz      short loc_180012431
0x180012415  movzx   eax, word ptr [rdx]
0x180012418  test    ax, ax
0x18001241b  jz      short loc_180012431
0x18001241d  mov     [rbx], ax
0x180012420  add     rdx, 2
0x180012424  add     rbx, 2
0x180012428  dec     rcx
0x18001242b  sub     r8, 1
0x18001242f  jnz     short loc_180012410
0x180012431  test    r8, r8
0x180012434  lea     rcx, [rbx-2]
0x180012438  mov     edi, 8007007Ah
0x18001243d  cmovnz  rcx, rbx
0x180012441  cmovnz  edi, r12d
0x180012445  mov     [rcx], r12w
0x180012449  mov     r14, [rsp+90h+var_28]
0x18001244e  test    r9, r9
0x180012451  jz      short loc_18001245C
0x180012453  mov     rcx, r9; pv
0x180012456  call    cs:__imp_CoTaskMemFree
0x18001245c  cmp     [rbp+57h+TokenHandle], 0
0x180012461  mov     r12, [rsp+90h+var_18]
0x180012466  mov     rbx, [rsp+90h+arg_8]
0x18001246e  mov     [rbp+57h+var_60], r13
0x180012472  mov     r13, [rsp+90h+var_20]
0x180012477  jz      loc_1800125F0
0x18001247d  lea     rcx, [rbp+57h+var_60]
0x180012481  call    ?InternalClose@?$HandleT@USemaphoreTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits>::InternalClose(void)
0x180012486  test    al, al
0x180012488  jnz     loc_1800125F0
0x18001248e  call    cs:__imp_GetLastError
0x180012494  test    eax, eax
0x180012496  jle     short loc_1800124A0
0x180012498  movzx   eax, ax
0x18001249b  or      eax, 80070000h
0x1800124a0  xor     r9d, r9d; lpArguments
0x1800124a3  xor     r8d, r8d; nNumberOfArguments
0x1800124a6  mov     edx, 1; dwExceptionFlags
0x1800124ab  mov     ecx, eax; dwExceptionCode
0x1800124ad  call    cs:__imp_RaiseException
0x1800124b3  int     3; Trap to Debugger
0x1800124b4  call    cs:__imp_GetCurrentThread
0x1800124ba  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800124be  mov     edx, 8; DesiredAccess
0x1800124c3  mov     rcx, rax; ThreadHandle
0x1800124c6  mov     r8d, 1; OpenAsSelf
0x1800124cc  call    cs:__imp_OpenThreadToken
0x1800124d2  test    eax, eax
0x1800124d4  jz      loc_180012571
0x1800124da  mov     edi, r12d
0x1800124dd  call    cs:__imp_CoRevertToSelf
0x1800124e3  jmp     loc_180012321
0x1800124e8  lea     r8, [rbp+57h+hObject]; void **
0x1800124ec  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800124f1  mov     edi, eax
0x1800124f3  test    eax, eax
0x1800124f5  js      loc_1800123CB
0x1800124fb  mov     r15, [rbp+57h+hObject]
0x1800124ff  jmp     loc_18001235B
0x180012504  mov     edi, 8007000Eh
0x180012509  jmp     loc_1800123B6
0x18001250e  mov     r9, [rbp+57h+StringSid]
0x180012512  jmp     loc_180012449
0x180012517  movzx   edi, ax
0x18001251a  or      edi, 80070000h
0x180012520  test    edi, edi
0x180012522  jns     loc_1800123B3
0x180012528  mov     rcx, rsi; hMem
0x18001252b  call    cs:__imp_LocalFree
0x180012531  jmp     loc_1800123B6
0x180012536  call    cs:__imp_GetLastError
0x18001253c  mov     edi, eax
0x18001253e  test    eax, eax
0x180012540  jle     short loc_180012520
0x180012542  jmp     short loc_180012517
0x180012544  test    eax, eax
0x180012546  jle     short loc_180012520
0x180012548  jmp     short loc_180012517
0x18001254a  call    IsUMgrEnumerateSessionUsersPresent
0x18001254f  test    al, al
0x180012551  jz      short loc_180012567
0x180012553  lea     rdx, [rbp+57h+TokenHandle]
0x180012557  mov     rcx, rdi
0x18001255a  call    cs:__imp_UMgrQueryUserToken
0x180012560  mov     edi, eax
0x180012562  jmp     loc_180012321
0x180012567  mov     edi, 80004001h
0x18001256c  jmp     loc_18001245C
0x180012571  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180012576  mov     edi, eax
0x180012578  jmp     loc_1800124DD
0x18001257d  call    cs:__imp_GetLastError
0x180012583  mov     edi, eax
0x180012585  cmp     eax, 7Ah ; 'z'
0x180012588  jnz     short loc_180012544
0x18001258a  mov     rcx, rsi; hMem
0x18001258d  call    cs:__imp_LocalFree
0x180012593  mov     r8d, dword ptr [rbp+57h+ReturnLength]; unsigned __int64
0x180012597  lea     r9, [rbp+57h+hMem]; void **
0x18001259b  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800125a0  mov     rsi, [rbp+57h+hMem]
0x1800125a4  mov     edi, eax
0x1800125a6  test    eax, eax
0x1800125a8  js      loc_180012528
0x1800125ae  mov     r9d, dword ptr [rbp+57h+ReturnLength]; TokenInformationLength
0x1800125b2  lea     rax, [rbp+57h+ReturnLength]
0x1800125b6  mov     r8, rsi; TokenInformation
0x1800125b9  mov     [rsp+20h], rax; ReturnLength
0x1800125be  mov     edx, 1; TokenInformationClass
0x1800125c3  mov     rcx, r15; TokenHandle
0x1800125c6  call    cs:__imp_GetTokenInformation
0x1800125cc  test    eax, eax
0x1800125ce  jnz     loc_1800123B3
0x1800125d4  jmp     loc_180012536
0x1800125d9  call    cs:__imp_CloseHandle
0x1800125df  jmp     loc_1800123CB
0x1800125e4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800125e9  mov     edi, eax
0x1800125eb  jmp     loc_1800123ED
0x1800125f0  mov     eax, edi
0x1800125f2  add     rsp, 88h
0x1800125f9  pop     rdi
0x1800125fa  pop     rbp
0x1800125fb  retn
```

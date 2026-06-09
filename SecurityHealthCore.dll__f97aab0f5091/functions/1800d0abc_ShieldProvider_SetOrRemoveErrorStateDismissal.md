# ShieldProvider::SetOrRemoveErrorStateDismissal

- ea: `0x1800d0abc`
- end: `0x1800d0c0b`
- name: `ShieldProvider::SetOrRemoveErrorStateDismissal`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180095e50`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x1800cf8d0`
- `0x1800d0abc`
- `0x1800df118`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800d0afa`
- `KERNEL32!GetLastError` at `0x1800d0afa`
- `KERNEL32!CloseHandle` at `0x1800d0b84`
- `KERNEL32!CloseHandle` at `0x1800d0bf3`
- `KERNEL32!CloseHandle` at `0x1800d0b84`
- `KERNEL32!CloseHandle` at `0x1800d0bf3`
- `KERNEL32!GetCurrentThread` at `0x1800d0adc`
- `KERNEL32!GetCurrentThread` at `0x1800d0adc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d0af0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d0af0`

## pseudocode

```c
__int64 __fastcall ShieldProvider::SetOrRemoveErrorStateDismissal(unsigned int a1, char a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // r8
  unsigned int v5; // r9d
  signed int LastError; // eax
  signed int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 IndexForDeviceWideErrorDismissalState; // rbx
  unsigned int v12[4]; // [rsp+20h] [rbp-20h] BYREF
  char v13; // [rsp+30h] [rbp-10h]
  char v14; // [rsp+58h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+20h] BYREF

  v14 = a2;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 49;
LABEL_12:
        WPP_SF_d(v8[2], v9, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids, (unsigned int)v7);
        goto LABEL_13;
      }
      goto LABEL_13;
    }
  }
  v14 = 0;
  v7 = CommonUtil::UtilCheckTokenMembershipByRid((CommonUtil *)&v14, (bool *)TokenHandle, v4, v5, v12[0]);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 47;
      goto LABEL_12;
    }
LABEL_13:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return (unsigned int)v7;
  }
  if ( !v14 )
  {
    v8 = WPP_GLOBAL_Control;
    v7 = -2147024891;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 48;
      goto LABEL_12;
    }
    goto LABEL_13;
  }
  IndexForDeviceWideErrorDismissalState = (unsigned int)ShieldProvider::GetIndexForDeviceWideErrorDismissalState(a1);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v12,
    ShieldProvider::g_aCSwarningStates);
  v13 = 0;
  *((_BYTE *)&dword_18013A654 + IndexForDeviceWideErrorDismissalState) = 1;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v12);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1800d0abc  mov     [rsp-8+arg_0], rbx
0x1800d0ac1  mov     [rsp-8+arg_18], rdi
0x1800d0ac6  mov     [rsp-8+arg_8], dl
0x1800d0aca  push    rbp
0x1800d0acb  mov     rbp, rsp
0x1800d0ace  sub     rsp, 40h
0x1800d0ad2  mov     edi, ecx
0x1800d0ad4  mov     [rbp+TokenHandle], 0
0x1800d0adc  call    cs:__imp_GetCurrentThread
0x1800d0ae2  xor     r8d, r8d; OpenAsSelf
0x1800d0ae5  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d0ae9  mov     rcx, rax; ThreadHandle
0x1800d0aec  lea     edx, [r8+8]; DesiredAccess
0x1800d0af0  call    cs:__imp_OpenThreadToken
0x1800d0af6  test    eax, eax
0x1800d0af8  jnz     short loc_1800D0B33
0x1800d0afa  call    cs:__imp_GetLastError
0x1800d0b00  mov     ebx, eax
0x1800d0b02  test    eax, eax
0x1800d0b04  jle     short loc_1800D0B0F
0x1800d0b06  movzx   ebx, ax
0x1800d0b09  or      ebx, 80070000h
0x1800d0b0f  test    ebx, ebx
0x1800d0b11  jns     short loc_1800D0B33
0x1800d0b13  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0b1a  lea     rax, WPP_GLOBAL_Control
0x1800d0b21  cmp     rcx, rax
0x1800d0b24  jz      short loc_1800D0B7B
0x1800d0b26  test    byte ptr [rcx+1Ch], 1
0x1800d0b2a  jz      short loc_1800D0B7B
0x1800d0b2c  mov     edx, 31h ; '1'
0x1800d0b31  jmp     short loc_1800D0B68
0x1800d0b33  mov     rdx, [rbp+TokenHandle]; bool *
0x1800d0b37  lea     rcx, [rbp+arg_8]; this
0x1800d0b3b  mov     [rbp+arg_8], 0
0x1800d0b3f  call    ?UtilCheckTokenMembershipByRid@CommonUtil@@YAJPEA_NPEAXKK@Z; CommonUtil::UtilCheckTokenMembershipByRid(bool *,void *,ulong,ulong)
0x1800d0b44  mov     ebx, eax
0x1800d0b46  test    eax, eax
0x1800d0b48  jns     short loc_1800D0B8E
0x1800d0b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0b51  lea     rax, WPP_GLOBAL_Control
0x1800d0b58  cmp     rcx, rax
0x1800d0b5b  jz      short loc_1800D0B7B
0x1800d0b5d  test    byte ptr [rcx+1Ch], 1
0x1800d0b61  jz      short loc_1800D0B7B
0x1800d0b63  mov     edx, 2Fh ; '/'
0x1800d0b68  mov     rcx, [rcx+10h]
0x1800d0b6c  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d0b73  mov     r9d, ebx
0x1800d0b76  call    WPP_SF_d
0x1800d0b7b  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d0b7f  test    rcx, rcx
0x1800d0b82  jz      short loc_1800D0B8A
0x1800d0b84  call    cs:__imp_CloseHandle
0x1800d0b8a  mov     eax, ebx
0x1800d0b8c  jmp     short loc_1800D0BFB
0x1800d0b8e  cmp     [rbp+arg_8], 0
0x1800d0b92  jnz     short loc_1800D0BB9
0x1800d0b94  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0b9b  lea     rax, WPP_GLOBAL_Control
0x1800d0ba2  mov     ebx, 80070005h
0x1800d0ba7  cmp     rcx, rax
0x1800d0baa  jz      short loc_1800D0B7B
0x1800d0bac  test    byte ptr [rcx+1Ch], 1
0x1800d0bb0  jz      short loc_1800D0B7B
0x1800d0bb2  mov     edx, 30h ; '0'
0x1800d0bb7  jmp     short loc_1800D0B68
0x1800d0bb9  mov     ecx, edi
0x1800d0bbb  call    ShieldProvider__GetIndexForDeviceWideErrorDismissalState
0x1800d0bc0  lea     rdx, ?g_aCSwarningStates@ShieldProvider@@3U?$CSimpleGlobalAtStartup2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@A; CommonUtil::CSimpleGlobalAtStartup2nd<CommonUtil::CMpCriticalSection> ShieldProvider::g_aCSwarningStates
0x1800d0bc7  mov     ebx, eax
0x1800d0bc9  lea     rcx, [rbp+var_20]
0x1800d0bcd  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800d0bd2  lea     rcx, dword_18013A654
0x1800d0bd9  mov     [rbp+var_10], 0
0x1800d0bdd  mov     byte ptr [rbx+rcx], 1
0x1800d0be1  lea     rcx, [rbp+var_20]
0x1800d0be5  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800d0bea  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d0bee  test    rcx, rcx
0x1800d0bf1  jz      short loc_1800D0BF9
0x1800d0bf3  call    cs:__imp_CloseHandle
0x1800d0bf9  xor     eax, eax
0x1800d0bfb  mov     rbx, [rsp+40h+arg_0]
0x1800d0c00  mov     rdi, [rsp+40h+arg_18]
0x1800d0c05  add     rsp, 40h
0x1800d0c09  pop     rbp
0x1800d0c0a  retn
```

# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002ab5c`
- end: `0x18002ad55`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180112958`

## callees

- `0x180015eec`
- `0x18002ab5c`
- `0x18002ad5c`
- `0x18002ae98`
- `0x180030298`
- `0x18003f184`
- `0x180040658`
- `0x180048fdc`
- `0x180053518`
- `0x180059920`
- `0x18005f27c`
- `0x180060424`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x18002abd3`
- `KERNEL32!CreateMutexExW` at `0x18002abd3`
- `KERNEL32!GetCurrentProcessId` at `0x18002ab97`
- `KERNEL32!GetCurrentProcessId` at `0x18002ab97`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002abfb`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002abfb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v23[0] = v12;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v22, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
    LastErrorFailHr = v15;
    goto LABEL_14;
  }
  v16 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v16;
    ++*v16;
  }
  else
  {
    v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    LastErrorFailHr = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v17,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
      goto LABEL_14;
    }
    v6 = v21;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x18002ab5c  mov     [rsp-8+arg_10], rbx
0x18002ab61  mov     [rsp-8+arg_18], rsi
0x18002ab66  push    rbp
0x18002ab67  push    rdi
0x18002ab68  push    r14
0x18002ab6a  lea     rbp, [rsp-170h]
0x18002ab72  sub     rsp, 270h
0x18002ab79  mov     rax, cs:__security_cookie
0x18002ab80  xor     rax, rsp
0x18002ab83  mov     [rbp+180h+var_20], rax
0x18002ab8a  mov     r14, rdx
0x18002ab8d  mov     qword ptr [rdx], 0
0x18002ab94  mov     rbx, rcx
0x18002ab97  call    cs:__imp_GetCurrentProcessId
0x18002ab9d  mov     [rsp+280h+var_258], rbx
0x18002aba2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002aba9  mov     r9d, eax
0x18002abac  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18002abb4  mov     edx, 104h; unsigned __int64
0x18002abb9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002abbe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002abc3  mov     r9d, 1F0001h; dwDesiredAccess
0x18002abc9  lea     rdx, [rsp+280h+Name]; lpName
0x18002abce  xor     r8d, r8d; dwFlags
0x18002abd1  xor     ecx, ecx; lpMutexAttributes
0x18002abd3  call    cs:__imp_CreateMutexExW
0x18002abd9  mov     [rsp+280h+var_250], rax
0x18002abde  mov     rbx, rax
0x18002abe1  test    rax, rax
0x18002abe4  jnz     short loc_18002ABF2
0x18002abe6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002abeb  mov     ebx, eax
0x18002abed  jmp     loc_18002ACFF
0x18002abf2  xor     r8d, r8d; bAlertable
0x18002abf5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002abf8  mov     rcx, rbx; hHandle
0x18002abfb  call    cs:__imp_WaitForSingleObjectEx
0x18002ac01  cmp     eax, 102h
0x18002ac06  jz      short loc_18002AC21
0x18002ac08  test    eax, 0FFFFFF7Fh
0x18002ac0d  jz      short loc_18002AC1C
0x18002ac0f  mov     rcx, [rbp+188h]; this
0x18002ac16  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002ac1c  mov     rdi, rbx
0x18002ac1f  jmp     short loc_18002AC23
0x18002ac21  xor     edi, edi
0x18002ac23  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18002ac28  mov     [rsp+280h+var_240], rdi
0x18002ac2d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002ac32  mov     [rsp+280h+var_248], 0
0x18002ac3b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002ac40  mov     esi, eax
0x18002ac42  test    eax, eax
0x18002ac44  jns     short loc_18002ACA5
0x18002ac46  mov     rcx, [rbp+188h]; this
0x18002ac4d  lea     r8, aWil; "wil"
0x18002ac54  mov     r9d, eax; char *
0x18002ac57  mov     edx, 66h ; 'f'; void *
0x18002ac5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac61  mov     rcx, [rbp+188h]; this
0x18002ac68  lea     r8, aWil; "wil"
0x18002ac6f  mov     r9d, esi; char *
0x18002ac72  mov     edx, 6Fh ; 'o'; void *
0x18002ac77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac7c  mov     rcx, [rbp+188h]; this
0x18002ac83  lea     r8, aWil; "wil"
0x18002ac8a  mov     r9d, esi; char *
0x18002ac8d  mov     edx, 12Eh; void *
0x18002ac92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac97  lea     rcx, [rsp+280h+var_240]
0x18002ac9c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002aca1  mov     ebx, esi
0x18002aca3  jmp     short loc_18002ACFF
0x18002aca5  mov     rax, [rsp+280h+var_248]
0x18002acaa  lea     rcx, ds:0[rax*4]
0x18002acb2  test    rcx, rcx
0x18002acb5  jz      short loc_18002ACC2
0x18002acb7  mov     [r14], rcx
0x18002acba  mov     eax, [rcx]
0x18002acbc  inc     eax
0x18002acbe  mov     [rcx], eax
0x18002acc0  jmp     short loc_18002AD12
0x18002acc2  mov     r8, r14
0x18002acc5  lea     rdx, [rsp+280h+var_250]
0x18002acca  lea     rcx, [rsp+280h+Name]
0x18002accf  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002acd4  mov     ebx, eax
0x18002acd6  test    eax, eax
0x18002acd8  jns     short loc_18002AD0D
0x18002acda  mov     rcx, [rbp+188h]; this
0x18002ace1  lea     r8, aWil; "wil"
0x18002ace8  mov     r9d, eax; char *
0x18002aceb  mov     edx, 137h; void *
0x18002acf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acf5  lea     rcx, [rsp+280h+var_240]
0x18002acfa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002acff  lea     rcx, [rsp+280h+var_250]
0x18002ad04  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ad09  mov     eax, ebx
0x18002ad0b  jmp     short loc_18002AD2E
0x18002ad0d  mov     rbx, [rsp+280h+var_250]
0x18002ad12  test    rdi, rdi
0x18002ad15  jz      short loc_18002AD1F
0x18002ad17  mov     rcx, rdi; this
0x18002ad1a  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18002ad1f  test    rbx, rbx
0x18002ad22  jz      short loc_18002AD2C
0x18002ad24  mov     rcx, rbx; this
0x18002ad27  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002ad2c  xor     eax, eax
0x18002ad2e  mov     rcx, [rbp+180h+var_20]
0x18002ad35  xor     rcx, rsp; StackCookie
0x18002ad38  call    __security_check_cookie
0x18002ad3d  lea     r11, [rsp+280h+var_10]
0x18002ad45  mov     rbx, [r11+30h]
0x18002ad49  mov     rsi, [r11+38h]
0x18002ad4d  mov     rsp, r11
0x18002ad50  pop     r14
0x18002ad52  pop     rdi
0x18002ad53  pop     rbp
0x18002ad54  retn
```

# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800061d0`
- end: `0x18000632f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009a6c`

## callees

- `0x180005624`
- `0x180005640`
- `0x1800061d0`
- `0x1800096fc`
- `0x18000bfc0`
- `0x18000e7dc`
- `0x180012864`
- `0x1800132d4`
- `0x180013eb0`
- `0x180014620`
- `0x18006c690`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x18000624d`
- `KERNEL32!CreateMutexExW` at `0x18000624d`
- `KERNEL32!GetCurrentProcessId` at `0x180006208`
- `KERNEL32!GetCurrentProcessId` at `0x180006208`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800061d0  mov     [rsp-8+arg_10], rbx
0x1800061d5  mov     [rsp-8+arg_18], rdi
0x1800061da  push    rbp
0x1800061db  lea     rbp, [rsp-170h]
0x1800061e3  sub     rsp, 270h
0x1800061ea  mov     rax, cs:__security_cookie
0x1800061f1  xor     rax, rsp
0x1800061f4  mov     [rbp+170h+var_10], rax
0x1800061fb  mov     rdi, rdx
0x1800061fe  mov     qword ptr [rdx], 0
0x180006205  mov     rbx, rcx
0x180006208  call    cs:__imp_GetCurrentProcessId
0x18000620e  mov     [rsp+270h+var_248], rbx
0x180006213  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000621a  mov     r9d, eax
0x18000621d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180006225  mov     edx, 104h; unsigned __int64
0x18000622a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000622f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006234  mov     r9d, 1F0001h; dwDesiredAccess
0x18000623a  mov     [rsp+270h+var_240], 0
0x180006243  xor     r8d, r8d; dwFlags
0x180006246  lea     rdx, [rsp+270h+Name]; lpName
0x18000624b  xor     ecx, ecx; lpMutexAttributes
0x18000624d  call    cs:__imp_CreateMutexExW
0x180006253  mov     rdx, rax
0x180006256  lea     rcx, [rsp+270h+var_240]
0x18000625b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006260  cmp     [rsp+270h+var_240], 0
0x180006266  jnz     short loc_180006271
0x180006268  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000626d  mov     ebx, eax
0x18000626f  jmp     short loc_1800062DD
0x180006271  lea     rdx, [rsp+270h+var_238]
0x180006276  lea     rcx, [rsp+270h+var_240]
0x18000627b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006280  lea     rdx, [rsp+270h+var_230]; void **
0x180006285  mov     [rsp+270h+var_230], 0
0x18000628e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006293  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180006298  mov     ebx, eax
0x18000629a  test    eax, eax
0x18000629c  jns     short loc_1800062BE
0x18000629e  mov     edx, 12Eh; void *
0x1800062a3  mov     rcx, [rbp+178h]; this
0x1800062aa  mov     r9d, eax; char *
0x1800062ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062b2  lea     rcx, [rsp+270h+var_238]
0x1800062b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800062bc  jmp     short loc_1800062DD
0x1800062be  mov     rcx, [rsp+270h+var_230]
0x1800062c3  test    rcx, rcx
0x1800062c6  jz      short loc_18000630D
0x1800062c8  mov     [rdi], rcx
0x1800062cb  mov     eax, [rcx]
0x1800062cd  inc     eax
0x1800062cf  mov     [rcx], eax
0x1800062d1  lea     rcx, [rsp+270h+var_238]
0x1800062d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800062db  xor     ebx, ebx
0x1800062dd  lea     rcx, [rsp+270h+var_240]
0x1800062e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800062e7  mov     eax, ebx
0x1800062e9  mov     rcx, [rbp+170h+var_10]
0x1800062f0  xor     rcx, rsp; StackCookie
0x1800062f3  call    __security_check_cookie
0x1800062f8  lea     r11, [rsp+270h+var_s0]
0x180006300  mov     rbx, [r11+20h]
0x180006304  mov     rdi, [r11+28h]
0x180006308  mov     rsp, r11
0x18000630b  pop     rbp
0x18000630c  retn
0x18000630d  mov     r8, rdi
0x180006310  lea     rdx, [rsp+270h+var_240]
0x180006315  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000631a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000631f  mov     ebx, eax
0x180006321  test    eax, eax
0x180006323  jns     short loc_1800062D1
0x180006325  mov     edx, 137h
0x18000632a  jmp     loc_1800062A3
```

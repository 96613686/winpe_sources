# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003dcd0`
- end: `0x18003dea0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `464`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004c574`

## callees

- `0x180016258`
- `0x1800162e4`
- `0x180038270`
- `0x18003dcd0`
- `0x18003dea8`
- `0x18003ded4`
- `0x180049f70`
- `0x18004c09c`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003dd43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003dde7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003dd43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003dde7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd68`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // eax
  unsigned int v13; // r8d
  int v15[2]; // [rsp+28h] [rbp-E0h] BYREF
  int v16[2]; // [rsp+30h] [rbp-D8h] BYREF
  HANDLE v17; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE hHandle; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v19[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+290h] [rbp+188h]

  v19[1] = -2;
  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  *(_QWORD *)v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  ____0PEAX__V___unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA___QEAPEAX_Z(
    &hHandle,
    v16);
  if ( hHandle )
  {
    v16[0] = 0;
    v15[0] = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(hHandle, v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        v9,
        (const char *)(unsigned int)ValueFromSemaphore,
        v15[0]);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v19[0] = OpenSemaphoreW(0x1F0003u, 0, Name);
    ____0PEAX__V___unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA___QEAPEAX_Z(
      &v17,
      v19);
    if ( v17 )
    {
      v12 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, v15);
      LastError = v12;
      if ( v12 >= 0 )
      {
        __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v17);
        *a3 = v16[0] | (unsigned __int64)((__int64)v15[0] << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v13, (const char *)(unsigned int)v12, v15[0]);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v10, v11);
    }
    __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v5, v6);
LABEL_13:
  __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hHandle);
  return LastError;
}

```

## disassembly

```asm
0x18003dcd0  mov     rax, rsp
0x18003dcd3  push    rbp
0x18003dcd4  push    rdi
0x18003dcd5  push    r14
0x18003dcd7  lea     rbp, [rax-188h]
0x18003dcde  sub     rsp, 270h
0x18003dce5  mov     qword ptr [rsp+280h+var_238], 0FFFFFFFFFFFFFFFEh
0x18003dcee  mov     [rax+10h], rbx
0x18003dcf2  mov     rax, cs:__security_cookie
0x18003dcf9  xor     rax, rsp
0x18003dcfc  mov     [rbp+180h+var_20], rax
0x18003dd03  mov     rdi, r8
0x18003dd06  mov     qword ptr [r8], 0
0x18003dd0d  mov     r8, rcx; unsigned __int16 *
0x18003dd10  mov     r14d, 104h
0x18003dd16  mov     edx, r14d; unsigned __int64
0x18003dd19  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003dd1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003dd23  lea     r8, aP0; "_p0"
0x18003dd2a  mov     edx, r14d; unsigned __int64
0x18003dd2d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003dd32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003dd37  lea     r8, [rsp+280h+Name]; lpName
0x18003dd3c  xor     edx, edx; bInheritHandle
0x18003dd3e  mov     ecx, 1F0003h; dwDesiredAccess
0x18003dd43  call    cs:__imp_OpenSemaphoreW
0x18003dd49  mov     qword ptr [rsp+280h+var_258], rax
0x18003dd4e  lea     rdx, [rsp+280h+var_258]
0x18003dd53  lea     rcx, [rsp+280h+hHandle]
0x18003dd58  call    ??$?0PEAX$$V@?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@$$QEAPEAX@Z
0x18003dd5d  nop
0x18003dd5e  mov     rcx, [rsp+280h+hHandle]; hHandle
0x18003dd63  test    rcx, rcx
0x18003dd66  jnz     short loc_18003DD8E
0x18003dd68  call    cs:__imp_GetLastError
0x18003dd6e  cmp     eax, 2
0x18003dd71  jz      loc_18003DE6F
0x18003dd77  mov     rcx, [rbp+188h]; this
0x18003dd7e  lea     edx, [r14-34h]; void *
0x18003dd82  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003dd87  mov     ebx, eax
0x18003dd89  jmp     loc_18003DE71
0x18003dd8e  mov     [rsp+280h+var_258], 0
0x18003dd96  mov     [rsp+280h+var_260], 0; int
0x18003dd9e  lea     rdx, [rsp+280h+var_258]; int *
0x18003dda3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003dda8  mov     ebx, eax
0x18003ddaa  test    eax, eax
0x18003ddac  jns     short loc_18003DDC7
0x18003ddae  mov     rcx, [rbp+188h]; this
0x18003ddb5  mov     r9d, eax; char *
0x18003ddb8  mov     edx, 0D6h; void *
0x18003ddbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ddc2  jmp     loc_18003DE71
0x18003ddc7  lea     r8, asc_1800BE788; "h"
0x18003ddce  mov     rdx, r14; unsigned __int64
0x18003ddd1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003ddd6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003dddb  lea     r8, [rsp+280h+Name]; lpName
0x18003dde0  xor     edx, edx; bInheritHandle
0x18003dde2  mov     ecx, 1F0003h; dwDesiredAccess
0x18003dde7  call    cs:__imp_OpenSemaphoreW
0x18003dded  mov     [rsp+280h+var_240], rax
0x18003ddf2  lea     rdx, [rsp+280h+var_240]
0x18003ddf7  lea     rcx, [rsp+280h+var_250]
0x18003ddfc  call    ??$?0PEAX$$V@?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@$$QEAPEAX@Z
0x18003de01  nop
0x18003de02  mov     rcx, [rsp+280h+var_250]; hHandle
0x18003de07  test    rcx, rcx
0x18003de0a  jnz     short loc_18003DE2B
0x18003de0c  mov     rcx, [rbp+188h]; this
0x18003de13  mov     edx, 0DCh; void *
0x18003de18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003de1d  mov     ebx, eax
0x18003de1f  lea     rcx, [rsp+280h+var_250]
0x18003de24  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18003de29  jmp     short loc_18003DE71
0x18003de2b  lea     rdx, [rsp+280h+var_260]; int *
0x18003de30  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003de35  mov     ebx, eax
0x18003de37  test    eax, eax
0x18003de39  jns     short loc_18003DE51
0x18003de3b  mov     rcx, [rbp+188h]; this
0x18003de42  mov     r9d, eax; char *
0x18003de45  mov     edx, 0DEh; void *
0x18003de4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003de4f  jmp     short loc_18003DE1F
0x18003de51  lea     rcx, [rsp+280h+var_250]
0x18003de56  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18003de5b  movsxd  rcx, [rsp+280h+var_260]
0x18003de60  shl     rcx, 1Fh
0x18003de64  movsxd  rax, [rsp+280h+var_258]
0x18003de69  or      rcx, rax
0x18003de6c  mov     [rdi], rcx
0x18003de6f  xor     ebx, ebx
0x18003de71  lea     rcx, [rsp+280h+hHandle]
0x18003de76  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18003de7b  mov     eax, ebx
0x18003de7d  mov     rcx, [rbp+180h+var_20]
0x18003de84  xor     rcx, rsp; StackCookie
0x18003de87  call    __security_check_cookie
0x18003de8c  mov     rbx, [rsp+280h+arg_8]
0x18003de94  add     rsp, 270h
0x18003de9b  pop     r14
0x18003de9d  pop     rdi
0x18003de9e  pop     rbp
0x18003de9f  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002942c`
- end: `0x1800295c3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800293b8`

## callees

- `0x18001eb5c`
- `0x18001f650`
- `0x180024df8`
- `0x180027c18`
- `0x180028ac4`
- `0x180028ae4`
- `0x1800290a4`
- `0x18002942c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002949b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002949b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002948b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002951b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002948b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002951b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x18002942c  mov     [rsp-8+arg_8], rbx
0x180029431  mov     [rsp-8+arg_18], rdi
0x180029436  push    rbp
0x180029437  lea     rbp, [rsp-160h]
0x18002943f  sub     rsp, 260h
0x180029446  mov     rax, cs:__security_cookie
0x18002944d  xor     rax, rsp
0x180029450  mov     [rbp+160h+var_10], rax
0x180029457  mov     rdi, r8
0x18002945a  mov     qword ptr [r8], 0
0x180029461  mov     r8, rcx; unsigned __int16 *
0x180029464  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180029469  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002946e  lea     r8, aP0; "_p0"
0x180029475  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002947a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002947f  lea     r8, [rsp+260h+Name]; lpName
0x180029484  xor     edx, edx; bInheritHandle
0x180029486  mov     ecx, 1F0003h; dwDesiredAccess
0x18002948b  call    cs:__imp_OpenSemaphoreW
0x180029491  mov     [rsp+260h+var_230], rax
0x180029496  test    rax, rax
0x180029499  jnz     short loc_1800294C2
0x18002949b  call    cs:__imp_GetLastError
0x1800294a1  cmp     eax, 2
0x1800294a4  jz      loc_180029591
0x1800294aa  mov     rcx, [rbp+168h]; this
0x1800294b1  mov     edx, 0D0h; void *
0x1800294b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800294bb  mov     ebx, eax
0x1800294bd  jmp     loc_180029593
0x1800294c2  lea     rdx, [rsp+260h+var_23C]; int *
0x1800294c7  mov     [rsp+260h+var_23C], 0
0x1800294cf  mov     rcx, rax; hHandle
0x1800294d2  mov     [rsp+260h+var_240], 0; int
0x1800294da  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800294df  mov     ebx, eax
0x1800294e1  test    eax, eax
0x1800294e3  jns     short loc_1800294FE
0x1800294e5  mov     rcx, [rbp+168h]; this
0x1800294ec  mov     r9d, eax; char *
0x1800294ef  mov     edx, 0D6h; void *
0x1800294f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800294f9  jmp     loc_180029593
0x1800294fe  lea     r8, asc_18003E0C8; "h"
0x180029505  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002950a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002950f  lea     r8, [rsp+260h+Name]; lpName
0x180029514  xor     edx, edx; bInheritHandle
0x180029516  mov     ecx, 1F0003h; dwDesiredAccess
0x18002951b  call    cs:__imp_OpenSemaphoreW
0x180029521  mov     [rsp+260h+var_238], rax
0x180029526  test    rax, rax
0x180029529  jnz     short loc_18002954A
0x18002952b  mov     rcx, [rbp+168h]; this
0x180029532  mov     edx, 0DCh; void *
0x180029537  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002953c  mov     ebx, eax
0x18002953e  lea     rcx, [rsp+260h+var_238]
0x180029543  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029548  jmp     short loc_180029593
0x18002954a  lea     rdx, [rsp+260h+var_240]; int *
0x18002954f  mov     rcx, rax; hHandle
0x180029552  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180029557  mov     ebx, eax
0x180029559  test    eax, eax
0x18002955b  jns     short loc_180029573
0x18002955d  mov     rcx, [rbp+168h]; this
0x180029564  mov     r9d, eax; char *
0x180029567  mov     edx, 0DEh; void *
0x18002956c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029571  jmp     short loc_18002953E
0x180029573  lea     rcx, [rsp+260h+var_238]
0x180029578  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002957d  movsxd  rcx, [rsp+260h+var_240]
0x180029582  movsxd  rax, [rsp+260h+var_23C]
0x180029587  shl     rcx, 1Fh
0x18002958b  or      rcx, rax
0x18002958e  mov     [rdi], rcx
0x180029591  xor     ebx, ebx
0x180029593  lea     rcx, [rsp+260h+var_230]
0x180029598  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002959d  mov     eax, ebx
0x18002959f  mov     rcx, [rbp+160h+var_10]
0x1800295a6  xor     rcx, rsp; StackCookie
0x1800295a9  call    __security_check_cookie
0x1800295ae  lea     r11, [rsp+260h+var_s0]
0x1800295b6  mov     rbx, [r11+18h]
0x1800295ba  mov     rdi, [r11+28h]
0x1800295be  mov     rsp, r11
0x1800295c1  pop     rbp
0x1800295c2  retn
```

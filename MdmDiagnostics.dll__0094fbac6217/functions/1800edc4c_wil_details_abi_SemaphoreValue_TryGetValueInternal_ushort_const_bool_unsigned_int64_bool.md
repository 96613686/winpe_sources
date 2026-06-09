# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800edc4c`
- end: `0x1800ede0a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800edbc8`

## callees

- `0x180019000`
- `0x1800e7cc0`
- `0x1800ea9f8`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800ed5fc`
- `0x1800ed6e4`
- `0x1800edc4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800edcb5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800edd55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800edcb5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800edd55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edcc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edcc5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x1800edc4c  mov     [rsp-8+arg_8], rbx
0x1800edc51  push    rbp
0x1800edc52  push    rdi
0x1800edc53  push    r14
0x1800edc55  lea     rbp, [rsp-160h]
0x1800edc5d  sub     rsp, 260h
0x1800edc64  mov     rax, cs:__security_cookie
0x1800edc6b  xor     rax, rsp
0x1800edc6e  mov     [rbp+170h+var_20], rax
0x1800edc75  mov     rdi, r8
0x1800edc78  mov     qword ptr [r8], 0
0x1800edc7f  mov     r8, rcx; unsigned __int16 *
0x1800edc82  mov     r14d, 104h
0x1800edc88  mov     edx, r14d; unsigned __int64
0x1800edc8b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800edc90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800edc95  lea     r8, aP0; "_p0"
0x1800edc9c  mov     edx, r14d; unsigned __int64
0x1800edc9f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800edca4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800edca9  lea     r8, [rsp+270h+Name]; lpName
0x1800edcae  xor     edx, edx; bInheritHandle
0x1800edcb0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800edcb5  call    cs:__imp_OpenSemaphoreW
0x1800edcbb  mov     [rsp+270h+var_240], rax
0x1800edcc0  test    rax, rax
0x1800edcc3  jnz     short loc_1800EDCF2
0x1800edcc5  call    cs:__imp_GetLastError
0x1800edccb  cmp     eax, 2
0x1800edcce  jz      loc_1800EDDD9
0x1800edcd4  mov     rcx, [rbp+178h]; this
0x1800edcdb  lea     r8, aWil; "wil"
0x1800edce2  lea     edx, [r14-34h]; void *
0x1800edce6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800edceb  mov     ebx, eax
0x1800edced  jmp     loc_1800EDDDB
0x1800edcf2  lea     rdx, [rsp+270h+var_24C]; int *
0x1800edcf7  mov     [rsp+270h+var_24C], 0
0x1800edcff  mov     rcx, rax; hHandle
0x1800edd02  mov     [rsp+270h+var_250], 0; int
0x1800edd0a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800edd0f  mov     ebx, eax
0x1800edd11  test    eax, eax
0x1800edd13  jns     short loc_1800EDD35
0x1800edd15  mov     rcx, [rbp+178h]; this
0x1800edd1c  lea     r8, aWil; "wil"
0x1800edd23  mov     r9d, eax; char *
0x1800edd26  mov     edx, 0D6h; void *
0x1800edd2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800edd30  jmp     loc_1800EDDDB
0x1800edd35  lea     r8, asc_1801B9E58; "h"
0x1800edd3c  mov     rdx, r14; unsigned __int64
0x1800edd3f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800edd44  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800edd49  lea     r8, [rsp+270h+Name]; lpName
0x1800edd4e  xor     edx, edx; bInheritHandle
0x1800edd50  mov     ecx, 1F0003h; dwDesiredAccess
0x1800edd55  call    cs:__imp_OpenSemaphoreW
0x1800edd5b  mov     [rsp+270h+var_248], rax
0x1800edd60  test    rax, rax
0x1800edd63  jnz     short loc_1800EDD8B
0x1800edd65  mov     rcx, [rbp+178h]; this
0x1800edd6c  lea     r8, aWil; "wil"
0x1800edd73  mov     edx, 0DCh; void *
0x1800edd78  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800edd7d  mov     ebx, eax
0x1800edd7f  lea     rcx, [rsp+270h+var_248]
0x1800edd84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800edd89  jmp     short loc_1800EDDDB
0x1800edd8b  lea     rdx, [rsp+270h+var_250]; int *
0x1800edd90  mov     rcx, rax; hHandle
0x1800edd93  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800edd98  mov     ebx, eax
0x1800edd9a  test    eax, eax
0x1800edd9c  jns     short loc_1800EDDBB
0x1800edd9e  mov     rcx, [rbp+178h]; this
0x1800edda5  lea     r8, aWil; "wil"
0x1800eddac  mov     r9d, eax; char *
0x1800eddaf  mov     edx, 0DEh; void *
0x1800eddb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eddb9  jmp     short loc_1800EDD7F
0x1800eddbb  lea     rcx, [rsp+270h+var_248]
0x1800eddc0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800eddc5  movsxd  rcx, [rsp+270h+var_250]
0x1800eddca  movsxd  rax, [rsp+270h+var_24C]
0x1800eddcf  shl     rcx, 1Fh
0x1800eddd3  or      rcx, rax
0x1800eddd6  mov     [rdi], rcx
0x1800eddd9  xor     ebx, ebx
0x1800edddb  lea     rcx, [rsp+270h+var_240]
0x1800edde0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800edde5  mov     eax, ebx
0x1800edde7  mov     rcx, [rbp+170h+var_20]
0x1800eddee  xor     rcx, rsp; StackCookie
0x1800eddf1  call    __security_check_cookie
0x1800eddf6  mov     rbx, [rsp+270h+arg_8]
0x1800eddfe  add     rsp, 260h
0x1800ede05  pop     r14
0x1800ede07  pop     rdi
0x1800ede08  pop     rbp
0x1800ede09  retn
```

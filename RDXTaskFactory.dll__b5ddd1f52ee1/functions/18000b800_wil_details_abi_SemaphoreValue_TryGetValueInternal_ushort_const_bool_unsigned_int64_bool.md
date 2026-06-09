# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b800`
- end: `0x18000b9be`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b77c`

## callees

- `0x180003390`
- `0x180006d4c`
- `0x180008874`
- `0x18000aa5c`
- `0x18000aa7c`
- `0x18000b148`
- `0x18000b1d4`
- `0x18000b800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b869`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b909`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b869`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b879`

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
0x18000b800  mov     [rsp-8+arg_8], rbx
0x18000b805  push    rbp
0x18000b806  push    rdi
0x18000b807  push    r14
0x18000b809  lea     rbp, [rsp-160h]
0x18000b811  sub     rsp, 260h
0x18000b818  mov     rax, cs:__security_cookie
0x18000b81f  xor     rax, rsp
0x18000b822  mov     [rbp+170h+var_20], rax
0x18000b829  mov     rdi, r8
0x18000b82c  mov     qword ptr [r8], 0
0x18000b833  mov     r8, rcx; unsigned __int16 *
0x18000b836  mov     r14d, 104h
0x18000b83c  mov     edx, r14d; unsigned __int64
0x18000b83f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b844  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b849  lea     r8, aP0; "_p0"
0x18000b850  mov     edx, r14d; unsigned __int64
0x18000b853  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b858  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b85d  lea     r8, [rsp+270h+Name]; lpName
0x18000b862  xor     edx, edx; bInheritHandle
0x18000b864  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b869  call    cs:__imp_OpenSemaphoreW
0x18000b86f  mov     [rsp+270h+var_240], rax
0x18000b874  test    rax, rax
0x18000b877  jnz     short loc_18000B8A6
0x18000b879  call    cs:__imp_GetLastError
0x18000b87f  cmp     eax, 2
0x18000b882  jz      loc_18000B98D
0x18000b888  mov     rcx, [rbp+178h]; this
0x18000b88f  lea     r8, aWil; "wil"
0x18000b896  lea     edx, [r14-34h]; void *
0x18000b89a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b89f  mov     ebx, eax
0x18000b8a1  jmp     loc_18000B98F
0x18000b8a6  lea     rdx, [rsp+270h+var_24C]; int *
0x18000b8ab  mov     [rsp+270h+var_24C], 0
0x18000b8b3  mov     rcx, rax; hHandle
0x18000b8b6  mov     [rsp+270h+var_250], 0; int
0x18000b8be  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b8c3  mov     ebx, eax
0x18000b8c5  test    eax, eax
0x18000b8c7  jns     short loc_18000B8E9
0x18000b8c9  mov     rcx, [rbp+178h]; this
0x18000b8d0  lea     r8, aWil; "wil"
0x18000b8d7  mov     r9d, eax; char *
0x18000b8da  mov     edx, 0D6h; void *
0x18000b8df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8e4  jmp     loc_18000B98F
0x18000b8e9  lea     r8, asc_180057EC0; "h"
0x18000b8f0  mov     rdx, r14; unsigned __int64
0x18000b8f3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b8f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b8fd  lea     r8, [rsp+270h+Name]; lpName
0x18000b902  xor     edx, edx; bInheritHandle
0x18000b904  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b909  call    cs:__imp_OpenSemaphoreW
0x18000b90f  mov     [rsp+270h+var_248], rax
0x18000b914  test    rax, rax
0x18000b917  jnz     short loc_18000B93F
0x18000b919  mov     rcx, [rbp+178h]; this
0x18000b920  lea     r8, aWil; "wil"
0x18000b927  mov     edx, 0DCh; void *
0x18000b92c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b931  mov     ebx, eax
0x18000b933  lea     rcx, [rsp+270h+var_248]
0x18000b938  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b93d  jmp     short loc_18000B98F
0x18000b93f  lea     rdx, [rsp+270h+var_250]; int *
0x18000b944  mov     rcx, rax; hHandle
0x18000b947  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b94c  mov     ebx, eax
0x18000b94e  test    eax, eax
0x18000b950  jns     short loc_18000B96F
0x18000b952  mov     rcx, [rbp+178h]; this
0x18000b959  lea     r8, aWil; "wil"
0x18000b960  mov     r9d, eax; char *
0x18000b963  mov     edx, 0DEh; void *
0x18000b968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b96d  jmp     short loc_18000B933
0x18000b96f  lea     rcx, [rsp+270h+var_248]
0x18000b974  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b979  movsxd  rcx, [rsp+270h+var_250]
0x18000b97e  movsxd  rax, [rsp+270h+var_24C]
0x18000b983  shl     rcx, 1Fh
0x18000b987  or      rcx, rax
0x18000b98a  mov     [rdi], rcx
0x18000b98d  xor     ebx, ebx
0x18000b98f  lea     rcx, [rsp+270h+var_240]
0x18000b994  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b999  mov     eax, ebx
0x18000b99b  mov     rcx, [rbp+170h+var_20]
0x18000b9a2  xor     rcx, rsp; StackCookie
0x18000b9a5  call    __security_check_cookie
0x18000b9aa  mov     rbx, [rsp+270h+arg_8]
0x18000b9b2  add     rsp, 260h
0x18000b9b9  pop     r14
0x18000b9bb  pop     rdi
0x18000b9bc  pop     rbp
0x18000b9bd  retn
```

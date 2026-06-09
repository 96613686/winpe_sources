# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800589fc`
- end: `0x180058bcd`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180058978`

## callees

- `0x180007270`
- `0x180053f9c`
- `0x180055978`
- `0x180057c4c`
- `0x180057c6c`
- `0x180058368`
- `0x1800583e8`
- `0x1800589fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058a65`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058b11`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058a65`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a7b`

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
0x1800589fc  mov     [rsp-8+arg_8], rbx
0x180058a01  push    rbp
0x180058a02  push    rdi
0x180058a03  push    r14
0x180058a05  lea     rbp, [rsp-160h]
0x180058a0d  sub     rsp, 260h
0x180058a14  mov     rax, cs:__security_cookie
0x180058a1b  xor     rax, rsp
0x180058a1e  mov     [rbp+170h+var_20], rax
0x180058a25  mov     rdi, r8
0x180058a28  mov     qword ptr [r8], 0
0x180058a2f  mov     r8, rcx; unsigned __int16 *
0x180058a32  mov     r14d, 104h
0x180058a38  mov     edx, r14d; unsigned __int64
0x180058a3b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180058a40  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058a45  lea     r8, aP0; "_p0"
0x180058a4c  mov     edx, r14d; unsigned __int64
0x180058a4f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180058a54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058a59  lea     r8, [rsp+270h+Name]; lpName
0x180058a5e  xor     edx, edx; bInheritHandle
0x180058a60  mov     ecx, 1F0003h; dwDesiredAccess
0x180058a65  call    cs:__imp_OpenSemaphoreW
0x180058a6c  nop     dword ptr [rax+rax+00h]
0x180058a71  mov     [rsp+270h+var_240], rax
0x180058a76  test    rax, rax
0x180058a79  jnz     short loc_180058AAE
0x180058a7b  call    cs:__imp_GetLastError
0x180058a82  nop     dword ptr [rax+rax+00h]
0x180058a87  cmp     eax, 2
0x180058a8a  jz      loc_180058B9B
0x180058a90  mov     rcx, [rbp+178h]; this
0x180058a97  lea     r8, aWil; "wil"
0x180058a9e  lea     edx, [r14-34h]; void *
0x180058aa2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058aa7  mov     ebx, eax
0x180058aa9  jmp     loc_180058B9D
0x180058aae  lea     rdx, [rsp+270h+var_24C]; int *
0x180058ab3  mov     [rsp+270h+var_24C], 0
0x180058abb  mov     rcx, rax; hHandle
0x180058abe  mov     [rsp+270h+var_250], 0; int
0x180058ac6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180058acb  mov     ebx, eax
0x180058acd  test    eax, eax
0x180058acf  jns     short loc_180058AF1
0x180058ad1  mov     rcx, [rbp+178h]; this
0x180058ad8  lea     r8, aWil; "wil"
0x180058adf  mov     r9d, eax; char *
0x180058ae2  mov     edx, 0D6h; void *
0x180058ae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058aec  jmp     loc_180058B9D
0x180058af1  lea     r8, asc_1800CF380; "h"
0x180058af8  mov     rdx, r14; unsigned __int64
0x180058afb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180058b00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058b05  lea     r8, [rsp+270h+Name]; lpName
0x180058b0a  xor     edx, edx; bInheritHandle
0x180058b0c  mov     ecx, 1F0003h; dwDesiredAccess
0x180058b11  call    cs:__imp_OpenSemaphoreW
0x180058b18  nop     dword ptr [rax+rax+00h]
0x180058b1d  mov     [rsp+270h+var_248], rax
0x180058b22  test    rax, rax
0x180058b25  jnz     short loc_180058B4D
0x180058b27  mov     rcx, [rbp+178h]; this
0x180058b2e  lea     r8, aWil; "wil"
0x180058b35  mov     edx, 0DCh; void *
0x180058b3a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058b3f  mov     ebx, eax
0x180058b41  lea     rcx, [rsp+270h+var_248]
0x180058b46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058b4b  jmp     short loc_180058B9D
0x180058b4d  lea     rdx, [rsp+270h+var_250]; int *
0x180058b52  mov     rcx, rax; hHandle
0x180058b55  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180058b5a  mov     ebx, eax
0x180058b5c  test    eax, eax
0x180058b5e  jns     short loc_180058B7D
0x180058b60  mov     rcx, [rbp+178h]; this
0x180058b67  lea     r8, aWil; "wil"
0x180058b6e  mov     r9d, eax; char *
0x180058b71  mov     edx, 0DEh; void *
0x180058b76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058b7b  jmp     short loc_180058B41
0x180058b7d  lea     rcx, [rsp+270h+var_248]
0x180058b82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058b87  movsxd  rcx, [rsp+270h+var_250]
0x180058b8c  movsxd  rax, [rsp+270h+var_24C]
0x180058b91  shl     rcx, 1Fh
0x180058b95  or      rcx, rax
0x180058b98  mov     [rdi], rcx
0x180058b9b  xor     ebx, ebx
0x180058b9d  lea     rcx, [rsp+270h+var_240]
0x180058ba2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058ba7  mov     eax, ebx
0x180058ba9  mov     rcx, [rbp+170h+var_20]
0x180058bb0  xor     rcx, rsp; StackCookie
0x180058bb3  call    __security_check_cookie
0x180058bb8  mov     rbx, [rsp+270h+arg_8]
0x180058bc0  add     rsp, 260h
0x180058bc7  pop     r14
0x180058bc9  pop     rdi
0x180058bca  pop     rbp
0x180058bcb  retn
```

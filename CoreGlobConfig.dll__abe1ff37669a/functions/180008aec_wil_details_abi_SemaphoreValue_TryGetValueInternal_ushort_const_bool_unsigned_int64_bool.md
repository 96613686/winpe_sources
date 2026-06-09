# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008aec`
- end: `0x180008caa`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008a68`

## callees

- `0x180002380`
- `0x1800067a4`
- `0x1800075fc`
- `0x180008274`
- `0x180008294`
- `0x1800087e4`
- `0x180008870`
- `0x180008aec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008b55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008bf5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008b55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b65`

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
0x180008aec  mov     [rsp-8+arg_8], rbx
0x180008af1  push    rbp
0x180008af2  push    rdi
0x180008af3  push    r14
0x180008af5  lea     rbp, [rsp-160h]
0x180008afd  sub     rsp, 260h
0x180008b04  mov     rax, cs:__security_cookie
0x180008b0b  xor     rax, rsp
0x180008b0e  mov     [rbp+170h+var_20], rax
0x180008b15  mov     rdi, r8
0x180008b18  mov     qword ptr [r8], 0
0x180008b1f  mov     r8, rcx; unsigned __int16 *
0x180008b22  mov     r14d, 104h
0x180008b28  mov     edx, r14d; unsigned __int64
0x180008b2b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008b30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008b35  lea     r8, aP0; "_p0"
0x180008b3c  mov     edx, r14d; unsigned __int64
0x180008b3f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008b44  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b49  lea     r8, [rsp+270h+Name]; lpName
0x180008b4e  xor     edx, edx; bInheritHandle
0x180008b50  mov     ecx, 1F0003h; dwDesiredAccess
0x180008b55  call    cs:__imp_OpenSemaphoreW
0x180008b5b  mov     [rsp+270h+var_240], rax
0x180008b60  test    rax, rax
0x180008b63  jnz     short loc_180008B92
0x180008b65  call    cs:__imp_GetLastError
0x180008b6b  cmp     eax, 2
0x180008b6e  jz      loc_180008C79
0x180008b74  mov     rcx, [rbp+178h]; this
0x180008b7b  lea     r8, aWil; "wil"
0x180008b82  lea     edx, [r14-34h]; void *
0x180008b86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008b8b  mov     ebx, eax
0x180008b8d  jmp     loc_180008C7B
0x180008b92  lea     rdx, [rsp+270h+var_24C]; int *
0x180008b97  mov     [rsp+270h+var_24C], 0
0x180008b9f  mov     rcx, rax; hHandle
0x180008ba2  mov     [rsp+270h+var_250], 0; int
0x180008baa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008baf  mov     ebx, eax
0x180008bb1  test    eax, eax
0x180008bb3  jns     short loc_180008BD5
0x180008bb5  mov     rcx, [rbp+178h]; this
0x180008bbc  lea     r8, aWil; "wil"
0x180008bc3  mov     r9d, eax; char *
0x180008bc6  mov     edx, 0D6h; void *
0x180008bcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bd0  jmp     loc_180008C7B
0x180008bd5  lea     r8, asc_1800282C8; "h"
0x180008bdc  mov     rdx, r14; unsigned __int64
0x180008bdf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008be4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008be9  lea     r8, [rsp+270h+Name]; lpName
0x180008bee  xor     edx, edx; bInheritHandle
0x180008bf0  mov     ecx, 1F0003h; dwDesiredAccess
0x180008bf5  call    cs:__imp_OpenSemaphoreW
0x180008bfb  mov     [rsp+270h+var_248], rax
0x180008c00  test    rax, rax
0x180008c03  jnz     short loc_180008C2B
0x180008c05  mov     rcx, [rbp+178h]; this
0x180008c0c  lea     r8, aWil; "wil"
0x180008c13  mov     edx, 0DCh; void *
0x180008c18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008c1d  mov     ebx, eax
0x180008c1f  lea     rcx, [rsp+270h+var_248]
0x180008c24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008c29  jmp     short loc_180008C7B
0x180008c2b  lea     rdx, [rsp+270h+var_250]; int *
0x180008c30  mov     rcx, rax; hHandle
0x180008c33  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008c38  mov     ebx, eax
0x180008c3a  test    eax, eax
0x180008c3c  jns     short loc_180008C5B
0x180008c3e  mov     rcx, [rbp+178h]; this
0x180008c45  lea     r8, aWil; "wil"
0x180008c4c  mov     r9d, eax; char *
0x180008c4f  mov     edx, 0DEh; void *
0x180008c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c59  jmp     short loc_180008C1F
0x180008c5b  lea     rcx, [rsp+270h+var_248]
0x180008c60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008c65  movsxd  rcx, [rsp+270h+var_250]
0x180008c6a  movsxd  rax, [rsp+270h+var_24C]
0x180008c6f  shl     rcx, 1Fh
0x180008c73  or      rcx, rax
0x180008c76  mov     [rdi], rcx
0x180008c79  xor     ebx, ebx
0x180008c7b  lea     rcx, [rsp+270h+var_240]
0x180008c80  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008c85  mov     eax, ebx
0x180008c87  mov     rcx, [rbp+170h+var_20]
0x180008c8e  xor     rcx, rsp; StackCookie
0x180008c91  call    __security_check_cookie
0x180008c96  mov     rbx, [rsp+270h+arg_8]
0x180008c9e  add     rsp, 260h
0x180008ca5  pop     r14
0x180008ca7  pop     rdi
0x180008ca8  pop     rbp
0x180008ca9  retn
```

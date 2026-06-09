# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005a88`
- end: `0x140005c38`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005a04`

## callees

- `0x1400023e0`
- `0x140003da4`
- `0x140004a0c`
- `0x140005490`
- `0x1400054b0`
- `0x1400057b8`
- `0x14000580c`
- `0x140005a88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005af1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005b8a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005af1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b01`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x140005a88  mov     [rsp-8+arg_8], rbx
0x140005a8d  push    rbp
0x140005a8e  push    rdi
0x140005a8f  push    r14
0x140005a91  lea     rbp, [rsp-160h]
0x140005a99  sub     rsp, 260h
0x140005aa0  mov     rax, cs:__security_cookie
0x140005aa7  xor     rax, rsp
0x140005aaa  mov     [rbp+170h+var_20], rax
0x140005ab1  mov     rdi, r8
0x140005ab4  mov     qword ptr [r8], 0
0x140005abb  mov     r8, rcx; wchar_t *
0x140005abe  mov     r14d, 104h
0x140005ac4  mov     edx, r14d; unsigned __int64
0x140005ac7  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005acc  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140005ad1  lea     r8, aP0; "_p0"
0x140005ad8  mov     edx, r14d; unsigned __int64
0x140005adb  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005ae0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140005ae5  lea     r8, [rsp+270h+Name]; lpName
0x140005aea  xor     edx, edx; bInheritHandle
0x140005aec  mov     ecx, 1F0003h; dwDesiredAccess
0x140005af1  call    cs:__imp_OpenSemaphoreW
0x140005af7  mov     [rsp+270h+var_240], rax
0x140005afc  test    rax, rax
0x140005aff  jnz     short loc_140005B27
0x140005b01  call    cs:__imp_GetLastError
0x140005b07  cmp     eax, 2
0x140005b0a  jz      loc_140005C07
0x140005b10  mov     rcx, [rbp+178h]; this
0x140005b17  lea     edx, [r14-34h]; void *
0x140005b1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005b20  mov     ebx, eax
0x140005b22  jmp     loc_140005C09
0x140005b27  lea     rdx, [rsp+270h+var_24C]; int *
0x140005b2c  mov     [rsp+270h+var_24C], 0
0x140005b34  mov     rcx, rax; hHandle
0x140005b37  mov     [rsp+270h+var_250], 0; int
0x140005b3f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005b44  mov     ebx, eax
0x140005b46  test    eax, eax
0x140005b48  jns     short loc_140005B6A
0x140005b4a  mov     rcx, [rbp+178h]; this
0x140005b51  lea     r8, aWil; "wil"
0x140005b58  mov     r9d, eax; char *
0x140005b5b  mov     edx, 0D6h; void *
0x140005b60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005b65  jmp     loc_140005C09
0x140005b6a  lea     r8, asc_14002F638; "h"
0x140005b71  mov     rdx, r14; unsigned __int64
0x140005b74  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005b79  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140005b7e  lea     r8, [rsp+270h+Name]; lpName
0x140005b83  xor     edx, edx; bInheritHandle
0x140005b85  mov     ecx, 1F0003h; dwDesiredAccess
0x140005b8a  call    cs:__imp_OpenSemaphoreW
0x140005b90  mov     [rsp+270h+var_248], rax
0x140005b95  test    rax, rax
0x140005b98  jnz     short loc_140005BB9
0x140005b9a  mov     rcx, [rbp+178h]; this
0x140005ba1  mov     edx, 0DCh; void *
0x140005ba6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005bab  mov     ebx, eax
0x140005bad  lea     rcx, [rsp+270h+var_248]
0x140005bb2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005bb7  jmp     short loc_140005C09
0x140005bb9  lea     rdx, [rsp+270h+var_250]; int *
0x140005bbe  mov     rcx, rax; hHandle
0x140005bc1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005bc6  mov     ebx, eax
0x140005bc8  test    eax, eax
0x140005bca  jns     short loc_140005BE9
0x140005bcc  mov     rcx, [rbp+178h]; this
0x140005bd3  lea     r8, aWil; "wil"
0x140005bda  mov     r9d, eax; char *
0x140005bdd  mov     edx, 0DEh; void *
0x140005be2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005be7  jmp     short loc_140005BAD
0x140005be9  lea     rcx, [rsp+270h+var_248]
0x140005bee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005bf3  movsxd  rcx, [rsp+270h+var_250]
0x140005bf8  movsxd  rax, [rsp+270h+var_24C]
0x140005bfd  shl     rcx, 1Fh
0x140005c01  or      rcx, rax
0x140005c04  mov     [rdi], rcx
0x140005c07  xor     ebx, ebx
0x140005c09  lea     rcx, [rsp+270h+var_240]
0x140005c0e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005c13  mov     eax, ebx
0x140005c15  mov     rcx, [rbp+170h+var_20]
0x140005c1c  xor     rcx, rsp; StackCookie
0x140005c1f  call    __security_check_cookie
0x140005c24  mov     rbx, [rsp+270h+arg_8]
0x140005c2c  add     rsp, 260h
0x140005c33  pop     r14
0x140005c35  pop     rdi
0x140005c36  pop     rbp
0x140005c37  retn
```

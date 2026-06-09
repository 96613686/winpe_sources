# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001b6b8`
- end: `0x18001b895`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `477`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001b490`
- `0x180023454`

## callees

- `0x18001b670`
- `0x18001b68c`
- `0x18001b6b8`
- `0x18001b89c`
- `0x180023328`
- `0x1800234c8`
- `0x1800277b0`
- `0x180040410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b74f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b7e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b74f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b7e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b762`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v4; // rax
  size_t v6; // rdx
  __int64 v7; // r9
  wchar_t *v8; // rcx
  wil::details *v9; // rax
  wil::details *v10; // rbx
  unsigned int v11; // r8d
  const char *v12; // r9
  int ValueFromSemaphore; // eax
  size_t v15; // rdx
  unsigned int v16; // r8d
  unsigned int LastError; // edi
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  int v21; // eax
  unsigned int v22; // r8d
  void *v23; // rdx
  int v24; // [rsp+20h] [rbp-E0h] BYREF
  int v25; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v26; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v27; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = pszDest;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(pszDest, v6, L"_p0");
  v9 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v27 = v9;
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v11, v12);
    LastError = 0;
    goto LABEL_14;
  }
  v25 = 0;
  v24 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v25);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v16, (const char *)(unsigned int)ValueFromSemaphore, v24);
    goto LABEL_14;
  }
  StringCchCatW(pszDest, v15, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v26 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
LABEL_13:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v24);
  LastError = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v24);
    goto LABEL_13;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
  *a3 = v25 | (unsigned __int64)((__int64)v24 << 31);
  wil::details::CloseHandle(v10, v23);
  return 0;
}

```

## disassembly

```asm
0x18001b6b8  mov     [rsp-8+arg_0], rbx
0x18001b6bd  mov     [rsp-8+arg_8], rsi
0x18001b6c2  push    rbp
0x18001b6c3  push    rdi
0x18001b6c4  push    r14
0x18001b6c6  lea     rbp, [rsp-160h]
0x18001b6ce  sub     rsp, 260h
0x18001b6d5  mov     rax, cs:__security_cookie
0x18001b6dc  xor     rax, rsp
0x18001b6df  mov     [rbp+170h+var_20], rax
0x18001b6e6  xor     r14d, r14d
0x18001b6e9  lea     rax, [rsp+270h+pszDest]
0x18001b6ee  mov     [r8], r14
0x18001b6f1  mov     rsi, r8
0x18001b6f4  mov     edx, 104h
0x18001b6f9  mov     r9d, 7FFFFFFEh
0x18001b6ff  test    r9, r9
0x18001b702  jz      short loc_18001B723
0x18001b704  movzx   r8d, word ptr [rcx]
0x18001b708  test    r8w, r8w
0x18001b70c  jz      short loc_18001B723
0x18001b70e  mov     [rax], r8w
0x18001b712  add     rcx, 2
0x18001b716  add     rax, 2
0x18001b71a  dec     r9
0x18001b71d  sub     rdx, 1; cchDest
0x18001b721  jnz     short loc_18001B6FF
0x18001b723  test    rdx, rdx
0x18001b726  lea     rcx, [rax-2]
0x18001b72a  lea     r8, aP0; "_p0"
0x18001b731  cmovnz  rcx, rax
0x18001b735  mov     [rcx], r14w
0x18001b739  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001b73e  call    StringCchCatW
0x18001b743  lea     r8, [rsp+270h+pszDest]; lpName
0x18001b748  xor     edx, edx; bInheritHandle
0x18001b74a  mov     ecx, 1F0003h; dwDesiredAccess
0x18001b74f  call    cs:__imp_OpenSemaphoreW
0x18001b755  mov     [rsp+270h+var_240], rax
0x18001b75a  mov     rbx, rax
0x18001b75d  test    rax, rax
0x18001b760  jnz     short loc_18001B7A9
0x18001b762  call    cs:__imp_GetLastError
0x18001b768  cmp     eax, 2
0x18001b76b  jz      loc_18001B88D
0x18001b771  mov     rcx, [rbp+178h]; this
0x18001b778  mov     edx, 0D0h; void *
0x18001b77d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b782  mov     rcx, [rbp+170h+var_20]
0x18001b789  xor     rcx, rsp; StackCookie
0x18001b78c  call    __security_check_cookie
0x18001b791  lea     r11, [rsp+270h+var_10]
0x18001b799  mov     rbx, [r11+20h]
0x18001b79d  mov     rsi, [r11+28h]
0x18001b7a1  mov     rsp, r11
0x18001b7a4  pop     r14
0x18001b7a6  pop     rdi
0x18001b7a7  pop     rbp
0x18001b7a8  retn
0x18001b7a9  lea     rdx, [rsp+270h+var_24C]; int *
0x18001b7ae  mov     [rsp+270h+var_24C], r14d
0x18001b7b3  mov     rcx, rbx; hHandle
0x18001b7b6  mov     [rsp+270h+var_250], r14d; int
0x18001b7bb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001b7c0  mov     edi, eax
0x18001b7c2  test    eax, eax
0x18001b7c4  js      short loc_18001B821
0x18001b7c6  lea     r8, asc_180079E28; "h"
0x18001b7cd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001b7d2  call    StringCchCatW
0x18001b7d7  lea     r8, [rsp+270h+pszDest]; lpName
0x18001b7dc  xor     edx, edx; bInheritHandle
0x18001b7de  mov     ecx, 1F0003h; dwDesiredAccess
0x18001b7e3  call    cs:__imp_OpenSemaphoreW
0x18001b7e9  mov     [rsp+270h+var_248], rax
0x18001b7ee  test    rax, rax
0x18001b7f1  jnz     short loc_18001B837
0x18001b7f3  mov     rcx, [rbp+178h]; this
0x18001b7fa  mov     edx, 0DCh; void *
0x18001b7ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b804  mov     edi, eax
0x18001b806  lea     rcx, [rsp+270h+var_248]
0x18001b80b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b810  lea     rcx, [rsp+270h+var_240]
0x18001b815  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b81a  mov     eax, edi
0x18001b81c  jmp     loc_18001B782
0x18001b821  mov     rcx, [rbp+178h]; this
0x18001b828  mov     r9d, eax; char *
0x18001b82b  mov     edx, 0D6h; void *
0x18001b830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b835  jmp     short loc_18001B810
0x18001b837  lea     rdx, [rsp+270h+var_250]; int *
0x18001b83c  mov     rcx, rax; hHandle
0x18001b83f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001b844  mov     edi, eax
0x18001b846  test    eax, eax
0x18001b848  jns     short loc_18001B860
0x18001b84a  mov     rcx, [rbp+178h]; this
0x18001b851  mov     r9d, eax; char *
0x18001b854  mov     edx, 0DEh; void *
0x18001b859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b85e  jmp     short loc_18001B806
0x18001b860  lea     rcx, [rsp+270h+var_248]
0x18001b865  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b86a  movsxd  rax, [rsp+270h+var_24C]
0x18001b86f  movsxd  rcx, [rsp+270h+var_250]
0x18001b874  shl     rcx, 1Fh
0x18001b878  or      rcx, rax
0x18001b87b  mov     [rsi], rcx
0x18001b87e  mov     rcx, rbx; this
0x18001b881  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001b886  xor     eax, eax
0x18001b888  jmp     loc_18001B782
0x18001b88d  mov     edi, r14d
0x18001b890  jmp     loc_18001B810
```

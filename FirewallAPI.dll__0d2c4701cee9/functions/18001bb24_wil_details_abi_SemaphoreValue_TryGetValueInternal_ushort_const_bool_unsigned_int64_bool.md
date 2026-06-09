# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001bb24`
- end: `0x18001bd14`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `496`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001b8e0`
- `0x180024ee4`

## callees

- `0x18001bad4`
- `0x18001baf4`
- `0x18001bb24`
- `0x18001bd1c`
- `0x180024db4`
- `0x180024f5c`
- `0x1800294b0`
- `0x1800435b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bbbb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bc5c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bbbb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001bc5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbd4`

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
0x18001bb24  mov     [rsp-8+arg_0], rbx
0x18001bb29  mov     [rsp-8+arg_8], rsi
0x18001bb2e  push    rbp
0x18001bb2f  push    rdi
0x18001bb30  push    r14
0x18001bb32  lea     rbp, [rsp-160h]
0x18001bb3a  sub     rsp, 260h
0x18001bb41  mov     rax, cs:__security_cookie
0x18001bb48  xor     rax, rsp
0x18001bb4b  mov     [rbp+170h+var_20], rax
0x18001bb52  xor     r14d, r14d
0x18001bb55  lea     rax, [rsp+270h+pszDest]
0x18001bb5a  mov     [r8], r14
0x18001bb5d  mov     rsi, r8
0x18001bb60  mov     edx, 104h
0x18001bb65  mov     r9d, 7FFFFFFEh
0x18001bb6b  test    r9, r9
0x18001bb6e  jz      short loc_18001BB8F
0x18001bb70  movzx   r8d, word ptr [rcx]
0x18001bb74  test    r8w, r8w
0x18001bb78  jz      short loc_18001BB8F
0x18001bb7a  mov     [rax], r8w
0x18001bb7e  add     rcx, 2
0x18001bb82  add     rax, 2
0x18001bb86  dec     r9
0x18001bb89  sub     rdx, 1; cchDest
0x18001bb8d  jnz     short loc_18001BB6B
0x18001bb8f  test    rdx, rdx
0x18001bb92  lea     rcx, [rax-2]
0x18001bb96  lea     r8, aP0; "_p0"
0x18001bb9d  cmovnz  rcx, rax
0x18001bba1  mov     [rcx], r14w
0x18001bba5  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001bbaa  call    StringCchCatW
0x18001bbaf  lea     r8, [rsp+270h+pszDest]; lpName
0x18001bbb4  xor     edx, edx; bInheritHandle
0x18001bbb6  mov     ecx, 1F0003h; dwDesiredAccess
0x18001bbbb  call    cs:__imp_OpenSemaphoreW
0x18001bbc2  nop     dword ptr [rax+rax+00h]
0x18001bbc7  mov     [rsp+270h+var_240], rax
0x18001bbcc  mov     rbx, rax
0x18001bbcf  test    rax, rax
0x18001bbd2  jnz     short loc_18001BC22
0x18001bbd4  call    cs:__imp_GetLastError
0x18001bbdb  nop     dword ptr [rax+rax+00h]
0x18001bbe0  cmp     eax, 2
0x18001bbe3  jz      loc_18001BD0C
0x18001bbe9  mov     rcx, [rbp+178h]; this
0x18001bbf0  mov     edx, 0D0h; void *
0x18001bbf5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bbfa  mov     rcx, [rbp+170h+var_20]
0x18001bc01  xor     rcx, rsp; StackCookie
0x18001bc04  call    __security_check_cookie
0x18001bc09  lea     r11, [rsp+270h+var_10]
0x18001bc11  mov     rbx, [r11+20h]
0x18001bc15  mov     rsi, [r11+28h]
0x18001bc19  mov     rsp, r11
0x18001bc1c  pop     r14
0x18001bc1e  pop     rdi
0x18001bc1f  pop     rbp
0x18001bc20  retn
0x18001bc22  lea     rdx, [rsp+270h+var_24C]; int *
0x18001bc27  mov     [rsp+270h+var_24C], r14d
0x18001bc2c  mov     rcx, rbx; hHandle
0x18001bc2f  mov     [rsp+270h+var_250], r14d; int
0x18001bc34  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001bc39  mov     edi, eax
0x18001bc3b  test    eax, eax
0x18001bc3d  js      short loc_18001BCA0
0x18001bc3f  lea     r8, asc_180080228; "h"
0x18001bc46  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001bc4b  call    StringCchCatW
0x18001bc50  lea     r8, [rsp+270h+pszDest]; lpName
0x18001bc55  xor     edx, edx; bInheritHandle
0x18001bc57  mov     ecx, 1F0003h; dwDesiredAccess
0x18001bc5c  call    cs:__imp_OpenSemaphoreW
0x18001bc63  nop     dword ptr [rax+rax+00h]
0x18001bc68  mov     [rsp+270h+var_248], rax
0x18001bc6d  test    rax, rax
0x18001bc70  jnz     short loc_18001BCB6
0x18001bc72  mov     rcx, [rbp+178h]; this
0x18001bc79  mov     edx, 0DCh; void *
0x18001bc7e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bc83  mov     edi, eax
0x18001bc85  lea     rcx, [rsp+270h+var_248]
0x18001bc8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bc8f  lea     rcx, [rsp+270h+var_240]
0x18001bc94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bc99  mov     eax, edi
0x18001bc9b  jmp     loc_18001BBFA
0x18001bca0  mov     rcx, [rbp+178h]; this
0x18001bca7  mov     r9d, eax; char *
0x18001bcaa  mov     edx, 0D6h; void *
0x18001bcaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcb4  jmp     short loc_18001BC8F
0x18001bcb6  lea     rdx, [rsp+270h+var_250]; int *
0x18001bcbb  mov     rcx, rax; hHandle
0x18001bcbe  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001bcc3  mov     edi, eax
0x18001bcc5  test    eax, eax
0x18001bcc7  jns     short loc_18001BCDF
0x18001bcc9  mov     rcx, [rbp+178h]; this
0x18001bcd0  mov     r9d, eax; char *
0x18001bcd3  mov     edx, 0DEh; void *
0x18001bcd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcdd  jmp     short loc_18001BC85
0x18001bcdf  lea     rcx, [rsp+270h+var_248]
0x18001bce4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bce9  movsxd  rax, [rsp+270h+var_24C]
0x18001bcee  movsxd  rcx, [rsp+270h+var_250]
0x18001bcf3  shl     rcx, 1Fh
0x18001bcf7  or      rcx, rax
0x18001bcfa  mov     [rsi], rcx
0x18001bcfd  mov     rcx, rbx; this
0x18001bd00  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001bd05  xor     eax, eax
0x18001bd07  jmp     loc_18001BBFA
0x18001bd0c  mov     edi, r14d
0x18001bd0f  jmp     loc_18001BC8F
```

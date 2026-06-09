# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800a765c`
- end: `0x1800a7806`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800a66a4`

## callees

- `0x180003180`
- `0x1800a4c74`
- `0x1800a65b0`
- `0x1800a6e0c`
- `0x1800a72f4`
- `0x1800a7588`
- `0x1800a7604`
- `0x1800a765c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a76c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a7757`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a76c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a7757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a76d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a76d0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v17);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
0x1800a765c  mov     [rsp-8+arg_8], rbx
0x1800a7661  mov     [rsp-8+arg_18], rdi
0x1800a7666  push    rbp
0x1800a7667  lea     rbp, [rsp-170h]
0x1800a766f  sub     rsp, 270h
0x1800a7676  mov     rax, cs:__security_cookie
0x1800a767d  xor     rax, rsp
0x1800a7680  mov     [rbp+170h+var_10], rax
0x1800a7687  mov     r9, rcx; pszSrc
0x1800a768a  mov     qword ptr [r8], 0
0x1800a7691  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800a7696  mov     edx, 104h; cchDest
0x1800a769b  mov     rdi, r8
0x1800a769e  call    StringCopyWorkerW
0x1800a76a3  lea     r8, aP0; "_p0"
0x1800a76aa  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800a76af  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a76b4  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a76b9  xor     edx, edx; bInheritHandle
0x1800a76bb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a76c0  call    cs:__imp_OpenSemaphoreW
0x1800a76c6  mov     [rsp+270h+var_230], rax
0x1800a76cb  test    rax, rax
0x1800a76ce  jnz     short loc_1800A76F7
0x1800a76d0  call    cs:__imp_GetLastError
0x1800a76d6  cmp     eax, 2
0x1800a76d9  jz      loc_1800A77D4
0x1800a76df  mov     rcx, [rbp+178h]; this
0x1800a76e6  mov     edx, 0D0h; void *
0x1800a76eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a76f0  mov     ebx, eax
0x1800a76f2  jmp     loc_1800A77D6
0x1800a76f7  lea     rdx, [rsp+270h+var_23C]; int *
0x1800a76fc  mov     [rsp+270h+var_23C], 0
0x1800a7704  mov     rcx, rax; hHandle
0x1800a7707  mov     [rsp+270h+var_240], 0
0x1800a770f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a7714  mov     ebx, eax
0x1800a7716  test    eax, eax
0x1800a7718  jns     short loc_1800A773A
0x1800a771a  mov     rcx, [rbp+178h]; this
0x1800a7721  lea     r8, aWil; "wil"
0x1800a7728  mov     r9d, eax; char *
0x1800a772b  mov     edx, 0D6h; void *
0x1800a7730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7735  jmp     loc_1800A77D6
0x1800a773a  lea     r8, asc_180113C10; "h"
0x1800a7741  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800a7746  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a774b  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a7750  xor     edx, edx; bInheritHandle
0x1800a7752  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a7757  call    cs:__imp_OpenSemaphoreW
0x1800a775d  mov     [rsp+270h+var_238], rax
0x1800a7762  test    rax, rax
0x1800a7765  jnz     short loc_1800A7786
0x1800a7767  mov     rcx, [rbp+178h]; this
0x1800a776e  mov     edx, 0DCh; void *
0x1800a7773  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a7778  mov     ebx, eax
0x1800a777a  lea     rcx, [rsp+270h+var_238]
0x1800a777f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a7784  jmp     short loc_1800A77D6
0x1800a7786  lea     rdx, [rsp+270h+var_240]; int *
0x1800a778b  mov     rcx, rax; hHandle
0x1800a778e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a7793  mov     ebx, eax
0x1800a7795  test    eax, eax
0x1800a7797  jns     short loc_1800A77B6
0x1800a7799  mov     rcx, [rbp+178h]; this
0x1800a77a0  lea     r8, aWil; "wil"
0x1800a77a7  mov     r9d, eax; char *
0x1800a77aa  mov     edx, 0DEh; void *
0x1800a77af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a77b4  jmp     short loc_1800A777A
0x1800a77b6  lea     rcx, [rsp+270h+var_238]
0x1800a77bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a77c0  movsxd  rcx, [rsp+270h+var_240]
0x1800a77c5  movsxd  rax, [rsp+270h+var_23C]
0x1800a77ca  shl     rcx, 1Fh
0x1800a77ce  or      rcx, rax
0x1800a77d1  mov     [rdi], rcx
0x1800a77d4  xor     ebx, ebx
0x1800a77d6  lea     rcx, [rsp+270h+var_230]
0x1800a77db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a77e0  mov     eax, ebx
0x1800a77e2  mov     rcx, [rbp+170h+var_10]
0x1800a77e9  xor     rcx, rsp; StackCookie
0x1800a77ec  call    __security_check_cookie
0x1800a77f1  lea     r11, [rsp+270h+var_s0]
0x1800a77f9  mov     rbx, [r11+18h]
0x1800a77fd  mov     rdi, [r11+28h]
0x1800a7801  mov     rsp, r11
0x1800a7804  pop     rbp
0x1800a7805  retn
```

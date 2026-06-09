# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800093ec`
- end: `0x1800095b7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009368`

## callees

- `0x18000473c`
- `0x180006494`
- `0x1800087cc`
- `0x1800087ec`
- `0x180008ee0`
- `0x180009010`
- `0x1800093ec`
- `0x180028860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009450`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800094fa`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009450`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800094fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009466`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800093ec  mov     [rsp-8+arg_8], rbx
0x1800093f1  mov     [rsp-8+arg_18], rdi
0x1800093f6  push    rbp
0x1800093f7  lea     rbp, [rsp-170h]
0x1800093ff  sub     rsp, 270h
0x180009406  mov     rax, cs:__security_cookie
0x18000940d  xor     rax, rsp
0x180009410  mov     [rbp+170h+var_10], rax
0x180009417  mov     r9, rcx; pszSrc
0x18000941a  mov     qword ptr [r8], 0
0x180009421  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180009426  mov     edx, 104h; cchDest
0x18000942b  mov     rdi, r8
0x18000942e  call    StringCopyWorkerW
0x180009433  lea     r8, aP0; "_p0"
0x18000943a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000943f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009444  lea     r8, [rsp+270h+pszDest]; lpName
0x180009449  xor     edx, edx; bInheritHandle
0x18000944b  mov     ecx, 1F0003h; dwDesiredAccess
0x180009450  call    cs:__imp_OpenSemaphoreW
0x180009457  nop     dword ptr [rax+rax+00h]
0x18000945c  mov     [rsp+270h+var_230], rax
0x180009461  test    rax, rax
0x180009464  jnz     short loc_18000949A
0x180009466  call    cs:__imp_GetLastError
0x18000946d  nop     dword ptr [rax+rax+00h]
0x180009472  cmp     eax, 2
0x180009475  jz      loc_180009584
0x18000947b  mov     rcx, [rbp+178h]; this
0x180009482  lea     r8, aWil; "wil"
0x180009489  mov     edx, 0D0h; void *
0x18000948e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009493  mov     ebx, eax
0x180009495  jmp     loc_180009586
0x18000949a  lea     rdx, [rsp+270h+var_23C]; int *
0x18000949f  mov     [rsp+270h+var_23C], 0
0x1800094a7  mov     rcx, rax; hHandle
0x1800094aa  mov     [rsp+270h+var_240], 0
0x1800094b2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800094b7  mov     ebx, eax
0x1800094b9  test    eax, eax
0x1800094bb  jns     short loc_1800094DD
0x1800094bd  mov     rcx, [rbp+178h]; this
0x1800094c4  lea     r8, aWil; "wil"
0x1800094cb  mov     r9d, eax; char *
0x1800094ce  mov     edx, 0D6h; void *
0x1800094d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094d8  jmp     loc_180009586
0x1800094dd  lea     r8, asc_180033390; "h"
0x1800094e4  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800094e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800094ee  lea     r8, [rsp+270h+pszDest]; lpName
0x1800094f3  xor     edx, edx; bInheritHandle
0x1800094f5  mov     ecx, 1F0003h; dwDesiredAccess
0x1800094fa  call    cs:__imp_OpenSemaphoreW
0x180009501  nop     dword ptr [rax+rax+00h]
0x180009506  mov     [rsp+270h+var_238], rax
0x18000950b  test    rax, rax
0x18000950e  jnz     short loc_180009536
0x180009510  mov     rcx, [rbp+178h]; this
0x180009517  lea     r8, aWil; "wil"
0x18000951e  mov     edx, 0DCh; void *
0x180009523  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009528  mov     ebx, eax
0x18000952a  lea     rcx, [rsp+270h+var_238]
0x18000952f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009534  jmp     short loc_180009586
0x180009536  lea     rdx, [rsp+270h+var_240]; int *
0x18000953b  mov     rcx, rax; hHandle
0x18000953e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009543  mov     ebx, eax
0x180009545  test    eax, eax
0x180009547  jns     short loc_180009566
0x180009549  mov     rcx, [rbp+178h]; this
0x180009550  lea     r8, aWil; "wil"
0x180009557  mov     r9d, eax; char *
0x18000955a  mov     edx, 0DEh; void *
0x18000955f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009564  jmp     short loc_18000952A
0x180009566  lea     rcx, [rsp+270h+var_238]
0x18000956b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009570  movsxd  rcx, [rsp+270h+var_240]
0x180009575  movsxd  rax, [rsp+270h+var_23C]
0x18000957a  shl     rcx, 1Fh
0x18000957e  or      rcx, rax
0x180009581  mov     [rdi], rcx
0x180009584  xor     ebx, ebx
0x180009586  lea     rcx, [rsp+270h+var_230]
0x18000958b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009590  mov     eax, ebx
0x180009592  mov     rcx, [rbp+170h+var_10]
0x180009599  xor     rcx, rsp; StackCookie
0x18000959c  call    __security_check_cookie
0x1800095a1  lea     r11, [rsp+270h+var_s0]
0x1800095a9  mov     rbx, [r11+18h]
0x1800095ad  mov     rdi, [r11+28h]
0x1800095b1  mov     rsp, r11
0x1800095b4  pop     rbp
0x1800095b5  retn
```

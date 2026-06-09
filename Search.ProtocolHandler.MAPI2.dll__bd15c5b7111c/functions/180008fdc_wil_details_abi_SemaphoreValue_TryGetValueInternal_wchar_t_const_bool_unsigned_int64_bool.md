# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008fdc`
- end: `0x180009186`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008f58`

## callees

- `0x180002300`
- `0x180004ce4`
- `0x1800063e8`
- `0x18000833c`
- `0x18000835c`
- `0x180008a20`
- `0x180008a9c`
- `0x180008fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009040`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800090d7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009040`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800090d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009050`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
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
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180008fdc  mov     [rsp-8+arg_8], rbx
0x180008fe1  mov     [rsp-8+arg_18], rdi
0x180008fe6  push    rbp
0x180008fe7  lea     rbp, [rsp-160h]
0x180008fef  sub     rsp, 260h
0x180008ff6  mov     rax, cs:__security_cookie
0x180008ffd  xor     rax, rsp
0x180009000  mov     [rbp+160h+var_10], rax
0x180009007  mov     rdi, r8
0x18000900a  mov     qword ptr [r8], 0
0x180009011  mov     r8, rcx; wchar_t *
0x180009014  mov     edx, 104h; unsigned __int64
0x180009019  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000901e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009023  lea     r8, aP0; "_p0"
0x18000902a  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000902f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009034  lea     r8, [rsp+260h+Name]; lpName
0x180009039  xor     edx, edx; bInheritHandle
0x18000903b  mov     ecx, 1F0003h; dwDesiredAccess
0x180009040  call    cs:__imp_OpenSemaphoreW
0x180009046  mov     [rsp+260h+var_230], rax
0x18000904b  test    rax, rax
0x18000904e  jnz     short loc_180009077
0x180009050  call    cs:__imp_GetLastError
0x180009056  cmp     eax, 2
0x180009059  jz      loc_180009154
0x18000905f  mov     rcx, [rbp+168h]; this
0x180009066  mov     edx, 0D0h; void *
0x18000906b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009070  mov     ebx, eax
0x180009072  jmp     loc_180009156
0x180009077  lea     rdx, [rsp+260h+var_23C]; int *
0x18000907c  mov     [rsp+260h+var_23C], 0
0x180009084  mov     rcx, rax; hHandle
0x180009087  mov     [rsp+260h+var_240], 0; int
0x18000908f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009094  mov     ebx, eax
0x180009096  test    eax, eax
0x180009098  jns     short loc_1800090BA
0x18000909a  mov     rcx, [rbp+168h]; this
0x1800090a1  lea     r8, aWil; "wil"
0x1800090a8  mov     r9d, eax; char *
0x1800090ab  mov     edx, 0D6h; void *
0x1800090b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090b5  jmp     loc_180009156
0x1800090ba  lea     r8, asc_180044818; "h"
0x1800090c1  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800090c6  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800090cb  lea     r8, [rsp+260h+Name]; lpName
0x1800090d0  xor     edx, edx; bInheritHandle
0x1800090d2  mov     ecx, 1F0003h; dwDesiredAccess
0x1800090d7  call    cs:__imp_OpenSemaphoreW
0x1800090dd  mov     [rsp+260h+var_238], rax
0x1800090e2  test    rax, rax
0x1800090e5  jnz     short loc_180009106
0x1800090e7  mov     rcx, [rbp+168h]; this
0x1800090ee  mov     edx, 0DCh; void *
0x1800090f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800090f8  mov     ebx, eax
0x1800090fa  lea     rcx, [rsp+260h+var_238]
0x1800090ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009104  jmp     short loc_180009156
0x180009106  lea     rdx, [rsp+260h+var_240]; int *
0x18000910b  mov     rcx, rax; hHandle
0x18000910e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009113  mov     ebx, eax
0x180009115  test    eax, eax
0x180009117  jns     short loc_180009136
0x180009119  mov     rcx, [rbp+168h]; this
0x180009120  lea     r8, aWil; "wil"
0x180009127  mov     r9d, eax; char *
0x18000912a  mov     edx, 0DEh; void *
0x18000912f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009134  jmp     short loc_1800090FA
0x180009136  lea     rcx, [rsp+260h+var_238]
0x18000913b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009140  movsxd  rcx, [rsp+260h+var_240]
0x180009145  movsxd  rax, [rsp+260h+var_23C]
0x18000914a  shl     rcx, 1Fh
0x18000914e  or      rcx, rax
0x180009151  mov     [rdi], rcx
0x180009154  xor     ebx, ebx
0x180009156  lea     rcx, [rsp+260h+var_230]
0x18000915b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009160  mov     eax, ebx
0x180009162  mov     rcx, [rbp+160h+var_10]
0x180009169  xor     rcx, rsp; StackCookie
0x18000916c  call    __security_check_cookie
0x180009171  lea     r11, [rsp+260h+var_s0]
0x180009179  mov     rbx, [r11+18h]
0x18000917d  mov     rdi, [r11+28h]
0x180009181  mov     rsp, r11
0x180009184  pop     rbp
0x180009185  retn
```

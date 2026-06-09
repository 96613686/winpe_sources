# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180060278`
- end: `0x180060443`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800601f4`

## callees

- `0x180056400`
- `0x18005aa60`
- `0x18005cb18`
- `0x18005e17c`
- `0x18005f4e4`
- `0x18005fc94`
- `0x18005fd8c`
- `0x180060278`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800602dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060386`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800602dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602f2`

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
  StringCopyWorkerW_0(pszDest, 0x104u, a3, pszSrc, v15);
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
0x180060278  mov     [rsp-8+arg_8], rbx
0x18006027d  mov     [rsp-8+arg_18], rdi
0x180060282  push    rbp
0x180060283  lea     rbp, [rsp-170h]
0x18006028b  sub     rsp, 270h
0x180060292  mov     rax, cs:__security_cookie
0x180060299  xor     rax, rsp
0x18006029c  mov     [rbp+170h+var_10], rax
0x1800602a3  mov     r9, rcx; pszSrc
0x1800602a6  mov     qword ptr [r8], 0
0x1800602ad  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800602b2  mov     edx, 104h; cchDest
0x1800602b7  mov     rdi, r8
0x1800602ba  call    StringCopyWorkerW_0
0x1800602bf  lea     r8, aP0; "_p0"
0x1800602c6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800602cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800602d0  lea     r8, [rsp+270h+pszDest]; lpName
0x1800602d5  xor     edx, edx; bInheritHandle
0x1800602d7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800602dc  call    cs:__imp_OpenSemaphoreW
0x1800602e3  nop     dword ptr [rax+rax+00h]
0x1800602e8  mov     [rsp+270h+var_230], rax
0x1800602ed  test    rax, rax
0x1800602f0  jnz     short loc_180060326
0x1800602f2  call    cs:__imp_GetLastError
0x1800602f9  nop     dword ptr [rax+rax+00h]
0x1800602fe  cmp     eax, 2
0x180060301  jz      loc_180060410
0x180060307  mov     rcx, [rbp+178h]; this
0x18006030e  lea     r8, aWil; "wil"
0x180060315  mov     edx, 0D0h; void *
0x18006031a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006031f  mov     ebx, eax
0x180060321  jmp     loc_180060412
0x180060326  lea     rdx, [rsp+270h+var_23C]; int *
0x18006032b  mov     [rsp+270h+var_23C], 0
0x180060333  mov     rcx, rax; hHandle
0x180060336  mov     [rsp+270h+var_240], 0
0x18006033e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180060343  mov     ebx, eax
0x180060345  test    eax, eax
0x180060347  jns     short loc_180060369
0x180060349  mov     rcx, [rbp+178h]; this
0x180060350  lea     r8, aWil; "wil"
0x180060357  mov     r9d, eax; char *
0x18006035a  mov     edx, 0D6h; void *
0x18006035f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060364  jmp     loc_180060412
0x180060369  lea     r8, asc_1800C28A8; "h"
0x180060370  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180060375  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006037a  lea     r8, [rsp+270h+pszDest]; lpName
0x18006037f  xor     edx, edx; bInheritHandle
0x180060381  mov     ecx, 1F0003h; dwDesiredAccess
0x180060386  call    cs:__imp_OpenSemaphoreW
0x18006038d  nop     dword ptr [rax+rax+00h]
0x180060392  mov     [rsp+270h+var_238], rax
0x180060397  test    rax, rax
0x18006039a  jnz     short loc_1800603C2
0x18006039c  mov     rcx, [rbp+178h]; this
0x1800603a3  lea     r8, aWil; "wil"
0x1800603aa  mov     edx, 0DCh; void *
0x1800603af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800603b4  mov     ebx, eax
0x1800603b6  lea     rcx, [rsp+270h+var_238]
0x1800603bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800603c0  jmp     short loc_180060412
0x1800603c2  lea     rdx, [rsp+270h+var_240]; int *
0x1800603c7  mov     rcx, rax; hHandle
0x1800603ca  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800603cf  mov     ebx, eax
0x1800603d1  test    eax, eax
0x1800603d3  jns     short loc_1800603F2
0x1800603d5  mov     rcx, [rbp+178h]; this
0x1800603dc  lea     r8, aWil; "wil"
0x1800603e3  mov     r9d, eax; char *
0x1800603e6  mov     edx, 0DEh; void *
0x1800603eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800603f0  jmp     short loc_1800603B6
0x1800603f2  lea     rcx, [rsp+270h+var_238]
0x1800603f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800603fc  movsxd  rcx, [rsp+270h+var_240]
0x180060401  movsxd  rax, [rsp+270h+var_23C]
0x180060406  shl     rcx, 1Fh
0x18006040a  or      rcx, rax
0x18006040d  mov     [rdi], rcx
0x180060410  xor     ebx, ebx
0x180060412  lea     rcx, [rsp+270h+var_230]
0x180060417  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006041c  mov     eax, ebx
0x18006041e  mov     rcx, [rbp+170h+var_10]
0x180060425  xor     rcx, rsp; StackCookie
0x180060428  call    __security_check_cookie
0x18006042d  lea     r11, [rsp+270h+var_s0]
0x180060435  mov     rbx, [r11+18h]
0x180060439  mov     rdi, [r11+28h]
0x18006043d  mov     rsp, r11
0x180060440  pop     rbp
0x180060441  retn
```

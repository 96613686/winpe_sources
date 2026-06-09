# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800076bc`
- end: `0x180007874`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007638`

## callees

- `0x180003160`
- `0x1800056f0`
- `0x180006420`
- `0x180006e64`
- `0x180006e84`
- `0x1800073a0`
- `0x180007530`
- `0x1800076bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007720`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800077be`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007720`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800077be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007730`

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
0x1800076bc  mov     [rsp-8+arg_8], rbx
0x1800076c1  mov     [rsp-8+arg_18], rdi
0x1800076c6  push    rbp
0x1800076c7  lea     rbp, [rsp-170h]
0x1800076cf  sub     rsp, 270h
0x1800076d6  mov     rax, cs:__security_cookie
0x1800076dd  xor     rax, rsp
0x1800076e0  mov     [rbp+170h+var_10], rax
0x1800076e7  mov     r9, rcx; pszSrc
0x1800076ea  mov     qword ptr [r8], 0
0x1800076f1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800076f6  mov     edx, 104h; cchDest
0x1800076fb  mov     rdi, r8
0x1800076fe  call    StringCopyWorkerW
0x180007703  lea     r8, aP0; "_p0"
0x18000770a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000770f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007714  lea     r8, [rsp+270h+pszDest]; lpName
0x180007719  xor     edx, edx; bInheritHandle
0x18000771b  mov     ecx, 1F0003h; dwDesiredAccess
0x180007720  call    cs:__imp_OpenSemaphoreW
0x180007726  mov     [rsp+270h+var_230], rax
0x18000772b  test    rax, rax
0x18000772e  jnz     short loc_18000775E
0x180007730  call    cs:__imp_GetLastError
0x180007736  cmp     eax, 2
0x180007739  jz      loc_180007842
0x18000773f  mov     rcx, [rbp+178h]; this
0x180007746  lea     r8, aWil; "wil"
0x18000774d  mov     edx, 0D0h; void *
0x180007752  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007757  mov     ebx, eax
0x180007759  jmp     loc_180007844
0x18000775e  lea     rdx, [rsp+270h+var_23C]; int *
0x180007763  mov     [rsp+270h+var_23C], 0
0x18000776b  mov     rcx, rax; hHandle
0x18000776e  mov     [rsp+270h+var_240], 0
0x180007776  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000777b  mov     ebx, eax
0x18000777d  test    eax, eax
0x18000777f  jns     short loc_1800077A1
0x180007781  mov     rcx, [rbp+178h]; this
0x180007788  lea     r8, aWil; "wil"
0x18000778f  mov     r9d, eax; char *
0x180007792  mov     edx, 0D6h; void *
0x180007797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000779c  jmp     loc_180007844
0x1800077a1  lea     r8, asc_180039290; "h"
0x1800077a8  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800077ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800077b2  lea     r8, [rsp+270h+pszDest]; lpName
0x1800077b7  xor     edx, edx; bInheritHandle
0x1800077b9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800077be  call    cs:__imp_OpenSemaphoreW
0x1800077c4  mov     [rsp+270h+var_238], rax
0x1800077c9  test    rax, rax
0x1800077cc  jnz     short loc_1800077F4
0x1800077ce  mov     rcx, [rbp+178h]; this
0x1800077d5  lea     r8, aWil; "wil"
0x1800077dc  mov     edx, 0DCh; void *
0x1800077e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800077e6  mov     ebx, eax
0x1800077e8  lea     rcx, [rsp+270h+var_238]
0x1800077ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800077f2  jmp     short loc_180007844
0x1800077f4  lea     rdx, [rsp+270h+var_240]; int *
0x1800077f9  mov     rcx, rax; hHandle
0x1800077fc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007801  mov     ebx, eax
0x180007803  test    eax, eax
0x180007805  jns     short loc_180007824
0x180007807  mov     rcx, [rbp+178h]; this
0x18000780e  lea     r8, aWil; "wil"
0x180007815  mov     r9d, eax; char *
0x180007818  mov     edx, 0DEh; void *
0x18000781d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007822  jmp     short loc_1800077E8
0x180007824  lea     rcx, [rsp+270h+var_238]
0x180007829  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000782e  movsxd  rcx, [rsp+270h+var_240]
0x180007833  movsxd  rax, [rsp+270h+var_23C]
0x180007838  shl     rcx, 1Fh
0x18000783c  or      rcx, rax
0x18000783f  mov     [rdi], rcx
0x180007842  xor     ebx, ebx
0x180007844  lea     rcx, [rsp+270h+var_230]
0x180007849  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000784e  mov     eax, ebx
0x180007850  mov     rcx, [rbp+170h+var_10]
0x180007857  xor     rcx, rsp; StackCookie
0x18000785a  call    __security_check_cookie
0x18000785f  lea     r11, [rsp+270h+var_s0]
0x180007867  mov     rbx, [r11+18h]
0x18000786b  mov     rdi, [r11+28h]
0x18000786f  mov     rsp, r11
0x180007872  pop     rbp
0x180007873  retn
```

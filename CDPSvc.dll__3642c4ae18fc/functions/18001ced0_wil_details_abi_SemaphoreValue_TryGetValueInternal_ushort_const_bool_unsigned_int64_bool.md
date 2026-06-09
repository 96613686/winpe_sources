# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001ced0`
- end: `0x18001d088`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002a7cc`

## callees

- `0x1800130ec`
- `0x18001ced0`
- `0x18001d090`
- `0x18001d10c`
- `0x18001d20c`
- `0x18001d264`
- `0x1800225a0`
- `0x180028cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cf34`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cfd2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cf34`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cfd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf44`

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
0x18001ced0  mov     [rsp-8+arg_8], rbx
0x18001ced5  mov     [rsp-8+arg_18], rdi
0x18001ceda  push    rbp
0x18001cedb  lea     rbp, [rsp-170h]
0x18001cee3  sub     rsp, 270h
0x18001ceea  mov     rax, cs:__security_cookie
0x18001cef1  xor     rax, rsp
0x18001cef4  mov     [rbp+170h+var_10], rax
0x18001cefb  mov     r9, rcx; pszSrc
0x18001cefe  mov     qword ptr [r8], 0
0x18001cf05  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001cf0a  mov     edx, 104h; cchDest
0x18001cf0f  mov     rdi, r8
0x18001cf12  call    StringCopyWorkerW
0x18001cf17  lea     r8, aP0; "_p0"
0x18001cf1e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001cf23  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cf28  lea     r8, [rsp+270h+pszDest]; lpName
0x18001cf2d  xor     edx, edx; bInheritHandle
0x18001cf2f  mov     ecx, 1F0003h; dwDesiredAccess
0x18001cf34  call    cs:__imp_OpenSemaphoreW
0x18001cf3a  mov     [rsp+270h+var_230], rax
0x18001cf3f  test    rax, rax
0x18001cf42  jnz     short loc_18001CF72
0x18001cf44  call    cs:__imp_GetLastError
0x18001cf4a  cmp     eax, 2
0x18001cf4d  jz      loc_18001D056
0x18001cf53  mov     rcx, [rbp+178h]; this
0x18001cf5a  lea     r8, aWil; "wil"
0x18001cf61  mov     edx, 0D0h; void *
0x18001cf66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cf6b  mov     ebx, eax
0x18001cf6d  jmp     loc_18001D058
0x18001cf72  lea     rdx, [rsp+270h+var_23C]; int *
0x18001cf77  mov     [rsp+270h+var_23C], 0
0x18001cf7f  mov     rcx, rax; hHandle
0x18001cf82  mov     [rsp+270h+var_240], 0
0x18001cf8a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001cf8f  mov     ebx, eax
0x18001cf91  test    eax, eax
0x18001cf93  jns     short loc_18001CFB5
0x18001cf95  mov     rcx, [rbp+178h]; this
0x18001cf9c  lea     r8, aWil; "wil"
0x18001cfa3  mov     r9d, eax; char *
0x18001cfa6  mov     edx, 0D6h; void *
0x18001cfab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfb0  jmp     loc_18001D058
0x18001cfb5  lea     r8, asc_180076530; "h"
0x18001cfbc  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001cfc1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cfc6  lea     r8, [rsp+270h+pszDest]; lpName
0x18001cfcb  xor     edx, edx; bInheritHandle
0x18001cfcd  mov     ecx, 1F0003h; dwDesiredAccess
0x18001cfd2  call    cs:__imp_OpenSemaphoreW
0x18001cfd8  mov     [rsp+270h+var_238], rax
0x18001cfdd  test    rax, rax
0x18001cfe0  jnz     short loc_18001D008
0x18001cfe2  mov     rcx, [rbp+178h]; this
0x18001cfe9  lea     r8, aWil; "wil"
0x18001cff0  mov     edx, 0DCh; void *
0x18001cff5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cffa  mov     ebx, eax
0x18001cffc  lea     rcx, [rsp+270h+var_238]
0x18001d001  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d006  jmp     short loc_18001D058
0x18001d008  lea     rdx, [rsp+270h+var_240]; int *
0x18001d00d  mov     rcx, rax; hHandle
0x18001d010  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001d015  mov     ebx, eax
0x18001d017  test    eax, eax
0x18001d019  jns     short loc_18001D038
0x18001d01b  mov     rcx, [rbp+178h]; this
0x18001d022  lea     r8, aWil; "wil"
0x18001d029  mov     r9d, eax; char *
0x18001d02c  mov     edx, 0DEh; void *
0x18001d031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d036  jmp     short loc_18001CFFC
0x18001d038  lea     rcx, [rsp+270h+var_238]
0x18001d03d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d042  movsxd  rcx, [rsp+270h+var_240]
0x18001d047  movsxd  rax, [rsp+270h+var_23C]
0x18001d04c  shl     rcx, 1Fh
0x18001d050  or      rcx, rax
0x18001d053  mov     [rdi], rcx
0x18001d056  xor     ebx, ebx
0x18001d058  lea     rcx, [rsp+270h+var_230]
0x18001d05d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d062  mov     eax, ebx
0x18001d064  mov     rcx, [rbp+170h+var_10]
0x18001d06b  xor     rcx, rsp; StackCookie
0x18001d06e  call    __security_check_cookie
0x18001d073  lea     r11, [rsp+270h+var_s0]
0x18001d07b  mov     rbx, [r11+18h]
0x18001d07f  mov     rdi, [r11+28h]
0x18001d083  mov     rsp, r11
0x18001d086  pop     rbp
0x18001d087  retn
```

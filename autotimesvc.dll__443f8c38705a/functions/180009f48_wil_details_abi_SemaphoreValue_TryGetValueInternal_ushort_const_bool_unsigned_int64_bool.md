# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009f48`
- end: `0x18000a100`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005cc8`

## callees

- `0x180002a70`
- `0x18000587c`
- `0x1800070c8`
- `0x180009174`
- `0x180009194`
- `0x1800099e4`
- `0x180009b0c`
- `0x180009f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a04a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fbc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22 = v6;
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
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v21,
          v16);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v21,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v22,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180009f48  mov     [rsp-8+arg_8], rbx
0x180009f4d  mov     [rsp-8+arg_18], rdi
0x180009f52  push    rbp
0x180009f53  lea     rbp, [rsp-170h]
0x180009f5b  sub     rsp, 270h
0x180009f62  mov     rax, cs:__security_cookie
0x180009f69  xor     rax, rsp
0x180009f6c  mov     [rbp+170h+var_10], rax
0x180009f73  mov     r9, rcx; pszSrc
0x180009f76  mov     qword ptr [r8], 0
0x180009f7d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180009f82  mov     edx, 104h; cchDest
0x180009f87  mov     rdi, r8
0x180009f8a  call    StringCopyWorkerW
0x180009f8f  lea     r8, aP0; "_p0"
0x180009f96  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180009f9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009fa0  lea     r8, [rsp+270h+pszDest]; lpName
0x180009fa5  xor     edx, edx; bInheritHandle
0x180009fa7  mov     ecx, 1F0003h; dwDesiredAccess
0x180009fac  call    cs:__imp_OpenSemaphoreW
0x180009fb2  mov     [rsp+270h+var_230], rax
0x180009fb7  test    rax, rax
0x180009fba  jnz     short loc_180009FEA
0x180009fbc  call    cs:__imp_GetLastError
0x180009fc2  cmp     eax, 2
0x180009fc5  jz      loc_18000A0CE
0x180009fcb  mov     rcx, [rbp+178h]; this
0x180009fd2  lea     r8, aWil; "wil"
0x180009fd9  mov     edx, 0D0h; void *
0x180009fde  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009fe3  mov     ebx, eax
0x180009fe5  jmp     loc_18000A0D0
0x180009fea  lea     rdx, [rsp+270h+var_23C]; int *
0x180009fef  mov     [rsp+270h+var_23C], 0
0x180009ff7  mov     rcx, rax; hHandle
0x180009ffa  mov     [rsp+270h+var_240], 0
0x18000a002  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a007  mov     ebx, eax
0x18000a009  test    eax, eax
0x18000a00b  jns     short loc_18000A02D
0x18000a00d  mov     rcx, [rbp+178h]; this
0x18000a014  lea     r8, aWil; "wil"
0x18000a01b  mov     r9d, eax; char *
0x18000a01e  mov     edx, 0D6h; void *
0x18000a023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a028  jmp     loc_18000A0D0
0x18000a02d  lea     r8, asc_1800153D8; "h"
0x18000a034  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000a039  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a03e  lea     r8, [rsp+270h+pszDest]; lpName
0x18000a043  xor     edx, edx; bInheritHandle
0x18000a045  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a04a  call    cs:__imp_OpenSemaphoreW
0x18000a050  mov     [rsp+270h+var_238], rax
0x18000a055  test    rax, rax
0x18000a058  jnz     short loc_18000A080
0x18000a05a  mov     rcx, [rbp+178h]; this
0x18000a061  lea     r8, aWil; "wil"
0x18000a068  mov     edx, 0DCh; void *
0x18000a06d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a072  mov     ebx, eax
0x18000a074  lea     rcx, [rsp+270h+var_238]
0x18000a079  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a07e  jmp     short loc_18000A0D0
0x18000a080  lea     rdx, [rsp+270h+var_240]; int *
0x18000a085  mov     rcx, rax; hHandle
0x18000a088  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a08d  mov     ebx, eax
0x18000a08f  test    eax, eax
0x18000a091  jns     short loc_18000A0B0
0x18000a093  mov     rcx, [rbp+178h]; this
0x18000a09a  lea     r8, aWil; "wil"
0x18000a0a1  mov     r9d, eax; char *
0x18000a0a4  mov     edx, 0DEh; void *
0x18000a0a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0ae  jmp     short loc_18000A074
0x18000a0b0  lea     rcx, [rsp+270h+var_238]
0x18000a0b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a0ba  movsxd  rcx, [rsp+270h+var_240]
0x18000a0bf  movsxd  rax, [rsp+270h+var_23C]
0x18000a0c4  shl     rcx, 1Fh
0x18000a0c8  or      rcx, rax
0x18000a0cb  mov     [rdi], rcx
0x18000a0ce  xor     ebx, ebx
0x18000a0d0  lea     rcx, [rsp+270h+var_230]
0x18000a0d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a0da  mov     eax, ebx
0x18000a0dc  mov     rcx, [rbp+170h+var_10]
0x18000a0e3  xor     rcx, rsp; StackCookie
0x18000a0e6  call    __security_check_cookie
0x18000a0eb  lea     r11, [rsp+270h+var_s0]
0x18000a0f3  mov     rbx, [r11+18h]
0x18000a0f7  mov     rdi, [r11+28h]
0x18000a0fb  mov     rsp, r11
0x18000a0fe  pop     rbp
0x18000a0ff  retn
```

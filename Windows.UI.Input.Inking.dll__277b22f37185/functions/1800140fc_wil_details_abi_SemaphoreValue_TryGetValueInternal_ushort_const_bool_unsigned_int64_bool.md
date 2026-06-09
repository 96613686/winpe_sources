# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800140fc`
- end: `0x1800142b4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180014078`

## callees

- `0x1800062a0`
- `0x18000bf50`
- `0x18000fc54`
- `0x18001330c`
- `0x18001332c`
- `0x180013a4c`
- `0x180013b74`
- `0x1800140fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180014160`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800141fe`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180014160`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800141fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014170`

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
0x1800140fc  mov     [rsp-8+arg_8], rbx
0x180014101  mov     [rsp-8+arg_18], rdi
0x180014106  push    rbp
0x180014107  lea     rbp, [rsp-170h]
0x18001410f  sub     rsp, 270h
0x180014116  mov     rax, cs:__security_cookie
0x18001411d  xor     rax, rsp
0x180014120  mov     [rbp+170h+var_10], rax
0x180014127  mov     r9, rcx; pszSrc
0x18001412a  mov     qword ptr [r8], 0
0x180014131  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180014136  mov     edx, 104h; cchDest
0x18001413b  mov     rdi, r8
0x18001413e  call    StringCopyWorkerW
0x180014143  lea     r8, aP0; "_p0"
0x18001414a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001414f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014154  lea     r8, [rsp+270h+pszDest]; lpName
0x180014159  xor     edx, edx; bInheritHandle
0x18001415b  mov     ecx, 1F0003h; dwDesiredAccess
0x180014160  call    cs:__imp_OpenSemaphoreW
0x180014166  mov     [rsp+270h+var_230], rax
0x18001416b  test    rax, rax
0x18001416e  jnz     short loc_18001419E
0x180014170  call    cs:__imp_GetLastError
0x180014176  cmp     eax, 2
0x180014179  jz      loc_180014282
0x18001417f  mov     rcx, [rbp+178h]; this
0x180014186  lea     r8, aWil; "wil"
0x18001418d  mov     edx, 0D0h; void *
0x180014192  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014197  mov     ebx, eax
0x180014199  jmp     loc_180014284
0x18001419e  lea     rdx, [rsp+270h+var_23C]; int *
0x1800141a3  mov     [rsp+270h+var_23C], 0
0x1800141ab  mov     rcx, rax; hHandle
0x1800141ae  mov     [rsp+270h+var_240], 0
0x1800141b6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800141bb  mov     ebx, eax
0x1800141bd  test    eax, eax
0x1800141bf  jns     short loc_1800141E1
0x1800141c1  mov     rcx, [rbp+178h]; this
0x1800141c8  lea     r8, aWil; "wil"
0x1800141cf  mov     r9d, eax; char *
0x1800141d2  mov     edx, 0D6h; void *
0x1800141d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141dc  jmp     loc_180014284
0x1800141e1  lea     r8, asc_180113178; "h"
0x1800141e8  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800141ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800141f2  lea     r8, [rsp+270h+pszDest]; lpName
0x1800141f7  xor     edx, edx; bInheritHandle
0x1800141f9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800141fe  call    cs:__imp_OpenSemaphoreW
0x180014204  mov     [rsp+270h+var_238], rax
0x180014209  test    rax, rax
0x18001420c  jnz     short loc_180014234
0x18001420e  mov     rcx, [rbp+178h]; this
0x180014215  lea     r8, aWil; "wil"
0x18001421c  mov     edx, 0DCh; void *
0x180014221  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014226  mov     ebx, eax
0x180014228  lea     rcx, [rsp+270h+var_238]
0x18001422d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014232  jmp     short loc_180014284
0x180014234  lea     rdx, [rsp+270h+var_240]; int *
0x180014239  mov     rcx, rax; hHandle
0x18001423c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180014241  mov     ebx, eax
0x180014243  test    eax, eax
0x180014245  jns     short loc_180014264
0x180014247  mov     rcx, [rbp+178h]; this
0x18001424e  lea     r8, aWil; "wil"
0x180014255  mov     r9d, eax; char *
0x180014258  mov     edx, 0DEh; void *
0x18001425d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014262  jmp     short loc_180014228
0x180014264  lea     rcx, [rsp+270h+var_238]
0x180014269  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001426e  movsxd  rcx, [rsp+270h+var_240]
0x180014273  movsxd  rax, [rsp+270h+var_23C]
0x180014278  shl     rcx, 1Fh
0x18001427c  or      rcx, rax
0x18001427f  mov     [rdi], rcx
0x180014282  xor     ebx, ebx
0x180014284  lea     rcx, [rsp+270h+var_230]
0x180014289  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001428e  mov     eax, ebx
0x180014290  mov     rcx, [rbp+170h+var_10]
0x180014297  xor     rcx, rsp; StackCookie
0x18001429a  call    __security_check_cookie
0x18001429f  lea     r11, [rsp+270h+var_s0]
0x1800142a7  mov     rbx, [r11+18h]
0x1800142ab  mov     rdi, [r11+28h]
0x1800142af  mov     rsp, r11
0x1800142b2  pop     rbp
0x1800142b3  retn
```

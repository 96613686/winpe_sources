# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180017544`
- end: `0x1800176fc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800174c0`

## callees

- `0x18000bd24`
- `0x18000fea4`
- `0x1800166ac`
- `0x1800166cc`
- `0x180016e54`
- `0x180016eb0`
- `0x180017544`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800175a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017646`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800175a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175b8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180017544  mov     [rsp-8+arg_8], rbx
0x180017549  mov     [rsp-8+arg_18], rdi
0x18001754e  push    rbp
0x18001754f  lea     rbp, [rsp-160h]
0x180017557  sub     rsp, 260h
0x18001755e  mov     rax, cs:__security_cookie
0x180017565  xor     rax, rsp
0x180017568  mov     [rbp+160h+var_10], rax
0x18001756f  mov     rdi, r8
0x180017572  mov     qword ptr [r8], 0
0x180017579  mov     r8, rcx; unsigned __int16 *
0x18001757c  mov     edx, 104h; unsigned __int64
0x180017581  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180017586  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001758b  lea     r8, aP0; "_p0"
0x180017592  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180017597  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001759c  lea     r8, [rsp+260h+Name]; lpName
0x1800175a1  xor     edx, edx; bInheritHandle
0x1800175a3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800175a8  call    cs:__imp_OpenSemaphoreW
0x1800175ae  mov     [rsp+260h+var_230], rax
0x1800175b3  test    rax, rax
0x1800175b6  jnz     short loc_1800175E6
0x1800175b8  call    cs:__imp_GetLastError
0x1800175be  cmp     eax, 2
0x1800175c1  jz      loc_1800176CA
0x1800175c7  mov     rcx, [rbp+168h]; this
0x1800175ce  lea     r8, aWil; "wil"
0x1800175d5  mov     edx, 0D0h; void *
0x1800175da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800175df  mov     ebx, eax
0x1800175e1  jmp     loc_1800176CC
0x1800175e6  lea     rdx, [rsp+260h+var_23C]; int *
0x1800175eb  mov     [rsp+260h+var_23C], 0
0x1800175f3  mov     rcx, rax; hHandle
0x1800175f6  mov     [rsp+260h+var_240], 0; int
0x1800175fe  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017603  mov     ebx, eax
0x180017605  test    eax, eax
0x180017607  jns     short loc_180017629
0x180017609  mov     rcx, [rbp+168h]; this
0x180017610  lea     r8, aWil; "wil"
0x180017617  mov     r9d, eax; char *
0x18001761a  mov     edx, 0D6h; void *
0x18001761f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017624  jmp     loc_1800176CC
0x180017629  lea     r8, asc_180034620; "h"
0x180017630  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180017635  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001763a  lea     r8, [rsp+260h+Name]; lpName
0x18001763f  xor     edx, edx; bInheritHandle
0x180017641  mov     ecx, 1F0003h; dwDesiredAccess
0x180017646  call    cs:__imp_OpenSemaphoreW
0x18001764c  mov     [rsp+260h+var_238], rax
0x180017651  test    rax, rax
0x180017654  jnz     short loc_18001767C
0x180017656  mov     rcx, [rbp+168h]; this
0x18001765d  lea     r8, aWil; "wil"
0x180017664  mov     edx, 0DCh; void *
0x180017669  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001766e  mov     ebx, eax
0x180017670  lea     rcx, [rsp+260h+var_238]
0x180017675  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001767a  jmp     short loc_1800176CC
0x18001767c  lea     rdx, [rsp+260h+var_240]; int *
0x180017681  mov     rcx, rax; hHandle
0x180017684  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017689  mov     ebx, eax
0x18001768b  test    eax, eax
0x18001768d  jns     short loc_1800176AC
0x18001768f  mov     rcx, [rbp+168h]; this
0x180017696  lea     r8, aWil; "wil"
0x18001769d  mov     r9d, eax; char *
0x1800176a0  mov     edx, 0DEh; void *
0x1800176a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800176aa  jmp     short loc_180017670
0x1800176ac  lea     rcx, [rsp+260h+var_238]
0x1800176b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800176b6  movsxd  rcx, [rsp+260h+var_240]
0x1800176bb  movsxd  rax, [rsp+260h+var_23C]
0x1800176c0  shl     rcx, 1Fh
0x1800176c4  or      rcx, rax
0x1800176c7  mov     [rdi], rcx
0x1800176ca  xor     ebx, ebx
0x1800176cc  lea     rcx, [rsp+260h+var_230]
0x1800176d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800176d6  mov     eax, ebx
0x1800176d8  mov     rcx, [rbp+160h+var_10]
0x1800176df  xor     rcx, rsp; StackCookie
0x1800176e2  call    __security_check_cookie
0x1800176e7  lea     r11, [rsp+260h+var_s0]
0x1800176ef  mov     rbx, [r11+18h]
0x1800176f3  mov     rdi, [r11+28h]
0x1800176f7  mov     rsp, r11
0x1800176fa  pop     rbp
0x1800176fb  retn
```

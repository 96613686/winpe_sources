# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007940`
- end: `0x180007af8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800078bc`

## callees

- `0x1800032b0`
- `0x1800056c8`
- `0x180006494`
- `0x180007114`
- `0x180007134`
- `0x180007650`
- `0x1800076cc`
- `0x180007940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800079a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a42`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800079a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b4`

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
0x180007940  mov     [rsp-8+arg_8], rbx
0x180007945  mov     [rsp-8+arg_18], rdi
0x18000794a  push    rbp
0x18000794b  lea     rbp, [rsp-160h]
0x180007953  sub     rsp, 260h
0x18000795a  mov     rax, cs:__security_cookie
0x180007961  xor     rax, rsp
0x180007964  mov     [rbp+160h+var_10], rax
0x18000796b  mov     rdi, r8
0x18000796e  mov     qword ptr [r8], 0
0x180007975  mov     r8, rcx; unsigned __int16 *
0x180007978  mov     edx, 104h; unsigned __int64
0x18000797d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007982  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007987  lea     r8, aP0; "_p0"
0x18000798e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007993  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007998  lea     r8, [rsp+260h+Name]; lpName
0x18000799d  xor     edx, edx; bInheritHandle
0x18000799f  mov     ecx, 1F0003h; dwDesiredAccess
0x1800079a4  call    cs:__imp_OpenSemaphoreW
0x1800079aa  mov     [rsp+260h+var_230], rax
0x1800079af  test    rax, rax
0x1800079b2  jnz     short loc_1800079E2
0x1800079b4  call    cs:__imp_GetLastError
0x1800079ba  cmp     eax, 2
0x1800079bd  jz      loc_180007AC6
0x1800079c3  mov     rcx, [rbp+168h]; this
0x1800079ca  lea     r8, aWil; "wil"
0x1800079d1  mov     edx, 0D0h; void *
0x1800079d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800079db  mov     ebx, eax
0x1800079dd  jmp     loc_180007AC8
0x1800079e2  lea     rdx, [rsp+260h+var_23C]; int *
0x1800079e7  mov     [rsp+260h+var_23C], 0
0x1800079ef  mov     rcx, rax; hHandle
0x1800079f2  mov     [rsp+260h+var_240], 0; int
0x1800079fa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800079ff  mov     ebx, eax
0x180007a01  test    eax, eax
0x180007a03  jns     short loc_180007A25
0x180007a05  mov     rcx, [rbp+168h]; this
0x180007a0c  lea     r8, aWil; "wil"
0x180007a13  mov     r9d, eax; char *
0x180007a16  mov     edx, 0D6h; void *
0x180007a1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a20  jmp     loc_180007AC8
0x180007a25  lea     r8, asc_1800546A8; "h"
0x180007a2c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007a31  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007a36  lea     r8, [rsp+260h+Name]; lpName
0x180007a3b  xor     edx, edx; bInheritHandle
0x180007a3d  mov     ecx, 1F0003h; dwDesiredAccess
0x180007a42  call    cs:__imp_OpenSemaphoreW
0x180007a48  mov     [rsp+260h+var_238], rax
0x180007a4d  test    rax, rax
0x180007a50  jnz     short loc_180007A78
0x180007a52  mov     rcx, [rbp+168h]; this
0x180007a59  lea     r8, aWil; "wil"
0x180007a60  mov     edx, 0DCh; void *
0x180007a65  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007a6a  mov     ebx, eax
0x180007a6c  lea     rcx, [rsp+260h+var_238]
0x180007a71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007a76  jmp     short loc_180007AC8
0x180007a78  lea     rdx, [rsp+260h+var_240]; int *
0x180007a7d  mov     rcx, rax; hHandle
0x180007a80  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007a85  mov     ebx, eax
0x180007a87  test    eax, eax
0x180007a89  jns     short loc_180007AA8
0x180007a8b  mov     rcx, [rbp+168h]; this
0x180007a92  lea     r8, aWil; "wil"
0x180007a99  mov     r9d, eax; char *
0x180007a9c  mov     edx, 0DEh; void *
0x180007aa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007aa6  jmp     short loc_180007A6C
0x180007aa8  lea     rcx, [rsp+260h+var_238]
0x180007aad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007ab2  movsxd  rcx, [rsp+260h+var_240]
0x180007ab7  movsxd  rax, [rsp+260h+var_23C]
0x180007abc  shl     rcx, 1Fh
0x180007ac0  or      rcx, rax
0x180007ac3  mov     [rdi], rcx
0x180007ac6  xor     ebx, ebx
0x180007ac8  lea     rcx, [rsp+260h+var_230]
0x180007acd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007ad2  mov     eax, ebx
0x180007ad4  mov     rcx, [rbp+160h+var_10]
0x180007adb  xor     rcx, rsp; StackCookie
0x180007ade  call    __security_check_cookie
0x180007ae3  lea     r11, [rsp+260h+var_s0]
0x180007aeb  mov     rbx, [r11+18h]
0x180007aef  mov     rdi, [r11+28h]
0x180007af3  mov     rsp, r11
0x180007af6  pop     rbp
0x180007af7  retn
```

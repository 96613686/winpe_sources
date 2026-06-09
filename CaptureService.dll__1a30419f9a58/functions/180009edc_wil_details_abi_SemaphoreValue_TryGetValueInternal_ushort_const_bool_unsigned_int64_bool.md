# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009edc`
- end: `0x18000a094`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009e58`

## callees

- `0x180002e60`
- `0x18000560c`
- `0x1800072b4`
- `0x18000905c`
- `0x18000907c`
- `0x18000974c`
- `0x1800097c8`
- `0x180009edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fde`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f50`

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
0x180009edc  mov     [rsp-8+arg_8], rbx
0x180009ee1  mov     [rsp-8+arg_18], rdi
0x180009ee6  push    rbp
0x180009ee7  lea     rbp, [rsp-160h]
0x180009eef  sub     rsp, 260h
0x180009ef6  mov     rax, cs:__security_cookie
0x180009efd  xor     rax, rsp
0x180009f00  mov     [rbp+160h+var_10], rax
0x180009f07  mov     rdi, r8
0x180009f0a  mov     qword ptr [r8], 0
0x180009f11  mov     r8, rcx; unsigned __int16 *
0x180009f14  mov     edx, 104h; unsigned __int64
0x180009f19  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009f1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009f23  lea     r8, aP0; "_p0"
0x180009f2a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009f2f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009f34  lea     r8, [rsp+260h+Name]; lpName
0x180009f39  xor     edx, edx; bInheritHandle
0x180009f3b  mov     ecx, 1F0003h; dwDesiredAccess
0x180009f40  call    cs:__imp_OpenSemaphoreW
0x180009f46  mov     [rsp+260h+var_230], rax
0x180009f4b  test    rax, rax
0x180009f4e  jnz     short loc_180009F7E
0x180009f50  call    cs:__imp_GetLastError
0x180009f56  cmp     eax, 2
0x180009f59  jz      loc_18000A062
0x180009f5f  mov     rcx, [rbp+168h]; this
0x180009f66  lea     r8, aWil; "wil"
0x180009f6d  mov     edx, 0D0h; void *
0x180009f72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009f77  mov     ebx, eax
0x180009f79  jmp     loc_18000A064
0x180009f7e  lea     rdx, [rsp+260h+var_23C]; int *
0x180009f83  mov     [rsp+260h+var_23C], 0
0x180009f8b  mov     rcx, rax; hHandle
0x180009f8e  mov     [rsp+260h+var_240], 0; int
0x180009f96  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009f9b  mov     ebx, eax
0x180009f9d  test    eax, eax
0x180009f9f  jns     short loc_180009FC1
0x180009fa1  mov     rcx, [rbp+168h]; this
0x180009fa8  lea     r8, aWil; "wil"
0x180009faf  mov     r9d, eax; char *
0x180009fb2  mov     edx, 0D6h; void *
0x180009fb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fbc  jmp     loc_18000A064
0x180009fc1  lea     r8, asc_180026660; "h"
0x180009fc8  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009fcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009fd2  lea     r8, [rsp+260h+Name]; lpName
0x180009fd7  xor     edx, edx; bInheritHandle
0x180009fd9  mov     ecx, 1F0003h; dwDesiredAccess
0x180009fde  call    cs:__imp_OpenSemaphoreW
0x180009fe4  mov     [rsp+260h+var_238], rax
0x180009fe9  test    rax, rax
0x180009fec  jnz     short loc_18000A014
0x180009fee  mov     rcx, [rbp+168h]; this
0x180009ff5  lea     r8, aWil; "wil"
0x180009ffc  mov     edx, 0DCh; void *
0x18000a001  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a006  mov     ebx, eax
0x18000a008  lea     rcx, [rsp+260h+var_238]
0x18000a00d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a012  jmp     short loc_18000A064
0x18000a014  lea     rdx, [rsp+260h+var_240]; int *
0x18000a019  mov     rcx, rax; hHandle
0x18000a01c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a021  mov     ebx, eax
0x18000a023  test    eax, eax
0x18000a025  jns     short loc_18000A044
0x18000a027  mov     rcx, [rbp+168h]; this
0x18000a02e  lea     r8, aWil; "wil"
0x18000a035  mov     r9d, eax; char *
0x18000a038  mov     edx, 0DEh; void *
0x18000a03d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a042  jmp     short loc_18000A008
0x18000a044  lea     rcx, [rsp+260h+var_238]
0x18000a049  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a04e  movsxd  rcx, [rsp+260h+var_240]
0x18000a053  movsxd  rax, [rsp+260h+var_23C]
0x18000a058  shl     rcx, 1Fh
0x18000a05c  or      rcx, rax
0x18000a05f  mov     [rdi], rcx
0x18000a062  xor     ebx, ebx
0x18000a064  lea     rcx, [rsp+260h+var_230]
0x18000a069  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a06e  mov     eax, ebx
0x18000a070  mov     rcx, [rbp+160h+var_10]
0x18000a077  xor     rcx, rsp; StackCookie
0x18000a07a  call    __security_check_cookie
0x18000a07f  lea     r11, [rsp+260h+var_s0]
0x18000a087  mov     rbx, [r11+18h]
0x18000a08b  mov     rdi, [r11+28h]
0x18000a08f  mov     rsp, r11
0x18000a092  pop     rbp
0x18000a093  retn
```

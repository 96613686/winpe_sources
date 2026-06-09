# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180012cf0`
- end: `0x180012ea8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180012c6c`

## callees

- `0x18000a6e0`
- `0x18000eb00`
- `0x180010240`
- `0x18001206c`
- `0x18001208c`
- `0x180012758`
- `0x1800127d4`
- `0x180012cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012d54`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012df2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012d54`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d64`

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
0x180012cf0  mov     [rsp-8+arg_8], rbx
0x180012cf5  mov     [rsp-8+arg_18], rdi
0x180012cfa  push    rbp
0x180012cfb  lea     rbp, [rsp-160h]
0x180012d03  sub     rsp, 260h
0x180012d0a  mov     rax, cs:__security_cookie
0x180012d11  xor     rax, rsp
0x180012d14  mov     [rbp+160h+var_10], rax
0x180012d1b  mov     rdi, r8
0x180012d1e  mov     qword ptr [r8], 0
0x180012d25  mov     r8, rcx; unsigned __int16 *
0x180012d28  mov     edx, 104h; unsigned __int64
0x180012d2d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180012d32  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012d37  lea     r8, aP0; "_p0"
0x180012d3e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180012d43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012d48  lea     r8, [rsp+260h+Name]; lpName
0x180012d4d  xor     edx, edx; bInheritHandle
0x180012d4f  mov     ecx, 1F0003h; dwDesiredAccess
0x180012d54  call    cs:__imp_OpenSemaphoreW
0x180012d5a  mov     [rsp+260h+var_230], rax
0x180012d5f  test    rax, rax
0x180012d62  jnz     short loc_180012D92
0x180012d64  call    cs:__imp_GetLastError
0x180012d6a  cmp     eax, 2
0x180012d6d  jz      loc_180012E76
0x180012d73  mov     rcx, [rbp+168h]; this
0x180012d7a  lea     r8, aWil; "wil"
0x180012d81  mov     edx, 0D0h; void *
0x180012d86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012d8b  mov     ebx, eax
0x180012d8d  jmp     loc_180012E78
0x180012d92  lea     rdx, [rsp+260h+var_23C]; int *
0x180012d97  mov     [rsp+260h+var_23C], 0
0x180012d9f  mov     rcx, rax; hHandle
0x180012da2  mov     [rsp+260h+var_240], 0; int
0x180012daa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012daf  mov     ebx, eax
0x180012db1  test    eax, eax
0x180012db3  jns     short loc_180012DD5
0x180012db5  mov     rcx, [rbp+168h]; this
0x180012dbc  lea     r8, aWil; "wil"
0x180012dc3  mov     r9d, eax; char *
0x180012dc6  mov     edx, 0D6h; void *
0x180012dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012dd0  jmp     loc_180012E78
0x180012dd5  lea     r8, asc_180061538; "h"
0x180012ddc  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180012de1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012de6  lea     r8, [rsp+260h+Name]; lpName
0x180012deb  xor     edx, edx; bInheritHandle
0x180012ded  mov     ecx, 1F0003h; dwDesiredAccess
0x180012df2  call    cs:__imp_OpenSemaphoreW
0x180012df8  mov     [rsp+260h+var_238], rax
0x180012dfd  test    rax, rax
0x180012e00  jnz     short loc_180012E28
0x180012e02  mov     rcx, [rbp+168h]; this
0x180012e09  lea     r8, aWil; "wil"
0x180012e10  mov     edx, 0DCh; void *
0x180012e15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012e1a  mov     ebx, eax
0x180012e1c  lea     rcx, [rsp+260h+var_238]
0x180012e21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012e26  jmp     short loc_180012E78
0x180012e28  lea     rdx, [rsp+260h+var_240]; int *
0x180012e2d  mov     rcx, rax; hHandle
0x180012e30  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012e35  mov     ebx, eax
0x180012e37  test    eax, eax
0x180012e39  jns     short loc_180012E58
0x180012e3b  mov     rcx, [rbp+168h]; this
0x180012e42  lea     r8, aWil; "wil"
0x180012e49  mov     r9d, eax; char *
0x180012e4c  mov     edx, 0DEh; void *
0x180012e51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e56  jmp     short loc_180012E1C
0x180012e58  lea     rcx, [rsp+260h+var_238]
0x180012e5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012e62  movsxd  rcx, [rsp+260h+var_240]
0x180012e67  movsxd  rax, [rsp+260h+var_23C]
0x180012e6c  shl     rcx, 1Fh
0x180012e70  or      rcx, rax
0x180012e73  mov     [rdi], rcx
0x180012e76  xor     ebx, ebx
0x180012e78  lea     rcx, [rsp+260h+var_230]
0x180012e7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012e82  mov     eax, ebx
0x180012e84  mov     rcx, [rbp+160h+var_10]
0x180012e8b  xor     rcx, rsp; StackCookie
0x180012e8e  call    __security_check_cookie
0x180012e93  lea     r11, [rsp+260h+var_s0]
0x180012e9b  mov     rbx, [r11+18h]
0x180012e9f  mov     rdi, [r11+28h]
0x180012ea3  mov     rsp, r11
0x180012ea6  pop     rbp
0x180012ea7  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140016ea0`
- end: `0x140017058`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140016dbc`

## callees

- `0x140003620`
- `0x1400091f0`
- `0x14000e0b8`
- `0x1400136dc`
- `0x1400136fc`
- `0x14001620c`
- `0x140016378`
- `0x140016ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140016f14`
- `KERNEL32!GetLastError` at `0x140016f14`
- `KERNEL32!OpenSemaphoreW` at `0x140016f04`
- `KERNEL32!OpenSemaphoreW` at `0x140016fa2`
- `KERNEL32!OpenSemaphoreW` at `0x140016f04`
- `KERNEL32!OpenSemaphoreW` at `0x140016fa2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140016ea0  mov     [rsp-8+arg_8], rbx
0x140016ea5  mov     [rsp-8+arg_18], rdi
0x140016eaa  push    rbp
0x140016eab  lea     rbp, [rsp-160h]
0x140016eb3  sub     rsp, 260h
0x140016eba  mov     rax, cs:__security_cookie
0x140016ec1  xor     rax, rsp
0x140016ec4  mov     [rbp+160h+var_10], rax
0x140016ecb  mov     rdi, r8
0x140016ece  mov     qword ptr [r8], 0
0x140016ed5  mov     r8, rcx; unsigned __int16 *
0x140016ed8  mov     edx, 104h; unsigned __int64
0x140016edd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140016ee2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140016ee7  lea     r8, aP0; "_p0"
0x140016eee  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140016ef3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140016ef8  lea     r8, [rsp+260h+Name]; lpName
0x140016efd  xor     edx, edx; bInheritHandle
0x140016eff  mov     ecx, 1F0003h; dwDesiredAccess
0x140016f04  call    cs:__imp_OpenSemaphoreW
0x140016f0a  mov     [rsp+260h+var_230], rax
0x140016f0f  test    rax, rax
0x140016f12  jnz     short loc_140016F42
0x140016f14  call    cs:__imp_GetLastError
0x140016f1a  cmp     eax, 2
0x140016f1d  jz      loc_140017026
0x140016f23  mov     rcx, [rbp+168h]; this
0x140016f2a  lea     r8, aWil; "wil"
0x140016f31  mov     edx, 0D0h; void *
0x140016f36  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140016f3b  mov     ebx, eax
0x140016f3d  jmp     loc_140017028
0x140016f42  lea     rdx, [rsp+260h+var_23C]; int *
0x140016f47  mov     [rsp+260h+var_23C], 0
0x140016f4f  mov     rcx, rax; hHandle
0x140016f52  mov     [rsp+260h+var_240], 0; int
0x140016f5a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140016f5f  mov     ebx, eax
0x140016f61  test    eax, eax
0x140016f63  jns     short loc_140016F85
0x140016f65  mov     rcx, [rbp+168h]; this
0x140016f6c  lea     r8, aWil; "wil"
0x140016f73  mov     r9d, eax; char *
0x140016f76  mov     edx, 0D6h; void *
0x140016f7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016f80  jmp     loc_140017028
0x140016f85  lea     r8, asc_140023270; "h"
0x140016f8c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140016f91  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140016f96  lea     r8, [rsp+260h+Name]; lpName
0x140016f9b  xor     edx, edx; bInheritHandle
0x140016f9d  mov     ecx, 1F0003h; dwDesiredAccess
0x140016fa2  call    cs:__imp_OpenSemaphoreW
0x140016fa8  mov     [rsp+260h+var_238], rax
0x140016fad  test    rax, rax
0x140016fb0  jnz     short loc_140016FD8
0x140016fb2  mov     rcx, [rbp+168h]; this
0x140016fb9  lea     r8, aWil; "wil"
0x140016fc0  mov     edx, 0DCh; void *
0x140016fc5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140016fca  mov     ebx, eax
0x140016fcc  lea     rcx, [rsp+260h+var_238]
0x140016fd1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140016fd6  jmp     short loc_140017028
0x140016fd8  lea     rdx, [rsp+260h+var_240]; int *
0x140016fdd  mov     rcx, rax; hHandle
0x140016fe0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140016fe5  mov     ebx, eax
0x140016fe7  test    eax, eax
0x140016fe9  jns     short loc_140017008
0x140016feb  mov     rcx, [rbp+168h]; this
0x140016ff2  lea     r8, aWil; "wil"
0x140016ff9  mov     r9d, eax; char *
0x140016ffc  mov     edx, 0DEh; void *
0x140017001  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017006  jmp     short loc_140016FCC
0x140017008  lea     rcx, [rsp+260h+var_238]
0x14001700d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140017012  movsxd  rcx, [rsp+260h+var_240]
0x140017017  movsxd  rax, [rsp+260h+var_23C]
0x14001701c  shl     rcx, 1Fh
0x140017020  or      rcx, rax
0x140017023  mov     [rdi], rcx
0x140017026  xor     ebx, ebx
0x140017028  lea     rcx, [rsp+260h+var_230]
0x14001702d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140017032  mov     eax, ebx
0x140017034  mov     rcx, [rbp+160h+var_10]
0x14001703b  xor     rcx, rsp; StackCookie
0x14001703e  call    __security_check_cookie
0x140017043  lea     r11, [rsp+260h+var_s0]
0x14001704b  mov     rbx, [r11+18h]
0x14001704f  mov     rdi, [r11+28h]
0x140017053  mov     rsp, r11
0x140017056  pop     rbp
0x140017057  retn
```

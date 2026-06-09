# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180143fc4`
- end: `0x180144173`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180143f40`

## callees

- `0x18013bad0`
- `0x1801405c0`
- `0x180141aac`
- `0x18014355c`
- `0x18014357c`
- `0x1801439e8`
- `0x180143a3c`
- `0x180143fc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180144028`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1801440c4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180144028`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1801440c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144038`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180143fc4  mov     [rsp-8+arg_8], rbx
0x180143fc9  mov     [rsp-8+arg_18], rdi
0x180143fce  push    rbp
0x180143fcf  lea     rbp, [rsp-160h]
0x180143fd7  sub     rsp, 260h
0x180143fde  mov     rax, cs:__security_cookie
0x180143fe5  xor     rax, rsp
0x180143fe8  mov     [rbp+160h+var_10], rax
0x180143fef  mov     rdi, r8
0x180143ff2  mov     qword ptr [r8], 0
0x180143ff9  mov     r8, rcx; unsigned __int16 *
0x180143ffc  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180144001  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180144006  lea     r8, aP0; "_p0"
0x18014400d  mov     edx, 104h; unsigned __int64
0x180144012  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180144017  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18014401c  lea     r8, [rsp+260h+Name]; lpName
0x180144021  xor     edx, edx; bInheritHandle
0x180144023  mov     ecx, 1F0003h; dwDesiredAccess
0x180144028  call    cs:__imp_OpenSemaphoreW
0x18014402e  mov     [rsp+260h+var_230], rax
0x180144033  test    rax, rax
0x180144036  jnz     short loc_18014405F
0x180144038  call    cs:__imp_GetLastError
0x18014403e  cmp     eax, 2
0x180144041  jz      loc_180144141
0x180144047  mov     rcx, [rbp+168h]; this
0x18014404e  mov     edx, 0D0h; void *
0x180144053  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180144058  mov     ebx, eax
0x18014405a  jmp     loc_180144143
0x18014405f  lea     rdx, [rsp+260h+var_23C]; int *
0x180144064  mov     [rsp+260h+var_23C], 0
0x18014406c  mov     rcx, rax; hHandle
0x18014406f  mov     [rsp+260h+var_240], 0; int
0x180144077  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18014407c  mov     ebx, eax
0x18014407e  test    eax, eax
0x180144080  jns     short loc_1801440A2
0x180144082  mov     rcx, [rbp+168h]; this
0x180144089  lea     r8, aWil; "wil"
0x180144090  mov     r9d, eax; char *
0x180144093  mov     edx, 0D6h; void *
0x180144098  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014409d  jmp     loc_180144143
0x1801440a2  lea     r8, asc_1802A8CF0; "h"
0x1801440a9  mov     edx, 104h; unsigned __int64
0x1801440ae  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1801440b3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801440b8  lea     r8, [rsp+260h+Name]; lpName
0x1801440bd  xor     edx, edx; bInheritHandle
0x1801440bf  mov     ecx, 1F0003h; dwDesiredAccess
0x1801440c4  call    cs:__imp_OpenSemaphoreW
0x1801440ca  mov     [rsp+260h+var_238], rax
0x1801440cf  test    rax, rax
0x1801440d2  jnz     short loc_1801440F3
0x1801440d4  mov     rcx, [rbp+168h]; this
0x1801440db  mov     edx, 0DCh; void *
0x1801440e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801440e5  mov     ebx, eax
0x1801440e7  lea     rcx, [rsp+260h+var_238]
0x1801440ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801440f1  jmp     short loc_180144143
0x1801440f3  lea     rdx, [rsp+260h+var_240]; int *
0x1801440f8  mov     rcx, rax; hHandle
0x1801440fb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180144100  mov     ebx, eax
0x180144102  test    eax, eax
0x180144104  jns     short loc_180144123
0x180144106  mov     rcx, [rbp+168h]; this
0x18014410d  lea     r8, aWil; "wil"
0x180144114  mov     r9d, eax; char *
0x180144117  mov     edx, 0DEh; void *
0x18014411c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144121  jmp     short loc_1801440E7
0x180144123  lea     rcx, [rsp+260h+var_238]
0x180144128  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014412d  movsxd  rcx, [rsp+260h+var_240]
0x180144132  movsxd  rax, [rsp+260h+var_23C]
0x180144137  shl     rcx, 1Fh
0x18014413b  or      rcx, rax
0x18014413e  mov     [rdi], rcx
0x180144141  xor     ebx, ebx
0x180144143  lea     rcx, [rsp+260h+var_230]
0x180144148  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014414d  mov     eax, ebx
0x18014414f  mov     rcx, [rbp+160h+var_10]
0x180144156  xor     rcx, rsp; StackCookie
0x180144159  call    __security_check_cookie
0x18014415e  lea     r11, [rsp+260h+var_s0]
0x180144166  mov     rbx, [r11+18h]
0x18014416a  mov     rdi, [r11+28h]
0x18014416e  mov     rsp, r11
0x180144171  pop     rbp
0x180144172  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009fc0`
- end: `0x18000a178`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009f3c`

## callees

- `0x180003ed0`
- `0x180007c70`
- `0x180008b14`
- `0x180009794`
- `0x1800097b4`
- `0x180009cd0`
- `0x180009d4c`
- `0x180009fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a024`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0c2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a024`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a034`

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
0x180009fc0  mov     [rsp-8+arg_8], rbx
0x180009fc5  mov     [rsp-8+arg_18], rdi
0x180009fca  push    rbp
0x180009fcb  lea     rbp, [rsp-160h]
0x180009fd3  sub     rsp, 260h
0x180009fda  mov     rax, cs:__security_cookie
0x180009fe1  xor     rax, rsp
0x180009fe4  mov     [rbp+160h+var_10], rax
0x180009feb  mov     rdi, r8
0x180009fee  mov     qword ptr [r8], 0
0x180009ff5  mov     r8, rcx; unsigned __int16 *
0x180009ff8  mov     edx, 104h; unsigned __int64
0x180009ffd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a002  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a007  lea     r8, aP0; "_p0"
0x18000a00e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a013  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a018  lea     r8, [rsp+260h+Name]; lpName
0x18000a01d  xor     edx, edx; bInheritHandle
0x18000a01f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a024  call    cs:__imp_OpenSemaphoreW
0x18000a02a  mov     [rsp+260h+var_230], rax
0x18000a02f  test    rax, rax
0x18000a032  jnz     short loc_18000A062
0x18000a034  call    cs:__imp_GetLastError
0x18000a03a  cmp     eax, 2
0x18000a03d  jz      loc_18000A146
0x18000a043  mov     rcx, [rbp+168h]; this
0x18000a04a  lea     r8, aWil; "wil"
0x18000a051  mov     edx, 0D0h; void *
0x18000a056  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a05b  mov     ebx, eax
0x18000a05d  jmp     loc_18000A148
0x18000a062  lea     rdx, [rsp+260h+var_23C]; int *
0x18000a067  mov     [rsp+260h+var_23C], 0
0x18000a06f  mov     rcx, rax; hHandle
0x18000a072  mov     [rsp+260h+var_240], 0; int
0x18000a07a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a07f  mov     ebx, eax
0x18000a081  test    eax, eax
0x18000a083  jns     short loc_18000A0A5
0x18000a085  mov     rcx, [rbp+168h]; this
0x18000a08c  lea     r8, aWil; "wil"
0x18000a093  mov     r9d, eax; char *
0x18000a096  mov     edx, 0D6h; void *
0x18000a09b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0a0  jmp     loc_18000A148
0x18000a0a5  lea     r8, asc_180098C90; "h"
0x18000a0ac  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a0b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a0b6  lea     r8, [rsp+260h+Name]; lpName
0x18000a0bb  xor     edx, edx; bInheritHandle
0x18000a0bd  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a0c2  call    cs:__imp_OpenSemaphoreW
0x18000a0c8  mov     [rsp+260h+var_238], rax
0x18000a0cd  test    rax, rax
0x18000a0d0  jnz     short loc_18000A0F8
0x18000a0d2  mov     rcx, [rbp+168h]; this
0x18000a0d9  lea     r8, aWil; "wil"
0x18000a0e0  mov     edx, 0DCh; void *
0x18000a0e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a0ea  mov     ebx, eax
0x18000a0ec  lea     rcx, [rsp+260h+var_238]
0x18000a0f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a0f6  jmp     short loc_18000A148
0x18000a0f8  lea     rdx, [rsp+260h+var_240]; int *
0x18000a0fd  mov     rcx, rax; hHandle
0x18000a100  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a105  mov     ebx, eax
0x18000a107  test    eax, eax
0x18000a109  jns     short loc_18000A128
0x18000a10b  mov     rcx, [rbp+168h]; this
0x18000a112  lea     r8, aWil; "wil"
0x18000a119  mov     r9d, eax; char *
0x18000a11c  mov     edx, 0DEh; void *
0x18000a121  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a126  jmp     short loc_18000A0EC
0x18000a128  lea     rcx, [rsp+260h+var_238]
0x18000a12d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a132  movsxd  rcx, [rsp+260h+var_240]
0x18000a137  movsxd  rax, [rsp+260h+var_23C]
0x18000a13c  shl     rcx, 1Fh
0x18000a140  or      rcx, rax
0x18000a143  mov     [rdi], rcx
0x18000a146  xor     ebx, ebx
0x18000a148  lea     rcx, [rsp+260h+var_230]
0x18000a14d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a152  mov     eax, ebx
0x18000a154  mov     rcx, [rbp+160h+var_10]
0x18000a15b  xor     rcx, rsp; StackCookie
0x18000a15e  call    __security_check_cookie
0x18000a163  lea     r11, [rsp+260h+var_s0]
0x18000a16b  mov     rbx, [r11+18h]
0x18000a16f  mov     rdi, [r11+28h]
0x18000a173  mov     rsp, r11
0x18000a176  pop     rbp
0x18000a177  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800098bc`
- end: `0x180009a74`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009838`

## callees

- `0x180004c70`
- `0x1800071a4`
- `0x1800082d8`
- `0x1800090d4`
- `0x1800090f4`
- `0x180009610`
- `0x18000968c`
- `0x1800098bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009920`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099be`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009920`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009930`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
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
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
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
0x1800098bc  mov     [rsp-8+arg_8], rbx
0x1800098c1  mov     [rsp-8+arg_18], rdi
0x1800098c6  push    rbp
0x1800098c7  lea     rbp, [rsp-160h]
0x1800098cf  sub     rsp, 260h
0x1800098d6  mov     rax, cs:__security_cookie
0x1800098dd  xor     rax, rsp
0x1800098e0  mov     [rbp+160h+var_10], rax
0x1800098e7  mov     rdi, r8
0x1800098ea  mov     qword ptr [r8], 0
0x1800098f1  mov     r8, rcx; unsigned __int16 *
0x1800098f4  mov     edx, 104h; unsigned __int64
0x1800098f9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800098fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009903  lea     r8, aP0; "_p0"
0x18000990a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000990f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009914  lea     r8, [rsp+260h+Name]; lpName
0x180009919  xor     edx, edx; bInheritHandle
0x18000991b  mov     ecx, 1F0003h; dwDesiredAccess
0x180009920  call    cs:__imp_OpenSemaphoreW
0x180009926  mov     [rsp+260h+var_230], rax
0x18000992b  test    rax, rax
0x18000992e  jnz     short loc_18000995E
0x180009930  call    cs:__imp_GetLastError
0x180009936  cmp     eax, 2
0x180009939  jz      loc_180009A42
0x18000993f  mov     rcx, [rbp+168h]; this
0x180009946  lea     r8, aWil; "wil"
0x18000994d  mov     edx, 0D0h; void *
0x180009952  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009957  mov     ebx, eax
0x180009959  jmp     loc_180009A44
0x18000995e  lea     rdx, [rsp+260h+var_23C]; int *
0x180009963  mov     [rsp+260h+var_23C], 0
0x18000996b  mov     rcx, rax; hHandle
0x18000996e  mov     [rsp+260h+var_240], 0; int
0x180009976  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000997b  mov     ebx, eax
0x18000997d  test    eax, eax
0x18000997f  jns     short loc_1800099A1
0x180009981  mov     rcx, [rbp+168h]; this
0x180009988  lea     r8, aWil; "wil"
0x18000998f  mov     r9d, eax; char *
0x180009992  mov     edx, 0D6h; void *
0x180009997  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000999c  jmp     loc_180009A44
0x1800099a1  lea     r8, asc_180016BA0; "h"
0x1800099a8  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800099ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800099b2  lea     r8, [rsp+260h+Name]; lpName
0x1800099b7  xor     edx, edx; bInheritHandle
0x1800099b9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800099be  call    cs:__imp_OpenSemaphoreW
0x1800099c4  mov     [rsp+260h+var_238], rax
0x1800099c9  test    rax, rax
0x1800099cc  jnz     short loc_1800099F4
0x1800099ce  mov     rcx, [rbp+168h]; this
0x1800099d5  lea     r8, aWil; "wil"
0x1800099dc  mov     edx, 0DCh; void *
0x1800099e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800099e6  mov     ebx, eax
0x1800099e8  lea     rcx, [rsp+260h+var_238]
0x1800099ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800099f2  jmp     short loc_180009A44
0x1800099f4  lea     rdx, [rsp+260h+var_240]; int *
0x1800099f9  mov     rcx, rax; hHandle
0x1800099fc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009a01  mov     ebx, eax
0x180009a03  test    eax, eax
0x180009a05  jns     short loc_180009A24
0x180009a07  mov     rcx, [rbp+168h]; this
0x180009a0e  lea     r8, aWil; "wil"
0x180009a15  mov     r9d, eax; char *
0x180009a18  mov     edx, 0DEh; void *
0x180009a1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a22  jmp     short loc_1800099E8
0x180009a24  lea     rcx, [rsp+260h+var_238]
0x180009a29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009a2e  movsxd  rcx, [rsp+260h+var_240]
0x180009a33  movsxd  rax, [rsp+260h+var_23C]
0x180009a38  shl     rcx, 1Fh
0x180009a3c  or      rcx, rax
0x180009a3f  mov     [rdi], rcx
0x180009a42  xor     ebx, ebx
0x180009a44  lea     rcx, [rsp+260h+var_230]
0x180009a49  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009a4e  mov     eax, ebx
0x180009a50  mov     rcx, [rbp+160h+var_10]
0x180009a57  xor     rcx, rsp; StackCookie
0x180009a5a  call    __security_check_cookie
0x180009a5f  lea     r11, [rsp+260h+var_s0]
0x180009a67  mov     rbx, [r11+18h]
0x180009a6b  mov     rdi, [r11+28h]
0x180009a6f  mov     rsp, r11
0x180009a72  pop     rbp
0x180009a73  retn
```

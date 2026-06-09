# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007568`
- end: `0x140007704`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400074f4`

## callees

- `0x140003b30`
- `0x140004ff8`
- `0x140006b7c`
- `0x140006b9c`
- `0x140007040`
- `0x1400070bc`
- `0x140007568`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400075cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000765c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400075cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000765c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075dc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x140007568  mov     [rsp-8+arg_8], rbx
0x14000756d  mov     [rsp-8+arg_18], rdi
0x140007572  push    rbp
0x140007573  lea     rbp, [rsp-160h]
0x14000757b  sub     rsp, 260h
0x140007582  mov     rax, cs:__security_cookie
0x140007589  xor     rax, rsp
0x14000758c  mov     [rbp+160h+var_10], rax
0x140007593  mov     rdi, r8
0x140007596  mov     qword ptr [r8], 0
0x14000759d  mov     r8, rcx; unsigned __int16 *
0x1400075a0  mov     edx, 104h; unsigned __int64
0x1400075a5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1400075aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400075af  lea     r8, aP0; "_p0"
0x1400075b6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1400075bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400075c0  lea     r8, [rsp+260h+Name]; lpName
0x1400075c5  xor     edx, edx; bInheritHandle
0x1400075c7  mov     ecx, 1F0003h; dwDesiredAccess
0x1400075cc  call    cs:__imp_OpenSemaphoreW
0x1400075d2  mov     [rsp+260h+var_230], rax
0x1400075d7  test    rax, rax
0x1400075da  jnz     short loc_140007603
0x1400075dc  call    cs:__imp_GetLastError
0x1400075e2  cmp     eax, 2
0x1400075e5  jz      loc_1400076D2
0x1400075eb  mov     rcx, [rbp+168h]; this
0x1400075f2  mov     edx, 0D0h; void *
0x1400075f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400075fc  mov     ebx, eax
0x1400075fe  jmp     loc_1400076D4
0x140007603  lea     rdx, [rsp+260h+var_23C]; int *
0x140007608  mov     [rsp+260h+var_23C], 0
0x140007610  mov     rcx, rax; hHandle
0x140007613  mov     [rsp+260h+var_240], 0; int
0x14000761b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007620  mov     ebx, eax
0x140007622  test    eax, eax
0x140007624  jns     short loc_14000763F
0x140007626  mov     rcx, [rbp+168h]; this
0x14000762d  mov     r9d, eax; char *
0x140007630  mov     edx, 0D6h; void *
0x140007635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000763a  jmp     loc_1400076D4
0x14000763f  lea     r8, asc_14004A0C0; "h"
0x140007646  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14000764b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007650  lea     r8, [rsp+260h+Name]; lpName
0x140007655  xor     edx, edx; bInheritHandle
0x140007657  mov     ecx, 1F0003h; dwDesiredAccess
0x14000765c  call    cs:__imp_OpenSemaphoreW
0x140007662  mov     [rsp+260h+var_238], rax
0x140007667  test    rax, rax
0x14000766a  jnz     short loc_14000768B
0x14000766c  mov     rcx, [rbp+168h]; this
0x140007673  mov     edx, 0DCh; void *
0x140007678  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000767d  mov     ebx, eax
0x14000767f  lea     rcx, [rsp+260h+var_238]
0x140007684  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007689  jmp     short loc_1400076D4
0x14000768b  lea     rdx, [rsp+260h+var_240]; int *
0x140007690  mov     rcx, rax; hHandle
0x140007693  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007698  mov     ebx, eax
0x14000769a  test    eax, eax
0x14000769c  jns     short loc_1400076B4
0x14000769e  mov     rcx, [rbp+168h]; this
0x1400076a5  mov     r9d, eax; char *
0x1400076a8  mov     edx, 0DEh; void *
0x1400076ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400076b2  jmp     short loc_14000767F
0x1400076b4  lea     rcx, [rsp+260h+var_238]
0x1400076b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400076be  movsxd  rcx, [rsp+260h+var_240]
0x1400076c3  movsxd  rax, [rsp+260h+var_23C]
0x1400076c8  shl     rcx, 1Fh
0x1400076cc  or      rcx, rax
0x1400076cf  mov     [rdi], rcx
0x1400076d2  xor     ebx, ebx
0x1400076d4  lea     rcx, [rsp+260h+var_230]
0x1400076d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400076de  mov     eax, ebx
0x1400076e0  mov     rcx, [rbp+160h+var_10]
0x1400076e7  xor     rcx, rsp; StackCookie
0x1400076ea  call    __security_check_cookie
0x1400076ef  lea     r11, [rsp+260h+var_s0]
0x1400076f7  mov     rbx, [r11+18h]
0x1400076fb  mov     rdi, [r11+28h]
0x1400076ff  mov     rsp, r11
0x140007702  pop     rbp
0x140007703  retn
```

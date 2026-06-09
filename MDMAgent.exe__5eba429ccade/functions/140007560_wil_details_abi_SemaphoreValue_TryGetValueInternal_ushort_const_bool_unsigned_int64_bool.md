# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007560`
- end: `0x14000771e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400074dc`

## callees

- `0x140002930`
- `0x140004b2c`
- `0x140005b78`
- `0x140006964`
- `0x140006984`
- `0x140007230`
- `0x140007324`
- `0x140007560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400075c9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007669`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400075c9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075d9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v10; // rax
  const char *v11; // r9
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v18; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v19; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 260, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v5;
  if ( v5 )
  {
    v17 = 0;
    v16 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v17);
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
    StringCchCatW(Name, 260, L"h");
    v10 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v18 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v16);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v18,
          v14);
        *a3 = v17 | (unsigned __int64)((__int64)v16 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v11);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v18,
      v12);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v19,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x140007560  mov     [rsp-8+arg_8], rbx
0x140007565  push    rbp
0x140007566  push    rdi
0x140007567  push    r14
0x140007569  lea     rbp, [rsp-160h]
0x140007571  sub     rsp, 260h
0x140007578  mov     rax, cs:__security_cookie
0x14000757f  xor     rax, rsp
0x140007582  mov     [rbp+170h+var_20], rax
0x140007589  mov     rdi, r8
0x14000758c  mov     qword ptr [r8], 0
0x140007593  mov     r8, rcx; unsigned __int16 *
0x140007596  mov     r14d, 104h
0x14000759c  mov     edx, r14d; unsigned __int64
0x14000759f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400075a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400075a9  lea     r8, aP0; "_p0"
0x1400075b0  mov     edx, r14d; unsigned __int64
0x1400075b3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400075b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400075bd  lea     r8, [rsp+270h+Name]; lpName
0x1400075c2  xor     edx, edx; bInheritHandle
0x1400075c4  mov     ecx, 1F0003h; dwDesiredAccess
0x1400075c9  call    cs:__imp_OpenSemaphoreW
0x1400075cf  mov     [rsp+270h+var_240], rax
0x1400075d4  test    rax, rax
0x1400075d7  jnz     short loc_140007606
0x1400075d9  call    cs:__imp_GetLastError
0x1400075df  cmp     eax, 2
0x1400075e2  jz      loc_1400076ED
0x1400075e8  mov     rcx, [rbp+178h]; this
0x1400075ef  lea     r8, aWil; "wil"
0x1400075f6  lea     edx, [r14-34h]; void *
0x1400075fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400075ff  mov     ebx, eax
0x140007601  jmp     loc_1400076EF
0x140007606  lea     rdx, [rsp+270h+var_24C]; int *
0x14000760b  mov     [rsp+270h+var_24C], 0
0x140007613  mov     rcx, rax; hHandle
0x140007616  mov     [rsp+270h+var_250], 0; int
0x14000761e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007623  mov     ebx, eax
0x140007625  test    eax, eax
0x140007627  jns     short loc_140007649
0x140007629  mov     rcx, [rbp+178h]; this
0x140007630  lea     r8, aWil; "wil"
0x140007637  mov     r9d, eax; char *
0x14000763a  mov     edx, 0D6h; void *
0x14000763f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007644  jmp     loc_1400076EF
0x140007649  lea     r8, asc_14001B068; "h"
0x140007650  mov     rdx, r14; unsigned __int64
0x140007653  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007658  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000765d  lea     r8, [rsp+270h+Name]; lpName
0x140007662  xor     edx, edx; bInheritHandle
0x140007664  mov     ecx, 1F0003h; dwDesiredAccess
0x140007669  call    cs:__imp_OpenSemaphoreW
0x14000766f  mov     [rsp+270h+var_248], rax
0x140007674  test    rax, rax
0x140007677  jnz     short loc_14000769F
0x140007679  mov     rcx, [rbp+178h]; this
0x140007680  lea     r8, aWil; "wil"
0x140007687  mov     edx, 0DCh; void *
0x14000768c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007691  mov     ebx, eax
0x140007693  lea     rcx, [rsp+270h+var_248]
0x140007698  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000769d  jmp     short loc_1400076EF
0x14000769f  lea     rdx, [rsp+270h+var_250]; int *
0x1400076a4  mov     rcx, rax; hHandle
0x1400076a7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400076ac  mov     ebx, eax
0x1400076ae  test    eax, eax
0x1400076b0  jns     short loc_1400076CF
0x1400076b2  mov     rcx, [rbp+178h]; this
0x1400076b9  lea     r8, aWil; "wil"
0x1400076c0  mov     r9d, eax; char *
0x1400076c3  mov     edx, 0DEh; void *
0x1400076c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400076cd  jmp     short loc_140007693
0x1400076cf  lea     rcx, [rsp+270h+var_248]
0x1400076d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400076d9  movsxd  rcx, [rsp+270h+var_250]
0x1400076de  movsxd  rax, [rsp+270h+var_24C]
0x1400076e3  shl     rcx, 1Fh
0x1400076e7  or      rcx, rax
0x1400076ea  mov     [rdi], rcx
0x1400076ed  xor     ebx, ebx
0x1400076ef  lea     rcx, [rsp+270h+var_240]
0x1400076f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400076f9  mov     eax, ebx
0x1400076fb  mov     rcx, [rbp+170h+var_20]
0x140007702  xor     rcx, rsp; StackCookie
0x140007705  call    __security_check_cookie
0x14000770a  mov     rbx, [rsp+270h+arg_8]
0x140007712  add     rsp, 260h
0x140007719  pop     r14
0x14000771b  pop     rdi
0x14000771c  pop     rbp
0x14000771d  retn
```

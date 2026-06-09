# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800102ec`
- end: `0x180010488`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180010278`

## callees

- `0x180001720`
- `0x180005a28`
- `0x180005b30`
- `0x1800087c4`
- `0x18000bab0`
- `0x18000f0ac`
- `0x18000f0cc`
- `0x1800102ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010360`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010350`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800103e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010350`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800103e0`

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
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x1800102ec  mov     [rsp-8+arg_8], rbx
0x1800102f1  mov     [rsp-8+arg_18], rdi
0x1800102f6  push    rbp
0x1800102f7  lea     rbp, [rsp-160h]
0x1800102ff  sub     rsp, 260h
0x180010306  mov     rax, cs:__security_cookie
0x18001030d  xor     rax, rsp
0x180010310  mov     [rbp+160h+var_10], rax
0x180010317  mov     rdi, r8
0x18001031a  mov     qword ptr [r8], 0
0x180010321  mov     r8, rcx; unsigned __int16 *
0x180010324  mov     edx, 104h; unsigned __int64
0x180010329  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001032e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010333  lea     r8, aP0; "_p0"
0x18001033a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001033f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010344  lea     r8, [rsp+260h+Name]; lpName
0x180010349  xor     edx, edx; bInheritHandle
0x18001034b  mov     ecx, 1F0003h; dwDesiredAccess
0x180010350  call    cs:__imp_OpenSemaphoreW
0x180010356  mov     [rsp+260h+var_230], rax
0x18001035b  test    rax, rax
0x18001035e  jnz     short loc_180010387
0x180010360  call    cs:__imp_GetLastError
0x180010366  cmp     eax, 2
0x180010369  jz      loc_180010456
0x18001036f  mov     rcx, [rbp+168h]; this
0x180010376  mov     edx, 0D0h; void *
0x18001037b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010380  mov     ebx, eax
0x180010382  jmp     loc_180010458
0x180010387  lea     rdx, [rsp+260h+var_23C]; int *
0x18001038c  mov     [rsp+260h+var_23C], 0
0x180010394  mov     rcx, rax; hHandle
0x180010397  mov     [rsp+260h+var_240], 0; int
0x18001039f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800103a4  mov     ebx, eax
0x1800103a6  test    eax, eax
0x1800103a8  jns     short loc_1800103C3
0x1800103aa  mov     rcx, [rbp+168h]; this
0x1800103b1  mov     r9d, eax; char *
0x1800103b4  mov     edx, 0D6h; void *
0x1800103b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103be  jmp     loc_180010458
0x1800103c3  lea     r8, asc_180018DC8; "h"
0x1800103ca  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800103cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800103d4  lea     r8, [rsp+260h+Name]; lpName
0x1800103d9  xor     edx, edx; bInheritHandle
0x1800103db  mov     ecx, 1F0003h; dwDesiredAccess
0x1800103e0  call    cs:__imp_OpenSemaphoreW
0x1800103e6  mov     [rsp+260h+var_238], rax
0x1800103eb  test    rax, rax
0x1800103ee  jnz     short loc_18001040F
0x1800103f0  mov     rcx, [rbp+168h]; this
0x1800103f7  mov     edx, 0DCh; void *
0x1800103fc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010401  mov     ebx, eax
0x180010403  lea     rcx, [rsp+260h+var_238]
0x180010408  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001040d  jmp     short loc_180010458
0x18001040f  lea     rdx, [rsp+260h+var_240]; int *
0x180010414  mov     rcx, rax; hHandle
0x180010417  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001041c  mov     ebx, eax
0x18001041e  test    eax, eax
0x180010420  jns     short loc_180010438
0x180010422  mov     rcx, [rbp+168h]; this
0x180010429  mov     r9d, eax; char *
0x18001042c  mov     edx, 0DEh; void *
0x180010431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010436  jmp     short loc_180010403
0x180010438  lea     rcx, [rsp+260h+var_238]
0x18001043d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010442  movsxd  rcx, [rsp+260h+var_240]
0x180010447  movsxd  rax, [rsp+260h+var_23C]
0x18001044c  shl     rcx, 1Fh
0x180010450  or      rcx, rax
0x180010453  mov     [rdi], rcx
0x180010456  xor     ebx, ebx
0x180010458  lea     rcx, [rsp+260h+var_230]
0x18001045d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010462  mov     eax, ebx
0x180010464  mov     rcx, [rbp+160h+var_10]
0x18001046b  xor     rcx, rsp; StackCookie
0x18001046e  call    __security_check_cookie
0x180010473  lea     r11, [rsp+260h+var_s0]
0x18001047b  mov     rbx, [r11+18h]
0x18001047f  mov     rdi, [r11+28h]
0x180010483  mov     rsp, r11
0x180010486  pop     rbp
0x180010487  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800081ac`
- end: `0x180008364`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008128`

## callees

- `0x180001dd0`
- `0x1800040d8`
- `0x1800056f8`
- `0x1800074fc`
- `0x18000751c`
- `0x180007be8`
- `0x180007c64`
- `0x1800081ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008210`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082ae`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008210`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008220`

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
0x1800081ac  mov     [rsp-8+arg_8], rbx
0x1800081b1  mov     [rsp-8+arg_18], rdi
0x1800081b6  push    rbp
0x1800081b7  lea     rbp, [rsp-160h]
0x1800081bf  sub     rsp, 260h
0x1800081c6  mov     rax, cs:__security_cookie
0x1800081cd  xor     rax, rsp
0x1800081d0  mov     [rbp+160h+var_10], rax
0x1800081d7  mov     rdi, r8
0x1800081da  mov     qword ptr [r8], 0
0x1800081e1  mov     r8, rcx; unsigned __int16 *
0x1800081e4  mov     edx, 104h; unsigned __int64
0x1800081e9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800081ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800081f3  lea     r8, aP0; "_p0"
0x1800081fa  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800081ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008204  lea     r8, [rsp+260h+Name]; lpName
0x180008209  xor     edx, edx; bInheritHandle
0x18000820b  mov     ecx, 1F0003h; dwDesiredAccess
0x180008210  call    cs:__imp_OpenSemaphoreW
0x180008216  mov     [rsp+260h+var_230], rax
0x18000821b  test    rax, rax
0x18000821e  jnz     short loc_18000824E
0x180008220  call    cs:__imp_GetLastError
0x180008226  cmp     eax, 2
0x180008229  jz      loc_180008332
0x18000822f  mov     rcx, [rbp+168h]; this
0x180008236  lea     r8, aWil; "wil"
0x18000823d  mov     edx, 0D0h; void *
0x180008242  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008247  mov     ebx, eax
0x180008249  jmp     loc_180008334
0x18000824e  lea     rdx, [rsp+260h+var_23C]; int *
0x180008253  mov     [rsp+260h+var_23C], 0
0x18000825b  mov     rcx, rax; hHandle
0x18000825e  mov     [rsp+260h+var_240], 0; int
0x180008266  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000826b  mov     ebx, eax
0x18000826d  test    eax, eax
0x18000826f  jns     short loc_180008291
0x180008271  mov     rcx, [rbp+168h]; this
0x180008278  lea     r8, aWil; "wil"
0x18000827f  mov     r9d, eax; char *
0x180008282  mov     edx, 0D6h; void *
0x180008287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000828c  jmp     loc_180008334
0x180008291  lea     r8, asc_180065BE8; "h"
0x180008298  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000829d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082a2  lea     r8, [rsp+260h+Name]; lpName
0x1800082a7  xor     edx, edx; bInheritHandle
0x1800082a9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800082ae  call    cs:__imp_OpenSemaphoreW
0x1800082b4  mov     [rsp+260h+var_238], rax
0x1800082b9  test    rax, rax
0x1800082bc  jnz     short loc_1800082E4
0x1800082be  mov     rcx, [rbp+168h]; this
0x1800082c5  lea     r8, aWil; "wil"
0x1800082cc  mov     edx, 0DCh; void *
0x1800082d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800082d6  mov     ebx, eax
0x1800082d8  lea     rcx, [rsp+260h+var_238]
0x1800082dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800082e2  jmp     short loc_180008334
0x1800082e4  lea     rdx, [rsp+260h+var_240]; int *
0x1800082e9  mov     rcx, rax; hHandle
0x1800082ec  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800082f1  mov     ebx, eax
0x1800082f3  test    eax, eax
0x1800082f5  jns     short loc_180008314
0x1800082f7  mov     rcx, [rbp+168h]; this
0x1800082fe  lea     r8, aWil; "wil"
0x180008305  mov     r9d, eax; char *
0x180008308  mov     edx, 0DEh; void *
0x18000830d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008312  jmp     short loc_1800082D8
0x180008314  lea     rcx, [rsp+260h+var_238]
0x180008319  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000831e  movsxd  rcx, [rsp+260h+var_240]
0x180008323  movsxd  rax, [rsp+260h+var_23C]
0x180008328  shl     rcx, 1Fh
0x18000832c  or      rcx, rax
0x18000832f  mov     [rdi], rcx
0x180008332  xor     ebx, ebx
0x180008334  lea     rcx, [rsp+260h+var_230]
0x180008339  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000833e  mov     eax, ebx
0x180008340  mov     rcx, [rbp+160h+var_10]
0x180008347  xor     rcx, rsp; StackCookie
0x18000834a  call    __security_check_cookie
0x18000834f  lea     r11, [rsp+260h+var_s0]
0x180008357  mov     rbx, [r11+18h]
0x18000835b  mov     rdi, [r11+28h]
0x18000835f  mov     rsp, r11
0x180008362  pop     rbp
0x180008363  retn
```

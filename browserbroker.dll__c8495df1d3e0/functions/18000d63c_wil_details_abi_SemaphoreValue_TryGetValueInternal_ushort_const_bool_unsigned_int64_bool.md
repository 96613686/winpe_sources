# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d63c`
- end: `0x18000d7fa`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d5b8`

## callees

- `0x180002ce0`
- `0x180007034`
- `0x18000a184`
- `0x18000c144`
- `0x18000c164`
- `0x18000d088`
- `0x18000d17c`
- `0x18000d63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d6a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d745`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d6a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6b5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  StringCchCatW(Name, 0x104u, L"_p0");
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
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
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
0x18000d63c  mov     [rsp-8+arg_8], rbx
0x18000d641  push    rbp
0x18000d642  push    rdi
0x18000d643  push    r14
0x18000d645  lea     rbp, [rsp-160h]
0x18000d64d  sub     rsp, 260h
0x18000d654  mov     rax, cs:__security_cookie
0x18000d65b  xor     rax, rsp
0x18000d65e  mov     [rbp+170h+var_20], rax
0x18000d665  mov     rdi, r8
0x18000d668  mov     qword ptr [r8], 0
0x18000d66f  mov     r8, rcx; unsigned __int16 *
0x18000d672  mov     r14d, 104h
0x18000d678  mov     edx, r14d; unsigned __int64
0x18000d67b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d680  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d685  lea     r8, aP0; "_p0"
0x18000d68c  mov     edx, r14d; unsigned __int64
0x18000d68f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d694  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d699  lea     r8, [rsp+270h+Name]; lpName
0x18000d69e  xor     edx, edx; bInheritHandle
0x18000d6a0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d6a5  call    cs:__imp_OpenSemaphoreW
0x18000d6ab  mov     [rsp+270h+var_240], rax
0x18000d6b0  test    rax, rax
0x18000d6b3  jnz     short loc_18000D6E2
0x18000d6b5  call    cs:__imp_GetLastError
0x18000d6bb  cmp     eax, 2
0x18000d6be  jz      loc_18000D7C9
0x18000d6c4  mov     rcx, [rbp+178h]; this
0x18000d6cb  lea     r8, aWil; "wil"
0x18000d6d2  lea     edx, [r14-34h]; void *
0x18000d6d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d6db  mov     ebx, eax
0x18000d6dd  jmp     loc_18000D7CB
0x18000d6e2  lea     rdx, [rsp+270h+var_24C]; int *
0x18000d6e7  mov     [rsp+270h+var_24C], 0
0x18000d6ef  mov     rcx, rax; hHandle
0x18000d6f2  mov     [rsp+270h+var_250], 0; int
0x18000d6fa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d6ff  mov     ebx, eax
0x18000d701  test    eax, eax
0x18000d703  jns     short loc_18000D725
0x18000d705  mov     rcx, [rbp+178h]; this
0x18000d70c  lea     r8, aWil; "wil"
0x18000d713  mov     r9d, eax; char *
0x18000d716  mov     edx, 0D6h; void *
0x18000d71b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d720  jmp     loc_18000D7CB
0x18000d725  lea     r8, asc_180030B40; "h"
0x18000d72c  mov     rdx, r14; unsigned __int64
0x18000d72f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d734  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d739  lea     r8, [rsp+270h+Name]; lpName
0x18000d73e  xor     edx, edx; bInheritHandle
0x18000d740  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d745  call    cs:__imp_OpenSemaphoreW
0x18000d74b  mov     [rsp+270h+var_248], rax
0x18000d750  test    rax, rax
0x18000d753  jnz     short loc_18000D77B
0x18000d755  mov     rcx, [rbp+178h]; this
0x18000d75c  lea     r8, aWil; "wil"
0x18000d763  mov     edx, 0DCh; void *
0x18000d768  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d76d  mov     ebx, eax
0x18000d76f  lea     rcx, [rsp+270h+var_248]
0x18000d774  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d779  jmp     short loc_18000D7CB
0x18000d77b  lea     rdx, [rsp+270h+var_250]; int *
0x18000d780  mov     rcx, rax; hHandle
0x18000d783  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d788  mov     ebx, eax
0x18000d78a  test    eax, eax
0x18000d78c  jns     short loc_18000D7AB
0x18000d78e  mov     rcx, [rbp+178h]; this
0x18000d795  lea     r8, aWil; "wil"
0x18000d79c  mov     r9d, eax; char *
0x18000d79f  mov     edx, 0DEh; void *
0x18000d7a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7a9  jmp     short loc_18000D76F
0x18000d7ab  lea     rcx, [rsp+270h+var_248]
0x18000d7b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d7b5  movsxd  rcx, [rsp+270h+var_250]
0x18000d7ba  movsxd  rax, [rsp+270h+var_24C]
0x18000d7bf  shl     rcx, 1Fh
0x18000d7c3  or      rcx, rax
0x18000d7c6  mov     [rdi], rcx
0x18000d7c9  xor     ebx, ebx
0x18000d7cb  lea     rcx, [rsp+270h+var_240]
0x18000d7d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d7d5  mov     eax, ebx
0x18000d7d7  mov     rcx, [rbp+170h+var_20]
0x18000d7de  xor     rcx, rsp; StackCookie
0x18000d7e1  call    __security_check_cookie
0x18000d7e6  mov     rbx, [rsp+270h+arg_8]
0x18000d7ee  add     rsp, 260h
0x18000d7f5  pop     r14
0x18000d7f7  pop     rdi
0x18000d7f8  pop     rbp
0x18000d7f9  retn
```

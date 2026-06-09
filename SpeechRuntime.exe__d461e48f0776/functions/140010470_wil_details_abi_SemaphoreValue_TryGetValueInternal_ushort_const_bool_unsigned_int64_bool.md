# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140010470`
- end: `0x14001062e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400103ec`

## callees

- `0x140002d30`
- `0x140007fc8`
- `0x14000bf08`
- `0x14000e010`
- `0x14000e030`
- `0x14000fea4`
- `0x14000ff98`
- `0x140010470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400104d9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140010579`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400104d9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140010579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400104e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400104e9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x140010470  mov     [rsp-8+arg_8], rbx
0x140010475  push    rbp
0x140010476  push    rdi
0x140010477  push    r14
0x140010479  lea     rbp, [rsp-160h]
0x140010481  sub     rsp, 260h
0x140010488  mov     rax, cs:__security_cookie
0x14001048f  xor     rax, rsp
0x140010492  mov     [rbp+170h+var_20], rax
0x140010499  mov     rdi, r8
0x14001049c  mov     qword ptr [r8], 0
0x1400104a3  mov     r8, rcx; unsigned __int16 *
0x1400104a6  mov     r14d, 104h
0x1400104ac  mov     edx, r14d; unsigned __int64
0x1400104af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400104b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400104b9  lea     r8, aP0; "_p0"
0x1400104c0  mov     edx, r14d; unsigned __int64
0x1400104c3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400104c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400104cd  lea     r8, [rsp+270h+Name]; lpName
0x1400104d2  xor     edx, edx; bInheritHandle
0x1400104d4  mov     ecx, 1F0003h; dwDesiredAccess
0x1400104d9  call    cs:__imp_OpenSemaphoreW
0x1400104df  mov     [rsp+270h+var_240], rax
0x1400104e4  test    rax, rax
0x1400104e7  jnz     short loc_140010516
0x1400104e9  call    cs:__imp_GetLastError
0x1400104ef  cmp     eax, 2
0x1400104f2  jz      loc_1400105FD
0x1400104f8  mov     rcx, [rbp+178h]; this
0x1400104ff  lea     r8, aWil; "wil"
0x140010506  lea     edx, [r14-34h]; void *
0x14001050a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001050f  mov     ebx, eax
0x140010511  jmp     loc_1400105FF
0x140010516  lea     rdx, [rsp+270h+var_24C]; int *
0x14001051b  mov     [rsp+270h+var_24C], 0
0x140010523  mov     rcx, rax; hHandle
0x140010526  mov     [rsp+270h+var_250], 0; int
0x14001052e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140010533  mov     ebx, eax
0x140010535  test    eax, eax
0x140010537  jns     short loc_140010559
0x140010539  mov     rcx, [rbp+178h]; this
0x140010540  lea     r8, aWil; "wil"
0x140010547  mov     r9d, eax; char *
0x14001054a  mov     edx, 0D6h; void *
0x14001054f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010554  jmp     loc_1400105FF
0x140010559  lea     r8, asc_140034F70; "h"
0x140010560  mov     rdx, r14; unsigned __int64
0x140010563  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140010568  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001056d  lea     r8, [rsp+270h+Name]; lpName
0x140010572  xor     edx, edx; bInheritHandle
0x140010574  mov     ecx, 1F0003h; dwDesiredAccess
0x140010579  call    cs:__imp_OpenSemaphoreW
0x14001057f  mov     [rsp+270h+var_248], rax
0x140010584  test    rax, rax
0x140010587  jnz     short loc_1400105AF
0x140010589  mov     rcx, [rbp+178h]; this
0x140010590  lea     r8, aWil; "wil"
0x140010597  mov     edx, 0DCh; void *
0x14001059c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400105a1  mov     ebx, eax
0x1400105a3  lea     rcx, [rsp+270h+var_248]
0x1400105a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400105ad  jmp     short loc_1400105FF
0x1400105af  lea     rdx, [rsp+270h+var_250]; int *
0x1400105b4  mov     rcx, rax; hHandle
0x1400105b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400105bc  mov     ebx, eax
0x1400105be  test    eax, eax
0x1400105c0  jns     short loc_1400105DF
0x1400105c2  mov     rcx, [rbp+178h]; this
0x1400105c9  lea     r8, aWil; "wil"
0x1400105d0  mov     r9d, eax; char *
0x1400105d3  mov     edx, 0DEh; void *
0x1400105d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400105dd  jmp     short loc_1400105A3
0x1400105df  lea     rcx, [rsp+270h+var_248]
0x1400105e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400105e9  movsxd  rcx, [rsp+270h+var_250]
0x1400105ee  movsxd  rax, [rsp+270h+var_24C]
0x1400105f3  shl     rcx, 1Fh
0x1400105f7  or      rcx, rax
0x1400105fa  mov     [rdi], rcx
0x1400105fd  xor     ebx, ebx
0x1400105ff  lea     rcx, [rsp+270h+var_240]
0x140010604  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140010609  mov     eax, ebx
0x14001060b  mov     rcx, [rbp+170h+var_20]
0x140010612  xor     rcx, rsp; StackCookie
0x140010615  call    __security_check_cookie
0x14001061a  mov     rbx, [rsp+270h+arg_8]
0x140010622  add     rsp, 260h
0x140010629  pop     r14
0x14001062b  pop     rdi
0x14001062c  pop     rbp
0x14001062d  retn
```

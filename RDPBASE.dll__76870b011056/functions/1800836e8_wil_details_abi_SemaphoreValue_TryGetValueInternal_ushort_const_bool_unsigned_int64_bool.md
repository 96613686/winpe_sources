# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800836e8`
- end: `0x18008388a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180081a90`

## callees

- `0x180038984`
- `0x18006ce24`
- `0x180078c20`
- `0x180081a10`
- `0x1800827e0`
- `0x180083030`
- `0x180083050`
- `0x1800836e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083761`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180083751`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800837e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180083751`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800837e3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800836e8  mov     [rsp-8+arg_8], rbx
0x1800836ed  push    rbp
0x1800836ee  push    rdi
0x1800836ef  push    r14
0x1800836f1  lea     rbp, [rsp-160h]
0x1800836f9  sub     rsp, 260h
0x180083700  mov     rax, cs:__security_cookie
0x180083707  xor     rax, rsp
0x18008370a  mov     [rbp+170h+var_20], rax
0x180083711  mov     rdi, r8
0x180083714  mov     qword ptr [r8], 0
0x18008371b  mov     r8, rcx; unsigned __int16 *
0x18008371e  mov     r14d, 104h
0x180083724  mov     edx, r14d; unsigned __int64
0x180083727  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008372c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180083731  lea     r8, aP0; "_p0"
0x180083738  mov     edx, r14d; unsigned __int64
0x18008373b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180083740  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180083745  lea     r8, [rsp+270h+Name]; lpName
0x18008374a  xor     edx, edx; bInheritHandle
0x18008374c  mov     ecx, 1F0003h; dwDesiredAccess
0x180083751  call    cs:__imp_OpenSemaphoreW
0x180083757  mov     [rsp+270h+var_240], rax
0x18008375c  test    rax, rax
0x18008375f  jnz     short loc_180083787
0x180083761  call    cs:__imp_GetLastError
0x180083767  cmp     eax, 2
0x18008376a  jz      loc_180083859
0x180083770  mov     rcx, [rbp+178h]; this
0x180083777  lea     edx, [r14-34h]; void *
0x18008377b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180083780  mov     ebx, eax
0x180083782  jmp     loc_18008385B
0x180083787  lea     rdx, [rsp+270h+var_24C]; int *
0x18008378c  mov     [rsp+270h+var_24C], 0
0x180083794  mov     rcx, rax; hHandle
0x180083797  mov     [rsp+270h+var_250], 0; int
0x18008379f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800837a4  mov     ebx, eax
0x1800837a6  test    eax, eax
0x1800837a8  jns     short loc_1800837C3
0x1800837aa  mov     rcx, [rbp+178h]; this
0x1800837b1  mov     r9d, eax; char *
0x1800837b4  mov     edx, 0D6h; void *
0x1800837b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800837be  jmp     loc_18008385B
0x1800837c3  lea     r8, asc_1801722E0; "h"
0x1800837ca  mov     rdx, r14; unsigned __int64
0x1800837cd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800837d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800837d7  lea     r8, [rsp+270h+Name]; lpName
0x1800837dc  xor     edx, edx; bInheritHandle
0x1800837de  mov     ecx, 1F0003h; dwDesiredAccess
0x1800837e3  call    cs:__imp_OpenSemaphoreW
0x1800837e9  mov     [rsp+270h+var_248], rax
0x1800837ee  test    rax, rax
0x1800837f1  jnz     short loc_180083812
0x1800837f3  mov     rcx, [rbp+178h]; this
0x1800837fa  mov     edx, 0DCh; void *
0x1800837ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180083804  mov     ebx, eax
0x180083806  lea     rcx, [rsp+270h+var_248]
0x18008380b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180083810  jmp     short loc_18008385B
0x180083812  lea     rdx, [rsp+270h+var_250]; int *
0x180083817  mov     rcx, rax; hHandle
0x18008381a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18008381f  mov     ebx, eax
0x180083821  test    eax, eax
0x180083823  jns     short loc_18008383B
0x180083825  mov     rcx, [rbp+178h]; this
0x18008382c  mov     r9d, eax; char *
0x18008382f  mov     edx, 0DEh; void *
0x180083834  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083839  jmp     short loc_180083806
0x18008383b  lea     rcx, [rsp+270h+var_248]
0x180083840  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180083845  movsxd  rcx, [rsp+270h+var_250]
0x18008384a  movsxd  rax, [rsp+270h+var_24C]
0x18008384f  shl     rcx, 1Fh
0x180083853  or      rcx, rax
0x180083856  mov     [rdi], rcx
0x180083859  xor     ebx, ebx
0x18008385b  lea     rcx, [rsp+270h+var_240]
0x180083860  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180083865  mov     eax, ebx
0x180083867  mov     rcx, [rbp+170h+var_20]
0x18008386e  xor     rcx, rsp; StackCookie
0x180083871  call    __security_check_cookie
0x180083876  mov     rbx, [rsp+270h+arg_8]
0x18008387e  add     rsp, 260h
0x180083885  pop     r14
0x180083887  pop     rdi
0x180083888  pop     rbp
0x180083889  retn
```

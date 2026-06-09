# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002543c`
- end: `0x1800255dd`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `417`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800253c8`

## callees

- `0x18000af20`
- `0x18000c060`
- `0x180015200`
- `0x180016020`
- `0x180016c26`
- `0x180022944`
- `0x180023ad8`
- `0x180024d78`
- `0x18002543c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800254a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025536`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800254a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025536`

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
  if ( GetLastError_0() == 2 )
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
0x18002543c  mov     [rsp-8+arg_8], rbx
0x180025441  push    rbp
0x180025442  push    rdi
0x180025443  push    r14
0x180025445  lea     rbp, [rsp-160h]
0x18002544d  sub     rsp, 260h
0x180025454  mov     rax, cs:__security_cookie
0x18002545b  xor     rax, rsp
0x18002545e  mov     [rbp+170h+var_20], rax
0x180025465  mov     rdi, r8
0x180025468  mov     qword ptr [r8], 0
0x18002546f  mov     r8, rcx; unsigned __int16 *
0x180025472  mov     r14d, 104h
0x180025478  mov     edx, r14d; unsigned __int64
0x18002547b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025480  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025485  lea     r8, aP0; "_p0"
0x18002548c  mov     edx, r14d; unsigned __int64
0x18002548f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025494  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025499  lea     r8, [rsp+270h+Name]; lpName
0x18002549e  xor     edx, edx; bInheritHandle
0x1800254a0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800254a5  call    cs:__imp_OpenSemaphoreW
0x1800254ab  mov     [rsp+270h+var_240], rax
0x1800254b0  test    rax, rax
0x1800254b3  jnz     short loc_1800254DA
0x1800254b5  call    GetLastError_0
0x1800254ba  cmp     eax, 2
0x1800254bd  jz      loc_1800255AC
0x1800254c3  mov     rcx, [rbp+178h]; this
0x1800254ca  lea     edx, [r14-34h]; void *
0x1800254ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800254d3  mov     ebx, eax
0x1800254d5  jmp     loc_1800255AE
0x1800254da  lea     rdx, [rsp+270h+var_24C]; int *
0x1800254df  mov     [rsp+270h+var_24C], 0
0x1800254e7  mov     rcx, rax; hHandle
0x1800254ea  mov     [rsp+270h+var_250], 0; int
0x1800254f2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800254f7  mov     ebx, eax
0x1800254f9  test    eax, eax
0x1800254fb  jns     short loc_180025516
0x1800254fd  mov     rcx, [rbp+178h]; this
0x180025504  mov     r9d, eax; char *
0x180025507  mov     edx, 0D6h; void *
0x18002550c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025511  jmp     loc_1800255AE
0x180025516  lea     r8, asc_180091ED8; "h"
0x18002551d  mov     rdx, r14; unsigned __int64
0x180025520  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025525  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002552a  lea     r8, [rsp+270h+Name]; lpName
0x18002552f  xor     edx, edx; bInheritHandle
0x180025531  mov     ecx, 1F0003h; dwDesiredAccess
0x180025536  call    cs:__imp_OpenSemaphoreW
0x18002553c  mov     [rsp+270h+var_248], rax
0x180025541  test    rax, rax
0x180025544  jnz     short loc_180025565
0x180025546  mov     rcx, [rbp+178h]; this
0x18002554d  mov     edx, 0DCh; void *
0x180025552  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025557  mov     ebx, eax
0x180025559  lea     rcx, [rsp+270h+var_248]
0x18002555e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025563  jmp     short loc_1800255AE
0x180025565  lea     rdx, [rsp+270h+var_250]; int *
0x18002556a  mov     rcx, rax; hHandle
0x18002556d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180025572  mov     ebx, eax
0x180025574  test    eax, eax
0x180025576  jns     short loc_18002558E
0x180025578  mov     rcx, [rbp+178h]; this
0x18002557f  mov     r9d, eax; char *
0x180025582  mov     edx, 0DEh; void *
0x180025587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002558c  jmp     short loc_180025559
0x18002558e  lea     rcx, [rsp+270h+var_248]
0x180025593  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025598  movsxd  rcx, [rsp+270h+var_250]
0x18002559d  movsxd  rax, [rsp+270h+var_24C]
0x1800255a2  shl     rcx, 1Fh
0x1800255a6  or      rcx, rax
0x1800255a9  mov     [rdi], rcx
0x1800255ac  xor     ebx, ebx
0x1800255ae  lea     rcx, [rsp+270h+var_240]
0x1800255b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800255b8  mov     eax, ebx
0x1800255ba  mov     rcx, [rbp+170h+var_20]
0x1800255c1  xor     rcx, rsp; StackCookie
0x1800255c4  call    __security_check_cookie
0x1800255c9  mov     rbx, [rsp+270h+arg_8]
0x1800255d1  add     rsp, 260h
0x1800255d8  pop     r14
0x1800255da  pop     rdi
0x1800255db  pop     rbp
0x1800255dc  retn
```

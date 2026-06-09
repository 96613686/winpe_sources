# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180013348`
- end: `0x1800134ea`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800132d4`

## callees

- `0x180005624`
- `0x180009b30`
- `0x18000e7bc`
- `0x18000e7dc`
- `0x180012794`
- `0x180012820`
- `0x180013348`
- `0x18006c690`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x1800133b1`
- `KERNEL32!OpenSemaphoreW` at `0x180013443`
- `KERNEL32!OpenSemaphoreW` at `0x1800133b1`
- `KERNEL32!OpenSemaphoreW` at `0x180013443`
- `KERNEL32!GetLastError` at `0x1800133c1`
- `KERNEL32!GetLastError` at `0x1800133c1`

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
0x180013348  mov     [rsp-8+arg_8], rbx
0x18001334d  push    rbp
0x18001334e  push    rdi
0x18001334f  push    r14
0x180013351  lea     rbp, [rsp-160h]
0x180013359  sub     rsp, 260h
0x180013360  mov     rax, cs:__security_cookie
0x180013367  xor     rax, rsp
0x18001336a  mov     [rbp+170h+var_20], rax
0x180013371  mov     rdi, r8
0x180013374  mov     qword ptr [r8], 0
0x18001337b  mov     r8, rcx; unsigned __int16 *
0x18001337e  mov     r14d, 104h
0x180013384  mov     edx, r14d; unsigned __int64
0x180013387  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001338c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013391  lea     r8, aP0; "_p0"
0x180013398  mov     edx, r14d; unsigned __int64
0x18001339b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800133a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800133a5  lea     r8, [rsp+270h+Name]; lpName
0x1800133aa  xor     edx, edx; bInheritHandle
0x1800133ac  mov     ecx, 1F0003h; dwDesiredAccess
0x1800133b1  call    cs:__imp_OpenSemaphoreW
0x1800133b7  mov     [rsp+270h+var_240], rax
0x1800133bc  test    rax, rax
0x1800133bf  jnz     short loc_1800133E7
0x1800133c1  call    cs:__imp_GetLastError
0x1800133c7  cmp     eax, 2
0x1800133ca  jz      loc_1800134B9
0x1800133d0  mov     rcx, [rbp+178h]; this
0x1800133d7  lea     edx, [r14-34h]; void *
0x1800133db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800133e0  mov     ebx, eax
0x1800133e2  jmp     loc_1800134BB
0x1800133e7  lea     rdx, [rsp+270h+var_24C]; int *
0x1800133ec  mov     [rsp+270h+var_24C], 0
0x1800133f4  mov     rcx, rax; hHandle
0x1800133f7  mov     [rsp+270h+var_250], 0; int
0x1800133ff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013404  mov     ebx, eax
0x180013406  test    eax, eax
0x180013408  jns     short loc_180013423
0x18001340a  mov     rcx, [rbp+178h]; this
0x180013411  mov     r9d, eax; char *
0x180013414  mov     edx, 0D6h; void *
0x180013419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001341e  jmp     loc_1800134BB
0x180013423  lea     r8, asc_180076158; "h"
0x18001342a  mov     rdx, r14; unsigned __int64
0x18001342d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180013432  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013437  lea     r8, [rsp+270h+Name]; lpName
0x18001343c  xor     edx, edx; bInheritHandle
0x18001343e  mov     ecx, 1F0003h; dwDesiredAccess
0x180013443  call    cs:__imp_OpenSemaphoreW
0x180013449  mov     [rsp+270h+var_248], rax
0x18001344e  test    rax, rax
0x180013451  jnz     short loc_180013472
0x180013453  mov     rcx, [rbp+178h]; this
0x18001345a  mov     edx, 0DCh; void *
0x18001345f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013464  mov     ebx, eax
0x180013466  lea     rcx, [rsp+270h+var_248]
0x18001346b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013470  jmp     short loc_1800134BB
0x180013472  lea     rdx, [rsp+270h+var_250]; int *
0x180013477  mov     rcx, rax; hHandle
0x18001347a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001347f  mov     ebx, eax
0x180013481  test    eax, eax
0x180013483  jns     short loc_18001349B
0x180013485  mov     rcx, [rbp+178h]; this
0x18001348c  mov     r9d, eax; char *
0x18001348f  mov     edx, 0DEh; void *
0x180013494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013499  jmp     short loc_180013466
0x18001349b  lea     rcx, [rsp+270h+var_248]
0x1800134a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800134a5  movsxd  rcx, [rsp+270h+var_250]
0x1800134aa  movsxd  rax, [rsp+270h+var_24C]
0x1800134af  shl     rcx, 1Fh
0x1800134b3  or      rcx, rax
0x1800134b6  mov     [rdi], rcx
0x1800134b9  xor     ebx, ebx
0x1800134bb  lea     rcx, [rsp+270h+var_240]
0x1800134c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800134c5  mov     eax, ebx
0x1800134c7  mov     rcx, [rbp+170h+var_20]
0x1800134ce  xor     rcx, rsp; StackCookie
0x1800134d1  call    __security_check_cookie
0x1800134d6  mov     rbx, [rsp+270h+arg_8]
0x1800134de  add     rsp, 260h
0x1800134e5  pop     r14
0x1800134e7  pop     rdi
0x1800134e8  pop     rbp
0x1800134e9  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000863c`
- end: `0x1800087ec`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800085b8`

## callees

- `0x180002dc0`
- `0x180005d00`
- `0x180006f1c`
- `0x180007d54`
- `0x180007d74`
- `0x180008290`
- `0x180008380`
- `0x18000863c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800086a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000873e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800086a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000873e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086b5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v23 = v5;
  if ( v5 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v19);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v11 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v22 = v11;
    if ( v11 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v20);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v16);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v14);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x18000863c  mov     [rsp-8+arg_8], rbx
0x180008641  push    rbp
0x180008642  push    rdi
0x180008643  push    r14
0x180008645  lea     rbp, [rsp-170h]
0x18000864d  sub     rsp, 270h
0x180008654  mov     rax, cs:__security_cookie
0x18000865b  xor     rax, rsp
0x18000865e  mov     [rbp+180h+var_20], rax
0x180008665  mov     r9, rcx; pszSrc
0x180008668  mov     qword ptr [r8], 0
0x18000866f  mov     r14d, 104h
0x180008675  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000867a  mov     edx, r14d; cchDest
0x18000867d  mov     rdi, r8
0x180008680  call    StringCopyWorkerW
0x180008685  lea     r8, aP0; "_p0"
0x18000868c  mov     edx, r14d; unsigned __int64
0x18000868f  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180008694  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008699  lea     r8, [rsp+280h+pszDest]; lpName
0x18000869e  xor     edx, edx; bInheritHandle
0x1800086a0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800086a5  call    cs:__imp_OpenSemaphoreW
0x1800086ab  mov     [rsp+280h+var_240], rax
0x1800086b0  test    rax, rax
0x1800086b3  jnz     short loc_1800086DB
0x1800086b5  call    cs:__imp_GetLastError
0x1800086bb  cmp     eax, 2
0x1800086be  jz      loc_1800087BB
0x1800086c4  mov     rcx, [rbp+188h]; this
0x1800086cb  lea     edx, [r14-34h]; void *
0x1800086cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800086d4  mov     ebx, eax
0x1800086d6  jmp     loc_1800087BD
0x1800086db  lea     rdx, [rsp+280h+var_24C]; int *
0x1800086e0  mov     [rsp+280h+var_24C], 0
0x1800086e8  mov     rcx, rax; hHandle
0x1800086eb  mov     [rsp+280h+var_250], 0
0x1800086f3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800086f8  mov     ebx, eax
0x1800086fa  test    eax, eax
0x1800086fc  jns     short loc_18000871E
0x1800086fe  mov     rcx, [rbp+188h]; this
0x180008705  lea     r8, aWil; "wil"
0x18000870c  mov     r9d, eax; char *
0x18000870f  mov     edx, 0D6h; void *
0x180008714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008719  jmp     loc_1800087BD
0x18000871e  lea     r8, asc_180034DF8; "h"
0x180008725  mov     rdx, r14; unsigned __int64
0x180008728  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18000872d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008732  lea     r8, [rsp+280h+pszDest]; lpName
0x180008737  xor     edx, edx; bInheritHandle
0x180008739  mov     ecx, 1F0003h; dwDesiredAccess
0x18000873e  call    cs:__imp_OpenSemaphoreW
0x180008744  mov     [rsp+280h+var_248], rax
0x180008749  test    rax, rax
0x18000874c  jnz     short loc_18000876D
0x18000874e  mov     rcx, [rbp+188h]; this
0x180008755  mov     edx, 0DCh; void *
0x18000875a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000875f  mov     ebx, eax
0x180008761  lea     rcx, [rsp+280h+var_248]
0x180008766  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000876b  jmp     short loc_1800087BD
0x18000876d  lea     rdx, [rsp+280h+var_250]; int *
0x180008772  mov     rcx, rax; hHandle
0x180008775  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000877a  mov     ebx, eax
0x18000877c  test    eax, eax
0x18000877e  jns     short loc_18000879D
0x180008780  mov     rcx, [rbp+188h]; this
0x180008787  lea     r8, aWil; "wil"
0x18000878e  mov     r9d, eax; char *
0x180008791  mov     edx, 0DEh; void *
0x180008796  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000879b  jmp     short loc_180008761
0x18000879d  lea     rcx, [rsp+280h+var_248]
0x1800087a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800087a7  movsxd  rcx, [rsp+280h+var_250]
0x1800087ac  movsxd  rax, [rsp+280h+var_24C]
0x1800087b1  shl     rcx, 1Fh
0x1800087b5  or      rcx, rax
0x1800087b8  mov     [rdi], rcx
0x1800087bb  xor     ebx, ebx
0x1800087bd  lea     rcx, [rsp+280h+var_240]
0x1800087c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800087c7  mov     eax, ebx
0x1800087c9  mov     rcx, [rbp+180h+var_20]
0x1800087d0  xor     rcx, rsp; StackCookie
0x1800087d3  call    __security_check_cookie
0x1800087d8  mov     rbx, [rsp+280h+arg_8]
0x1800087e0  add     rsp, 270h
0x1800087e7  pop     r14
0x1800087e9  pop     rdi
0x1800087ea  pop     rbp
0x1800087eb  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180017fa0`
- end: `0x1800181b6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `534`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180010320`
- `0x180017f20`

## callees

- `0x180007c78`
- `0x18001288c`
- `0x180017fa0`
- `0x1800181f8`
- `0x180018218`
- `0x180018268`
- `0x180018400`
- `0x180018420`
- `0x18001af9c`
- `0x180044a20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018046`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800180eb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018046`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800180eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebx
  size_t *v6; // r8
  const wchar_t *v7; // r9
  size_t *v8; // r8
  HANDLE v9; // rax
  const char *v10; // r9
  int ValueFromSemaphore; // eax
  int v13; // edi
  HANDLE v14; // rax
  const char *v15; // r9
  int v16; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  size_t pcchDestLength; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  LastError = 0;
  *a3 = 0;
  if ( StringValidateDestW(a1, 0x104u, (const size_t)a3) < 0 )
    pszDest[0] = 0;
  else
    StringCopyWorkerW(pszDest, 0x104u, v6, v7, v17);
  pcchDestLength = 0;
  if ( StringValidateDestAndLengthW(pszDest, 0x104u, &pcchDestLength, (const size_t)v7) >= 0 )
    StringCopyWorkerW(&pszDest[pcchDestLength], 260 - pcchDestLength, v8, L"_p0", v17);
  v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v21[0] = v9;
  if ( v9 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v20);
    v13 = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(pszDest, 0x104u, L"h");
      v14 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
      pcchDestLength = (size_t)v14;
      if ( !v14 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v15);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pcchDestLength);
        goto LABEL_17;
      }
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v19);
      v13 = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pcchDestLength);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_17;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v16,
        v17);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pcchDestLength);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
    }
    LastError = v13;
  }
  else if ( GetLastError() != 2 )
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v10);
  }
LABEL_17:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  return LastError;
}

```

## disassembly

```asm
0x180017fa0  mov     [rsp-8+arg_0], rbx
0x180017fa5  mov     [rsp-8+arg_8], rsi
0x180017faa  push    rbp
0x180017fab  push    rdi
0x180017fac  push    r14
0x180017fae  lea     rbp, [rsp-170h]
0x180017fb6  sub     rsp, 270h
0x180017fbd  mov     rax, cs:__security_cookie
0x180017fc4  xor     rax, rsp
0x180017fc7  mov     [rbp+180h+var_20], rax
0x180017fce  mov     r14d, 104h
0x180017fd4  xor     ebx, ebx
0x180017fd6  mov     edx, r14d; cchDest
0x180017fd9  mov     [r8], rbx
0x180017fdc  mov     rsi, r8
0x180017fdf  mov     r9, rcx
0x180017fe2  call    StringValidateDestW
0x180017fe7  test    eax, eax
0x180017fe9  js      short loc_180017FFA
0x180017feb  mov     edx, r14d; cchDest
0x180017fee  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180017ff3  call    StringCopyWorkerW
0x180017ff8  jmp     short loc_180017FFF
0x180017ffa  mov     [rsp+280h+pszDest], bx
0x180017fff  lea     r8, [rsp+280h+pcchDestLength]; pcchDestLength
0x180018004  mov     [rsp+280h+pcchDestLength], rbx
0x180018009  mov     rdx, r14; cchDest
0x18001800c  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180018011  call    StringValidateDestAndLengthW
0x180018016  test    eax, eax
0x180018018  js      short loc_18001803A
0x18001801a  mov     rax, [rsp+280h+pcchDestLength]
0x18001801f  lea     rcx, [rsp+280h+pszDest]
0x180018024  mov     rdx, r14
0x180018027  lea     r9, aP0; "_p0"
0x18001802e  sub     rdx, rax; cchDest
0x180018031  lea     rcx, [rcx+rax*2]; pszDest
0x180018035  call    StringCopyWorkerW
0x18001803a  lea     r8, [rsp+280h+pszDest]; lpName
0x18001803f  xor     edx, edx; bInheritHandle
0x180018041  mov     ecx, 1F0003h; dwDesiredAccess
0x180018046  call    cs:__imp_OpenSemaphoreW
0x18001804d  nop     dword ptr [rax+rax+00h]
0x180018052  mov     [rsp+280h+var_240], rax
0x180018057  test    rax, rax
0x18001805a  jnz     short loc_18001808E
0x18001805c  call    cs:__imp_GetLastError
0x180018063  nop     dword ptr [rax+rax+00h]
0x180018068  cmp     eax, 2
0x18001806b  jz      loc_180018182
0x180018071  mov     rcx, [rbp+188h]; this
0x180018078  lea     r8, aWil; "wil"
0x18001807f  mov     edx, 0CDh; void *
0x180018084  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018089  jmp     loc_18001818E
0x18001808e  lea     rdx, [rsp+280h+var_244]; int *
0x180018093  mov     [rsp+280h+var_244], ebx
0x180018097  mov     rcx, rax; hHandle
0x18001809a  mov     [rsp+280h+var_248], ebx
0x18001809e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800180a3  mov     edi, eax
0x1800180a5  test    eax, eax
0x1800180a7  jns     short loc_1800180CB
0x1800180a9  mov     rcx, [rbp+188h]; this
0x1800180b0  lea     r8, aWil; "wil"
0x1800180b7  mov     r9d, eax; char *
0x1800180ba  mov     edx, 0D3h; void *
0x1800180bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180c4  mov     ebx, edi
0x1800180c6  jmp     loc_180018182
0x1800180cb  lea     r8, asc_18004D43C; "h"
0x1800180d2  mov     rdx, r14; unsigned __int64
0x1800180d5  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x1800180da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800180df  lea     r8, [rsp+280h+pszDest]; lpName
0x1800180e4  xor     edx, edx; bInheritHandle
0x1800180e6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800180eb  call    cs:__imp_OpenSemaphoreW
0x1800180f2  nop     dword ptr [rax+rax+00h]
0x1800180f7  mov     [rsp+280h+pcchDestLength], rax
0x1800180fc  test    rax, rax
0x1800180ff  jnz     short loc_180018127
0x180018101  mov     rcx, [rbp+188h]; this
0x180018108  lea     r8, aWil; "wil"
0x18001810f  mov     edx, 0D9h; void *
0x180018114  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018119  lea     rcx, [rsp+280h+pcchDestLength]
0x18001811e  mov     ebx, eax
0x180018120  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018125  jmp     short loc_180018182
0x180018127  lea     rdx, [rsp+280h+var_248]; int *
0x18001812c  mov     rcx, rax; hHandle
0x18001812f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180018134  mov     edi, eax
0x180018136  test    eax, eax
0x180018138  jns     short loc_180018164
0x18001813a  mov     rcx, [rbp+188h]; this
0x180018141  lea     r8, aWil; "wil"
0x180018148  mov     r9d, eax; char *
0x18001814b  mov     edx, 0DBh; void *
0x180018150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018155  lea     rcx, [rsp+280h+pcchDestLength]
0x18001815a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001815f  jmp     loc_1800180C4
0x180018164  lea     rcx, [rsp+280h+pcchDestLength]
0x180018169  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001816e  movsxd  rdx, [rsp+280h+var_248]
0x180018173  movsxd  rcx, [rsp+280h+var_244]
0x180018178  shl     rdx, 1Fh
0x18001817c  or      rdx, rcx
0x18001817f  mov     [rsi], rdx
0x180018182  lea     rcx, [rsp+280h+var_240]
0x180018187  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001818c  mov     eax, ebx
0x18001818e  mov     rcx, [rbp+180h+var_20]
0x180018195  xor     rcx, rsp; StackCookie
0x180018198  call    __security_check_cookie
0x18001819d  lea     r11, [rsp+280h+var_10]
0x1800181a5  mov     rbx, [r11+20h]
0x1800181a9  mov     rsi, [r11+28h]
0x1800181ad  mov     rsp, r11
0x1800181b0  pop     r14
0x1800181b2  pop     rdi
0x1800181b3  pop     rbp
0x1800181b4  retn
```

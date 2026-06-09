# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000e2a0`
- end: `0x18000e493`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `499`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e49c`
- `0x180023f80`

## callees

- `0x18000e1c0`
- `0x18000e2a0`
- `0x18001abe4`
- `0x18002477c`
- `0x180026474`
- `0x1800264cc`
- `0x18002a030`
- `0x18002c9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e3cc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e3cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e405`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // r10
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // ebx
  bool v12; // zf
  WCHAR *v13; // rcx
  __int64 v14; // r8
  WCHAR *v15; // rax
  __int64 v16; // r9
  WCHAR *v17; // rax
  const wchar_t *v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // rcx
  LONG v21; // r8d
  wil::details *v22; // rcx
  HANDLE Semaphore; // rdi
  int LastErrorFailHr; // eax
  unsigned __int64 v25; // rdx
  unsigned int v26; // edi
  unsigned __int64 v28; // rsi
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v30; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = 260;
  v11 = 1;
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v9;
    --v10;
  }
  while ( v10 );
  v12 = v10 == 0;
  v13 = v7 - 1;
  v14 = 260;
  if ( !v12 )
    v13 = v7;
  v15 = Name;
  *v13 = 0;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = (260 - v14) & -(__int64)(v14 != 0);
  if ( v14 )
  {
    v17 = &Name[v16];
    v18 = L"_p0";
    v19 = 260 - v16;
    if ( 260 != v16 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v18 )
          break;
        *v17++ = *v18++;
        --v8;
        --v19;
      }
      while ( v19 );
    }
    v20 = v17 - 1;
    if ( v19 )
      v20 = v17;
    *v20 = 0;
  }
  v21 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v21 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v21, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v22);
    v26 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v26;
    }
  }
  v28 = a4 >> 31;
  StringCchCatW(Name, v25, L"h");
  if ( (_DWORD)v28 )
    v11 = v28;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 8, (unsigned int)v28, v11, Name);
  v30 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"wil",
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    dwFlags);
  return v30;
}

```

## disassembly

```asm
0x18000e2a0  mov     [rsp+arg_8], rbx
0x18000e2a5  mov     [rsp+arg_10], rbp
0x18000e2aa  push    rsi
0x18000e2ab  push    rdi
0x18000e2ac  push    r14
0x18000e2ae  sub     rsp, 260h
0x18000e2b5  mov     rax, cs:__security_cookie
0x18000e2bc  xor     rax, rsp
0x18000e2bf  mov     [rsp+278h+var_28], rax
0x18000e2c7  mov     rax, 0C000000000000000h
0x18000e2d1  mov     rsi, r9
0x18000e2d4  mov     r11, rdx
0x18000e2d7  mov     rbp, rcx
0x18000e2da  test    rax, r9
0x18000e2dd  jz      short loc_18000E2E5
0x18000e2df  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18000e2e5  xor     r14d, r14d
0x18000e2e8  lea     rax, [rsp+278h+Name]
0x18000e2ed  mov     r10d, 7FFFFFFEh
0x18000e2f3  mov     edx, 104h
0x18000e2f8  mov     ecx, r10d
0x18000e2fb  mov     r8d, edx
0x18000e2fe  lea     ebx, [r14+1]
0x18000e302  test    rcx, rcx
0x18000e305  jz      short loc_18000E325
0x18000e307  movzx   r9d, word ptr [r11]
0x18000e30b  test    r9w, r9w
0x18000e30f  jz      short loc_18000E325
0x18000e311  mov     [rax], r9w
0x18000e315  add     r11, 2
0x18000e319  add     rax, 2
0x18000e31d  sub     rcx, rbx
0x18000e320  sub     r8, rbx
0x18000e323  jnz     short loc_18000E302
0x18000e325  test    r8, r8
0x18000e328  lea     rcx, [rax-2]
0x18000e32c  mov     r8, rdx
0x18000e32f  cmovnz  rcx, rax
0x18000e333  lea     rax, [rsp+278h+Name]
0x18000e338  mov     [rcx], r14w
0x18000e33c  cmp     [rax], r14w
0x18000e340  jz      short loc_18000E34B
0x18000e342  add     rax, 2
0x18000e346  sub     r8, rbx
0x18000e349  jnz     short loc_18000E33C
0x18000e34b  mov     rcx, rdx
0x18000e34e  mov     rax, r8
0x18000e351  sub     rcx, r8
0x18000e354  neg     rax
0x18000e357  sbb     r9, r9
0x18000e35a  and     r9, rcx
0x18000e35d  test    r8, r8
0x18000e360  jz      short loc_18000E3A9
0x18000e362  lea     rax, [rsp+278h+Name]
0x18000e367  lea     rax, [rax+r9*2]
0x18000e36b  lea     rcx, aP0; "_p0"
0x18000e372  sub     rdx, r9
0x18000e375  jz      short loc_18000E39A
0x18000e377  test    r10, r10
0x18000e37a  jz      short loc_18000E39A
0x18000e37c  movzx   r8d, word ptr [rcx]
0x18000e380  test    r8w, r8w
0x18000e384  jz      short loc_18000E39A
0x18000e386  mov     [rax], r8w
0x18000e38a  add     rcx, 2
0x18000e38e  add     rax, 2
0x18000e392  sub     r10, rbx
0x18000e395  sub     rdx, rbx
0x18000e398  jnz     short loc_18000E377
0x18000e39a  test    rdx, rdx
0x18000e39d  lea     rcx, [rax-2]
0x18000e3a1  cmovnz  rcx, rax
0x18000e3a5  mov     [rcx], r14w
0x18000e3a9  mov     edx, esi
0x18000e3ab  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000e3b3  and     edx, 7FFFFFFFh; lInitialCount
0x18000e3b9  mov     [rsp+278h+dwFlags], r14d; int
0x18000e3be  mov     r8d, ebx
0x18000e3c1  lea     r9, [rsp+278h+Name]; lpName
0x18000e3c6  cmova   r8d, edx; lMaximumCount
0x18000e3ca  xor     ecx, ecx; lpSemaphoreAttributes
0x18000e3cc  call    cs:__imp_CreateSemaphoreExW
0x18000e3d2  mov     rdi, rax
0x18000e3d5  test    rax, rax
0x18000e3d8  jnz     short loc_18000E405
0x18000e3da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e3df  mov     edi, eax
0x18000e3e1  test    eax, eax
0x18000e3e3  jns     short loc_18000E416
0x18000e3e5  mov     rcx, [rsp+278h]; this
0x18000e3ed  lea     r8, aWil; "wil"
0x18000e3f4  mov     r9d, eax; char *
0x18000e3f7  mov     edx, 8Bh; void *
0x18000e3fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e401  mov     eax, edi
0x18000e403  jmp     short loc_18000E46B
0x18000e405  call    cs:__imp_GetLastError
0x18000e40b  mov     rdx, rdi
0x18000e40e  mov     rcx, rbp
0x18000e411  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e416  lea     r8, asc_180043ED8; "h"
0x18000e41d  shr     rsi, 1Fh
0x18000e421  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000e426  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e42b  test    esi, esi
0x18000e42d  lea     rcx, [rbp+8]
0x18000e431  lea     r9, [rsp+278h+Name]
0x18000e436  mov     edx, esi
0x18000e438  cmovnz  ebx, esi
0x18000e43b  mov     r8d, ebx
0x18000e43e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e443  mov     ebx, eax
0x18000e445  test    eax, eax
0x18000e447  jns     short loc_18000E469
0x18000e449  mov     rcx, [rsp+278h]; this
0x18000e451  lea     r8, aWil; "wil"
0x18000e458  mov     r9d, eax; char *
0x18000e45b  mov     edx, 90h; void *
0x18000e460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e465  mov     eax, ebx
0x18000e467  jmp     short loc_18000E46B
0x18000e469  xor     eax, eax
0x18000e46b  mov     rcx, [rsp+278h+var_28]
0x18000e473  xor     rcx, rsp; StackCookie
0x18000e476  call    __security_check_cookie
0x18000e47b  lea     r11, [rsp+278h+var_18]
0x18000e483  mov     rbx, [r11+28h]
0x18000e487  mov     rbp, [r11+30h]
0x18000e48b  mov     rsp, r11
0x18000e48e  pop     r14
0x18000e490  pop     rdi
0x18000e491  pop     rsi
0x18000e492  retn
```

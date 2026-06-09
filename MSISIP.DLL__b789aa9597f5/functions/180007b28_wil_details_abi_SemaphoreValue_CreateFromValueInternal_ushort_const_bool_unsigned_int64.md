# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007b28`
- end: `0x180007c89`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `353`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000983c`
- `0x180009990`

## callees

- `0x180007224`
- `0x180007254`
- `0x180007ad0`
- `0x180007b28`
- `0x180007c90`
- `0x180007cb8`
- `0x180007e2c`
- `0x180009aec`
- `0x18000d300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007bec`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c1e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  __int64 v6; // r11
  wchar_t *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // edi
  __int64 v10; // r8
  LONG v11; // r8d
  wil::details *v12; // rcx
  HANDLE Semaphore; // rbx
  unsigned __int64 v14; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v16; // r8d
  __int64 v17; // rdx
  unsigned __int64 v19; // rsi
  size_t dwFlags; // [rsp+20h] [rbp-268h]
  size_t dwFlagsa; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-268h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, dwFlags);
  v7 = pszDest;
  v8 = (unsigned int)v6;
  v9 = 1;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  if ( v8 )
  {
    v10 = (v6 - v8) & -(__int64)(v8 != 0);
    StringCopyWorkerW(&pszDest[v10], v6 - v10, (size_t *)v10, L"_p0", dwFlagsa);
  }
  v11 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v11 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v11, pszDest, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    if ( LastErrorFailHr < 0 )
    {
      v17 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlagsb);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v19 = a4 >> 31;
  StringCchCatW(pszDest, v14, L"h");
  if ( (_DWORD)v19 )
    v9 = v19;
  LastErrorFailHr = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                      (char *)this + 8,
                      (unsigned int)v19,
                      v9,
                      pszDest);
  if ( LastErrorFailHr < 0 )
  {
    v17 = 144;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x180007b28  push    rbx
0x180007b2a  push    rbp
0x180007b2b  push    rsi
0x180007b2c  push    rdi
0x180007b2d  push    r14
0x180007b2f  sub     rsp, 260h
0x180007b36  mov     rax, cs:__security_cookie
0x180007b3d  xor     rax, rsp
0x180007b40  mov     [rsp+288h+var_38], rax
0x180007b48  mov     rax, 0C000000000000000h
0x180007b52  mov     rsi, r9
0x180007b55  mov     rbp, rcx
0x180007b58  test    rax, r9
0x180007b5b  jz      short loc_180007B63
0x180007b5d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007b63  mov     r9, rdx; pszSrc
0x180007b66  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180007b6b  mov     r11d, 104h
0x180007b71  mov     edx, r11d; cchDest
0x180007b74  call    StringCopyWorkerW
0x180007b79  xor     r14d, r14d
0x180007b7c  lea     rax, [rsp+288h+pszDest]
0x180007b81  mov     edx, r11d
0x180007b84  lea     edi, [r14+1]
0x180007b88  cmp     [rax], r14w
0x180007b8c  jz      short loc_180007B97
0x180007b8e  add     rax, 2
0x180007b92  sub     rdx, rdi
0x180007b95  jnz     short loc_180007B88
0x180007b97  mov     rcx, r11
0x180007b9a  mov     rax, rdx
0x180007b9d  sub     rcx, rdx
0x180007ba0  neg     rax
0x180007ba3  sbb     r8, r8
0x180007ba6  and     r8, rcx; pcchNewDestLength
0x180007ba9  test    rdx, rdx
0x180007bac  jz      short loc_180007BC9
0x180007bae  sub     r11, r8
0x180007bb1  lea     rcx, [rsp+288h+pszDest]
0x180007bb6  lea     rcx, [rcx+r8*2]; pszDest
0x180007bba  mov     rdx, r11; cchDest
0x180007bbd  lea     r9, aP0; "_p0"
0x180007bc4  call    StringCopyWorkerW
0x180007bc9  mov     edx, esi
0x180007bcb  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007bd3  and     edx, 7FFFFFFFh; lInitialCount
0x180007bd9  mov     dword ptr [rsp+288h+dwFlags], r14d; int
0x180007bde  mov     r8d, edi
0x180007be1  lea     r9, [rsp+288h+pszDest]; lpName
0x180007be6  cmova   r8d, edx; lMaximumCount
0x180007bea  xor     ecx, ecx; lpSemaphoreAttributes
0x180007bec  call    cs:__imp_CreateSemaphoreExW
0x180007bf2  mov     rbx, rax
0x180007bf5  test    rax, rax
0x180007bf8  jnz     short loc_180007C1E
0x180007bfa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007bff  mov     ebx, eax
0x180007c01  test    eax, eax
0x180007c03  jns     short loc_180007C2F
0x180007c05  mov     edx, 8Bh; void *
0x180007c0a  mov     rcx, [rsp+288h]; this
0x180007c12  mov     r9d, ebx; char *
0x180007c15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c1a  mov     eax, ebx
0x180007c1c  jmp     short loc_180007C6B
0x180007c1e  call    cs:__imp_GetLastError
0x180007c24  mov     rdx, rbx
0x180007c27  mov     rcx, rbp
0x180007c2a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007c2f  lea     r8, asc_18000FA98; "h"
0x180007c36  shr     rsi, 1Fh
0x180007c3a  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x180007c3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007c44  test    esi, esi
0x180007c46  lea     rcx, [rbp+8]
0x180007c4a  lea     r9, [rsp+288h+pszDest]
0x180007c4f  mov     edx, esi
0x180007c51  cmovnz  edi, esi
0x180007c54  mov     r8d, edi
0x180007c57  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180007c5c  mov     ebx, eax
0x180007c5e  test    eax, eax
0x180007c60  jns     short loc_180007C69
0x180007c62  mov     edx, 90h
0x180007c67  jmp     short loc_180007C0A
0x180007c69  xor     eax, eax
0x180007c6b  mov     rcx, [rsp+288h+var_38]
0x180007c73  xor     rcx, rsp; StackCookie
0x180007c76  call    __security_check_cookie
0x180007c7b  add     rsp, 260h
0x180007c82  pop     r14
0x180007c84  pop     rdi
0x180007c85  pop     rsi
0x180007c86  pop     rbp
0x180007c87  pop     rbx
0x180007c88  retn
```

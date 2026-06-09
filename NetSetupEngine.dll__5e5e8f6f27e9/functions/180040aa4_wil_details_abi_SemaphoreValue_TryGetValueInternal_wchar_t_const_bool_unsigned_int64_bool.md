# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180040aa4`
- end: `0x180040cd8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `564`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004b134`
- `0x18004b200`

## callees

- `0x180040aa4`
- `0x180040ce0`
- `0x180040e4c`
- `0x18004b3e0`
- `0x18004b410`
- `0x18004b460`
- `0x1800580a8`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040b43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040be6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040b43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c7c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v5; // rax
  __int64 v6; // r11
  __int64 v7; // r8
  wil::details *v8; // rax
  wil::details *v9; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v11; // r8d
  unsigned int LastError; // ebx
  __int64 v13; // rdx
  wchar_t *v14; // rax
  __int64 v15; // r8
  wil::details *v16; // rax
  const char *v17; // r9
  wil::details *v18; // rbx
  int v19; // eax
  void *v20; // rdx
  unsigned int v21; // r8d
  int v22; // esi
  void *v23; // rdx
  const char *v25; // r9
  size_t v26; // [rsp+20h] [rbp-E0h]
  size_t v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v30; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v31; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v26);
  v5 = pszDest;
  v6 = 260;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  if ( v6 )
  {
    v7 = (260 - v6) & -(__int64)(v6 != 0);
    StringCopyWorkerW(&pszDest[v7], 260 - v7, (size_t *)v7, L"_p0", v27);
  }
  v8 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v31 = v8;
  v9 = v8;
  if ( v8 )
  {
    v29 = 0;
    v28 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v8, &v29);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      v13 = 260;
      v14 = pszDest;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      if ( v13 )
      {
        v15 = (260 - v13) & -(__int64)(v13 != 0);
        StringCopyWorkerW(&pszDest[v15], 260 - v15, (size_t *)v15, L"h", v27);
      }
      v16 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
      v30 = v16;
      v18 = v16;
      if ( v16 )
      {
        v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v28);
        v22 = v19;
        if ( v19 >= 0 )
        {
          wil::details::CloseHandle(v18, v20);
          *a3 = v29 | (unsigned __int64)((__int64)v28 << 31);
          wil::details::CloseHandle(v9, v23);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v21, (const char *)(unsigned int)v19, v27);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
        LastError = v22;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore, v27);
    }
  }
  else if ( GetLastError() == 2 )
  {
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
  return LastError;
}

```

## disassembly

```asm
0x180040aa4  mov     [rsp-8+arg_8], rbx
0x180040aa9  push    rbp
0x180040aaa  push    rsi
0x180040aab  push    rdi
0x180040aac  push    r14
0x180040aae  push    r15
0x180040ab0  lea     rbp, [rsp-170h]
0x180040ab8  sub     rsp, 270h
0x180040abf  mov     rax, cs:__security_cookie
0x180040ac6  xor     rax, rsp
0x180040ac9  mov     [rbp+190h+var_30], rax
0x180040ad0  xor     r15d, r15d
0x180040ad3  mov     r9, rcx; pszSrc
0x180040ad6  mov     esi, 104h
0x180040adb  mov     [r8], r15
0x180040ade  mov     edx, esi; cchDest
0x180040ae0  lea     rcx, [rsp+290h+pszDest]; pszDest
0x180040ae5  mov     r14, r8
0x180040ae8  call    StringCopyWorkerW
0x180040aed  lea     rax, [rsp+290h+pszDest]
0x180040af2  mov     r11d, esi
0x180040af5  cmp     [rax], r15w
0x180040af9  jz      short loc_180040B05
0x180040afb  add     rax, 2
0x180040aff  sub     r11, 1
0x180040b03  jnz     short loc_180040AF5
0x180040b05  mov     rcx, rsi
0x180040b08  mov     rax, r11
0x180040b0b  sub     rcx, r11
0x180040b0e  neg     rax
0x180040b11  sbb     r8, r8
0x180040b14  and     r8, rcx; pcchNewDestLength
0x180040b17  test    r11, r11
0x180040b1a  jz      short loc_180040B37
0x180040b1c  mov     rdx, rsi
0x180040b1f  lea     rcx, [rsp+290h+pszDest]
0x180040b24  sub     rdx, r8; cchDest
0x180040b27  lea     rcx, [rcx+r8*2]; pszDest
0x180040b2b  lea     r9, aP0; "_p0"
0x180040b32  call    StringCopyWorkerW
0x180040b37  lea     r8, [rsp+290h+pszDest]; lpName
0x180040b3c  xor     edx, edx; bInheritHandle
0x180040b3e  mov     ecx, 1F0003h; dwDesiredAccess
0x180040b43  call    cs:__imp_OpenSemaphoreW
0x180040b49  mov     [rsp+290h+var_250], rax
0x180040b4e  mov     rdi, rax
0x180040b51  test    rax, rax
0x180040b54  jz      loc_180040C7C
0x180040b5a  lea     rdx, [rsp+290h+var_25C]; int *
0x180040b5f  mov     [rsp+290h+var_25C], r15d
0x180040b64  mov     rcx, rax; hHandle
0x180040b67  mov     [rsp+290h+var_260], r15d
0x180040b6c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180040b71  mov     ebx, eax
0x180040b73  test    eax, eax
0x180040b75  jns     short loc_180040B90
0x180040b77  mov     rcx, [rbp+198h]; this
0x180040b7e  mov     r9d, eax; char *
0x180040b81  mov     edx, 0D6h; void *
0x180040b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040b8b  jmp     loc_180040CA6
0x180040b90  mov     rdx, rsi
0x180040b93  lea     rax, [rsp+290h+pszDest]
0x180040b98  cmp     [rax], r15w
0x180040b9c  jz      short loc_180040BA8
0x180040b9e  add     rax, 2
0x180040ba2  sub     rdx, 1
0x180040ba6  jnz     short loc_180040B98
0x180040ba8  mov     rcx, rsi
0x180040bab  mov     rax, rdx
0x180040bae  sub     rcx, rdx
0x180040bb1  neg     rax
0x180040bb4  sbb     r8, r8
0x180040bb7  and     r8, rcx; pcchNewDestLength
0x180040bba  test    rdx, rdx
0x180040bbd  jz      short loc_180040BDA
0x180040bbf  sub     rsi, r8
0x180040bc2  lea     rcx, [rsp+290h+pszDest]
0x180040bc7  lea     rcx, [rcx+r8*2]; pszDest
0x180040bcb  mov     rdx, rsi; cchDest
0x180040bce  lea     r9, asc_1800A3160; "h"
0x180040bd5  call    StringCopyWorkerW
0x180040bda  lea     r8, [rsp+290h+pszDest]; lpName
0x180040bdf  xor     edx, edx; bInheritHandle
0x180040be1  mov     ecx, 1F0003h; dwDesiredAccess
0x180040be6  call    cs:__imp_OpenSemaphoreW
0x180040bec  mov     [rsp+290h+var_258], rax
0x180040bf1  mov     rbx, rax
0x180040bf4  test    rax, rax
0x180040bf7  jz      short loc_180040C56
0x180040bf9  lea     rdx, [rsp+290h+var_260]; int *
0x180040bfe  mov     rcx, rax; hHandle
0x180040c01  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180040c06  mov     esi, eax
0x180040c08  test    eax, eax
0x180040c0a  jns     short loc_180040C2E
0x180040c0c  mov     rcx, [rbp+198h]; this
0x180040c13  mov     r9d, eax; char *
0x180040c16  mov     edx, 0DEh; void *
0x180040c1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040c20  lea     rcx, [rsp+290h+var_258]
0x180040c25  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040c2a  mov     ebx, esi
0x180040c2c  jmp     short loc_180040CA6
0x180040c2e  mov     rcx, rbx; this
0x180040c31  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180040c36  movsxd  rax, [rsp+290h+var_25C]
0x180040c3b  movsxd  rcx, [rsp+290h+var_260]
0x180040c40  shl     rcx, 1Fh
0x180040c44  or      rcx, rax
0x180040c47  mov     [r14], rcx
0x180040c4a  mov     rcx, rdi; this
0x180040c4d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180040c52  xor     eax, eax
0x180040c54  jmp     short loc_180040CB2
0x180040c56  mov     rcx, [rbp+198h]; this
0x180040c5d  lea     r8, aWil; "wil"
0x180040c64  mov     edx, 0DCh; void *
0x180040c69  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040c6e  lea     rcx, [rsp+290h+var_258]
0x180040c73  mov     ebx, eax
0x180040c75  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040c7a  jmp     short loc_180040CA6
0x180040c7c  call    cs:__imp_GetLastError
0x180040c82  cmp     eax, 2
0x180040c85  jnz     short loc_180040C8C
0x180040c87  mov     ebx, r15d
0x180040c8a  jmp     short loc_180040CA6
0x180040c8c  mov     rcx, [rbp+198h]; this
0x180040c93  lea     r8, aWil; "wil"
0x180040c9a  mov     edx, 0D0h; void *
0x180040c9f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040ca4  mov     ebx, eax
0x180040ca6  lea     rcx, [rsp+290h+var_250]
0x180040cab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040cb0  mov     eax, ebx
0x180040cb2  mov     rcx, [rbp+190h+var_30]
0x180040cb9  xor     rcx, rsp; StackCookie
0x180040cbc  call    __security_check_cookie
0x180040cc1  mov     rbx, [rsp+290h+arg_8]
0x180040cc9  add     rsp, 270h
0x180040cd0  pop     r15
0x180040cd2  pop     r14
0x180040cd4  pop     rdi
0x180040cd5  pop     rsi
0x180040cd6  pop     rbp
0x180040cd7  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003322c`
- end: `0x18003343c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `528`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180026ec8`
- `0x1800288d8`

## callees

- `0x180010da8`
- `0x18001d390`
- `0x18003322c`
- `0x180033444`
- `0x180033828`
- `0x180033864`
- `0x18003e920`
- `0x180041b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800332f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003335c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800332f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003335c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ee`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r9
  __int64 v7; // r10
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rax
  __int64 v11; // r9
  HANDLE v12; // rax
  int ValueFromSemaphore; // eax
  unsigned __int64 v14; // rdx
  unsigned int LastError; // ebx
  HANDLE v16; // rax
  const char *v17; // r9
  int v18; // eax
  const char *v20; // r9
  size_t v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  v9 = 260;
  if ( v5 )
    v8 = v4;
  v10 = Name;
  *v8 = 0;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
  {
    v11 = (260 - v9) & -(__int64)(v9 != 0);
    StringCopyWorkerW_1(&Name[v11], 260 - v11, (size_t *)v9, L"_p0", v21);
  }
  v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v25[0] = v12;
  if ( v12 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, v14, L"h");
      v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v24 = v16;
      if ( v16 )
      {
        v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v22);
        LastError = v18;
        if ( v18 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
          *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          v21);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v21);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v20);
}

```

## disassembly

```asm
0x18003322c  push    rbp
0x18003322e  push    rbx
0x18003322f  push    rsi
0x180033230  push    rdi
0x180033231  lea     rbp, [rsp-178h]
0x180033239  sub     rsp, 278h
0x180033240  mov     rax, cs:__security_cookie
0x180033247  xor     rax, rsp
0x18003324a  mov     [rbp+190h+var_30], rax
0x180033251  xor     esi, esi
0x180033253  lea     rax, [rsp+290h+Name]
0x180033258  mov     edx, 104h
0x18003325d  mov     [r8], rsi
0x180033260  mov     r9d, edx
0x180033263  mov     rdi, r8
0x180033266  mov     r10d, 7FFFFFFEh
0x18003326c  test    r10, r10
0x18003326f  jz      short loc_180033290
0x180033271  movzx   r8d, word ptr [rcx]
0x180033275  test    r8w, r8w
0x180033279  jz      short loc_180033290
0x18003327b  mov     [rax], r8w
0x18003327f  add     rcx, 2
0x180033283  add     rax, 2
0x180033287  dec     r10
0x18003328a  sub     r9, 1
0x18003328e  jnz     short loc_18003326C
0x180033290  lea     rcx, [rax-2]
0x180033294  test    r9, r9
0x180033297  mov     r8, rdx
0x18003329a  cmovnz  rcx, rax
0x18003329e  lea     rax, [rsp+290h+Name]
0x1800332a3  mov     [rcx], si
0x1800332a6  cmp     [rax], si
0x1800332a9  jz      short loc_1800332B5
0x1800332ab  add     rax, 2
0x1800332af  sub     r8, 1; pcchNewDestLength
0x1800332b3  jnz     short loc_1800332A6
0x1800332b5  mov     rcx, rdx
0x1800332b8  mov     rax, r8
0x1800332bb  sub     rcx, r8
0x1800332be  neg     rax
0x1800332c1  sbb     r9, r9
0x1800332c4  and     r9, rcx
0x1800332c7  test    r8, r8
0x1800332ca  jz      short loc_1800332E4
0x1800332cc  sub     rdx, r9; cchDest
0x1800332cf  lea     rcx, [rsp+290h+Name]
0x1800332d4  lea     rcx, [rcx+r9*2]; pszDest
0x1800332d8  lea     r9, aP0; "_p0"
0x1800332df  call    StringCopyWorkerW_1
0x1800332e4  lea     r8, [rsp+290h+Name]; lpName
0x1800332e9  xor     edx, edx; bInheritHandle
0x1800332eb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800332f0  call    cs:__imp_OpenSemaphoreW
0x1800332f6  mov     [rsp+290h+var_250], rax
0x1800332fb  test    rax, rax
0x1800332fe  jz      loc_1800333EE
0x180033304  lea     rdx, [rsp+290h+var_25C]; int *
0x180033309  mov     [rsp+290h+var_25C], esi
0x18003330d  mov     rcx, rax; hHandle
0x180033310  mov     [rsp+290h+var_260], esi
0x180033314  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180033319  mov     ebx, eax
0x18003331b  test    eax, eax
0x18003331d  jns     short loc_18003333F
0x18003331f  mov     rcx, [rbp+198h]; this
0x180033326  lea     r8, aWil; "wil"
0x18003332d  mov     r9d, eax; char *
0x180033330  mov     edx, 0D6h; void *
0x180033335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003333a  jmp     loc_1800333FB
0x18003333f  lea     r8, asc_18006E14C; "h"
0x180033346  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18003334b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033350  lea     r8, [rsp+290h+Name]; lpName
0x180033355  xor     edx, edx; bInheritHandle
0x180033357  mov     ecx, 1F0003h; dwDesiredAccess
0x18003335c  call    cs:__imp_OpenSemaphoreW
0x180033362  mov     [rsp+290h+var_258], rax
0x180033367  test    rax, rax
0x18003336a  jz      short loc_1800333C8
0x18003336c  lea     rdx, [rsp+290h+var_260]; int *
0x180033371  mov     rcx, rax; hHandle
0x180033374  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180033379  mov     ebx, eax
0x18003337b  test    eax, eax
0x18003337d  jns     short loc_18003339C
0x18003337f  mov     rcx, [rbp+198h]; this
0x180033386  lea     r8, aWil; "wil"
0x18003338d  mov     r9d, eax; char *
0x180033390  mov     edx, 0DEh; void *
0x180033395  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003339a  jmp     short loc_1800333E2
0x18003339c  lea     rcx, [rsp+290h+var_258]
0x1800333a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800333a6  movsxd  rax, [rsp+290h+var_25C]
0x1800333ab  movsxd  rcx, [rsp+290h+var_260]
0x1800333b0  shl     rcx, 1Fh
0x1800333b4  or      rcx, rax
0x1800333b7  mov     [rdi], rcx
0x1800333ba  lea     rcx, [rsp+290h+var_250]
0x1800333bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800333c4  xor     eax, eax
0x1800333c6  jmp     short loc_180033421
0x1800333c8  mov     rcx, [rbp+198h]; this
0x1800333cf  lea     r8, aWil; "wil"
0x1800333d6  mov     edx, 0DCh; void *
0x1800333db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800333e0  mov     ebx, eax
0x1800333e2  lea     rcx, [rsp+290h+var_258]
0x1800333e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800333ec  jmp     short loc_1800333FB
0x1800333ee  call    cs:__imp_GetLastError
0x1800333f4  cmp     eax, 2
0x1800333f7  jnz     short loc_180033409
0x1800333f9  mov     ebx, esi
0x1800333fb  lea     rcx, [rsp+290h+var_250]
0x180033400  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033405  mov     eax, ebx
0x180033407  jmp     short loc_180033421
0x180033409  mov     rcx, [rbp+198h]; this
0x180033410  lea     r8, aWil; "wil"
0x180033417  mov     edx, 0D0h; void *
0x18003341c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033421  mov     rcx, [rbp+190h+var_30]
0x180033428  xor     rcx, rsp; StackCookie
0x18003342b  call    __security_check_cookie
0x180033430  add     rsp, 278h
0x180033437  pop     rdi
0x180033438  pop     rsi
0x180033439  pop     rbx
0x18003343a  pop     rbp
0x18003343b  retn
```

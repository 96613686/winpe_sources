# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180012190`
- end: `0x1800123bc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180027c1c`

## callees

- `0x180012190`
- `0x1800123d0`
- `0x180012440`
- `0x180016e94`
- `0x180020110`
- `0x1800202bc`
- `0x1800238d0`
- `0x180026200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012261`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800122d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012261`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800122d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012362`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  bool v8; // zf
  WCHAR *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rax
  __int64 v12; // r8
  wil::details *v13; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  void *v16; // rdx
  wil::details *v17; // rax
  const char *v18; // r9
  int v19; // eax
  void *v20; // rdx
  void *v21; // rdx
  void *v22; // rdx
  const char *v24; // r9
  size_t v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  int v27; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v28; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v29[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

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
  v8 = v5 == 0;
  v9 = v4 - 1;
  v10 = 260;
  if ( !v8 )
    v9 = v4;
  v11 = Name;
  *v9 = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( v10 )
  {
    v12 = (260 - v10) & -(__int64)(v10 != 0);
    StringCopyWorkerW(&Name[v12], 260 - v12, (size_t *)v12, L"_p0", v25);
  }
  v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v29[0] = v13;
  if ( v13 )
  {
    v27 = 0;
    v26 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v27);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v17 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v28 = v17;
      if ( v17 )
      {
        v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v26);
        LastError = v19;
        if ( v19 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
            &v28,
            v20);
          *a3 = v27 | (unsigned __int64)((__int64)v26 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
            v29,
            v22);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v19,
          v25);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v28,
        v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v25);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      v29,
      v16);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v24);
}

```

## disassembly

```asm
0x180012190  mov     [rsp-8+arg_0], rbx
0x180012195  mov     [rsp-8+arg_8], rsi
0x18001219a  push    rbp
0x18001219b  push    rdi
0x18001219c  push    r14
0x18001219e  lea     rbp, [rsp-170h]
0x1800121a6  sub     rsp, 270h
0x1800121ad  mov     rax, cs:__security_cookie
0x1800121b4  xor     rax, rsp
0x1800121b7  mov     [rbp+180h+var_20], rax
0x1800121be  xor     esi, esi
0x1800121c0  lea     rax, [rsp+280h+Name]
0x1800121c5  mov     r14d, 104h
0x1800121cb  mov     [r8], rsi
0x1800121ce  mov     edx, r14d
0x1800121d1  mov     rdi, r8
0x1800121d4  mov     r9d, 7FFFFFFEh
0x1800121da  test    r9, r9
0x1800121dd  jz      short loc_1800121FE
0x1800121df  movzx   r8d, word ptr [rcx]
0x1800121e3  test    r8w, r8w
0x1800121e7  jz      short loc_1800121FE
0x1800121e9  mov     [rax], r8w
0x1800121ed  add     rcx, 2
0x1800121f1  add     rax, 2
0x1800121f5  dec     r9
0x1800121f8  sub     rdx, 1
0x1800121fc  jnz     short loc_1800121DA
0x1800121fe  test    rdx, rdx
0x180012201  lea     rcx, [rax-2]
0x180012205  mov     rdx, r14
0x180012208  cmovnz  rcx, rax
0x18001220c  lea     rax, [rsp+280h+Name]
0x180012211  mov     [rcx], si
0x180012214  cmp     [rax], si
0x180012217  jz      short loc_180012223
0x180012219  add     rax, 2
0x18001221d  sub     rdx, 1
0x180012221  jnz     short loc_180012214
0x180012223  mov     rcx, r14
0x180012226  mov     rax, rdx
0x180012229  sub     rcx, rdx
0x18001222c  neg     rax
0x18001222f  sbb     r8, r8
0x180012232  and     r8, rcx; pcchNewDestLength
0x180012235  test    rdx, rdx
0x180012238  jz      short loc_180012255
0x18001223a  mov     rdx, r14
0x18001223d  lea     rcx, [rsp+280h+Name]
0x180012242  sub     rdx, r8; cchDest
0x180012245  lea     rcx, [rcx+r8*2]; pszDest
0x180012249  lea     r9, aP0; "_p0"
0x180012250  call    StringCopyWorkerW
0x180012255  lea     r8, [rsp+280h+Name]; lpName
0x18001225a  xor     edx, edx; bInheritHandle
0x18001225c  mov     ecx, 1F0003h; dwDesiredAccess
0x180012261  call    cs:__imp_OpenSemaphoreW
0x180012267  mov     [rsp+280h+var_240], rax
0x18001226c  test    rax, rax
0x18001226f  jz      loc_180012362
0x180012275  lea     rdx, [rsp+280h+var_24C]; int *
0x18001227a  mov     [rsp+280h+var_24C], esi
0x18001227e  mov     rcx, rax; hHandle
0x180012281  mov     [rsp+280h+var_250], esi
0x180012285  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001228a  mov     ebx, eax
0x18001228c  test    eax, eax
0x18001228e  jns     short loc_1800122B0
0x180012290  mov     rcx, [rbp+188h]; this
0x180012297  lea     r8, aWil; "wil"
0x18001229e  mov     r9d, eax; char *
0x1800122a1  mov     edx, 0D6h; void *
0x1800122a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800122ab  jmp     loc_18001236F
0x1800122b0  lea     r8, asc_18003A140; "h"
0x1800122b7  mov     rdx, r14; unsigned __int64
0x1800122ba  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800122bf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800122c4  lea     r8, [rsp+280h+Name]; lpName
0x1800122c9  xor     edx, edx; bInheritHandle
0x1800122cb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800122d0  call    cs:__imp_OpenSemaphoreW
0x1800122d6  mov     [rsp+280h+var_248], rax
0x1800122db  test    rax, rax
0x1800122de  jz      short loc_18001233C
0x1800122e0  lea     rdx, [rsp+280h+var_250]; int *
0x1800122e5  mov     rcx, rax; hHandle
0x1800122e8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800122ed  mov     ebx, eax
0x1800122ef  test    eax, eax
0x1800122f1  jns     short loc_180012310
0x1800122f3  mov     rcx, [rbp+188h]; this
0x1800122fa  lea     r8, aWil; "wil"
0x180012301  mov     r9d, eax; char *
0x180012304  mov     edx, 0DEh; void *
0x180012309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001230e  jmp     short loc_180012356
0x180012310  lea     rcx, [rsp+280h+var_248]
0x180012315  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001231a  movsxd  rax, [rsp+280h+var_24C]
0x18001231f  movsxd  rcx, [rsp+280h+var_250]
0x180012324  shl     rcx, 1Fh
0x180012328  or      rcx, rax
0x18001232b  mov     [rdi], rcx
0x18001232e  lea     rcx, [rsp+280h+var_240]
0x180012333  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012338  xor     eax, eax
0x18001233a  jmp     short loc_180012395
0x18001233c  mov     rcx, [rbp+188h]; this
0x180012343  lea     r8, aWil; "wil"
0x18001234a  mov     edx, 0DCh; void *
0x18001234f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012354  mov     ebx, eax
0x180012356  lea     rcx, [rsp+280h+var_248]
0x18001235b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012360  jmp     short loc_18001236F
0x180012362  call    cs:__imp_GetLastError
0x180012368  cmp     eax, 2
0x18001236b  jnz     short loc_18001237D
0x18001236d  mov     ebx, esi
0x18001236f  lea     rcx, [rsp+280h+var_240]
0x180012374  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012379  mov     eax, ebx
0x18001237b  jmp     short loc_180012395
0x18001237d  mov     rcx, [rbp+188h]; this
0x180012384  lea     r8, aWil; "wil"
0x18001238b  mov     edx, 0D0h; void *
0x180012390  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012395  mov     rcx, [rbp+180h+var_20]
0x18001239c  xor     rcx, rsp; StackCookie
0x18001239f  call    __security_check_cookie
0x1800123a4  lea     r11, [rsp+280h+var_10]
0x1800123ac  mov     rbx, [r11+20h]
0x1800123b0  mov     rsi, [r11+28h]
0x1800123b4  mov     rsp, r11
0x1800123b7  pop     r14
0x1800123b9  pop     rdi
0x1800123ba  pop     rbp
0x1800123bb  retn
```

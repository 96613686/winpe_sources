# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001c0f8`
- end: `0x18001c3ce`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `726`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001b668`
- `0x18001b6ec`

## callees

- `0x18001b4e0`
- `0x18001b628`
- `0x18001c0f8`
- `0x18003f6ac`
- `0x18003fbc0`
- `0x180040270`
- `0x180043c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001c204`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001c2d8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001c204`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001c2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c37c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rbx
  int ValueFromSemaphore; // eax
  unsigned int v22; // esi
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rdi
  WCHAR *v29; // rdx
  HANDLE v30; // rax
  const char *v31; // r9
  int v32; // eax
  void *v34; // rdx
  unsigned int LastError; // edi
  void *v36; // rdx
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h] BYREF
  int v39; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v40; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v41; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v41 = v19;
  v20 = v19;
  if ( v19 )
  {
    v39 = 0;
    v38 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v39);
    v22 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v38);
LABEL_35:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
      return v22;
    }
    v23 = 260;
    v24 = Name;
    do
    {
      if ( !*v24 )
        break;
      ++v24;
      --v23;
    }
    while ( v23 );
    v25 = (260 - v23) & -(__int64)(v23 != 0);
    if ( v23 )
    {
      v26 = &Name[v25];
      v27 = L"h";
      v28 = 260 - v25;
      if ( 260 != v25 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v27 )
            break;
          *v26++ = *v27++;
          --v5;
          --v28;
        }
        while ( v28 );
      }
      v29 = v26 - 1;
      if ( v28 )
        v29 = v26;
      *v29 = 0;
    }
    v30 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v40 = v30;
    if ( !v30 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
      wil::details::CloseHandle(v20, v36);
      return LastError;
    }
    v32 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v38);
    v22 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v32,
        v38);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v40);
      goto LABEL_35;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v40);
    *a3 = v39 | (unsigned __int64)((__int64)v38 << 31);
    wil::details::CloseHandle(v20, v34);
    return 0;
  }
  if ( GetLastError() == 2 )
    return 0;
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v37);
}

```

## disassembly

```asm
0x18001c0f8  mov     [rsp-8+arg_0], rbx
0x18001c0fd  mov     [rsp-8+arg_8], rsi
0x18001c102  push    rbp
0x18001c103  push    rdi
0x18001c104  push    r12
0x18001c106  push    r14
0x18001c108  push    r15
0x18001c10a  lea     rbp, [rsp-160h]
0x18001c112  sub     rsp, 260h
0x18001c119  mov     rax, cs:__security_cookie
0x18001c120  xor     rax, rsp
0x18001c123  mov     [rbp+180h+var_30], rax
0x18001c12a  xor     r12d, r12d
0x18001c12d  lea     rax, [rsp+280h+Name]
0x18001c132  mov     r14d, 7FFFFFFEh
0x18001c138  mov     [r8], r12
0x18001c13b  mov     edi, 104h
0x18001c140  mov     r9d, r14d
0x18001c143  mov     edx, edi
0x18001c145  mov     r15, r8
0x18001c148  test    r9, r9
0x18001c14b  jz      short loc_18001C16C
0x18001c14d  movzx   r8d, word ptr [rcx]
0x18001c151  test    r8w, r8w
0x18001c155  jz      short loc_18001C16C
0x18001c157  mov     [rax], r8w
0x18001c15b  add     rcx, 2
0x18001c15f  add     rax, 2
0x18001c163  dec     r9
0x18001c166  sub     rdx, 1
0x18001c16a  jnz     short loc_18001C148
0x18001c16c  test    rdx, rdx
0x18001c16f  lea     rcx, [rax-2]
0x18001c173  mov     rdx, rdi
0x18001c176  cmovnz  rcx, rax
0x18001c17a  lea     rax, [rsp+280h+Name]
0x18001c17f  mov     [rcx], r12w
0x18001c183  cmp     [rax], r12w
0x18001c187  jz      short loc_18001C193
0x18001c189  add     rax, 2
0x18001c18d  sub     rdx, 1
0x18001c191  jnz     short loc_18001C183
0x18001c193  mov     rcx, rdi
0x18001c196  mov     rax, rdx
0x18001c199  sub     rcx, rdx
0x18001c19c  neg     rax
0x18001c19f  sbb     r8, r8
0x18001c1a2  and     r8, rcx
0x18001c1a5  test    rdx, rdx
0x18001c1a8  jz      short loc_18001C1F8
0x18001c1aa  mov     rax, rdi
0x18001c1ad  lea     rdx, [rsp+280h+Name]
0x18001c1b2  lea     r9, aP0; "_p0"
0x18001c1b9  mov     rcx, r14
0x18001c1bc  lea     rdx, [rdx+r8*2]
0x18001c1c0  sub     rax, r8
0x18001c1c3  jz      short loc_18001C1E9
0x18001c1c5  test    rcx, rcx
0x18001c1c8  jz      short loc_18001C1E9
0x18001c1ca  movzx   r8d, word ptr [r9]
0x18001c1ce  test    r8w, r8w
0x18001c1d2  jz      short loc_18001C1E9
0x18001c1d4  mov     [rdx], r8w
0x18001c1d8  add     r9, 2
0x18001c1dc  add     rdx, 2
0x18001c1e0  dec     rcx
0x18001c1e3  sub     rax, 1
0x18001c1e7  jnz     short loc_18001C1C5
0x18001c1e9  test    rax, rax
0x18001c1ec  lea     rcx, [rdx-2]
0x18001c1f0  cmovnz  rcx, rdx
0x18001c1f4  mov     [rcx], r12w
0x18001c1f8  lea     r8, [rsp+280h+Name]; lpName
0x18001c1fd  xor     edx, edx; bInheritHandle
0x18001c1ff  mov     ecx, 1F0003h; dwDesiredAccess
0x18001c204  call    cs:__imp_OpenSemaphoreW
0x18001c20a  mov     [rsp+280h+var_250], rax
0x18001c20f  mov     rbx, rax
0x18001c212  test    rax, rax
0x18001c215  jz      loc_18001C37C
0x18001c21b  lea     rdx, [rsp+280h+var_25C]; int *
0x18001c220  mov     [rsp+280h+var_25C], r12d
0x18001c225  mov     rcx, rax; hHandle
0x18001c228  mov     [rsp+280h+var_260], r12d; int
0x18001c22d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001c232  mov     esi, eax
0x18001c234  test    eax, eax
0x18001c236  jns     short loc_18001C258
0x18001c238  mov     rcx, [rbp+188h]; this
0x18001c23f  lea     r8, aWil; "wil"
0x18001c246  mov     r9d, eax; char *
0x18001c249  mov     edx, 0D6h; void *
0x18001c24e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c253  jmp     loc_18001C320
0x18001c258  mov     rdx, rdi
0x18001c25b  lea     rax, [rsp+280h+Name]
0x18001c260  cmp     [rax], r12w
0x18001c264  jz      short loc_18001C270
0x18001c266  add     rax, 2
0x18001c26a  sub     rdx, 1
0x18001c26e  jnz     short loc_18001C260
0x18001c270  mov     rcx, rdi
0x18001c273  mov     rax, rdx
0x18001c276  sub     rcx, rdx
0x18001c279  neg     rax
0x18001c27c  sbb     r8, r8
0x18001c27f  and     r8, rcx
0x18001c282  test    rdx, rdx
0x18001c285  jz      short loc_18001C2CC
0x18001c287  lea     rax, [rsp+280h+Name]
0x18001c28c  lea     rax, [rax+r8*2]
0x18001c290  lea     rcx, asc_180079780; "h"
0x18001c297  sub     rdi, r8
0x18001c29a  jz      short loc_18001C2BD
0x18001c29c  test    r14, r14
0x18001c29f  jz      short loc_18001C2BD
0x18001c2a1  movzx   edx, word ptr [rcx]
0x18001c2a4  test    dx, dx
0x18001c2a7  jz      short loc_18001C2BD
0x18001c2a9  mov     [rax], dx
0x18001c2ac  add     rcx, 2
0x18001c2b0  add     rax, 2
0x18001c2b4  dec     r14
0x18001c2b7  sub     rdi, 1
0x18001c2bb  jnz     short loc_18001C29C
0x18001c2bd  test    rdi, rdi
0x18001c2c0  lea     rdx, [rax-2]
0x18001c2c4  cmovnz  rdx, rax
0x18001c2c8  mov     [rdx], r12w
0x18001c2cc  lea     r8, [rsp+280h+Name]; lpName
0x18001c2d1  xor     edx, edx; bInheritHandle
0x18001c2d3  mov     ecx, 1F0003h; dwDesiredAccess
0x18001c2d8  call    cs:__imp_OpenSemaphoreW
0x18001c2de  mov     [rsp+280h+var_258], rax
0x18001c2e3  test    rax, rax
0x18001c2e6  jz      short loc_18001C356
0x18001c2e8  lea     rdx, [rsp+280h+var_260]; int *
0x18001c2ed  mov     rcx, rax; hHandle
0x18001c2f0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001c2f5  mov     esi, eax
0x18001c2f7  test    eax, eax
0x18001c2f9  jns     short loc_18001C32E
0x18001c2fb  mov     rcx, [rbp+188h]; this
0x18001c302  lea     r8, aWil; "wil"
0x18001c309  mov     r9d, eax; char *
0x18001c30c  mov     edx, 0DEh; void *
0x18001c311  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c316  lea     rcx, [rsp+280h+var_258]
0x18001c31b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c320  lea     rcx, [rsp+280h+var_250]
0x18001c325  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c32a  mov     eax, esi
0x18001c32c  jmp     short loc_18001C3A3
0x18001c32e  lea     rcx, [rsp+280h+var_258]
0x18001c333  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c338  movsxd  rax, [rsp+280h+var_25C]
0x18001c33d  movsxd  rcx, [rsp+280h+var_260]
0x18001c342  shl     rcx, 1Fh
0x18001c346  or      rcx, rax
0x18001c349  mov     [r15], rcx
0x18001c34c  mov     rcx, rbx; this
0x18001c34f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001c354  jmp     short loc_18001C387
0x18001c356  mov     rcx, [rbp+188h]; this
0x18001c35d  lea     r8, aWil; "wil"
0x18001c364  mov     edx, 0DCh; void *
0x18001c369  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c36e  mov     rcx, rbx; this
0x18001c371  mov     edi, eax
0x18001c373  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001c378  mov     eax, edi
0x18001c37a  jmp     short loc_18001C3A3
0x18001c37c  call    cs:__imp_GetLastError
0x18001c382  cmp     eax, 2
0x18001c385  jnz     short loc_18001C38B
0x18001c387  xor     eax, eax
0x18001c389  jmp     short loc_18001C3A3
0x18001c38b  mov     rcx, [rbp+188h]; this
0x18001c392  lea     r8, aWil; "wil"
0x18001c399  mov     edx, 0D0h; void *
0x18001c39e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c3a3  mov     rcx, [rbp+180h+var_30]
0x18001c3aa  xor     rcx, rsp; StackCookie
0x18001c3ad  call    __security_check_cookie
0x18001c3b2  lea     r11, [rsp+280h+var_20]
0x18001c3ba  mov     rbx, [r11+30h]
0x18001c3be  mov     rsi, [r11+38h]
0x18001c3c2  mov     rsp, r11
0x18001c3c5  pop     r15
0x18001c3c7  pop     r14
0x18001c3c9  pop     r12
0x18001c3cb  pop     rdi
0x18001c3cc  pop     rbp
0x18001c3cd  retn
```

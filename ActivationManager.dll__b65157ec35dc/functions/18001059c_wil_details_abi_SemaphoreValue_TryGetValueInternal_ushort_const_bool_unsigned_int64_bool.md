# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001059c`
- end: `0x180010876`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `730`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000ffe8`
- `0x18004f49c`

## callees

- `0x18000b5c0`
- `0x18000dffc`
- `0x18001059c`
- `0x18001087c`
- `0x1800109d4`
- `0x180044408`
- `0x18005ae90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800106a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001077c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800106a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001077c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010817`

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
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rsi
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  int v33; // eax
  void *v34; // rdx
  int v35; // esi
  void *v36; // rdx
  void *v38; // rdx
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v43; // [rsp+30h] [rbp-D0h] BYREF
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
  v43 = v19;
  v20 = v19;
  if ( v19 )
  {
    v41 = 0;
    v40 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
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
      v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v42 = v30;
      v32 = v30;
      if ( !v30 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
        wil::details::CloseHandle(v20, v38);
        return LastError;
      }
      v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v40);
      v35 = v33;
      if ( v33 >= 0 )
      {
        wil::details::CloseHandle(v32, v34);
        *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
        wil::details::CloseHandle(v20, v36);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v33,
        v40);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
      LastError = v35;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v40);
    }
LABEL_39:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
    return LastError;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
    goto LABEL_39;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
}

```

## disassembly

```asm
0x18001059c  mov     [rsp-8+arg_0], rbx
0x1800105a1  mov     [rsp-8+arg_8], rsi
0x1800105a6  push    rbp
0x1800105a7  push    rdi
0x1800105a8  push    r12
0x1800105aa  push    r14
0x1800105ac  push    r15
0x1800105ae  lea     rbp, [rsp-160h]
0x1800105b6  sub     rsp, 260h
0x1800105bd  mov     rax, cs:__security_cookie
0x1800105c4  xor     rax, rsp
0x1800105c7  mov     [rbp+180h+var_30], rax
0x1800105ce  xor     r12d, r12d
0x1800105d1  lea     rax, [rsp+280h+Name]
0x1800105d6  mov     r14d, 7FFFFFFEh
0x1800105dc  mov     [r8], r12
0x1800105df  mov     esi, 104h
0x1800105e4  mov     r9d, r14d
0x1800105e7  mov     edx, esi
0x1800105e9  mov     r15, r8
0x1800105ec  test    r9, r9
0x1800105ef  jz      short loc_180010610
0x1800105f1  movzx   r8d, word ptr [rcx]
0x1800105f5  test    r8w, r8w
0x1800105f9  jz      short loc_180010610
0x1800105fb  mov     [rax], r8w
0x1800105ff  add     rcx, 2
0x180010603  add     rax, 2
0x180010607  dec     r9
0x18001060a  sub     rdx, 1
0x18001060e  jnz     short loc_1800105EC
0x180010610  test    rdx, rdx
0x180010613  lea     rcx, [rax-2]
0x180010617  mov     rdx, rsi
0x18001061a  cmovnz  rcx, rax
0x18001061e  lea     rax, [rsp+280h+Name]
0x180010623  mov     [rcx], r12w
0x180010627  cmp     [rax], r12w
0x18001062b  jz      short loc_180010637
0x18001062d  add     rax, 2
0x180010631  sub     rdx, 1
0x180010635  jnz     short loc_180010627
0x180010637  mov     rcx, rsi
0x18001063a  mov     rax, rdx
0x18001063d  sub     rcx, rdx
0x180010640  neg     rax
0x180010643  sbb     r8, r8
0x180010646  and     r8, rcx
0x180010649  test    rdx, rdx
0x18001064c  jz      short loc_18001069C
0x18001064e  mov     rax, rsi
0x180010651  lea     rdx, [rsp+280h+Name]
0x180010656  lea     r9, aP0; "_p0"
0x18001065d  mov     rcx, r14
0x180010660  lea     rdx, [rdx+r8*2]
0x180010664  sub     rax, r8
0x180010667  jz      short loc_18001068D
0x180010669  test    rcx, rcx
0x18001066c  jz      short loc_18001068D
0x18001066e  movzx   r8d, word ptr [r9]
0x180010672  test    r8w, r8w
0x180010676  jz      short loc_18001068D
0x180010678  mov     [rdx], r8w
0x18001067c  add     r9, 2
0x180010680  add     rdx, 2
0x180010684  dec     rcx
0x180010687  sub     rax, 1
0x18001068b  jnz     short loc_180010669
0x18001068d  test    rax, rax
0x180010690  lea     rcx, [rdx-2]
0x180010694  cmovnz  rcx, rdx
0x180010698  mov     [rcx], r12w
0x18001069c  lea     r8, [rsp+280h+Name]; lpName
0x1800106a1  xor     edx, edx; bInheritHandle
0x1800106a3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800106a8  call    cs:__imp_OpenSemaphoreW
0x1800106ae  mov     [rsp+280h+var_250], rax
0x1800106b3  mov     rdi, rax
0x1800106b6  test    rax, rax
0x1800106b9  jz      loc_180010817
0x1800106bf  lea     rdx, [rsp+280h+var_25C]; int *
0x1800106c4  mov     [rsp+280h+var_25C], r12d
0x1800106c9  mov     rcx, rax; hHandle
0x1800106cc  mov     [rsp+280h+var_260], r12d; int
0x1800106d1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800106d6  mov     ebx, eax
0x1800106d8  test    eax, eax
0x1800106da  jns     short loc_1800106FC
0x1800106dc  mov     rcx, [rbp+188h]; this
0x1800106e3  lea     r8, aWil; "wil"
0x1800106ea  mov     r9d, eax; char *
0x1800106ed  mov     edx, 0D6h; void *
0x1800106f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106f7  jmp     loc_180010825
0x1800106fc  mov     rdx, rsi
0x1800106ff  lea     rax, [rsp+280h+Name]
0x180010704  cmp     [rax], r12w
0x180010708  jz      short loc_180010714
0x18001070a  add     rax, 2
0x18001070e  sub     rdx, 1
0x180010712  jnz     short loc_180010704
0x180010714  mov     rcx, rsi
0x180010717  mov     rax, rdx
0x18001071a  sub     rcx, rdx
0x18001071d  neg     rax
0x180010720  sbb     r8, r8
0x180010723  and     r8, rcx
0x180010726  test    rdx, rdx
0x180010729  jz      short loc_180010770
0x18001072b  lea     rax, [rsp+280h+Name]
0x180010730  lea     rax, [rax+r8*2]
0x180010734  lea     rcx, asc_1800AB2C0; "h"
0x18001073b  sub     rsi, r8
0x18001073e  jz      short loc_180010761
0x180010740  test    r14, r14
0x180010743  jz      short loc_180010761
0x180010745  movzx   edx, word ptr [rcx]
0x180010748  test    dx, dx
0x18001074b  jz      short loc_180010761
0x18001074d  mov     [rax], dx
0x180010750  add     rcx, 2
0x180010754  add     rax, 2
0x180010758  dec     r14
0x18001075b  sub     rsi, 1
0x18001075f  jnz     short loc_180010740
0x180010761  test    rsi, rsi
0x180010764  lea     rdx, [rax-2]
0x180010768  cmovnz  rdx, rax
0x18001076c  mov     [rdx], r12w
0x180010770  lea     r8, [rsp+280h+Name]; lpName
0x180010775  xor     edx, edx; bInheritHandle
0x180010777  mov     ecx, 1F0003h; dwDesiredAccess
0x18001077c  call    cs:__imp_OpenSemaphoreW
0x180010782  mov     [rsp+280h+var_258], rax
0x180010787  mov     rbx, rax
0x18001078a  test    rax, rax
0x18001078d  jz      short loc_1800107F3
0x18001078f  lea     rdx, [rsp+280h+var_260]; int *
0x180010794  mov     rcx, rax; hHandle
0x180010797  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001079c  mov     esi, eax
0x18001079e  test    eax, eax
0x1800107a0  jns     short loc_1800107CB
0x1800107a2  mov     rcx, [rbp+188h]; this
0x1800107a9  lea     r8, aWil; "wil"
0x1800107b0  mov     r9d, eax; char *
0x1800107b3  mov     edx, 0DEh; void *
0x1800107b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107bd  lea     rcx, [rsp+280h+var_258]
0x1800107c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800107c7  mov     ebx, esi
0x1800107c9  jmp     short loc_180010825
0x1800107cb  mov     rcx, rbx; this
0x1800107ce  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800107d3  movsxd  rax, [rsp+280h+var_25C]
0x1800107d8  movsxd  rcx, [rsp+280h+var_260]
0x1800107dd  shl     rcx, 1Fh
0x1800107e1  or      rcx, rax
0x1800107e4  mov     [r15], rcx
0x1800107e7  mov     rcx, rdi; this
0x1800107ea  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800107ef  xor     eax, eax
0x1800107f1  jmp     short loc_18001084B
0x1800107f3  mov     rcx, [rbp+188h]; this
0x1800107fa  lea     r8, aWil; "wil"
0x180010801  mov     edx, 0DCh; void *
0x180010806  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001080b  mov     rcx, rdi; this
0x18001080e  mov     ebx, eax
0x180010810  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010815  jmp     short loc_18001082F
0x180010817  call    cs:__imp_GetLastError
0x18001081d  cmp     eax, 2
0x180010820  jnz     short loc_180010833
0x180010822  mov     ebx, r12d
0x180010825  lea     rcx, [rsp+280h+var_250]
0x18001082a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001082f  mov     eax, ebx
0x180010831  jmp     short loc_18001084B
0x180010833  mov     rcx, [rbp+188h]; this
0x18001083a  lea     r8, aWil; "wil"
0x180010841  mov     edx, 0D0h; void *
0x180010846  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001084b  mov     rcx, [rbp+180h+var_30]
0x180010852  xor     rcx, rsp; StackCookie
0x180010855  call    __security_check_cookie
0x18001085a  lea     r11, [rsp+280h+var_20]
0x180010862  mov     rbx, [r11+30h]
0x180010866  mov     rsi, [r11+38h]
0x18001086a  mov     rsp, r11
0x18001086d  pop     r15
0x18001086f  pop     r14
0x180010871  pop     r12
0x180010873  pop     rdi
0x180010874  pop     rbp
0x180010875  retn
```

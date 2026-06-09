# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800443f8`
- end: `0x1800446d3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `731`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004416c`
- `0x18009f16c`

## callees

- `0x180043fd8`
- `0x1800443f8`
- `0x1800446dc`
- `0x180044840`
- `0x1800c8458`
- `0x1800fc644`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044517`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180044504`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004460a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180044504`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004460a`

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
  const char *v21; // r9
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // r8
  WCHAR *v28; // rax
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rbx
  WCHAR *v31; // rdx
  wil::details *v32; // rax
  const char *v33; // r9
  wil::details *v34; // rbx
  void *v35; // rdx
  int v36; // eax
  void *v37; // rdx
  void *v38; // rdx
  void *v39; // rdx
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
  v42 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v21);
    LastError = 0;
    goto LABEL_42;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
  }
  v25 = 260;
  v26 = Name;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v27 = (260 - v25) & -(__int64)(v25 != 0);
  if ( v25 )
  {
    v28 = &Name[v27];
    v29 = L"h";
    v30 = 260 - v27;
    if ( 260 != v27 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v29 )
          break;
        *v28++ = *v29++;
        --v5;
        --v30;
      }
      while ( v30 );
    }
    v31 = v28 - 1;
    if ( v30 )
      v31 = v28;
    *v31 = 0;
  }
  v32 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v34 = v32;
  if ( !v32 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v33);
LABEL_35:
    wil::details::CloseHandle(v20, v35);
    return LastError;
  }
  v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v32, &v40);
  LastError = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v36, v40);
    wil::details::CloseHandle(v34, v39);
    goto LABEL_35;
  }
  wil::details::CloseHandle(v34, v37);
  *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
  wil::details::CloseHandle(v20, v38);
  return 0;
}

```

## disassembly

```asm
0x1800443f8  mov     [rsp-8+arg_0], rbx
0x1800443fd  mov     [rsp-8+arg_8], rsi
0x180044402  push    rbp
0x180044403  push    rdi
0x180044404  push    r12
0x180044406  push    r14
0x180044408  push    r15
0x18004440a  lea     rbp, [rsp-150h]
0x180044412  sub     rsp, 250h
0x180044419  mov     rax, cs:__security_cookie
0x180044420  xor     rax, rsp
0x180044423  mov     [rbp+170h+var_30], rax
0x18004442a  xor     r12d, r12d
0x18004442d  lea     rax, [rsp+270h+Name]
0x180044432  mov     r14d, 7FFFFFFEh
0x180044438  mov     [r8], r12
0x18004443b  mov     ebx, 104h
0x180044440  mov     r9d, r14d
0x180044443  mov     edx, ebx
0x180044445  mov     r15, r8
0x180044448  test    r9, r9
0x18004444b  jz      short loc_18004446C
0x18004444d  movzx   r8d, word ptr [rcx]
0x180044451  test    r8w, r8w
0x180044455  jz      short loc_18004446C
0x180044457  mov     [rax], r8w
0x18004445b  add     rcx, 2
0x18004445f  add     rax, 2
0x180044463  dec     r9
0x180044466  sub     rdx, 1
0x18004446a  jnz     short loc_180044448
0x18004446c  test    rdx, rdx
0x18004446f  lea     rcx, [rax-2]
0x180044473  mov     rdx, rbx
0x180044476  cmovnz  rcx, rax
0x18004447a  lea     rax, [rsp+270h+Name]
0x18004447f  mov     [rcx], r12w
0x180044483  cmp     [rax], r12w
0x180044487  jz      short loc_180044493
0x180044489  add     rax, 2
0x18004448d  sub     rdx, 1
0x180044491  jnz     short loc_180044483
0x180044493  mov     rcx, rbx
0x180044496  mov     rax, rdx
0x180044499  sub     rcx, rdx
0x18004449c  neg     rax
0x18004449f  sbb     r8, r8
0x1800444a2  and     r8, rcx
0x1800444a5  test    rdx, rdx
0x1800444a8  jz      short loc_1800444F8
0x1800444aa  mov     rax, rbx
0x1800444ad  lea     rdx, [rsp+270h+Name]
0x1800444b2  lea     r9, aP0; "_p0"
0x1800444b9  mov     rcx, r14
0x1800444bc  lea     rdx, [rdx+r8*2]
0x1800444c0  sub     rax, r8
0x1800444c3  jz      short loc_1800444E9
0x1800444c5  test    rcx, rcx
0x1800444c8  jz      short loc_1800444E9
0x1800444ca  movzx   r8d, word ptr [r9]
0x1800444ce  test    r8w, r8w
0x1800444d2  jz      short loc_1800444E9
0x1800444d4  mov     [rdx], r8w
0x1800444d8  add     r9, 2
0x1800444dc  add     rdx, 2
0x1800444e0  dec     rcx
0x1800444e3  sub     rax, 1
0x1800444e7  jnz     short loc_1800444C5
0x1800444e9  test    rax, rax
0x1800444ec  lea     rcx, [rdx-2]
0x1800444f0  cmovnz  rcx, rdx
0x1800444f4  mov     [rcx], r12w
0x1800444f8  lea     r8, [rsp+270h+Name]; lpName
0x1800444fd  xor     edx, edx; bInheritHandle
0x1800444ff  mov     ecx, 1F0003h; dwDesiredAccess
0x180044504  call    cs:__imp_OpenSemaphoreW
0x18004450a  mov     [rsp+270h+var_248], rax
0x18004450f  mov     rdi, rax
0x180044512  test    rax, rax
0x180044515  jnz     short loc_180044569
0x180044517  call    cs:__imp_GetLastError
0x18004451d  cmp     eax, 2
0x180044520  jz      loc_1800446C1
0x180044526  mov     rcx, [rbp+178h]; this
0x18004452d  lea     r8, aWil; "wil"
0x180044534  mov     edx, 0D0h; void *
0x180044539  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004453e  mov     rcx, [rbp+170h+var_30]
0x180044545  xor     rcx, rsp; StackCookie
0x180044548  call    __security_check_cookie
0x18004454d  lea     r11, [rsp+270h+var_20]
0x180044555  mov     rbx, [r11+30h]
0x180044559  mov     rsi, [r11+38h]
0x18004455d  mov     rsp, r11
0x180044560  pop     r15
0x180044562  pop     r14
0x180044564  pop     r12
0x180044566  pop     rdi
0x180044567  pop     rbp
0x180044568  retn
0x180044569  lea     rdx, [rsp+270h+var_24C]; int *
0x18004456e  mov     [rsp+270h+var_24C], r12d
0x180044573  mov     rcx, rdi; hHandle
0x180044576  mov     [rsp+270h+var_250], r12d; int
0x18004457b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180044580  mov     esi, eax
0x180044582  test    eax, eax
0x180044584  js      loc_1800446A4
0x18004458a  mov     rdx, rbx
0x18004458d  lea     rax, [rsp+270h+Name]
0x180044592  cmp     [rax], r12w
0x180044596  jz      short loc_1800445A2
0x180044598  add     rax, 2
0x18004459c  sub     rdx, 1
0x1800445a0  jnz     short loc_180044592
0x1800445a2  mov     rcx, rbx
0x1800445a5  mov     rax, rdx
0x1800445a8  sub     rcx, rdx
0x1800445ab  neg     rax
0x1800445ae  sbb     r8, r8
0x1800445b1  and     r8, rcx
0x1800445b4  test    rdx, rdx
0x1800445b7  jz      short loc_1800445FE
0x1800445b9  lea     rax, [rsp+270h+Name]
0x1800445be  lea     rax, [rax+r8*2]
0x1800445c2  lea     rcx, asc_1802294B4; "h"
0x1800445c9  sub     rbx, r8
0x1800445cc  jz      short loc_1800445EF
0x1800445ce  test    r14, r14
0x1800445d1  jz      short loc_1800445EF
0x1800445d3  movzx   edx, word ptr [rcx]
0x1800445d6  test    dx, dx
0x1800445d9  jz      short loc_1800445EF
0x1800445db  mov     [rax], dx
0x1800445de  add     rcx, 2
0x1800445e2  add     rax, 2
0x1800445e6  dec     r14
0x1800445e9  sub     rbx, 1
0x1800445ed  jnz     short loc_1800445CE
0x1800445ef  test    rbx, rbx
0x1800445f2  lea     rdx, [rax-2]
0x1800445f6  cmovnz  rdx, rax
0x1800445fa  mov     [rdx], r12w
0x1800445fe  lea     r8, [rsp+270h+Name]; lpName
0x180044603  xor     edx, edx; bInheritHandle
0x180044605  mov     ecx, 1F0003h; dwDesiredAccess
0x18004460a  call    cs:__imp_OpenSemaphoreW
0x180044610  mov     rbx, rax
0x180044613  test    rax, rax
0x180044616  jnz     short loc_180044641
0x180044618  mov     rcx, [rbp+178h]; this
0x18004461f  lea     r8, aWil; "wil"
0x180044626  mov     edx, 0DCh; void *
0x18004462b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044630  mov     esi, eax
0x180044632  mov     rcx, rdi; this
0x180044635  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004463a  mov     eax, esi
0x18004463c  jmp     loc_18004453E
0x180044641  lea     rdx, [rsp+270h+var_250]; int *
0x180044646  mov     rcx, rbx; hHandle
0x180044649  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004464e  mov     esi, eax
0x180044650  test    eax, eax
0x180044652  js      short loc_18004467F
0x180044654  mov     rcx, rbx; this
0x180044657  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004465c  movsxd  rax, [rsp+270h+var_24C]
0x180044661  movsxd  rcx, [rsp+270h+var_250]
0x180044666  shl     rcx, 1Fh
0x18004466a  or      rcx, rax
0x18004466d  mov     [r15], rcx
0x180044670  mov     rcx, rdi; this
0x180044673  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180044678  xor     eax, eax
0x18004467a  jmp     loc_18004453E
0x18004467f  mov     rcx, [rbp+178h]; this
0x180044686  lea     r8, aWil; "wil"
0x18004468d  mov     r9d, eax; char *
0x180044690  mov     edx, 0DEh; void *
0x180044695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004469a  mov     rcx, rbx; this
0x18004469d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800446a2  jmp     short loc_180044632
0x1800446a4  mov     rcx, [rbp+178h]; this
0x1800446ab  lea     r8, aWil; "wil"
0x1800446b2  mov     r9d, eax; char *
0x1800446b5  mov     edx, 0D6h; void *
0x1800446ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800446bf  jmp     short loc_1800446C4
0x1800446c1  mov     esi, r12d
0x1800446c4  lea     rcx, [rsp+270h+var_248]
0x1800446c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800446ce  jmp     loc_18004463A
```

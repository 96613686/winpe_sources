# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180014420`
- end: `0x1800146e2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180013e64`
- `0x180013f24`

## callees

- `0x180014420`
- `0x1800146e8`
- `0x180014704`
- `0x1800147fc`
- `0x18008e540`
- `0x1800a7a2c`
- `0x1800bb480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001452c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001465d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001452c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001465d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001453f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001453f`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int LastError; // ebx
  void *v25; // rdx
  int ValueFromSemaphore; // eax
  unsigned int v27; // r8d
  unsigned int v28; // esi
  __int64 v29; // rdx
  WCHAR *v30; // rax
  __int64 v31; // r8
  WCHAR *v32; // rax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rbx
  WCHAR *v35; // rdx
  wil::details *v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  wil::details *v39; // rbx
  void *v40; // rdx
  int v41; // eax
  void *v42; // rdx
  unsigned int v43; // r8d
  void *v44; // rdx
  int v45; // [rsp+20h] [rbp-E0h] BYREF
  int v46; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v47; // [rsp+28h] [rbp-D8h] BYREF
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
  v47 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v21, v22);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v47);
      return LastError;
    }
    return 0;
  }
  v46 = 0;
  v45 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v46);
  v28 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v27, (const char *)(unsigned int)ValueFromSemaphore, v45);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v47);
  }
  else
  {
    v29 = 260;
    v30 = Name;
    do
    {
      if ( !*v30 )
        break;
      ++v30;
      --v29;
    }
    while ( v29 );
    v31 = (260 - v29) & -(__int64)(v29 != 0);
    if ( v29 )
    {
      v32 = &Name[v31];
      v33 = L"h";
      v34 = 260 - v31;
      if ( 260 != v31 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v33 )
            break;
          *v32++ = *v33++;
          --v5;
          --v34;
        }
        while ( v34 );
      }
      v35 = v32 - 1;
      if ( v34 )
        v35 = v32;
      *v35 = 0;
    }
    v36 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v39 = v36;
    if ( v36 )
    {
      v41 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v36, &v45);
      v28 = v41;
      if ( v41 >= 0 )
      {
        wil::details::CloseHandle(v39, v42);
        *a3 = v46 | (unsigned __int64)((__int64)v45 << 31);
        wil::details::CloseHandle(v20, v25);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v43, (const char *)(unsigned int)v41, v45);
      wil::details::CloseHandle(v39, v44);
    }
    else
    {
      v28 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v37, v38);
    }
    wil::details::CloseHandle(v20, v40);
  }
  return v28;
}

```

## disassembly

```asm
0x180014420  mov     [rsp-8+arg_0], rbx
0x180014425  mov     [rsp-8+arg_8], rsi
0x18001442a  push    rbp
0x18001442b  push    rdi
0x18001442c  push    r12
0x18001442e  push    r14
0x180014430  push    r15
0x180014432  lea     rbp, [rsp-150h]
0x18001443a  sub     rsp, 250h
0x180014441  mov     rax, cs:__security_cookie
0x180014448  xor     rax, rsp
0x18001444b  mov     [rbp+170h+var_30], rax
0x180014452  xor     r12d, r12d
0x180014455  lea     rax, [rsp+270h+Name]
0x18001445a  mov     r14d, 7FFFFFFEh
0x180014460  mov     [r8], r12
0x180014463  mov     ebx, 104h
0x180014468  mov     r9d, r14d
0x18001446b  mov     edx, ebx
0x18001446d  mov     r15, r8
0x180014470  test    r9, r9
0x180014473  jz      short loc_180014494
0x180014475  movzx   r8d, word ptr [rcx]
0x180014479  test    r8w, r8w
0x18001447d  jz      short loc_180014494
0x18001447f  mov     [rax], r8w
0x180014483  add     rcx, 2
0x180014487  add     rax, 2
0x18001448b  dec     r9
0x18001448e  sub     rdx, 1
0x180014492  jnz     short loc_180014470
0x180014494  test    rdx, rdx
0x180014497  lea     rcx, [rax-2]
0x18001449b  mov     rdx, rbx
0x18001449e  cmovnz  rcx, rax
0x1800144a2  lea     rax, [rsp+270h+Name]
0x1800144a7  mov     [rcx], r12w
0x1800144ab  cmp     [rax], r12w
0x1800144af  jz      short loc_1800144BB
0x1800144b1  add     rax, 2
0x1800144b5  sub     rdx, 1
0x1800144b9  jnz     short loc_1800144AB
0x1800144bb  mov     rcx, rbx
0x1800144be  mov     rax, rdx
0x1800144c1  sub     rcx, rdx
0x1800144c4  neg     rax
0x1800144c7  sbb     r8, r8
0x1800144ca  and     r8, rcx
0x1800144cd  test    rdx, rdx
0x1800144d0  jz      short loc_180014520
0x1800144d2  mov     rax, rbx
0x1800144d5  lea     rdx, [rsp+270h+Name]
0x1800144da  lea     r9, aP0; "_p0"
0x1800144e1  mov     rcx, r14
0x1800144e4  lea     rdx, [rdx+r8*2]
0x1800144e8  sub     rax, r8
0x1800144eb  jz      short loc_180014511
0x1800144ed  test    rcx, rcx
0x1800144f0  jz      short loc_180014511
0x1800144f2  movzx   r8d, word ptr [r9]
0x1800144f6  test    r8w, r8w
0x1800144fa  jz      short loc_180014511
0x1800144fc  mov     [rdx], r8w
0x180014500  add     r9, 2
0x180014504  add     rdx, 2
0x180014508  dec     rcx
0x18001450b  sub     rax, 1
0x18001450f  jnz     short loc_1800144ED
0x180014511  test    rax, rax
0x180014514  lea     rcx, [rdx-2]
0x180014518  cmovnz  rcx, rdx
0x18001451c  mov     [rcx], r12w
0x180014520  lea     r8, [rsp+270h+Name]; lpName
0x180014525  xor     edx, edx; bInheritHandle
0x180014527  mov     ecx, 1F0003h; dwDesiredAccess
0x18001452c  call    cs:__imp_OpenSemaphoreW
0x180014532  mov     [rsp+270h+var_248], rax
0x180014537  mov     rdi, rax
0x18001453a  test    rax, rax
0x18001453d  jnz     short loc_1800145BC
0x18001453f  call    cs:__imp_GetLastError
0x180014545  cmp     eax, 2
0x180014548  jz      short loc_18001458F
0x18001454a  mov     rcx, [rbp+178h]; this
0x180014551  mov     edx, 0D0h; void *
0x180014556  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001455b  lea     rcx, [rsp+270h+var_248]
0x180014560  mov     ebx, eax
0x180014562  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014567  mov     eax, ebx
0x180014569  jmp     short loc_180014591
0x18001456b  mov     rcx, rbx; this
0x18001456e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180014573  movsxd  rax, [rsp+270h+var_24C]
0x180014578  movsxd  rcx, [rsp+270h+var_250]
0x18001457d  shl     rcx, 1Fh
0x180014581  or      rcx, rax
0x180014584  mov     [r15], rcx
0x180014587  mov     rcx, rdi; this
0x18001458a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001458f  xor     eax, eax
0x180014591  mov     rcx, [rbp+170h+var_30]
0x180014598  xor     rcx, rsp; StackCookie
0x18001459b  call    __security_check_cookie
0x1800145a0  lea     r11, [rsp+270h+var_20]
0x1800145a8  mov     rbx, [r11+30h]
0x1800145ac  mov     rsi, [r11+38h]
0x1800145b0  mov     rsp, r11
0x1800145b3  pop     r15
0x1800145b5  pop     r14
0x1800145b7  pop     r12
0x1800145b9  pop     rdi
0x1800145ba  pop     rbp
0x1800145bb  retn
0x1800145bc  lea     rdx, [rsp+270h+var_24C]; int *
0x1800145c1  mov     [rsp+270h+var_24C], r12d
0x1800145c6  mov     rcx, rdi; hHandle
0x1800145c9  mov     [rsp+270h+var_250], r12d; int
0x1800145ce  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800145d3  mov     esi, eax
0x1800145d5  test    eax, eax
0x1800145d7  js      loc_1800146C2
0x1800145dd  mov     rdx, rbx
0x1800145e0  lea     rax, [rsp+270h+Name]
0x1800145e5  cmp     [rax], r12w
0x1800145e9  jz      short loc_1800145F5
0x1800145eb  add     rax, 2
0x1800145ef  sub     rdx, 1
0x1800145f3  jnz     short loc_1800145E5
0x1800145f5  mov     rcx, rbx
0x1800145f8  mov     rax, rdx
0x1800145fb  sub     rcx, rdx
0x1800145fe  neg     rax
0x180014601  sbb     r8, r8
0x180014604  and     r8, rcx
0x180014607  test    rdx, rdx
0x18001460a  jz      short loc_180014651
0x18001460c  lea     rax, [rsp+270h+Name]
0x180014611  lea     rax, [rax+r8*2]
0x180014615  lea     rcx, asc_180293DE0; "h"
0x18001461c  sub     rbx, r8
0x18001461f  jz      short loc_180014642
0x180014621  test    r14, r14
0x180014624  jz      short loc_180014642
0x180014626  movzx   edx, word ptr [rcx]
0x180014629  test    dx, dx
0x18001462c  jz      short loc_180014642
0x18001462e  mov     [rax], dx
0x180014631  add     rcx, 2
0x180014635  add     rax, 2
0x180014639  dec     r14
0x18001463c  sub     rbx, 1
0x180014640  jnz     short loc_180014621
0x180014642  test    rbx, rbx
0x180014645  lea     rdx, [rax-2]
0x180014649  cmovnz  rdx, rax
0x18001464d  mov     [rdx], r12w
0x180014651  lea     r8, [rsp+270h+Name]; lpName
0x180014656  xor     edx, edx; bInheritHandle
0x180014658  mov     ecx, 1F0003h; dwDesiredAccess
0x18001465d  call    cs:__imp_OpenSemaphoreW
0x180014663  mov     rbx, rax
0x180014666  test    rax, rax
0x180014669  jnz     short loc_18001468D
0x18001466b  mov     rcx, [rbp+178h]; this
0x180014672  mov     edx, 0DCh; void *
0x180014677  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001467c  mov     esi, eax
0x18001467e  mov     rcx, rdi; this
0x180014681  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180014686  mov     eax, esi
0x180014688  jmp     loc_180014591
0x18001468d  lea     rdx, [rsp+270h+var_250]; int *
0x180014692  mov     rcx, rbx; hHandle
0x180014695  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001469a  mov     esi, eax
0x18001469c  test    eax, eax
0x18001469e  jns     loc_18001456B
0x1800146a4  mov     rcx, [rbp+178h]; this
0x1800146ab  mov     r9d, eax; char *
0x1800146ae  mov     edx, 0DEh; void *
0x1800146b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146b8  mov     rcx, rbx; this
0x1800146bb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800146c0  jmp     short loc_18001467E
0x1800146c2  mov     rcx, [rbp+178h]; this
0x1800146c9  mov     r9d, esi; char *
0x1800146cc  mov     edx, 0D6h; void *
0x1800146d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146d6  lea     rcx, [rsp+270h+var_248]
0x1800146db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800146e0  jmp     short loc_180014686
```

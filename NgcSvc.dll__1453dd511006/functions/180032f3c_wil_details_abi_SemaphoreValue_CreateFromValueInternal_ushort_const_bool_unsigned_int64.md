# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180032f3c`
- end: `0x1800331cc`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `656`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180051640`
- `0x180061824`

## callees

- `0x18000782c`
- `0x180032f3c`
- `0x180048098`
- `0x18004884c`
- `0x18005cee0`
- `0x180062a90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180033072`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180033153`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180033072`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180033153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003318c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003318c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  LONG v11; // edi
  bool v12; // zf
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r8
  const wchar_t *v17; // r9
  __int64 v18; // rcx
  WCHAR *v19; // rdx
  __int64 v20; // rax
  WCHAR *v21; // rcx
  LONG v22; // r8d
  wil::details *v23; // rcx
  HANDLE Semaphore; // rsi
  int LastErrorFailHr; // eax
  unsigned int v26; // esi
  unsigned __int64 v28; // rbp
  WCHAR *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  WCHAR *v32; // rax
  const wchar_t *v33; // rcx
  __int64 v34; // rbx
  WCHAR *v35; // rcx
  wil::details *v36; // rcx
  HANDLE v37; // rbx
  int v38; // eax
  unsigned int v39; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
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
    v17 = L"_p0";
    v18 = 2147483646;
    v19 = &Name[v16];
    v20 = 260 - v16;
    if ( v16 != 260 )
    {
      do
      {
        if ( !v18 )
          break;
        if ( !*v17 )
          break;
        *v19++ = *v17++;
        --v18;
        --v20;
      }
      while ( v20 );
    }
    v21 = v19 - 1;
    if ( v20 )
      v21 = v19;
    *v21 = 0;
  }
  v22 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v22 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v22, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v23);
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
  v29 = Name;
  v30 = 260;
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v30;
  }
  while ( v30 );
  v31 = (260 - v30) & -(__int64)(v30 != 0);
  if ( v30 )
  {
    v32 = &Name[v31];
    v33 = L"h";
    v34 = 260 - v31;
    if ( 260 != v31 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v33 )
          break;
        *v32++ = *v33++;
        --v8;
        --v34;
      }
      while ( v34 );
    }
    v35 = v32 - 1;
    if ( v34 )
      v35 = v32;
    *v35 = 0;
  }
  if ( (_DWORD)v28 )
    v11 = v28;
  v37 = CreateSemaphoreExW(0, v28, v11, Name, 0, 0x1F0003u);
  if ( v37 )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 8,
      v37);
  }
  else
  {
    v38 = wil::details::GetLastErrorFailHr(v36);
    v39 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v38,
        dwFlagsa);
      return v39;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180032f3c  mov     [rsp+arg_8], rbx
0x180032f41  mov     [rsp+arg_10], rbp
0x180032f46  push    rsi
0x180032f47  push    rdi
0x180032f48  push    r12
0x180032f4a  push    r14
0x180032f4c  push    r15
0x180032f4e  sub     rsp, 250h
0x180032f55  mov     rax, cs:__security_cookie
0x180032f5c  xor     rax, rsp
0x180032f5f  mov     [rsp+278h+var_38], rax
0x180032f67  mov     rax, 0C000000000000000h
0x180032f71  mov     rbp, r9
0x180032f74  mov     r8, rdx
0x180032f77  mov     r15, rcx
0x180032f7a  test    rax, r9
0x180032f7d  jz      short loc_180032F85
0x180032f7f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180032f85  xor     r12d, r12d
0x180032f88  lea     rax, [rsp+278h+Name]
0x180032f8d  mov     r14d, 7FFFFFFEh
0x180032f93  mov     ebx, 104h
0x180032f98  mov     ecx, r14d
0x180032f9b  mov     edx, ebx
0x180032f9d  lea     edi, [r12+1]
0x180032fa2  test    rcx, rcx
0x180032fa5  jz      short loc_180032FC5
0x180032fa7  movzx   r9d, word ptr [r8]
0x180032fab  test    r9w, r9w
0x180032faf  jz      short loc_180032FC5
0x180032fb1  mov     [rax], r9w
0x180032fb5  add     r8, 2
0x180032fb9  add     rax, 2
0x180032fbd  sub     rcx, rdi
0x180032fc0  sub     rdx, rdi
0x180032fc3  jnz     short loc_180032FA2
0x180032fc5  test    rdx, rdx
0x180032fc8  lea     rcx, [rax-2]
0x180032fcc  mov     rdx, rbx
0x180032fcf  cmovnz  rcx, rax
0x180032fd3  lea     rax, [rsp+278h+Name]
0x180032fd8  mov     [rcx], r12w
0x180032fdc  cmp     [rax], r12w
0x180032fe0  jz      short loc_180032FEB
0x180032fe2  add     rax, 2
0x180032fe6  sub     rdx, rdi
0x180032fe9  jnz     short loc_180032FDC
0x180032feb  mov     rcx, rbx
0x180032fee  mov     rax, rdx
0x180032ff1  sub     rcx, rdx
0x180032ff4  neg     rax
0x180032ff7  sbb     r8, r8
0x180032ffa  and     r8, rcx
0x180032ffd  test    rdx, rdx
0x180033000  jz      short loc_18003304F
0x180033002  mov     rax, rbx
0x180033005  lea     rdx, [rsp+278h+Name]
0x18003300a  lea     r9, aP0; "_p0"
0x180033011  mov     rcx, r14
0x180033014  lea     rdx, [rdx+r8*2]
0x180033018  sub     rax, r8
0x18003301b  jz      short loc_180033040
0x18003301d  test    rcx, rcx
0x180033020  jz      short loc_180033040
0x180033022  movzx   r8d, word ptr [r9]
0x180033026  test    r8w, r8w
0x18003302a  jz      short loc_180033040
0x18003302c  mov     [rdx], r8w
0x180033030  add     r9, 2
0x180033034  add     rdx, 2
0x180033038  sub     rcx, rdi
0x18003303b  sub     rax, rdi
0x18003303e  jnz     short loc_18003301D
0x180033040  test    rax, rax
0x180033043  lea     rcx, [rdx-2]
0x180033047  cmovnz  rcx, rdx
0x18003304b  mov     [rcx], r12w
0x18003304f  mov     edx, ebp
0x180033051  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180033059  and     edx, 7FFFFFFFh; lInitialCount
0x18003305f  mov     [rsp+278h+dwFlags], r12d; int
0x180033064  mov     r8d, edi
0x180033067  lea     r9, [rsp+278h+Name]; lpName
0x18003306c  cmova   r8d, edx; lMaximumCount
0x180033070  xor     ecx, ecx; lpSemaphoreAttributes
0x180033072  call    cs:__imp_CreateSemaphoreExW
0x180033078  mov     rsi, rax
0x18003307b  test    rax, rax
0x18003307e  jnz     short loc_1800330AE
0x180033080  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180033085  mov     esi, eax
0x180033087  test    eax, eax
0x180033089  jns     short loc_1800330BF
0x18003308b  mov     rcx, [rsp+278h]; this
0x180033093  lea     r8, aWil; "wil"
0x18003309a  mov     r9d, eax; char *
0x18003309d  mov     edx, 8Bh; void *
0x1800330a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800330a7  mov     eax, esi
0x1800330a9  jmp     loc_1800331A0
0x1800330ae  call    cs:__imp_GetLastError
0x1800330b4  mov     rdx, rsi
0x1800330b7  mov     rcx, r15
0x1800330ba  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800330bf  shr     rbp, 1Fh
0x1800330c3  lea     rax, [rsp+278h+Name]
0x1800330c8  mov     rdx, rbx
0x1800330cb  cmp     [rax], r12w
0x1800330cf  jz      short loc_1800330DA
0x1800330d1  add     rax, 2
0x1800330d5  sub     rdx, rdi
0x1800330d8  jnz     short loc_1800330CB
0x1800330da  mov     rcx, rbx
0x1800330dd  mov     rax, rdx
0x1800330e0  sub     rcx, rdx
0x1800330e3  neg     rax
0x1800330e6  sbb     r8, r8
0x1800330e9  and     r8, rcx
0x1800330ec  test    rdx, rdx
0x1800330ef  jz      short loc_180033135
0x1800330f1  lea     rax, [rsp+278h+Name]
0x1800330f6  lea     rax, [rax+r8*2]
0x1800330fa  lea     rcx, asc_1800DB980; "h"
0x180033101  sub     rbx, r8
0x180033104  jz      short loc_180033126
0x180033106  test    r14, r14
0x180033109  jz      short loc_180033126
0x18003310b  movzx   edx, word ptr [rcx]
0x18003310e  test    dx, dx
0x180033111  jz      short loc_180033126
0x180033113  mov     [rax], dx
0x180033116  add     rcx, 2
0x18003311a  add     rax, 2
0x18003311e  sub     r14, rdi
0x180033121  sub     rbx, rdi
0x180033124  jnz     short loc_180033106
0x180033126  test    rbx, rbx
0x180033129  lea     rcx, [rax-2]
0x18003312d  cmovnz  rcx, rax
0x180033131  mov     [rcx], r12w
0x180033135  test    ebp, ebp
0x180033137  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18003313f  lea     r9, [rsp+278h+Name]; lpName
0x180033144  mov     [rsp+278h+dwFlags], r12d; int
0x180033149  cmovnz  edi, ebp
0x18003314c  mov     edx, ebp; lInitialCount
0x18003314e  mov     r8d, edi; lMaximumCount
0x180033151  xor     ecx, ecx; lpSemaphoreAttributes
0x180033153  call    cs:__imp_CreateSemaphoreExW
0x180033159  mov     rbx, rax
0x18003315c  test    rax, rax
0x18003315f  jnz     short loc_18003318C
0x180033161  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180033166  mov     ebx, eax
0x180033168  test    eax, eax
0x18003316a  jns     short loc_18003319E
0x18003316c  mov     rcx, [rsp+278h]; this
0x180033174  lea     r8, aWil; "wil"
0x18003317b  mov     r9d, eax; char *
0x18003317e  mov     edx, 90h; void *
0x180033183  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033188  mov     eax, ebx
0x18003318a  jmp     short loc_1800331A0
0x18003318c  call    cs:__imp_GetLastError
0x180033192  lea     rcx, [r15+8]
0x180033196  mov     rdx, rbx
0x180033199  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003319e  xor     eax, eax
0x1800331a0  mov     rcx, [rsp+278h+var_38]
0x1800331a8  xor     rcx, rsp; StackCookie
0x1800331ab  call    __security_check_cookie
0x1800331b0  lea     r11, [rsp+278h+var_28]
0x1800331b8  mov     rbx, [r11+38h]
0x1800331bc  mov     rbp, [r11+40h]
0x1800331c0  mov     rsp, r11
0x1800331c3  pop     r15
0x1800331c5  pop     r14
0x1800331c7  pop     r12
0x1800331c9  pop     rdi
0x1800331ca  pop     rsi
0x1800331cb  retn
```

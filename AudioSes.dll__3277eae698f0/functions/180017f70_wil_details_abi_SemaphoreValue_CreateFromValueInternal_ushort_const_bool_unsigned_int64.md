# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180017f70`
- end: `0x180018200`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `656`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017e64`

## callees

- `0x180010a90`
- `0x180013ab8`
- `0x180017f70`
- `0x180069394`
- `0x180087e80`
- `0x18008e8d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800180a6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180018187`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800180a6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180018187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181c0`

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
0x180017f70  mov     [rsp+arg_8], rbx
0x180017f75  mov     [rsp+arg_10], rbp
0x180017f7a  push    rsi
0x180017f7b  push    rdi
0x180017f7c  push    r12
0x180017f7e  push    r14
0x180017f80  push    r15
0x180017f82  sub     rsp, 250h
0x180017f89  mov     rax, cs:__security_cookie
0x180017f90  xor     rax, rsp
0x180017f93  mov     [rsp+278h+var_38], rax
0x180017f9b  mov     rax, 0C000000000000000h
0x180017fa5  mov     rbp, r9
0x180017fa8  mov     r8, rdx
0x180017fab  mov     r15, rcx
0x180017fae  test    rax, r9
0x180017fb1  jz      short loc_180017FB9
0x180017fb3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180017fb9  xor     r12d, r12d
0x180017fbc  lea     rax, [rsp+278h+Name]
0x180017fc1  mov     r14d, 7FFFFFFEh
0x180017fc7  mov     ebx, 104h
0x180017fcc  mov     ecx, r14d
0x180017fcf  mov     edx, ebx
0x180017fd1  lea     edi, [r12+1]
0x180017fd6  test    rcx, rcx
0x180017fd9  jz      short loc_180017FF9
0x180017fdb  movzx   r9d, word ptr [r8]
0x180017fdf  test    r9w, r9w
0x180017fe3  jz      short loc_180017FF9
0x180017fe5  mov     [rax], r9w
0x180017fe9  add     r8, 2
0x180017fed  add     rax, 2
0x180017ff1  sub     rcx, rdi
0x180017ff4  sub     rdx, rdi
0x180017ff7  jnz     short loc_180017FD6
0x180017ff9  test    rdx, rdx
0x180017ffc  lea     rcx, [rax-2]
0x180018000  mov     rdx, rbx
0x180018003  cmovnz  rcx, rax
0x180018007  lea     rax, [rsp+278h+Name]
0x18001800c  mov     [rcx], r12w
0x180018010  cmp     [rax], r12w
0x180018014  jz      short loc_18001801F
0x180018016  add     rax, 2
0x18001801a  sub     rdx, rdi
0x18001801d  jnz     short loc_180018010
0x18001801f  mov     rcx, rbx
0x180018022  mov     rax, rdx
0x180018025  sub     rcx, rdx
0x180018028  neg     rax
0x18001802b  sbb     r8, r8
0x18001802e  and     r8, rcx
0x180018031  test    rdx, rdx
0x180018034  jz      short loc_180018083
0x180018036  mov     rax, rbx
0x180018039  lea     rdx, [rsp+278h+Name]
0x18001803e  lea     r9, aP0; "_p0"
0x180018045  mov     rcx, r14
0x180018048  lea     rdx, [rdx+r8*2]
0x18001804c  sub     rax, r8
0x18001804f  jz      short loc_180018074
0x180018051  test    rcx, rcx
0x180018054  jz      short loc_180018074
0x180018056  movzx   r8d, word ptr [r9]
0x18001805a  test    r8w, r8w
0x18001805e  jz      short loc_180018074
0x180018060  mov     [rdx], r8w
0x180018064  add     r9, 2
0x180018068  add     rdx, 2
0x18001806c  sub     rcx, rdi
0x18001806f  sub     rax, rdi
0x180018072  jnz     short loc_180018051
0x180018074  test    rax, rax
0x180018077  lea     rcx, [rdx-2]
0x18001807b  cmovnz  rcx, rdx
0x18001807f  mov     [rcx], r12w
0x180018083  mov     edx, ebp
0x180018085  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001808d  and     edx, 7FFFFFFFh; lInitialCount
0x180018093  mov     [rsp+278h+dwFlags], r12d; int
0x180018098  mov     r8d, edi
0x18001809b  lea     r9, [rsp+278h+Name]; lpName
0x1800180a0  cmova   r8d, edx; lMaximumCount
0x1800180a4  xor     ecx, ecx; lpSemaphoreAttributes
0x1800180a6  call    cs:__imp_CreateSemaphoreExW
0x1800180ac  mov     rsi, rax
0x1800180af  test    rax, rax
0x1800180b2  jnz     short loc_1800180E2
0x1800180b4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800180b9  mov     esi, eax
0x1800180bb  test    eax, eax
0x1800180bd  jns     short loc_1800180F3
0x1800180bf  mov     rcx, [rsp+278h]; this
0x1800180c7  lea     r8, aWil; "wil"
0x1800180ce  mov     r9d, eax; char *
0x1800180d1  mov     edx, 8Bh; void *
0x1800180d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180db  mov     eax, esi
0x1800180dd  jmp     loc_1800181D4
0x1800180e2  call    cs:__imp_GetLastError
0x1800180e8  mov     rdx, rsi
0x1800180eb  mov     rcx, r15
0x1800180ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800180f3  shr     rbp, 1Fh
0x1800180f7  lea     rax, [rsp+278h+Name]
0x1800180fc  mov     rdx, rbx
0x1800180ff  cmp     [rax], r12w
0x180018103  jz      short loc_18001810E
0x180018105  add     rax, 2
0x180018109  sub     rdx, rdi
0x18001810c  jnz     short loc_1800180FF
0x18001810e  mov     rcx, rbx
0x180018111  mov     rax, rdx
0x180018114  sub     rcx, rdx
0x180018117  neg     rax
0x18001811a  sbb     r8, r8
0x18001811d  and     r8, rcx
0x180018120  test    rdx, rdx
0x180018123  jz      short loc_180018169
0x180018125  lea     rax, [rsp+278h+Name]
0x18001812a  lea     rax, [rax+r8*2]
0x18001812e  lea     rcx, asc_1801486DC; "h"
0x180018135  sub     rbx, r8
0x180018138  jz      short loc_18001815A
0x18001813a  test    r14, r14
0x18001813d  jz      short loc_18001815A
0x18001813f  movzx   edx, word ptr [rcx]
0x180018142  test    dx, dx
0x180018145  jz      short loc_18001815A
0x180018147  mov     [rax], dx
0x18001814a  add     rcx, 2
0x18001814e  add     rax, 2
0x180018152  sub     r14, rdi
0x180018155  sub     rbx, rdi
0x180018158  jnz     short loc_18001813A
0x18001815a  test    rbx, rbx
0x18001815d  lea     rcx, [rax-2]
0x180018161  cmovnz  rcx, rax
0x180018165  mov     [rcx], r12w
0x180018169  test    ebp, ebp
0x18001816b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180018173  lea     r9, [rsp+278h+Name]; lpName
0x180018178  mov     [rsp+278h+dwFlags], r12d; int
0x18001817d  cmovnz  edi, ebp
0x180018180  mov     edx, ebp; lInitialCount
0x180018182  mov     r8d, edi; lMaximumCount
0x180018185  xor     ecx, ecx; lpSemaphoreAttributes
0x180018187  call    cs:__imp_CreateSemaphoreExW
0x18001818d  mov     rbx, rax
0x180018190  test    rax, rax
0x180018193  jnz     short loc_1800181C0
0x180018195  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001819a  mov     ebx, eax
0x18001819c  test    eax, eax
0x18001819e  jns     short loc_1800181D2
0x1800181a0  mov     rcx, [rsp+278h]; this
0x1800181a8  lea     r8, aWil; "wil"
0x1800181af  mov     r9d, eax; char *
0x1800181b2  mov     edx, 90h; void *
0x1800181b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181bc  mov     eax, ebx
0x1800181be  jmp     short loc_1800181D4
0x1800181c0  call    cs:__imp_GetLastError
0x1800181c6  lea     rcx, [r15+8]
0x1800181ca  mov     rdx, rbx
0x1800181cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800181d2  xor     eax, eax
0x1800181d4  mov     rcx, [rsp+278h+var_38]
0x1800181dc  xor     rcx, rsp; StackCookie
0x1800181df  call    __security_check_cookie
0x1800181e4  lea     r11, [rsp+278h+var_28]
0x1800181ec  mov     rbx, [r11+38h]
0x1800181f0  mov     rbp, [r11+40h]
0x1800181f4  mov     rsp, r11
0x1800181f7  pop     r15
0x1800181f9  pop     r14
0x1800181fb  pop     r12
0x1800181fd  pop     rdi
0x1800181fe  pop     rsi
0x1800181ff  retn
```

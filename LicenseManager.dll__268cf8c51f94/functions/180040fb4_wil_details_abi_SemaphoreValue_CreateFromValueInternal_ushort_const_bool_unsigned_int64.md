# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180040fb4`
- end: `0x1800411bb`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `519`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180060aa0`
- `0x180060bd8`

## callees

- `0x180040fb4`
- `0x1800411c4`
- `0x1800614e4`
- `0x180061f80`
- `0x18006d43c`
- `0x180075e60`
- `0x180083710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800410ad`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180041156`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800410ad`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180041156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041180`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // edi
  bool v11; // zf
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  WCHAR *v14; // rax
  __int64 v15; // r8
  LONG v16; // r8d
  wil::details *v17; // rcx
  HANDLE Semaphore; // rsi
  int LastErrorFailHr; // eax
  unsigned int v20; // edx
  int v21; // r9d
  unsigned int v22; // esi
  unsigned __int64 v24; // rbp
  WCHAR *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  wil::details *v28; // rcx
  HANDLE v29; // rbx
  int v30; // eax
  unsigned int v31; // edx
  int v32; // r9d
  unsigned int v33; // ebx
  size_t dwFlags; // [rsp+20h] [rbp-258h]
  size_t dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v9 == 0;
  v12 = v7 - 1;
  v13 = 260;
  if ( !v11 )
    v12 = v7;
  v14 = Name;
  *v12 = 0;
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
    StringCopyWorkerW(&Name[v15], 260 - v15, (size_t *)v15, L"_p0", dwFlags);
  }
  v16 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v16 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v16, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v17);
    v22 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)0x8B,
        v20,
        (const char *)(unsigned int)LastErrorFailHr,
        v21);
      return v22;
    }
  }
  v24 = a4 >> 31;
  v25 = Name;
  v26 = 260;
  do
  {
    if ( !*v25 )
      break;
    ++v25;
    --v26;
  }
  while ( v26 );
  if ( v26 )
  {
    v27 = (260 - v26) & -(__int64)(v26 != 0);
    StringCopyWorkerW(&Name[v27], 260 - v27, (size_t *)v27, L"h", dwFlagsa);
  }
  if ( (_DWORD)v24 )
    v10 = v24;
  v29 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v29 )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 8,
      v29);
  }
  else
  {
    v30 = wil::details::GetLastErrorFailHr(v28);
    v33 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0x90, v31, (const char *)(unsigned int)v30, v32);
      return v33;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180040fb4  mov     [rsp+arg_8], rbx
0x180040fb9  push    rbp
0x180040fba  push    rsi
0x180040fbb  push    rdi
0x180040fbc  push    r14
0x180040fbe  push    r15
0x180040fc0  sub     rsp, 250h
0x180040fc7  mov     rax, cs:__security_cookie
0x180040fce  xor     rax, rsp
0x180040fd1  mov     [rsp+278h+var_38], rax
0x180040fd9  mov     rax, 0C000000000000000h
0x180040fe3  mov     rbp, r9
0x180040fe6  mov     r8, rdx
0x180040fe9  mov     r14, rcx
0x180040fec  test    rax, r9
0x180040fef  jz      short loc_180040FF7
0x180040ff1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180040ff7  xor     r15d, r15d
0x180040ffa  lea     rax, [rsp+278h+Name]
0x180040fff  mov     ebx, 104h
0x180041004  mov     ecx, 7FFFFFFEh
0x180041009  mov     edx, ebx
0x18004100b  lea     edi, [r15+1]
0x18004100f  test    rcx, rcx
0x180041012  jz      short loc_180041032
0x180041014  movzx   r9d, word ptr [r8]
0x180041018  test    r9w, r9w
0x18004101c  jz      short loc_180041032
0x18004101e  mov     [rax], r9w
0x180041022  add     r8, 2
0x180041026  add     rax, 2
0x18004102a  sub     rcx, rdi
0x18004102d  sub     rdx, rdi
0x180041030  jnz     short loc_18004100F
0x180041032  test    rdx, rdx
0x180041035  lea     rcx, [rax-2]
0x180041039  mov     rdx, rbx
0x18004103c  cmovnz  rcx, rax
0x180041040  lea     rax, [rsp+278h+Name]
0x180041045  mov     [rcx], r15w
0x180041049  cmp     [rax], r15w
0x18004104d  jz      short loc_180041058
0x18004104f  add     rax, 2
0x180041053  sub     rdx, rdi
0x180041056  jnz     short loc_180041049
0x180041058  mov     rcx, rbx
0x18004105b  mov     rax, rdx
0x18004105e  sub     rcx, rdx
0x180041061  neg     rax
0x180041064  sbb     r8, r8
0x180041067  and     r8, rcx; pcchNewDestLength
0x18004106a  test    rdx, rdx
0x18004106d  jz      short loc_18004108A
0x18004106f  mov     rdx, rbx
0x180041072  lea     rcx, [rsp+278h+Name]
0x180041077  sub     rdx, r8; cchDest
0x18004107a  lea     rcx, [rcx+r8*2]; pszDest
0x18004107e  lea     r9, aP0; "_p0"
0x180041085  call    StringCopyWorkerW
0x18004108a  mov     edx, ebp
0x18004108c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180041094  and     edx, 7FFFFFFFh; lInitialCount
0x18004109a  mov     dword ptr [rsp+278h+dwFlags], r15d; cchToCopy
0x18004109f  mov     r8d, edi
0x1800410a2  lea     r9, [rsp+278h+Name]; lpName
0x1800410a7  cmova   r8d, edx; lMaximumCount
0x1800410ab  xor     ecx, ecx; lpSemaphoreAttributes
0x1800410ad  call    cs:__imp_CreateSemaphoreExW
0x1800410b3  mov     rsi, rax
0x1800410b6  test    rax, rax
0x1800410b9  jnz     short loc_1800410DA
0x1800410bb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800410c0  mov     esi, eax
0x1800410c2  test    eax, eax
0x1800410c4  jns     short loc_1800410EB
0x1800410c6  mov     r8d, eax; char *
0x1800410c9  mov     ecx, 8Bh; this
0x1800410ce  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x1800410d3  mov     eax, esi
0x1800410d5  jmp     loc_180041194
0x1800410da  call    cs:__imp_GetLastError
0x1800410e0  mov     rdx, rsi
0x1800410e3  mov     rcx, r14
0x1800410e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800410eb  shr     rbp, 1Fh
0x1800410ef  lea     rax, [rsp+278h+Name]
0x1800410f4  mov     rdx, rbx
0x1800410f7  cmp     [rax], r15w
0x1800410fb  jz      short loc_180041106
0x1800410fd  add     rax, 2
0x180041101  sub     rdx, rdi
0x180041104  jnz     short loc_1800410F7
0x180041106  mov     rcx, rbx
0x180041109  mov     rax, rdx
0x18004110c  sub     rcx, rdx
0x18004110f  neg     rax
0x180041112  sbb     r8, r8
0x180041115  and     r8, rcx; pcchNewDestLength
0x180041118  test    rdx, rdx
0x18004111b  jz      short loc_180041138
0x18004111d  sub     rbx, r8
0x180041120  lea     rcx, [rsp+278h+Name]
0x180041125  lea     rcx, [rcx+r8*2]; pszDest
0x180041129  mov     rdx, rbx; cchDest
0x18004112c  lea     r9, asc_1800C9AE8; "h"
0x180041133  call    StringCopyWorkerW
0x180041138  test    ebp, ebp
0x18004113a  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180041142  lea     r9, [rsp+278h+Name]; lpName
0x180041147  mov     dword ptr [rsp+278h+dwFlags], r15d; dwFlags
0x18004114c  cmovnz  edi, ebp
0x18004114f  mov     edx, ebp; lInitialCount
0x180041151  mov     r8d, edi; lMaximumCount
0x180041154  xor     ecx, ecx; lpSemaphoreAttributes
0x180041156  call    cs:__imp_CreateSemaphoreExW
0x18004115c  mov     rbx, rax
0x18004115f  test    rax, rax
0x180041162  jnz     short loc_180041180
0x180041164  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180041169  mov     ebx, eax
0x18004116b  test    eax, eax
0x18004116d  jns     short loc_180041192
0x18004116f  mov     r8d, eax; char *
0x180041172  mov     ecx, 90h; this
0x180041177  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18004117c  mov     eax, ebx
0x18004117e  jmp     short loc_180041194
0x180041180  call    cs:__imp_GetLastError
0x180041186  lea     rcx, [r14+8]
0x18004118a  mov     rdx, rbx
0x18004118d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180041192  xor     eax, eax
0x180041194  mov     rcx, [rsp+278h+var_38]
0x18004119c  xor     rcx, rsp; StackCookie
0x18004119f  call    __security_check_cookie
0x1800411a4  mov     rbx, [rsp+278h+arg_8]
0x1800411ac  add     rsp, 250h
0x1800411b3  pop     r15
0x1800411b5  pop     r14
0x1800411b7  pop     rdi
0x1800411b8  pop     rsi
0x1800411b9  pop     rbp
0x1800411ba  retn
```

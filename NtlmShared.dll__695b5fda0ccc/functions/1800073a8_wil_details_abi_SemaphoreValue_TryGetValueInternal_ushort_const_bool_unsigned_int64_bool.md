# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800073a8`
- end: `0x180007614`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000321c`
- `0x1800035c0`

## callees

- `0x180004b00`
- `0x1800069b4`
- `0x1800069d4`
- `0x180006f10`
- `0x1800073a8`
- `0x180007c5c`
- `0x18000c560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000743c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800074b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000743c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800074b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007538`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000755a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007538`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000755a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x1800073a8  push    rbp
0x1800073aa  push    rbx
0x1800073ab  push    rsi
0x1800073ac  push    rdi
0x1800073ad  push    r14
0x1800073af  push    r15
0x1800073b1  lea     rbp, [rsp-158h]
0x1800073b9  sub     rsp, 258h
0x1800073c0  mov     rax, cs:__security_cookie
0x1800073c7  xor     rax, rsp
0x1800073ca  mov     [rbp+180h+var_40], rax
0x1800073d1  xor     r15d, r15d
0x1800073d4  lea     rax, [rsp+280h+Name]
0x1800073d9  mov     [r8], r15
0x1800073dc  mov     r14, r8
0x1800073df  mov     edx, 104h
0x1800073e4  mov     r9d, 7FFFFFFEh
0x1800073ea  test    r9, r9
0x1800073ed  jz      short loc_18000740E
0x1800073ef  movzx   r8d, word ptr [rcx]
0x1800073f3  test    r8w, r8w
0x1800073f7  jz      short loc_18000740E
0x1800073f9  mov     [rax], r8w
0x1800073fd  add     rcx, 2
0x180007401  add     rax, 2
0x180007405  dec     r9
0x180007408  sub     rdx, 1; unsigned __int64
0x18000740c  jnz     short loc_1800073EA
0x18000740e  test    rdx, rdx
0x180007411  lea     rcx, [rax-2]
0x180007415  lea     r8, aP0; "_p0"
0x18000741c  cmovnz  rcx, rax
0x180007420  mov     [rcx], r15w
0x180007424  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007429  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000742e  mov     esi, 1F0003h
0x180007433  lea     r8, [rsp+280h+Name]; lpName
0x180007438  mov     ecx, esi; dwDesiredAccess
0x18000743a  xor     edx, edx; bInheritHandle
0x18000743c  call    cs:__imp_OpenSemaphoreW
0x180007442  mov     rbx, rax
0x180007445  test    rax, rax
0x180007448  jz      loc_180007569
0x18000744e  lea     rdx, [rsp+280h+var_25C]; int *
0x180007453  mov     [rsp+280h+var_25C], r15d
0x180007458  mov     rcx, rax; hHandle
0x18000745b  mov     [rsp+280h+var_260], r15d; int
0x180007460  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007465  mov     edi, eax
0x180007467  test    eax, eax
0x180007469  jns     short loc_180007497
0x18000746b  mov     rcx, [rbp+188h]; this
0x180007472  mov     r9d, eax; char *
0x180007475  mov     edx, 0D6h; void *
0x18000747a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000747f  mov     rcx, rbx; hObject
0x180007482  call    cs:__imp_CloseHandle
0x180007488  test    eax, eax
0x18000748a  jz      loc_1800075DE
0x180007490  mov     eax, edi
0x180007492  jmp     loc_180007589
0x180007497  lea     r8, asc_18000EB40; "h"
0x18000749e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800074a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800074a8  lea     r8, [rsp+280h+Name]; lpName
0x1800074ad  xor     edx, edx; bInheritHandle
0x1800074af  mov     ecx, esi; dwDesiredAccess
0x1800074b1  call    cs:__imp_OpenSemaphoreW
0x1800074b7  mov     rdi, rax
0x1800074ba  test    rax, rax
0x1800074bd  jz      loc_180007544
0x1800074c3  lea     rdx, [rsp+280h+var_260]; int *
0x1800074c8  mov     rcx, rax; hHandle
0x1800074cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800074d0  mov     esi, eax
0x1800074d2  test    eax, eax
0x1800074d4  jns     short loc_180007510
0x1800074d6  mov     rcx, [rbp+188h]; this
0x1800074dd  mov     r9d, eax; char *
0x1800074e0  mov     edx, 0DEh; void *
0x1800074e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074ea  mov     rcx, rdi; hObject
0x1800074ed  call    cs:__imp_CloseHandle
0x1800074f3  test    eax, eax
0x1800074f5  jz      loc_1800075F0
0x1800074fb  mov     rcx, rbx; hObject
0x1800074fe  call    cs:__imp_CloseHandle
0x180007504  test    eax, eax
0x180007506  jz      loc_180007602
0x18000750c  mov     eax, esi
0x18000750e  jmp     short loc_180007589
0x180007510  mov     rcx, rdi; hObject
0x180007513  call    cs:__imp_CloseHandle
0x180007519  test    eax, eax
0x18000751b  jz      loc_1800075A8
0x180007521  movsxd  rax, [rsp+280h+var_25C]
0x180007526  movsxd  rcx, [rsp+280h+var_260]
0x18000752b  shl     rcx, 1Fh
0x18000752f  or      rcx, rax
0x180007532  mov     [r14], rcx
0x180007535  mov     rcx, rbx; hObject
0x180007538  call    cs:__imp_CloseHandle
0x18000753e  test    eax, eax
0x180007540  jz      short loc_1800075BA
0x180007542  jmp     short loc_180007574
0x180007544  mov     rcx, [rbp+188h]; this
0x18000754b  mov     edx, 0DCh; void *
0x180007550  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007555  mov     rcx, rbx; hObject
0x180007558  mov     edi, eax
0x18000755a  call    cs:__imp_CloseHandle
0x180007560  test    eax, eax
0x180007562  jz      short loc_1800075CC
0x180007564  jmp     loc_180007490
0x180007569  call    cs:__imp_GetLastError
0x18000756f  cmp     eax, 2
0x180007572  jnz     short loc_180007578
0x180007574  xor     eax, eax
0x180007576  jmp     short loc_180007589
0x180007578  mov     rcx, [rbp+188h]; this
0x18000757f  mov     edx, 0D0h; void *
0x180007584  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007589  mov     rcx, [rbp+180h+var_40]
0x180007590  xor     rcx, rsp; StackCookie
0x180007593  call    __security_check_cookie
0x180007598  add     rsp, 258h
0x18000759f  pop     r15
0x1800075a1  pop     r14
0x1800075a3  pop     rdi
0x1800075a4  pop     rsi
0x1800075a5  pop     rbx
0x1800075a6  pop     rbp
0x1800075a7  retn
0x1800075a8  mov     rcx, [rbp+188h]; this
0x1800075af  mov     edx, 0A0Bh; void *
0x1800075b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075ba  mov     rcx, [rbp+188h]; this
0x1800075c1  mov     edx, 0A0Bh; void *
0x1800075c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075cc  mov     rcx, [rbp+188h]; this
0x1800075d3  mov     edx, 0A0Bh; void *
0x1800075d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075de  mov     rcx, [rbp+188h]; this
0x1800075e5  mov     edx, 0A0Bh; void *
0x1800075ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075f0  mov     rcx, [rbp+188h]; this
0x1800075f7  mov     edx, 0A0Bh; void *
0x1800075fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007602  mov     rcx, [rbp+188h]; this
0x180007609  mov     edx, 0A0Bh; void *
0x18000760e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007348`
- end: `0x1800075b4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800036f4`
- `0x180003a98`

## callees

- `0x1800018e0`
- `0x180004f10`
- `0x180006ac0`
- `0x180006ae0`
- `0x180006efc`
- `0x180007348`
- `0x180007b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007451`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007509`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000748d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000749e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000748d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000749e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074fa`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x180007348  push    rbp
0x18000734a  push    rbx
0x18000734b  push    rsi
0x18000734c  push    rdi
0x18000734d  push    r14
0x18000734f  push    r15
0x180007351  lea     rbp, [rsp-158h]
0x180007359  sub     rsp, 258h
0x180007360  mov     rax, cs:__security_cookie
0x180007367  xor     rax, rsp
0x18000736a  mov     [rbp+180h+var_40], rax
0x180007371  xor     r15d, r15d
0x180007374  lea     rax, [rsp+280h+Name]
0x180007379  mov     [r8], r15
0x18000737c  mov     r14, r8
0x18000737f  mov     edx, 104h
0x180007384  mov     r9d, 7FFFFFFEh
0x18000738a  test    r9, r9
0x18000738d  jz      short loc_1800073AE
0x18000738f  movzx   r8d, word ptr [rcx]
0x180007393  test    r8w, r8w
0x180007397  jz      short loc_1800073AE
0x180007399  mov     [rax], r8w
0x18000739d  add     rcx, 2
0x1800073a1  add     rax, 2
0x1800073a5  dec     r9
0x1800073a8  sub     rdx, 1; unsigned __int64
0x1800073ac  jnz     short loc_18000738A
0x1800073ae  test    rdx, rdx
0x1800073b1  lea     rcx, [rax-2]
0x1800073b5  lea     r8, aP0; "_p0"
0x1800073bc  cmovnz  rcx, rax
0x1800073c0  mov     [rcx], r15w
0x1800073c4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800073c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800073ce  mov     esi, 1F0003h
0x1800073d3  lea     r8, [rsp+280h+Name]; lpName
0x1800073d8  mov     ecx, esi; dwDesiredAccess
0x1800073da  xor     edx, edx; bInheritHandle
0x1800073dc  call    cs:__imp_OpenSemaphoreW
0x1800073e2  mov     rbx, rax
0x1800073e5  test    rax, rax
0x1800073e8  jz      loc_180007509
0x1800073ee  lea     rdx, [rsp+280h+var_25C]; int *
0x1800073f3  mov     [rsp+280h+var_25C], r15d
0x1800073f8  mov     rcx, rax; hHandle
0x1800073fb  mov     [rsp+280h+var_260], r15d; int
0x180007400  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007405  mov     edi, eax
0x180007407  test    eax, eax
0x180007409  jns     short loc_180007437
0x18000740b  mov     rcx, [rbp+188h]; this
0x180007412  mov     r9d, eax; char *
0x180007415  mov     edx, 0D6h; void *
0x18000741a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000741f  mov     rcx, rbx; hObject
0x180007422  call    cs:__imp_CloseHandle
0x180007428  test    eax, eax
0x18000742a  jz      loc_18000757E
0x180007430  mov     eax, edi
0x180007432  jmp     loc_180007529
0x180007437  lea     r8, asc_180029148; "h"
0x18000743e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007443  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007448  lea     r8, [rsp+280h+Name]; lpName
0x18000744d  xor     edx, edx; bInheritHandle
0x18000744f  mov     ecx, esi; dwDesiredAccess
0x180007451  call    cs:__imp_OpenSemaphoreW
0x180007457  mov     rdi, rax
0x18000745a  test    rax, rax
0x18000745d  jz      loc_1800074E4
0x180007463  lea     rdx, [rsp+280h+var_260]; int *
0x180007468  mov     rcx, rax; hHandle
0x18000746b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007470  mov     esi, eax
0x180007472  test    eax, eax
0x180007474  jns     short loc_1800074B0
0x180007476  mov     rcx, [rbp+188h]; this
0x18000747d  mov     r9d, eax; char *
0x180007480  mov     edx, 0DEh; void *
0x180007485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000748a  mov     rcx, rdi; hObject
0x18000748d  call    cs:__imp_CloseHandle
0x180007493  test    eax, eax
0x180007495  jz      loc_180007590
0x18000749b  mov     rcx, rbx; hObject
0x18000749e  call    cs:__imp_CloseHandle
0x1800074a4  test    eax, eax
0x1800074a6  jz      loc_1800075A2
0x1800074ac  mov     eax, esi
0x1800074ae  jmp     short loc_180007529
0x1800074b0  mov     rcx, rdi; hObject
0x1800074b3  call    cs:__imp_CloseHandle
0x1800074b9  test    eax, eax
0x1800074bb  jz      loc_180007548
0x1800074c1  movsxd  rax, [rsp+280h+var_25C]
0x1800074c6  movsxd  rcx, [rsp+280h+var_260]
0x1800074cb  shl     rcx, 1Fh
0x1800074cf  or      rcx, rax
0x1800074d2  mov     [r14], rcx
0x1800074d5  mov     rcx, rbx; hObject
0x1800074d8  call    cs:__imp_CloseHandle
0x1800074de  test    eax, eax
0x1800074e0  jz      short loc_18000755A
0x1800074e2  jmp     short loc_180007514
0x1800074e4  mov     rcx, [rbp+188h]; this
0x1800074eb  mov     edx, 0DCh; void *
0x1800074f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800074f5  mov     rcx, rbx; hObject
0x1800074f8  mov     edi, eax
0x1800074fa  call    cs:__imp_CloseHandle
0x180007500  test    eax, eax
0x180007502  jz      short loc_18000756C
0x180007504  jmp     loc_180007430
0x180007509  call    cs:__imp_GetLastError
0x18000750f  cmp     eax, 2
0x180007512  jnz     short loc_180007518
0x180007514  xor     eax, eax
0x180007516  jmp     short loc_180007529
0x180007518  mov     rcx, [rbp+188h]; this
0x18000751f  mov     edx, 0D0h; void *
0x180007524  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007529  mov     rcx, [rbp+180h+var_40]
0x180007530  xor     rcx, rsp; StackCookie
0x180007533  call    __security_check_cookie
0x180007538  add     rsp, 258h
0x18000753f  pop     r15
0x180007541  pop     r14
0x180007543  pop     rdi
0x180007544  pop     rsi
0x180007545  pop     rbx
0x180007546  pop     rbp
0x180007547  retn
0x180007548  mov     rcx, [rbp+188h]; this
0x18000754f  mov     edx, 0A0Bh; void *
0x180007554  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000755a  mov     rcx, [rbp+188h]; this
0x180007561  mov     edx, 0A0Bh; void *
0x180007566  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000756c  mov     rcx, [rbp+188h]; this
0x180007573  mov     edx, 0A0Bh; void *
0x180007578  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000757e  mov     rcx, [rbp+188h]; this
0x180007585  mov     edx, 0A0Bh; void *
0x18000758a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007590  mov     rcx, [rbp+188h]; this
0x180007597  mov     edx, 0A0Bh; void *
0x18000759c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075a2  mov     rcx, [rbp+188h]; this
0x1800075a9  mov     edx, 0A0Bh; void *
0x1800075ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

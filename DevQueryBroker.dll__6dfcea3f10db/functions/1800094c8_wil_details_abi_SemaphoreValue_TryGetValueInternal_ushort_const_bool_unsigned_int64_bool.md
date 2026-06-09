# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800094c8`
- end: `0x180009734`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000596c`
- `0x180005d10`

## callees

- `0x180007190`
- `0x180008cd0`
- `0x180008cf0`
- `0x180009110`
- `0x1800094c8`
- `0x180009cac`
- `0x18000a1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000955c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800095d1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000955c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800095d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000960d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000961e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000967a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000960d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000961e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000967a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
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
0x1800094c8  push    rbp
0x1800094ca  push    rbx
0x1800094cb  push    rsi
0x1800094cc  push    rdi
0x1800094cd  push    r14
0x1800094cf  push    r15
0x1800094d1  lea     rbp, [rsp-158h]
0x1800094d9  sub     rsp, 258h
0x1800094e0  mov     rax, cs:__security_cookie
0x1800094e7  xor     rax, rsp
0x1800094ea  mov     [rbp+180h+var_40], rax
0x1800094f1  xor     r15d, r15d
0x1800094f4  lea     rax, [rsp+280h+Name]
0x1800094f9  mov     [r8], r15
0x1800094fc  mov     r14, r8
0x1800094ff  mov     edx, 104h
0x180009504  mov     r9d, 7FFFFFFEh
0x18000950a  test    r9, r9
0x18000950d  jz      short loc_18000952E
0x18000950f  movzx   r8d, word ptr [rcx]
0x180009513  test    r8w, r8w
0x180009517  jz      short loc_18000952E
0x180009519  mov     [rax], r8w
0x18000951d  add     rcx, 2
0x180009521  add     rax, 2
0x180009525  dec     r9
0x180009528  sub     rdx, 1; unsigned __int64
0x18000952c  jnz     short loc_18000950A
0x18000952e  test    rdx, rdx
0x180009531  lea     rcx, [rax-2]
0x180009535  lea     r8, aP0; "_p0"
0x18000953c  cmovnz  rcx, rax
0x180009540  mov     [rcx], r15w
0x180009544  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009549  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000954e  mov     esi, 1F0003h
0x180009553  lea     r8, [rsp+280h+Name]; lpName
0x180009558  mov     ecx, esi; dwDesiredAccess
0x18000955a  xor     edx, edx; bInheritHandle
0x18000955c  call    cs:__imp_OpenSemaphoreW
0x180009562  mov     rbx, rax
0x180009565  test    rax, rax
0x180009568  jz      loc_180009689
0x18000956e  lea     rdx, [rsp+280h+var_25C]; int *
0x180009573  mov     [rsp+280h+var_25C], r15d
0x180009578  mov     rcx, rax; hHandle
0x18000957b  mov     [rsp+280h+var_260], r15d; int
0x180009580  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009585  mov     edi, eax
0x180009587  test    eax, eax
0x180009589  jns     short loc_1800095B7
0x18000958b  mov     rcx, [rbp+188h]; this
0x180009592  mov     r9d, eax; char *
0x180009595  mov     edx, 0D6h; void *
0x18000959a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000959f  mov     rcx, rbx; hObject
0x1800095a2  call    cs:__imp_CloseHandle
0x1800095a8  test    eax, eax
0x1800095aa  jz      loc_1800096FE
0x1800095b0  mov     eax, edi
0x1800095b2  jmp     loc_1800096A9
0x1800095b7  lea     r8, asc_18000E800; "h"
0x1800095be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800095c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800095c8  lea     r8, [rsp+280h+Name]; lpName
0x1800095cd  xor     edx, edx; bInheritHandle
0x1800095cf  mov     ecx, esi; dwDesiredAccess
0x1800095d1  call    cs:__imp_OpenSemaphoreW
0x1800095d7  mov     rdi, rax
0x1800095da  test    rax, rax
0x1800095dd  jz      loc_180009664
0x1800095e3  lea     rdx, [rsp+280h+var_260]; int *
0x1800095e8  mov     rcx, rax; hHandle
0x1800095eb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800095f0  mov     esi, eax
0x1800095f2  test    eax, eax
0x1800095f4  jns     short loc_180009630
0x1800095f6  mov     rcx, [rbp+188h]; this
0x1800095fd  mov     r9d, eax; char *
0x180009600  mov     edx, 0DEh; void *
0x180009605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000960a  mov     rcx, rdi; hObject
0x18000960d  call    cs:__imp_CloseHandle
0x180009613  test    eax, eax
0x180009615  jz      loc_180009710
0x18000961b  mov     rcx, rbx; hObject
0x18000961e  call    cs:__imp_CloseHandle
0x180009624  test    eax, eax
0x180009626  jz      loc_180009722
0x18000962c  mov     eax, esi
0x18000962e  jmp     short loc_1800096A9
0x180009630  mov     rcx, rdi; hObject
0x180009633  call    cs:__imp_CloseHandle
0x180009639  test    eax, eax
0x18000963b  jz      loc_1800096C8
0x180009641  movsxd  rax, [rsp+280h+var_25C]
0x180009646  movsxd  rcx, [rsp+280h+var_260]
0x18000964b  shl     rcx, 1Fh
0x18000964f  or      rcx, rax
0x180009652  mov     [r14], rcx
0x180009655  mov     rcx, rbx; hObject
0x180009658  call    cs:__imp_CloseHandle
0x18000965e  test    eax, eax
0x180009660  jz      short loc_1800096DA
0x180009662  jmp     short loc_180009694
0x180009664  mov     rcx, [rbp+188h]; this
0x18000966b  mov     edx, 0DCh; void *
0x180009670  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009675  mov     rcx, rbx; hObject
0x180009678  mov     edi, eax
0x18000967a  call    cs:__imp_CloseHandle
0x180009680  test    eax, eax
0x180009682  jz      short loc_1800096EC
0x180009684  jmp     loc_1800095B0
0x180009689  call    cs:__imp_GetLastError
0x18000968f  cmp     eax, 2
0x180009692  jnz     short loc_180009698
0x180009694  xor     eax, eax
0x180009696  jmp     short loc_1800096A9
0x180009698  mov     rcx, [rbp+188h]; this
0x18000969f  mov     edx, 0D0h; void *
0x1800096a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800096a9  mov     rcx, [rbp+180h+var_40]
0x1800096b0  xor     rcx, rsp; StackCookie
0x1800096b3  call    __security_check_cookie
0x1800096b8  add     rsp, 258h
0x1800096bf  pop     r15
0x1800096c1  pop     r14
0x1800096c3  pop     rdi
0x1800096c4  pop     rsi
0x1800096c5  pop     rbx
0x1800096c6  pop     rbp
0x1800096c7  retn
0x1800096c8  mov     rcx, [rbp+188h]; this
0x1800096cf  mov     edx, 0A0Bh; void *
0x1800096d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096da  mov     rcx, [rbp+188h]; this
0x1800096e1  mov     edx, 0A0Bh; void *
0x1800096e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096ec  mov     rcx, [rbp+188h]; this
0x1800096f3  mov     edx, 0A0Bh; void *
0x1800096f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096fe  mov     rcx, [rbp+188h]; this
0x180009705  mov     edx, 0A0Bh; void *
0x18000970a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009710  mov     rcx, [rbp+188h]; this
0x180009717  mov     edx, 0A0Bh; void *
0x18000971c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009722  mov     rcx, [rbp+188h]; this
0x180009729  mov     edx, 0A0Bh; void *
0x18000972e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

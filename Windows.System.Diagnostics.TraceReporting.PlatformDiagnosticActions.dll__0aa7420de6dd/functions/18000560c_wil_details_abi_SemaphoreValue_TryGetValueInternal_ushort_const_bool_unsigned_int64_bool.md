# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000560c`
- end: `0x180005886`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003018`

## callees

- `0x1800016a0`
- `0x180003fa4`
- `0x180004ba4`
- `0x180004bc4`
- `0x1800054a0`
- `0x18000560c`
- `0x1800059dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800056a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000571c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800056a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000571c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000575f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000575f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057cc`

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
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000560c  push    rbp
0x18000560e  push    rbx
0x18000560f  push    rsi
0x180005610  push    rdi
0x180005611  push    r14
0x180005613  push    r15
0x180005615  lea     rbp, [rsp-158h]
0x18000561d  sub     rsp, 258h
0x180005624  mov     rax, cs:__security_cookie
0x18000562b  xor     rax, rsp
0x18000562e  mov     [rbp+180h+var_40], rax
0x180005635  xor     r15d, r15d
0x180005638  lea     rax, [rsp+280h+Name]
0x18000563d  mov     [r8], r15
0x180005640  mov     r14, r8
0x180005643  mov     edx, 104h
0x180005648  mov     r9d, 7FFFFFFEh
0x18000564e  test    r9, r9
0x180005651  jz      short loc_180005672
0x180005653  movzx   r8d, word ptr [rcx]
0x180005657  test    r8w, r8w
0x18000565b  jz      short loc_180005672
0x18000565d  mov     [rax], r8w
0x180005661  add     rcx, 2
0x180005665  add     rax, 2
0x180005669  dec     r9
0x18000566c  sub     rdx, 1; unsigned __int64
0x180005670  jnz     short loc_18000564E
0x180005672  test    rdx, rdx
0x180005675  lea     rcx, [rax-2]
0x180005679  lea     r8, aP0; "_p0"
0x180005680  cmovnz  rcx, rax
0x180005684  mov     [rcx], r15w
0x180005688  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000568d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005692  mov     esi, 1F0003h
0x180005697  lea     r8, [rsp+280h+Name]; lpName
0x18000569c  mov     ecx, esi; dwDesiredAccess
0x18000569e  xor     edx, edx; bInheritHandle
0x1800056a0  call    cs:__imp_OpenSemaphoreW
0x1800056a6  mov     rbx, rax
0x1800056a9  test    rax, rax
0x1800056ac  jz      loc_1800057DB
0x1800056b2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800056b7  mov     [rsp+280h+var_25C], r15d
0x1800056bc  mov     rcx, rax; hHandle
0x1800056bf  mov     [rsp+280h+var_260], r15d; int
0x1800056c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800056c9  mov     edi, eax
0x1800056cb  test    eax, eax
0x1800056cd  jns     short loc_180005702
0x1800056cf  mov     rcx, [rbp+188h]; this
0x1800056d6  lea     r8, aWil; "wil"
0x1800056dd  mov     r9d, eax; char *
0x1800056e0  mov     edx, 0D6h; void *
0x1800056e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056ea  mov     rcx, rbx; hObject
0x1800056ed  call    cs:__imp_CloseHandle
0x1800056f3  test    eax, eax
0x1800056f5  jz      loc_180005850
0x1800056fb  mov     eax, edi
0x1800056fd  jmp     loc_1800057FB
0x180005702  lea     r8, asc_18000FBA8; "h"
0x180005709  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000570e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005713  lea     r8, [rsp+280h+Name]; lpName
0x180005718  xor     edx, edx; bInheritHandle
0x18000571a  mov     ecx, esi; dwDesiredAccess
0x18000571c  call    cs:__imp_OpenSemaphoreW
0x180005722  mov     rdi, rax
0x180005725  test    rax, rax
0x180005728  jz      loc_1800057B6
0x18000572e  lea     rdx, [rsp+280h+var_260]; int *
0x180005733  mov     rcx, rax; hHandle
0x180005736  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000573b  mov     esi, eax
0x18000573d  test    eax, eax
0x18000573f  jns     short loc_180005782
0x180005741  mov     rcx, [rbp+188h]; this
0x180005748  lea     r8, aWil; "wil"
0x18000574f  mov     r9d, eax; char *
0x180005752  mov     edx, 0DEh; void *
0x180005757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000575c  mov     rcx, rdi; hObject
0x18000575f  call    cs:__imp_CloseHandle
0x180005765  test    eax, eax
0x180005767  jz      loc_180005862
0x18000576d  mov     rcx, rbx; hObject
0x180005770  call    cs:__imp_CloseHandle
0x180005776  test    eax, eax
0x180005778  jz      loc_180005874
0x18000577e  mov     eax, esi
0x180005780  jmp     short loc_1800057FB
0x180005782  mov     rcx, rdi; hObject
0x180005785  call    cs:__imp_CloseHandle
0x18000578b  test    eax, eax
0x18000578d  jz      loc_18000581A
0x180005793  movsxd  rax, [rsp+280h+var_25C]
0x180005798  movsxd  rcx, [rsp+280h+var_260]
0x18000579d  shl     rcx, 1Fh
0x1800057a1  or      rcx, rax
0x1800057a4  mov     [r14], rcx
0x1800057a7  mov     rcx, rbx; hObject
0x1800057aa  call    cs:__imp_CloseHandle
0x1800057b0  test    eax, eax
0x1800057b2  jz      short loc_18000582C
0x1800057b4  jmp     short loc_1800057E6
0x1800057b6  mov     rcx, [rbp+188h]; this
0x1800057bd  mov     edx, 0DCh; void *
0x1800057c2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800057c7  mov     rcx, rbx; hObject
0x1800057ca  mov     edi, eax
0x1800057cc  call    cs:__imp_CloseHandle
0x1800057d2  test    eax, eax
0x1800057d4  jz      short loc_18000583E
0x1800057d6  jmp     loc_1800056FB
0x1800057db  call    cs:__imp_GetLastError
0x1800057e1  cmp     eax, 2
0x1800057e4  jnz     short loc_1800057EA
0x1800057e6  xor     eax, eax
0x1800057e8  jmp     short loc_1800057FB
0x1800057ea  mov     rcx, [rbp+188h]; this
0x1800057f1  mov     edx, 0D0h; void *
0x1800057f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800057fb  mov     rcx, [rbp+180h+var_40]
0x180005802  xor     rcx, rsp; StackCookie
0x180005805  call    __security_check_cookie
0x18000580a  add     rsp, 258h
0x180005811  pop     r15
0x180005813  pop     r14
0x180005815  pop     rdi
0x180005816  pop     rsi
0x180005817  pop     rbx
0x180005818  pop     rbp
0x180005819  retn
0x18000581a  mov     rcx, [rbp+188h]; this
0x180005821  mov     edx, 0A0Bh; void *
0x180005826  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000582c  mov     rcx, [rbp+188h]; this
0x180005833  mov     edx, 0A0Bh; void *
0x180005838  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000583e  mov     rcx, [rbp+188h]; this
0x180005845  mov     edx, 0A0Bh; void *
0x18000584a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005850  mov     rcx, [rbp+188h]; this
0x180005857  mov     edx, 0A0Bh; void *
0x18000585c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005862  mov     rcx, [rbp+188h]; this
0x180005869  mov     edx, 0A0Bh; void *
0x18000586e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005874  mov     rcx, [rbp+188h]; this
0x18000587b  mov     edx, 0A0Bh; void *
0x180005880  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000948c`
- end: `0x18000971b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006df8`
- `0x180039194`

## callees

- `0x180003a60`
- `0x180007e44`
- `0x1800089c4`
- `0x1800089e4`
- `0x180009324`
- `0x18000948c`
- `0x18000987c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009520`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000959c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009520`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000959c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000956d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000962d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000965a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000956d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000962d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000965a`

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
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000948c  push    rbp
0x18000948e  push    rbx
0x18000948f  push    rsi
0x180009490  push    rdi
0x180009491  push    r14
0x180009493  push    r15
0x180009495  lea     rbp, [rsp-158h]
0x18000949d  sub     rsp, 258h
0x1800094a4  mov     rax, cs:__security_cookie
0x1800094ab  xor     rax, rsp
0x1800094ae  mov     [rbp+180h+var_40], rax
0x1800094b5  xor     r15d, r15d
0x1800094b8  lea     rax, [rsp+280h+Name]
0x1800094bd  mov     [r8], r15
0x1800094c0  mov     r14, r8
0x1800094c3  mov     edx, 104h
0x1800094c8  mov     r9d, 7FFFFFFEh
0x1800094ce  test    r9, r9
0x1800094d1  jz      short loc_1800094F2
0x1800094d3  movzx   r8d, word ptr [rcx]
0x1800094d7  test    r8w, r8w
0x1800094db  jz      short loc_1800094F2
0x1800094dd  mov     [rax], r8w
0x1800094e1  add     rcx, 2
0x1800094e5  add     rax, 2
0x1800094e9  dec     r9
0x1800094ec  sub     rdx, 1; unsigned __int64
0x1800094f0  jnz     short loc_1800094CE
0x1800094f2  test    rdx, rdx
0x1800094f5  lea     rcx, [rax-2]
0x1800094f9  lea     r8, aP0; "_p0"
0x180009500  cmovnz  rcx, rax
0x180009504  mov     [rcx], r15w
0x180009508  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000950d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009512  mov     esi, 1F0003h
0x180009517  lea     r8, [rsp+280h+Name]; lpName
0x18000951c  mov     ecx, esi; dwDesiredAccess
0x18000951e  xor     edx, edx; bInheritHandle
0x180009520  call    cs:__imp_OpenSemaphoreW
0x180009526  mov     rbx, rax
0x180009529  test    rax, rax
0x18000952c  jz      loc_180009669
0x180009532  lea     rdx, [rsp+280h+var_25C]; int *
0x180009537  mov     [rsp+280h+var_25C], r15d
0x18000953c  mov     rcx, rax; hHandle
0x18000953f  mov     [rsp+280h+var_260], r15d; int
0x180009544  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009549  mov     edi, eax
0x18000954b  test    eax, eax
0x18000954d  jns     short loc_180009582
0x18000954f  mov     rcx, [rbp+188h]; this
0x180009556  lea     r8, aWil; "wil"
0x18000955d  mov     r9d, eax; char *
0x180009560  mov     edx, 0D6h; void *
0x180009565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000956a  mov     rcx, rbx; hObject
0x18000956d  call    cs:__imp_CloseHandle
0x180009573  test    eax, eax
0x180009575  jz      loc_1800096E5
0x18000957b  mov     eax, edi
0x18000957d  jmp     loc_180009690
0x180009582  lea     r8, asc_180073990; "h"
0x180009589  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000958e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009593  lea     r8, [rsp+280h+Name]; lpName
0x180009598  xor     edx, edx; bInheritHandle
0x18000959a  mov     ecx, esi; dwDesiredAccess
0x18000959c  call    cs:__imp_OpenSemaphoreW
0x1800095a2  mov     rdi, rax
0x1800095a5  test    rax, rax
0x1800095a8  jz      loc_18000963D
0x1800095ae  lea     rdx, [rsp+280h+var_260]; int *
0x1800095b3  mov     rcx, rax; hHandle
0x1800095b6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800095bb  mov     esi, eax
0x1800095bd  test    eax, eax
0x1800095bf  jns     short loc_180009605
0x1800095c1  mov     rcx, [rbp+188h]; this
0x1800095c8  lea     r8, aWil; "wil"
0x1800095cf  mov     r9d, eax; char *
0x1800095d2  mov     edx, 0DEh; void *
0x1800095d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095dc  mov     rcx, rdi; hObject
0x1800095df  call    cs:__imp_CloseHandle
0x1800095e5  test    eax, eax
0x1800095e7  jz      loc_1800096F7
0x1800095ed  mov     rcx, rbx; hObject
0x1800095f0  call    cs:__imp_CloseHandle
0x1800095f6  test    eax, eax
0x1800095f8  jz      loc_180009709
0x1800095fe  mov     eax, esi
0x180009600  jmp     loc_180009690
0x180009605  mov     rcx, rdi; hObject
0x180009608  call    cs:__imp_CloseHandle
0x18000960e  test    eax, eax
0x180009610  jz      loc_1800096AF
0x180009616  movsxd  rax, [rsp+280h+var_25C]
0x18000961b  movsxd  rcx, [rsp+280h+var_260]
0x180009620  shl     rcx, 1Fh
0x180009624  or      rcx, rax
0x180009627  mov     [r14], rcx
0x18000962a  mov     rcx, rbx; hObject
0x18000962d  call    cs:__imp_CloseHandle
0x180009633  test    eax, eax
0x180009635  jz      loc_1800096C1
0x18000963b  jmp     short loc_180009674
0x18000963d  mov     rcx, [rbp+188h]; this
0x180009644  lea     r8, aWil; "wil"
0x18000964b  mov     edx, 0DCh; void *
0x180009650  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009655  mov     rcx, rbx; hObject
0x180009658  mov     edi, eax
0x18000965a  call    cs:__imp_CloseHandle
0x180009660  test    eax, eax
0x180009662  jz      short loc_1800096D3
0x180009664  jmp     loc_18000957B
0x180009669  call    cs:__imp_GetLastError
0x18000966f  cmp     eax, 2
0x180009672  jnz     short loc_180009678
0x180009674  xor     eax, eax
0x180009676  jmp     short loc_180009690
0x180009678  mov     rcx, [rbp+188h]; this
0x18000967f  lea     r8, aWil; "wil"
0x180009686  mov     edx, 0D0h; void *
0x18000968b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009690  mov     rcx, [rbp+180h+var_40]
0x180009697  xor     rcx, rsp; StackCookie
0x18000969a  call    __security_check_cookie
0x18000969f  add     rsp, 258h
0x1800096a6  pop     r15
0x1800096a8  pop     r14
0x1800096aa  pop     rdi
0x1800096ab  pop     rsi
0x1800096ac  pop     rbx
0x1800096ad  pop     rbp
0x1800096ae  retn
0x1800096af  mov     rcx, [rbp+188h]; this
0x1800096b6  mov     edx, 0A0Bh; void *
0x1800096bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096c1  mov     rcx, [rbp+188h]; this
0x1800096c8  mov     edx, 0A0Bh; void *
0x1800096cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096d3  mov     rcx, [rbp+188h]; this
0x1800096da  mov     edx, 0A0Bh; void *
0x1800096df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096e5  mov     rcx, [rbp+188h]; this
0x1800096ec  mov     edx, 0A0Bh; void *
0x1800096f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096f7  mov     rcx, [rbp+188h]; this
0x1800096fe  mov     edx, 0A0Bh; void *
0x180009703  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009709  mov     rcx, [rbp+188h]; this
0x180009710  mov     edx, 0A0Bh; void *
0x180009715  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

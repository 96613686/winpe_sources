# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000964c`
- end: `0x1800098b8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004df8`
- `0x18000519c`

## callees

- `0x1800026f0`
- `0x180006724`
- `0x1800086a4`
- `0x1800086cc`
- `0x180009134`
- `0x18000964c`
- `0x180009f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800096e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009755`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800096e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000980d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000980d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009726`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009726`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000964c  push    rbp
0x18000964e  push    rbx
0x18000964f  push    rsi
0x180009650  push    rdi
0x180009651  push    r14
0x180009653  push    r15
0x180009655  lea     rbp, [rsp-158h]
0x18000965d  sub     rsp, 258h
0x180009664  mov     rax, cs:__security_cookie
0x18000966b  xor     rax, rsp
0x18000966e  mov     [rbp+180h+var_40], rax
0x180009675  xor     r15d, r15d
0x180009678  lea     rax, [rsp+280h+Name]
0x18000967d  mov     [r8], r15
0x180009680  mov     r14, r8
0x180009683  mov     edx, 104h
0x180009688  mov     r9d, 7FFFFFFEh
0x18000968e  test    r9, r9
0x180009691  jz      short loc_1800096B2
0x180009693  movzx   r8d, word ptr [rcx]
0x180009697  test    r8w, r8w
0x18000969b  jz      short loc_1800096B2
0x18000969d  mov     [rax], r8w
0x1800096a1  add     rcx, 2
0x1800096a5  add     rax, 2
0x1800096a9  dec     r9
0x1800096ac  sub     rdx, 1; unsigned __int64
0x1800096b0  jnz     short loc_18000968E
0x1800096b2  test    rdx, rdx
0x1800096b5  lea     rcx, [rax-2]
0x1800096b9  lea     r8, aP0; "_p0"
0x1800096c0  cmovnz  rcx, rax
0x1800096c4  mov     [rcx], r15w
0x1800096c8  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800096cd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800096d2  mov     esi, 1F0003h
0x1800096d7  lea     r8, [rsp+280h+Name]; lpName
0x1800096dc  mov     ecx, esi; dwDesiredAccess
0x1800096de  xor     edx, edx; bInheritHandle
0x1800096e0  call    cs:__imp_OpenSemaphoreW
0x1800096e6  mov     rbx, rax
0x1800096e9  test    rax, rax
0x1800096ec  jz      loc_18000980D
0x1800096f2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800096f7  mov     [rsp+280h+var_25C], r15d
0x1800096fc  mov     rcx, rax; hHandle
0x1800096ff  mov     [rsp+280h+var_260], r15d; int
0x180009704  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009709  mov     edi, eax
0x18000970b  test    eax, eax
0x18000970d  jns     short loc_18000973B
0x18000970f  mov     rcx, [rbp+188h]; this
0x180009716  mov     r9d, eax; char *
0x180009719  mov     edx, 0D6h; void *
0x18000971e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009723  mov     rcx, rbx; hObject
0x180009726  call    cs:__imp_CloseHandle
0x18000972c  test    eax, eax
0x18000972e  jz      loc_180009882
0x180009734  mov     eax, edi
0x180009736  jmp     loc_18000982D
0x18000973b  lea     r8, asc_18001AC50; "h"
0x180009742  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180009747  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000974c  lea     r8, [rsp+280h+Name]; lpName
0x180009751  xor     edx, edx; bInheritHandle
0x180009753  mov     ecx, esi; dwDesiredAccess
0x180009755  call    cs:__imp_OpenSemaphoreW
0x18000975b  mov     rdi, rax
0x18000975e  test    rax, rax
0x180009761  jz      loc_1800097E8
0x180009767  lea     rdx, [rsp+280h+var_260]; int *
0x18000976c  mov     rcx, rax; hHandle
0x18000976f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009774  mov     esi, eax
0x180009776  test    eax, eax
0x180009778  jns     short loc_1800097B4
0x18000977a  mov     rcx, [rbp+188h]; this
0x180009781  mov     r9d, eax; char *
0x180009784  mov     edx, 0DEh; void *
0x180009789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000978e  mov     rcx, rdi; hObject
0x180009791  call    cs:__imp_CloseHandle
0x180009797  test    eax, eax
0x180009799  jz      loc_180009894
0x18000979f  mov     rcx, rbx; hObject
0x1800097a2  call    cs:__imp_CloseHandle
0x1800097a8  test    eax, eax
0x1800097aa  jz      loc_1800098A6
0x1800097b0  mov     eax, esi
0x1800097b2  jmp     short loc_18000982D
0x1800097b4  mov     rcx, rdi; hObject
0x1800097b7  call    cs:__imp_CloseHandle
0x1800097bd  test    eax, eax
0x1800097bf  jz      loc_18000984C
0x1800097c5  movsxd  rax, [rsp+280h+var_25C]
0x1800097ca  movsxd  rcx, [rsp+280h+var_260]
0x1800097cf  shl     rcx, 1Fh
0x1800097d3  or      rcx, rax
0x1800097d6  mov     [r14], rcx
0x1800097d9  mov     rcx, rbx; hObject
0x1800097dc  call    cs:__imp_CloseHandle
0x1800097e2  test    eax, eax
0x1800097e4  jz      short loc_18000985E
0x1800097e6  jmp     short loc_180009818
0x1800097e8  mov     rcx, [rbp+188h]; this
0x1800097ef  mov     edx, 0DCh; void *
0x1800097f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800097f9  mov     rcx, rbx; hObject
0x1800097fc  mov     edi, eax
0x1800097fe  call    cs:__imp_CloseHandle
0x180009804  test    eax, eax
0x180009806  jz      short loc_180009870
0x180009808  jmp     loc_180009734
0x18000980d  call    cs:__imp_GetLastError
0x180009813  cmp     eax, 2
0x180009816  jnz     short loc_18000981C
0x180009818  xor     eax, eax
0x18000981a  jmp     short loc_18000982D
0x18000981c  mov     rcx, [rbp+188h]; this
0x180009823  mov     edx, 0D0h; void *
0x180009828  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000982d  mov     rcx, [rbp+180h+var_40]
0x180009834  xor     rcx, rsp; StackCookie
0x180009837  call    __security_check_cookie
0x18000983c  add     rsp, 258h
0x180009843  pop     r15
0x180009845  pop     r14
0x180009847  pop     rdi
0x180009848  pop     rsi
0x180009849  pop     rbx
0x18000984a  pop     rbp
0x18000984b  retn
0x18000984c  mov     rcx, [rbp+188h]; this
0x180009853  mov     edx, 0A0Bh; void *
0x180009858  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000985e  mov     rcx, [rbp+188h]; this
0x180009865  mov     edx, 0A0Bh; void *
0x18000986a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009870  mov     rcx, [rbp+188h]; this
0x180009877  mov     edx, 0A0Bh; void *
0x18000987c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009882  mov     rcx, [rbp+188h]; this
0x180009889  mov     edx, 0A0Bh; void *
0x18000988e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009894  mov     rcx, [rbp+188h]; this
0x18000989b  mov     edx, 0A0Bh; void *
0x1800098a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098a6  mov     rcx, [rbp+188h]; this
0x1800098ad  mov     edx, 0A0Bh; void *
0x1800098b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

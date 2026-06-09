# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000930c`
- end: `0x180009578`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004988`
- `0x180004d38`

## callees

- `0x180001d40`
- `0x180006284`
- `0x180008394`
- `0x1800083b4`
- `0x180008df8`
- `0x18000930c`
- `0x180009bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000949c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000949c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094be`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800093a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009415`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800093a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009415`

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
0x18000930c  push    rbp
0x18000930e  push    rbx
0x18000930f  push    rsi
0x180009310  push    rdi
0x180009311  push    r14
0x180009313  push    r15
0x180009315  lea     rbp, [rsp-158h]
0x18000931d  sub     rsp, 258h
0x180009324  mov     rax, cs:__security_cookie
0x18000932b  xor     rax, rsp
0x18000932e  mov     [rbp+180h+var_40], rax
0x180009335  xor     r15d, r15d
0x180009338  lea     rax, [rsp+280h+Name]
0x18000933d  mov     [r8], r15
0x180009340  mov     r14, r8
0x180009343  mov     edx, 104h
0x180009348  mov     r9d, 7FFFFFFEh
0x18000934e  test    r9, r9
0x180009351  jz      short loc_180009372
0x180009353  movzx   r8d, word ptr [rcx]
0x180009357  test    r8w, r8w
0x18000935b  jz      short loc_180009372
0x18000935d  mov     [rax], r8w
0x180009361  add     rcx, 2
0x180009365  add     rax, 2
0x180009369  dec     r9
0x18000936c  sub     rdx, 1; unsigned __int64
0x180009370  jnz     short loc_18000934E
0x180009372  test    rdx, rdx
0x180009375  lea     rcx, [rax-2]
0x180009379  lea     r8, aP0; "_p0"
0x180009380  cmovnz  rcx, rax
0x180009384  mov     [rcx], r15w
0x180009388  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000938d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009392  mov     esi, 1F0003h
0x180009397  lea     r8, [rsp+280h+Name]; lpName
0x18000939c  mov     ecx, esi; dwDesiredAccess
0x18000939e  xor     edx, edx; bInheritHandle
0x1800093a0  call    cs:__imp_OpenSemaphoreW
0x1800093a6  mov     rbx, rax
0x1800093a9  test    rax, rax
0x1800093ac  jz      loc_1800094CD
0x1800093b2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800093b7  mov     [rsp+280h+var_25C], r15d
0x1800093bc  mov     rcx, rax; hHandle
0x1800093bf  mov     [rsp+280h+var_260], r15d; int
0x1800093c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800093c9  mov     edi, eax
0x1800093cb  test    eax, eax
0x1800093cd  jns     short loc_1800093FB
0x1800093cf  mov     rcx, [rbp+188h]; this
0x1800093d6  mov     r9d, eax; char *
0x1800093d9  mov     edx, 0D6h; void *
0x1800093de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800093e3  mov     rcx, rbx; hObject
0x1800093e6  call    cs:__imp_CloseHandle
0x1800093ec  test    eax, eax
0x1800093ee  jz      loc_180009542
0x1800093f4  mov     eax, edi
0x1800093f6  jmp     loc_1800094ED
0x1800093fb  lea     r8, asc_18001B8A0; "h"
0x180009402  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009407  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000940c  lea     r8, [rsp+280h+Name]; lpName
0x180009411  xor     edx, edx; bInheritHandle
0x180009413  mov     ecx, esi; dwDesiredAccess
0x180009415  call    cs:__imp_OpenSemaphoreW
0x18000941b  mov     rdi, rax
0x18000941e  test    rax, rax
0x180009421  jz      loc_1800094A8
0x180009427  lea     rdx, [rsp+280h+var_260]; int *
0x18000942c  mov     rcx, rax; hHandle
0x18000942f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009434  mov     esi, eax
0x180009436  test    eax, eax
0x180009438  jns     short loc_180009474
0x18000943a  mov     rcx, [rbp+188h]; this
0x180009441  mov     r9d, eax; char *
0x180009444  mov     edx, 0DEh; void *
0x180009449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000944e  mov     rcx, rdi; hObject
0x180009451  call    cs:__imp_CloseHandle
0x180009457  test    eax, eax
0x180009459  jz      loc_180009554
0x18000945f  mov     rcx, rbx; hObject
0x180009462  call    cs:__imp_CloseHandle
0x180009468  test    eax, eax
0x18000946a  jz      loc_180009566
0x180009470  mov     eax, esi
0x180009472  jmp     short loc_1800094ED
0x180009474  mov     rcx, rdi; hObject
0x180009477  call    cs:__imp_CloseHandle
0x18000947d  test    eax, eax
0x18000947f  jz      loc_18000950C
0x180009485  movsxd  rax, [rsp+280h+var_25C]
0x18000948a  movsxd  rcx, [rsp+280h+var_260]
0x18000948f  shl     rcx, 1Fh
0x180009493  or      rcx, rax
0x180009496  mov     [r14], rcx
0x180009499  mov     rcx, rbx; hObject
0x18000949c  call    cs:__imp_CloseHandle
0x1800094a2  test    eax, eax
0x1800094a4  jz      short loc_18000951E
0x1800094a6  jmp     short loc_1800094D8
0x1800094a8  mov     rcx, [rbp+188h]; this
0x1800094af  mov     edx, 0DCh; void *
0x1800094b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800094b9  mov     rcx, rbx; hObject
0x1800094bc  mov     edi, eax
0x1800094be  call    cs:__imp_CloseHandle
0x1800094c4  test    eax, eax
0x1800094c6  jz      short loc_180009530
0x1800094c8  jmp     loc_1800093F4
0x1800094cd  call    cs:__imp_GetLastError
0x1800094d3  cmp     eax, 2
0x1800094d6  jnz     short loc_1800094DC
0x1800094d8  xor     eax, eax
0x1800094da  jmp     short loc_1800094ED
0x1800094dc  mov     rcx, [rbp+188h]; this
0x1800094e3  mov     edx, 0D0h; void *
0x1800094e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800094ed  mov     rcx, [rbp+180h+var_40]
0x1800094f4  xor     rcx, rsp; StackCookie
0x1800094f7  call    __security_check_cookie
0x1800094fc  add     rsp, 258h
0x180009503  pop     r15
0x180009505  pop     r14
0x180009507  pop     rdi
0x180009508  pop     rsi
0x180009509  pop     rbx
0x18000950a  pop     rbp
0x18000950b  retn
0x18000950c  mov     rcx, [rbp+188h]; this
0x180009513  mov     edx, 0A0Bh; void *
0x180009518  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000951e  mov     rcx, [rbp+188h]; this
0x180009525  mov     edx, 0A0Bh; void *
0x18000952a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009530  mov     rcx, [rbp+188h]; this
0x180009537  mov     edx, 0A0Bh; void *
0x18000953c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009542  mov     rcx, [rbp+188h]; this
0x180009549  mov     edx, 0A0Bh; void *
0x18000954e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009554  mov     rcx, [rbp+188h]; this
0x18000955b  mov     edx, 0A0Bh; void *
0x180009560  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009566  mov     rcx, [rbp+188h]; this
0x18000956d  mov     edx, 0A0Bh; void *
0x180009572  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

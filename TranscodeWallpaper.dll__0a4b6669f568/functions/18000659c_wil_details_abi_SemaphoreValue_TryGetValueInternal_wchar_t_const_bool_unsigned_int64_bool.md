# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000659c`
- end: `0x18000682b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003e88`
- `0x180007c8c`

## callees

- `0x180002170`
- `0x180004ec4`
- `0x180005ab4`
- `0x180005ad4`
- `0x180006414`
- `0x18000659c`
- `0x18000698c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006630`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800066ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006630`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800066ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000667d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000673d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000676a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000667d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000673d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000676a`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000659c  push    rbp
0x18000659e  push    rbx
0x18000659f  push    rsi
0x1800065a0  push    rdi
0x1800065a1  push    r14
0x1800065a3  push    r15
0x1800065a5  lea     rbp, [rsp-158h]
0x1800065ad  sub     rsp, 258h
0x1800065b4  mov     rax, cs:__security_cookie
0x1800065bb  xor     rax, rsp
0x1800065be  mov     [rbp+180h+var_40], rax
0x1800065c5  xor     r15d, r15d
0x1800065c8  lea     rax, [rsp+280h+Name]
0x1800065cd  mov     [r8], r15
0x1800065d0  mov     r14, r8
0x1800065d3  mov     edx, 104h
0x1800065d8  mov     r9d, 7FFFFFFEh
0x1800065de  test    r9, r9
0x1800065e1  jz      short loc_180006602
0x1800065e3  movzx   r8d, word ptr [rcx]
0x1800065e7  test    r8w, r8w
0x1800065eb  jz      short loc_180006602
0x1800065ed  mov     [rax], r8w
0x1800065f1  add     rcx, 2
0x1800065f5  add     rax, 2
0x1800065f9  dec     r9
0x1800065fc  sub     rdx, 1; unsigned __int64
0x180006600  jnz     short loc_1800065DE
0x180006602  test    rdx, rdx
0x180006605  lea     rcx, [rax-2]
0x180006609  lea     r8, aP0; "_p0"
0x180006610  cmovnz  rcx, rax
0x180006614  mov     [rcx], r15w
0x180006618  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000661d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006622  mov     esi, 1F0003h
0x180006627  lea     r8, [rsp+280h+Name]; lpName
0x18000662c  mov     ecx, esi; dwDesiredAccess
0x18000662e  xor     edx, edx; bInheritHandle
0x180006630  call    cs:__imp_OpenSemaphoreW
0x180006636  mov     rbx, rax
0x180006639  test    rax, rax
0x18000663c  jz      loc_180006779
0x180006642  lea     rdx, [rsp+280h+var_25C]; int *
0x180006647  mov     [rsp+280h+var_25C], r15d
0x18000664c  mov     rcx, rax; hHandle
0x18000664f  mov     [rsp+280h+var_260], r15d; int
0x180006654  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006659  mov     edi, eax
0x18000665b  test    eax, eax
0x18000665d  jns     short loc_180006692
0x18000665f  mov     rcx, [rbp+188h]; this
0x180006666  lea     r8, aWil; "wil"
0x18000666d  mov     r9d, eax; char *
0x180006670  mov     edx, 0D6h; void *
0x180006675  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000667a  mov     rcx, rbx; hObject
0x18000667d  call    cs:__imp_CloseHandle
0x180006683  test    eax, eax
0x180006685  jz      loc_1800067F5
0x18000668b  mov     eax, edi
0x18000668d  jmp     loc_1800067A0
0x180006692  lea     r8, asc_1800113E0; "h"
0x180006699  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000669e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800066a3  lea     r8, [rsp+280h+Name]; lpName
0x1800066a8  xor     edx, edx; bInheritHandle
0x1800066aa  mov     ecx, esi; dwDesiredAccess
0x1800066ac  call    cs:__imp_OpenSemaphoreW
0x1800066b2  mov     rdi, rax
0x1800066b5  test    rax, rax
0x1800066b8  jz      loc_18000674D
0x1800066be  lea     rdx, [rsp+280h+var_260]; int *
0x1800066c3  mov     rcx, rax; hHandle
0x1800066c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800066cb  mov     esi, eax
0x1800066cd  test    eax, eax
0x1800066cf  jns     short loc_180006715
0x1800066d1  mov     rcx, [rbp+188h]; this
0x1800066d8  lea     r8, aWil; "wil"
0x1800066df  mov     r9d, eax; char *
0x1800066e2  mov     edx, 0DEh; void *
0x1800066e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066ec  mov     rcx, rdi; hObject
0x1800066ef  call    cs:__imp_CloseHandle
0x1800066f5  test    eax, eax
0x1800066f7  jz      loc_180006807
0x1800066fd  mov     rcx, rbx; hObject
0x180006700  call    cs:__imp_CloseHandle
0x180006706  test    eax, eax
0x180006708  jz      loc_180006819
0x18000670e  mov     eax, esi
0x180006710  jmp     loc_1800067A0
0x180006715  mov     rcx, rdi; hObject
0x180006718  call    cs:__imp_CloseHandle
0x18000671e  test    eax, eax
0x180006720  jz      loc_1800067BF
0x180006726  movsxd  rax, [rsp+280h+var_25C]
0x18000672b  movsxd  rcx, [rsp+280h+var_260]
0x180006730  shl     rcx, 1Fh
0x180006734  or      rcx, rax
0x180006737  mov     [r14], rcx
0x18000673a  mov     rcx, rbx; hObject
0x18000673d  call    cs:__imp_CloseHandle
0x180006743  test    eax, eax
0x180006745  jz      loc_1800067D1
0x18000674b  jmp     short loc_180006784
0x18000674d  mov     rcx, [rbp+188h]; this
0x180006754  lea     r8, aWil; "wil"
0x18000675b  mov     edx, 0DCh; void *
0x180006760  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006765  mov     rcx, rbx; hObject
0x180006768  mov     edi, eax
0x18000676a  call    cs:__imp_CloseHandle
0x180006770  test    eax, eax
0x180006772  jz      short loc_1800067E3
0x180006774  jmp     loc_18000668B
0x180006779  call    cs:__imp_GetLastError
0x18000677f  cmp     eax, 2
0x180006782  jnz     short loc_180006788
0x180006784  xor     eax, eax
0x180006786  jmp     short loc_1800067A0
0x180006788  mov     rcx, [rbp+188h]; this
0x18000678f  lea     r8, aWil; "wil"
0x180006796  mov     edx, 0D0h; void *
0x18000679b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800067a0  mov     rcx, [rbp+180h+var_40]
0x1800067a7  xor     rcx, rsp; StackCookie
0x1800067aa  call    __security_check_cookie
0x1800067af  add     rsp, 258h
0x1800067b6  pop     r15
0x1800067b8  pop     r14
0x1800067ba  pop     rdi
0x1800067bb  pop     rsi
0x1800067bc  pop     rbx
0x1800067bd  pop     rbp
0x1800067be  retn
0x1800067bf  mov     rcx, [rbp+188h]; this
0x1800067c6  mov     edx, 0A0Bh; void *
0x1800067cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067d1  mov     rcx, [rbp+188h]; this
0x1800067d8  mov     edx, 0A0Bh; void *
0x1800067dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067e3  mov     rcx, [rbp+188h]; this
0x1800067ea  mov     edx, 0A0Bh; void *
0x1800067ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067f5  mov     rcx, [rbp+188h]; this
0x1800067fc  mov     edx, 0A0Bh; void *
0x180006801  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006807  mov     rcx, [rbp+188h]; this
0x18000680e  mov     edx, 0A0Bh; void *
0x180006813  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006819  mov     rcx, [rbp+188h]; this
0x180006820  mov     edx, 0A0Bh; void *
0x180006825  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

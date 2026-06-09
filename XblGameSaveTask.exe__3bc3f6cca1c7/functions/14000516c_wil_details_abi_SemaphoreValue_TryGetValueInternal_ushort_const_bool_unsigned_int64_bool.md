# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000516c`
- end: `0x1400053ed`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `641`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002d58`

## callees

- `0x140001480`
- `0x140003c94`
- `0x140004704`
- `0x140004724`
- `0x140005000`
- `0x14000516c`
- `0x14000554c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005200`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005275`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005200`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000533b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000533b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000532c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000532c`

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
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  int v22; // r8d
  unsigned int v23; // esi
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
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
  v20 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v35);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x14000516c  push    rbp
0x14000516e  push    rbx
0x14000516f  push    rsi
0x140005170  push    rdi
0x140005171  push    r14
0x140005173  push    r15
0x140005175  lea     rbp, [rsp-158h]
0x14000517d  sub     rsp, 258h
0x140005184  mov     rax, cs:__security_cookie
0x14000518b  xor     rax, rsp
0x14000518e  mov     [rbp+180h+var_40], rax
0x140005195  xor     r15d, r15d
0x140005198  lea     rax, [rsp+280h+Name]
0x14000519d  mov     [r8], r15
0x1400051a0  mov     r14, r8
0x1400051a3  mov     edx, 104h
0x1400051a8  mov     r9d, 7FFFFFFEh
0x1400051ae  test    r9, r9
0x1400051b1  jz      short loc_1400051D2
0x1400051b3  movzx   r8d, word ptr [rcx]
0x1400051b7  test    r8w, r8w
0x1400051bb  jz      short loc_1400051D2
0x1400051bd  mov     [rax], r8w
0x1400051c1  add     rcx, 2
0x1400051c5  add     rax, 2
0x1400051c9  dec     r9
0x1400051cc  sub     rdx, 1; unsigned __int64
0x1400051d0  jnz     short loc_1400051AE
0x1400051d2  test    rdx, rdx
0x1400051d5  lea     rcx, [rax-2]
0x1400051d9  lea     r8, aP0; "_p0"
0x1400051e0  cmovnz  rcx, rax
0x1400051e4  mov     [rcx], r15w
0x1400051e8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400051ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400051f2  mov     esi, 1F0003h
0x1400051f7  lea     r8, [rsp+280h+Name]; lpName
0x1400051fc  mov     ecx, esi; dwDesiredAccess
0x1400051fe  xor     edx, edx; bInheritHandle
0x140005200  call    cs:__imp_OpenSemaphoreW
0x140005206  mov     rbx, rax
0x140005209  test    rax, rax
0x14000520c  jz      loc_14000533B
0x140005212  lea     rdx, [rsp+280h+var_25C]; int *
0x140005217  mov     [rsp+280h+var_25C], r15d
0x14000521c  mov     rcx, rax; hHandle
0x14000521f  mov     [rsp+280h+var_260], r15d; int
0x140005224  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005229  mov     edi, eax
0x14000522b  test    eax, eax
0x14000522d  jns     short loc_14000525B
0x14000522f  mov     rcx, [rbp+188h]; this
0x140005236  mov     r9d, eax; char *
0x140005239  mov     edx, 0D6h; void *
0x14000523e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005243  mov     rcx, rbx; hObject
0x140005246  call    cs:__imp_CloseHandle
0x14000524c  test    eax, eax
0x14000524e  jz      loc_1400053B7
0x140005254  mov     eax, edi
0x140005256  jmp     loc_140005362
0x14000525b  lea     r8, asc_140008B38; "h"
0x140005262  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005267  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000526c  lea     r8, [rsp+280h+Name]; lpName
0x140005271  xor     edx, edx; bInheritHandle
0x140005273  mov     ecx, esi; dwDesiredAccess
0x140005275  call    cs:__imp_OpenSemaphoreW
0x14000527b  mov     rdi, rax
0x14000527e  test    rax, rax
0x140005281  jz      loc_14000530F
0x140005287  lea     rdx, [rsp+280h+var_260]; int *
0x14000528c  mov     rcx, rax; hHandle
0x14000528f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005294  mov     esi, eax
0x140005296  test    eax, eax
0x140005298  jns     short loc_1400052D7
0x14000529a  mov     rcx, [rbp+188h]; this
0x1400052a1  mov     r9d, eax; char *
0x1400052a4  mov     edx, 0DEh; void *
0x1400052a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400052ae  mov     rcx, rdi; hObject
0x1400052b1  call    cs:__imp_CloseHandle
0x1400052b7  test    eax, eax
0x1400052b9  jz      loc_1400053C9
0x1400052bf  mov     rcx, rbx; hObject
0x1400052c2  call    cs:__imp_CloseHandle
0x1400052c8  test    eax, eax
0x1400052ca  jz      loc_1400053DB
0x1400052d0  mov     eax, esi
0x1400052d2  jmp     loc_140005362
0x1400052d7  mov     rcx, rdi; hObject
0x1400052da  call    cs:__imp_CloseHandle
0x1400052e0  test    eax, eax
0x1400052e2  jz      loc_140005381
0x1400052e8  movsxd  rax, [rsp+280h+var_25C]
0x1400052ed  movsxd  rcx, [rsp+280h+var_260]
0x1400052f2  shl     rcx, 1Fh
0x1400052f6  or      rcx, rax
0x1400052f9  mov     [r14], rcx
0x1400052fc  mov     rcx, rbx; hObject
0x1400052ff  call    cs:__imp_CloseHandle
0x140005305  test    eax, eax
0x140005307  jz      loc_140005393
0x14000530d  jmp     short loc_140005346
0x14000530f  mov     rcx, [rbp+188h]; this
0x140005316  lea     r8, aWil; "wil"
0x14000531d  mov     edx, 0DCh; void *
0x140005322  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005327  mov     rcx, rbx; hObject
0x14000532a  mov     edi, eax
0x14000532c  call    cs:__imp_CloseHandle
0x140005332  test    eax, eax
0x140005334  jz      short loc_1400053A5
0x140005336  jmp     loc_140005254
0x14000533b  call    cs:__imp_GetLastError
0x140005341  cmp     eax, 2
0x140005344  jnz     short loc_14000534A
0x140005346  xor     eax, eax
0x140005348  jmp     short loc_140005362
0x14000534a  mov     rcx, [rbp+188h]; this
0x140005351  lea     r8, aWil; "wil"
0x140005358  mov     edx, 0D0h; void *
0x14000535d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005362  mov     rcx, [rbp+180h+var_40]
0x140005369  xor     rcx, rsp; StackCookie
0x14000536c  call    __security_check_cookie
0x140005371  add     rsp, 258h
0x140005378  pop     r15
0x14000537a  pop     r14
0x14000537c  pop     rdi
0x14000537d  pop     rsi
0x14000537e  pop     rbx
0x14000537f  pop     rbp
0x140005380  retn
0x140005381  mov     rcx, [rbp+188h]; this
0x140005388  mov     edx, 0A0Bh; void *
0x14000538d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005393  mov     rcx, [rbp+188h]; this
0x14000539a  mov     edx, 0A0Bh; void *
0x14000539f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400053a5  mov     rcx, [rbp+188h]; this
0x1400053ac  mov     edx, 0A0Bh; void *
0x1400053b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400053b7  mov     rcx, [rbp+188h]; this
0x1400053be  mov     edx, 0A0Bh; void *
0x1400053c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400053c9  mov     rcx, [rbp+188h]; this
0x1400053d0  mov     edx, 0A0Bh; void *
0x1400053d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400053db  mov     rcx, [rbp+188h]; this
0x1400053e2  mov     edx, 0A0Bh; void *
0x1400053e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

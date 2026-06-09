# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000986c`
- end: `0x180009afb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008080`

## callees

- `0x180006e80`
- `0x180006ea0`
- `0x1800071e4`
- `0x180008b60`
- `0x180009700`
- `0x18000986c`
- `0x18000e990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a49`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009900`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000997c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009900`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000997c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000994d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000994d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a3a`

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
0x18000986c  push    rbp
0x18000986e  push    rbx
0x18000986f  push    rsi
0x180009870  push    rdi
0x180009871  push    r14
0x180009873  push    r15
0x180009875  lea     rbp, [rsp-158h]
0x18000987d  sub     rsp, 258h
0x180009884  mov     rax, cs:__security_cookie
0x18000988b  xor     rax, rsp
0x18000988e  mov     [rbp+180h+var_40], rax
0x180009895  xor     r15d, r15d
0x180009898  lea     rax, [rsp+280h+Name]
0x18000989d  mov     [r8], r15
0x1800098a0  mov     r14, r8
0x1800098a3  mov     edx, 104h
0x1800098a8  mov     r9d, 7FFFFFFEh
0x1800098ae  test    r9, r9
0x1800098b1  jz      short loc_1800098D2
0x1800098b3  movzx   r8d, word ptr [rcx]
0x1800098b7  test    r8w, r8w
0x1800098bb  jz      short loc_1800098D2
0x1800098bd  mov     [rax], r8w
0x1800098c1  add     rcx, 2
0x1800098c5  add     rax, 2
0x1800098c9  dec     r9
0x1800098cc  sub     rdx, 1; unsigned __int64
0x1800098d0  jnz     short loc_1800098AE
0x1800098d2  test    rdx, rdx
0x1800098d5  lea     rcx, [rax-2]
0x1800098d9  lea     r8, aP0; "_p0"
0x1800098e0  cmovnz  rcx, rax
0x1800098e4  mov     [rcx], r15w
0x1800098e8  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800098ed  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800098f2  mov     esi, 1F0003h
0x1800098f7  lea     r8, [rsp+280h+Name]; lpName
0x1800098fc  mov     ecx, esi; dwDesiredAccess
0x1800098fe  xor     edx, edx; bInheritHandle
0x180009900  call    cs:__imp_OpenSemaphoreW
0x180009906  mov     rbx, rax
0x180009909  test    rax, rax
0x18000990c  jz      loc_180009A49
0x180009912  lea     rdx, [rsp+280h+var_25C]; int *
0x180009917  mov     [rsp+280h+var_25C], r15d
0x18000991c  mov     rcx, rax; hHandle
0x18000991f  mov     [rsp+280h+var_260], r15d; int
0x180009924  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009929  mov     edi, eax
0x18000992b  test    eax, eax
0x18000992d  jns     short loc_180009962
0x18000992f  mov     rcx, [rbp+188h]; this
0x180009936  lea     r8, aWil; "wil"
0x18000993d  mov     r9d, eax; char *
0x180009940  mov     edx, 0D6h; void *
0x180009945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000994a  mov     rcx, rbx; hObject
0x18000994d  call    cs:__imp_CloseHandle
0x180009953  test    eax, eax
0x180009955  jz      loc_180009AC5
0x18000995b  mov     eax, edi
0x18000995d  jmp     loc_180009A70
0x180009962  lea     r8, asc_1800139C0; "h"
0x180009969  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000996e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009973  lea     r8, [rsp+280h+Name]; lpName
0x180009978  xor     edx, edx; bInheritHandle
0x18000997a  mov     ecx, esi; dwDesiredAccess
0x18000997c  call    cs:__imp_OpenSemaphoreW
0x180009982  mov     rdi, rax
0x180009985  test    rax, rax
0x180009988  jz      loc_180009A1D
0x18000998e  lea     rdx, [rsp+280h+var_260]; int *
0x180009993  mov     rcx, rax; hHandle
0x180009996  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000999b  mov     esi, eax
0x18000999d  test    eax, eax
0x18000999f  jns     short loc_1800099E5
0x1800099a1  mov     rcx, [rbp+188h]; this
0x1800099a8  lea     r8, aWil; "wil"
0x1800099af  mov     r9d, eax; char *
0x1800099b2  mov     edx, 0DEh; void *
0x1800099b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099bc  mov     rcx, rdi; hObject
0x1800099bf  call    cs:__imp_CloseHandle
0x1800099c5  test    eax, eax
0x1800099c7  jz      loc_180009AD7
0x1800099cd  mov     rcx, rbx; hObject
0x1800099d0  call    cs:__imp_CloseHandle
0x1800099d6  test    eax, eax
0x1800099d8  jz      loc_180009AE9
0x1800099de  mov     eax, esi
0x1800099e0  jmp     loc_180009A70
0x1800099e5  mov     rcx, rdi; hObject
0x1800099e8  call    cs:__imp_CloseHandle
0x1800099ee  test    eax, eax
0x1800099f0  jz      loc_180009A8F
0x1800099f6  movsxd  rax, [rsp+280h+var_25C]
0x1800099fb  movsxd  rcx, [rsp+280h+var_260]
0x180009a00  shl     rcx, 1Fh
0x180009a04  or      rcx, rax
0x180009a07  mov     [r14], rcx
0x180009a0a  mov     rcx, rbx; hObject
0x180009a0d  call    cs:__imp_CloseHandle
0x180009a13  test    eax, eax
0x180009a15  jz      loc_180009AA1
0x180009a1b  jmp     short loc_180009A54
0x180009a1d  mov     rcx, [rbp+188h]; this
0x180009a24  lea     r8, aWil; "wil"
0x180009a2b  mov     edx, 0DCh; void *
0x180009a30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009a35  mov     rcx, rbx; hObject
0x180009a38  mov     edi, eax
0x180009a3a  call    cs:__imp_CloseHandle
0x180009a40  test    eax, eax
0x180009a42  jz      short loc_180009AB3
0x180009a44  jmp     loc_18000995B
0x180009a49  call    cs:__imp_GetLastError
0x180009a4f  cmp     eax, 2
0x180009a52  jnz     short loc_180009A58
0x180009a54  xor     eax, eax
0x180009a56  jmp     short loc_180009A70
0x180009a58  mov     rcx, [rbp+188h]; this
0x180009a5f  lea     r8, aWil; "wil"
0x180009a66  mov     edx, 0D0h; void *
0x180009a6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009a70  mov     rcx, [rbp+180h+var_40]
0x180009a77  xor     rcx, rsp; StackCookie
0x180009a7a  call    __security_check_cookie
0x180009a7f  add     rsp, 258h
0x180009a86  pop     r15
0x180009a88  pop     r14
0x180009a8a  pop     rdi
0x180009a8b  pop     rsi
0x180009a8c  pop     rbx
0x180009a8d  pop     rbp
0x180009a8e  retn
0x180009a8f  mov     rcx, [rbp+188h]; this
0x180009a96  mov     edx, 0A0Bh; void *
0x180009a9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009aa1  mov     rcx, [rbp+188h]; this
0x180009aa8  mov     edx, 0A0Bh; void *
0x180009aad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ab3  mov     rcx, [rbp+188h]; this
0x180009aba  mov     edx, 0A0Bh; void *
0x180009abf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ac5  mov     rcx, [rbp+188h]; this
0x180009acc  mov     edx, 0A0Bh; void *
0x180009ad1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ad7  mov     rcx, [rbp+188h]; this
0x180009ade  mov     edx, 0A0Bh; void *
0x180009ae3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ae9  mov     rcx, [rbp+188h]; this
0x180009af0  mov     edx, 0A0Bh; void *
0x180009af5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

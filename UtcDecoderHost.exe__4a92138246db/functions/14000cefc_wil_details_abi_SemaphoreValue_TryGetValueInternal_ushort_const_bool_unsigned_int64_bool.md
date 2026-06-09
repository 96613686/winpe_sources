# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000cefc`
- end: `0x14000d18b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000aac8`
- `0x14001373c`

## callees

- `0x140008660`
- `0x14000bb14`
- `0x14000c414`
- `0x14000c434`
- `0x14000cd74`
- `0x14000cefc`
- `0x14000d2ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000cf90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d00c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000cf90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cfdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d04f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d060`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d09d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d0ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cfdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d04f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d060`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d09d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d0ca`

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
0x14000cefc  push    rbp
0x14000cefe  push    rbx
0x14000ceff  push    rsi
0x14000cf00  push    rdi
0x14000cf01  push    r14
0x14000cf03  push    r15
0x14000cf05  lea     rbp, [rsp-158h]
0x14000cf0d  sub     rsp, 258h
0x14000cf14  mov     rax, cs:__security_cookie
0x14000cf1b  xor     rax, rsp
0x14000cf1e  mov     [rbp+180h+var_40], rax
0x14000cf25  xor     r15d, r15d
0x14000cf28  lea     rax, [rsp+280h+Name]
0x14000cf2d  mov     [r8], r15
0x14000cf30  mov     r14, r8
0x14000cf33  mov     edx, 104h
0x14000cf38  mov     r9d, 7FFFFFFEh
0x14000cf3e  test    r9, r9
0x14000cf41  jz      short loc_14000CF62
0x14000cf43  movzx   r8d, word ptr [rcx]
0x14000cf47  test    r8w, r8w
0x14000cf4b  jz      short loc_14000CF62
0x14000cf4d  mov     [rax], r8w
0x14000cf51  add     rcx, 2
0x14000cf55  add     rax, 2
0x14000cf59  dec     r9
0x14000cf5c  sub     rdx, 1; unsigned __int64
0x14000cf60  jnz     short loc_14000CF3E
0x14000cf62  test    rdx, rdx
0x14000cf65  lea     rcx, [rax-2]
0x14000cf69  lea     r8, aP0; "_p0"
0x14000cf70  cmovnz  rcx, rax
0x14000cf74  mov     [rcx], r15w
0x14000cf78  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000cf7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000cf82  mov     esi, 1F0003h
0x14000cf87  lea     r8, [rsp+280h+Name]; lpName
0x14000cf8c  mov     ecx, esi; dwDesiredAccess
0x14000cf8e  xor     edx, edx; bInheritHandle
0x14000cf90  call    cs:__imp_OpenSemaphoreW
0x14000cf96  mov     rbx, rax
0x14000cf99  test    rax, rax
0x14000cf9c  jz      loc_14000D0D9
0x14000cfa2  lea     rdx, [rsp+280h+var_25C]; int *
0x14000cfa7  mov     [rsp+280h+var_25C], r15d
0x14000cfac  mov     rcx, rax; hHandle
0x14000cfaf  mov     [rsp+280h+var_260], r15d; int
0x14000cfb4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000cfb9  mov     edi, eax
0x14000cfbb  test    eax, eax
0x14000cfbd  jns     short loc_14000CFF2
0x14000cfbf  mov     rcx, [rbp+188h]; this
0x14000cfc6  lea     r8, aWil; "wil"
0x14000cfcd  mov     r9d, eax; char *
0x14000cfd0  mov     edx, 0D6h; void *
0x14000cfd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000cfda  mov     rcx, rbx; hObject
0x14000cfdd  call    cs:__imp_CloseHandle
0x14000cfe3  test    eax, eax
0x14000cfe5  jz      loc_14000D155
0x14000cfeb  mov     eax, edi
0x14000cfed  jmp     loc_14000D100
0x14000cff2  lea     r8, asc_14001C728; "h"
0x14000cff9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000cffe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d003  lea     r8, [rsp+280h+Name]; lpName
0x14000d008  xor     edx, edx; bInheritHandle
0x14000d00a  mov     ecx, esi; dwDesiredAccess
0x14000d00c  call    cs:__imp_OpenSemaphoreW
0x14000d012  mov     rdi, rax
0x14000d015  test    rax, rax
0x14000d018  jz      loc_14000D0AD
0x14000d01e  lea     rdx, [rsp+280h+var_260]; int *
0x14000d023  mov     rcx, rax; hHandle
0x14000d026  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000d02b  mov     esi, eax
0x14000d02d  test    eax, eax
0x14000d02f  jns     short loc_14000D075
0x14000d031  mov     rcx, [rbp+188h]; this
0x14000d038  lea     r8, aWil; "wil"
0x14000d03f  mov     r9d, eax; char *
0x14000d042  mov     edx, 0DEh; void *
0x14000d047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d04c  mov     rcx, rdi; hObject
0x14000d04f  call    cs:__imp_CloseHandle
0x14000d055  test    eax, eax
0x14000d057  jz      loc_14000D167
0x14000d05d  mov     rcx, rbx; hObject
0x14000d060  call    cs:__imp_CloseHandle
0x14000d066  test    eax, eax
0x14000d068  jz      loc_14000D179
0x14000d06e  mov     eax, esi
0x14000d070  jmp     loc_14000D100
0x14000d075  mov     rcx, rdi; hObject
0x14000d078  call    cs:__imp_CloseHandle
0x14000d07e  test    eax, eax
0x14000d080  jz      loc_14000D11F
0x14000d086  movsxd  rax, [rsp+280h+var_25C]
0x14000d08b  movsxd  rcx, [rsp+280h+var_260]
0x14000d090  shl     rcx, 1Fh
0x14000d094  or      rcx, rax
0x14000d097  mov     [r14], rcx
0x14000d09a  mov     rcx, rbx; hObject
0x14000d09d  call    cs:__imp_CloseHandle
0x14000d0a3  test    eax, eax
0x14000d0a5  jz      loc_14000D131
0x14000d0ab  jmp     short loc_14000D0E4
0x14000d0ad  mov     rcx, [rbp+188h]; this
0x14000d0b4  lea     r8, aWil; "wil"
0x14000d0bb  mov     edx, 0DCh; void *
0x14000d0c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d0c5  mov     rcx, rbx; hObject
0x14000d0c8  mov     edi, eax
0x14000d0ca  call    cs:__imp_CloseHandle
0x14000d0d0  test    eax, eax
0x14000d0d2  jz      short loc_14000D143
0x14000d0d4  jmp     loc_14000CFEB
0x14000d0d9  call    cs:__imp_GetLastError
0x14000d0df  cmp     eax, 2
0x14000d0e2  jnz     short loc_14000D0E8
0x14000d0e4  xor     eax, eax
0x14000d0e6  jmp     short loc_14000D100
0x14000d0e8  mov     rcx, [rbp+188h]; this
0x14000d0ef  lea     r8, aWil; "wil"
0x14000d0f6  mov     edx, 0D0h; void *
0x14000d0fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d100  mov     rcx, [rbp+180h+var_40]
0x14000d107  xor     rcx, rsp; StackCookie
0x14000d10a  call    __security_check_cookie
0x14000d10f  add     rsp, 258h
0x14000d116  pop     r15
0x14000d118  pop     r14
0x14000d11a  pop     rdi
0x14000d11b  pop     rsi
0x14000d11c  pop     rbx
0x14000d11d  pop     rbp
0x14000d11e  retn
0x14000d11f  mov     rcx, [rbp+188h]; this
0x14000d126  mov     edx, 0A0Bh; void *
0x14000d12b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d131  mov     rcx, [rbp+188h]; this
0x14000d138  mov     edx, 0A0Bh; void *
0x14000d13d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d143  mov     rcx, [rbp+188h]; this
0x14000d14a  mov     edx, 0A0Bh; void *
0x14000d14f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d155  mov     rcx, [rbp+188h]; this
0x14000d15c  mov     edx, 0A0Bh; void *
0x14000d161  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d167  mov     rcx, [rbp+188h]; this
0x14000d16e  mov     edx, 0A0Bh; void *
0x14000d173  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d179  mov     rcx, [rbp+188h]; this
0x14000d180  mov     edx, 0A0Bh; void *
0x14000d185  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

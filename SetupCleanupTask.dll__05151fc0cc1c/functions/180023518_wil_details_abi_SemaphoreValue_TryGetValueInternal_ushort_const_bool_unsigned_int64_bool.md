# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180023518`
- end: `0x18002378d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180019770`
- `0x180019b14`

## callees

- `0x18001c5ec`
- `0x180021f18`
- `0x180021f38`
- `0x180022e70`
- `0x180023518`
- `0x1800247f4`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800235af`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002362a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800235af`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002362a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800235f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023666`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002368c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800236b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800236d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800235f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023666`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002368c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800236b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800236d3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  int v12; // r8d
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
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
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
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
0x180023518  push    rbp
0x18002351a  push    rbx
0x18002351b  push    rsi
0x18002351c  push    rdi
0x18002351d  push    r14
0x18002351f  push    r15
0x180023521  lea     rbp, [rsp-158h]
0x180023529  sub     rsp, 258h
0x180023530  mov     rax, cs:__security_cookie
0x180023537  xor     rax, rsp
0x18002353a  mov     [rbp+180h+var_40], rax
0x180023541  xor     r15d, r15d
0x180023544  lea     rax, [rsp+280h+Name]
0x180023549  mov     esi, 104h
0x18002354e  mov     [r8], r15
0x180023551  mov     edx, esi
0x180023553  mov     r14, r8
0x180023556  mov     r9d, 7FFFFFFEh
0x18002355c  test    r9, r9
0x18002355f  jz      short loc_180023580
0x180023561  movzx   r8d, word ptr [rcx]
0x180023565  test    r8w, r8w
0x180023569  jz      short loc_180023580
0x18002356b  mov     [rax], r8w
0x18002356f  add     rcx, 2
0x180023573  add     rax, 2
0x180023577  dec     r9
0x18002357a  sub     rdx, 1
0x18002357e  jnz     short loc_18002355C
0x180023580  test    rdx, rdx
0x180023583  lea     rcx, [rax-2]
0x180023587  lea     r8, aP0; "_p0"
0x18002358e  mov     rdx, rsi; unsigned __int64
0x180023591  cmovnz  rcx, rax
0x180023595  mov     [rcx], r15w
0x180023599  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002359e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800235a3  lea     r8, [rsp+280h+Name]; lpName
0x1800235a8  xor     edx, edx; bInheritHandle
0x1800235aa  mov     ecx, 1F0003h; dwDesiredAccess
0x1800235af  call    cs:__imp_OpenSemaphoreW
0x1800235b5  mov     rbx, rax
0x1800235b8  test    rax, rax
0x1800235bb  jz      loc_1800236E2
0x1800235c1  lea     rdx, [rsp+280h+var_25C]; int *
0x1800235c6  mov     [rsp+280h+var_25C], r15d
0x1800235cb  mov     rcx, rax; hHandle
0x1800235ce  mov     [rsp+280h+var_260], r15d; int
0x1800235d3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800235d8  mov     edi, eax
0x1800235da  test    eax, eax
0x1800235dc  jns     short loc_18002360A
0x1800235de  mov     rcx, [rbp+188h]; this
0x1800235e5  mov     r9d, eax; char *
0x1800235e8  mov     edx, 0D6h; void *
0x1800235ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800235f2  mov     rcx, rbx; hObject
0x1800235f5  call    cs:__imp_CloseHandle
0x1800235fb  test    eax, eax
0x1800235fd  jz      loc_180023757
0x180023603  mov     eax, edi
0x180023605  jmp     loc_180023702
0x18002360a  lea     r8, asc_180041280; "h"
0x180023611  mov     rdx, rsi; unsigned __int64
0x180023614  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180023619  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002361e  lea     r8, [rsp+280h+Name]; lpName
0x180023623  xor     edx, edx; bInheritHandle
0x180023625  mov     ecx, 1F0003h; dwDesiredAccess
0x18002362a  call    cs:__imp_OpenSemaphoreW
0x180023630  mov     rdi, rax
0x180023633  test    rax, rax
0x180023636  jz      loc_1800236BD
0x18002363c  lea     rdx, [rsp+280h+var_260]; int *
0x180023641  mov     rcx, rax; hHandle
0x180023644  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180023649  mov     esi, eax
0x18002364b  test    eax, eax
0x18002364d  jns     short loc_180023689
0x18002364f  mov     rcx, [rbp+188h]; this
0x180023656  mov     r9d, eax; char *
0x180023659  mov     edx, 0DEh; void *
0x18002365e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023663  mov     rcx, rdi; hObject
0x180023666  call    cs:__imp_CloseHandle
0x18002366c  test    eax, eax
0x18002366e  jz      loc_180023769
0x180023674  mov     rcx, rbx; hObject
0x180023677  call    cs:__imp_CloseHandle
0x18002367d  test    eax, eax
0x18002367f  jz      loc_18002377B
0x180023685  mov     eax, esi
0x180023687  jmp     short loc_180023702
0x180023689  mov     rcx, rdi; hObject
0x18002368c  call    cs:__imp_CloseHandle
0x180023692  test    eax, eax
0x180023694  jz      loc_180023721
0x18002369a  movsxd  rax, [rsp+280h+var_25C]
0x18002369f  movsxd  rcx, [rsp+280h+var_260]
0x1800236a4  shl     rcx, 1Fh
0x1800236a8  or      rcx, rax
0x1800236ab  mov     [r14], rcx
0x1800236ae  mov     rcx, rbx; hObject
0x1800236b1  call    cs:__imp_CloseHandle
0x1800236b7  test    eax, eax
0x1800236b9  jz      short loc_180023733
0x1800236bb  jmp     short loc_1800236ED
0x1800236bd  mov     rcx, [rbp+188h]; this
0x1800236c4  mov     edx, 0DCh; void *
0x1800236c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800236ce  mov     rcx, rbx; hObject
0x1800236d1  mov     edi, eax
0x1800236d3  call    cs:__imp_CloseHandle
0x1800236d9  test    eax, eax
0x1800236db  jz      short loc_180023745
0x1800236dd  jmp     loc_180023603
0x1800236e2  call    cs:__imp_GetLastError
0x1800236e8  cmp     eax, 2
0x1800236eb  jnz     short loc_1800236F1
0x1800236ed  xor     eax, eax
0x1800236ef  jmp     short loc_180023702
0x1800236f1  mov     rcx, [rbp+188h]; this
0x1800236f8  mov     edx, 0D0h; void *
0x1800236fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023702  mov     rcx, [rbp+180h+var_40]
0x180023709  xor     rcx, rsp; StackCookie
0x18002370c  call    __security_check_cookie
0x180023711  add     rsp, 258h
0x180023718  pop     r15
0x18002371a  pop     r14
0x18002371c  pop     rdi
0x18002371d  pop     rsi
0x18002371e  pop     rbx
0x18002371f  pop     rbp
0x180023720  retn
0x180023721  mov     rcx, [rbp+188h]; this
0x180023728  mov     edx, 0A0Bh; void *
0x18002372d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023733  mov     rcx, [rbp+188h]; this
0x18002373a  mov     edx, 0A0Bh; void *
0x18002373f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023745  mov     rcx, [rbp+188h]; this
0x18002374c  mov     edx, 0A0Bh; void *
0x180023751  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023757  mov     rcx, [rbp+188h]; this
0x18002375e  mov     edx, 0A0Bh; void *
0x180023763  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023769  mov     rcx, [rbp+188h]; this
0x180023770  mov     edx, 0A0Bh; void *
0x180023775  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002377b  mov     rcx, [rbp+188h]; this
0x180023782  mov     edx, 0A0Bh; void *
0x180023787  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

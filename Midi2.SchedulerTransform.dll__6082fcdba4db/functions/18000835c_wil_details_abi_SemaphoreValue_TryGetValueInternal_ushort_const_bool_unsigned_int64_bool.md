# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000835c`
- end: `0x1800085d6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a88`

## callees

- `0x180002000`
- `0x1800059f4`
- `0x180007844`
- `0x180007864`
- `0x1800081f4`
- `0x18000835c`
- `0x180008a14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800083f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000846c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800083f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000846c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000843d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000851c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000843d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000851c`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000835c  push    rbp
0x18000835e  push    rbx
0x18000835f  push    rsi
0x180008360  push    rdi
0x180008361  push    r14
0x180008363  push    r15
0x180008365  lea     rbp, [rsp-158h]
0x18000836d  sub     rsp, 258h
0x180008374  mov     rax, cs:__security_cookie
0x18000837b  xor     rax, rsp
0x18000837e  mov     [rbp+180h+var_40], rax
0x180008385  xor     r15d, r15d
0x180008388  lea     rax, [rsp+280h+Name]
0x18000838d  mov     [r8], r15
0x180008390  mov     r14, r8
0x180008393  mov     edx, 104h
0x180008398  mov     r9d, 7FFFFFFEh
0x18000839e  test    r9, r9
0x1800083a1  jz      short loc_1800083C2
0x1800083a3  movzx   r8d, word ptr [rcx]
0x1800083a7  test    r8w, r8w
0x1800083ab  jz      short loc_1800083C2
0x1800083ad  mov     [rax], r8w
0x1800083b1  add     rcx, 2
0x1800083b5  add     rax, 2
0x1800083b9  dec     r9
0x1800083bc  sub     rdx, 1; unsigned __int64
0x1800083c0  jnz     short loc_18000839E
0x1800083c2  test    rdx, rdx
0x1800083c5  lea     rcx, [rax-2]
0x1800083c9  lea     r8, aP0; "_p0"
0x1800083d0  cmovnz  rcx, rax
0x1800083d4  mov     [rcx], r15w
0x1800083d8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800083dd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800083e2  mov     esi, 1F0003h
0x1800083e7  lea     r8, [rsp+280h+Name]; lpName
0x1800083ec  mov     ecx, esi; dwDesiredAccess
0x1800083ee  xor     edx, edx; bInheritHandle
0x1800083f0  call    cs:__imp_OpenSemaphoreW
0x1800083f6  mov     rbx, rax
0x1800083f9  test    rax, rax
0x1800083fc  jz      loc_18000852B
0x180008402  lea     rdx, [rsp+280h+var_25C]; int *
0x180008407  mov     [rsp+280h+var_25C], r15d
0x18000840c  mov     rcx, rax; hHandle
0x18000840f  mov     [rsp+280h+var_260], r15d; int
0x180008414  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008419  mov     edi, eax
0x18000841b  test    eax, eax
0x18000841d  jns     short loc_180008452
0x18000841f  mov     rcx, [rbp+188h]; this
0x180008426  lea     r8, aWil; "wil"
0x18000842d  mov     r9d, eax; char *
0x180008430  mov     edx, 0D6h; void *
0x180008435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000843a  mov     rcx, rbx; hObject
0x18000843d  call    cs:__imp_CloseHandle
0x180008443  test    eax, eax
0x180008445  jz      loc_1800085A0
0x18000844b  mov     eax, edi
0x18000844d  jmp     loc_18000854B
0x180008452  lea     r8, asc_180010080; "h"
0x180008459  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000845e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008463  lea     r8, [rsp+280h+Name]; lpName
0x180008468  xor     edx, edx; bInheritHandle
0x18000846a  mov     ecx, esi; dwDesiredAccess
0x18000846c  call    cs:__imp_OpenSemaphoreW
0x180008472  mov     rdi, rax
0x180008475  test    rax, rax
0x180008478  jz      loc_180008506
0x18000847e  lea     rdx, [rsp+280h+var_260]; int *
0x180008483  mov     rcx, rax; hHandle
0x180008486  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000848b  mov     esi, eax
0x18000848d  test    eax, eax
0x18000848f  jns     short loc_1800084D2
0x180008491  mov     rcx, [rbp+188h]; this
0x180008498  lea     r8, aWil; "wil"
0x18000849f  mov     r9d, eax; char *
0x1800084a2  mov     edx, 0DEh; void *
0x1800084a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084ac  mov     rcx, rdi; hObject
0x1800084af  call    cs:__imp_CloseHandle
0x1800084b5  test    eax, eax
0x1800084b7  jz      loc_1800085B2
0x1800084bd  mov     rcx, rbx; hObject
0x1800084c0  call    cs:__imp_CloseHandle
0x1800084c6  test    eax, eax
0x1800084c8  jz      loc_1800085C4
0x1800084ce  mov     eax, esi
0x1800084d0  jmp     short loc_18000854B
0x1800084d2  mov     rcx, rdi; hObject
0x1800084d5  call    cs:__imp_CloseHandle
0x1800084db  test    eax, eax
0x1800084dd  jz      loc_18000856A
0x1800084e3  movsxd  rax, [rsp+280h+var_25C]
0x1800084e8  movsxd  rcx, [rsp+280h+var_260]
0x1800084ed  shl     rcx, 1Fh
0x1800084f1  or      rcx, rax
0x1800084f4  mov     [r14], rcx
0x1800084f7  mov     rcx, rbx; hObject
0x1800084fa  call    cs:__imp_CloseHandle
0x180008500  test    eax, eax
0x180008502  jz      short loc_18000857C
0x180008504  jmp     short loc_180008536
0x180008506  mov     rcx, [rbp+188h]; this
0x18000850d  mov     edx, 0DCh; void *
0x180008512  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008517  mov     rcx, rbx; hObject
0x18000851a  mov     edi, eax
0x18000851c  call    cs:__imp_CloseHandle
0x180008522  test    eax, eax
0x180008524  jz      short loc_18000858E
0x180008526  jmp     loc_18000844B
0x18000852b  call    cs:__imp_GetLastError
0x180008531  cmp     eax, 2
0x180008534  jnz     short loc_18000853A
0x180008536  xor     eax, eax
0x180008538  jmp     short loc_18000854B
0x18000853a  mov     rcx, [rbp+188h]; this
0x180008541  mov     edx, 0D0h; void *
0x180008546  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000854b  mov     rcx, [rbp+180h+var_40]
0x180008552  xor     rcx, rsp; StackCookie
0x180008555  call    __security_check_cookie
0x18000855a  add     rsp, 258h
0x180008561  pop     r15
0x180008563  pop     r14
0x180008565  pop     rdi
0x180008566  pop     rsi
0x180008567  pop     rbx
0x180008568  pop     rbp
0x180008569  retn
0x18000856a  mov     rcx, [rbp+188h]; this
0x180008571  mov     edx, 0A0Bh; void *
0x180008576  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000857c  mov     rcx, [rbp+188h]; this
0x180008583  mov     edx, 0A0Bh; void *
0x180008588  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000858e  mov     rcx, [rbp+188h]; this
0x180008595  mov     edx, 0A0Bh; void *
0x18000859a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800085a0  mov     rcx, [rbp+188h]; this
0x1800085a7  mov     edx, 0A0Bh; void *
0x1800085ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800085b2  mov     rcx, [rbp+188h]; this
0x1800085b9  mov     edx, 0A0Bh; void *
0x1800085be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800085c4  mov     rcx, [rbp+188h]; this
0x1800085cb  mov     edx, 0A0Bh; void *
0x1800085d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

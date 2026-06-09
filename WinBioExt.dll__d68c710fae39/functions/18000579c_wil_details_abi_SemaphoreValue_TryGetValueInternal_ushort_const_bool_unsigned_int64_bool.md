# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000579c`
- end: `0x180005a08`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003168`
- `0x180007824`

## callees

- `0x180001610`
- `0x180004154`
- `0x180004cd4`
- `0x180004cf4`
- `0x180005634`
- `0x18000579c`
- `0x180005b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005830`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005830`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000595d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000595d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005907`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000592c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000594e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005907`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000592c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000594e`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18000579c  push    rbp
0x18000579e  push    rbx
0x18000579f  push    rsi
0x1800057a0  push    rdi
0x1800057a1  push    r14
0x1800057a3  push    r15
0x1800057a5  lea     rbp, [rsp-158h]
0x1800057ad  sub     rsp, 258h
0x1800057b4  mov     rax, cs:__security_cookie
0x1800057bb  xor     rax, rsp
0x1800057be  mov     [rbp+180h+var_40], rax
0x1800057c5  xor     r15d, r15d
0x1800057c8  lea     rax, [rsp+280h+Name]
0x1800057cd  mov     [r8], r15
0x1800057d0  mov     r14, r8
0x1800057d3  mov     edx, 104h
0x1800057d8  mov     r9d, 7FFFFFFEh
0x1800057de  test    r9, r9
0x1800057e1  jz      short loc_180005802
0x1800057e3  movzx   r8d, word ptr [rcx]
0x1800057e7  test    r8w, r8w
0x1800057eb  jz      short loc_180005802
0x1800057ed  mov     [rax], r8w
0x1800057f1  add     rcx, 2
0x1800057f5  add     rax, 2
0x1800057f9  dec     r9
0x1800057fc  sub     rdx, 1; unsigned __int64
0x180005800  jnz     short loc_1800057DE
0x180005802  test    rdx, rdx
0x180005805  lea     rcx, [rax-2]
0x180005809  lea     r8, aP0; "_p0"
0x180005810  cmovnz  rcx, rax
0x180005814  mov     [rcx], r15w
0x180005818  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000581d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005822  mov     esi, 1F0003h
0x180005827  lea     r8, [rsp+280h+Name]; lpName
0x18000582c  mov     ecx, esi; dwDesiredAccess
0x18000582e  xor     edx, edx; bInheritHandle
0x180005830  call    cs:__imp_OpenSemaphoreW
0x180005836  mov     rbx, rax
0x180005839  test    rax, rax
0x18000583c  jz      loc_18000595D
0x180005842  lea     rdx, [rsp+280h+var_25C]; int *
0x180005847  mov     [rsp+280h+var_25C], r15d
0x18000584c  mov     rcx, rax; hHandle
0x18000584f  mov     [rsp+280h+var_260], r15d; int
0x180005854  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005859  mov     edi, eax
0x18000585b  test    eax, eax
0x18000585d  jns     short loc_18000588B
0x18000585f  mov     rcx, [rbp+188h]; this
0x180005866  mov     r9d, eax; char *
0x180005869  mov     edx, 0D6h; void *
0x18000586e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005873  mov     rcx, rbx; hObject
0x180005876  call    cs:__imp_CloseHandle
0x18000587c  test    eax, eax
0x18000587e  jz      loc_1800059D2
0x180005884  mov     eax, edi
0x180005886  jmp     loc_18000597D
0x18000588b  lea     r8, asc_18000CC38; "h"
0x180005892  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005897  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000589c  lea     r8, [rsp+280h+Name]; lpName
0x1800058a1  xor     edx, edx; bInheritHandle
0x1800058a3  mov     ecx, esi; dwDesiredAccess
0x1800058a5  call    cs:__imp_OpenSemaphoreW
0x1800058ab  mov     rdi, rax
0x1800058ae  test    rax, rax
0x1800058b1  jz      loc_180005938
0x1800058b7  lea     rdx, [rsp+280h+var_260]; int *
0x1800058bc  mov     rcx, rax; hHandle
0x1800058bf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800058c4  mov     esi, eax
0x1800058c6  test    eax, eax
0x1800058c8  jns     short loc_180005904
0x1800058ca  mov     rcx, [rbp+188h]; this
0x1800058d1  mov     r9d, eax; char *
0x1800058d4  mov     edx, 0DEh; void *
0x1800058d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058de  mov     rcx, rdi; hObject
0x1800058e1  call    cs:__imp_CloseHandle
0x1800058e7  test    eax, eax
0x1800058e9  jz      loc_1800059E4
0x1800058ef  mov     rcx, rbx; hObject
0x1800058f2  call    cs:__imp_CloseHandle
0x1800058f8  test    eax, eax
0x1800058fa  jz      loc_1800059F6
0x180005900  mov     eax, esi
0x180005902  jmp     short loc_18000597D
0x180005904  mov     rcx, rdi; hObject
0x180005907  call    cs:__imp_CloseHandle
0x18000590d  test    eax, eax
0x18000590f  jz      loc_18000599C
0x180005915  movsxd  rax, [rsp+280h+var_25C]
0x18000591a  movsxd  rcx, [rsp+280h+var_260]
0x18000591f  shl     rcx, 1Fh
0x180005923  or      rcx, rax
0x180005926  mov     [r14], rcx
0x180005929  mov     rcx, rbx; hObject
0x18000592c  call    cs:__imp_CloseHandle
0x180005932  test    eax, eax
0x180005934  jz      short loc_1800059AE
0x180005936  jmp     short loc_180005968
0x180005938  mov     rcx, [rbp+188h]; this
0x18000593f  mov     edx, 0DCh; void *
0x180005944  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005949  mov     rcx, rbx; hObject
0x18000594c  mov     edi, eax
0x18000594e  call    cs:__imp_CloseHandle
0x180005954  test    eax, eax
0x180005956  jz      short loc_1800059C0
0x180005958  jmp     loc_180005884
0x18000595d  call    cs:__imp_GetLastError
0x180005963  cmp     eax, 2
0x180005966  jnz     short loc_18000596C
0x180005968  xor     eax, eax
0x18000596a  jmp     short loc_18000597D
0x18000596c  mov     rcx, [rbp+188h]; this
0x180005973  mov     edx, 0D0h; void *
0x180005978  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000597d  mov     rcx, [rbp+180h+var_40]
0x180005984  xor     rcx, rsp; StackCookie
0x180005987  call    __security_check_cookie
0x18000598c  add     rsp, 258h
0x180005993  pop     r15
0x180005995  pop     r14
0x180005997  pop     rdi
0x180005998  pop     rsi
0x180005999  pop     rbx
0x18000599a  pop     rbp
0x18000599b  retn
0x18000599c  mov     rcx, [rbp+188h]; this
0x1800059a3  mov     edx, 0A0Bh; void *
0x1800059a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800059ae  mov     rcx, [rbp+188h]; this
0x1800059b5  mov     edx, 0A0Bh; void *
0x1800059ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800059c0  mov     rcx, [rbp+188h]; this
0x1800059c7  mov     edx, 0A0Bh; void *
0x1800059cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800059d2  mov     rcx, [rbp+188h]; this
0x1800059d9  mov     edx, 0A0Bh; void *
0x1800059de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800059e4  mov     rcx, [rbp+188h]; this
0x1800059eb  mov     edx, 0A0Bh; void *
0x1800059f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800059f6  mov     rcx, [rbp+188h]; this
0x1800059fd  mov     edx, 0A0Bh; void *
0x180005a02  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

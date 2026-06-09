# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000dea8`
- end: `0x18000e122`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b298`
- `0x180010e64`

## callees

- `0x1800060a0`
- `0x18000c598`
- `0x18000d274`
- `0x18000d294`
- `0x18000dbd4`
- `0x18000dea8`
- `0x18000e59c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e077`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dffb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e00c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e068`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dffb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e00c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e068`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000df3c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dfb8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000df3c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dfb8`

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
0x18000dea8  push    rbp
0x18000deaa  push    rbx
0x18000deab  push    rsi
0x18000deac  push    rdi
0x18000dead  push    r14
0x18000deaf  push    r15
0x18000deb1  lea     rbp, [rsp-158h]
0x18000deb9  sub     rsp, 258h
0x18000dec0  mov     rax, cs:__security_cookie
0x18000dec7  xor     rax, rsp
0x18000deca  mov     [rbp+180h+var_40], rax
0x18000ded1  xor     r15d, r15d
0x18000ded4  lea     rax, [rsp+280h+Name]
0x18000ded9  mov     [r8], r15
0x18000dedc  mov     r14, r8
0x18000dedf  mov     edx, 104h
0x18000dee4  mov     r9d, 7FFFFFFEh
0x18000deea  test    r9, r9
0x18000deed  jz      short loc_18000DF0E
0x18000deef  movzx   r8d, word ptr [rcx]
0x18000def3  test    r8w, r8w
0x18000def7  jz      short loc_18000DF0E
0x18000def9  mov     [rax], r8w
0x18000defd  add     rcx, 2
0x18000df01  add     rax, 2
0x18000df05  dec     r9
0x18000df08  sub     rdx, 1; unsigned __int64
0x18000df0c  jnz     short loc_18000DEEA
0x18000df0e  test    rdx, rdx
0x18000df11  lea     rcx, [rax-2]
0x18000df15  lea     r8, aP0; "_p0"
0x18000df1c  cmovnz  rcx, rax
0x18000df20  mov     [rcx], r15w
0x18000df24  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000df29  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000df2e  mov     esi, 1F0003h
0x18000df33  lea     r8, [rsp+280h+Name]; lpName
0x18000df38  mov     ecx, esi; dwDesiredAccess
0x18000df3a  xor     edx, edx; bInheritHandle
0x18000df3c  call    cs:__imp_OpenSemaphoreW
0x18000df42  mov     rbx, rax
0x18000df45  test    rax, rax
0x18000df48  jz      loc_18000E077
0x18000df4e  lea     rdx, [rsp+280h+var_25C]; int *
0x18000df53  mov     [rsp+280h+var_25C], r15d
0x18000df58  mov     rcx, rax; hHandle
0x18000df5b  mov     [rsp+280h+var_260], r15d; int
0x18000df60  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000df65  mov     edi, eax
0x18000df67  test    eax, eax
0x18000df69  jns     short loc_18000DF9E
0x18000df6b  mov     rcx, [rbp+188h]; this
0x18000df72  lea     r8, aWil; "wil"
0x18000df79  mov     r9d, eax; char *
0x18000df7c  mov     edx, 0D6h; void *
0x18000df81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df86  mov     rcx, rbx; hObject
0x18000df89  call    cs:__imp_CloseHandle
0x18000df8f  test    eax, eax
0x18000df91  jz      loc_18000E0EC
0x18000df97  mov     eax, edi
0x18000df99  jmp     loc_18000E097
0x18000df9e  lea     r8, asc_1800B76E0; "h"
0x18000dfa5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dfaa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dfaf  lea     r8, [rsp+280h+Name]; lpName
0x18000dfb4  xor     edx, edx; bInheritHandle
0x18000dfb6  mov     ecx, esi; dwDesiredAccess
0x18000dfb8  call    cs:__imp_OpenSemaphoreW
0x18000dfbe  mov     rdi, rax
0x18000dfc1  test    rax, rax
0x18000dfc4  jz      loc_18000E052
0x18000dfca  lea     rdx, [rsp+280h+var_260]; int *
0x18000dfcf  mov     rcx, rax; hHandle
0x18000dfd2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dfd7  mov     esi, eax
0x18000dfd9  test    eax, eax
0x18000dfdb  jns     short loc_18000E01E
0x18000dfdd  mov     rcx, [rbp+188h]; this
0x18000dfe4  lea     r8, aWil; "wil"
0x18000dfeb  mov     r9d, eax; char *
0x18000dfee  mov     edx, 0DEh; void *
0x18000dff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dff8  mov     rcx, rdi; hObject
0x18000dffb  call    cs:__imp_CloseHandle
0x18000e001  test    eax, eax
0x18000e003  jz      loc_18000E0FE
0x18000e009  mov     rcx, rbx; hObject
0x18000e00c  call    cs:__imp_CloseHandle
0x18000e012  test    eax, eax
0x18000e014  jz      loc_18000E110
0x18000e01a  mov     eax, esi
0x18000e01c  jmp     short loc_18000E097
0x18000e01e  mov     rcx, rdi; hObject
0x18000e021  call    cs:__imp_CloseHandle
0x18000e027  test    eax, eax
0x18000e029  jz      loc_18000E0B6
0x18000e02f  movsxd  rax, [rsp+280h+var_25C]
0x18000e034  movsxd  rcx, [rsp+280h+var_260]
0x18000e039  shl     rcx, 1Fh
0x18000e03d  or      rcx, rax
0x18000e040  mov     [r14], rcx
0x18000e043  mov     rcx, rbx; hObject
0x18000e046  call    cs:__imp_CloseHandle
0x18000e04c  test    eax, eax
0x18000e04e  jz      short loc_18000E0C8
0x18000e050  jmp     short loc_18000E082
0x18000e052  mov     rcx, [rbp+188h]; this
0x18000e059  mov     edx, 0DCh; void *
0x18000e05e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e063  mov     rcx, rbx; hObject
0x18000e066  mov     edi, eax
0x18000e068  call    cs:__imp_CloseHandle
0x18000e06e  test    eax, eax
0x18000e070  jz      short loc_18000E0DA
0x18000e072  jmp     loc_18000DF97
0x18000e077  call    cs:__imp_GetLastError
0x18000e07d  cmp     eax, 2
0x18000e080  jnz     short loc_18000E086
0x18000e082  xor     eax, eax
0x18000e084  jmp     short loc_18000E097
0x18000e086  mov     rcx, [rbp+188h]; this
0x18000e08d  mov     edx, 0D0h; void *
0x18000e092  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e097  mov     rcx, [rbp+180h+var_40]
0x18000e09e  xor     rcx, rsp; StackCookie
0x18000e0a1  call    __security_check_cookie
0x18000e0a6  add     rsp, 258h
0x18000e0ad  pop     r15
0x18000e0af  pop     r14
0x18000e0b1  pop     rdi
0x18000e0b2  pop     rsi
0x18000e0b3  pop     rbx
0x18000e0b4  pop     rbp
0x18000e0b5  retn
0x18000e0b6  mov     rcx, [rbp+188h]; this
0x18000e0bd  mov     edx, 0A0Bh; void *
0x18000e0c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e0c8  mov     rcx, [rbp+188h]; this
0x18000e0cf  mov     edx, 0A0Bh; void *
0x18000e0d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e0da  mov     rcx, [rbp+188h]; this
0x18000e0e1  mov     edx, 0A0Bh; void *
0x18000e0e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e0ec  mov     rcx, [rbp+188h]; this
0x18000e0f3  mov     edx, 0A0Bh; void *
0x18000e0f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e0fe  mov     rcx, [rbp+188h]; this
0x18000e105  mov     edx, 0A0Bh; void *
0x18000e10a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e110  mov     rcx, [rbp+188h]; this
0x18000e117  mov     edx, 0A0Bh; void *
0x18000e11c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000dc68`
- end: `0x18000def7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008c68`
- `0x180009038`

## callees

- `0x180004ea0`
- `0x18000a5d4`
- `0x18000caa4`
- `0x18000cac4`
- `0x18000d508`
- `0x18000dc68`
- `0x18000e54c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dcfc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dd78`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dcfc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dd78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dde4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dde4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de36`

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
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000dc68  push    rbp
0x18000dc6a  push    rbx
0x18000dc6b  push    rsi
0x18000dc6c  push    rdi
0x18000dc6d  push    r14
0x18000dc6f  push    r15
0x18000dc71  lea     rbp, [rsp-158h]
0x18000dc79  sub     rsp, 258h
0x18000dc80  mov     rax, cs:__security_cookie
0x18000dc87  xor     rax, rsp
0x18000dc8a  mov     [rbp+180h+var_40], rax
0x18000dc91  xor     r15d, r15d
0x18000dc94  lea     rax, [rsp+280h+Name]
0x18000dc99  mov     [r8], r15
0x18000dc9c  mov     r14, r8
0x18000dc9f  mov     edx, 104h
0x18000dca4  mov     r9d, 7FFFFFFEh
0x18000dcaa  test    r9, r9
0x18000dcad  jz      short loc_18000DCCE
0x18000dcaf  movzx   r8d, word ptr [rcx]
0x18000dcb3  test    r8w, r8w
0x18000dcb7  jz      short loc_18000DCCE
0x18000dcb9  mov     [rax], r8w
0x18000dcbd  add     rcx, 2
0x18000dcc1  add     rax, 2
0x18000dcc5  dec     r9
0x18000dcc8  sub     rdx, 1; unsigned __int64
0x18000dccc  jnz     short loc_18000DCAA
0x18000dcce  test    rdx, rdx
0x18000dcd1  lea     rcx, [rax-2]
0x18000dcd5  lea     r8, aP0; "_p0"
0x18000dcdc  cmovnz  rcx, rax
0x18000dce0  mov     [rcx], r15w
0x18000dce4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dce9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dcee  mov     esi, 1F0003h
0x18000dcf3  lea     r8, [rsp+280h+Name]; lpName
0x18000dcf8  mov     ecx, esi; dwDesiredAccess
0x18000dcfa  xor     edx, edx; bInheritHandle
0x18000dcfc  call    cs:__imp_OpenSemaphoreW
0x18000dd02  mov     rbx, rax
0x18000dd05  test    rax, rax
0x18000dd08  jz      loc_18000DE45
0x18000dd0e  lea     rdx, [rsp+280h+var_25C]; int *
0x18000dd13  mov     [rsp+280h+var_25C], r15d
0x18000dd18  mov     rcx, rax; hHandle
0x18000dd1b  mov     [rsp+280h+var_260], r15d; int
0x18000dd20  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dd25  mov     edi, eax
0x18000dd27  test    eax, eax
0x18000dd29  jns     short loc_18000DD5E
0x18000dd2b  mov     rcx, [rbp+188h]; this
0x18000dd32  lea     r8, aWil; "wil"
0x18000dd39  mov     r9d, eax; char *
0x18000dd3c  mov     edx, 0D6h; void *
0x18000dd41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd46  mov     rcx, rbx; hObject
0x18000dd49  call    cs:__imp_CloseHandle
0x18000dd4f  test    eax, eax
0x18000dd51  jz      loc_18000DEC1
0x18000dd57  mov     eax, edi
0x18000dd59  jmp     loc_18000DE6C
0x18000dd5e  lea     r8, asc_1800F2F38; "h"
0x18000dd65  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dd6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dd6f  lea     r8, [rsp+280h+Name]; lpName
0x18000dd74  xor     edx, edx; bInheritHandle
0x18000dd76  mov     ecx, esi; dwDesiredAccess
0x18000dd78  call    cs:__imp_OpenSemaphoreW
0x18000dd7e  mov     rdi, rax
0x18000dd81  test    rax, rax
0x18000dd84  jz      loc_18000DE19
0x18000dd8a  lea     rdx, [rsp+280h+var_260]; int *
0x18000dd8f  mov     rcx, rax; hHandle
0x18000dd92  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dd97  mov     esi, eax
0x18000dd99  test    eax, eax
0x18000dd9b  jns     short loc_18000DDE1
0x18000dd9d  mov     rcx, [rbp+188h]; this
0x18000dda4  lea     r8, aWil; "wil"
0x18000ddab  mov     r9d, eax; char *
0x18000ddae  mov     edx, 0DEh; void *
0x18000ddb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddb8  mov     rcx, rdi; hObject
0x18000ddbb  call    cs:__imp_CloseHandle
0x18000ddc1  test    eax, eax
0x18000ddc3  jz      loc_18000DED3
0x18000ddc9  mov     rcx, rbx; hObject
0x18000ddcc  call    cs:__imp_CloseHandle
0x18000ddd2  test    eax, eax
0x18000ddd4  jz      loc_18000DEE5
0x18000ddda  mov     eax, esi
0x18000dddc  jmp     loc_18000DE6C
0x18000dde1  mov     rcx, rdi; hObject
0x18000dde4  call    cs:__imp_CloseHandle
0x18000ddea  test    eax, eax
0x18000ddec  jz      loc_18000DE8B
0x18000ddf2  movsxd  rax, [rsp+280h+var_25C]
0x18000ddf7  movsxd  rcx, [rsp+280h+var_260]
0x18000ddfc  shl     rcx, 1Fh
0x18000de00  or      rcx, rax
0x18000de03  mov     [r14], rcx
0x18000de06  mov     rcx, rbx; hObject
0x18000de09  call    cs:__imp_CloseHandle
0x18000de0f  test    eax, eax
0x18000de11  jz      loc_18000DE9D
0x18000de17  jmp     short loc_18000DE50
0x18000de19  mov     rcx, [rbp+188h]; this
0x18000de20  lea     r8, aWil; "wil"
0x18000de27  mov     edx, 0DCh; void *
0x18000de2c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de31  mov     rcx, rbx; hObject
0x18000de34  mov     edi, eax
0x18000de36  call    cs:__imp_CloseHandle
0x18000de3c  test    eax, eax
0x18000de3e  jz      short loc_18000DEAF
0x18000de40  jmp     loc_18000DD57
0x18000de45  call    cs:__imp_GetLastError
0x18000de4b  cmp     eax, 2
0x18000de4e  jnz     short loc_18000DE54
0x18000de50  xor     eax, eax
0x18000de52  jmp     short loc_18000DE6C
0x18000de54  mov     rcx, [rbp+188h]; this
0x18000de5b  lea     r8, aWil; "wil"
0x18000de62  mov     edx, 0D0h; void *
0x18000de67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de6c  mov     rcx, [rbp+180h+var_40]
0x18000de73  xor     rcx, rsp; StackCookie
0x18000de76  call    __security_check_cookie
0x18000de7b  add     rsp, 258h
0x18000de82  pop     r15
0x18000de84  pop     r14
0x18000de86  pop     rdi
0x18000de87  pop     rsi
0x18000de88  pop     rbx
0x18000de89  pop     rbp
0x18000de8a  retn
0x18000de8b  mov     rcx, [rbp+188h]; this
0x18000de92  mov     edx, 0A0Bh; void *
0x18000de97  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000de9d  mov     rcx, [rbp+188h]; this
0x18000dea4  mov     edx, 0A0Bh; void *
0x18000dea9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000deaf  mov     rcx, [rbp+188h]; this
0x18000deb6  mov     edx, 0A0Bh; void *
0x18000debb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dec1  mov     rcx, [rbp+188h]; this
0x18000dec8  mov     edx, 0A0Bh; void *
0x18000decd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ded3  mov     rcx, [rbp+188h]; this
0x18000deda  mov     edx, 0A0Bh; void *
0x18000dedf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dee5  mov     rcx, [rbp+188h]; this
0x18000deec  mov     edx, 0A0Bh; void *
0x18000def1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

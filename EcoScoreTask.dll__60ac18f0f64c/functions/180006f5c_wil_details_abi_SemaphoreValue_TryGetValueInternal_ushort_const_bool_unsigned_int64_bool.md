# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006f5c`
- end: `0x1800071d6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003648`

## callees

- `0x180004a24`
- `0x180005e4c`
- `0x180005e6c`
- `0x180006e20`
- `0x180006f5c`
- `0x1800078f4`
- `0x180007c90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000703d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000711c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000703d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000711c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000712b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000712b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ff0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000706c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ff0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000706c`

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
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  __int64 v18; // r8
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x180006f5c  push    rbp
0x180006f5e  push    rbx
0x180006f5f  push    rsi
0x180006f60  push    rdi
0x180006f61  push    r14
0x180006f63  push    r15
0x180006f65  lea     rbp, [rsp-158h]
0x180006f6d  sub     rsp, 258h
0x180006f74  mov     rax, cs:__security_cookie
0x180006f7b  xor     rax, rsp
0x180006f7e  mov     [rbp+180h+var_40], rax
0x180006f85  xor     r15d, r15d
0x180006f88  lea     rax, [rsp+280h+Name]
0x180006f8d  mov     [r8], r15
0x180006f90  mov     r14, r8
0x180006f93  mov     edx, 104h
0x180006f98  mov     r9d, 7FFFFFFEh
0x180006f9e  test    r9, r9
0x180006fa1  jz      short loc_180006FC2
0x180006fa3  movzx   r8d, word ptr [rcx]
0x180006fa7  test    r8w, r8w
0x180006fab  jz      short loc_180006FC2
0x180006fad  mov     [rax], r8w
0x180006fb1  add     rcx, 2
0x180006fb5  add     rax, 2
0x180006fb9  dec     r9
0x180006fbc  sub     rdx, 1; unsigned __int64
0x180006fc0  jnz     short loc_180006F9E
0x180006fc2  test    rdx, rdx
0x180006fc5  lea     rcx, [rax-2]
0x180006fc9  lea     r8, aP0; "_p0"
0x180006fd0  cmovnz  rcx, rax
0x180006fd4  mov     [rcx], r15w
0x180006fd8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006fdd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006fe2  mov     esi, 1F0003h
0x180006fe7  lea     r8, [rsp+280h+Name]; lpName
0x180006fec  mov     ecx, esi; dwDesiredAccess
0x180006fee  xor     edx, edx; bInheritHandle
0x180006ff0  call    cs:__imp_OpenSemaphoreW
0x180006ff6  mov     rbx, rax
0x180006ff9  test    rax, rax
0x180006ffc  jz      loc_18000712B
0x180007002  lea     rdx, [rsp+280h+var_25C]; int *
0x180007007  mov     [rsp+280h+var_25C], r15d
0x18000700c  mov     rcx, rax; hHandle
0x18000700f  mov     [rsp+280h+var_260], r15d; int
0x180007014  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007019  mov     edi, eax
0x18000701b  test    eax, eax
0x18000701d  jns     short loc_180007052
0x18000701f  mov     rcx, [rbp+188h]; this
0x180007026  lea     r8, aWil; "wil"
0x18000702d  mov     r9d, eax; char *
0x180007030  mov     edx, 0D6h; void *
0x180007035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000703a  mov     rcx, rbx; hObject
0x18000703d  call    cs:__imp_CloseHandle
0x180007043  test    eax, eax
0x180007045  jz      loc_1800071A0
0x18000704b  mov     eax, edi
0x18000704d  jmp     loc_18000714B
0x180007052  lea     r8, asc_18000A908; "h"
0x180007059  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000705e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007063  lea     r8, [rsp+280h+Name]; lpName
0x180007068  xor     edx, edx; bInheritHandle
0x18000706a  mov     ecx, esi; dwDesiredAccess
0x18000706c  call    cs:__imp_OpenSemaphoreW
0x180007072  mov     rdi, rax
0x180007075  test    rax, rax
0x180007078  jz      loc_180007106
0x18000707e  lea     rdx, [rsp+280h+var_260]; int *
0x180007083  mov     rcx, rax; hHandle
0x180007086  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000708b  mov     esi, eax
0x18000708d  test    eax, eax
0x18000708f  jns     short loc_1800070D2
0x180007091  mov     rcx, [rbp+188h]; this
0x180007098  lea     r8, aWil; "wil"
0x18000709f  mov     r9d, eax; char *
0x1800070a2  mov     edx, 0DEh; void *
0x1800070a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070ac  mov     rcx, rdi; hObject
0x1800070af  call    cs:__imp_CloseHandle
0x1800070b5  test    eax, eax
0x1800070b7  jz      loc_1800071B2
0x1800070bd  mov     rcx, rbx; hObject
0x1800070c0  call    cs:__imp_CloseHandle
0x1800070c6  test    eax, eax
0x1800070c8  jz      loc_1800071C4
0x1800070ce  mov     eax, esi
0x1800070d0  jmp     short loc_18000714B
0x1800070d2  mov     rcx, rdi; hObject
0x1800070d5  call    cs:__imp_CloseHandle
0x1800070db  test    eax, eax
0x1800070dd  jz      loc_18000716A
0x1800070e3  movsxd  rax, [rsp+280h+var_25C]
0x1800070e8  movsxd  rcx, [rsp+280h+var_260]
0x1800070ed  shl     rcx, 1Fh
0x1800070f1  or      rcx, rax
0x1800070f4  mov     [r14], rcx
0x1800070f7  mov     rcx, rbx; hObject
0x1800070fa  call    cs:__imp_CloseHandle
0x180007100  test    eax, eax
0x180007102  jz      short loc_18000717C
0x180007104  jmp     short loc_180007136
0x180007106  mov     rcx, [rbp+188h]; this
0x18000710d  mov     edx, 0DCh; void *
0x180007112  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007117  mov     rcx, rbx; hObject
0x18000711a  mov     edi, eax
0x18000711c  call    cs:__imp_CloseHandle
0x180007122  test    eax, eax
0x180007124  jz      short loc_18000718E
0x180007126  jmp     loc_18000704B
0x18000712b  call    cs:__imp_GetLastError
0x180007131  cmp     eax, 2
0x180007134  jnz     short loc_18000713A
0x180007136  xor     eax, eax
0x180007138  jmp     short loc_18000714B
0x18000713a  mov     rcx, [rbp+188h]; this
0x180007141  mov     edx, 0D0h; void *
0x180007146  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000714b  mov     rcx, [rbp+180h+var_40]
0x180007152  xor     rcx, rsp; StackCookie
0x180007155  call    __security_check_cookie
0x18000715a  add     rsp, 258h
0x180007161  pop     r15
0x180007163  pop     r14
0x180007165  pop     rdi
0x180007166  pop     rsi
0x180007167  pop     rbx
0x180007168  pop     rbp
0x180007169  retn
0x18000716a  mov     rcx, [rbp+188h]; this
0x180007171  mov     edx, 0A0Bh; void *
0x180007176  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000717c  mov     rcx, [rbp+188h]; this
0x180007183  mov     edx, 0A0Bh; void *
0x180007188  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000718e  mov     rcx, [rbp+188h]; this
0x180007195  mov     edx, 0A0Bh; void *
0x18000719a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071a0  mov     rcx, [rbp+188h]; this
0x1800071a7  mov     edx, 0A0Bh; void *
0x1800071ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071b2  mov     rcx, [rbp+188h]; this
0x1800071b9  mov     edx, 0A0Bh; void *
0x1800071be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071c4  mov     rcx, [rbp+188h]; this
0x1800071cb  mov     edx, 0A0Bh; void *
0x1800071d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

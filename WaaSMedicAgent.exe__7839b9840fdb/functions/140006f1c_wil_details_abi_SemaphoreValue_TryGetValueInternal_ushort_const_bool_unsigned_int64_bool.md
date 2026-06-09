# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140006f1c`
- end: `0x1400071ab`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400048f8`
- `0x14000c164`

## callees

- `0x140002a30`
- `0x140005a18`
- `0x140006424`
- `0x14000644c`
- `0x140006db0`
- `0x140006f1c`
- `0x1400073c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006fb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000702c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006fb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000702c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006ffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000706f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400070bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400070ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006ffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000706f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400070bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400070ea`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
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
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
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
0x140006f1c  push    rbp
0x140006f1e  push    rbx
0x140006f1f  push    rsi
0x140006f20  push    rdi
0x140006f21  push    r14
0x140006f23  push    r15
0x140006f25  lea     rbp, [rsp-158h]
0x140006f2d  sub     rsp, 258h
0x140006f34  mov     rax, cs:__security_cookie
0x140006f3b  xor     rax, rsp
0x140006f3e  mov     [rbp+180h+var_40], rax
0x140006f45  xor     r15d, r15d
0x140006f48  lea     rax, [rsp+280h+Name]
0x140006f4d  mov     [r8], r15
0x140006f50  mov     r14, r8
0x140006f53  mov     edx, 104h
0x140006f58  mov     r9d, 7FFFFFFEh
0x140006f5e  test    r9, r9
0x140006f61  jz      short loc_140006F82
0x140006f63  movzx   r8d, word ptr [rcx]
0x140006f67  test    r8w, r8w
0x140006f6b  jz      short loc_140006F82
0x140006f6d  mov     [rax], r8w
0x140006f71  add     rcx, 2
0x140006f75  add     rax, 2
0x140006f79  dec     r9
0x140006f7c  sub     rdx, 1; unsigned __int64
0x140006f80  jnz     short loc_140006F5E
0x140006f82  test    rdx, rdx
0x140006f85  lea     rcx, [rax-2]
0x140006f89  lea     r8, aP0; "_p0"
0x140006f90  cmovnz  rcx, rax
0x140006f94  mov     [rcx], r15w
0x140006f98  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006f9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006fa2  mov     esi, 1F0003h
0x140006fa7  lea     r8, [rsp+280h+Name]; lpName
0x140006fac  mov     ecx, esi; dwDesiredAccess
0x140006fae  xor     edx, edx; bInheritHandle
0x140006fb0  call    cs:__imp_OpenSemaphoreW
0x140006fb6  mov     rbx, rax
0x140006fb9  test    rax, rax
0x140006fbc  jz      loc_1400070F9
0x140006fc2  lea     rdx, [rsp+280h+var_25C]; int *
0x140006fc7  mov     [rsp+280h+var_25C], r15d
0x140006fcc  mov     rcx, rax; hHandle
0x140006fcf  mov     [rsp+280h+var_260], r15d; int
0x140006fd4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006fd9  mov     edi, eax
0x140006fdb  test    eax, eax
0x140006fdd  jns     short loc_140007012
0x140006fdf  mov     rcx, [rbp+188h]; this
0x140006fe6  lea     r8, aWil; "wil"
0x140006fed  mov     r9d, eax; char *
0x140006ff0  mov     edx, 0D6h; void *
0x140006ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006ffa  mov     rcx, rbx; hObject
0x140006ffd  call    cs:__imp_CloseHandle
0x140007003  test    eax, eax
0x140007005  jz      loc_140007175
0x14000700b  mov     eax, edi
0x14000700d  jmp     loc_140007120
0x140007012  lea     r8, asc_140015340; "h"
0x140007019  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000701e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007023  lea     r8, [rsp+280h+Name]; lpName
0x140007028  xor     edx, edx; bInheritHandle
0x14000702a  mov     ecx, esi; dwDesiredAccess
0x14000702c  call    cs:__imp_OpenSemaphoreW
0x140007032  mov     rdi, rax
0x140007035  test    rax, rax
0x140007038  jz      loc_1400070CD
0x14000703e  lea     rdx, [rsp+280h+var_260]; int *
0x140007043  mov     rcx, rax; hHandle
0x140007046  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000704b  mov     esi, eax
0x14000704d  test    eax, eax
0x14000704f  jns     short loc_140007095
0x140007051  mov     rcx, [rbp+188h]; this
0x140007058  lea     r8, aWil; "wil"
0x14000705f  mov     r9d, eax; char *
0x140007062  mov     edx, 0DEh; void *
0x140007067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000706c  mov     rcx, rdi; hObject
0x14000706f  call    cs:__imp_CloseHandle
0x140007075  test    eax, eax
0x140007077  jz      loc_140007187
0x14000707d  mov     rcx, rbx; hObject
0x140007080  call    cs:__imp_CloseHandle
0x140007086  test    eax, eax
0x140007088  jz      loc_140007199
0x14000708e  mov     eax, esi
0x140007090  jmp     loc_140007120
0x140007095  mov     rcx, rdi; hObject
0x140007098  call    cs:__imp_CloseHandle
0x14000709e  test    eax, eax
0x1400070a0  jz      loc_14000713F
0x1400070a6  movsxd  rax, [rsp+280h+var_25C]
0x1400070ab  movsxd  rcx, [rsp+280h+var_260]
0x1400070b0  shl     rcx, 1Fh
0x1400070b4  or      rcx, rax
0x1400070b7  mov     [r14], rcx
0x1400070ba  mov     rcx, rbx; hObject
0x1400070bd  call    cs:__imp_CloseHandle
0x1400070c3  test    eax, eax
0x1400070c5  jz      loc_140007151
0x1400070cb  jmp     short loc_140007104
0x1400070cd  mov     rcx, [rbp+188h]; this
0x1400070d4  lea     r8, aWil; "wil"
0x1400070db  mov     edx, 0DCh; void *
0x1400070e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400070e5  mov     rcx, rbx; hObject
0x1400070e8  mov     edi, eax
0x1400070ea  call    cs:__imp_CloseHandle
0x1400070f0  test    eax, eax
0x1400070f2  jz      short loc_140007163
0x1400070f4  jmp     loc_14000700B
0x1400070f9  call    cs:__imp_GetLastError
0x1400070ff  cmp     eax, 2
0x140007102  jnz     short loc_140007108
0x140007104  xor     eax, eax
0x140007106  jmp     short loc_140007120
0x140007108  mov     rcx, [rbp+188h]; this
0x14000710f  lea     r8, aWil; "wil"
0x140007116  mov     edx, 0D0h; void *
0x14000711b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007120  mov     rcx, [rbp+180h+var_40]
0x140007127  xor     rcx, rsp; StackCookie
0x14000712a  call    __security_check_cookie
0x14000712f  add     rsp, 258h
0x140007136  pop     r15
0x140007138  pop     r14
0x14000713a  pop     rdi
0x14000713b  pop     rsi
0x14000713c  pop     rbx
0x14000713d  pop     rbp
0x14000713e  retn
0x14000713f  mov     rcx, [rbp+188h]; this
0x140007146  mov     edx, 0A0Bh; void *
0x14000714b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007151  mov     rcx, [rbp+188h]; this
0x140007158  mov     edx, 0A0Bh; void *
0x14000715d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007163  mov     rcx, [rbp+188h]; this
0x14000716a  mov     edx, 0A0Bh; void *
0x14000716f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007175  mov     rcx, [rbp+188h]; this
0x14000717c  mov     edx, 0A0Bh; void *
0x140007181  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007187  mov     rcx, [rbp+188h]; this
0x14000718e  mov     edx, 0A0Bh; void *
0x140007193  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007199  mov     rcx, [rbp+188h]; this
0x1400071a0  mov     edx, 0A0Bh; void *
0x1400071a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

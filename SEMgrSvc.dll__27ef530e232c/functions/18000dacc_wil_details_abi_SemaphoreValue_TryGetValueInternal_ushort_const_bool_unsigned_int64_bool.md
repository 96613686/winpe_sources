# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000dacc`
- end: `0x18000dd64`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800088b8`
- `0x180008c94`

## callees

- `0x1800049a0`
- `0x18000a518`
- `0x18000c944`
- `0x18000c964`
- `0x18000d3b4`
- `0x18000dacc`
- `0x18000e4c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000db63`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dbe5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000db63`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dca3`

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
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000dacc  push    rbp
0x18000dace  push    rbx
0x18000dacf  push    rsi
0x18000dad0  push    rdi
0x18000dad1  push    r14
0x18000dad3  push    r15
0x18000dad5  lea     rbp, [rsp-158h]
0x18000dadd  sub     rsp, 258h
0x18000dae4  mov     rax, cs:__security_cookie
0x18000daeb  xor     rax, rsp
0x18000daee  mov     [rbp+180h+var_40], rax
0x18000daf5  xor     r15d, r15d
0x18000daf8  lea     rax, [rsp+280h+Name]
0x18000dafd  mov     esi, 104h
0x18000db02  mov     [r8], r15
0x18000db05  mov     edx, esi
0x18000db07  mov     r14, r8
0x18000db0a  mov     r9d, 7FFFFFFEh
0x18000db10  test    r9, r9
0x18000db13  jz      short loc_18000DB34
0x18000db15  movzx   r8d, word ptr [rcx]
0x18000db19  test    r8w, r8w
0x18000db1d  jz      short loc_18000DB34
0x18000db1f  mov     [rax], r8w
0x18000db23  add     rcx, 2
0x18000db27  add     rax, 2
0x18000db2b  dec     r9
0x18000db2e  sub     rdx, 1
0x18000db32  jnz     short loc_18000DB10
0x18000db34  test    rdx, rdx
0x18000db37  lea     rcx, [rax-2]
0x18000db3b  lea     r8, aP0; "_p0"
0x18000db42  mov     rdx, rsi; unsigned __int64
0x18000db45  cmovnz  rcx, rax
0x18000db49  mov     [rcx], r15w
0x18000db4d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000db52  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000db57  lea     r8, [rsp+280h+Name]; lpName
0x18000db5c  xor     edx, edx; bInheritHandle
0x18000db5e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000db63  call    cs:__imp_OpenSemaphoreW
0x18000db69  mov     rbx, rax
0x18000db6c  test    rax, rax
0x18000db6f  jz      loc_18000DCB2
0x18000db75  lea     rdx, [rsp+280h+var_25C]; int *
0x18000db7a  mov     [rsp+280h+var_25C], r15d
0x18000db7f  mov     rcx, rax; hHandle
0x18000db82  mov     [rsp+280h+var_260], r15d; int
0x18000db87  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000db8c  mov     edi, eax
0x18000db8e  test    eax, eax
0x18000db90  jns     short loc_18000DBC5
0x18000db92  mov     rcx, [rbp+188h]; this
0x18000db99  lea     r8, aWil; "wil"
0x18000dba0  mov     r9d, eax; char *
0x18000dba3  mov     edx, 0D6h; void *
0x18000dba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbad  mov     rcx, rbx; hObject
0x18000dbb0  call    cs:__imp_CloseHandle
0x18000dbb6  test    eax, eax
0x18000dbb8  jz      loc_18000DD2E
0x18000dbbe  mov     eax, edi
0x18000dbc0  jmp     loc_18000DCD9
0x18000dbc5  lea     r8, asc_1800A5EC8; "h"
0x18000dbcc  mov     rdx, rsi; unsigned __int64
0x18000dbcf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dbd4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dbd9  lea     r8, [rsp+280h+Name]; lpName
0x18000dbde  xor     edx, edx; bInheritHandle
0x18000dbe0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000dbe5  call    cs:__imp_OpenSemaphoreW
0x18000dbeb  mov     rdi, rax
0x18000dbee  test    rax, rax
0x18000dbf1  jz      loc_18000DC86
0x18000dbf7  lea     rdx, [rsp+280h+var_260]; int *
0x18000dbfc  mov     rcx, rax; hHandle
0x18000dbff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dc04  mov     esi, eax
0x18000dc06  test    eax, eax
0x18000dc08  jns     short loc_18000DC4E
0x18000dc0a  mov     rcx, [rbp+188h]; this
0x18000dc11  lea     r8, aWil; "wil"
0x18000dc18  mov     r9d, eax; char *
0x18000dc1b  mov     edx, 0DEh; void *
0x18000dc20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc25  mov     rcx, rdi; hObject
0x18000dc28  call    cs:__imp_CloseHandle
0x18000dc2e  test    eax, eax
0x18000dc30  jz      loc_18000DD40
0x18000dc36  mov     rcx, rbx; hObject
0x18000dc39  call    cs:__imp_CloseHandle
0x18000dc3f  test    eax, eax
0x18000dc41  jz      loc_18000DD52
0x18000dc47  mov     eax, esi
0x18000dc49  jmp     loc_18000DCD9
0x18000dc4e  mov     rcx, rdi; hObject
0x18000dc51  call    cs:__imp_CloseHandle
0x18000dc57  test    eax, eax
0x18000dc59  jz      loc_18000DCF8
0x18000dc5f  movsxd  rax, [rsp+280h+var_25C]
0x18000dc64  movsxd  rcx, [rsp+280h+var_260]
0x18000dc69  shl     rcx, 1Fh
0x18000dc6d  or      rcx, rax
0x18000dc70  mov     [r14], rcx
0x18000dc73  mov     rcx, rbx; hObject
0x18000dc76  call    cs:__imp_CloseHandle
0x18000dc7c  test    eax, eax
0x18000dc7e  jz      loc_18000DD0A
0x18000dc84  jmp     short loc_18000DCBD
0x18000dc86  mov     rcx, [rbp+188h]; this
0x18000dc8d  lea     r8, aWil; "wil"
0x18000dc94  mov     edx, 0DCh; void *
0x18000dc99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dc9e  mov     rcx, rbx; hObject
0x18000dca1  mov     edi, eax
0x18000dca3  call    cs:__imp_CloseHandle
0x18000dca9  test    eax, eax
0x18000dcab  jz      short loc_18000DD1C
0x18000dcad  jmp     loc_18000DBBE
0x18000dcb2  call    cs:__imp_GetLastError
0x18000dcb8  cmp     eax, 2
0x18000dcbb  jnz     short loc_18000DCC1
0x18000dcbd  xor     eax, eax
0x18000dcbf  jmp     short loc_18000DCD9
0x18000dcc1  mov     rcx, [rbp+188h]; this
0x18000dcc8  lea     r8, aWil; "wil"
0x18000dccf  mov     edx, 0D0h; void *
0x18000dcd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dcd9  mov     rcx, [rbp+180h+var_40]
0x18000dce0  xor     rcx, rsp; StackCookie
0x18000dce3  call    __security_check_cookie
0x18000dce8  add     rsp, 258h
0x18000dcef  pop     r15
0x18000dcf1  pop     r14
0x18000dcf3  pop     rdi
0x18000dcf4  pop     rsi
0x18000dcf5  pop     rbx
0x18000dcf6  pop     rbp
0x18000dcf7  retn
0x18000dcf8  mov     rcx, [rbp+188h]; this
0x18000dcff  mov     edx, 0A0Bh; void *
0x18000dd04  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd0a  mov     rcx, [rbp+188h]; this
0x18000dd11  mov     edx, 0A0Bh; void *
0x18000dd16  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd1c  mov     rcx, [rbp+188h]; this
0x18000dd23  mov     edx, 0A0Bh; void *
0x18000dd28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd2e  mov     rcx, [rbp+188h]; this
0x18000dd35  mov     edx, 0A0Bh; void *
0x18000dd3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd40  mov     rcx, [rbp+188h]; this
0x18000dd47  mov     edx, 0A0Bh; void *
0x18000dd4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd52  mov     rcx, [rbp+188h]; this
0x18000dd59  mov     edx, 0A0Bh; void *
0x18000dd5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

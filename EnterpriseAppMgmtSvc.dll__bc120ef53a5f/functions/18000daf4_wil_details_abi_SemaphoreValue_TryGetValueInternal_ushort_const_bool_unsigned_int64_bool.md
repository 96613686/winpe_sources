# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000daf4`
- end: `0x18000ddc3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a660`
- `0x18002bab0`

## callees

- `0x18000b618`
- `0x18000d3bc`
- `0x18000d3dc`
- `0x18000d520`
- `0x18000daf4`
- `0x18000e7c8`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcf5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000db8b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dc19`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000db8b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dc19`

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
0x18000daf4  push    rbp
0x18000daf6  push    rbx
0x18000daf7  push    rsi
0x18000daf8  push    rdi
0x18000daf9  push    r14
0x18000dafb  push    r15
0x18000dafd  lea     rbp, [rsp-158h]
0x18000db05  sub     rsp, 258h
0x18000db0c  mov     rax, cs:__security_cookie
0x18000db13  xor     rax, rsp
0x18000db16  mov     [rbp+180h+var_40], rax
0x18000db1d  xor     r15d, r15d
0x18000db20  lea     rax, [rsp+280h+Name]
0x18000db25  mov     esi, 104h
0x18000db2a  mov     [r8], r15
0x18000db2d  mov     edx, esi
0x18000db2f  mov     r14, r8
0x18000db32  mov     r9d, 7FFFFFFEh
0x18000db38  test    r9, r9
0x18000db3b  jz      short loc_18000DB5C
0x18000db3d  movzx   r8d, word ptr [rcx]
0x18000db41  test    r8w, r8w
0x18000db45  jz      short loc_18000DB5C
0x18000db47  mov     [rax], r8w
0x18000db4b  add     rcx, 2
0x18000db4f  add     rax, 2
0x18000db53  dec     r9
0x18000db56  sub     rdx, 1
0x18000db5a  jnz     short loc_18000DB38
0x18000db5c  test    rdx, rdx
0x18000db5f  lea     rcx, [rax-2]
0x18000db63  lea     r8, aP0; "_p0"
0x18000db6a  mov     rdx, rsi; unsigned __int64
0x18000db6d  cmovnz  rcx, rax
0x18000db71  mov     [rcx], r15w
0x18000db75  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000db7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000db7f  lea     r8, [rsp+280h+Name]; lpName
0x18000db84  xor     edx, edx; bInheritHandle
0x18000db86  mov     ecx, 1F0003h; dwDesiredAccess
0x18000db8b  call    cs:__imp_OpenSemaphoreW
0x18000db92  nop     dword ptr [rax+rax+00h]
0x18000db97  mov     rbx, rax
0x18000db9a  test    rax, rax
0x18000db9d  jz      loc_18000DD0A
0x18000dba3  lea     rdx, [rsp+280h+var_25C]; int *
0x18000dba8  mov     [rsp+280h+var_25C], r15d
0x18000dbad  mov     rcx, rax; hHandle
0x18000dbb0  mov     [rsp+280h+var_260], r15d; int
0x18000dbb5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dbba  mov     edi, eax
0x18000dbbc  test    eax, eax
0x18000dbbe  jns     short loc_18000DBF9
0x18000dbc0  mov     rcx, [rbp+188h]; this
0x18000dbc7  lea     r8, aWil; "wil"
0x18000dbce  mov     r9d, eax; char *
0x18000dbd1  mov     edx, 0D6h; void *
0x18000dbd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbdb  mov     rcx, rbx; hObject
0x18000dbde  call    cs:__imp_CloseHandle
0x18000dbe5  nop     dword ptr [rax+rax+00h]
0x18000dbea  test    eax, eax
0x18000dbec  jz      loc_18000DD8D
0x18000dbf2  mov     eax, edi
0x18000dbf4  jmp     loc_18000DD37
0x18000dbf9  lea     r8, asc_1800773B8; "h"
0x18000dc00  mov     rdx, rsi; unsigned __int64
0x18000dc03  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dc08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dc0d  lea     r8, [rsp+280h+Name]; lpName
0x18000dc12  xor     edx, edx; bInheritHandle
0x18000dc14  mov     ecx, 1F0003h; dwDesiredAccess
0x18000dc19  call    cs:__imp_OpenSemaphoreW
0x18000dc20  nop     dword ptr [rax+rax+00h]
0x18000dc25  mov     rdi, rax
0x18000dc28  test    rax, rax
0x18000dc2b  jz      loc_18000DCD8
0x18000dc31  lea     rdx, [rsp+280h+var_260]; int *
0x18000dc36  mov     rcx, rax; hHandle
0x18000dc39  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dc3e  mov     esi, eax
0x18000dc40  test    eax, eax
0x18000dc42  jns     short loc_18000DC94
0x18000dc44  mov     rcx, [rbp+188h]; this
0x18000dc4b  lea     r8, aWil; "wil"
0x18000dc52  mov     r9d, eax; char *
0x18000dc55  mov     edx, 0DEh; void *
0x18000dc5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc5f  mov     rcx, rdi; hObject
0x18000dc62  call    cs:__imp_CloseHandle
0x18000dc69  nop     dword ptr [rax+rax+00h]
0x18000dc6e  test    eax, eax
0x18000dc70  jz      loc_18000DD9F
0x18000dc76  mov     rcx, rbx; hObject
0x18000dc79  call    cs:__imp_CloseHandle
0x18000dc80  nop     dword ptr [rax+rax+00h]
0x18000dc85  test    eax, eax
0x18000dc87  jz      loc_18000DDB1
0x18000dc8d  mov     eax, esi
0x18000dc8f  jmp     loc_18000DD37
0x18000dc94  mov     rcx, rdi; hObject
0x18000dc97  call    cs:__imp_CloseHandle
0x18000dc9e  nop     dword ptr [rax+rax+00h]
0x18000dca3  test    eax, eax
0x18000dca5  jz      loc_18000DD57
0x18000dcab  movsxd  rax, [rsp+280h+var_25C]
0x18000dcb0  movsxd  rcx, [rsp+280h+var_260]
0x18000dcb5  shl     rcx, 1Fh
0x18000dcb9  or      rcx, rax
0x18000dcbc  mov     [r14], rcx
0x18000dcbf  mov     rcx, rbx; hObject
0x18000dcc2  call    cs:__imp_CloseHandle
0x18000dcc9  nop     dword ptr [rax+rax+00h]
0x18000dcce  test    eax, eax
0x18000dcd0  jz      loc_18000DD69
0x18000dcd6  jmp     short loc_18000DD1B
0x18000dcd8  mov     rcx, [rbp+188h]; this
0x18000dcdf  lea     r8, aWil; "wil"
0x18000dce6  mov     edx, 0DCh; void *
0x18000dceb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dcf0  mov     rcx, rbx; hObject
0x18000dcf3  mov     edi, eax
0x18000dcf5  call    cs:__imp_CloseHandle
0x18000dcfc  nop     dword ptr [rax+rax+00h]
0x18000dd01  test    eax, eax
0x18000dd03  jz      short loc_18000DD7B
0x18000dd05  jmp     loc_18000DBF2
0x18000dd0a  call    cs:__imp_GetLastError
0x18000dd11  nop     dword ptr [rax+rax+00h]
0x18000dd16  cmp     eax, 2
0x18000dd19  jnz     short loc_18000DD1F
0x18000dd1b  xor     eax, eax
0x18000dd1d  jmp     short loc_18000DD37
0x18000dd1f  mov     rcx, [rbp+188h]; this
0x18000dd26  lea     r8, aWil; "wil"
0x18000dd2d  mov     edx, 0D0h; void *
0x18000dd32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dd37  mov     rcx, [rbp+180h+var_40]
0x18000dd3e  xor     rcx, rsp; StackCookie
0x18000dd41  call    __security_check_cookie
0x18000dd46  add     rsp, 258h
0x18000dd4d  pop     r15
0x18000dd4f  pop     r14
0x18000dd51  pop     rdi
0x18000dd52  pop     rsi
0x18000dd53  pop     rbx
0x18000dd54  pop     rbp
0x18000dd55  retn
0x18000dd57  mov     rcx, [rbp+188h]; this
0x18000dd5e  mov     edx, 0A0Bh; void *
0x18000dd63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd69  mov     rcx, [rbp+188h]; this
0x18000dd70  mov     edx, 0A0Bh; void *
0x18000dd75  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd7b  mov     rcx, [rbp+188h]; this
0x18000dd82  mov     edx, 0A0Bh; void *
0x18000dd87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd8d  mov     rcx, [rbp+188h]; this
0x18000dd94  mov     edx, 0A0Bh; void *
0x18000dd99  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd9f  mov     rcx, [rbp+188h]; this
0x18000dda6  mov     edx, 0A0Bh; void *
0x18000ddab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ddb1  mov     rcx, [rbp+188h]; this
0x18000ddb8  mov     edx, 0A0Bh; void *
0x18000ddbd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

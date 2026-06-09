# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005138`
- end: `0x1400053a4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400030b0`
- `0x1400063bc`

## callees

- `0x140004170`
- `0x140004cc0`
- `0x140004ce0`
- `0x140004ffc`
- `0x140005138`
- `0x1400054fc`
- `0x1400134a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400051cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005241`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400051cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000527d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000528e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000527d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000528e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052ea`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x140005138  push    rbp
0x14000513a  push    rbx
0x14000513b  push    rsi
0x14000513c  push    rdi
0x14000513d  push    r14
0x14000513f  push    r15
0x140005141  lea     rbp, [rsp-158h]
0x140005149  sub     rsp, 258h
0x140005150  mov     rax, cs:__security_cookie
0x140005157  xor     rax, rsp
0x14000515a  mov     [rbp+180h+var_40], rax
0x140005161  xor     r15d, r15d
0x140005164  lea     rax, [rsp+280h+Name]
0x140005169  mov     [r8], r15
0x14000516c  mov     r14, r8
0x14000516f  mov     edx, 104h
0x140005174  mov     r9d, 7FFFFFFEh
0x14000517a  test    r9, r9
0x14000517d  jz      short loc_14000519E
0x14000517f  movzx   r8d, word ptr [rcx]
0x140005183  test    r8w, r8w
0x140005187  jz      short loc_14000519E
0x140005189  mov     [rax], r8w
0x14000518d  add     rcx, 2
0x140005191  add     rax, 2
0x140005195  dec     r9
0x140005198  sub     rdx, 1; unsigned __int64
0x14000519c  jnz     short loc_14000517A
0x14000519e  test    rdx, rdx
0x1400051a1  lea     rcx, [rax-2]
0x1400051a5  lea     r8, aP0; "_p0"
0x1400051ac  cmovnz  rcx, rax
0x1400051b0  mov     [rcx], r15w
0x1400051b4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400051b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400051be  mov     esi, 1F0003h
0x1400051c3  lea     r8, [rsp+280h+Name]; lpName
0x1400051c8  mov     ecx, esi; dwDesiredAccess
0x1400051ca  xor     edx, edx; bInheritHandle
0x1400051cc  call    cs:__imp_OpenSemaphoreW
0x1400051d2  mov     rbx, rax
0x1400051d5  test    rax, rax
0x1400051d8  jz      loc_1400052F9
0x1400051de  lea     rdx, [rsp+280h+var_25C]; int *
0x1400051e3  mov     [rsp+280h+var_25C], r15d
0x1400051e8  mov     rcx, rax; hHandle
0x1400051eb  mov     [rsp+280h+var_260], r15d; int
0x1400051f0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400051f5  mov     edi, eax
0x1400051f7  test    eax, eax
0x1400051f9  jns     short loc_140005227
0x1400051fb  mov     rcx, [rbp+188h]; this
0x140005202  mov     r9d, eax; char *
0x140005205  mov     edx, 0D6h; void *
0x14000520a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000520f  mov     rcx, rbx; hObject
0x140005212  call    cs:__imp_CloseHandle
0x140005218  test    eax, eax
0x14000521a  jz      loc_14000536E
0x140005220  mov     eax, edi
0x140005222  jmp     loc_140005319
0x140005227  lea     r8, asc_140015AC8; "h"
0x14000522e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005233  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005238  lea     r8, [rsp+280h+Name]; lpName
0x14000523d  xor     edx, edx; bInheritHandle
0x14000523f  mov     ecx, esi; dwDesiredAccess
0x140005241  call    cs:__imp_OpenSemaphoreW
0x140005247  mov     rdi, rax
0x14000524a  test    rax, rax
0x14000524d  jz      loc_1400052D4
0x140005253  lea     rdx, [rsp+280h+var_260]; int *
0x140005258  mov     rcx, rax; hHandle
0x14000525b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005260  mov     esi, eax
0x140005262  test    eax, eax
0x140005264  jns     short loc_1400052A0
0x140005266  mov     rcx, [rbp+188h]; this
0x14000526d  mov     r9d, eax; char *
0x140005270  mov     edx, 0DEh; void *
0x140005275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000527a  mov     rcx, rdi; hObject
0x14000527d  call    cs:__imp_CloseHandle
0x140005283  test    eax, eax
0x140005285  jz      loc_140005380
0x14000528b  mov     rcx, rbx; hObject
0x14000528e  call    cs:__imp_CloseHandle
0x140005294  test    eax, eax
0x140005296  jz      loc_140005392
0x14000529c  mov     eax, esi
0x14000529e  jmp     short loc_140005319
0x1400052a0  mov     rcx, rdi; hObject
0x1400052a3  call    cs:__imp_CloseHandle
0x1400052a9  test    eax, eax
0x1400052ab  jz      loc_140005338
0x1400052b1  movsxd  rax, [rsp+280h+var_25C]
0x1400052b6  movsxd  rcx, [rsp+280h+var_260]
0x1400052bb  shl     rcx, 1Fh
0x1400052bf  or      rcx, rax
0x1400052c2  mov     [r14], rcx
0x1400052c5  mov     rcx, rbx; hObject
0x1400052c8  call    cs:__imp_CloseHandle
0x1400052ce  test    eax, eax
0x1400052d0  jz      short loc_14000534A
0x1400052d2  jmp     short loc_140005304
0x1400052d4  mov     rcx, [rbp+188h]; this
0x1400052db  mov     edx, 0DCh; void *
0x1400052e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400052e5  mov     rcx, rbx; hObject
0x1400052e8  mov     edi, eax
0x1400052ea  call    cs:__imp_CloseHandle
0x1400052f0  test    eax, eax
0x1400052f2  jz      short loc_14000535C
0x1400052f4  jmp     loc_140005220
0x1400052f9  call    cs:__imp_GetLastError
0x1400052ff  cmp     eax, 2
0x140005302  jnz     short loc_140005308
0x140005304  xor     eax, eax
0x140005306  jmp     short loc_140005319
0x140005308  mov     rcx, [rbp+188h]; this
0x14000530f  mov     edx, 0D0h; void *
0x140005314  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005319  mov     rcx, [rbp+180h+var_40]
0x140005320  xor     rcx, rsp; StackCookie
0x140005323  call    __security_check_cookie
0x140005328  add     rsp, 258h
0x14000532f  pop     r15
0x140005331  pop     r14
0x140005333  pop     rdi
0x140005334  pop     rsi
0x140005335  pop     rbx
0x140005336  pop     rbp
0x140005337  retn
0x140005338  mov     rcx, [rbp+188h]; this
0x14000533f  mov     edx, 0A0Bh; void *
0x140005344  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000534a  mov     rcx, [rbp+188h]; this
0x140005351  mov     edx, 0A0Bh; void *
0x140005356  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000535c  mov     rcx, [rbp+188h]; this
0x140005363  mov     edx, 0A0Bh; void *
0x140005368  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000536e  mov     rcx, [rbp+188h]; this
0x140005375  mov     edx, 0A0Bh; void *
0x14000537a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005380  mov     rcx, [rbp+188h]; this
0x140005387  mov     edx, 0A0Bh; void *
0x14000538c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005392  mov     rcx, [rbp+188h]; this
0x140005399  mov     edx, 0A0Bh; void *
0x14000539e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800066cc`
- end: `0x18000695b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ad0`
- `0x180008f1c`

## callees

- `0x180004d38`
- `0x180005c84`
- `0x180005ca4`
- `0x180006424`
- `0x1800066cc`
- `0x180006bb4`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006760`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800067dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006760`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800067dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000681f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006848`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000686d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000689a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000681f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006848`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000686d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000689a`

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
0x1800066cc  push    rbp
0x1800066ce  push    rbx
0x1800066cf  push    rsi
0x1800066d0  push    rdi
0x1800066d1  push    r14
0x1800066d3  push    r15
0x1800066d5  lea     rbp, [rsp-158h]
0x1800066dd  sub     rsp, 258h
0x1800066e4  mov     rax, cs:__security_cookie
0x1800066eb  xor     rax, rsp
0x1800066ee  mov     [rbp+180h+var_40], rax
0x1800066f5  xor     r15d, r15d
0x1800066f8  lea     rax, [rsp+280h+Name]
0x1800066fd  mov     [r8], r15
0x180006700  mov     r14, r8
0x180006703  mov     edx, 104h
0x180006708  mov     r9d, 7FFFFFFEh
0x18000670e  test    r9, r9
0x180006711  jz      short loc_180006732
0x180006713  movzx   r8d, word ptr [rcx]
0x180006717  test    r8w, r8w
0x18000671b  jz      short loc_180006732
0x18000671d  mov     [rax], r8w
0x180006721  add     rcx, 2
0x180006725  add     rax, 2
0x180006729  dec     r9
0x18000672c  sub     rdx, 1; unsigned __int64
0x180006730  jnz     short loc_18000670E
0x180006732  test    rdx, rdx
0x180006735  lea     rcx, [rax-2]
0x180006739  lea     r8, aP0; "_p0"
0x180006740  cmovnz  rcx, rax
0x180006744  mov     [rcx], r15w
0x180006748  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000674d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006752  mov     esi, 1F0003h
0x180006757  lea     r8, [rsp+280h+Name]; lpName
0x18000675c  mov     ecx, esi; dwDesiredAccess
0x18000675e  xor     edx, edx; bInheritHandle
0x180006760  call    cs:__imp_OpenSemaphoreW
0x180006766  mov     rbx, rax
0x180006769  test    rax, rax
0x18000676c  jz      loc_1800068A9
0x180006772  lea     rdx, [rsp+280h+var_25C]; int *
0x180006777  mov     [rsp+280h+var_25C], r15d
0x18000677c  mov     rcx, rax; hHandle
0x18000677f  mov     [rsp+280h+var_260], r15d; int
0x180006784  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006789  mov     edi, eax
0x18000678b  test    eax, eax
0x18000678d  jns     short loc_1800067C2
0x18000678f  mov     rcx, [rbp+188h]; this
0x180006796  lea     r8, aWil; "wil"
0x18000679d  mov     r9d, eax; char *
0x1800067a0  mov     edx, 0D6h; void *
0x1800067a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067aa  mov     rcx, rbx; hObject
0x1800067ad  call    cs:__imp_CloseHandle
0x1800067b3  test    eax, eax
0x1800067b5  jz      loc_180006925
0x1800067bb  mov     eax, edi
0x1800067bd  jmp     loc_1800068D0
0x1800067c2  lea     r8, asc_1800284A8; "h"
0x1800067c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800067ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800067d3  lea     r8, [rsp+280h+Name]; lpName
0x1800067d8  xor     edx, edx; bInheritHandle
0x1800067da  mov     ecx, esi; dwDesiredAccess
0x1800067dc  call    cs:__imp_OpenSemaphoreW
0x1800067e2  mov     rdi, rax
0x1800067e5  test    rax, rax
0x1800067e8  jz      loc_18000687D
0x1800067ee  lea     rdx, [rsp+280h+var_260]; int *
0x1800067f3  mov     rcx, rax; hHandle
0x1800067f6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800067fb  mov     esi, eax
0x1800067fd  test    eax, eax
0x1800067ff  jns     short loc_180006845
0x180006801  mov     rcx, [rbp+188h]; this
0x180006808  lea     r8, aWil; "wil"
0x18000680f  mov     r9d, eax; char *
0x180006812  mov     edx, 0DEh; void *
0x180006817  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000681c  mov     rcx, rdi; hObject
0x18000681f  call    cs:__imp_CloseHandle
0x180006825  test    eax, eax
0x180006827  jz      loc_180006937
0x18000682d  mov     rcx, rbx; hObject
0x180006830  call    cs:__imp_CloseHandle
0x180006836  test    eax, eax
0x180006838  jz      loc_180006949
0x18000683e  mov     eax, esi
0x180006840  jmp     loc_1800068D0
0x180006845  mov     rcx, rdi; hObject
0x180006848  call    cs:__imp_CloseHandle
0x18000684e  test    eax, eax
0x180006850  jz      loc_1800068EF
0x180006856  movsxd  rax, [rsp+280h+var_25C]
0x18000685b  movsxd  rcx, [rsp+280h+var_260]
0x180006860  shl     rcx, 1Fh
0x180006864  or      rcx, rax
0x180006867  mov     [r14], rcx
0x18000686a  mov     rcx, rbx; hObject
0x18000686d  call    cs:__imp_CloseHandle
0x180006873  test    eax, eax
0x180006875  jz      loc_180006901
0x18000687b  jmp     short loc_1800068B4
0x18000687d  mov     rcx, [rbp+188h]; this
0x180006884  lea     r8, aWil; "wil"
0x18000688b  mov     edx, 0DCh; void *
0x180006890  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006895  mov     rcx, rbx; hObject
0x180006898  mov     edi, eax
0x18000689a  call    cs:__imp_CloseHandle
0x1800068a0  test    eax, eax
0x1800068a2  jz      short loc_180006913
0x1800068a4  jmp     loc_1800067BB
0x1800068a9  call    cs:__imp_GetLastError
0x1800068af  cmp     eax, 2
0x1800068b2  jnz     short loc_1800068B8
0x1800068b4  xor     eax, eax
0x1800068b6  jmp     short loc_1800068D0
0x1800068b8  mov     rcx, [rbp+188h]; this
0x1800068bf  lea     r8, aWil; "wil"
0x1800068c6  mov     edx, 0D0h; void *
0x1800068cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800068d0  mov     rcx, [rbp+180h+var_40]
0x1800068d7  xor     rcx, rsp; StackCookie
0x1800068da  call    __security_check_cookie
0x1800068df  add     rsp, 258h
0x1800068e6  pop     r15
0x1800068e8  pop     r14
0x1800068ea  pop     rdi
0x1800068eb  pop     rsi
0x1800068ec  pop     rbx
0x1800068ed  pop     rbp
0x1800068ee  retn
0x1800068ef  mov     rcx, [rbp+188h]; this
0x1800068f6  mov     edx, 0A0Bh; void *
0x1800068fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006901  mov     rcx, [rbp+188h]; this
0x180006908  mov     edx, 0A0Bh; void *
0x18000690d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006913  mov     rcx, [rbp+188h]; this
0x18000691a  mov     edx, 0A0Bh; void *
0x18000691f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006925  mov     rcx, [rbp+188h]; this
0x18000692c  mov     edx, 0A0Bh; void *
0x180006931  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006937  mov     rcx, [rbp+188h]; this
0x18000693e  mov     edx, 0A0Bh; void *
0x180006943  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006949  mov     rcx, [rbp+188h]; this
0x180006950  mov     edx, 0A0Bh; void *
0x180006955  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

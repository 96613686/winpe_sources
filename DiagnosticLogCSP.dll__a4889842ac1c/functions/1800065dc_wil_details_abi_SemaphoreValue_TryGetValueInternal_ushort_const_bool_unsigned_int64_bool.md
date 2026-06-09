# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800065dc`
- end: `0x18000685f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800040e8`

## callees

- `0x180001b60`
- `0x180005074`
- `0x180005ae4`
- `0x180005b04`
- `0x1800063e0`
- `0x1800065dc`
- `0x1800069bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006673`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800066f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006673`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800066f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000675e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000675e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067a5`

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
  unsigned int v17; // r8d
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
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v34);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x1800065dc  push    rbp
0x1800065de  push    rbx
0x1800065df  push    rsi
0x1800065e0  push    rdi
0x1800065e1  push    r14
0x1800065e3  push    r15
0x1800065e5  lea     rbp, [rsp-158h]
0x1800065ed  sub     rsp, 258h
0x1800065f4  mov     rax, cs:__security_cookie
0x1800065fb  xor     rax, rsp
0x1800065fe  mov     [rbp+180h+var_40], rax
0x180006605  xor     r15d, r15d
0x180006608  lea     rax, [rsp+280h+Name]
0x18000660d  mov     esi, 104h
0x180006612  mov     [r8], r15
0x180006615  mov     edx, esi
0x180006617  mov     r14, r8
0x18000661a  mov     r9d, 7FFFFFFEh
0x180006620  test    r9, r9
0x180006623  jz      short loc_180006644
0x180006625  movzx   r8d, word ptr [rcx]
0x180006629  test    r8w, r8w
0x18000662d  jz      short loc_180006644
0x18000662f  mov     [rax], r8w
0x180006633  add     rcx, 2
0x180006637  add     rax, 2
0x18000663b  dec     r9
0x18000663e  sub     rdx, 1
0x180006642  jnz     short loc_180006620
0x180006644  test    rdx, rdx
0x180006647  lea     rcx, [rax-2]
0x18000664b  lea     r8, aP0; "_p0"
0x180006652  mov     rdx, rsi; unsigned __int64
0x180006655  cmovnz  rcx, rax
0x180006659  mov     [rcx], r15w
0x18000665d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006662  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006667  lea     r8, [rsp+280h+Name]; lpName
0x18000666c  xor     edx, edx; bInheritHandle
0x18000666e  mov     ecx, 1F0003h; dwDesiredAccess
0x180006673  call    cs:__imp_OpenSemaphoreW
0x180006679  mov     rbx, rax
0x18000667c  test    rax, rax
0x18000667f  jz      loc_1800067B4
0x180006685  lea     rdx, [rsp+280h+var_25C]; int *
0x18000668a  mov     [rsp+280h+var_25C], r15d
0x18000668f  mov     rcx, rax; hHandle
0x180006692  mov     [rsp+280h+var_260], r15d; int
0x180006697  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000669c  mov     edi, eax
0x18000669e  test    eax, eax
0x1800066a0  jns     short loc_1800066D5
0x1800066a2  mov     rcx, [rbp+188h]; this
0x1800066a9  lea     r8, aWil; "wil"
0x1800066b0  mov     r9d, eax; char *
0x1800066b3  mov     edx, 0D6h; void *
0x1800066b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066bd  mov     rcx, rbx; hObject
0x1800066c0  call    cs:__imp_CloseHandle
0x1800066c6  test    eax, eax
0x1800066c8  jz      loc_180006829
0x1800066ce  mov     eax, edi
0x1800066d0  jmp     loc_1800067D4
0x1800066d5  lea     r8, asc_18003B690; "h"
0x1800066dc  mov     rdx, rsi; unsigned __int64
0x1800066df  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800066e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800066e9  lea     r8, [rsp+280h+Name]; lpName
0x1800066ee  xor     edx, edx; bInheritHandle
0x1800066f0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800066f5  call    cs:__imp_OpenSemaphoreW
0x1800066fb  mov     rdi, rax
0x1800066fe  test    rax, rax
0x180006701  jz      loc_18000678F
0x180006707  lea     rdx, [rsp+280h+var_260]; int *
0x18000670c  mov     rcx, rax; hHandle
0x18000670f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006714  mov     esi, eax
0x180006716  test    eax, eax
0x180006718  jns     short loc_18000675B
0x18000671a  mov     rcx, [rbp+188h]; this
0x180006721  lea     r8, aWil; "wil"
0x180006728  mov     r9d, eax; char *
0x18000672b  mov     edx, 0DEh; void *
0x180006730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006735  mov     rcx, rdi; hObject
0x180006738  call    cs:__imp_CloseHandle
0x18000673e  test    eax, eax
0x180006740  jz      loc_18000683B
0x180006746  mov     rcx, rbx; hObject
0x180006749  call    cs:__imp_CloseHandle
0x18000674f  test    eax, eax
0x180006751  jz      loc_18000684D
0x180006757  mov     eax, esi
0x180006759  jmp     short loc_1800067D4
0x18000675b  mov     rcx, rdi; hObject
0x18000675e  call    cs:__imp_CloseHandle
0x180006764  test    eax, eax
0x180006766  jz      loc_1800067F3
0x18000676c  movsxd  rax, [rsp+280h+var_25C]
0x180006771  movsxd  rcx, [rsp+280h+var_260]
0x180006776  shl     rcx, 1Fh
0x18000677a  or      rcx, rax
0x18000677d  mov     [r14], rcx
0x180006780  mov     rcx, rbx; hObject
0x180006783  call    cs:__imp_CloseHandle
0x180006789  test    eax, eax
0x18000678b  jz      short loc_180006805
0x18000678d  jmp     short loc_1800067BF
0x18000678f  mov     rcx, [rbp+188h]; this
0x180006796  mov     edx, 0DCh; void *
0x18000679b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800067a0  mov     rcx, rbx; hObject
0x1800067a3  mov     edi, eax
0x1800067a5  call    cs:__imp_CloseHandle
0x1800067ab  test    eax, eax
0x1800067ad  jz      short loc_180006817
0x1800067af  jmp     loc_1800066CE
0x1800067b4  call    cs:__imp_GetLastError
0x1800067ba  cmp     eax, 2
0x1800067bd  jnz     short loc_1800067C3
0x1800067bf  xor     eax, eax
0x1800067c1  jmp     short loc_1800067D4
0x1800067c3  mov     rcx, [rbp+188h]; this
0x1800067ca  mov     edx, 0D0h; void *
0x1800067cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800067d4  mov     rcx, [rbp+180h+var_40]
0x1800067db  xor     rcx, rsp; StackCookie
0x1800067de  call    __security_check_cookie
0x1800067e3  add     rsp, 258h
0x1800067ea  pop     r15
0x1800067ec  pop     r14
0x1800067ee  pop     rdi
0x1800067ef  pop     rsi
0x1800067f0  pop     rbx
0x1800067f1  pop     rbp
0x1800067f2  retn
0x1800067f3  mov     rcx, [rbp+188h]; this
0x1800067fa  mov     edx, 0A0Bh; void *
0x1800067ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006805  mov     rcx, [rbp+188h]; this
0x18000680c  mov     edx, 0A0Bh; void *
0x180006811  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006817  mov     rcx, [rbp+188h]; this
0x18000681e  mov     edx, 0A0Bh; void *
0x180006823  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006829  mov     rcx, [rbp+188h]; this
0x180006830  mov     edx, 0A0Bh; void *
0x180006835  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000683b  mov     rcx, [rbp+188h]; this
0x180006842  mov     edx, 0A0Bh; void *
0x180006847  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000684d  mov     rcx, [rbp+188h]; this
0x180006854  mov     edx, 0A0Bh; void *
0x180006859  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

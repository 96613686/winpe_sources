# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800081ac`
- end: `0x180008426`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800038e8`

## callees

- `0x180001e60`
- `0x180005854`
- `0x180007694`
- `0x1800076b4`
- `0x180008044`
- `0x1800081ac`
- `0x180008864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008240`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008240`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000837b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000837b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000828d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000834a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000836c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000828d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000834a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000836c`

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
0x1800081ac  push    rbp
0x1800081ae  push    rbx
0x1800081af  push    rsi
0x1800081b0  push    rdi
0x1800081b1  push    r14
0x1800081b3  push    r15
0x1800081b5  lea     rbp, [rsp-158h]
0x1800081bd  sub     rsp, 258h
0x1800081c4  mov     rax, cs:__security_cookie
0x1800081cb  xor     rax, rsp
0x1800081ce  mov     [rbp+180h+var_40], rax
0x1800081d5  xor     r15d, r15d
0x1800081d8  lea     rax, [rsp+280h+Name]
0x1800081dd  mov     [r8], r15
0x1800081e0  mov     r14, r8
0x1800081e3  mov     edx, 104h
0x1800081e8  mov     r9d, 7FFFFFFEh
0x1800081ee  test    r9, r9
0x1800081f1  jz      short loc_180008212
0x1800081f3  movzx   r8d, word ptr [rcx]
0x1800081f7  test    r8w, r8w
0x1800081fb  jz      short loc_180008212
0x1800081fd  mov     [rax], r8w
0x180008201  add     rcx, 2
0x180008205  add     rax, 2
0x180008209  dec     r9
0x18000820c  sub     rdx, 1; unsigned __int64
0x180008210  jnz     short loc_1800081EE
0x180008212  test    rdx, rdx
0x180008215  lea     rcx, [rax-2]
0x180008219  lea     r8, aP0; "_p0"
0x180008220  cmovnz  rcx, rax
0x180008224  mov     [rcx], r15w
0x180008228  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000822d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008232  mov     esi, 1F0003h
0x180008237  lea     r8, [rsp+280h+Name]; lpName
0x18000823c  mov     ecx, esi; dwDesiredAccess
0x18000823e  xor     edx, edx; bInheritHandle
0x180008240  call    cs:__imp_OpenSemaphoreW
0x180008246  mov     rbx, rax
0x180008249  test    rax, rax
0x18000824c  jz      loc_18000837B
0x180008252  lea     rdx, [rsp+280h+var_25C]; int *
0x180008257  mov     [rsp+280h+var_25C], r15d
0x18000825c  mov     rcx, rax; hHandle
0x18000825f  mov     [rsp+280h+var_260], r15d; int
0x180008264  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008269  mov     edi, eax
0x18000826b  test    eax, eax
0x18000826d  jns     short loc_1800082A2
0x18000826f  mov     rcx, [rbp+188h]; this
0x180008276  lea     r8, aWil; "wil"
0x18000827d  mov     r9d, eax; char *
0x180008280  mov     edx, 0D6h; void *
0x180008285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000828a  mov     rcx, rbx; hObject
0x18000828d  call    cs:__imp_CloseHandle
0x180008293  test    eax, eax
0x180008295  jz      loc_1800083F0
0x18000829b  mov     eax, edi
0x18000829d  jmp     loc_18000839B
0x1800082a2  lea     r8, asc_18000DF90; "h"
0x1800082a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800082ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082b3  lea     r8, [rsp+280h+Name]; lpName
0x1800082b8  xor     edx, edx; bInheritHandle
0x1800082ba  mov     ecx, esi; dwDesiredAccess
0x1800082bc  call    cs:__imp_OpenSemaphoreW
0x1800082c2  mov     rdi, rax
0x1800082c5  test    rax, rax
0x1800082c8  jz      loc_180008356
0x1800082ce  lea     rdx, [rsp+280h+var_260]; int *
0x1800082d3  mov     rcx, rax; hHandle
0x1800082d6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800082db  mov     esi, eax
0x1800082dd  test    eax, eax
0x1800082df  jns     short loc_180008322
0x1800082e1  mov     rcx, [rbp+188h]; this
0x1800082e8  lea     r8, aWil; "wil"
0x1800082ef  mov     r9d, eax; char *
0x1800082f2  mov     edx, 0DEh; void *
0x1800082f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082fc  mov     rcx, rdi; hObject
0x1800082ff  call    cs:__imp_CloseHandle
0x180008305  test    eax, eax
0x180008307  jz      loc_180008402
0x18000830d  mov     rcx, rbx; hObject
0x180008310  call    cs:__imp_CloseHandle
0x180008316  test    eax, eax
0x180008318  jz      loc_180008414
0x18000831e  mov     eax, esi
0x180008320  jmp     short loc_18000839B
0x180008322  mov     rcx, rdi; hObject
0x180008325  call    cs:__imp_CloseHandle
0x18000832b  test    eax, eax
0x18000832d  jz      loc_1800083BA
0x180008333  movsxd  rax, [rsp+280h+var_25C]
0x180008338  movsxd  rcx, [rsp+280h+var_260]
0x18000833d  shl     rcx, 1Fh
0x180008341  or      rcx, rax
0x180008344  mov     [r14], rcx
0x180008347  mov     rcx, rbx; hObject
0x18000834a  call    cs:__imp_CloseHandle
0x180008350  test    eax, eax
0x180008352  jz      short loc_1800083CC
0x180008354  jmp     short loc_180008386
0x180008356  mov     rcx, [rbp+188h]; this
0x18000835d  mov     edx, 0DCh; void *
0x180008362  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008367  mov     rcx, rbx; hObject
0x18000836a  mov     edi, eax
0x18000836c  call    cs:__imp_CloseHandle
0x180008372  test    eax, eax
0x180008374  jz      short loc_1800083DE
0x180008376  jmp     loc_18000829B
0x18000837b  call    cs:__imp_GetLastError
0x180008381  cmp     eax, 2
0x180008384  jnz     short loc_18000838A
0x180008386  xor     eax, eax
0x180008388  jmp     short loc_18000839B
0x18000838a  mov     rcx, [rbp+188h]; this
0x180008391  mov     edx, 0D0h; void *
0x180008396  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000839b  mov     rcx, [rbp+180h+var_40]
0x1800083a2  xor     rcx, rsp; StackCookie
0x1800083a5  call    __security_check_cookie
0x1800083aa  add     rsp, 258h
0x1800083b1  pop     r15
0x1800083b3  pop     r14
0x1800083b5  pop     rdi
0x1800083b6  pop     rsi
0x1800083b7  pop     rbx
0x1800083b8  pop     rbp
0x1800083b9  retn
0x1800083ba  mov     rcx, [rbp+188h]; this
0x1800083c1  mov     edx, 0A0Bh; void *
0x1800083c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083cc  mov     rcx, [rbp+188h]; this
0x1800083d3  mov     edx, 0A0Bh; void *
0x1800083d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083de  mov     rcx, [rbp+188h]; this
0x1800083e5  mov     edx, 0A0Bh; void *
0x1800083ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083f0  mov     rcx, [rbp+188h]; this
0x1800083f7  mov     edx, 0A0Bh; void *
0x1800083fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008402  mov     rcx, [rbp+188h]; this
0x180008409  mov     edx, 0A0Bh; void *
0x18000840e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008414  mov     rcx, [rbp+188h]; this
0x18000841b  mov     edx, 0A0Bh; void *
0x180008420  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

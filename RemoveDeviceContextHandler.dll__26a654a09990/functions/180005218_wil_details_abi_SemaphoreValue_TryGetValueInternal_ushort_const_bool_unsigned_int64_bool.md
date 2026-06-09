# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005218`
- end: `0x180005484`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003758`

## callees

- `0x180004674`
- `0x180004da4`
- `0x180004dc4`
- `0x1800050dc`
- `0x180005218`
- `0x180005688`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005321`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000535d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000535d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053ca`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x180005218  push    rbp
0x18000521a  push    rbx
0x18000521b  push    rsi
0x18000521c  push    rdi
0x18000521d  push    r14
0x18000521f  push    r15
0x180005221  lea     rbp, [rsp-158h]
0x180005229  sub     rsp, 258h
0x180005230  mov     rax, cs:__security_cookie
0x180005237  xor     rax, rsp
0x18000523a  mov     [rbp+180h+var_40], rax
0x180005241  xor     r15d, r15d
0x180005244  lea     rax, [rsp+280h+Name]
0x180005249  mov     [r8], r15
0x18000524c  mov     r14, r8
0x18000524f  mov     edx, 104h
0x180005254  mov     r9d, 7FFFFFFEh
0x18000525a  test    r9, r9
0x18000525d  jz      short loc_18000527E
0x18000525f  movzx   r8d, word ptr [rcx]
0x180005263  test    r8w, r8w
0x180005267  jz      short loc_18000527E
0x180005269  mov     [rax], r8w
0x18000526d  add     rcx, 2
0x180005271  add     rax, 2
0x180005275  dec     r9
0x180005278  sub     rdx, 1; unsigned __int64
0x18000527c  jnz     short loc_18000525A
0x18000527e  test    rdx, rdx
0x180005281  lea     rcx, [rax-2]
0x180005285  lea     r8, aP0; "_p0"
0x18000528c  cmovnz  rcx, rax
0x180005290  mov     [rcx], r15w
0x180005294  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005299  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000529e  mov     esi, 1F0003h
0x1800052a3  lea     r8, [rsp+280h+Name]; lpName
0x1800052a8  mov     ecx, esi; dwDesiredAccess
0x1800052aa  xor     edx, edx; bInheritHandle
0x1800052ac  call    cs:__imp_OpenSemaphoreW
0x1800052b2  mov     rbx, rax
0x1800052b5  test    rax, rax
0x1800052b8  jz      loc_1800053D9
0x1800052be  lea     rdx, [rsp+280h+var_25C]; int *
0x1800052c3  mov     [rsp+280h+var_25C], r15d
0x1800052c8  mov     rcx, rax; hHandle
0x1800052cb  mov     [rsp+280h+var_260], r15d; int
0x1800052d0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800052d5  mov     edi, eax
0x1800052d7  test    eax, eax
0x1800052d9  jns     short loc_180005307
0x1800052db  mov     rcx, [rbp+188h]; this
0x1800052e2  mov     r9d, eax; char *
0x1800052e5  mov     edx, 0D6h; void *
0x1800052ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052ef  mov     rcx, rbx; hObject
0x1800052f2  call    cs:__imp_CloseHandle
0x1800052f8  test    eax, eax
0x1800052fa  jz      loc_18000544E
0x180005300  mov     eax, edi
0x180005302  jmp     loc_1800053F9
0x180005307  lea     r8, asc_1800100F0; "h"
0x18000530e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005313  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005318  lea     r8, [rsp+280h+Name]; lpName
0x18000531d  xor     edx, edx; bInheritHandle
0x18000531f  mov     ecx, esi; dwDesiredAccess
0x180005321  call    cs:__imp_OpenSemaphoreW
0x180005327  mov     rdi, rax
0x18000532a  test    rax, rax
0x18000532d  jz      loc_1800053B4
0x180005333  lea     rdx, [rsp+280h+var_260]; int *
0x180005338  mov     rcx, rax; hHandle
0x18000533b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005340  mov     esi, eax
0x180005342  test    eax, eax
0x180005344  jns     short loc_180005380
0x180005346  mov     rcx, [rbp+188h]; this
0x18000534d  mov     r9d, eax; char *
0x180005350  mov     edx, 0DEh; void *
0x180005355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000535a  mov     rcx, rdi; hObject
0x18000535d  call    cs:__imp_CloseHandle
0x180005363  test    eax, eax
0x180005365  jz      loc_180005460
0x18000536b  mov     rcx, rbx; hObject
0x18000536e  call    cs:__imp_CloseHandle
0x180005374  test    eax, eax
0x180005376  jz      loc_180005472
0x18000537c  mov     eax, esi
0x18000537e  jmp     short loc_1800053F9
0x180005380  mov     rcx, rdi; hObject
0x180005383  call    cs:__imp_CloseHandle
0x180005389  test    eax, eax
0x18000538b  jz      loc_180005418
0x180005391  movsxd  rax, [rsp+280h+var_25C]
0x180005396  movsxd  rcx, [rsp+280h+var_260]
0x18000539b  shl     rcx, 1Fh
0x18000539f  or      rcx, rax
0x1800053a2  mov     [r14], rcx
0x1800053a5  mov     rcx, rbx; hObject
0x1800053a8  call    cs:__imp_CloseHandle
0x1800053ae  test    eax, eax
0x1800053b0  jz      short loc_18000542A
0x1800053b2  jmp     short loc_1800053E4
0x1800053b4  mov     rcx, [rbp+188h]; this
0x1800053bb  mov     edx, 0DCh; void *
0x1800053c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800053c5  mov     rcx, rbx; hObject
0x1800053c8  mov     edi, eax
0x1800053ca  call    cs:__imp_CloseHandle
0x1800053d0  test    eax, eax
0x1800053d2  jz      short loc_18000543C
0x1800053d4  jmp     loc_180005300
0x1800053d9  call    cs:__imp_GetLastError
0x1800053df  cmp     eax, 2
0x1800053e2  jnz     short loc_1800053E8
0x1800053e4  xor     eax, eax
0x1800053e6  jmp     short loc_1800053F9
0x1800053e8  mov     rcx, [rbp+188h]; this
0x1800053ef  mov     edx, 0D0h; void *
0x1800053f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800053f9  mov     rcx, [rbp+180h+var_40]
0x180005400  xor     rcx, rsp; StackCookie
0x180005403  call    __security_check_cookie
0x180005408  add     rsp, 258h
0x18000540f  pop     r15
0x180005411  pop     r14
0x180005413  pop     rdi
0x180005414  pop     rsi
0x180005415  pop     rbx
0x180005416  pop     rbp
0x180005417  retn
0x180005418  mov     rcx, [rbp+188h]; this
0x18000541f  mov     edx, 0A0Bh; void *
0x180005424  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000542a  mov     rcx, [rbp+188h]; this
0x180005431  mov     edx, 0A0Bh; void *
0x180005436  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000543c  mov     rcx, [rbp+188h]; this
0x180005443  mov     edx, 0A0Bh; void *
0x180005448  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000544e  mov     rcx, [rbp+188h]; this
0x180005455  mov     edx, 0A0Bh; void *
0x18000545a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005460  mov     rcx, [rbp+188h]; this
0x180005467  mov     edx, 0A0Bh; void *
0x18000546c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005472  mov     rcx, [rbp+188h]; this
0x180005479  mov     edx, 0A0Bh; void *
0x18000547e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

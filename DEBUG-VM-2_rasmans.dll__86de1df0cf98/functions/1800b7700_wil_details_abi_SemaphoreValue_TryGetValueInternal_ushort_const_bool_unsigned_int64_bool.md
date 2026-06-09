# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800b7700`
- end: `0x1800b796c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800aed6c`
- `0x1800af110`

## callees

- `0x1800b2350`
- `0x1800b6e54`
- `0x1800b6e74`
- `0x1800b72f8`
- `0x1800b7700`
- `0x1800b7fbc`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b77da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b786b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b78b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b77da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b786b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b78b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b78c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b78c1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800b7794`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800b7809`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800b7794`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800b7809`

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
0x1800b7700  push    rbp
0x1800b7702  push    rbx
0x1800b7703  push    rsi
0x1800b7704  push    rdi
0x1800b7705  push    r14
0x1800b7707  push    r15
0x1800b7709  lea     rbp, [rsp-158h]
0x1800b7711  sub     rsp, 258h
0x1800b7718  mov     rax, cs:__security_cookie
0x1800b771f  xor     rax, rsp
0x1800b7722  mov     [rbp+180h+var_40], rax
0x1800b7729  xor     r15d, r15d
0x1800b772c  lea     rax, [rsp+280h+Name]
0x1800b7731  mov     [r8], r15
0x1800b7734  mov     r14, r8
0x1800b7737  mov     edx, 104h
0x1800b773c  mov     r9d, 7FFFFFFEh
0x1800b7742  test    r9, r9
0x1800b7745  jz      short loc_1800B7766
0x1800b7747  movzx   r8d, word ptr [rcx]
0x1800b774b  test    r8w, r8w
0x1800b774f  jz      short loc_1800B7766
0x1800b7751  mov     [rax], r8w
0x1800b7755  add     rcx, 2
0x1800b7759  add     rax, 2
0x1800b775d  dec     r9
0x1800b7760  sub     rdx, 1; unsigned __int64
0x1800b7764  jnz     short loc_1800B7742
0x1800b7766  test    rdx, rdx
0x1800b7769  lea     rcx, [rax-2]
0x1800b776d  lea     r8, aP0; "_p0"
0x1800b7774  cmovnz  rcx, rax
0x1800b7778  mov     [rcx], r15w
0x1800b777c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800b7781  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b7786  mov     esi, 1F0003h
0x1800b778b  lea     r8, [rsp+280h+Name]; lpName
0x1800b7790  mov     ecx, esi; dwDesiredAccess
0x1800b7792  xor     edx, edx; bInheritHandle
0x1800b7794  call    cs:__imp_OpenSemaphoreW
0x1800b779a  mov     rbx, rax
0x1800b779d  test    rax, rax
0x1800b77a0  jz      loc_1800B78C1
0x1800b77a6  lea     rdx, [rsp+280h+var_25C]; int *
0x1800b77ab  mov     [rsp+280h+var_25C], r15d
0x1800b77b0  mov     rcx, rax; hHandle
0x1800b77b3  mov     [rsp+280h+var_260], r15d; int
0x1800b77b8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800b77bd  mov     edi, eax
0x1800b77bf  test    eax, eax
0x1800b77c1  jns     short loc_1800B77EF
0x1800b77c3  mov     rcx, [rbp+188h]; this
0x1800b77ca  mov     r9d, eax; char *
0x1800b77cd  mov     edx, 0D6h; void *
0x1800b77d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b77d7  mov     rcx, rbx; hObject
0x1800b77da  call    cs:__imp_CloseHandle
0x1800b77e0  test    eax, eax
0x1800b77e2  jz      loc_1800B7936
0x1800b77e8  mov     eax, edi
0x1800b77ea  jmp     loc_1800B78E1
0x1800b77ef  lea     r8, asc_1800FA9B4; "h"
0x1800b77f6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800b77fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b7800  lea     r8, [rsp+280h+Name]; lpName
0x1800b7805  xor     edx, edx; bInheritHandle
0x1800b7807  mov     ecx, esi; dwDesiredAccess
0x1800b7809  call    cs:__imp_OpenSemaphoreW
0x1800b780f  mov     rdi, rax
0x1800b7812  test    rax, rax
0x1800b7815  jz      loc_1800B789C
0x1800b781b  lea     rdx, [rsp+280h+var_260]; int *
0x1800b7820  mov     rcx, rax; hHandle
0x1800b7823  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800b7828  mov     esi, eax
0x1800b782a  test    eax, eax
0x1800b782c  jns     short loc_1800B7868
0x1800b782e  mov     rcx, [rbp+188h]; this
0x1800b7835  mov     r9d, eax; char *
0x1800b7838  mov     edx, 0DEh; void *
0x1800b783d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7842  mov     rcx, rdi; hObject
0x1800b7845  call    cs:__imp_CloseHandle
0x1800b784b  test    eax, eax
0x1800b784d  jz      loc_1800B7948
0x1800b7853  mov     rcx, rbx; hObject
0x1800b7856  call    cs:__imp_CloseHandle
0x1800b785c  test    eax, eax
0x1800b785e  jz      loc_1800B795A
0x1800b7864  mov     eax, esi
0x1800b7866  jmp     short loc_1800B78E1
0x1800b7868  mov     rcx, rdi; hObject
0x1800b786b  call    cs:__imp_CloseHandle
0x1800b7871  test    eax, eax
0x1800b7873  jz      loc_1800B7900
0x1800b7879  movsxd  rax, [rsp+280h+var_25C]
0x1800b787e  movsxd  rcx, [rsp+280h+var_260]
0x1800b7883  shl     rcx, 1Fh
0x1800b7887  or      rcx, rax
0x1800b788a  mov     [r14], rcx
0x1800b788d  mov     rcx, rbx; hObject
0x1800b7890  call    cs:__imp_CloseHandle
0x1800b7896  test    eax, eax
0x1800b7898  jz      short loc_1800B7912
0x1800b789a  jmp     short loc_1800B78CC
0x1800b789c  mov     rcx, [rbp+188h]; this
0x1800b78a3  mov     edx, 0DCh; void *
0x1800b78a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b78ad  mov     rcx, rbx; hObject
0x1800b78b0  mov     edi, eax
0x1800b78b2  call    cs:__imp_CloseHandle
0x1800b78b8  test    eax, eax
0x1800b78ba  jz      short loc_1800B7924
0x1800b78bc  jmp     loc_1800B77E8
0x1800b78c1  call    cs:__imp_GetLastError
0x1800b78c7  cmp     eax, 2
0x1800b78ca  jnz     short loc_1800B78D0
0x1800b78cc  xor     eax, eax
0x1800b78ce  jmp     short loc_1800B78E1
0x1800b78d0  mov     rcx, [rbp+188h]; this
0x1800b78d7  mov     edx, 0D0h; void *
0x1800b78dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b78e1  mov     rcx, [rbp+180h+var_40]
0x1800b78e8  xor     rcx, rsp; StackCookie
0x1800b78eb  call    __security_check_cookie
0x1800b78f0  add     rsp, 258h
0x1800b78f7  pop     r15
0x1800b78f9  pop     r14
0x1800b78fb  pop     rdi
0x1800b78fc  pop     rsi
0x1800b78fd  pop     rbx
0x1800b78fe  pop     rbp
0x1800b78ff  retn
0x1800b7900  mov     rcx, [rbp+188h]; this
0x1800b7907  mov     edx, 0A0Bh; void *
0x1800b790c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b7912  mov     rcx, [rbp+188h]; this
0x1800b7919  mov     edx, 0A0Bh; void *
0x1800b791e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b7924  mov     rcx, [rbp+188h]; this
0x1800b792b  mov     edx, 0A0Bh; void *
0x1800b7930  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b7936  mov     rcx, [rbp+188h]; this
0x1800b793d  mov     edx, 0A0Bh; void *
0x1800b7942  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b7948  mov     rcx, [rbp+188h]; this
0x1800b794f  mov     edx, 0A0Bh; void *
0x1800b7954  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b795a  mov     rcx, [rbp+188h]; this
0x1800b7961  mov     edx, 0A0Bh; void *
0x1800b7966  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

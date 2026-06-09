# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000847c`
- end: `0x1800086e8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a78`
- `0x180003e1c`

## callees

- `0x180005490`
- `0x1800075a0`
- `0x1800075c0`
- `0x180008150`
- `0x18000847c`
- `0x180009484`
- `0x180013840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000863d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000863d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008510`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008585`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008510`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000860c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000862e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000860c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000862e`

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
0x18000847c  push    rbp
0x18000847e  push    rbx
0x18000847f  push    rsi
0x180008480  push    rdi
0x180008481  push    r14
0x180008483  push    r15
0x180008485  lea     rbp, [rsp-158h]
0x18000848d  sub     rsp, 258h
0x180008494  mov     rax, cs:__security_cookie
0x18000849b  xor     rax, rsp
0x18000849e  mov     [rbp+180h+var_40], rax
0x1800084a5  xor     r15d, r15d
0x1800084a8  lea     rax, [rsp+280h+Name]
0x1800084ad  mov     [r8], r15
0x1800084b0  mov     r14, r8
0x1800084b3  mov     edx, 104h
0x1800084b8  mov     r9d, 7FFFFFFEh
0x1800084be  test    r9, r9
0x1800084c1  jz      short loc_1800084E2
0x1800084c3  movzx   r8d, word ptr [rcx]
0x1800084c7  test    r8w, r8w
0x1800084cb  jz      short loc_1800084E2
0x1800084cd  mov     [rax], r8w
0x1800084d1  add     rcx, 2
0x1800084d5  add     rax, 2
0x1800084d9  dec     r9
0x1800084dc  sub     rdx, 1; unsigned __int64
0x1800084e0  jnz     short loc_1800084BE
0x1800084e2  test    rdx, rdx
0x1800084e5  lea     rcx, [rax-2]
0x1800084e9  lea     r8, aP0; "_p0"
0x1800084f0  cmovnz  rcx, rax
0x1800084f4  mov     [rcx], r15w
0x1800084f8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800084fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008502  mov     esi, 1F0003h
0x180008507  lea     r8, [rsp+280h+Name]; lpName
0x18000850c  mov     ecx, esi; dwDesiredAccess
0x18000850e  xor     edx, edx; bInheritHandle
0x180008510  call    cs:__imp_OpenSemaphoreW
0x180008516  mov     rbx, rax
0x180008519  test    rax, rax
0x18000851c  jz      loc_18000863D
0x180008522  lea     rdx, [rsp+280h+var_25C]; int *
0x180008527  mov     [rsp+280h+var_25C], r15d
0x18000852c  mov     rcx, rax; hHandle
0x18000852f  mov     [rsp+280h+var_260], r15d; int
0x180008534  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008539  mov     edi, eax
0x18000853b  test    eax, eax
0x18000853d  jns     short loc_18000856B
0x18000853f  mov     rcx, [rbp+188h]; this
0x180008546  mov     r9d, eax; char *
0x180008549  mov     edx, 0D6h; void *
0x18000854e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008553  mov     rcx, rbx; hObject
0x180008556  call    cs:__imp_CloseHandle
0x18000855c  test    eax, eax
0x18000855e  jz      loc_1800086B2
0x180008564  mov     eax, edi
0x180008566  jmp     loc_18000865D
0x18000856b  lea     r8, asc_180015FC0; "h"
0x180008572  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008577  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000857c  lea     r8, [rsp+280h+Name]; lpName
0x180008581  xor     edx, edx; bInheritHandle
0x180008583  mov     ecx, esi; dwDesiredAccess
0x180008585  call    cs:__imp_OpenSemaphoreW
0x18000858b  mov     rdi, rax
0x18000858e  test    rax, rax
0x180008591  jz      loc_180008618
0x180008597  lea     rdx, [rsp+280h+var_260]; int *
0x18000859c  mov     rcx, rax; hHandle
0x18000859f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800085a4  mov     esi, eax
0x1800085a6  test    eax, eax
0x1800085a8  jns     short loc_1800085E4
0x1800085aa  mov     rcx, [rbp+188h]; this
0x1800085b1  mov     r9d, eax; char *
0x1800085b4  mov     edx, 0DEh; void *
0x1800085b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085be  mov     rcx, rdi; hObject
0x1800085c1  call    cs:__imp_CloseHandle
0x1800085c7  test    eax, eax
0x1800085c9  jz      loc_1800086C4
0x1800085cf  mov     rcx, rbx; hObject
0x1800085d2  call    cs:__imp_CloseHandle
0x1800085d8  test    eax, eax
0x1800085da  jz      loc_1800086D6
0x1800085e0  mov     eax, esi
0x1800085e2  jmp     short loc_18000865D
0x1800085e4  mov     rcx, rdi; hObject
0x1800085e7  call    cs:__imp_CloseHandle
0x1800085ed  test    eax, eax
0x1800085ef  jz      loc_18000867C
0x1800085f5  movsxd  rax, [rsp+280h+var_25C]
0x1800085fa  movsxd  rcx, [rsp+280h+var_260]
0x1800085ff  shl     rcx, 1Fh
0x180008603  or      rcx, rax
0x180008606  mov     [r14], rcx
0x180008609  mov     rcx, rbx; hObject
0x18000860c  call    cs:__imp_CloseHandle
0x180008612  test    eax, eax
0x180008614  jz      short loc_18000868E
0x180008616  jmp     short loc_180008648
0x180008618  mov     rcx, [rbp+188h]; this
0x18000861f  mov     edx, 0DCh; void *
0x180008624  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008629  mov     rcx, rbx; hObject
0x18000862c  mov     edi, eax
0x18000862e  call    cs:__imp_CloseHandle
0x180008634  test    eax, eax
0x180008636  jz      short loc_1800086A0
0x180008638  jmp     loc_180008564
0x18000863d  call    cs:__imp_GetLastError
0x180008643  cmp     eax, 2
0x180008646  jnz     short loc_18000864C
0x180008648  xor     eax, eax
0x18000864a  jmp     short loc_18000865D
0x18000864c  mov     rcx, [rbp+188h]; this
0x180008653  mov     edx, 0D0h; void *
0x180008658  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000865d  mov     rcx, [rbp+180h+var_40]
0x180008664  xor     rcx, rsp; StackCookie
0x180008667  call    __security_check_cookie
0x18000866c  add     rsp, 258h
0x180008673  pop     r15
0x180008675  pop     r14
0x180008677  pop     rdi
0x180008678  pop     rsi
0x180008679  pop     rbx
0x18000867a  pop     rbp
0x18000867b  retn
0x18000867c  mov     rcx, [rbp+188h]; this
0x180008683  mov     edx, 0A0Bh; void *
0x180008688  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000868e  mov     rcx, [rbp+188h]; this
0x180008695  mov     edx, 0A0Bh; void *
0x18000869a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800086a0  mov     rcx, [rbp+188h]; this
0x1800086a7  mov     edx, 0A0Bh; void *
0x1800086ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800086b2  mov     rcx, [rbp+188h]; this
0x1800086b9  mov     edx, 0A0Bh; void *
0x1800086be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800086c4  mov     rcx, [rbp+188h]; this
0x1800086cb  mov     edx, 0A0Bh; void *
0x1800086d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800086d6  mov     rcx, [rbp+188h]; this
0x1800086dd  mov     edx, 0A0Bh; void *
0x1800086e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

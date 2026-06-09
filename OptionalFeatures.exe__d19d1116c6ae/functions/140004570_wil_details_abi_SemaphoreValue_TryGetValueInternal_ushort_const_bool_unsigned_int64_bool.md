# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140004570`
- end: `0x1400047dc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400024f4`

## callees

- `0x140003430`
- `0x140003e74`
- `0x140003e94`
- `0x140004144`
- `0x140004570`
- `0x14000493c`
- `0x140004ba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004731`
- `KERNEL32!GetLastError` at `0x140004731`
- `KERNEL32!OpenSemaphoreW` at `0x140004604`
- `KERNEL32!OpenSemaphoreW` at `0x140004679`
- `KERNEL32!OpenSemaphoreW` at `0x140004604`
- `KERNEL32!OpenSemaphoreW` at `0x140004679`
- `KERNEL32!CloseHandle` at `0x14000464a`
- `KERNEL32!CloseHandle` at `0x1400046b5`
- `KERNEL32!CloseHandle` at `0x1400046c6`
- `KERNEL32!CloseHandle` at `0x1400046db`
- `KERNEL32!CloseHandle` at `0x140004700`
- `KERNEL32!CloseHandle` at `0x140004722`
- `KERNEL32!CloseHandle` at `0x14000464a`
- `KERNEL32!CloseHandle` at `0x1400046b5`
- `KERNEL32!CloseHandle` at `0x1400046c6`
- `KERNEL32!CloseHandle` at `0x1400046db`
- `KERNEL32!CloseHandle` at `0x140004700`
- `KERNEL32!CloseHandle` at `0x140004722`

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
0x140004570  push    rbp
0x140004572  push    rbx
0x140004573  push    rsi
0x140004574  push    rdi
0x140004575  push    r14
0x140004577  push    r15
0x140004579  lea     rbp, [rsp-158h]
0x140004581  sub     rsp, 258h
0x140004588  mov     rax, cs:__security_cookie
0x14000458f  xor     rax, rsp
0x140004592  mov     [rbp+180h+var_40], rax
0x140004599  xor     r15d, r15d
0x14000459c  lea     rax, [rsp+280h+Name]
0x1400045a1  mov     [r8], r15
0x1400045a4  mov     r14, r8
0x1400045a7  mov     edx, 104h
0x1400045ac  mov     r9d, 7FFFFFFEh
0x1400045b2  test    r9, r9
0x1400045b5  jz      short loc_1400045D6
0x1400045b7  movzx   r8d, word ptr [rcx]
0x1400045bb  test    r8w, r8w
0x1400045bf  jz      short loc_1400045D6
0x1400045c1  mov     [rax], r8w
0x1400045c5  add     rcx, 2
0x1400045c9  add     rax, 2
0x1400045cd  dec     r9
0x1400045d0  sub     rdx, 1; unsigned __int64
0x1400045d4  jnz     short loc_1400045B2
0x1400045d6  test    rdx, rdx
0x1400045d9  lea     rcx, [rax-2]
0x1400045dd  lea     r8, aP0; "_p0"
0x1400045e4  cmovnz  rcx, rax
0x1400045e8  mov     [rcx], r15w
0x1400045ec  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400045f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400045f6  mov     esi, 1F0003h
0x1400045fb  lea     r8, [rsp+280h+Name]; lpName
0x140004600  mov     ecx, esi; dwDesiredAccess
0x140004602  xor     edx, edx; bInheritHandle
0x140004604  call    cs:__imp_OpenSemaphoreW
0x14000460a  mov     rbx, rax
0x14000460d  test    rax, rax
0x140004610  jz      loc_140004731
0x140004616  lea     rdx, [rsp+280h+var_25C]; int *
0x14000461b  mov     [rsp+280h+var_25C], r15d
0x140004620  mov     rcx, rax; hHandle
0x140004623  mov     [rsp+280h+var_260], r15d; int
0x140004628  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000462d  mov     edi, eax
0x14000462f  test    eax, eax
0x140004631  jns     short loc_14000465F
0x140004633  mov     rcx, [rbp+188h]; this
0x14000463a  mov     r9d, eax; char *
0x14000463d  mov     edx, 0D6h; void *
0x140004642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004647  mov     rcx, rbx; hObject
0x14000464a  call    cs:__imp_CloseHandle
0x140004650  test    eax, eax
0x140004652  jz      loc_1400047A6
0x140004658  mov     eax, edi
0x14000465a  jmp     loc_140004751
0x14000465f  lea     r8, asc_140006788; "h"
0x140004666  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000466b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004670  lea     r8, [rsp+280h+Name]; lpName
0x140004675  xor     edx, edx; bInheritHandle
0x140004677  mov     ecx, esi; dwDesiredAccess
0x140004679  call    cs:__imp_OpenSemaphoreW
0x14000467f  mov     rdi, rax
0x140004682  test    rax, rax
0x140004685  jz      loc_14000470C
0x14000468b  lea     rdx, [rsp+280h+var_260]; int *
0x140004690  mov     rcx, rax; hHandle
0x140004693  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140004698  mov     esi, eax
0x14000469a  test    eax, eax
0x14000469c  jns     short loc_1400046D8
0x14000469e  mov     rcx, [rbp+188h]; this
0x1400046a5  mov     r9d, eax; char *
0x1400046a8  mov     edx, 0DEh; void *
0x1400046ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400046b2  mov     rcx, rdi; hObject
0x1400046b5  call    cs:__imp_CloseHandle
0x1400046bb  test    eax, eax
0x1400046bd  jz      loc_1400047B8
0x1400046c3  mov     rcx, rbx; hObject
0x1400046c6  call    cs:__imp_CloseHandle
0x1400046cc  test    eax, eax
0x1400046ce  jz      loc_1400047CA
0x1400046d4  mov     eax, esi
0x1400046d6  jmp     short loc_140004751
0x1400046d8  mov     rcx, rdi; hObject
0x1400046db  call    cs:__imp_CloseHandle
0x1400046e1  test    eax, eax
0x1400046e3  jz      loc_140004770
0x1400046e9  movsxd  rax, [rsp+280h+var_25C]
0x1400046ee  movsxd  rcx, [rsp+280h+var_260]
0x1400046f3  shl     rcx, 1Fh
0x1400046f7  or      rcx, rax
0x1400046fa  mov     [r14], rcx
0x1400046fd  mov     rcx, rbx; hObject
0x140004700  call    cs:__imp_CloseHandle
0x140004706  test    eax, eax
0x140004708  jz      short loc_140004782
0x14000470a  jmp     short loc_14000473C
0x14000470c  mov     rcx, [rbp+188h]; this
0x140004713  mov     edx, 0DCh; void *
0x140004718  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000471d  mov     rcx, rbx; hObject
0x140004720  mov     edi, eax
0x140004722  call    cs:__imp_CloseHandle
0x140004728  test    eax, eax
0x14000472a  jz      short loc_140004794
0x14000472c  jmp     loc_140004658
0x140004731  call    cs:__imp_GetLastError
0x140004737  cmp     eax, 2
0x14000473a  jnz     short loc_140004740
0x14000473c  xor     eax, eax
0x14000473e  jmp     short loc_140004751
0x140004740  mov     rcx, [rbp+188h]; this
0x140004747  mov     edx, 0D0h; void *
0x14000474c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140004751  mov     rcx, [rbp+180h+var_40]
0x140004758  xor     rcx, rsp; StackCookie
0x14000475b  call    __security_check_cookie
0x140004760  add     rsp, 258h
0x140004767  pop     r15
0x140004769  pop     r14
0x14000476b  pop     rdi
0x14000476c  pop     rsi
0x14000476d  pop     rbx
0x14000476e  pop     rbp
0x14000476f  retn
0x140004770  mov     rcx, [rbp+188h]; this
0x140004777  mov     edx, 0A0Bh; void *
0x14000477c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004782  mov     rcx, [rbp+188h]; this
0x140004789  mov     edx, 0A0Bh; void *
0x14000478e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004794  mov     rcx, [rbp+188h]; this
0x14000479b  mov     edx, 0A0Bh; void *
0x1400047a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047a6  mov     rcx, [rbp+188h]; this
0x1400047ad  mov     edx, 0A0Bh; void *
0x1400047b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047b8  mov     rcx, [rbp+188h]; this
0x1400047bf  mov     edx, 0A0Bh; void *
0x1400047c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047ca  mov     rcx, [rbp+188h]; this
0x1400047d1  mov     edx, 0A0Bh; void *
0x1400047d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

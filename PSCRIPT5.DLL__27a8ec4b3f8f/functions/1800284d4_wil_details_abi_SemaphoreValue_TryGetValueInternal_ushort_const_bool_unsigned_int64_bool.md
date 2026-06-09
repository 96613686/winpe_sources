# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800284d4`
- end: `0x1800287a3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180024584`
- `0x180024960`

## callees

- `0x180001f20`
- `0x180020acc`
- `0x180025eac`
- `0x180027c54`
- `0x180027c74`
- `0x1800284d4`
- `0x180028d00`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18002856b`
- `KERNEL32!OpenSemaphoreW` at `0x1800285f9`
- `KERNEL32!OpenSemaphoreW` at `0x18002856b`
- `KERNEL32!OpenSemaphoreW` at `0x1800285f9`
- `KERNEL32!CloseHandle` at `0x1800285be`
- `KERNEL32!CloseHandle` at `0x180028642`
- `KERNEL32!CloseHandle` at `0x180028659`
- `KERNEL32!CloseHandle` at `0x180028677`
- `KERNEL32!CloseHandle` at `0x1800286a2`
- `KERNEL32!CloseHandle` at `0x1800286d5`
- `KERNEL32!CloseHandle` at `0x1800285be`
- `KERNEL32!CloseHandle` at `0x180028642`
- `KERNEL32!CloseHandle` at `0x180028659`
- `KERNEL32!CloseHandle` at `0x180028677`
- `KERNEL32!CloseHandle` at `0x1800286a2`
- `KERNEL32!CloseHandle` at `0x1800286d5`
- `KERNEL32!GetLastError` at `0x1800286ea`
- `KERNEL32!GetLastError` at `0x1800286ea`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  wchar_t *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t pszDest[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = pszDest;
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
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v31);
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
      (__int64)"wil",
      (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(pszDest, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (__int64)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x1800284d4  push    rbp
0x1800284d6  push    rbx
0x1800284d7  push    rsi
0x1800284d8  push    rdi
0x1800284d9  push    r14
0x1800284db  push    r15
0x1800284dd  lea     rbp, [rsp-158h]
0x1800284e5  sub     rsp, 258h
0x1800284ec  mov     rax, cs:__security_cookie
0x1800284f3  xor     rax, rsp
0x1800284f6  mov     [rbp+180h+var_40], rax
0x1800284fd  xor     r15d, r15d
0x180028500  lea     rax, [rsp+280h+pszDest]
0x180028505  mov     esi, 104h
0x18002850a  mov     [r8], r15
0x18002850d  mov     edx, esi
0x18002850f  mov     r14, r8
0x180028512  mov     r9d, 7FFFFFFEh
0x180028518  test    r9, r9
0x18002851b  jz      short loc_18002853C
0x18002851d  movzx   r8d, word ptr [rcx]
0x180028521  test    r8w, r8w
0x180028525  jz      short loc_18002853C
0x180028527  mov     [rax], r8w
0x18002852b  add     rcx, 2
0x18002852f  add     rax, 2
0x180028533  dec     r9
0x180028536  sub     rdx, 1
0x18002853a  jnz     short loc_180028518
0x18002853c  test    rdx, rdx
0x18002853f  lea     rcx, [rax-2]
0x180028543  lea     r8, aP0; "_p0"
0x18002854a  mov     rdx, rsi; cchDest
0x18002854d  cmovnz  rcx, rax
0x180028551  mov     [rcx], r15w
0x180028555  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18002855a  call    StringCchCatW
0x18002855f  lea     r8, [rsp+280h+pszDest]; lpName
0x180028564  xor     edx, edx; bInheritHandle
0x180028566  mov     ecx, 1F0003h; dwDesiredAccess
0x18002856b  call    cs:__imp_OpenSemaphoreW
0x180028572  nop     dword ptr [rax+rax+00h]
0x180028577  mov     rbx, rax
0x18002857a  test    rax, rax
0x18002857d  jz      loc_1800286EA
0x180028583  lea     rdx, [rsp+280h+var_25C]; int *
0x180028588  mov     [rsp+280h+var_25C], r15d
0x18002858d  mov     rcx, rax; hHandle
0x180028590  mov     [rsp+280h+var_260], r15d; int
0x180028595  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002859a  mov     edi, eax
0x18002859c  test    eax, eax
0x18002859e  jns     short loc_1800285D9
0x1800285a0  mov     rcx, [rbp+188h]; this
0x1800285a7  lea     r8, aWil; "wil"
0x1800285ae  mov     r9d, eax; char *
0x1800285b1  mov     edx, 0D6h; void *
0x1800285b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285bb  mov     rcx, rbx; hObject
0x1800285be  call    cs:__imp_CloseHandle
0x1800285c5  nop     dword ptr [rax+rax+00h]
0x1800285ca  test    eax, eax
0x1800285cc  jz      loc_18002876D
0x1800285d2  mov     eax, edi
0x1800285d4  jmp     loc_180028717
0x1800285d9  lea     r8, asc_180066DE0; "h"
0x1800285e0  mov     rdx, rsi; cchDest
0x1800285e3  lea     rcx, [rsp+280h+pszDest]; pszDest
0x1800285e8  call    StringCchCatW
0x1800285ed  lea     r8, [rsp+280h+pszDest]; lpName
0x1800285f2  xor     edx, edx; bInheritHandle
0x1800285f4  mov     ecx, 1F0003h; dwDesiredAccess
0x1800285f9  call    cs:__imp_OpenSemaphoreW
0x180028600  nop     dword ptr [rax+rax+00h]
0x180028605  mov     rdi, rax
0x180028608  test    rax, rax
0x18002860b  jz      loc_1800286B8
0x180028611  lea     rdx, [rsp+280h+var_260]; int *
0x180028616  mov     rcx, rax; hHandle
0x180028619  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002861e  mov     esi, eax
0x180028620  test    eax, eax
0x180028622  jns     short loc_180028674
0x180028624  mov     rcx, [rbp+188h]; this
0x18002862b  lea     r8, aWil; "wil"
0x180028632  mov     r9d, eax; char *
0x180028635  mov     edx, 0DEh; void *
0x18002863a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002863f  mov     rcx, rdi; hObject
0x180028642  call    cs:__imp_CloseHandle
0x180028649  nop     dword ptr [rax+rax+00h]
0x18002864e  test    eax, eax
0x180028650  jz      loc_18002877F
0x180028656  mov     rcx, rbx; hObject
0x180028659  call    cs:__imp_CloseHandle
0x180028660  nop     dword ptr [rax+rax+00h]
0x180028665  test    eax, eax
0x180028667  jz      loc_180028791
0x18002866d  mov     eax, esi
0x18002866f  jmp     loc_180028717
0x180028674  mov     rcx, rdi; hObject
0x180028677  call    cs:__imp_CloseHandle
0x18002867e  nop     dword ptr [rax+rax+00h]
0x180028683  test    eax, eax
0x180028685  jz      loc_180028737
0x18002868b  movsxd  rax, [rsp+280h+var_25C]
0x180028690  movsxd  rcx, [rsp+280h+var_260]
0x180028695  shl     rcx, 1Fh
0x180028699  or      rcx, rax
0x18002869c  mov     [r14], rcx
0x18002869f  mov     rcx, rbx; hObject
0x1800286a2  call    cs:__imp_CloseHandle
0x1800286a9  nop     dword ptr [rax+rax+00h]
0x1800286ae  test    eax, eax
0x1800286b0  jz      loc_180028749
0x1800286b6  jmp     short loc_1800286FB
0x1800286b8  mov     rcx, [rbp+188h]; this
0x1800286bf  lea     r8, aWil; "wil"
0x1800286c6  mov     edx, 0DCh; void *
0x1800286cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800286d0  mov     rcx, rbx; hObject
0x1800286d3  mov     edi, eax
0x1800286d5  call    cs:__imp_CloseHandle
0x1800286dc  nop     dword ptr [rax+rax+00h]
0x1800286e1  test    eax, eax
0x1800286e3  jz      short loc_18002875B
0x1800286e5  jmp     loc_1800285D2
0x1800286ea  call    cs:__imp_GetLastError
0x1800286f1  nop     dword ptr [rax+rax+00h]
0x1800286f6  cmp     eax, 2
0x1800286f9  jnz     short loc_1800286FF
0x1800286fb  xor     eax, eax
0x1800286fd  jmp     short loc_180028717
0x1800286ff  mov     rcx, [rbp+188h]; this
0x180028706  lea     r8, aWil; "wil"
0x18002870d  mov     edx, 0D0h; void *
0x180028712  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028717  mov     rcx, [rbp+180h+var_40]
0x18002871e  xor     rcx, rsp; StackCookie
0x180028721  call    __security_check_cookie
0x180028726  add     rsp, 258h
0x18002872d  pop     r15
0x18002872f  pop     r14
0x180028731  pop     rdi
0x180028732  pop     rsi
0x180028733  pop     rbx
0x180028734  pop     rbp
0x180028735  retn
0x180028737  mov     rcx, [rbp+188h]; this
0x18002873e  mov     edx, 0A0Bh; void *
0x180028743  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028749  mov     rcx, [rbp+188h]; this
0x180028750  mov     edx, 0A0Bh; void *
0x180028755  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002875b  mov     rcx, [rbp+188h]; this
0x180028762  mov     edx, 0A0Bh; void *
0x180028767  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002876d  mov     rcx, [rbp+188h]; this
0x180028774  mov     edx, 0A0Bh; void *
0x180028779  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002877f  mov     rcx, [rbp+188h]; this
0x180028786  mov     edx, 0A0Bh; void *
0x18002878b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028791  mov     rcx, [rbp+188h]; this
0x180028798  mov     edx, 0A0Bh; void *
0x18002879d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

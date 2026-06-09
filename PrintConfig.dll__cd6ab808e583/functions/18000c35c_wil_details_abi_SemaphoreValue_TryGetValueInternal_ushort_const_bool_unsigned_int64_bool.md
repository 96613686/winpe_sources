# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c35c`
- end: `0x18000c5f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006e28`
- `0x1800071fc`

## callees

- `0x1800032e0`
- `0x180008d60`
- `0x18000b274`
- `0x18000b29c`
- `0x18000be0c`
- `0x18000c35c`
- `0x18000ccf0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18000c3f3`
- `KERNEL32!OpenSemaphoreW` at `0x18000c475`
- `KERNEL32!OpenSemaphoreW` at `0x18000c3f3`
- `KERNEL32!OpenSemaphoreW` at `0x18000c475`
- `KERNEL32!CloseHandle` at `0x18000c440`
- `KERNEL32!CloseHandle` at `0x18000c4b8`
- `KERNEL32!CloseHandle` at `0x18000c4c9`
- `KERNEL32!CloseHandle` at `0x18000c4e1`
- `KERNEL32!CloseHandle` at `0x18000c506`
- `KERNEL32!CloseHandle` at `0x18000c533`
- `KERNEL32!CloseHandle` at `0x18000c440`
- `KERNEL32!CloseHandle` at `0x18000c4b8`
- `KERNEL32!CloseHandle` at `0x18000c4c9`
- `KERNEL32!CloseHandle` at `0x18000c4e1`
- `KERNEL32!CloseHandle` at `0x18000c506`
- `KERNEL32!CloseHandle` at `0x18000c533`
- `KERNEL32!GetLastError` at `0x18000c542`
- `KERNEL32!GetLastError` at `0x18000c542`

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
0x18000c35c  push    rbp
0x18000c35e  push    rbx
0x18000c35f  push    rsi
0x18000c360  push    rdi
0x18000c361  push    r14
0x18000c363  push    r15
0x18000c365  lea     rbp, [rsp-158h]
0x18000c36d  sub     rsp, 258h
0x18000c374  mov     rax, cs:__security_cookie
0x18000c37b  xor     rax, rsp
0x18000c37e  mov     [rbp+180h+var_40], rax
0x18000c385  xor     r15d, r15d
0x18000c388  lea     rax, [rsp+280h+Name]
0x18000c38d  mov     esi, 104h
0x18000c392  mov     [r8], r15
0x18000c395  mov     edx, esi
0x18000c397  mov     r14, r8
0x18000c39a  mov     r9d, 7FFFFFFEh
0x18000c3a0  test    r9, r9
0x18000c3a3  jz      short loc_18000C3C4
0x18000c3a5  movzx   r8d, word ptr [rcx]
0x18000c3a9  test    r8w, r8w
0x18000c3ad  jz      short loc_18000C3C4
0x18000c3af  mov     [rax], r8w
0x18000c3b3  add     rcx, 2
0x18000c3b7  add     rax, 2
0x18000c3bb  dec     r9
0x18000c3be  sub     rdx, 1
0x18000c3c2  jnz     short loc_18000C3A0
0x18000c3c4  test    rdx, rdx
0x18000c3c7  lea     rcx, [rax-2]
0x18000c3cb  lea     r8, aP0; "_p0"
0x18000c3d2  mov     rdx, rsi; unsigned __int64
0x18000c3d5  cmovnz  rcx, rax
0x18000c3d9  mov     [rcx], r15w
0x18000c3dd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c3e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c3e7  lea     r8, [rsp+280h+Name]; lpName
0x18000c3ec  xor     edx, edx; bInheritHandle
0x18000c3ee  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c3f3  call    cs:__imp_OpenSemaphoreW
0x18000c3f9  mov     rbx, rax
0x18000c3fc  test    rax, rax
0x18000c3ff  jz      loc_18000C542
0x18000c405  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c40a  mov     [rsp+280h+var_25C], r15d
0x18000c40f  mov     rcx, rax; hHandle
0x18000c412  mov     [rsp+280h+var_260], r15d; int
0x18000c417  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c41c  mov     edi, eax
0x18000c41e  test    eax, eax
0x18000c420  jns     short loc_18000C455
0x18000c422  mov     rcx, [rbp+188h]; this
0x18000c429  lea     r8, aWil; "wil"
0x18000c430  mov     r9d, eax; char *
0x18000c433  mov     edx, 0D6h; void *
0x18000c438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c43d  mov     rcx, rbx; hObject
0x18000c440  call    cs:__imp_CloseHandle
0x18000c446  test    eax, eax
0x18000c448  jz      loc_18000C5BE
0x18000c44e  mov     eax, edi
0x18000c450  jmp     loc_18000C569
0x18000c455  lea     r8, asc_1801DCF50; "h"
0x18000c45c  mov     rdx, rsi; unsigned __int64
0x18000c45f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c464  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c469  lea     r8, [rsp+280h+Name]; lpName
0x18000c46e  xor     edx, edx; bInheritHandle
0x18000c470  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c475  call    cs:__imp_OpenSemaphoreW
0x18000c47b  mov     rdi, rax
0x18000c47e  test    rax, rax
0x18000c481  jz      loc_18000C516
0x18000c487  lea     rdx, [rsp+280h+var_260]; int *
0x18000c48c  mov     rcx, rax; hHandle
0x18000c48f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c494  mov     esi, eax
0x18000c496  test    eax, eax
0x18000c498  jns     short loc_18000C4DE
0x18000c49a  mov     rcx, [rbp+188h]; this
0x18000c4a1  lea     r8, aWil; "wil"
0x18000c4a8  mov     r9d, eax; char *
0x18000c4ab  mov     edx, 0DEh; void *
0x18000c4b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c4b5  mov     rcx, rdi; hObject
0x18000c4b8  call    cs:__imp_CloseHandle
0x18000c4be  test    eax, eax
0x18000c4c0  jz      loc_18000C5D0
0x18000c4c6  mov     rcx, rbx; hObject
0x18000c4c9  call    cs:__imp_CloseHandle
0x18000c4cf  test    eax, eax
0x18000c4d1  jz      loc_18000C5E2
0x18000c4d7  mov     eax, esi
0x18000c4d9  jmp     loc_18000C569
0x18000c4de  mov     rcx, rdi; hObject
0x18000c4e1  call    cs:__imp_CloseHandle
0x18000c4e7  test    eax, eax
0x18000c4e9  jz      loc_18000C588
0x18000c4ef  movsxd  rax, [rsp+280h+var_25C]
0x18000c4f4  movsxd  rcx, [rsp+280h+var_260]
0x18000c4f9  shl     rcx, 1Fh
0x18000c4fd  or      rcx, rax
0x18000c500  mov     [r14], rcx
0x18000c503  mov     rcx, rbx; hObject
0x18000c506  call    cs:__imp_CloseHandle
0x18000c50c  test    eax, eax
0x18000c50e  jz      loc_18000C59A
0x18000c514  jmp     short loc_18000C54D
0x18000c516  mov     rcx, [rbp+188h]; this
0x18000c51d  lea     r8, aWil; "wil"
0x18000c524  mov     edx, 0DCh; void *
0x18000c529  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c52e  mov     rcx, rbx; hObject
0x18000c531  mov     edi, eax
0x18000c533  call    cs:__imp_CloseHandle
0x18000c539  test    eax, eax
0x18000c53b  jz      short loc_18000C5AC
0x18000c53d  jmp     loc_18000C44E
0x18000c542  call    cs:__imp_GetLastError
0x18000c548  cmp     eax, 2
0x18000c54b  jnz     short loc_18000C551
0x18000c54d  xor     eax, eax
0x18000c54f  jmp     short loc_18000C569
0x18000c551  mov     rcx, [rbp+188h]; this
0x18000c558  lea     r8, aWil; "wil"
0x18000c55f  mov     edx, 0D0h; void *
0x18000c564  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c569  mov     rcx, [rbp+180h+var_40]
0x18000c570  xor     rcx, rsp; StackCookie
0x18000c573  call    __security_check_cookie
0x18000c578  add     rsp, 258h
0x18000c57f  pop     r15
0x18000c581  pop     r14
0x18000c583  pop     rdi
0x18000c584  pop     rsi
0x18000c585  pop     rbx
0x18000c586  pop     rbp
0x18000c587  retn
0x18000c588  mov     rcx, [rbp+188h]; this
0x18000c58f  mov     edx, 0A0Bh; void *
0x18000c594  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c59a  mov     rcx, [rbp+188h]; this
0x18000c5a1  mov     edx, 0A0Bh; void *
0x18000c5a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c5ac  mov     rcx, [rbp+188h]; this
0x18000c5b3  mov     edx, 0A0Bh; void *
0x18000c5b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c5be  mov     rcx, [rbp+188h]; this
0x18000c5c5  mov     edx, 0A0Bh; void *
0x18000c5ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c5d0  mov     rcx, [rbp+188h]; this
0x18000c5d7  mov     edx, 0A0Bh; void *
0x18000c5dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c5e2  mov     rcx, [rbp+188h]; this
0x18000c5e9  mov     edx, 0A0Bh; void *
0x18000c5ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

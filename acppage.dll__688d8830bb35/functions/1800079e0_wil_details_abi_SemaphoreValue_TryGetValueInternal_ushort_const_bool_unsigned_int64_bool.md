# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800079e0`
- end: `0x180007c55`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800038a8`
- `0x180003c4c`

## callees

- `0x180005360`
- `0x180007254`
- `0x180007274`
- `0x1800079e0`
- `0x1800082d4`
- `0x180008878`
- `0x180016280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007baa`
- `KERNEL32!GetLastError` at `0x180007baa`
- `KERNEL32!OpenSemaphoreW` at `0x180007a77`
- `KERNEL32!OpenSemaphoreW` at `0x180007af2`
- `KERNEL32!OpenSemaphoreW` at `0x180007a77`
- `KERNEL32!OpenSemaphoreW` at `0x180007af2`
- `KERNEL32!CloseHandle` at `0x180007abd`
- `KERNEL32!CloseHandle` at `0x180007b2e`
- `KERNEL32!CloseHandle` at `0x180007b3f`
- `KERNEL32!CloseHandle` at `0x180007b54`
- `KERNEL32!CloseHandle` at `0x180007b79`
- `KERNEL32!CloseHandle` at `0x180007b9b`
- `KERNEL32!CloseHandle` at `0x180007abd`
- `KERNEL32!CloseHandle` at `0x180007b2e`
- `KERNEL32!CloseHandle` at `0x180007b3f`
- `KERNEL32!CloseHandle` at `0x180007b54`
- `KERNEL32!CloseHandle` at `0x180007b79`
- `KERNEL32!CloseHandle` at `0x180007b9b`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
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
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(pszDest, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x1800079e0  push    rbp
0x1800079e2  push    rbx
0x1800079e3  push    rsi
0x1800079e4  push    rdi
0x1800079e5  push    r14
0x1800079e7  push    r15
0x1800079e9  lea     rbp, [rsp-158h]
0x1800079f1  sub     rsp, 258h
0x1800079f8  mov     rax, cs:__security_cookie
0x1800079ff  xor     rax, rsp
0x180007a02  mov     [rbp+180h+var_40], rax
0x180007a09  xor     r15d, r15d
0x180007a0c  lea     rax, [rsp+280h+pszDest]
0x180007a11  mov     esi, 104h
0x180007a16  mov     [r8], r15
0x180007a19  mov     edx, esi
0x180007a1b  mov     r14, r8
0x180007a1e  mov     r9d, 7FFFFFFEh
0x180007a24  test    r9, r9
0x180007a27  jz      short loc_180007A48
0x180007a29  movzx   r8d, word ptr [rcx]
0x180007a2d  test    r8w, r8w
0x180007a31  jz      short loc_180007A48
0x180007a33  mov     [rax], r8w
0x180007a37  add     rcx, 2
0x180007a3b  add     rax, 2
0x180007a3f  dec     r9
0x180007a42  sub     rdx, 1
0x180007a46  jnz     short loc_180007A24
0x180007a48  test    rdx, rdx
0x180007a4b  lea     rcx, [rax-2]
0x180007a4f  lea     r8, aP0; "_p0"
0x180007a56  mov     rdx, rsi; cchDest
0x180007a59  cmovnz  rcx, rax
0x180007a5d  mov     [rcx], r15w
0x180007a61  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180007a66  call    StringCchCatW
0x180007a6b  lea     r8, [rsp+280h+pszDest]; lpName
0x180007a70  xor     edx, edx; bInheritHandle
0x180007a72  mov     ecx, 1F0003h; dwDesiredAccess
0x180007a77  call    cs:__imp_OpenSemaphoreW
0x180007a7d  mov     rbx, rax
0x180007a80  test    rax, rax
0x180007a83  jz      loc_180007BAA
0x180007a89  lea     rdx, [rsp+280h+var_25C]; int *
0x180007a8e  mov     [rsp+280h+var_25C], r15d
0x180007a93  mov     rcx, rax; hHandle
0x180007a96  mov     [rsp+280h+var_260], r15d; int
0x180007a9b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007aa0  mov     edi, eax
0x180007aa2  test    eax, eax
0x180007aa4  jns     short loc_180007AD2
0x180007aa6  mov     rcx, [rbp+188h]; this
0x180007aad  mov     r9d, eax; char *
0x180007ab0  mov     edx, 0D6h; void *
0x180007ab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007aba  mov     rcx, rbx; hObject
0x180007abd  call    cs:__imp_CloseHandle
0x180007ac3  test    eax, eax
0x180007ac5  jz      loc_180007C1F
0x180007acb  mov     eax, edi
0x180007acd  jmp     loc_180007BCA
0x180007ad2  lea     r8, asc_180019A28; "h"
0x180007ad9  mov     rdx, rsi; cchDest
0x180007adc  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180007ae1  call    StringCchCatW
0x180007ae6  lea     r8, [rsp+280h+pszDest]; lpName
0x180007aeb  xor     edx, edx; bInheritHandle
0x180007aed  mov     ecx, 1F0003h; dwDesiredAccess
0x180007af2  call    cs:__imp_OpenSemaphoreW
0x180007af8  mov     rdi, rax
0x180007afb  test    rax, rax
0x180007afe  jz      loc_180007B85
0x180007b04  lea     rdx, [rsp+280h+var_260]; int *
0x180007b09  mov     rcx, rax; hHandle
0x180007b0c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007b11  mov     esi, eax
0x180007b13  test    eax, eax
0x180007b15  jns     short loc_180007B51
0x180007b17  mov     rcx, [rbp+188h]; this
0x180007b1e  mov     r9d, eax; char *
0x180007b21  mov     edx, 0DEh; void *
0x180007b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b2b  mov     rcx, rdi; hObject
0x180007b2e  call    cs:__imp_CloseHandle
0x180007b34  test    eax, eax
0x180007b36  jz      loc_180007C31
0x180007b3c  mov     rcx, rbx; hObject
0x180007b3f  call    cs:__imp_CloseHandle
0x180007b45  test    eax, eax
0x180007b47  jz      loc_180007C43
0x180007b4d  mov     eax, esi
0x180007b4f  jmp     short loc_180007BCA
0x180007b51  mov     rcx, rdi; hObject
0x180007b54  call    cs:__imp_CloseHandle
0x180007b5a  test    eax, eax
0x180007b5c  jz      loc_180007BE9
0x180007b62  movsxd  rax, [rsp+280h+var_25C]
0x180007b67  movsxd  rcx, [rsp+280h+var_260]
0x180007b6c  shl     rcx, 1Fh
0x180007b70  or      rcx, rax
0x180007b73  mov     [r14], rcx
0x180007b76  mov     rcx, rbx; hObject
0x180007b79  call    cs:__imp_CloseHandle
0x180007b7f  test    eax, eax
0x180007b81  jz      short loc_180007BFB
0x180007b83  jmp     short loc_180007BB5
0x180007b85  mov     rcx, [rbp+188h]; this
0x180007b8c  mov     edx, 0DCh; void *
0x180007b91  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007b96  mov     rcx, rbx; hObject
0x180007b99  mov     edi, eax
0x180007b9b  call    cs:__imp_CloseHandle
0x180007ba1  test    eax, eax
0x180007ba3  jz      short loc_180007C0D
0x180007ba5  jmp     loc_180007ACB
0x180007baa  call    cs:__imp_GetLastError
0x180007bb0  cmp     eax, 2
0x180007bb3  jnz     short loc_180007BB9
0x180007bb5  xor     eax, eax
0x180007bb7  jmp     short loc_180007BCA
0x180007bb9  mov     rcx, [rbp+188h]; this
0x180007bc0  mov     edx, 0D0h; void *
0x180007bc5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007bca  mov     rcx, [rbp+180h+var_40]
0x180007bd1  xor     rcx, rsp; StackCookie
0x180007bd4  call    __security_check_cookie
0x180007bd9  add     rsp, 258h
0x180007be0  pop     r15
0x180007be2  pop     r14
0x180007be4  pop     rdi
0x180007be5  pop     rsi
0x180007be6  pop     rbx
0x180007be7  pop     rbp
0x180007be8  retn
0x180007be9  mov     rcx, [rbp+188h]; this
0x180007bf0  mov     edx, 0A0Bh; void *
0x180007bf5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bfb  mov     rcx, [rbp+188h]; this
0x180007c02  mov     edx, 0A0Bh; void *
0x180007c07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007c0d  mov     rcx, [rbp+188h]; this
0x180007c14  mov     edx, 0A0Bh; void *
0x180007c19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007c1f  mov     rcx, [rbp+188h]; this
0x180007c26  mov     edx, 0A0Bh; void *
0x180007c2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007c31  mov     rcx, [rbp+188h]; this
0x180007c38  mov     edx, 0A0Bh; void *
0x180007c3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007c43  mov     rcx, [rbp+188h]; this
0x180007c4a  mov     edx, 0A0Bh; void *
0x180007c4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

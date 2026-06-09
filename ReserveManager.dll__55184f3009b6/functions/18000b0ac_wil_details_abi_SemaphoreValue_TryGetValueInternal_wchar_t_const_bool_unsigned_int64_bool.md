# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b0ac`
- end: `0x18000b33b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800061c8`
- `0x180006598`

## callees

- `0x180003870`
- `0x180007e08`
- `0x18000a0cc`
- `0x18000a0f4`
- `0x18000ab70`
- `0x18000b0ac`
- `0x18000bf7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b140`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b1bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b140`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b1bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b18d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b24d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b27a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b18d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b24d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b27a`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000b0ac  push    rbp
0x18000b0ae  push    rbx
0x18000b0af  push    rsi
0x18000b0b0  push    rdi
0x18000b0b1  push    r14
0x18000b0b3  push    r15
0x18000b0b5  lea     rbp, [rsp-158h]
0x18000b0bd  sub     rsp, 258h
0x18000b0c4  mov     rax, cs:__security_cookie
0x18000b0cb  xor     rax, rsp
0x18000b0ce  mov     [rbp+180h+var_40], rax
0x18000b0d5  xor     r15d, r15d
0x18000b0d8  lea     rax, [rsp+280h+Name]
0x18000b0dd  mov     [r8], r15
0x18000b0e0  mov     r14, r8
0x18000b0e3  mov     edx, 104h
0x18000b0e8  mov     r9d, 7FFFFFFEh
0x18000b0ee  test    r9, r9
0x18000b0f1  jz      short loc_18000B112
0x18000b0f3  movzx   r8d, word ptr [rcx]
0x18000b0f7  test    r8w, r8w
0x18000b0fb  jz      short loc_18000B112
0x18000b0fd  mov     [rax], r8w
0x18000b101  add     rcx, 2
0x18000b105  add     rax, 2
0x18000b109  dec     r9
0x18000b10c  sub     rdx, 1; unsigned __int64
0x18000b110  jnz     short loc_18000B0EE
0x18000b112  test    rdx, rdx
0x18000b115  lea     rcx, [rax-2]
0x18000b119  lea     r8, aP0; "_p0"
0x18000b120  cmovnz  rcx, rax
0x18000b124  mov     [rcx], r15w
0x18000b128  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b12d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b132  mov     esi, 1F0003h
0x18000b137  lea     r8, [rsp+280h+Name]; lpName
0x18000b13c  mov     ecx, esi; dwDesiredAccess
0x18000b13e  xor     edx, edx; bInheritHandle
0x18000b140  call    cs:__imp_OpenSemaphoreW
0x18000b146  mov     rbx, rax
0x18000b149  test    rax, rax
0x18000b14c  jz      loc_18000B289
0x18000b152  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b157  mov     [rsp+280h+var_25C], r15d
0x18000b15c  mov     rcx, rax; hHandle
0x18000b15f  mov     [rsp+280h+var_260], r15d; int
0x18000b164  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b169  mov     edi, eax
0x18000b16b  test    eax, eax
0x18000b16d  jns     short loc_18000B1A2
0x18000b16f  mov     rcx, [rbp+188h]; this
0x18000b176  lea     r8, aWil; "wil"
0x18000b17d  mov     r9d, eax; char *
0x18000b180  mov     edx, 0D6h; void *
0x18000b185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b18a  mov     rcx, rbx; hObject
0x18000b18d  call    cs:__imp_CloseHandle
0x18000b193  test    eax, eax
0x18000b195  jz      loc_18000B305
0x18000b19b  mov     eax, edi
0x18000b19d  jmp     loc_18000B2B0
0x18000b1a2  lea     r8, asc_180036DD8; "h"
0x18000b1a9  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b1ae  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b1b3  lea     r8, [rsp+280h+Name]; lpName
0x18000b1b8  xor     edx, edx; bInheritHandle
0x18000b1ba  mov     ecx, esi; dwDesiredAccess
0x18000b1bc  call    cs:__imp_OpenSemaphoreW
0x18000b1c2  mov     rdi, rax
0x18000b1c5  test    rax, rax
0x18000b1c8  jz      loc_18000B25D
0x18000b1ce  lea     rdx, [rsp+280h+var_260]; int *
0x18000b1d3  mov     rcx, rax; hHandle
0x18000b1d6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b1db  mov     esi, eax
0x18000b1dd  test    eax, eax
0x18000b1df  jns     short loc_18000B225
0x18000b1e1  mov     rcx, [rbp+188h]; this
0x18000b1e8  lea     r8, aWil; "wil"
0x18000b1ef  mov     r9d, eax; char *
0x18000b1f2  mov     edx, 0DEh; void *
0x18000b1f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1fc  mov     rcx, rdi; hObject
0x18000b1ff  call    cs:__imp_CloseHandle
0x18000b205  test    eax, eax
0x18000b207  jz      loc_18000B317
0x18000b20d  mov     rcx, rbx; hObject
0x18000b210  call    cs:__imp_CloseHandle
0x18000b216  test    eax, eax
0x18000b218  jz      loc_18000B329
0x18000b21e  mov     eax, esi
0x18000b220  jmp     loc_18000B2B0
0x18000b225  mov     rcx, rdi; hObject
0x18000b228  call    cs:__imp_CloseHandle
0x18000b22e  test    eax, eax
0x18000b230  jz      loc_18000B2CF
0x18000b236  movsxd  rax, [rsp+280h+var_25C]
0x18000b23b  movsxd  rcx, [rsp+280h+var_260]
0x18000b240  shl     rcx, 1Fh
0x18000b244  or      rcx, rax
0x18000b247  mov     [r14], rcx
0x18000b24a  mov     rcx, rbx; hObject
0x18000b24d  call    cs:__imp_CloseHandle
0x18000b253  test    eax, eax
0x18000b255  jz      loc_18000B2E1
0x18000b25b  jmp     short loc_18000B294
0x18000b25d  mov     rcx, [rbp+188h]; this
0x18000b264  lea     r8, aWil; "wil"
0x18000b26b  mov     edx, 0DCh; void *
0x18000b270  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b275  mov     rcx, rbx; hObject
0x18000b278  mov     edi, eax
0x18000b27a  call    cs:__imp_CloseHandle
0x18000b280  test    eax, eax
0x18000b282  jz      short loc_18000B2F3
0x18000b284  jmp     loc_18000B19B
0x18000b289  call    cs:__imp_GetLastError
0x18000b28f  cmp     eax, 2
0x18000b292  jnz     short loc_18000B298
0x18000b294  xor     eax, eax
0x18000b296  jmp     short loc_18000B2B0
0x18000b298  mov     rcx, [rbp+188h]; this
0x18000b29f  lea     r8, aWil; "wil"
0x18000b2a6  mov     edx, 0D0h; void *
0x18000b2ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b2b0  mov     rcx, [rbp+180h+var_40]
0x18000b2b7  xor     rcx, rsp; StackCookie
0x18000b2ba  call    __security_check_cookie
0x18000b2bf  add     rsp, 258h
0x18000b2c6  pop     r15
0x18000b2c8  pop     r14
0x18000b2ca  pop     rdi
0x18000b2cb  pop     rsi
0x18000b2cc  pop     rbx
0x18000b2cd  pop     rbp
0x18000b2ce  retn
0x18000b2cf  mov     rcx, [rbp+188h]; this
0x18000b2d6  mov     edx, 0A0Bh; void *
0x18000b2db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2e1  mov     rcx, [rbp+188h]; this
0x18000b2e8  mov     edx, 0A0Bh; void *
0x18000b2ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2f3  mov     rcx, [rbp+188h]; this
0x18000b2fa  mov     edx, 0A0Bh; void *
0x18000b2ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b305  mov     rcx, [rbp+188h]; this
0x18000b30c  mov     edx, 0A0Bh; void *
0x18000b311  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b317  mov     rcx, [rbp+188h]; this
0x18000b31e  mov     edx, 0A0Bh; void *
0x18000b323  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b329  mov     rcx, [rbp+188h]; this
0x18000b330  mov     edx, 0A0Bh; void *
0x18000b335  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

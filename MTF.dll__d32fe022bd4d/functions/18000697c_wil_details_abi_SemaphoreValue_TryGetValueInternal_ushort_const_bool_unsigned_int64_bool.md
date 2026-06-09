# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000697c`
- end: `0x180006c0b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004010`
- `0x180009988`

## callees

- `0x180005098`
- `0x180006054`
- `0x180006074`
- `0x1800067f4`
- `0x18000697c`
- `0x180006f10`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a10`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a8c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a10`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b4a`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000697c  push    rbp
0x18000697e  push    rbx
0x18000697f  push    rsi
0x180006980  push    rdi
0x180006981  push    r14
0x180006983  push    r15
0x180006985  lea     rbp, [rsp-158h]
0x18000698d  sub     rsp, 258h
0x180006994  mov     rax, cs:__security_cookie
0x18000699b  xor     rax, rsp
0x18000699e  mov     [rbp+180h+var_40], rax
0x1800069a5  xor     r15d, r15d
0x1800069a8  lea     rax, [rsp+280h+Name]
0x1800069ad  mov     [r8], r15
0x1800069b0  mov     r14, r8
0x1800069b3  mov     edx, 104h
0x1800069b8  mov     r9d, 7FFFFFFEh
0x1800069be  test    r9, r9
0x1800069c1  jz      short loc_1800069E2
0x1800069c3  movzx   r8d, word ptr [rcx]
0x1800069c7  test    r8w, r8w
0x1800069cb  jz      short loc_1800069E2
0x1800069cd  mov     [rax], r8w
0x1800069d1  add     rcx, 2
0x1800069d5  add     rax, 2
0x1800069d9  dec     r9
0x1800069dc  sub     rdx, 1; unsigned __int64
0x1800069e0  jnz     short loc_1800069BE
0x1800069e2  test    rdx, rdx
0x1800069e5  lea     rcx, [rax-2]
0x1800069e9  lea     r8, aP0; "_p0"
0x1800069f0  cmovnz  rcx, rax
0x1800069f4  mov     [rcx], r15w
0x1800069f8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800069fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006a02  mov     esi, 1F0003h
0x180006a07  lea     r8, [rsp+280h+Name]; lpName
0x180006a0c  mov     ecx, esi; dwDesiredAccess
0x180006a0e  xor     edx, edx; bInheritHandle
0x180006a10  call    cs:__imp_OpenSemaphoreW
0x180006a16  mov     rbx, rax
0x180006a19  test    rax, rax
0x180006a1c  jz      loc_180006B59
0x180006a22  lea     rdx, [rsp+280h+var_25C]; int *
0x180006a27  mov     [rsp+280h+var_25C], r15d
0x180006a2c  mov     rcx, rax; hHandle
0x180006a2f  mov     [rsp+280h+var_260], r15d; int
0x180006a34  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006a39  mov     edi, eax
0x180006a3b  test    eax, eax
0x180006a3d  jns     short loc_180006A72
0x180006a3f  mov     rcx, [rbp+188h]; this
0x180006a46  lea     r8, aWil; "wil"
0x180006a4d  mov     r9d, eax; char *
0x180006a50  mov     edx, 0D6h; void *
0x180006a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a5a  mov     rcx, rbx; hObject
0x180006a5d  call    cs:__imp_CloseHandle
0x180006a63  test    eax, eax
0x180006a65  jz      loc_180006BD5
0x180006a6b  mov     eax, edi
0x180006a6d  jmp     loc_180006B80
0x180006a72  lea     r8, asc_180034058; "h"
0x180006a79  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006a7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006a83  lea     r8, [rsp+280h+Name]; lpName
0x180006a88  xor     edx, edx; bInheritHandle
0x180006a8a  mov     ecx, esi; dwDesiredAccess
0x180006a8c  call    cs:__imp_OpenSemaphoreW
0x180006a92  mov     rdi, rax
0x180006a95  test    rax, rax
0x180006a98  jz      loc_180006B2D
0x180006a9e  lea     rdx, [rsp+280h+var_260]; int *
0x180006aa3  mov     rcx, rax; hHandle
0x180006aa6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006aab  mov     esi, eax
0x180006aad  test    eax, eax
0x180006aaf  jns     short loc_180006AF5
0x180006ab1  mov     rcx, [rbp+188h]; this
0x180006ab8  lea     r8, aWil; "wil"
0x180006abf  mov     r9d, eax; char *
0x180006ac2  mov     edx, 0DEh; void *
0x180006ac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006acc  mov     rcx, rdi; hObject
0x180006acf  call    cs:__imp_CloseHandle
0x180006ad5  test    eax, eax
0x180006ad7  jz      loc_180006BE7
0x180006add  mov     rcx, rbx; hObject
0x180006ae0  call    cs:__imp_CloseHandle
0x180006ae6  test    eax, eax
0x180006ae8  jz      loc_180006BF9
0x180006aee  mov     eax, esi
0x180006af0  jmp     loc_180006B80
0x180006af5  mov     rcx, rdi; hObject
0x180006af8  call    cs:__imp_CloseHandle
0x180006afe  test    eax, eax
0x180006b00  jz      loc_180006B9F
0x180006b06  movsxd  rax, [rsp+280h+var_25C]
0x180006b0b  movsxd  rcx, [rsp+280h+var_260]
0x180006b10  shl     rcx, 1Fh
0x180006b14  or      rcx, rax
0x180006b17  mov     [r14], rcx
0x180006b1a  mov     rcx, rbx; hObject
0x180006b1d  call    cs:__imp_CloseHandle
0x180006b23  test    eax, eax
0x180006b25  jz      loc_180006BB1
0x180006b2b  jmp     short loc_180006B64
0x180006b2d  mov     rcx, [rbp+188h]; this
0x180006b34  lea     r8, aWil; "wil"
0x180006b3b  mov     edx, 0DCh; void *
0x180006b40  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006b45  mov     rcx, rbx; hObject
0x180006b48  mov     edi, eax
0x180006b4a  call    cs:__imp_CloseHandle
0x180006b50  test    eax, eax
0x180006b52  jz      short loc_180006BC3
0x180006b54  jmp     loc_180006A6B
0x180006b59  call    cs:__imp_GetLastError
0x180006b5f  cmp     eax, 2
0x180006b62  jnz     short loc_180006B68
0x180006b64  xor     eax, eax
0x180006b66  jmp     short loc_180006B80
0x180006b68  mov     rcx, [rbp+188h]; this
0x180006b6f  lea     r8, aWil; "wil"
0x180006b76  mov     edx, 0D0h; void *
0x180006b7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006b80  mov     rcx, [rbp+180h+var_40]
0x180006b87  xor     rcx, rsp; StackCookie
0x180006b8a  call    __security_check_cookie
0x180006b8f  add     rsp, 258h
0x180006b96  pop     r15
0x180006b98  pop     r14
0x180006b9a  pop     rdi
0x180006b9b  pop     rsi
0x180006b9c  pop     rbx
0x180006b9d  pop     rbp
0x180006b9e  retn
0x180006b9f  mov     rcx, [rbp+188h]; this
0x180006ba6  mov     edx, 0A0Bh; void *
0x180006bab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bb1  mov     rcx, [rbp+188h]; this
0x180006bb8  mov     edx, 0A0Bh; void *
0x180006bbd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bc3  mov     rcx, [rbp+188h]; this
0x180006bca  mov     edx, 0A0Bh; void *
0x180006bcf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bd5  mov     rcx, [rbp+188h]; this
0x180006bdc  mov     edx, 0A0Bh; void *
0x180006be1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006be7  mov     rcx, [rbp+188h]; this
0x180006bee  mov     edx, 0A0Bh; void *
0x180006bf3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bf9  mov     rcx, [rbp+188h]; this
0x180006c00  mov     edx, 0A0Bh; void *
0x180006c05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

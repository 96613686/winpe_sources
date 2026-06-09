# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800ebc8c`
- end: `0x1800ebf1b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800e6c08`
- `0x1800e6fe4`

## callees

- `0x180003060`
- `0x1800e86c8`
- `0x1800eabd4`
- `0x1800eabf4`
- `0x1800eb644`
- `0x1800ebc8c`
- `0x1800ec618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ebd20`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ebd9c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ebd20`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ebd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ebe69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ebe69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebd6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebdf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebe08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebe2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebe5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebd6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebdf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebe08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebe2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebe5a`

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
0x1800ebc8c  push    rbp
0x1800ebc8e  push    rbx
0x1800ebc8f  push    rsi
0x1800ebc90  push    rdi
0x1800ebc91  push    r14
0x1800ebc93  push    r15
0x1800ebc95  lea     rbp, [rsp-158h]
0x1800ebc9d  sub     rsp, 258h
0x1800ebca4  mov     rax, cs:__security_cookie
0x1800ebcab  xor     rax, rsp
0x1800ebcae  mov     [rbp+180h+var_40], rax
0x1800ebcb5  xor     r15d, r15d
0x1800ebcb8  lea     rax, [rsp+280h+Name]
0x1800ebcbd  mov     [r8], r15
0x1800ebcc0  mov     r14, r8
0x1800ebcc3  mov     edx, 104h
0x1800ebcc8  mov     r9d, 7FFFFFFEh
0x1800ebcce  test    r9, r9
0x1800ebcd1  jz      short loc_1800EBCF2
0x1800ebcd3  movzx   r8d, word ptr [rcx]
0x1800ebcd7  test    r8w, r8w
0x1800ebcdb  jz      short loc_1800EBCF2
0x1800ebcdd  mov     [rax], r8w
0x1800ebce1  add     rcx, 2
0x1800ebce5  add     rax, 2
0x1800ebce9  dec     r9
0x1800ebcec  sub     rdx, 1; unsigned __int64
0x1800ebcf0  jnz     short loc_1800EBCCE
0x1800ebcf2  test    rdx, rdx
0x1800ebcf5  lea     rcx, [rax-2]
0x1800ebcf9  lea     r8, aP0; "_p0"
0x1800ebd00  cmovnz  rcx, rax
0x1800ebd04  mov     [rcx], r15w
0x1800ebd08  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800ebd0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ebd12  mov     esi, 1F0003h
0x1800ebd17  lea     r8, [rsp+280h+Name]; lpName
0x1800ebd1c  mov     ecx, esi; dwDesiredAccess
0x1800ebd1e  xor     edx, edx; bInheritHandle
0x1800ebd20  call    cs:__imp_OpenSemaphoreW
0x1800ebd26  mov     rbx, rax
0x1800ebd29  test    rax, rax
0x1800ebd2c  jz      loc_1800EBE69
0x1800ebd32  lea     rdx, [rsp+280h+var_25C]; int *
0x1800ebd37  mov     [rsp+280h+var_25C], r15d
0x1800ebd3c  mov     rcx, rax; hHandle
0x1800ebd3f  mov     [rsp+280h+var_260], r15d; int
0x1800ebd44  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ebd49  mov     edi, eax
0x1800ebd4b  test    eax, eax
0x1800ebd4d  jns     short loc_1800EBD82
0x1800ebd4f  mov     rcx, [rbp+188h]; this
0x1800ebd56  lea     r8, aWil; "wil"
0x1800ebd5d  mov     r9d, eax; char *
0x1800ebd60  mov     edx, 0D6h; void *
0x1800ebd65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebd6a  mov     rcx, rbx; hObject
0x1800ebd6d  call    cs:__imp_CloseHandle
0x1800ebd73  test    eax, eax
0x1800ebd75  jz      loc_1800EBEE5
0x1800ebd7b  mov     eax, edi
0x1800ebd7d  jmp     loc_1800EBE90
0x1800ebd82  lea     r8, asc_1801223E0; "h"
0x1800ebd89  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800ebd8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ebd93  lea     r8, [rsp+280h+Name]; lpName
0x1800ebd98  xor     edx, edx; bInheritHandle
0x1800ebd9a  mov     ecx, esi; dwDesiredAccess
0x1800ebd9c  call    cs:__imp_OpenSemaphoreW
0x1800ebda2  mov     rdi, rax
0x1800ebda5  test    rax, rax
0x1800ebda8  jz      loc_1800EBE3D
0x1800ebdae  lea     rdx, [rsp+280h+var_260]; int *
0x1800ebdb3  mov     rcx, rax; hHandle
0x1800ebdb6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ebdbb  mov     esi, eax
0x1800ebdbd  test    eax, eax
0x1800ebdbf  jns     short loc_1800EBE05
0x1800ebdc1  mov     rcx, [rbp+188h]; this
0x1800ebdc8  lea     r8, aWil; "wil"
0x1800ebdcf  mov     r9d, eax; char *
0x1800ebdd2  mov     edx, 0DEh; void *
0x1800ebdd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebddc  mov     rcx, rdi; hObject
0x1800ebddf  call    cs:__imp_CloseHandle
0x1800ebde5  test    eax, eax
0x1800ebde7  jz      loc_1800EBEF7
0x1800ebded  mov     rcx, rbx; hObject
0x1800ebdf0  call    cs:__imp_CloseHandle
0x1800ebdf6  test    eax, eax
0x1800ebdf8  jz      loc_1800EBF09
0x1800ebdfe  mov     eax, esi
0x1800ebe00  jmp     loc_1800EBE90
0x1800ebe05  mov     rcx, rdi; hObject
0x1800ebe08  call    cs:__imp_CloseHandle
0x1800ebe0e  test    eax, eax
0x1800ebe10  jz      loc_1800EBEAF
0x1800ebe16  movsxd  rax, [rsp+280h+var_25C]
0x1800ebe1b  movsxd  rcx, [rsp+280h+var_260]
0x1800ebe20  shl     rcx, 1Fh
0x1800ebe24  or      rcx, rax
0x1800ebe27  mov     [r14], rcx
0x1800ebe2a  mov     rcx, rbx; hObject
0x1800ebe2d  call    cs:__imp_CloseHandle
0x1800ebe33  test    eax, eax
0x1800ebe35  jz      loc_1800EBEC1
0x1800ebe3b  jmp     short loc_1800EBE74
0x1800ebe3d  mov     rcx, [rbp+188h]; this
0x1800ebe44  lea     r8, aWil; "wil"
0x1800ebe4b  mov     edx, 0DCh; void *
0x1800ebe50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ebe55  mov     rcx, rbx; hObject
0x1800ebe58  mov     edi, eax
0x1800ebe5a  call    cs:__imp_CloseHandle
0x1800ebe60  test    eax, eax
0x1800ebe62  jz      short loc_1800EBED3
0x1800ebe64  jmp     loc_1800EBD7B
0x1800ebe69  call    cs:__imp_GetLastError
0x1800ebe6f  cmp     eax, 2
0x1800ebe72  jnz     short loc_1800EBE78
0x1800ebe74  xor     eax, eax
0x1800ebe76  jmp     short loc_1800EBE90
0x1800ebe78  mov     rcx, [rbp+188h]; this
0x1800ebe7f  lea     r8, aWil; "wil"
0x1800ebe86  mov     edx, 0D0h; void *
0x1800ebe8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ebe90  mov     rcx, [rbp+180h+var_40]
0x1800ebe97  xor     rcx, rsp; StackCookie
0x1800ebe9a  call    __security_check_cookie
0x1800ebe9f  add     rsp, 258h
0x1800ebea6  pop     r15
0x1800ebea8  pop     r14
0x1800ebeaa  pop     rdi
0x1800ebeab  pop     rsi
0x1800ebeac  pop     rbx
0x1800ebead  pop     rbp
0x1800ebeae  retn
0x1800ebeaf  mov     rcx, [rbp+188h]; this
0x1800ebeb6  mov     edx, 0A0Bh; void *
0x1800ebebb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800ebec1  mov     rcx, [rbp+188h]; this
0x1800ebec8  mov     edx, 0A0Bh; void *
0x1800ebecd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800ebed3  mov     rcx, [rbp+188h]; this
0x1800ebeda  mov     edx, 0A0Bh; void *
0x1800ebedf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800ebee5  mov     rcx, [rbp+188h]; this
0x1800ebeec  mov     edx, 0A0Bh; void *
0x1800ebef1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800ebef7  mov     rcx, [rbp+188h]; this
0x1800ebefe  mov     edx, 0A0Bh; void *
0x1800ebf03  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800ebf09  mov     rcx, [rbp+188h]; this
0x1800ebf10  mov     edx, 0A0Bh; void *
0x1800ebf15  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bc5c`
- end: `0x18000bedf`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009cd8`
- `0x180021c08`

## callees

- `0x18000ad10`
- `0x18000b740`
- `0x18000b760`
- `0x18000ba7c`
- `0x18000bc5c`
- `0x18000c03c`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bcf3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bd75`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bcf3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bd75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be25`

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
  unsigned int v17; // r8d
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
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v34);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000bc5c  push    rbp
0x18000bc5e  push    rbx
0x18000bc5f  push    rsi
0x18000bc60  push    rdi
0x18000bc61  push    r14
0x18000bc63  push    r15
0x18000bc65  lea     rbp, [rsp-158h]
0x18000bc6d  sub     rsp, 258h
0x18000bc74  mov     rax, cs:__security_cookie
0x18000bc7b  xor     rax, rsp
0x18000bc7e  mov     [rbp+180h+var_40], rax
0x18000bc85  xor     r15d, r15d
0x18000bc88  lea     rax, [rsp+280h+Name]
0x18000bc8d  mov     esi, 104h
0x18000bc92  mov     [r8], r15
0x18000bc95  mov     edx, esi
0x18000bc97  mov     r14, r8
0x18000bc9a  mov     r9d, 7FFFFFFEh
0x18000bca0  test    r9, r9
0x18000bca3  jz      short loc_18000BCC4
0x18000bca5  movzx   r8d, word ptr [rcx]
0x18000bca9  test    r8w, r8w
0x18000bcad  jz      short loc_18000BCC4
0x18000bcaf  mov     [rax], r8w
0x18000bcb3  add     rcx, 2
0x18000bcb7  add     rax, 2
0x18000bcbb  dec     r9
0x18000bcbe  sub     rdx, 1
0x18000bcc2  jnz     short loc_18000BCA0
0x18000bcc4  test    rdx, rdx
0x18000bcc7  lea     rcx, [rax-2]
0x18000bccb  lea     r8, aP0; "_p0"
0x18000bcd2  mov     rdx, rsi; unsigned __int64
0x18000bcd5  cmovnz  rcx, rax
0x18000bcd9  mov     [rcx], r15w
0x18000bcdd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bce2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bce7  lea     r8, [rsp+280h+Name]; lpName
0x18000bcec  xor     edx, edx; bInheritHandle
0x18000bcee  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bcf3  call    cs:__imp_OpenSemaphoreW
0x18000bcf9  mov     rbx, rax
0x18000bcfc  test    rax, rax
0x18000bcff  jz      loc_18000BE34
0x18000bd05  lea     rdx, [rsp+280h+var_25C]; int *
0x18000bd0a  mov     [rsp+280h+var_25C], r15d
0x18000bd0f  mov     rcx, rax; hHandle
0x18000bd12  mov     [rsp+280h+var_260], r15d; int
0x18000bd17  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bd1c  mov     edi, eax
0x18000bd1e  test    eax, eax
0x18000bd20  jns     short loc_18000BD55
0x18000bd22  mov     rcx, [rbp+188h]; this
0x18000bd29  lea     r8, aWil; "wil"
0x18000bd30  mov     r9d, eax; char *
0x18000bd33  mov     edx, 0D6h; void *
0x18000bd38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd3d  mov     rcx, rbx; hObject
0x18000bd40  call    cs:__imp_CloseHandle
0x18000bd46  test    eax, eax
0x18000bd48  jz      loc_18000BEA9
0x18000bd4e  mov     eax, edi
0x18000bd50  jmp     loc_18000BE54
0x18000bd55  lea     r8, asc_18009AB78; "h"
0x18000bd5c  mov     rdx, rsi; unsigned __int64
0x18000bd5f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bd64  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bd69  lea     r8, [rsp+280h+Name]; lpName
0x18000bd6e  xor     edx, edx; bInheritHandle
0x18000bd70  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bd75  call    cs:__imp_OpenSemaphoreW
0x18000bd7b  mov     rdi, rax
0x18000bd7e  test    rax, rax
0x18000bd81  jz      loc_18000BE0F
0x18000bd87  lea     rdx, [rsp+280h+var_260]; int *
0x18000bd8c  mov     rcx, rax; hHandle
0x18000bd8f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bd94  mov     esi, eax
0x18000bd96  test    eax, eax
0x18000bd98  jns     short loc_18000BDDB
0x18000bd9a  mov     rcx, [rbp+188h]; this
0x18000bda1  lea     r8, aWil; "wil"
0x18000bda8  mov     r9d, eax; char *
0x18000bdab  mov     edx, 0DEh; void *
0x18000bdb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdb5  mov     rcx, rdi; hObject
0x18000bdb8  call    cs:__imp_CloseHandle
0x18000bdbe  test    eax, eax
0x18000bdc0  jz      loc_18000BEBB
0x18000bdc6  mov     rcx, rbx; hObject
0x18000bdc9  call    cs:__imp_CloseHandle
0x18000bdcf  test    eax, eax
0x18000bdd1  jz      loc_18000BECD
0x18000bdd7  mov     eax, esi
0x18000bdd9  jmp     short loc_18000BE54
0x18000bddb  mov     rcx, rdi; hObject
0x18000bdde  call    cs:__imp_CloseHandle
0x18000bde4  test    eax, eax
0x18000bde6  jz      loc_18000BE73
0x18000bdec  movsxd  rax, [rsp+280h+var_25C]
0x18000bdf1  movsxd  rcx, [rsp+280h+var_260]
0x18000bdf6  shl     rcx, 1Fh
0x18000bdfa  or      rcx, rax
0x18000bdfd  mov     [r14], rcx
0x18000be00  mov     rcx, rbx; hObject
0x18000be03  call    cs:__imp_CloseHandle
0x18000be09  test    eax, eax
0x18000be0b  jz      short loc_18000BE85
0x18000be0d  jmp     short loc_18000BE3F
0x18000be0f  mov     rcx, [rbp+188h]; this
0x18000be16  mov     edx, 0DCh; void *
0x18000be1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000be20  mov     rcx, rbx; hObject
0x18000be23  mov     edi, eax
0x18000be25  call    cs:__imp_CloseHandle
0x18000be2b  test    eax, eax
0x18000be2d  jz      short loc_18000BE97
0x18000be2f  jmp     loc_18000BD4E
0x18000be34  call    cs:__imp_GetLastError
0x18000be3a  cmp     eax, 2
0x18000be3d  jnz     short loc_18000BE43
0x18000be3f  xor     eax, eax
0x18000be41  jmp     short loc_18000BE54
0x18000be43  mov     rcx, [rbp+188h]; this
0x18000be4a  mov     edx, 0D0h; void *
0x18000be4f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000be54  mov     rcx, [rbp+180h+var_40]
0x18000be5b  xor     rcx, rsp; StackCookie
0x18000be5e  call    __security_check_cookie
0x18000be63  add     rsp, 258h
0x18000be6a  pop     r15
0x18000be6c  pop     r14
0x18000be6e  pop     rdi
0x18000be6f  pop     rsi
0x18000be70  pop     rbx
0x18000be71  pop     rbp
0x18000be72  retn
0x18000be73  mov     rcx, [rbp+188h]; this
0x18000be7a  mov     edx, 0A0Bh; void *
0x18000be7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000be85  mov     rcx, [rbp+188h]; this
0x18000be8c  mov     edx, 0A0Bh; void *
0x18000be91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000be97  mov     rcx, [rbp+188h]; this
0x18000be9e  mov     edx, 0A0Bh; void *
0x18000bea3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bea9  mov     rcx, [rbp+188h]; this
0x18000beb0  mov     edx, 0A0Bh; void *
0x18000beb5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bebb  mov     rcx, [rbp+188h]; this
0x18000bec2  mov     edx, 0A0Bh; void *
0x18000bec7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000becd  mov     rcx, [rbp+188h]; this
0x18000bed4  mov     edx, 0A0Bh; void *
0x18000bed9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

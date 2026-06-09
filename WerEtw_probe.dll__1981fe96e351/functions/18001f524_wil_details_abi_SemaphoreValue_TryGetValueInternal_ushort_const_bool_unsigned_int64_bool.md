# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001f524`
- end: `0x18001f7a9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001be2c`

## callees

- `0x180001870`
- `0x18001d2d4`
- `0x18001e724`
- `0x18001e744`
- `0x18001f020`
- `0x18001f524`
- `0x18001f8fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f5bb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f63c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f5bb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f70b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f67e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f67e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // r9
  __int64 v6; // rdx
  WCHAR *v7; // rax
  WCHAR v8; // r8
  WCHAR *v9; // rcx
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
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
  int v38; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v39; // [rsp+28h] [rbp-D8h]
  HANDLE v40; // [rsp+30h] [rbp-D0h]
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v5 = 2147483646;
  v6 = 260;
  v7 = Name;
  do
  {
    if ( !v5 )
      break;
    v8 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v7++ = v8;
    --v5;
    --v6;
  }
  while ( v6 );
  v9 = v7 - 1;
  if ( v6 )
    v9 = v7;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  v39 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38 = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  v40 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38 | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18001f524  push    rbp
0x18001f526  push    rbx
0x18001f527  push    rsi
0x18001f528  push    rdi
0x18001f529  push    r14
0x18001f52b  push    r15
0x18001f52d  lea     rbp, [rsp-168h]
0x18001f535  sub     rsp, 268h
0x18001f53c  mov     rax, cs:__security_cookie
0x18001f543  xor     rax, rsp
0x18001f546  mov     [rbp+190h+var_40], rax
0x18001f54d  mov     r14, r8
0x18001f550  xor     r15d, r15d
0x18001f553  mov     [r8], r15
0x18001f556  mov     esi, 104h
0x18001f55b  mov     r9d, 7FFFFFFEh
0x18001f561  mov     edx, esi
0x18001f563  lea     rax, [rsp+290h+Name]
0x18001f568  test    r9, r9
0x18001f56b  jz      short loc_18001F58C
0x18001f56d  movzx   r8d, word ptr [rcx]
0x18001f571  test    r8w, r8w
0x18001f575  jz      short loc_18001F58C
0x18001f577  add     rcx, 2
0x18001f57b  mov     [rax], r8w
0x18001f57f  add     rax, 2
0x18001f583  dec     r9
0x18001f586  sub     rdx, 1
0x18001f58a  jnz     short loc_18001F568
0x18001f58c  lea     rcx, [rax-2]
0x18001f590  test    rdx, rdx
0x18001f593  cmovnz  rcx, rax
0x18001f597  mov     [rcx], r15w
0x18001f59b  lea     r8, aP0; "_p0"
0x18001f5a2  mov     rdx, rsi; unsigned __int64
0x18001f5a5  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18001f5aa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f5af  lea     r8, [rsp+290h+Name]; lpName
0x18001f5b4  xor     edx, edx; bInheritHandle
0x18001f5b6  mov     ecx, 1F0003h; dwDesiredAccess
0x18001f5bb  call    cs:__imp_OpenSemaphoreW
0x18001f5c1  mov     rbx, rax
0x18001f5c4  mov     [rsp+290h+var_268], rax
0x18001f5c9  test    rax, rax
0x18001f5cc  jz      loc_18001F70B
0x18001f5d2  mov     [rsp+290h+var_26C], r15d
0x18001f5d7  mov     [rsp+290h+var_270], r15d; int
0x18001f5dc  lea     rdx, [rsp+290h+var_26C]; int *
0x18001f5e1  mov     rcx, rax; hHandle
0x18001f5e4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001f5e9  mov     edi, eax
0x18001f5eb  test    eax, eax
0x18001f5ed  jns     short loc_18001F61C
0x18001f5ef  mov     rcx, [rbp+198h]; this
0x18001f5f6  mov     r9d, eax; char *
0x18001f5f9  mov     edx, 0D6h; void *
0x18001f5fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f603  nop
0x18001f604  mov     rcx, rbx; hObject
0x18001f607  call    cs:__imp_CloseHandle
0x18001f60d  test    eax, eax
0x18001f60f  jz      loc_18001F77A
0x18001f615  mov     eax, edi
0x18001f617  jmp     loc_18001F72C
0x18001f61c  lea     r8, asc_18002E858; "h"
0x18001f623  mov     rdx, rsi; unsigned __int64
0x18001f626  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18001f62b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f630  lea     r8, [rsp+290h+Name]; lpName
0x18001f635  xor     edx, edx; bInheritHandle
0x18001f637  mov     ecx, 1F0003h; dwDesiredAccess
0x18001f63c  call    cs:__imp_OpenSemaphoreW
0x18001f642  mov     rdi, rax
0x18001f645  mov     [rsp+290h+var_260], rax
0x18001f64a  test    rax, rax
0x18001f64d  jz      loc_18001F6E6
0x18001f653  lea     rdx, [rsp+290h+var_270]; int *
0x18001f658  mov     rcx, rax; hHandle
0x18001f65b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001f660  mov     esi, eax
0x18001f662  test    eax, eax
0x18001f664  jns     short loc_18001F6AB
0x18001f666  mov     rcx, [rbp+198h]; this
0x18001f66d  mov     r9d, eax; char *
0x18001f670  mov     edx, 0DEh; void *
0x18001f675  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f67a  nop
0x18001f67b  mov     rcx, rdi; hObject
0x18001f67e  call    cs:__imp_CloseHandle
0x18001f684  mov     rcx, [rbp+198h]; this
0x18001f68b  test    eax, eax
0x18001f68d  jz      loc_18001F78C
0x18001f693  mov     rcx, rbx; hObject
0x18001f696  call    cs:__imp_CloseHandle
0x18001f69c  test    eax, eax
0x18001f69e  jz      loc_18001F797
0x18001f6a4  mov     eax, esi
0x18001f6a6  jmp     loc_18001F72C
0x18001f6ab  mov     rcx, rdi; hObject
0x18001f6ae  call    cs:__imp_CloseHandle
0x18001f6b4  mov     rcx, [rbp+198h]; this
0x18001f6bb  test    eax, eax
0x18001f6bd  jz      loc_18001F74B
0x18001f6c3  movsxd  rcx, [rsp+290h+var_270]
0x18001f6c8  shl     rcx, 1Fh
0x18001f6cc  movsxd  rax, [rsp+290h+var_26C]
0x18001f6d1  or      rcx, rax
0x18001f6d4  mov     [r14], rcx
0x18001f6d7  mov     rcx, rbx; hObject
0x18001f6da  call    cs:__imp_CloseHandle
0x18001f6e0  test    eax, eax
0x18001f6e2  jz      short loc_18001F756
0x18001f6e4  jmp     short loc_18001F716
0x18001f6e6  mov     rcx, [rbp+198h]; this
0x18001f6ed  mov     edx, 0DCh; void *
0x18001f6f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f6f7  mov     edi, eax
0x18001f6f9  mov     rcx, rbx; hObject
0x18001f6fc  call    cs:__imp_CloseHandle
0x18001f702  test    eax, eax
0x18001f704  jz      short loc_18001F768
0x18001f706  jmp     loc_18001F615
0x18001f70b  call    cs:__imp_GetLastError
0x18001f711  cmp     eax, 2
0x18001f714  jnz     short loc_18001F71A
0x18001f716  xor     eax, eax
0x18001f718  jmp     short loc_18001F72C
0x18001f71a  mov     rcx, [rbp+198h]; this
0x18001f721  mov     edx, 0D0h; void *
0x18001f726  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f72b  nop
0x18001f72c  mov     rcx, [rbp+190h+var_40]
0x18001f733  xor     rcx, rsp; StackCookie
0x18001f736  call    __security_check_cookie
0x18001f73b  add     rsp, 268h
0x18001f742  pop     r15
0x18001f744  pop     r14
0x18001f746  pop     rdi
0x18001f747  pop     rsi
0x18001f748  pop     rbx
0x18001f749  pop     rbp
0x18001f74a  retn
0x18001f74b  mov     edx, 0A0Bh; void *
0x18001f750  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f756  mov     rcx, [rbp+198h]; this
0x18001f75d  mov     edx, 0A0Bh; void *
0x18001f762  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f768  mov     rcx, [rbp+198h]; this
0x18001f76f  mov     edx, 0A0Bh; void *
0x18001f774  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f77a  mov     rcx, [rbp+198h]; this
0x18001f781  mov     edx, 0A0Bh; void *
0x18001f786  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f78c  mov     edx, 0A0Bh; void *
0x18001f791  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f797  mov     rcx, [rbp+198h]; this
0x18001f79e  mov     edx, 0A0Bh; void *
0x18001f7a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# CSTRING::SetFromWideChar(ushort const *)

- ea: `0x18007149c`
- end: `0x18007161a`
- name: `?SetFromWideChar@CSTRING@@AEAAXPEBG@Z`
- size: `382`
- prototype: `void(CSTRING *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800711ec`

## callees

- `0x180006054`
- `0x18007149c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007150d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007150d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071587`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800714df`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007154a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800714df`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007154a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071504`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071527`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007156c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800715af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800715ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071504`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071527`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007156c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800715af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800715ed`

## pseudocode

```c
void __fastcall CSTRING::SetFromWideChar(CSTRING *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  int v5; // eax
  SIZE_T cbMultiByte; // rsi
  void *lpMultiByteStr; // rbx
  unsigned __int64 v8; // r15
  void *v9; // rsi

  if ( a2 )
  {
    v4 = -1;
    v5 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
    cbMultiByte = v5;
    if ( !v5 )
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    lpMultiByteStr = CoTaskMemAlloc(cbMultiByte);
    if ( !lpMultiByteStr )
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    if ( !WideCharToMultiByte(0, 0, a2, -1, (LPSTR)lpMultiByteStr, cbMultiByte, 0, 0) )
    {
      CoTaskMemFree(lpMultiByteStr);
      lpMultiByteStr = 0;
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    }
    do
      ++v4;
    while ( a2[v4] );
    v8 = (int)v4 + 1;
    v9 = CoTaskMemAlloc(2 * v8);
    if ( !v9 )
    {
      CoTaskMemFree(lpMultiByteStr);
      lpMultiByteStr = 0;
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    }
    if ( (int)StringCchCopyW((unsigned __int16 *)v9, v8, a2) < 0 )
    {
      CoTaskMemFree(lpMultiByteStr);
      CoTaskMemFree(v9);
      lpMultiByteStr = 0;
      v9 = 0;
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    }
  }
  else
  {
    v9 = 0;
    LODWORD(v4) = 0;
    lpMultiByteStr = 0;
  }
  *(_DWORD *)&this[1].Length = v4;
  this->Buffer = (const CHAR *)v9;
  *(_QWORD *)&this->Length = lpMultiByteStr;
}

```

## disassembly

```asm
0x18007149c  mov     rax, rsp
0x18007149f  push    rbx
0x1800714a0  push    rbp
0x1800714a1  push    rsi
0x1800714a2  push    rdi
0x1800714a3  push    r12
0x1800714a5  push    r13
0x1800714a7  push    r14
0x1800714a9  push    r15
0x1800714ab  sub     rsp, 48h
0x1800714af  xor     r12d, r12d
0x1800714b2  mov     rbp, rdx
0x1800714b5  mov     r14, rcx
0x1800714b8  test    rdx, rdx
0x1800714bb  jz      loc_1800715F5
0x1800714c1  mov     [rax-50h], r12
0x1800714c5  mov     r8, rdx; lpWideCharStr
0x1800714c8  mov     [rax-58h], r12
0x1800714cc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800714d0  mov     [rax-60h], r12d
0x1800714d4  mov     r9d, edi; cchWideChar
0x1800714d7  xor     edx, edx; dwFlags
0x1800714d9  mov     [rax-68h], r12
0x1800714dd  xor     ecx, ecx; CodePage
0x1800714df  call    cs:__imp_WideCharToMultiByte
0x1800714e5  movsxd  rsi, eax
0x1800714e8  mov     r13d, 0C0000025h
0x1800714ee  mov     r15d, 0C0000017h
0x1800714f4  test    eax, eax
0x1800714f6  jnz     short loc_18007150A
0x1800714f8  xor     r9d, r9d; lpArguments
0x1800714fb  xor     r8d, r8d; nNumberOfArguments
0x1800714fe  mov     edx, r13d; dwExceptionFlags
0x180071501  mov     ecx, r15d; dwExceptionCode
0x180071504  call    cs:__imp_RaiseException
0x18007150a  mov     rcx, rsi; cb
0x18007150d  call    cs:__imp_CoTaskMemAlloc
0x180071513  mov     rbx, rax
0x180071516  test    rax, rax
0x180071519  jnz     short loc_18007152D
0x18007151b  xor     r9d, r9d; lpArguments
0x18007151e  xor     r8d, r8d; nNumberOfArguments
0x180071521  mov     edx, r13d; dwExceptionFlags
0x180071524  mov     ecx, r15d; dwExceptionCode
0x180071527  call    cs:__imp_RaiseException
0x18007152d  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180071532  mov     r9d, edi; cchWideChar
0x180071535  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x18007153a  mov     r8, rbp; lpWideCharStr
0x18007153d  mov     [rsp+88h+cbMultiByte], esi; cbMultiByte
0x180071541  xor     edx, edx; dwFlags
0x180071543  xor     ecx, ecx; CodePage
0x180071545  mov     [rsp+88h+lpMultiByteStr], rbx; lpMultiByteStr
0x18007154a  call    cs:__imp_WideCharToMultiByte
0x180071550  test    eax, eax
0x180071552  jnz     short loc_180071572
0x180071554  mov     rcx, rbx; pv
0x180071557  call    cs:__imp_CoTaskMemFree
0x18007155d  xor     r9d, r9d; lpArguments
0x180071560  xor     r8d, r8d; nNumberOfArguments
0x180071563  mov     edx, r13d; dwExceptionFlags
0x180071566  mov     ecx, r15d; dwExceptionCode
0x180071569  mov     rbx, r12
0x18007156c  call    cs:__imp_RaiseException
0x180071572  inc     rdi
0x180071575  cmp     [rbp+rdi*2+0], r12w
0x18007157b  jnz     short loc_180071572
0x18007157d  lea     eax, [rdi+1]
0x180071580  movsxd  r15, eax
0x180071583  lea     rcx, [r15+r15]; cb
0x180071587  call    cs:__imp_CoTaskMemAlloc
0x18007158d  mov     rsi, rax
0x180071590  test    rax, rax
0x180071593  jnz     short loc_1800715B5
0x180071595  mov     rcx, rbx; pv
0x180071598  call    cs:__imp_CoTaskMemFree
0x18007159e  xor     r9d, r9d; lpArguments
0x1800715a1  xor     r8d, r8d; nNumberOfArguments
0x1800715a4  mov     edx, r13d; dwExceptionFlags
0x1800715a7  mov     ecx, 0C0000017h; dwExceptionCode
0x1800715ac  mov     rbx, r12
0x1800715af  call    cs:__imp_RaiseException
0x1800715b5  mov     r8, rbp; unsigned __int16 *
0x1800715b8  mov     rdx, r15; unsigned __int64
0x1800715bb  mov     rcx, rsi; unsigned __int16 *
0x1800715be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800715c3  test    eax, eax
0x1800715c5  jns     short loc_1800715FE
0x1800715c7  mov     rcx, rbx; pv
0x1800715ca  call    cs:__imp_CoTaskMemFree
0x1800715d0  mov     rcx, rsi; pv
0x1800715d3  call    cs:__imp_CoTaskMemFree
0x1800715d9  xor     r9d, r9d; lpArguments
0x1800715dc  xor     r8d, r8d; nNumberOfArguments
0x1800715df  mov     edx, r13d; dwExceptionFlags
0x1800715e2  mov     ecx, 0C0000017h; dwExceptionCode
0x1800715e7  mov     rbx, r12
0x1800715ea  mov     rsi, r12
0x1800715ed  call    cs:__imp_RaiseException
0x1800715f3  jmp     short loc_1800715FE
0x1800715f5  mov     rsi, r12
0x1800715f8  mov     edi, r12d
0x1800715fb  mov     rbx, r12
0x1800715fe  mov     [r14+10h], edi
0x180071602  mov     [r14+8], rsi
0x180071606  mov     [r14], rbx
0x180071609  add     rsp, 48h
0x18007160d  pop     r15
0x18007160f  pop     r14
0x180071611  pop     r13
0x180071613  pop     r12
0x180071615  pop     rdi
0x180071616  pop     rsi
0x180071617  pop     rbp
0x180071618  pop     rbx
0x180071619  retn
```

# DuplicateString(ushort const *,ushort * *)

- ea: `0x1800857c0`
- end: `0x18008589c`
- name: `?DuplicateString@@YAJPEBGPEAPEAG@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007d5b0`
- `0x180083214`
- `0x180087a2c`
- `0x180087c40`

## callees

- `0x180016f3c`
- `0x1800206c4`
- `0x1800846c0`
- `0x1800857c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008580b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008580b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008584d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008584d`

## string_xrefs

- `0x180085824`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x180085868`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x1800857d9`: `DuplicateString (com\complus\dtc\shared\util\stringutil.cpp@100): DuplicateString, ppwszDest != NULL`
- `0x18008582b`: `DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed`
- `0x18008586f`: `DuplicateString, StringCchCopyW failed`

## pseudocode

```c
__int64 __fastcall DuplicateString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  signed int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi
  signed int LastError; // eax

  if ( !a2 )
    DtcInternalErrorW(L"DuplicateString (com\\complus\\dtc\\shared\\util\\stringutil.cpp@100): DuplicateString, ppwszDest != NULL");
  *a2 = 0;
  v4 = 0;
  if ( a1 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    v6 = (unsigned int)(v5 + 1);
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
    v8 = v7;
    if ( !v7 )
    {
      v4 = -2147024882;
      TraceFileW(
        -2147024882,
        L"DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed",
        L"com\\complus\\dtc\\shared\\util\\stringutil.cpp",
        0x70u);
LABEL_12:
      CoTaskMemFree(v8);
      return (unsigned int)v4;
    }
    v4 = StringCchCopyW(v7, v6, a1);
    if ( v4 >= 0 )
    {
      *a2 = v8;
      return (unsigned int)v4;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    TraceFileW(v4, L"DuplicateString, StringCchCopyW failed", L"com\\complus\\dtc\\shared\\util\\stringutil.cpp", 0x77u);
    if ( v4 < 0 )
      goto LABEL_12;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800857c0  push    rbx
0x1800857c2  push    rbp
0x1800857c3  push    rsi
0x1800857c4  push    rdi
0x1800857c5  push    r14
0x1800857c7  sub     rsp, 20h
0x1800857cb  xor     r14d, r14d
0x1800857ce  mov     rdi, rdx
0x1800857d1  mov     rbp, rcx
0x1800857d4  test    rdx, rdx
0x1800857d7  jnz     short loc_1800857E6
0x1800857d9  lea     rcx, aDuplicatestrin_3; "DuplicateString (com\\complus\\dtc\\sha"...
0x1800857e0  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800857e6  mov     [rdx], r14
0x1800857e9  mov     ebx, r14d
0x1800857ec  test    rbp, rbp
0x1800857ef  jz      loc_18008588F
0x1800857f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800857f9  inc     rax
0x1800857fc  cmp     [rcx+rax*2], r14w
0x180085801  jnz     short loc_1800857F9
0x180085803  inc     eax
0x180085805  mov     ebx, eax
0x180085807  lea     rcx, [rax+rax]; cb
0x18008580b  call    cs:__imp_CoTaskMemAlloc
0x180085811  mov     rsi, rax
0x180085814  test    rax, rax
0x180085817  jnz     short loc_180085839
0x180085819  mov     ebx, 8007000Eh
0x18008581e  lea     r9d, [rax+70h]; unsigned int
0x180085822  mov     ecx, ebx; int
0x180085824  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18008582b  lea     rdx, aDuplicatestrin_1; "DuplicateString, CoTaskMemAlloc(dwSourc"...
0x180085832  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180085837  jmp     short loc_180085881
0x180085839  mov     r8, rbp; unsigned __int16 *
0x18008583c  mov     rdx, rbx; unsigned __int64
0x18008583f  mov     rcx, rsi; unsigned __int16 *
0x180085842  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180085847  mov     ebx, eax
0x180085849  test    eax, eax
0x18008584b  jns     short loc_18008588C
0x18008584d  call    cs:__imp_GetLastError
0x180085853  mov     ebx, eax
0x180085855  test    eax, eax
0x180085857  jle     short loc_180085862
0x180085859  movzx   ebx, ax
0x18008585c  or      ebx, 80070000h
0x180085862  mov     r9d, 77h ; 'w'; unsigned int
0x180085868  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18008586f  lea     rdx, aDuplicatestrin_2; "DuplicateString, StringCchCopyW failed"
0x180085876  mov     ecx, ebx; int
0x180085878  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18008587d  test    ebx, ebx
0x18008587f  jns     short loc_18008588F
0x180085881  mov     rcx, rsi; pv
0x180085884  call    cs:__imp_CoTaskMemFree
0x18008588a  jmp     short loc_18008588F
0x18008588c  mov     [rdi], rsi
0x18008588f  mov     eax, ebx
0x180085891  add     rsp, 20h
0x180085895  pop     r14
0x180085897  pop     rdi
0x180085898  pop     rsi
0x180085899  pop     rbp
0x18008589a  pop     rbx
0x18008589b  retn
```

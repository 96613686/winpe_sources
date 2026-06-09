# DuplicateString(ushort const *,ushort * *)

- ea: `0x180006324`
- end: `0x18000644b`
- name: `?DuplicateString@@YAJPEBGPEAPEAG@Z`
- size: `295`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `14`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006214`
- `0x180012774`
- `0x180014e80`
- `0x18001a9b8`
- `0x18001c410`
- `0x180052ab0`
- `0x180052ad0`
- `0x180052b90`
- `0x180052bb0`
- `0x180052d50`
- `0x18007007c`
- `0x180070290`
- `0x180076ce0`
- `0x180076de0`

## callees

- `0x180006324`
- `0x18000d5f4`
- `0x18001156c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000636e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000636e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ad`

## string_xrefs

- `0x180006387`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x1800063c8`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x1800063cf`: `DuplicateString, StringCchCopyW failed`
- `0x18000633e`: `DuplicateString (com\complus\dtc\shared\util\stringutil.cpp@100): DuplicateString, ppwszDest != NULL`
- `0x18000638e`: `DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed`

## pseudocode

```c
__int64 __fastcall DuplicateString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  const unsigned __int16 *v3; // rsi
  unsigned int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // rdi
  _WORD *v7; // rax
  void *v8; // r14
  signed int LastError; // eax
  __int64 v11; // rax
  _WORD *v12; // rdx
  _WORD *v13; // rcx

  v3 = a1;
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
    v7 = CoTaskMemAlloc(2 * v6);
    v8 = v7;
    if ( !v7 )
    {
      v4 = -2147024882;
      TraceFileW(
        -2147024882,
        L"DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed",
        L"com\\complus\\dtc\\shared\\util\\stringutil.cpp",
        0x70u);
LABEL_14:
      CoTaskMemFree(v8);
      return v4;
    }
    if ( v6 )
    {
      if ( v6 <= 0x7FFFFFFF )
      {
        v11 = 2147483646;
        v12 = v8;
        do
        {
          if ( !v11 )
            break;
          if ( !*v3 )
            break;
          *v12++ = *v3++;
          --v11;
          --v6;
        }
        while ( v6 );
        v13 = v12 - 1;
        v4 = v6 == 0 ? 0x8007007A : 0;
        if ( v6 )
          v13 = v12;
        *v13 = 0;
        if ( v6 )
        {
          *a2 = (unsigned __int16 *)v8;
          return v4;
        }
      }
      else
      {
        *v7 = 0;
      }
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    TraceFileW(v4, L"DuplicateString, StringCchCopyW failed", L"com\\complus\\dtc\\shared\\util\\stringutil.cpp", 0x77u);
    if ( (v4 & 0x80000000) != 0 )
      goto LABEL_14;
  }
  return v4;
}

```

## disassembly

```asm
0x180006324  push    rbx
0x180006326  push    rbp
0x180006327  push    rsi
0x180006328  push    rdi
0x180006329  push    r14
0x18000632b  push    r15
0x18000632d  sub     rsp, 28h
0x180006331  xor     ebp, ebp
0x180006333  mov     r15, rdx
0x180006336  mov     rsi, rcx
0x180006339  test    rdx, rdx
0x18000633c  jnz     short loc_18000634B
0x18000633e  lea     rcx, aDuplicatestrin_6; "DuplicateString (com\\complus\\dtc\\sha"...
0x180006345  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000634b  mov     [rdx], rbp
0x18000634e  mov     ebx, ebp
0x180006350  test    rcx, rcx
0x180006353  jz      loc_1800063EA
0x180006359  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000635d  inc     rax
0x180006360  cmp     [rcx+rax*2], bp
0x180006364  jnz     short loc_18000635D
0x180006366  inc     eax
0x180006368  mov     edi, eax
0x18000636a  lea     rcx, [rax+rax]; cb
0x18000636e  call    cs:__imp_CoTaskMemAlloc
0x180006374  mov     r14, rax
0x180006377  test    rax, rax
0x18000637a  jnz     short loc_18000639C
0x18000637c  mov     ebx, 8007000Eh
0x180006381  lea     r9d, [rax+70h]; unsigned int
0x180006385  mov     ecx, ebx; int
0x180006387  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18000638e  lea     rdx, aDuplicatestrin_3; "DuplicateString, CoTaskMemAlloc(dwSourc"...
0x180006395  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18000639a  jmp     short loc_1800063E1
0x18000639c  test    rdi, rdi
0x18000639f  jz      short loc_1800063AD
0x1800063a1  cmp     rdi, 7FFFFFFFh
0x1800063a8  jbe     short loc_1800063F9
0x1800063aa  mov     [rax], bp
0x1800063ad  call    cs:__imp_GetLastError
0x1800063b3  mov     ebx, eax
0x1800063b5  test    eax, eax
0x1800063b7  jle     short loc_1800063C2
0x1800063b9  movzx   ebx, ax
0x1800063bc  or      ebx, 80070000h
0x1800063c2  mov     r9d, 77h ; 'w'; unsigned int
0x1800063c8  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x1800063cf  lea     rdx, aDuplicatestrin_4; "DuplicateString, StringCchCopyW failed"
0x1800063d6  mov     ecx, ebx; int
0x1800063d8  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800063dd  test    ebx, ebx
0x1800063df  jns     short loc_1800063EA
0x1800063e1  mov     rcx, r14; pv
0x1800063e4  call    cs:__imp_CoTaskMemFree
0x1800063ea  mov     eax, ebx
0x1800063ec  add     rsp, 28h
0x1800063f0  pop     r15
0x1800063f2  pop     r14
0x1800063f4  pop     rdi
0x1800063f5  pop     rsi
0x1800063f6  pop     rbp
0x1800063f7  pop     rbx
0x1800063f8  retn
0x1800063f9  mov     eax, 7FFFFFFEh
0x1800063fe  mov     rdx, r14
0x180006401  test    rax, rax
0x180006404  jz      short loc_180006422
0x180006406  movzx   ecx, word ptr [rsi]
0x180006409  test    cx, cx
0x18000640c  jz      short loc_180006422
0x18000640e  mov     [rdx], cx
0x180006411  add     rsi, 2
0x180006415  add     rdx, 2
0x180006419  dec     rax
0x18000641c  sub     rdi, 1
0x180006420  jnz     short loc_180006401
0x180006422  mov     rax, rdi
0x180006425  lea     rcx, [rdx-2]
0x180006429  neg     rax
0x18000642c  sbb     ebx, ebx
0x18000642e  not     ebx
0x180006430  and     ebx, 8007007Ah
0x180006436  test    rdi, rdi
0x180006439  cmovnz  rcx, rdx
0x18000643d  mov     [rcx], bp
0x180006440  jz      loc_1800063AD
0x180006446  mov     [r15], r14
0x180006449  jmp     short loc_1800063EA
```
